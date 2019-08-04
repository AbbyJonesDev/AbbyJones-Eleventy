---
title:  "Cross Browser Date Picker"
date:   2015-02-25
summary: "This week I learned that Safari and Firefox handle date fields differently than Chrome. Chrome provides a really nice, native date picker, and it ensures that entries conform to the correct pattern. Safari and Firefox don't support date fields and treat them as regular text fields instead..."
tags: 
  - JavaScript
  - Rails
---
This week I learned that Safari and Firefox handle date fields differently than Chrome. Chrome provides a really nice, native date picker, and it ensures that entries conform to the correct pattern. Safari and Firefox don't support date fields and treat them as regular text fields instead.

<a href="http://jqueryui.com/" rel="nofollow">jQuery UI</a> provides a nice date picker that works across browsers. There's even a <a href="https://github.com/jhilden/jquery-ui-sass-rails" rel="nofollow">gem</a> for Rails with SASS support, and you can pull in just the modules that you want to use to keep the footprint small. Problem <em>almost</em> solved.

Using the datepicker from jQuery UI in Chrome created some weird behavior. It opened as expected, but selecting a date didn't populate the date field. <a href="http://tjvantoll.com/2012/06/30/creating-a-native-html5-datepicker-with-a-fallback-to-jquery-ui/" rel="nofollow">TJ VanToll's blog</a> describes a way to overcome this by using the native date picker in browsers that support it and falling back to the jQuery datepicker in browsers that don't. This method uses the <a href="http://modernizr.com/" rel="nofollow">Modernizr</a> library, which is included in <a href="http://getbootstrap.com/" rel="nofollow">Bootstrap</a> and <a href="http://foundation.zurb.com/" rel="nofollow">Foundation</a> out of the box.

The last step was writing some CSS rules to customize the look of the jQuery datepicker. The calendar is laid out as a table. Between the default Foundation styles for tables and the custom colors I'd defined for the site, the calendar looked pretty goofy and hard to read. I used DevTools to inspect the calendar and identify the classes jQuery assigned to key elements in the datepicker so I could style them.

The final result looks good and should be easy to use in any browser.

<em>Update: There was a bug I hadn't caught with how dates were submitted.  See <a href="{{ '/posts/2015-03-29-date-picker-part-two' | url}}">Date Picker Part Two</a> for more info and solution.</em>

``` ruby
# Gemfile 
gem 'jquery-ui-sass-rails'
// app/assets/javascripts/application.js
//= require jquery
//= require jquery_ujs
//= require jquery.ui.datepicker
//= require foundation
//= require_tree .
```

``` js
// app/assets/javascripts/admin/dashboard.js
if (!Modernizr.inputtypes.date) {
    $('input[type=date]').datepicker({
      dateFormat: 'mm-dd-yy'
    });
}
```

``` css
/* app/assets/stylesheets/application.css.scss
May look different for you - 
I import specific files individually for reasons
*/

@import "globals";
@import "static_pages";
@import "admin/dashboard";
@import "jquery.ui.datepicker"; 


// app/assets/stylesheets/admin/dashboard.css.scss
// Customizing look of the calendar

div.ui-datepicker-header {
  border: rem-calc(1px) solid $dark-blue;
}

.ui-datepicker-next {
  left: 82%;
}

table.ui-datepicker-calendar {
  border: rem-calc(1px) solid $dark-blue;

  th, td {
    border: rem-calc(1px) solid $dark-blue;
    color: $dark-blue;
  }

  a { color: $dark-blue; }

  tr:nth-child(even) {
    background-color: lighten($light-blue, 5%);
  }
  tr:nth-child(odd) {
    background-color: white;
  }  
}
```
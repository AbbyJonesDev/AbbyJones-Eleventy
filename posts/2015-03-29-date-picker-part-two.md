---
title:  "Date Picker Part Two"
date:   2015-03-29
summary: "Upon further examination, my wonderful date picker solution didn't work out quite as expected. It seemed to work fine in some cases, but other times the record would fail to save. This only happened in browsers that used the jQuery UI Date Picker. (Things worked fine on Chrome, which has a native date picker...)"
tags: 
  - JavaScript
  - Rails
---
Upon further examination, my wonderful <a href="{{ '/posts/2015-02-25-cross-browser-date-picker' | url }}">date picker solution</a> didn't work out quite as expected. It seemed to work fine in some cases, but other times the record would fail to save. This only happened in browsers that used the jQuery UI Date Picker. <em>(Things worked fine on Chrome, which has a native date picker.)</em>When I looked more closely at the "successful" cases, I realized that the values for month and day were reversed. For example, if the selected date was March 5th (3/5), the saved date would be May 3rd (5/3).

The problem turned out to be an incompatibility in how Date Picker formatted the date vs. how ActiveRecord expected to receive it. There are several ways to address the issue, but I decided to try the Alternate Field solution from <a href="http://allthingsrails.com/post/18389560407/using-jquery-ui-datepicker-with-rails" rel="nofollow">All Things Rails</a>. In this approach, a hidden field is added to the form and populated with an ActiveRecord-friendly value using Date Picker's <a href="http://api.jqueryui.com/datepicker/#option-altFormat" rel="nofollow">altFormat option</a>.

This works for creating new records but introduces hiccups when trying to edit an existing record. The value coming back from the database has to be formatted into the human-friendly version again for the visible field. Otherwise, the user sees a confusing version of the date, and - much worse - the record fails to save because the altFormat option still kicks in and reformats the value when the record is saved, now turning it into an invalid date.

Getting things to work with the jQuery UI Date Picker wasn't too bad after I understood the problem and implemented the solution from All Things Rails. Unfortunately, these changes broke the site when I ran it on Chrome with its native date picker.

I really wanted to use the native date picker when available, and I spent a lot of time trying to make it work both ways. The resulting code was just buggy and hacky and not worthwhile. I know the majority of my users will be on browsers that need the jQuery Date Picker anyway, and using it across all browsers will provide a consistent user interface with styling that's more consistent with the rest of the site. (The native date picker can't be styled, but jQuery's can.)

I changed my date fields to text fields, added ids, and modified my JavaScript to target these elements across all browsers instead of just browsers that don't support date fields. (Browsers that don't support date fields change them to text fields.)

Looking at the final code, I can't believe how many hours it took me to get down to these few lines.

``` ruby
# Form
<div class="medium-6 columns">
  <%= f.label :expires_on %>
  <%= f.text_field :expires_on, :placeholder => "mm/dd/yyyy", id: "visible-date-field",
           :value => @announcement.try(:expires_on).try(:strftime,'%m-%d-%y') 
  %>
  <%= f.hidden_field :expires_on, id: "hidden-date-field" %>
</div>
```

``` js
// JavaScript
var dateInput = $('#visible-date-field');
dateInput.datepicker({
  dateFormat: 'mm-dd-yy',    // Shown in view
  altFormat: "yy-mm-d",        // Sent to database
  altField: "#hidden-date-field",
});
```
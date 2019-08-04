---
title:  "Rails Hosting"
date:   2015-09-06
summary: "I've been hunting for the perfect Rails host for sites that I've built for two friends. One owns a small business, and the other needed a personal website for his music.  Cost is a big factor, but speed, reliability and security are important, too.  I've researched several options - Heroku, WebFaction, Digital Ocean, and OpenShift.  Each has different pros and cons, but after trying all of them, I think Heroku is still the best solution for smaller businesses and individuals..."
tags: 
  - Rails
  - Hosting
---
I've been hunting for the perfect Rails host for sites that I've built for two friends.  One owns a small business, and the other needed a personal website for his music.  Cost is a big factor, but speed, reliability and security are important, too.  I've researched several options - <a href="#Heroku-info">Heroku</a>,  <a href="#WebFaction-info">WebFaction</a>, <a href="#DigitalOcean-info">Digital Ocean</a>, and <a href="#OpenShift-info">OpenShift</a>.  Each has different pros and cons, but after trying all of them, I think Heroku is still the best solution for smaller businesses and individuals.

<section id="Heroku-info">
  <h2> <a href="https://www.heroku.com/">Heroku</a> </h2>
  <p>
    Heroku is the go-to choice for beginning Rails developers, and for good reason.  After some initial setup, all it takes to deploy or update an app is a simple Git push.  It's almost like Heroku was built with the same philosophy as Ruby - to make developers happy.  There's even a free tier with no limit to how many apps you can deploy.  This is beautiful for staging sites.  Until a recent pricing change, the free tier was even sufficient for small production sites.
  </p>
  <p>
    Heroku is a PAAS, or Platform as a Service.  They handle system details and security so developers can focus on building applications and getting them out the door. Application logs are accessible through the command line, which helps with debugging. Add ons like <a href="https://sendgrid.com/">SendGrid</a> (for email) and <a href="http://newrelic.com/">New Relic</a> (for monitoring) are easy to add, and there are different tiers available for them as well.  As an application grows, you can scale it up using sliders on the Heroku dashboard.  (And if traffic drops off, you can scale it back down again.)  It would be nice if the scaling could be done automatically, but the dashboard is easy to use.
    <br>
    <i>Note - sliding to scale is only available on the Professional tiers, not the Free or Hobby tiers.</i>
  </p>
  <p>
    Heroku changed it's pricing over the last few months.  
    <ul>
      <li>
        A free tier is still available, but it must sleep at least 6 hours in a 24-hour period.  No problem on a staging site, but disastrous in production.
      </li>
      <li>
        The "Hobby" level starts at $7/month and has no sleep time.
      </li>
      <li> 
        The "Standard" level - the entry-level professional tier - starts at $25/month.  It probably isn't necessary for our current needs, but it would run a little faster. 
      </li>
    </ul>
    So far so good... But databases aren't included.  And prices here ramp up quickly.
    <ul>
      <li>
        A free hobby database comes with up to 10K rows and has up to 4 hours of downtime/month.
      </li>
      <li>
        A Basic hobby database is $9/month and has up to 10 million rows and 4 hours of downtime/month.
      </li>
      <li>
        The "Standard" database starts at $50/month and has up to 1 hour of downtime per month.  It also comes with more protection, performance analytics, fork/follow capability, and 1-hour rollback.
      </li>
    </ul>
    My biggest concern with the Hobby databases is the potential amount of downtime.  This seemed like a significant problem, and the $50 price jump to the standard database was not an option. This started my intense search for another hosting option.  When I finally did the math, though, I realized the Hobby database still has at least 99.5% uptime.  Not a terrible tradeoff for keeping costs low.
  </p>
</section>
<section id="WebFaction-info">
  <h2><a href="https://www.webfaction.com/">WebFaction</a></h2>
  <p>
    I've had a WebFaction account for several years.  For $9.50/month, I can host as many sites as I want. I have several static sites and a couple of WordPress sites hosted there now, including this site.  The base plan includes 100GB of disk space, 600GB of bandwith per month, and 512MB of RAM.  All of these can be upgraded as needed.  SSH and SFTP access are both available.  You can also set up and manage email accounts from the dashboard.  Server maintenance, monitoring, and security are all handled for you.
  </p>
  <p>
     WebFaction has one-click installers for many popular tools include Rails, WordPress, and Django.  The dashboard allows you to set up domains and applications independently and then attach an application to a domain to create a website.  This is nice for staging, because I can get the application working smoothly on a staging domain and then move it directly to the production domain from the dashboard.  You get a free username.webfactional.com domain, and I create subdomains from this to use for my staging sites.
  </p>
  <p>
    I thought WebFaction would work beautifully for hosting my friends' Rails sites, but it didn't work out that way.  Even with the one-click installer, <a href="https://docs.webfaction.com/software/rails.html">setup and configuration</a> turned out to be a complicated process.  It might go more smoothly for someone with more experience, but I ran into one problem after another.  Over a couple of years, I tried launching several sites through WebFaction, and I never had one go quickly or easily.  When I finally got the last site deployed, it was painfully, painfully slow.  Strange, because my other sites load pretty quickly. 
  </p>
  <p>
    I'll keep WebFaction for static and WordPress sites, but it's not a good fit for Rails.
  </p>
</section>
<section id="DigitalOcean-info">
  <h2><a href="https://www.digitalocean.com/">Digital Ocean</a></h2>
  <p>
    Digital Ocean is used and recommended by Chris Oliver, the creater of <a href="https://gorails.com/about">GoRails</a>, and he put together a nice <a href="https://gorails.com/deploy/ubuntu/14.04">deployment guide</a> for it.  Unlike Heroku, Digital Ocean is an IAAS, or Infrastructure as a Service.  They provide a server running the Linux flavor of your choice and full SSH access.  From there, it's up to you to install and maintain whatever tools and software you need.  The difference in services is reflected in the price.  There's no free tier, but plans start at $5/month for 512MB of memory, 20GB of disk space, and 1TB of bandwith.  The most popular plan is a very affordable $10/month for 1GB of memory, 30GB of disk space, and 2TB of bandwidth.  They use all SSD drives, so apps run nice and fast.
  </p>
  <p>
    I've never set up a server on my own before, so it was a time-consuming process for me.  The GoRails guide helped a lot, but I still had to do some Googling.  Digital Ocean has a lot of good documentation that was helpful.  They do have one-click installers for a number of popular applications, including Rails, but I didn't try this option since I was following the GoRails guide. 
  </p>
  <p>
    I was able to get a site up and running in under a day, but sending emails is an important part of this particular app, and I couldn't get that function working.  I discovered that sendmail isn't magically available; it has to be installed and configured on the server.  I tried using a <a href="https://holarails.wordpress.com/2013/11/17/configure-sendmail-in-ubuntu-12-04-and-make-it-fast/">tutorial</a> I found, but I couldn't get it.  Then I tried sending through SMTP with Gmail instead.  On the first go, I got an email from Gmail saying they had blocked an insecure app from accessing my account.  A <a href="https://stackoverflow.com/questions/30331624/gmail-blocking-rails-app-from-sending-email/30331917#30331917">StackOverflow search</a> provided an easy solution - changing the port from 587 to 465.  I tried again, and the email went through.  <i><b>SO</b> excited</i>.  Except...it only worked once.  After that, the application log said the emails were sent, but they never arrived. <i><b>SO</b> frustrating</i>.
  </p>
  <p>
    While searching the logs to debug the email problem, I discovered attempts to hack the site.  It was running on an IP address with no domain attached, and it had been up for less than a week.  As far as I could tell, Rails blocked the attempts nicely.  Still, it was sobering.  Guess I should have followed the <a href="https://www.digitalocean.com/community/tutorials/additional-recommended-steps-for-new-ubuntu-14-04-servers">instructions</a> to secure my server and set up a firewall right away instead of putting it off...  I also realized that if I deployed my friends' sites here, someone would have to stay on top of keeping the system up to date and secure.  
  </p>
  <p>
    Given time and budget constraints and the need for more server experience than I have, Digital Ocean isn't a good fit for my current projects.  It could be a great option for companies with a little more tech support available, though.
  </p>
</section>
<section id="OpenShift-info">
  <h2><a href="https://www.openshift.com/">OpenShift</a></h2>
  <p>
    OpenShift looked like a great middle ground between Heroku and Digital Ocean.  It's a PAAS, so they take care of the system for you.  They have a command-line client similar to Heroku's and use a Git push for deployment.  They also offer SSH access, which is a nice bonus.  The free tier includes 3 basic "gears," enough to run a small Rails application with a database, and auto-scaling is available.  Small production gears start at about $18/month with 512MB of memory and 1GB of storage, and billing is done based on usage by the hour.
  </p>
  <p>
    I think OpenShift has a lot of potential and might be worth further exploration, but I haven't gotten my application to work on it yet.  In all fairness - fatigue may be playing a role at this point.  The first series of problems I encountered were because I misunderstood how to set up the Git repositories.  (They create a repo for you with their configuration in place.  You're supposed to merge your app repo into theirs, but I did it backwards.)  
  </p>
  <p>
    I started over when I realized this, and things went better the second time.  I was able to debug the issues I ran into, and eventually it appeared that everything was up and running.  When I visited the site, however, it would only show the generic index.html from the public directory.  Trying to visit other pages resulted in errors.  I can ssh in and see that all of my code is in place, and the routes are set correctly, but they aren't being followed.  There's no activity in the log, so it looks like the Rails code is never being touched.
  </p>
  <p>
    This may be (probably) a foolish mistake or oversight on my part, but I can't find a solution in the OpenShift documentation or on StackOverflow.  OpenShift's documentation is extensive and mostly good, but some details are out of date.  StackOverflow is usually a fountain of information, but searching for "openshift, rails" yielded a grand a total of 119 results.  (A search for "heroku, rails" has 9,852.)  
  </p>
  <p>
    I hate admitting defeat with OpenShift, because it's so close to being an excellent option.  But it's time to move on for now.
  </p>
</section>
<section>
  <h2>Summary</h2>
  <p>
    Rails has so many features that help developers build apps quickly.  Moving from development to staging and production can be more complicated.  Two options I didn't try were <a href="http://aws.amazon.com/">Amazon Web Services</a> and <a href="https://www.engineyard.com/">Engine Yard</a>. I've heard good thngs about both, but AWS requires more hands-on server administration like Digital Ocean, and Engine Yard was over budget for these projects.  Of the options I did try, Heroku's ease of use and abundance of community support and documentation made it the best option for our current needs. 
  </p>
</section>
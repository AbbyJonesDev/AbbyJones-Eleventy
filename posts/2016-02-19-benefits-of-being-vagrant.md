---
title:  "Benefits of Being Vagrant"
date:   2016-02-19
summary: "I had used Vagrant a little bit before, and this felt like the perfect opportunity to make it a regular part of my development workflow.  Vagrant is a great tool that works with VirtualBox or VMWare to set up and manage virtual environments. I really like the idea of keeping my machine as clean and light as possible and having each project compartmentalized in its own environment.  It should also help to build apps in a dev environment that closely matches the production environment..."
tags:  
  - Vagrant
  - Virtual Machines
---

I recently got a new computer.  _Yay!_

Then I rediscovered how much work it takes to get a computer set up for dev work.  _Sigh._  

I had used Vagrant a little bit before, and this felt like the perfect opportunity to make it a regular part of my development workflow.  Vagrant is a great tool that works with VirtualBox or VMWare to set up and manage virtual environments. I really like the idea of keeping my machine as clean and light as possible and having each project compartmentalized in its own environment.  It should also help to build apps in a dev environment that closely matches the production environment.

I've used VirtualBox by itself to run virtual Linux machines, and it works pretty well.  For the SAAS class offered by Berkeley on EdX, they provided an Ubuntu box that had everything we needed to create Ruby on Rails apps installed and ready to go.  This was a nice way to help us get started without spending hours on set up, but I found myself desperately missing the smoothness and shortcuts of OSX.  After a few weeks, I bit the bullet and installed everything on my MacBook.

Vagrant works _with_ VirtualBox, but it provides a "headless" virtual environment.  A Vagrantfile defines how the virtual machine will be built.  Running ```vagrant up``` from the command line installs the virtual machine and boots it up.  While it's running, you can use ```vagrant ssh``` to ssh into the box and run whatever commands you want.  

Vagrant automatically shares and syncs whatever files are in the same directory as the Vagrantfile.  This means I can use whatever text editor or program I want on my computer to edit the files.  Port forwarding can also be set up in the Vagrantfile, so I can run the server in the virtual machine and view the website in my browser.

Basicially - I get all the benefits of working on OSX with all of the benefits of using a virtual machine at the same time.  And when I'm finished with a project, I can run ```vagrant destroy``` to wipe out the virtual machine and reclaim all of the memory it was taking up.  (But my code is still saved on my local machine, and backed up in Github, of course.)  

The Vagrantfile can be checked into source control, so no matter how much time passes or what computer I might be using later, I can pick up right where I left off in the same environment.  New people can also get involved in a project with minimal setup.  As long as they have VirtualBox and Vagrant installed on their computer, they can check out the repo, run ```vagrant up```, and jump right in.  

I was pretty sold on the benefits of using Vagrant, but I didn't realize how much time I was about to spend getting a Vagrant box configured for Rails work.  I'll leave that story for another post.  Now that my project is running on Vagrant, it's time to jump back into some coding.
---
layout: post
title:      "My first Ruby on Rails app!"
date:       2018-08-09 03:39:10 +0000
permalink:  my_first_ruby_on_rails_app
---


The objective of this project is to create a Ruby on Rails web application that allows users to view, track and book coworking workspaces at various locations. 

The app provides for an admin functionality that allows a user who is registered as an admin, to be able to perform certan 'admin actions' such as add a new location or workspace to the database. 

The booking functionality is achieved by creating a join table between the user and the workspace, using the has_many through association. The user is able to view a list of available workspaces and book a particular workspace by submitting details such as booking date, booking time and booking duration. 



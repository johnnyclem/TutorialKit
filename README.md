TutorialKit
===========

TutorialKit is a client/server solution which uses unit tests to create checkpoints, milestones and interactive quizzes in your Xcode Tutorial projects.

##How It Works

Subclass TutorialKitTest and write unit tests as you normally would using the XCTest framework

In the AppDelegate of your Tutorial project (the Xcode project your students/readers will download), add two lines to register you'd Tutorial Project's UUID and the web address of your TutorialKit server.

Build and Run your TutorialKit target, this will compile a static library with your tests and the necessary networking code to check-in with your server when a milestone is passed.

The build and run step also creates a ruby file containing the server-side portion of your tests.  

Login to the admin panel of your TutorialKit server and create a new Tutorial.

Paste in the same UUID used in your AppDelegate code, then upload the generated TutorialKitTests.rb file and finally, upload the completed Xcode project folder (compress the entire project folder to .zip first).

When a user downloads the Xcode Tutorial Project, the TutorialKit server will inject a unique ID for that user into the .xcodeproj file, so that milestones and checkpoints are reported with the unique user ID of the student, to your TutorialKit server.

##Getting Started

Clone this repo, and the corresponding server app repo.

Deploy the TutorialKit server app to Heroku, Digital Ocean, or your preferred PaaS/IaaS.

Create your xcode project for your tutorial

create a new target which imports the TutorialKit framework (see the bundled demo app for a good example)

Write your unit tests

Build/Run, then upload your project and ruby file to your TutorialKit server by logging in to https://yourserver.com/admin (default u/p is admin/admin)


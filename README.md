# Generator-Meteor-Dokku
*A opinionated yeoman generator for Meteor with gulp as release system optimized for Dokku.*

## Usage
1. ```npm install -g yo```
2. ```npm install -g generator-meteor-dokku```
3. ```yo meteor-dokku```

## Generated project
The following preconfigured system will be setup.

### Meteor
A standard structured meteor project with iron router and other useful packages.

Version: 1.2.1

#### Dokku Compatability
Meteor contains a folder *.profile.d* which sets the ```METEOR_SETTINGS``` variable when the projected is pushed to Dokku.

It also contains an *.env* file that defines a Heroku/Dokku buildpack for Meteor.

#### Packages
```
# Meteor packages used by this project, one per line.
# Check this file (and the other files in this directory) into your repository.
#
# 'meteor add' and 'meteor remove' will edit this file for you,
# but you can also edit it by hand.

meteor-base             # Packages every Meteor app needs to have
mobile-experience       # Packages for a great mobile UX
mongo                   # The database Meteor supports right now
blaze-html-templates    # Compile .html files into Meteor Blaze views
session                 # Client-side reactive dictionary for your app
jquery                  # Helpful client-side library
tracker                 # Meteor's client-side reactive programming library
random
ejson

check
audit-argument-checks

standard-minifiers      # JS/CSS minifiers run for production mode
es5-shim                # ECMAScript 5 compatibility for older browsers.
ecmascript              # Enable ECMAScript2015+ syntax in app code

# Extra meteor packages
coffeescript
accounts-base
accounts-facebook

# Extra middleware packages
iron:router
aldeed:collection2
reywood:publish-composite
matb33:collection-hooks
okgrow:analytics

# Extra UI packages
semantic:ui-css
iandouglas:accounts-ui-semantic-ui
aldeed:autoform
aldeed:delete-button
fabienb4:autoform-semantic-ui
```

### Gulp
To help with change log generation and releasing a gulp release system is included. It uses *conventional changelog* using angular conventions.

#### What it does
* Set release packages
* Bumps version using SemVer
* Updates changelog
* Commits updated changelog
* Pushes master to origin
* Tags release
* Deploys to Dokku (needs config)

#### Installation
1. ```cd .gulp```
2. ```npm install --save-dev```

#### Usage
To release the master branch use:

1. Do, commit and merge changes to master.
2. ```gulp release --bump [patch|minor|major]```

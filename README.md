# CodeXX

## Getting on the Members list

1. Fork the codexx.github.io repo.
  ![GitHub Fork button](http://i.imgur.com/0K2fyDs.png)
2. Clone the fork into your development environment
3. Copy the developer template _\_template/dev.md_ to _\_devs/YourHandle.md_
4. Replace the placeholder values with your details, see below for details about the file structure.
5. Commit and push your changes to your fork.
6. Submit a pull request to [cavewoman/codexx.github.io](https://github.com/cavewoman/codexx.github.io).

Once you submit your pull request, someone will review it and let you know if there any changes or fixes that need to be made.  If everything looks good then it will be pulled in and you will start showing up as a CodeXX member!

## The member markdown file

The list of member is autogenerated by reading a directory filled with individual markdown files for each dev.  The structure of the files is as follows:

``` md
---
name: <Real Name>
github: <GitHub Username>
gravatar-id: <Gravatar ID>
urls:
    -   name: website
        url: <URL>
    -   name: twitter
        url: <URL>
    -   name: google+
        url: <URL>
layout: default
---
```

Fields that are required are:
* name
* github
* gravatar-id
* layout

### Name

The ```name``` field is for your name as you would like it to appear on the Devs page.

### Github

The ```github``` field is for your GitHub username, this way we can link back to your GitHub profile (you do want people to see how awesome you are after all right? :smile: )

### gravatar-id

The ```gravatar-id``` field contains your gravatar profile ID which is used to fetch your Gravatar ID to display.  [Gravatar](https://en.gravatar.com/) is a free service which allows you to associate a single profile picture with an email address, or multiple addresses if desired,  allowing you to have the same profile picture across multiple sites (GitHub included).  The hash that you use in this field is an unsalted MD5 hash of your email address, don't worry if you don't know you hash that is easy to find.

#### Finding out your Gravatar ID

As said in the previous section your Gravatar ID is the unsalted hash value of your email address.  There are many very easy ways to find out what this is.

##Instructions for Local Development

To replicate our development environment a number of open source tools are required, specifically:

* [Jekyll](http://jekyllrb.com)

##Getting Started

###Install bundler

~~~ sh
$ gem install bundler
~~~

###Have bundler resolve your dependencies

~~~ sh
$ bundle install
~~~

###Run Jekyll Server

~~~ sh
$ jekyll serve
~~~

If that fails you may need to run the Jekyll server with `bundle exec`.

~~~ sh
$ bundle exec jekyll serve
~~~

###Open Browser

Navigate to http://localhost:4000/

##Acquiring an API key for the events page

1. Go to the [Google Developers Console](https://console.developers.google.com).
2. Create a new project.
3. In the sidebar on the left, expand APIs & auth. Next, click APIs. In the list of APIs, make sure the calendar API is turned on.
4. In the sidebar on the left, select Credentials.
5. Click Create new Key and select Browser Key.
6. Enter `*localhost:4000/*` in the *"Accepts Requests From"* text box and click create.
7. Copy the new API key and replace the one located in the [event.js file](assets/js/events.js).
8. It should look something like `gapi.client.setApiKey('YOUR API KEY);`.
9. Wait a few moments, then navigate to [http://localhost:4000/events/](http://localhost:4000/events/) to make sure it worked.

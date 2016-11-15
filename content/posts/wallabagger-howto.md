date: 2016-11-15 08:00:00+00:00
slug: wallabagger-howto
title: Wallabagger howto
tags: wallabagger

# Wallabagger howto

Wallabagger is chrome extension for add pages to wallabag, with ability to:

- save current page
- edit title
- add (with autocomplete!) and remove tags
- set starred and  archived
- delete

## Requirements

- wallabag v2 on server side.
- Chrome-based browser

## Installation

You can install Wallabagger by three ways:

- [From google webstore:](https://chrome.google.com/webstore/detail/wallabagger/gbmgphmejlcoihgedabhgjdkcahacjlj) - open this page with chrome-based browser (tested chrome, yandex browser, vivaldi) and click the "add to chrome" button

  ![webstore](/images/wallabagger/inst-webstore.png)

- Opera and Yandex browsers can install extension from [Opera extension site](https://addons.opera.com/ru/extensions/details/wallabagger/)

- Use unpacked source:
  - Download source from or clone [github repository](https://github.com/rurik19/wallabagger)
  - Go to your chrome-based browser [extension setup page](chrome://extensions)
  - Click "Developer mode" checkbox

  ![Developer mode](/images/wallabagger/inst-developermode.png)

  - Click the "Load unpacked extension" button

  ![extension page](/images/wallabagger/inst-extensionbutton.png)

  - Select wallabagger folder (which consists *manifest.json*)

- Use packed .crx file
  - Download wallabagger.crx from or clone [github repository](https://github.com/rurik19/wallabagger)
  - Go to your chrome-based browser [extension setup page](chrome://extensions)
  - Drag wallabagger.crx to this page


## Options

First of all: you have to create new client on your wallabag installation. How to do that is described in [Documentation](http://doc.wallabag.org/en/master/developer/api.html#creating-a-new-api-client)
What we need from that client is two strings: Client ID and Client secret:

   ![Client](/images/wallabagger/opt-client.png)

### Access options page

After installation of wallabagger extension you can setup it by options page. This page is accessible by

- Right click on extension icon and choose menu "options"

   ![Menu](/images/wallabagger/opt-menu.png)

- Go to your chrome-based browser [extension setup page](chrome://extensions), and click on "options" in wallabagger section

   ![extensions](/images/wallabagger/opt-ext-optlink.png)

### Setup process

- Enter URL of your wallabag installation (without "http://" ), check "https" if you use that, and click "Check URL" button

   ![URL](/images/wallabagger/opt-url.png)

   if URL is valid then in checklist in the bottom of page will be information about that.

   ![checklist](/images/wallabagger/opt-checklist.png)

- If URL was checked and correct api is found, then appears client and user information fields. Fill it and click "Get token" button. In future access token will get authomatically, when it expires.

   ![Client fields](/images/wallabagger/opt-clientfields.png)

    if information is correct in checklist will be information about that.

   ![Token granted](/images/wallabagger/opt-granted.png)

- If you are to have tags consisting space in its, check appropriate options. This change fix symbol in tag input from Space to Enter

   ![Space in tags](/images/wallabagger/opt-spaceintags.png)

### Security warning

In this version of extension your password is stored in browser local storage in plain text and can be retrieved by abuser. Password encryption will be implemented in future versions.


## Usage

### Saving article

After installation and successful setup you can add current opened article to wallabag by clicking on wallabagger extension icon

   ![icon](/images/wallabagger/use-icon.png)

wait a couple of seconds

   ![Saving](/images/wallabagger/use-saving.png)

(There also may be message "Obtaining wallabag api token" if application token is expired (one time in two weeks))
If something goes wrong, an error message appears:

   ![Error](/images/wallabagger/use-error.png)

In that case, check your options.

If there was no errors, main window with saved article appears. Note: if the article from this URL was already saved, that article will appear with its tags, title, and flags (starred, archived).

![Article](/images/wallabagger/use-article.png)

### Article window

The article window consists from:

- the article picture
- the title - clicking by it opens article in wallabag interface

![Title](/images/wallabagger/use-title.png)

- domain name - clicking by it opens source article

![Domain](/images/wallabagger/use-domain.png)

- icons:
  - edit title icon ![Edit icon](images/use-editicon.png) clicking opens edit title dialog

   ![Edit title](/images/wallabagger/use-edittitle.png)

  - set archived and starred flags icons ![Flags icons](/images/Wallabagger/use-flagsicons.png) These icon changes its appearing when flags is set ![Flags is set](/images/wallabagger/use-flagsset.png)
  - delete article icon ![Delete icon](/images/wallabag/use-deleteicon.png) clicking opens delete confirmation dialog

   ![Delete dialog](/images/wallabagger/use-deletedialog.png)

- tags area: article tags with input field for adding new tags

   ![Tags area](/images/wallabagger/use-tagsarea.png)

### Working with tags

Tags, assosiated with the article appears in tags area before input field. You can delete tag from the article by clicking on the cross on the tag.

   ![Article tags](/images/wallabagger/use-articletags.png)

When you type name of new tag in the input field, after three letter, begins searching in existing tags, found tags appears on the bottom of input field. You can add it by clicking on it or by pressing right arrow key.

   ![Found tag](/images/wallabagger/use-foundtag.png)

You can add typed in input field tag by pressing ",", ";", space key (if you not choose option "Use space in tags" in settings) or enter key (if you choose option "Use space in tags" in settings)

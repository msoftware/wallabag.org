date: 2016-11-18 09:30:00+00:00
slug: wallabagger-howto
title: Presentation of our new Chrome addon, by Rurik19
tags: wallabagger

If you want to add articles in your wallabag account, you can use the classc form. You can also install browser extensions.  
Yuriy Evdokimov ([@Rurik19](https://github.com/Rurik19)) developed the new Chrome addon which supports wallabag v2.

Here is the howto for this addon. Thank you Yuriy! 

## Wallabagger howto

Wallabagger is a chrome extension to add pages to wallabag, with the ability to:

- save current page
- edit title
- add (with autocomplete!) and remove tags
- set starred and archived
- delete

### Requirements

- wallabag v2 on server side.
- Chromium-based browser (Chrome, Opera, Yandex, Vivaldi, etc.)

### Installation

You can install Wallabagger from these ways:

- [From google webstore:](https://chrome.google.com/webstore/detail/wallabagger/gbmgphmejlcoihgedabhgjdkcahacjlj). Open this page with Chromium-based browser (tested Chrome, Yandex browser, Vivaldi) and click the "add to chrome" button

  ![webstore](/images/wallabagger/inst-webstore.png)

- Opera and Yandex browsers can install the extension from [Opera extension site](https://addons.opera.com/ru/extensions/details/wallabagger/)

- Use the unpacked source:
  - Download the source from the github repository or clone the repository [github repository](https://github.com/rurik19/wallabagger)
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


### Options

First of all you have to create a new client on your wallabag installation. How to do that is described in [Documentation](http://doc.wallabag.org/en/master/developer/api.html#creating-a-new-api-client)

What we need from that client is two strings: Client ID and Client secret.

   ![Client](/images/wallabagger/opt-client.png)

#### Access options page

After the installation of Wallabagger extension you can setup it by going to the options page. This page is accessible by

- Right click on extension icon and choose menu "options"

   ![Menu](/images/wallabagger/opt-menu.png)

- Go to your Chromium-based browser [extension setup page](chrome://extensions), and click on the "options" link in the Wallabagger section

   ![extensions](/images/wallabagger/opt-ext-optlink.png)

#### Setup process

- Enter the URL of your wallabag installation (without "http://" ), check "https" if you use that, and click "Check URL" button

   ![URL](/images/wallabagger/opt-url.png)

   if the URL is valid then in checklist in the bottom of page will be information about that.

   ![checklist](/images/wallabagger/opt-checklist.png)

- If the URL was checked and a correct api is found, then the client and user credential fields appears. Fill them and click the "Get token" button. From now access token will be fetched authomatically, when it expires.

   ![Client fields](/images/wallabagger/opt-clientfields.png)

    if the credentials are correct you'll see it in the checklist with an information about that.

   ![Token granted](/images/wallabagger/opt-granted.png)

- If you have tags including spaces, check appropriate options. This will toggle the ending tag key from Space to Enter

   ![Space in tags](/images/wallabagger/opt-spaceintags.png)

#### Security warning

In this version of the extension your password is stored in the browser local storage as a plain text and could be retrieved by anyone with access to your computer. The password encryption will be implemented in future versions.


### Usage

#### Saving article

After installation and successful setup you can add articles to wallabag by clicking on the Wallabagger extension icon


   ![icon](/images/wallabagger/use-icon.png)

wait a couple of seconds

   ![Saving](/images/wallabagger/use-saving.png)

(There also may be message "Obtaining wallabag api token" if the application token is expired (once in two weeks))
If something goes wrong, an error message appears:

   ![Error](/images/wallabagger/use-error.png)

In that case, check your options.

If there was no errors, main window with saved article appears. Note: if the article from this URL was already saved, this article will appear with its tags, title, and flags (starred, archived).

![Article](/images/wallabagger/use-article.png)

#### Article window

The article window consists from:

- the article picture
- the title - clicking it opens article in the wallabag interface

![Title](/images/wallabagger/use-title.png)

- domain name - clicking it opens source article

![Domain](/images/wallabagger/use-domain.png)

- icons:
  - edit title icon ![Edit icon](/images/use-editicon.png) clicking it opens dialog to edit the title

   ![Edit title](/images/wallabagger/use-edittitle.png)

  - set archived and starred flags icons ![Flags icons](/images/wallabagger/use-flagsicons.png) These icons change its appeareance when the flags are set ![Flags is set](/images/wallabagger/use-flagsset.png)
  - delete article icon ![Delete icon](/images/wallabagger/use-deleteicon.png) clicking it opens a confirmation dialog  to make sure you want to delete your article

   ![Delete dialog](/images/wallabagger/use-deletedialog.png)

- tags area: article tags with input field for adding new tags

   ![Tags area](/images/wallabagger/use-tagsarea.png)

#### Working with tags

Tags applied to the article appear in the tags area before the input field. You can remove a tag from an article by clicking on the cross symbol next to the tag.

   ![Article tags](/images/wallabagger/use-articletags.png)

When you type the name of a new tag in the input field, after three letters, Wallabagger begins to search in existing tags. Found tags appear on the bottom of the input field. You can add them by clicking on them or by pressing the right arrow key.

   ![Found tag](/images/wallabagger/use-foundtag.png)

You can add typed in input field tag by pressing ",", ";" or the Space key (if you didn't checked the option "Use space in tags" inside the extension settings) or the Enter key (if you checked the option)

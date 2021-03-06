# YouTrack FreshPlug

This application allows you to integrate YouTrack into your Freshdesk helpdesk.

## Prerequisies


* You must have REST enabled on your YouTrack (which is by default)
* Allow CORS from the domain, where you have your helpdesk (e.g.: support.mycompany.com)
* Have a field in YouTrack, numeric or string type, where you store the ticket id of a Freshdesk ticket


## Features

* Display a list of linked issues, their status (resolved or not) and spent time
* Create a new issue in YouTrack, linked with the current open Freshdesk ticket


## How to use

Paste this piece of code as the Freshdesk custom app (FreshPlug)

```html
<div style="margin-top: 10px">
  <div id="youtrack-widget-container" data-yt-url="https://<your youtrack url>/"
    data-fdesk-ticket="{{ ticket.id }}" data-fdesk-field="<name of the field you use in YouTrack">
  </div>
  <script>
    (function() {
      var a = document.createElement("script");
      a.src = "https://cdn.rawgit.com/AwesomeDevelopersUG/freshdesk_youtrack/v1.0/dist/app.js";
      document.getElementsByTagName("head")[0].appendChild(a)
	})()
  </script>
</div>
```

There are three data attributes:

* **data-yt-url**: Url of your issue tracker, e.g. https://issues.company.com/
* **data-fdesk-ticket**: This is the placeholder to be replaced by Freshdesk on ticket edit page
* **data-fdesk-field**: Name of the field in YouTrack that references the freshdesk issue (e.g. Freshdesk).

## Development

If you wish to develop this further, just:

* `git clone`
* `npm install`
* `npm start` (app is now served on port 3000)

To build the updated app: `npm build_production`


## Contributions

Very welcome, this has been put together very quickly, so the code is not especially nice. It works though.


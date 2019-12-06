How to build
=========

To build JavaScript SDK, you can simply run:

    $ npm run build

The build will be in `dist/`. You can serve it by

    $ npm start

Building and running the extension
---------------------

To build the extension, run `npm run extension`. This will copy your `config.yaml` into
a browserified `token.js` file.

Then, to run the extension, load `chrome://extension`, hit "Load unpacked extension..." and
select the `/extension` folder.

Running Selenium
----------------

Selenium needs valid credentials to run, so first you'll want to copy over
the example config file and update it with your credentials:

    $ cp config.example.yaml config.yaml
    $ vim config.yaml

Next, make sure you've built any changes you've made, as selenium uses the dist folder:

    $ npm run build

Then, the suite can be run via the command:

    $ npm run test:selenium

Generating Coverage report
--------------------------

The Coverage report is generated by NYC and Mocha. Follow the instructions:

    $ npm run coverage

The output will be in coverage. Open the index.html file in browser.

Contributing
------------

Long story short: use spaces to indent, indent with 2 spaces.

1. Use this modeline in vim: et ts=2 sw=2 sta.
1. JavaScript indenting in vim is pretty bad, but there is a vim script that helps:
   http://www.vim.org/scripts/script.php?script_id=3081.

Deployment
---

Make sure to increase patch version number in `package.json`.

Twilio client is hosted on CDN.  Please check out [https://code.hq.twilio.com/client/sdk-release-tool](https://code.hq.twilio.com/client/sdk-release-tool). To upload to CDN:

    ./upload twilio-client-js.json 1.4.{patch} ../twiliojs

To pin it, please use:

    ./pin twilio-client-js.json 1.4.{patch}

Verify by using:

    ./list twilio-client-js.json

More Information
---

Please see [https://code.hq.twilio.com/client/twiliojs/wiki](https://code.hq.twilio.com/client/twiliojs/wiki).
# Localfile system links WebExtension (first test project)

Todos:

- [ ] add test folder + webserver for test cases (later, for now I'm starting the test server in a separate working copy)
- [ ] Icon adding not working properly
- [ ] Native message installer required (later, batch file for development OK)
- [ ] Check why native messaging is not working at the moment
- [ ] Create Extension settings page - options.html (uses Vue for view handling)
- [ ] Add "addon bar" icon to display activity of Extension on current tab
- [ ] Implement localization

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```

For detailed explanation on how things work, consult the [docs for vue-loader](http://vuejs.github.io/vue-loader).

## Extension testing in browser

### Install native app
Go to `src\host\` and run `install_host`. This will register the native app in your system-

### Manually starting
Run `npm run dev`, open Firefox and enter about:debugging in url bar and load `dist\manifest.json` Extension.

### With Web-ext CLI
Install [web-ext](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/Getting_started_with_web-ext) with `npm install --global web-ext`.

And run `web-ext run` in `dist` folder to start FF nightly with the Extension temporarily enabled.

$ npm install web-ext
$ cd src
See Tools > Manage API Keys (https://addons.mozilla.org/en-US/developers/addon/api/key/)
$ ../node_modules/web-ext/bin/web-ext sign --api-key ... --api-secret ...

    Building web extension from /home/gregor/dev/src-view/webextension-local-filelinks-prototype/src
    No extension ID specified (it will be auto-generated)
    Validating add-on [........................................................................................................................................................................................................................]
    Validation results: https://addons.mozilla.org/en-US/developers/upload/27ff39acca0a46dcac0c97e85a550421
    Your add-on failed validation and could not be signed
    FAIL

    WebExtError: The WebExtension could not be signed
        at _callee$ (/home/gregor/dev/src-view/webextension-local-filelinks-prototype/node_modules/web-ext/dist/webpack:/src/cmd/sign.js:136:15)
        at tryCatch (/home/gregor/dev/src-view/webextension-local-filelinks-prototype/node_modules/regenerator-runtime/runtime.js:65:40)
        at Generator.invoke [as _invoke] (/home/gregor/dev/src-view/webextension-local-filelinks-prototype/node_modules/regenerator-runtime/runtime.js:303:22)
        at Generator.prototype.(anonymous function) [as next] (/home/gregor/dev/src-view/webextension-local-filelinks-prototype/node_modules/regenerator-runtime/runtime.js:117:21)
        at step (/home/gregor/dev/src-view/webextension-local-filelinks-prototype/node_modules/web-ext/dist/webpack:/node_modules/babel-runtime/helpers/asyncToGenerator.js:17:1)
        at /home/gregor/dev/src-view/webextension-local-filelinks-prototype/node_modules/web-ext/dist/webpack:/node_modules/babel-runtime/helpers/asyncToGenerator.js:28:1
        at <anonymous>
        at process._tickCallback (internal/process/next_tick.js:188:7)

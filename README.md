# @hrax/now-globals

> Manually maintained global variables for different Service Now script scopes

Inspired by [globals](https://www.npmjs.com/package/globals), this is just a [JSON file](now-globals.json) that can be used in any environment.

Package is meant to add most common used Service Now globals to [ESLint configuration](https://eslint.org/docs/latest/use/configure/language-options#predefined-global-variables) for Service Now scripts.

## Install

```sh
npm i @hrax/now-globals
```

## Usage

```js
const nowGlobals = require("@hrax/now-globals");

// Print global variables accessible in Service Now client scripts
console.log(nowGlobals.client);
```

## Usage with ESLint

```js
// eslint.config.js
const nowGlobals = require("@hrax/now-globals");

module.exports = [
  {
    languageOptions: {
      globals: {
        ...nowGlobals.scopes,
        ...nowGlobals.server
      }
    }
  }
];
```

## Globals Sets

### nowGlobals.scopes

Set of global variable scopes in out-of-box Service Now instances or out-of-box activated Service Now plugins.

### nowGlobals.server

Service Now server globals used in Global or Scoped scripts.

### nowGlobals.client

Most common used Service Now client globals used in client scripts.
Should be used for scripts in, for example:
 - sys_script_client.script
 - sys_ui_action.client_script_v2
 - sys_ui_page.client_script
 - sys_ui_policy.script_false
 - sys_ui_policy.script_true

### nowGlobals.widget
Global variables accessible in Service Now Widget server scripts.

### nowGlobals.ng
Global variables used in Service Now Angular scripts.
Should be used for scripts in, for example:
 - sp_angular_provider.script
 - sp_widget.client_script
 - sp_widget.link

### nowGlobals.atf
Globals used in Service Now Test Step Configurations or Test Server Side Script step tests.
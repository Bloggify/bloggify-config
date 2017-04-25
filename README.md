
# bloggify-config

 [![Version](https://img.shields.io/npm/v/bloggify-config.svg)](https://www.npmjs.com/package/bloggify-config) [![Downloads](https://img.shields.io/npm/dt/bloggify-config.svg)](https://www.npmjs.com/package/bloggify-config)

> Helper module to create Bloggify configuration.

## :cloud: Installation

```sh
$ npm i --save bloggify-config
```


## :clipboard: Example



```js
const bloggifyConfig = require("bloggify-config");

console.log(bloggifyConfig.isProduction);
// => false

console.log(bloggifyConfig({
    title: "Bloggify"
  , prodPlugins: [
      "bloggify-analytics"
    ]
  , devPlugins: [
      "debug"
    ]
  , plugins: [
      "github-login"
    ]
  , description: "We make publishing easy."
  , domain: "https://example.com"
  , theme: "bloggify-theme-light"
  , devConfig: {
        ajsRenderer: {
            cache: false
        }
      , githubLogin: {
            secret: "foo"
          , clientId: "bar"
        }
    }
  , config: {
        githubLogin: {
            secret: "real foo"
          , clientId: "real bar"
        }
    }
}, {
    metadata: {
        twitter: "Bloggify"
    }
}));
// { metadata:
//    { twitter: 'Bloggify',
//      siteTitle: 'Bloggify',
//      description: 'We make publishing easy.',
//      domain: 'http://localhost:8080' },
//   corePlugins:
//    [ 'bloggify-plugin-manager',
//      'bloggify-router',
//      'bloggify-ajs-renderer',
//      'bloggify-viewer' ],
//   server: { port: 8080 },
//   theme: { path: 'node_modules/bloggify-theme-light' },
//   pluginConfigs:
//    { 'bloggify-plugin-manager': [ 'debug', 'github-login' ],
//      'github-login': { secret: 'foo', clientId: 'bar' },
//      'ajs-renderer': { cache: false } } }
```

## :question: Get Help

There are few ways to get help:

 1. Please [post questions on Stack Overflow](https://stackoverflow.com/questions/ask). You can open issues with questions, as long you add a link to your Stack Overflow question.
 2. For bug reports and feature requests, open issues. :bug:
 3. For direct and quick help from me, you can [use Codementor](https://www.codementor.io/johnnyb). :rocket:


## :memo: Documentation


### `bloggifyConfig(conf, additional)`
Create Bloggify configuration.

#### Params
- **Object** `conf`: An object containing the following fields:
 - `title` (String): The site title.
 - `description` (String): The site description.
 - `port` (Number): The server port (default: `8080`). You can set this using the `PORT` environment variable.
 - `devDomain` (String): The dev domain (default: `http://localhost:${PORT}`).
 - `theme` (String): The theme name (if it's a npm package) or the path to the theme directory (it should start with `/`).
 - `router` (String): The router plugin name (default: `"bloggify-router"`).
 - `pluginManager` (String): The plugin manager name (default: "bloggify-plugin-manager")
 - `renderer` (String): The renderer name (default: `"bloggify-ajs-renderer"`).
 - `viewer` (String): The viwer name (default: `"bloggify-viewer"`).
 - `devConfig` (Object): An object containing the development-specific plugin configs (default: {}).
 - `config` (Object): An object containing the plugin configs (default: {}).
 - `plugins` (Array): The plugins to be loaded (default: []).
 - `corePlugins` (Array): The plugins to be loaded before loading the router and the renderer.
 - `devPlugins` (Array): The plugins to be loaded in the development mode (default: []).
 - `prodPlugins` (Array): The plugins to be loaded in the production mode (default: []).
- **Object** `additional`: Additional fields to merge in the object.

#### Return
- **Object** The Bloggify config.



## :yum: How to contribute
Have an idea? Found a bug? See [how to contribute][contributing].


## :dizzy: Where is this library used?
If you are using this library in one of your projects, add it in this list. :sparkles:


 - [`bloggify-bloggify-quick-start`](https://github.com/Bloggify/bloggify-quick-start#readme)—A simple example of a Bloggify app.
 - [`bloggify-custom-app-template`](https://github.com/BloggifyTutorials/custom-app#readme)—A custom application built with @Bloggify.

## :scroll: License

[MIT][license] © [Bloggify][website]

[license]: http://showalicense.com/?fullname=Bloggify%20%3Csupport%40bloggify.org%3E%20(https%3A%2F%2Fbloggify.org)&year=2016#license-mit
[website]: https://bloggify.org
[contributing]: /CONTRIBUTING.md
[docs]: /DOCUMENTATION.md

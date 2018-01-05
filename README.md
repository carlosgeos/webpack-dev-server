<div align="center">
  <a href="https://github.com/webpack/webpack">
    <img width="200" height="200" src="https://webpack.js.org/assets/icon-square-big.svg">
  </a>
</div>

[![npm][npm]][npm-url]
[![node][node]][node-url]
[![deps][deps]][deps-url]
[![tests][tests]][tests-url]
[![coverage][cover]][cover-url]
[![chat][chat]][chat-url]

# webpack-dev-server

Use [webpack](https://webpack.js.org) with a development server that provides
live reloading. This should be used for **development only**.

It uses [webpack-dev-middleware][middleware-url] under the hood, which provides
fast in-memory access to the webpack assets.

## Project in Maintenance

**Please note that `webpack-dev-server` is presently in a maintenance-only mode**
and will not be accepting any additional features in the near term. Most new feature
requests can be accomplished with Express middleware; please look into using
the [`before`](https://webpack.js.org/configuration/dev-server/#devserver-before)
and [`after`](https://webpack.js.org/configuration/dev-server/#devserver-after)
hooks in the documentation.

## Getting Started

First thing's first, install the module:

```console
npm install webpack-dev-server --save-dev
```

_Note: While you can install and run webpack-dev-server globally, we recommend
installing it locally. webpack-dev-server will always use a local installation
over a global one._

## Usage

There are two main, recommended methods of using the module:

### With the CLI

The easiest way to use it is with the CLI. In the directory where your
`webpack.config.js` is, run:

```console
node_modules/.bin/webpack-dev-server
```

### With NPM Scripts

NPM package.json scripts are a convenient and useful means to run locally installed
binaries without having to be concerned about their full paths. Simply define a
script as such:

```json
"scripts": {
  "start:dev": "webpack-dev-server"
}
```

And run the following in your terminal/console:

```console
npm run start:dev
```

NPM will automagically reference the binary in `node_modules` for you, and
execute the file or command.

### The Result

Either method will start a server instance and begin listening for connections
from `localhost` on port `8080`.

webpack-dev-server is configured by default to support live-reload of files as
you edit your assets while the server is running.

See [**the documentation**][docs-url] for more use cases and options.

## Caveats

Version 2.8.0 introduced a change which included ES6 keywords `const` and `let`
within the scripts being served to the browser. This effects environments which
support _no ES6 whatsoever_, including older versions of UglifyJS and Internet
Explorer. This was not considered a breaking change at the time due to official
support for oldIE ending in 2016, rather this was seen as a maintenance update.
Those wishing to support oldIE should stick with version 2.7.1.

For version 2.8.0+ those using UglifyJS in their webpack configs should use the
beta version of [uglifyjs-webpack-plugin][uglify-url] independently, and _not_
the built-in plugin. This will change once the new version is out of beta.

## Support

We do our best to keep Issues in the repository focused on bugs, features, and
needed modifications to the code for the module. Because of that, we ask users
with general support, "how-to", or "why isn't this working" questions to try one
of the other support channels that are available.

Your first-stop-shop for support for webpack-dev-server should by the excellent
[documentation][docs-url] for the module. If you see an opportunity for improvement
of those docs, please head over to the [webpack.js.org repo][wjo-url] and open a
pull request.

From there, we encourage users to visit the [webpack Gitter chat][chat-url] and
talk to the fine folks there. If your quest for answers comes up dry in chat,
head over to [StackOverflow][stack-url] and do a quick search or open a new
question. Remember; It's always much easier to answer questions that include your
`webpack.config.js` and relevant files!

If you're twitter-savvy you can tweet [#webpack][hash-url] with your question
and someone should be able to reach out and lend a hand.

If you have discovered a :bug:, have a feature suggestion, of would like to see
a modification, please feel free to create an issue on Github. _Note: The issue
template isn't optional, so please be sure not to remove it, and please fill it
out completely._

## Contributing

We welcome your contributions! Please have a read of [CONTRIBUTING.md](CONTRIBUTING.md) for more information on how to get involved.

## Maintainers

<table>
  <tbody>
    <tr>
      <td align="center">
        <img src="https://avatars.githubusercontent.com/SpaceK33z?v=4&s=150">
        <br />
        <a href="https://github.com/SpaceK33z">Kees Kluskens</a>
      </td>
      <td align="center">
        <img src="https://i.imgur.com/4v6pgxh.png">
        <br />
        <a href="https://github.com/shellscape">Andrew Powell</a>
      </td>
    </tr>
  </tbody>
</table>

## Attribution

This project is heavily inspired by [peerigon/nof5](https://github.com/peerigon/nof5).

## License

#### [MIT](./LICENSE)


[npm]: https://img.shields.io/npm/v/webpack-dev-server.svg
[npm-url]: https://npmjs.com/package/webpack-dev-server

[node]: https://img.shields.io/node/v/webpack-dev-server.svg
[node-url]: https://nodejs.org

[deps]: https://david-dm.org/webpack/webpack-dev-server.svg
[deps-url]: https://david-dm.org/webpack/webpack-dev-server

[tests]: http://img.shields.io/travis/webpack/webpack-dev-server.svg
[tests-url]: https://travis-ci.org/webpack/webpack-dev-server

[cover]: https://codecov.io/gh/webpack/webpack-dev-server/branch/master/graph/badge.svg
[cover-url]: https://codecov.io/gh/webpack/webpack-dev-server

[chat]: https://badges.gitter.im/webpack/webpack.svg
[chat-url]: https://gitter.im/webpack/webpack

[docs-url]: https://webpack.js.org/configuration/dev-server/#devserver
[hash-url]: https://twitter.com/search?q=webpack
[middleware-url]: https://github.com/webpack/webpack-dev-middleware
[stack-url]: https://stackoverflow.com/questions/tagged/webpack-dev-server
[uglify-url]: https://github.com/webpack-contrib/uglifyjs-webpack-plugin
[wjo-url]: https://github.com/webpack/webpack.js.org

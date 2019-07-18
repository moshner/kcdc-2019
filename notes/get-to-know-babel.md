# Get to Know Babel

* Jonathan Kamp
* 7/18/2019 1:15pm
* [Slides](https://speakerdeck.com/jonkemp)

<!-- Summary: -->
Jonathan Kemp gave a high level overview of Babel. He started with the overall structure, moved to configuring, and getting started. There are a few good resources linked below that provide some places to go to get started. 

## Notes
[Babel Roadmap](https://babeljs.io/docs/en/roadmap)

Babel doesn't do anything out of the box, you must use plugins.

## Official Babel Presets
* @bable/preset-env <-- most important
* @babel/preset-flow
* @babel/preset-react
* @babel/preset-typescript

## @babel/polyfill
Polyfills transpile features for you.

Gives full 2015+ support

## Configuring Babel
```  // code block
export default () => ({
    presets: [
        [
            "@bable/preset-env",
            {
                "targets": "> 0.25%, not dead",
                "useBuiltIns": "usage"
            }
        ]
    ]
})
``` 

"usage" only compiles the things that you are acutally using.

"targets" any browser that is used by over 25% of people and has had an update in the last two years (not dead)

### Browserslist
open source project to share one config between autoprefixer, stylelint and bable-preset-env. 

```
package.json

"browerslist": [
    "last 1 version"...
]
```

accepts/supports:
* natural language "last 2 verions"
* global usage "> 5%"
* dead / not-dead
* defaults query
* default is: "> .5%, last 2 version, Firefox ESR, not dead"
* Can do different browsers list for each environment

browserl.ist - a page to display compatable browsers based on your browserlist string

## Getting Started
[Babel Setup](https://babeljs.io/setup)

* comes with CLI out of the box
* put is direclty into your npm scrips, allows `npm run build`

## Setting up with Webpack
This is helpful when you need additional transformations. 

Again webpack doesn't transpile code, you need plugins here too.

The babel setup page as a webpack filter you can sue for help.

## Lebab
Turn your ES5 code into readable ES6 (sugar-syntax). - Does the opposite of what Babel does.

This could be useful for legacy code.

Run old code through Lebab when you run across it

```
npm install -g lebab

lebab es5.js -o es6.js --transform let
```

### Lebab Editor Plugins
VSCode has plugin you can use directly. So do some others, look around.

## JSX
Babel uses JSX and JSX requires Babel to compile down to JS

## Insights

Babel supports node, not just browsers

Babel helps you learn the ES6 syntax and see what is happening behind the scenes with the repl tool[^1]

[ ] Can we use Lebab to help upgrade the legacy code in the upcoming redesign?

## Actions
[ ] Create summary

[ ] Migrate notes to Evernote

## Resources
* [Babel Docs](https://babeljs.io/docs/en)
* [Awesome Babel](https://github.com/babel/awesome-babel)
* [ES6 Compatibility Table](https://kangax.github.io/compat-table/es6)

<!-- Footnotes -->
[^1]: Babel Repl: https://babeljs.io/en/repl
# Get to Know Babel

* Jonathan Kamp
* 7/18/2019 1:15pm

<!-- Summary: -->

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


## Insights

Babel supports node, not just browsers

## Actions
[ ] Create summary

[ ] Migrate notes to Evernote

## Resources

<!-- Footnotes -->
[^1]: Example footnote

<!-- Markdown Cheatsheet https://www.markdownguide.org/cheat-sheet/ -->
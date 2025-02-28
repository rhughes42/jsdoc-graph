# Graph Technologies JSDoc Templates

Based on Minami, a clean, responsive documentation template theme for JSDoc 3 - this template is further configured for Graph Technologies usage.

![Minami Screenshot](http://i.imgur.com/rPCIFqT.png)


## Uses

- [the Taffy Database library](http://taffydb.com/)
- [Underscore Template library](http://underscorejs.org/#template)
- [Montserrat](https://fonts.google.com/specimen/Montserrat) & Helvetica Neue


## Install

```bash
$ npm install --save-dev minami
```


## Usage

Clone repository to your designated `jsdoc` template directory, then:

```bash
$ jsdoc entry-file.js -t path/to/jsdoc
```


### Node.js Dependency

In your projects `package.json` file add a generate script:

```json
"scripts": {
  "generate-docs": "jsdoc --configure ./docs-template/.jsdoc.conf.json --verbose"
}
```

In your `.jsdoc.json` file, add a template option.

```json
"opts": {
  "template": "node_modules/jsdoc-graph"
}
```


### Example JSDoc Config

```json
{
    "tags": {
        "allowUnknownTags": true,
        "dictionaries": ["jsdoc"]
    },
    "source": {
        "include": [
      			"./src",
      			"package.json",
      			"README.md"
    		],
    		"exclude": [
    			  "node_modules"
    		],
    		"includePattern": ".+\\.js(doc|x)?$",
    		"excludePattern": "(node_modules/|docs)"
    },
    "plugins": [
        "plugins/markdown"
    ],
    "templates": {
        "cleverLinks": false,
        "monospaceLinks": true,
        "useLongnameInNav": false,
        "showInheritedInNav": true
    },
    "opts": {
        "destination": "./docs/",
        "encoding": "utf8",
        "private": true,
        "recurse": true,
        "template": "./docs-template/jsdoc-graph"
    }
}
```

Specifying a number for useLongnameInNav it will be the max number of path elements to show in nav (starting from Class).

# Edrys Editor Module

This fork of [Edrys Module-Code](https://github.com/edrys-org/module-code) provides a simplified version, a general editor module that can be connected via the Edrys promiscuous pub-sub feature to different external modules and thus be used for different purposes.

## Usage

Use this URL to add the module to your class:

```
https://edrys-labs.github.io/module-editor/index.html
```

You may optionally specify any of the following module config, the `runCommand` is the only setting that is required:

```js
{
    "editorText": "Starting text in editor...",
    "runCommand": "execute", 
    "language": "cpp",
    "theme": "light",
    "synchronize": false
}
```

`runCommand` defines the subject under which the current editor-input will be published.
Other modules such as the [edrys_module-pyxtermjs](https://github.com/Cross-Lab-Project/edrys_module-pyxtermjs) can be configured to listen to this specific subject and execute some action when they receive this event.

By default the editor will be synchronized across all instances of the editor module. If you want to disable this feature, set `synchronize` to `false`.

### Multiple files

It is also possible to define multiple files like this.

```js
{
    "file": {
        "main.cpp": "Hello world...",
        "main.h": "another file another day"
    },
    "runCommand": "execute", 
    "language": "cpp",
    "theme": "light",
    "synchronize": true
}
```


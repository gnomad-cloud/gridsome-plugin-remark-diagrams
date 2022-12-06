# Draw diagrams in markdown

Draw diagrams using Markdown and publish with Gridsome. 

## use `mermaid` code blocks in your markdown to generate diagrams:

```
```mermaid
graph LR
  A --> B
  B --> C
```
```

See [mermaid](https://mermaid-js.github.io) for more examples.

## Install

```
bash
npm install gridsome-plugin-remark-mermaid
```

## Usage

Configure `gridsome.config.js` to use the plugin.

```
  transformers: {
    remark: {
      plugins: [
        'gridsome-plugin-remark-mermaid',
        // existing plugins //
      ]
    }
  }
```


## Advanced Styling

The generated SVG is wrapped in `<div class="mermaid"></div>` to help you customize your styles.

When using the `removeStyleTags` attribute, you will need to import your Mermaid themes yourself. You can find an example project [here](https://github.com/Braincoke/starter-gridsome-mermaid).

## Options

| Name            | Default               | Description                                                                                                                                                     |
| --------------- | --------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| language        | "mermaid"             | The code block language triggering a SVG generation. Change it to `"graph"` to create diagrams with ````graph`.                                                 |
| theme           | "default"             | This value can be set to `"dark"`, `"neutral"`, `"forest"` or `"default"`. Try them on the [mermaid editor](https://mermaid-js.github.io/mermaid-live-editor/). |
| viewport.width  | 200                   | The desired viewport width                                                                                                                                      |
| viewport.height | 200                   | The desired viewport height                                                                                                                                     |
| removeStyleTags | false                 | Remove all style tags from the generated SVG. If you use this option you will have to import the mermaid css at some point                                      |
| id              | `mermaid-<currentTime>` | Sets the identifier of the SVG. Defaults to a unique ID based on the time of generation                                                                         |
| mermaidOptions  | {}                    | Pass some custom [mermaid configuration options](https://mermaid-js.github.io/mermaid/#/mermaidAPI?id=configuration) to `mermaid.initialize()`                                                                                    |

The default options are:

```js
{
  language: "mermaid",
  theme: "default",
  viewport: {
    width: 200,
    height: 200
  },
  id: null,
  removeStyleTags: false,
  mermaidOptions: {}
}
```

## Provenance / Credits

This plugin was forked, upgraded and adopted with gratitude to the original authors.

You can find the original versions here: 

- Forked and upgraded from [gridsome-remark-mermaid](https://github.com/Braincoke/gridsome-plugin-remark-mermaid)
- Originally inspired by [gatsby-remark-mermaid](https://github.com/ChappIO/gatsby-remark-mermaid)

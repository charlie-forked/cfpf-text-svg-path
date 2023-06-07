# cfpf-text-svg-path

Convert text to SVG path without native dependence with Cloudflare Pages Functions.

```js
import TextToSVG from "text-svg-path";
const textToSVG = new TextToSVG();

export const onRequestGet = async (context) => {
    await textToSVG.load()

    const attributes = {fill: 'black', stroke: 'black'};
    const options = {x: 0, y: 0, fontSize: 72, anchor: 'top', attributes: attributes};
    
    const svg = textToSVG.getSVG(context.params.number, options);

    return new Response(svg, {
        headers: {
            'Content-Type': 'image/svg+xml',
        },
    });
}

```

## License

MIT

## Credits

- [opentype.js](https://github.com/nodebox/opentype.js)
- [text-to-svg]()

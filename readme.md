# Puppeteer Instaquote

> Instaquote / meme image generator using Puppeteer.

[![NPM](https://img.shields.io/npm/v/puppeteer-instaquote.svg)](https://www.npmjs.com/package/puppeteer-instaquote) [![Build Status](https://travis-ci.com/transitive-bullshit/puppeteer-instaquote.svg?branch=master)](https://travis-ci.com/transitive-bullshit/puppeteer-instaquote) [![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)

## Install

```bash
yarn add puppeteer-instaquote
```

## Usage

The first input is an excel spreadsheet containing two columns, one for **Author** and one for **Quote**.

The second input is a list of background images with some optional styles specific to each background image. So for a given background image, you could specify that you want to use a specific font, text color, padding (to identify the space within the output image that you want the text to fit within). It supports any CSS styles and any font from [Google Fonts](https://fonts.google.com/).

It performs **auto-sizing of the text** within the background image's specified padding area, so short quotes will use larger font sizes and longer quotes will automatically use smaller font sizes to ensure that no matter what input you give, the output text will always "fit" within the desired bounds.

## Examples

This repo comes with a demo containing 10 quotes rendered for each of the 9 example background images (so 90 images in total for this demo). This examples use the following Google Fonts: Caveat, Sacramento, Dancing Script, Great Vibes, Rochester, and Calligraffitti.

See [media/output](./media/output) for the full list of example output images.

![](https://raw.githubusercontent.com/transitive-bullshit/puppeteer-instaquote/master/media/output/quote-1-bg-1.png)
![](https://raw.githubusercontent.com/transitive-bullshit/puppeteer-instaquote/master/media/output/quote-4-bg-6.png)
![](https://raw.githubusercontent.com/transitive-bullshit/puppeteer-instaquote/master/media/output/quote-2-bg-3.png)
![](https://raw.githubusercontent.com/transitive-bullshit/puppeteer-instaquote/master/media/output/quote-3-bg-8.png)
![](https://raw.githubusercontent.com/transitive-bullshit/puppeteer-instaquote/master/media/output/quote-8-bg-10.png)

## Running the demo

Clone locally, then run `yarn` to install dependencies, then `node demo.js` to generate the output images.

## API

<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

### [renderInstaquote](https://git@github.com/:transitive-bullshit/puppeteer-instaquote/blob/49c8c98b390895dc18c4ac5a1e01e3c26d69f12d/index.js#L33-L209)

Renders the given meme via puppeteer to an `output` file.

If you want to load multiple google fonts, juse specify their font-families in `opts.style.fontFamily`
separated by commas as you normally would for CSS fonts.

The generated html page is returned as a string for debugging and batch rendering purposes.

Type: `function (opts): Promise`

-   `opts` **[object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** Configuration options
    -   `opts.output` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Path of image file to store result
    -   `opts.quote` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Main text (or html) of the content to render.
    -   `opts.author` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Main text (or html) of the sub-header (content author).
    -   `opts.background` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)?** Background image either as a local file path or as a URL (defaults to a transparent background).
    -   `opts.width` **[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)** Optional width of output image (optional, default `1080`)
    -   `opts.height` **[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)** Optional height of output image (optional, default `1080`)
    -   `opts.style` **[object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** Top-level [CSS styles](https://www.w3schools.com/jsref/dom_obj_style.asp) to apply to the top-level container div. (optional, default `{}`)
    -   `opts.quoteStyle` **[object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** Quote / main content [CSS styles](https://www.w3schools.com/jsref/dom_obj_style.asp) to apply to the main content div. (optional, default `{}`)
    -   `opts.authorStyle` **[object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** Author [CSS styles](https://www.w3schools.com/jsref/dom_obj_style.asp) to apply to the author's div. (optional, default `{}`)

## License

MIT © [Travis Fischer](https://saasify.sh)

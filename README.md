# Compliments Button

This is a template to create a “compliments button”,
a website with a button to give the recipient a compliment.
The original version only contains example compliments and should be customized.

## Customization

To customize the compliments button for a certain recipient,
create a copy of this repository and make at least the following changes to `index.html`:

- replace the <var>NAME</var> in the `<h1>` element
- optionally, replace the content of the `<p>` element immediately following the `<p>` element
- optionally, replace the text of the `<title>` element

Then, you need to add the actual compliments.
They are stored in a `compliments` JavaScript array inside `index.html`,
and can include text, an image, an audio file, and/or a video, as well as an author.
These elements can be freely combined (for instance, an image compliment can be accompanied by some text).

The example compliments (which you should remove once you’re done adding your own compliments)
are intended to demonstrate the different compliment options,
but the following sections also document the possible compliment options in more detail.

### Text compliments

The `text` option adds a piece of plain text to the compliment.
(No kind of markup is supported.)
Optionally, the `textLang` and `textDir` options can be used to set different [`lang=`][lang] and [`dir=` attributes][dir] for the element containing the text,
allowing you to include compliments in different languages in the same compliments button.
(The surrounding document is marked as being in English and left-to-right, though you’re free to change that, of course.)

### Image compliments

The `image` option adds an image to the compliment,
and should contain the name of a file that you place next to `index.html`.
It’s highly recommended that you also set the `imageWidth` and `imageHeight` options to the width and height of that image (in pixels),
so that the browser can calculate the right layout for the page before the image has been loaded.
The `imageAlt` option can be used to specify a textual description of the image (“alt text”, [`alt=` attribute][alt]).
The `imageSrcset` option can be used to define a [`srcset=` attribute][srcset] for the image:
the value is an object where the values are alternative file names and the keys are widths of those files in pixels.
This can be used to save bandwidth (by listing downscaled versions if the original file is very large).

### Audio compliments

The `audio` option adds an audio file to the compliment.
The value is either the name of a file that you place next to `index.html`,
or an object listing multiple files,
where each value is the name of a file and the key is the MIME media type of that file.
(Strictly speaking, the key will become the [`type=` attribute][type],
which can also include a `codecs` parameter.)
Support of audio formats varies across browsers and systems,
so it’s a good idea to list several formats here and let the browser pick one.

### Video compliments

The `video` option adds a video file to the compliment.
As with `audio`, the value is either the name of a file that you place next to `index.html`,
or a mapping from MIME type to file name;
as with `image`, you can use the `videoWidth` and `videoHeight` options to inform the browser of the width and height of the video in pixels.

### Compliment authors

The `author` option adds an author to whom the compliment is credited.
As with `text`, the value is plain text (not markup),
and you can use the `authorLang` and `authorDir` options to set different [`lang=`][lang] and [`dir=` attributes][dir] for the element containing the author.

[lang]: https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/lang
[dir]: https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir
[alt]: https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-alt
[srcset]: https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-srcset
[type]: https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source#attr-type

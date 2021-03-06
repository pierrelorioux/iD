# Contributing to iD

Thinking of contributing to iD? High five! Here are some basics for our habits
so that you can write code that fits in perfectly.

## Reporting Issues

We'd love to hear what you think about iD, about any specific problems or
concerns you have. Here's a quick list of things to consider:

Please [search for your issue before filing it: many bugs and improvements have already been reported](https://github.com/systemed/iD/issues/search?q=)

To report a bug:

* Write specifically what browser (type and version, like Firefox 22), OS, and browser extensions you have installed
* Write steps to replicate the error: when did it happen? What did you expect to happen? What happened instead?
* Please keep bug reports professional and straightforward: trust us, we share your dismay at software breaking.
* If you can, [enable web developer extensions](http://macwright.org/enable-web-developer-extensions/) and report the
  Javascript error message.

When in doubt, be over-descriptive of the bug and how you discovered it.

To request a feature:

* If the feature is available in some other software (like Potlatch), link to that software and the implementation.
  We care about prior art.
* Understand that iD is meant to be a simple editor and doesn't aim to be
  as complete or complicated as JOSM or similar.

## Javascript

We use the [Airbnb style for Javascript](https://github.com/airbnb/javascript) with
only one difference:

**4 space soft tabs always for Javascript, not 2.**

No aligned `=`, no aligned arguments, spaces are either indents or the 1
space between expressions. No hard tabs, ever.

Javascript code should pass through [JSHint](http://www.jshint.com/) with no
warnings.

## HTML

There isn't much HTML in iD, but what there is is similar to JS: 4 spaces
always, indented by the level of the tree:

```html
<div>
    <div></div>
</div>
```

## CSS

Just like HTML and Javascript, 4 space soft tabs always.

```css
.radial-menu-tooltip {
    background: rgba(255, 255, 255, 0.8);
}
```

We write vanilla CSS with no preprocessing step. Since iD targets modern browsers,
feel free to use newer features wisely.

## Tests

Test your code and make sure it passes. Our testing harness requires [node.js](http://nodejs.org/)
and a few modules:

1. [Install node.js](http://nodejs.org/) - 'Install' will download a package for your OS
2. Go to the directory where you have checked out `iD`
3. Run `npm install`
4. Run `npm test` to see whether your tests pass or fail.

## Building / Installing

You can build and install a concatenated and minified version of iD with the command `make install`.
Node.js is required for this.

By default iD will be built to the `build` directory, but you can move it elsewhere or specify the
build location with `make install install_root=/path/to/install`.

## Licensing

iD is under the [WTFPL](http://www.wtfpl.net/). Some of the libraries it uses
are under different licenses. If you're contributing to iD, you're contributing
WTFPL code.

## Submitting Changes

Let's say that you've thought of a great improvement to iD - a change that
turns everything red (please do not do this, we like colors other than red).

In your local copy, make a branch for this change:

    git checkout -b make-red

Make your changes to source files. By source files we mean the files in `js/`.
the `iD.js` and `iD.min.js` files in this project are autogenerated - don't edit
them.

So let's say you've changed `js/ui/confirm.js`.

1. Run `jshint js/id` to make sure your code is clean
2. Run tests with `npm test`
3. Commit your changes with an informative commit message
4. [Submit a pull request](https://help.github.com/articles/using-pull-requests) to the `systemed/iD` project.

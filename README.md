# @nib-styles/sass-grid

A responsive grid built on flexbox.

Uses `flexbox` in newer browsers and gracefully degrades in older browsers (<=IE9), supporting *most* of the same functionality using an `inline-block` grid.

## Installation

NPM:

    npm install --save @nib-styles/sass-grid

Component:

    component install nib-styles/sass-grid


## Usage

### Using the compiled classes

SCSS:

    @import "@nib-styles/sass-grid/compiled"

HTML:

    <html class="flexbox"><!-- You'll probably use Modernizr and won't need to manually put this class here --!>
    ...
      <div class="content">

        <div class="grid" g-xs="halign:justify-center">
            <div class="grid__unit" g-md="cols:3">Does stuff</div>
            <div class="grid__unit" g-md="cols:3">Does more stuff</div>
            <div class="grid__unit" g-md="cols:3">Does even more stuff</div>
            <div class="grid__unit" g-md="cols:3">It just does all the stuff!</div>
        </div>

      </div>

    ...
    </html>

See [sass-grid](https://www.npmjs.com/package/sass-grid) for a full list of the available classes.

### Using the mixins

SCSS:

    @import "@nib-styles/sass-grid"
    @import "@nib-styles/sass-breakpoints";

    .feature-panel-wrapper {
      @include content();
    }

    .feature-panel {
      @include grid();
      @include grid--halign-justify-center()
    }

    .feature-panel__feature {
      @include grid__unit();
      @include breakpoint('md') {
        @include grid__unit--cols(3);
      }
    }

HTML:

    <html class="flexbox"><!-- You'll probably use Modernizr and won't need to manually put this class here --!>
    ...

      <div class="feature-panel-wrapper">

        <div class="feature-panel">
            <div class="feature-panel__feature">Does stuff</div>
            <div class="feature-panel__feature">Does more stuff</div>
            <div class="feature-panel__feature">Does even more stuff</div>
            <div class="feature-panel__feature">It just does all the stuff!</div>
        </div>

      </div>

    ...
    </html>

See [sass-grid](https://www.npmjs.com/package/sass-grid) for a full list of the available mixins.

### .content

The `content` class is the default nib content container. It has a max width of 60rem/960px (*we are looking to increase this to ~1200px for future projects*). It is available as a class and a mixin. See previous two code sections for examples of usage.

**Note:** needs to be a child of `.sticky__content`, not on the same element

## Breakpoints

See [@nib-styles/sass-breakpoints](https://github.com/nib-styles/sass-breakpoints).

## Changelog

### 1.0.1

- fix: enforce container width to be 100% so `.content` works within a `flexbox` parent

### 1.0.0

- Bump to major version to avoid npm < 1.0.0 version weirdness

### 0.4.0

- Bump version of `sass-grid` to add wrapping utilities.

[](https://github.com/squidfunk/mkdocs-material/edit/master/docs/reference/admonitions.md "Edit this page")[](https://raw.githubusercontent.com/squidfunk/mkdocs-material/master/docs/reference/admonitions.md "View source of this page")

Admonitions, also known as _call-outs_, are an excellent choice for including side content without significantly interrupting the document flow. Material for MkDocs provides several different types of admonitions and allows for the inclusion and nesting of arbitrary content.

## Configuration[¶](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#configuration "Permanent link")

This configuration enables admonitions, allows to make them collapsible and to nest arbitrary content inside admonitions. Add the following lines to `mkdocs.yml`:

```
markdown_extensions:
  - admonition
  - pymdownx.details
  - pymdownx.superfences

```

See additional configuration options:

-   [Admonition](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown/#admonition)
-   [Details](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown-extensions/#details)
-   [SuperFences](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown-extensions/#superfences)

### Admonition icons[¶](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#admonition-icons "Permanent link")

[8.3.0](https://github.com/squidfunk/mkdocs-material/releases/tag/8.3.0) · Experimental

Each of the supported admonition types has a distinct icon, which can be changed to any icon bundled with the theme, or even a [custom icon](https://squidfunk.github.io/mkdocs-material/setup/changing-the-logo-and-icons/#additional-icons). Add the following lines to `mkdocs.yml`:

```
theme:
  icon:
    admonition:
      <type>: <icon> 

```

Expand to show alternate icon sets

```
theme:
  icon:
    admonition:
      note: octicons/tag-16
      abstract: octicons/checklist-16
      info: octicons/info-16
      tip: octicons/squirrel-16
      success: octicons/check-16
      question: octicons/question-16
      warning: octicons/alert-16
      failure: octicons/x-circle-16
      danger: octicons/zap-16
      bug: octicons/bug-16
      example: octicons/beaker-16
      quote: octicons/quote-16

```

```
theme:
  icon:
    admonition:
      note: fontawesome/solid/sticky-note
      abstract: fontawesome/solid/book
      info: fontawesome/solid/info-circle
      tip: fontawesome/solid/bullhorn
      success: fontawesome/solid/check
      question: fontawesome/solid/question-circle
      warning: fontawesome/solid/exclamation-triangle
      failure: fontawesome/solid/bomb
      danger: fontawesome/solid/skull
      bug: fontawesome/solid/robot
      example: fontawesome/solid/flask
      quote: fontawesome/solid/quote-left

```

## Usage[¶](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#usage "Permanent link")

Admonitions follow a simple syntax: a block starts with `!!!`, followed by a single keyword used as a [type qualifier](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#supported-types). The content of the block follows on the next line, indented by four spaces:

Admonition

```
!!! note

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.

```

Note

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

### Changing the title[¶](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#changing-the-title "Permanent link")

By default, the title will equal the type qualifier in titlecase. However, it can be changed by adding a quoted string containing valid Markdown (including links, formatting, ...) after the type qualifier:

Admonition with custom title

```
!!! note "Phasellus posuere in sem ut cursus"

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.

```

Phasellus posuere in sem ut cursus

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

### Removing the title[¶](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#removing-the-title "Permanent link")

Similar to [changing the title](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#changing-the-title), the icon and title can be omitted entirely by adding an empty string directly after the type qualifier. Note that this will not work for [collapsible blocks](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#collapsible-blocks):

Admonition without title

```
!!! note ""

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.

```

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

### Collapsible blocks[¶](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#collapsible-blocks "Permanent link")

When [Details](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown-extensions/#details) is enabled and an admonition block is started with `???` instead of `!!!`, the admonition is rendered as a collapsible block with a small toggle on the right side:

Admonition, collapsible

```
??? note

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.

```

Note

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

Adding a `+` after the `???` token renders the block expanded:

Admonition, collapsible and initially expanded

```
???+ note

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.

```

Note

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

### Inline blocks[¶](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#inline-blocks "Permanent link")

[7.0.0](https://github.com/squidfunk/mkdocs-material/releases/tag/7.0.0) · Experimental

Admonitions can also be rendered as inline blocks (i.e. for sidebars), placing them to the right using the `inline` + `end` modifiers, or to the left using only the `inline` modifier:

Info

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

```
!!! info inline end

    Lorem ipsum dolor sit amet, consectetur
    adipiscing elit. Nulla et euismod nulla.
    Curabitur feugiat, tortor non consequat
    finibus, justo purus auctor massa, nec
    semper lorem quam in massa.

```

Use `inline end` to align to the right (left for rtl languages).

Info

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

```
!!! info inline

    Lorem ipsum dolor sit amet, consectetur
    adipiscing elit. Nulla et euismod nulla.
    Curabitur feugiat, tortor non consequat
    finibus, justo purus auctor massa, nec
    semper lorem quam in massa.

```

Use `inline` to align to the left (right for rtl languages).

**Important**: admonitions that use the `inline` modifiers _must_ be declared prior to the content block you want to place them beside. If there's insufficient space to render the admonition next to the block, the admonition will stretch to the full width of the viewport, e.g. on mobile viewports.

### Supported types[¶](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#supported-types "Permanent link")

Following is a list of type qualifiers provided by Material for MkDocs, whereas the default type, and thus fallback for unknown type qualifiers, is `note`:

`note`

Note

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

`abstract`, `summary`, `tldr`

Abstract

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

`info`, `todo`

Info

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

`tip`, `hint`, `important`

Tip

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

`success`, `check`, `done`

Success

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

`question`, `help`, `faq`

Question

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

`warning`, `caution`, `attention`

Warning

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

`failure`, `fail`, `missing`

Failure

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

`danger`, `error`

Danger

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

`bug`

Bug

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

`example`

Example

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

`quote`, `cite`

Quote

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

## Customization[¶](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#customization "Permanent link")

### Custom admonitions[¶](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#custom-admonitions "Permanent link")

If you want to add a custom admonition type, all you need is a color and an `*.svg` icon. Copy the icon's code from the [`.icons`](https://github.com/squidfunk/mkdocs-material/tree/master/material/.icons) folder and add the following CSS to an [additional style sheet](https://squidfunk.github.io/mkdocs-material/customization/#additional-css):

```
:root {
  --md-admonition-icon--pied-piper: url('data:image/svg+xml;charset=utf-8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512"><path d="M244 246c-3.2-2-6.3-2.9-10.1-2.9-6.6 0-12.6 3.2-19.3 3.7l1.7 4.9zm135.9 197.9c-19 0-64.1 9.5-79.9 19.8l6.9 45.1c35.7 6.1 70.1 3.6 106-9.8-4.8-10-23.5-55.1-33-55.1zM340.8 177c6.6 2.8 11.5 9.2 22.7 22.1 2-1.4 7.5-5.2 7.5-8.6 0-4.9-11.8-13.2-13.2-23 11.2-5.7 25.2-6 37.6-8.9 68.1-16.4 116.3-52.9 146.8-116.7C548.3 29.3 554 16.1 554.6 2l-2 2.6c-28.4 50-33 63.2-81.3 100-31.9 24.4-69.2 40.2-106.6 54.6l-6.3-.3v-21.8c-19.6 1.6-19.7-14.6-31.6-23-18.7 20.6-31.6 40.8-58.9 51.1-12.7 4.8-19.6 10-25.9 21.8 34.9-16.4 91.2-13.5 98.8-10zM555.5 0l-.6 1.1-.3.9.6-.6zm-59.2 382.1c-33.9-56.9-75.3-118.4-150-115.5l-.3-6c-1.1-13.5 32.8 3.2 35.1-31l-14.4 7.2c-19.8-45.7-8.6-54.3-65.5-54.3-14.7 0-26.7 1.7-41.4 4.6 2.9 18.6 2.2 36.7-10.9 50.3l19.5 5.5c-1.7 3.2-2.9 6.3-2.9 9.8 0 21 42.8 2.9 42.8 33.6 0 18.4-36.8 60.1-54.9 60.1-8 0-53.7-50-53.4-60.1l.3-4.6 52.3-11.5c13-2.6 12.3-22.7-2.9-22.7-3.7 0-43.1 9.2-49.4 10.6-2-5.2-7.5-14.1-13.8-14.1-3.2 0-6.3 3.2-9.5 4-9.2 2.6-31 2.9-21.5 20.1L15.9 298.5c-5.5 1.1-8.9 6.3-8.9 11.8 0 6 5.5 10.9 11.5 10.9 8 0 131.3-28.4 147.4-32.2 2.6 3.2 4.6 6.3 7.8 8.6 20.1 14.4 59.8 85.9 76.4 85.9 24.1 0 58-22.4 71.3-41.9 3.2-4.3 6.9-7.5 12.4-6.9.6 13.8-31.6 34.2-33 43.7-1.4 10.2-1 35.2-.3 41.1 26.7 8.1 52-3.6 77.9-2.9 4.3-21 10.6-41.9 9.8-63.5l-.3-9.5c-1.4-34.2-10.9-38.5-34.8-58.6-1.1-1.1-2.6-2.6-3.7-4 2.2-1.4 1.1-1 4.6-1.7 88.5 0 56.3 183.6 111.5 229.9 33.1-15 72.5-27.9 103.5-47.2-29-25.6-52.6-45.7-72.7-79.9zm-196.2 46.1v27.2l11.8-3.4-2.9-23.8zm-68.7-150.4l24.1 61.2 21-13.8-31.3-50.9zm84.4 154.9l2 12.4c9-1.5 58.4-6.6 58.4-14.1 0-1.4-.6-3.2-.9-4.6-26.8 0-36.9 3.8-59.5 6.3z"/></svg>')
}
.md-typeset .admonition.pied-piper,
.md-typeset details.pied-piper {
  border-color: rgb(43, 155, 70);
}
.md-typeset .pied-piper > .admonition-title,
.md-typeset .pied-piper > summary {
  background-color: rgba(43, 155, 70, 0.1);
}
.md-typeset .pied-piper > .admonition-title::before,
.md-typeset .pied-piper > summary::before {
  background-color: rgb(43, 155, 70);
  -webkit-mask-image: var(--md-admonition-icon--pied-piper);
          mask-image: var(--md-admonition-icon--pied-piper);
}

```

```
extra_css:
  - stylesheets/extra.css

```

After applying the customization, you can use the custom admonition type:

Admonition with custom type

```
!!! pied-piper "Pied Piper"

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et
    euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo
    purus auctor massa, nec semper lorem quam in massa.

```

Pied Piper

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.
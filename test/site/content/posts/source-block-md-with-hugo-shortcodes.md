+++
title = "Markdown source block with Hugo shortcodes"
tags = ["src-block", "shortcode"]
draft = false
+++

## Shortcodes escaped {#shortcodes-escaped}

The `figure` shortcodes in the two Markdown source code blocks below
should **not** be expanded.. they should be visible verbatim.


### Code block using code fences {#code-block-using-code-fences}

```md
{{</* figure src="http://orgmode.org/img/org-mode-unicorn-logo.png" */>}}
```


### Code block using `highlight` shortcode {#code-block-using-highlight-shortcode}

Here, the `-n` switch is added to the Org source block to
auto-enable[^fn:1] using the `highlight` shortcode.

{{< highlight md "linenos=table, linenostart=1">}}
{{</* figure src="http://orgmode.org/img/org-mode-unicorn-logo.png" */>}}
{{< /highlight >}}


## Shortcodes **not** escaped {#shortcodes-not-escaped}

The `figure` shortcodes in the Markdown source code blocks below
**should** be expanded.. you should be seeing a nice little unicorn
below.

```text
{{< figure src="http://orgmode.org/img/org-mode-unicorn-logo.png" >}}
```

Above a `#+BEGIN_EXAMPLE` .. `#+END_EXAMPLE` block is used just
arbitrarily. The Hugo shortcodes will remain unescaped in **any**
source/example block except for <span class="underline">Markdown source blocks</span> (annotated
with `md` language).

[^fn:1]: Even if the user has set the `HUGO_CODE_FENCE` value to `t` (via variable, keyword or subtree property), the Hugo `highlight` shortcode will be used automatically instead of code fences if either (i) the user has chosen to either show the line numbers, or (ii) has chosen to highlight lines of code (See the `ox-hugo` documentation on [Source Blocks](https://ox-hugo.scripter.co/doc/source-blocks)).
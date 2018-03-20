# Markdown style guide

This is my style guide for the Markdown language.

**Disclaimer:**
> I used some other style guides to make mine.
> At the bottom is a [list](#see-also) of the style guides i used.

Contents:
1.  [Document layout](#document-layout)
1.  [See also](#see-also)

## Document layout
In general, most documents benefit from some variation of the following layout:

```Markdown
# Document Title

Short introduction.

Contents:
1.  [Topic](#topic)
1.  [See also](#see-also)

## Topic

Content.

## See also
* https://link-to-more-info
```

1.  `# Document Title`: The first heading should be a level one heading, and
    should ideally be the same or nearly the same as the filename. The first
    level one heading is used as the page `<title>

1.  `Short introduction.` 1-3 sentences providing a high-level overview of the
    topic. Imagine yourself as a complete newbie, who landed on your "Extending
    Foo" doc and needs to know the most basic assumptions you take for granted.
    "What is Foo? Why would I extend it?"

1.  `Content:`: Put a list of links to each topic after the short introduction.

1.  `## Topic`: The rest of your headings should start from level 2.

1.  `## See also`: Put miscellaneous links at the bottom for the user who wants
    to know more or didn't find what she needed.

## See also
* https://github.com/google/styleguide/blob/gh-pages/docguide/style.md

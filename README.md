Markdown vs. Sphinx
===================

Docsite
-------

On sites like Reddit, StackOverflow, Trello, and GitHub, it is
common for users to format written content with Markdown. Markdown is
well on its way to becoming the defacto markup language of the Web.

[Hexo](https://github.com/tommy351/hexo/) is a Jekyll-like static site
generator specializing in Markdown-based content. Hexo is themable,
extensible, and it's supported by a vibrant community. With Hexo,
it's possible to create and maintain a static site with [impressive
docs](http://zespia.tw/hexo/docs/), all in Markdown while using your
favorite view engines (EJS, Jade, Haml) and CSS preprocessors (Less,
Stylus, SCSS). Various other niceties are included.

Sphinx is a documentation system for Python projects. It is
popular and proven in the Python community as seen in Ansible's
documentation along with many others.

Content in Sphinx is written in RST, a markup format similar to Markdown
albeit significantly more structured. The Sphinx system can also act as
a static site generator.

[Acrylamid](https://github.com/posativ/acrylamid) and
[Tinkerer](http://tinkerer.me/) appeal to those wanting to create and
maintain static site content with Sphinx / RST.

I think that, as soon as you want to present documentation on a
static site, the static site generator framework begins to matter more
and more. Someone has to code the site, and that person should enjoy
the work. Someone has to write the content, and that person should
enjoy the work. Creating and maintaining everything should be a breeze
with really low barrier to entry.

There's just enough obscure syntax and rigidity in Sphinx/RST to
be offputting to some % of potential contributors. For this reason,
I believe Markdown is better suited for documentation ceteris paribus,
with the caveat that it needs to be paired with Hexo. Hexo makes Markdown
documentation highly themable and much more scriptable.

The cost of Hexo is bringing in a bit of the Node.js ecosystem,
and foregoing Sphinx.

Man Pages
---------

Both Sphinx/RST and Markdown ([ronn](http://rtomayko.github.io/ronn/))
can generate man pages. The advantage of using Sphinx instead of Markdown
for man pages is that Sphinx can generate the man pages during the
Electrum build process without requiring ugly dependencies. To this end,
`asciidoc` would also work as it too has very few ugly deps.

If man pages will be generated beforehand and not built as
part of the Electrum build process, it's a person preference thing.
Otherwise I would recommend Sphinx or asciidoc for generating man
pages.

Summary
-------

I would recommend Hexo + whatever you want to write the man pages in. I
think it's great to generate man pages as part of the build process, but
it's easy to avoid doing.

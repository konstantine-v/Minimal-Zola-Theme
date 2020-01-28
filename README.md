# Minimal
Minimal is a minimal version of the Even [theme](https://github.com/getzola/even.git), this requires no JS to be run and the CSS is under 10kb.

## Contents

[[_TOC_]]

## Installation
First download this theme to your `themes` directory:

```bash
$ cd themes
$ git clone git@gitlab.com:MaterialFuture/minimal-zola-theme.git
```
and then enable it in your `config.toml`:

```toml
theme = "minimal"
```

you can alternatively add it as a git submodule to save space when commiting.

The theme requires tags and categories taxonomies to be enabled in your `config.toml`:

```toml
taxonomies = [
    # You can enable/disable RSS
    {name = "categories", rss = true},
    {name = "tags", rss = true},
]
```
If you want to paginate taxonomies pages, you will need to overwrite the templates
as it only works for non-paginated taxonomies by default.

It also requires to put the posts in the root of the `content` folder and to enable pagination, for example in `content/_index.md`:

```
+++
paginate_by = 5
sort_by = "date"
+++
```

## Options

### Top-menu
Set a field in `extra` with a key of `even_menu`:

```toml
# This is the default menu
even_menu = [
    {url = "$BASE_URL", name = "Home"},
    {url = "$BASE_URL/categories", name = "Categories"},
    {url = "$BASE_URL/tags", name = "Tags"},
    {url = "$BASE_URL/about", name = "About"},
]
```

### Homepage Content
Set the content of the homepage

```toml
# This is where you'll put content you want on the homepage however you want it.
#Homepage Stuff - You'll see this on the homepage
homepage_content = [
    {content = "Another One"},
]
```

If you put `$BASE_URL` in a url, it will automatically be replaced by the actual
site URL.

### Title
The site title is shown on the header. As it might be different from the `<title>`
element that the `title` field in the config represents, you can set the `even_title`
instead.


### SEO and Header Tags

Some SEO Tags have been added as well as some important head tags for browser compatibility.

I kept this as minimal as possible, but if you need more SEO tags you can find more [here in this gist I created]{https://gitlab.com/snippets/1933851}.
# Linkshrubbery

A fast, minimal, responsive [Hugo](https://gohugo.io/) theme similar to
[Linktree](https://linktr.ee).

![screenshot.png](https://raw.githubusercontent.com/tohn/linkshrubbery/main/images/screenshot.png)

## Features

- All of Hugo's builtin [Content
  Management](https://gohugo.io/content-management/)
- Fast loading with a 95-100 score on [Google
  PageSpeed](https://developers.google.com/speed/pagespeed/insights/)
- Ability to use [Bootstrap
  4](https://getbootstrap.com/docs/4.0/getting-started/introduction/)
  CSS classes via HTML/CSS in Markdown
- Ability to use [Font Awesome](https://fontawesome.com/) icons
- Ability to customize the theme styles via [Sass](https://sass-lang.com/)
- Ability to customize the following items via Hugo
  [configuration](https://gohugo.io/getting-started/configuration/) file
  - Meta description
  - Subtitle
  - Avatar
  - Logo
  - Background color
  - Font color

## Usage

This following guides installation, configuration, and updating of the
Linkshrubbery Hugo theme.

### Installation

Before installing this theme, be sure to [install
Hugo](https://gohugo.io/getting-started/quick-start/)
and [create a new
site](https://gohugo.io/getting-started/quick-start/#step-2-create-a-new-site).

To install the theme, run the following from the root directory of your
Hugo site:

```bash
git submodule add https://github.com/tohn/linkshrubbery.git themes/linkshrubbery
```

### Configuration

Next, open the `config.toml` file in the root of your Hugo site and set
the theme:

```toml
theme = "linkshrubbery"
```

Example `config.toml` file with all configuration features filled out:

```toml
baseURL = "https://example.org"
title = "Linkshrubbery"
languageCode = "en-us"
theme = "linkshrubbery"
relativeURLs = true
enableEmoji = true
enableRobotsTXT = true
copyright = "&copy; Year, Your Name"
disableKinds = ["taxonomy", "term"]

# Configuration Features
[params]
  description = "Your meta description"  # Your meta description of the site
  avatar = "/images/avatar.png"          # Path to avatar image starting from the static directory
  logo = "/images/logo.png"              # Path to logo image starting from the static directory
  [params.style]                         # CSS style overrides
    backgroundColor = "#f8f9fa"
    fontColor = "#212529"
```

### Adding content

This theme uses [Data
Templates](https://gohugo.io/templates/data-templates/) for content. If
you want to add a "page", create two files:

- `data/shrubberies/new_page.yaml`
- `content/new_page.md`

The file `new_page.yaml` could contain the following content:

```yaml
---
name: "Test"
description: "Test."
avatar: "/images/avatar.png"
social:
  - name: "GitHub"
    link: "https://github.com/test"
    icon: "github"
  - name: "Website"
    link: "https://example.org"
    icon: "link"
    icon_set: "fas" # if it's not a brand, you have to provide the icon_set
  - name: "Instagram"
    link: "https://www.instagram.com/test/"
    icon: "instagram"
shrubberies:
  - name: "Ni!"
    link: "https://www.youtube.com/watch?v=2UbtcmjfKa8"
    icon: "youtube"
    icon_set: "fab" # here it's the other way around: if it's not a brand, you have to provide the icon_set
```

The file `content/new_page.md` could contain the following content:

```md
---
title: "Test"
---
Test.
```

### Updating

To get updates to the theme, run the following from the root directory
of your Hugo site:

```bash
git submodule update --remote themes/linkshrubbery
```

### Adding Custom Styles

Adding custom styles to the linkshrubbery theme is simple. There are two
options available for doing so.

#### Option 1

In the `config.toml` file of your website, you can set the following
custom style parameters:

```toml
[params.style]
  backgroundColor = "#f8f9fa"
  fontColor = "#212529"
```

If you'd like to see other custom styles available as config parameters,
please open an [issue](https://github.com/tohn/linkshrubbery/issues).

#### Option 2

To add custom [Sass](https://sass-lang.com/) styles to the linkshrubbery
theme, you'll need to add the following file to the
[assets](https://gohugo.io/hugo-pipes/introduction/#asset-directory)
directory of your site:

- `assets/sass/custom.scss`

In the file, you can use [Sass](https://sass-lang.com/) syntax to
declare your custom styles. After doing so, you should see custom
styling added to your linkshrubbery based Hugo site.

## Demo

To run a live demo of the theme on your laptop, run the following from
the `exampleSite` directory of the linkshrubbery theme:

```bash
hugo server --themesDir ../.. --watch --verbose --cleanDestinationDir --disableFastRender
```

For a live demo of the theme, see at:

- [ls.uxg.ch](https://ls.uxg.ch)

## Contributing

If you have an idea for a new feature or found a bug, please feel free
to use Github [issues](https://github.com/tohn/linkshrubbery/issues)
to let me know.

## License

[MIT](LICENSE)

## Credits

Thanks a lot! :blush:

[Credits](CREDITS.md)

## TODO

- use next-gen formats for images, like webp
- fix `isset`
- provide automatic width and height for images

# LiteNav

A simple servless nav page

# Design Philosophy and 101

This navigate page design to small team/studio usage, Account and permission not include, Best experience is server deploy with static cdn. But even through this, You still can easily deploy it into personal mode.

The page only designed for [`Sarasa Fixed Slab`](https://github.com/be5invis/Sarasa-Gothic), Missing of font will cause page into chaos.

Press `Shift` can manualy switch light/black mode. And this perfer setting will storage in `localStorage`.

# Deploy

- Setup a web server to host `index.html`  and font files
- Modify `<link rel="shortcut icon" type="image/png" href="favicon.ico">` to your real icon file URL
- Modify `src: url("sarasa-fixed-slab-sc-extralight.ttf");` to your to your real font file URL
- Create `content.json`, Config schema and guide below, (Name can be change `loadUrlContent('content.json');` or even another server)
- Done, Enjoy.

Hints:

- Always rember add `Cache-Control: no-cache` header to `content.json`
- If you want to use CDN then make sure you already config the CORS settings properly
- If you want change font, Add more `@font-face` and modify `font-family` section like this

```text
 .content > div:nth-child(1) > table tr:nth-child(2n+1) > td:nth-child(1) > div {
    /* BUTTON GROUP TITLE FONT */
    /*font-family: "Sarasa Fixed Slab $$ Light", serif;*/
    font-size: 30px;
    margin-right: 40px;
    width: max-content;
    min-width: max-content;
}
```

Recommendation: Use `Sarasa Fixed Slab $$ Light` in Button title and Button short.

# Config the content.json

## Config element

```json
{
  "title": "",
  "banner": "",
  "notify": [],
  "content": []
}
```

- `title` string, The title text of this page which show in broswer tabs
- `banner` string, The text shows in banner area
- `notify` array of string, A simple boardcast area to show some important message
- `content` array of object , The main feature of LiteNav

## Content element

```json
{
  "title": "",
  "menus": []
}
```

- `title` string, The title text of group
- `menus` array of object, content define

## Menus element

```json
{
  "title": "",
  "short": "",
  "url": ""
}
```

- `title` string, The title text
- `short` string, Sub title or I call it short url text
- `url` string, When click jump to this url, Remove this key for no jump

- An empty element means `<br/>` A line warp

# A Demo

![](https://github.com/Alceatraz/LiteNav/blob/master/demo.jpg)

```json
{
  "title": "BTStudio Portal",
  "banner": "BlackTechStudio Portal",
  "notify": [
    "Scheduled Maintance: Jenkins will unavailable at 17:00 ~ 18:00",
    "Scheduled Maintance: Office network will offline at 17:00 ~ 24:00"
  ],
  "content": [
    {
      "title": "Common",
      "menus": [
        {
          "title": "Google",
          "short": "www.google.com",
          "url": "https://www.google.com"
        },
        {
          "title": "Bing",
          "short": "www.bing.com",
          "url": "https://www.bing.com"
        },
        {},
        {
          "title": "BTStudio",
          "short": "www.btstudio.com"
        },
        {
          "title": "Foo",
          "short": "www.foo.com"
        },
        {
          "title": "Bar",
          "short": "www.bar.com"
        }
      ]
    },
    {
      "title": "Foo",
      "menus": [
        {
          "title": "GitHub",
          "short": "www.github.com",
          "url": "https://www.github.com"
        },
        {
          "title": "GitLab",
          "short": "www.gitlab.com",
          "url": "https://www.gitlab.com"
        }
      ]
    },
    {
      "title": "Bar",
      "menus": [
        {
          "title": "Steam",
          "short": "test.bar.com"
        },
        {
          "title": "Steam",
          "short": "test.bar.com"
        },
        {
          "title": "Steam",
          "short": "test.bar.com"
        },
        {
          "title": "Steam",
          "short": "test.bar.com"
        },
        {
          "title": "Steam",
          "short": "test.bar.com"
        },
        {
          "title": "Steam",
          "short": "test.bar.com"
        },
        {},
        {
          "title": "Steam",
          "short": "test.bar.com"
        },
        {
          "title": "Steam",
          "short": "test.bar.com"
        },
        {
          "title": "Steam",
          "short": "test.bar.com"
        },
        {},
        {
          "title": "Steam",
          "short": "test.bar.com"
        }
      ]
    }
  ]
}
```

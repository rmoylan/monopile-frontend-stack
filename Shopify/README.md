# Shopify

Shopify has two versions of their CLI, `Theme Kit` and `Shopify CLI`. `Theme Kit` is used for stores up to version 2 and `Shopify CLI` is for versions 2+.

## Theme Kit

[Getting started](https://shopify.dev/themes/tools/theme-kit/getting-started)

#### Notes

Changes made from the local version will update almost immediately to the live site. There doesn't seem to be a way to make changes and view without it going live. The proposed workaround is to duplicate your live theme and then target that duplicated theme for changes ([documented here](https://community.shopify.com/c/Shopify-Design/Preview-theme-changes-locally-before-going-to-store/td-p/442350#:~:text=To%20do%20this%20just%20go,would%20with%20your%20main%20store)). This could be used as a way to create releases. Each version in dev can be renamed to reflect versioning, and once the latest is pushed live, the previous will show up in the Theme Library.

## Shopify CLI

#### Features

- Sections available on all pages. In `Theme Kit` sections were limited to the homepage.
- [App Blocks](https://shopify.dev/apps/online-store/theme-app-extensions?itcat=partner_blog&itterm=shopify_online_store&shpxid=a582daeb-A96A-408A-CE9C-77C0B0B9A934) Allow developers to create app extensions that can be used across themes.
- [Improved Metafields](https://www.youtube.com/watch?v=KulSA9U2-u8&ab_channel=ShopifyDevs)
- Theme editor has more ability to modify pages via hiding/showing blocks
- Github can be connected directly to Shopify for ease of dev/publishing
- `Shopify CLI` allows for better dev experience. Hot reload with local dev server, publish from terminal, theme check for catching issues, populate dummy data
- By the end of the year, it will be required that all themes in the Shopify Theme Store and apps in the Shopify App Store use the new infrastructure.
- Filtering is greatly upgraded

#### Installation

[Shopify CLI](https://shopify.dev/themes/tools/cli/installation)

#### Dev

Currently there is a bug in the CLI when first creating the shop, but is solved by following [this solution](https://github.com/Shopify/shopify-cli/issues/1309#issuecomment-873221248)

- Create dev store at partners.shopify.com
- Log into store in CLI

```
shopify login --store=[STORE_NAME].myshopify.com
```

- Serve via CLI

```
shopify theme serve
```

- Add dummy products

```
shopify populate products
```

- Push theme in order to view in Shopify environment (pushing to Git does not push changes to Shopify)
```
shopify theme push
```

#### Notes
When working locally, it is easy to mistakenly pull changes from the shopify environment that will override your local version and vice versa. To avoid this, only work in one environment or the other at a time, saving/pushing before switching to the other environment.

#### Update to 2.0
Migrate Liquid templates into JSON templates.

- Move Liquid and HTML code to sections
## Reset Dusk for new store
In `settings_data.json`
- change `social_[SOCIAL NETWORK]` to `""`
- change `sections.header.settings.logo` to `""`

In `index.json`
- change `settings.carousel.blocks` to `{}`
- change `settings.carousel.block_order` to `[]`
- change `settings.image_banner` to `{}`
- change `settings.cta-nav.blocks` to `{}`
- change `settings.cta-nav.block_order` to `[]`
- change `settings.featured_products.settings` to `{}`



## Links

[API Documentation](https://shopify.dev/api/)
[Spotify Cheatsheet](https://www.shopify.com/partners/shopify-cheat-sheet?shpxid=a2be037a-2610-484B-641E-F0FF61CEA0C9)
[Online Store 2.0 (Shopify CLI) Introduction](https://www.shopify.com/partners/blog/shopify-online-store)

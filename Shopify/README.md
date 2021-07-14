# Shopify links

Shopify has two versions of their CLI, `Theme Kit` and `Shopify CLI`. `Theme Kit` is used for stores up to version 2 and `Shopify CLI` is for versions 2+.

## Theme Kit

[Getting started](https://shopify.dev/themes/tools/theme-kit/getting-started)
These use theme kit, which you can install [here](https://shopify.dev/themes/tools/theme-kit/getting-started).

#### Notes

Changes made from the local version will update almost immediately to the live site. There doesn't seem to be a way to make changes and view without it going live. The proposed workaround is to duplicate your live theme and then target that duplicated theme for changes ([documented here](https://community.shopify.com/c/Shopify-Design/Preview-theme-changes-locally-before-going-to-store/td-p/442350#:~:text=To%20do%20this%20just%20go,would%20with%20your%20main%20store)). This could be used as a way to create releases. Each version in dev can be renamed to reflect versioning, and once the latest is pushed live, the previous will show up in the Theme Library.

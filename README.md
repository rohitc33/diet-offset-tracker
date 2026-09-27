# Diet Offset Tracker

A single-file, local-only web app for logging meat purchases and tracking how much to donate to animal welfare causes to offset them.

Open `index.html` in any browser. No server, build step or network access needed. Everything is saved to the browser's `localStorage`.

## How the offset is calculated

Each meal's offset is the *welfare gap*: how much more that meat would have cost if a national law required every farm to meet a high welfare standard ("tier B"). That means no cages or crates, lower stocking density, slower-growing breeds and outdoor access where relevant, pain relief, and effective stunning.

```
offset = price paid × meat share × (humane multiplier − 1)
```

- **Humane multiplier**: the estimated long-run retail price once *all* meat meets tier B, divided by today's price. It reflects production cost at scale, not today's niche prices or the temporary spike while farms convert. Current values: chicken, turkey and duck 2.0×, eggs and pork 1.75×, veal 1.4×, beef 1.3×, farmed fish 1.2×, shrimp 1.1×, lamb and goat 1.08×, wild fish 1.05×. Chicken, eggs and pork are partly backed by cost studies (ADAS, Coalition for Sustainable Egg Supply, Prop 12 research). The rest are labelled estimates with the reasoning given. For comparison, each meat also shows the *legislated minimum* (Prop 12 / EU-style rules) and today's *farm-direct* pasture price. Everything can be edited in Settings.
- **Meat share**: how much of the price was the meat itself. Restaurants spend about 28–35% of the menu price on all ingredients, so the default for a restaurant dish is 20%. A subsidized work cafeteria charges roughly the ingredient cost, and meat is about two-thirds of the ingredients, so cafeteria meals default to 65%. Groceries default to 100%.

The offset measures the *price* gap, not suffering. Cheap fixes like stunning fish and shrimp barely raise the price, so those offsets are small even though a dollar of fish or shrimp involves many animals.

Changing settings only affects new entries. Logged meals keep the values they were logged with.

## Features

- Quick meal entry: meat type dropdown, price, optional dish name, date, restaurant / cafeteria / groceries toggle, and a live offset preview
- Running offset total for the year, plus a year picker for past years
- Record donations to see how much is still left to give ("Fill balance" pre-fills the balance)
- Breakdown of the offset by meat type
- Delete with undo, JSON export/import for backups, and "Recalculate logged meals" to apply changed settings to past entries
- App-style layout with a bottom tab bar: **Log** (totals and the meal form, fits on one phone screen), **History** (by-meat breakdown and meals), **Donate** (log donations and see the balance), **Settings** (meat shares, multipliers with sources, method, backup)
- Mobile-friendly: large tap targets, no zoom-on-focus on iOS, safe-area padding for notched phones, and it can be added to the home screen

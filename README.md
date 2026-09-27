# Diet Offset Tracker

A single-file, local-only web app for logging meat purchases and tracking how much to donate to animal welfare causes to offset them.

Open `index.html` in any browser. No server, build step or network access needed. Everything is saved to the browser's `localStorage`.

## How the offset is calculated

Imagine a law that required every farm to treat animals well: no cages or crates, less crowding, breeds that grow at a natural pace, time outdoors where it suits the animal, pain relief for painful procedures, and stunning so animals are unconscious when they're killed. Meat would cost more. Each meal's offset is that extra cost, which you give to animal welfare causes instead.

```
offset = what you paid × share of the price that's meat × (humane price − 1)
```

For example, a $20 restaurant chicken dish: about 20% of a restaurant price is the meat ($4), and humane chicken would cost about 2× as much, so the offset is $4 × (2 − 1) = $4.00.

- **Humane price**: an estimate of what the meat would cost once *every* farm meets that standard, as a multiple of today's price. It's not what specialty humane meat costs today (small farms cost more to run, and shops charge extra for the label), and it's not the short-term spike while farms switch over. Current values: chicken, turkey and duck 2×, eggs and pork 1.75×, veal 1.4×, beef 1.3×, farmed fish 1.2×, shrimp 1.1×, lamb and goat 1.08×, wild fish 1.05×. Only chicken, eggs and pork are based on cost studies; the rest are marked as best guesses, with the reasoning. For comparison, each meat also shows the price under current welfare laws (California, EU) and what pasture farms charge today.
- **Share of the price that's meat**: restaurants spend about 30% of the menu price on ingredients, mostly meat, so 20% of a restaurant price counts as meat. A subsidized work cafeteria charges roughly the ingredient cost, and meat is about two-thirds of that (65%). Groceries count as 100%.

This measures cost, not suffering. Cheap fixes like stunning fish and shrimp barely change the price, so their offsets come out small, even though each dollar spent on them involves many more animals.

All values can be edited in the app's Settings tab. Changes apply to new meals only, unless you use "Recalculate past meals".

## Features

- Quick meal entry: meat type dropdown, price, optional dish name, date, restaurant / cafeteria / groceries toggle, and a live offset preview
- Running offset total for the year, plus a year picker for past years
- Record donations to see how much is still left to give ("Fill balance" pre-fills the balance)
- Breakdown of the offset by meat type
- Delete with undo, JSON export/import for backups, and "Recalculate past meals" to apply changed settings to meals already logged
- App-style layout with a bottom tab bar: **Log** (totals and the meal form, fits on one phone screen), **History** (by-meat breakdown and meals), **Donate** (log donations and see the balance), **Settings** (how much of the price is meat, humane prices with sources, how it's calculated, backup)
- Mobile-friendly: large tap targets, no zoom-on-focus on iOS, safe-area padding for notched phones, and it can be added to the home screen

# Diet Offset Tracker

A single-file, local-only web app for logging meat purchases and tracking how much to donate to animal welfare causes to offset them.

Open `index.html` in any browser. No server, build step or network access needed. Everything is saved to the browser's `localStorage`.

## How the offset is calculated

Each meal's offset is the *welfare gap*, meaning the extra you would have paid if the meat had come from animals raised and slaughtered to high welfare standards:

```
offset = price paid × meat share × (humane multiplier − 1)
```

- **Humane multiplier**: roughly how many times more a high-welfare version of that meat costs than conventional (e.g. chicken 3.5×, pork 2.75×, beef 1.6×). These are rough estimates and can be edited per meat type.
- **Meat share**: how much of the price was the meat itself. Defaults are 35% for a restaurant dish and 100% for groceries. Both are editable.

Changing settings only affects new entries. Logged meals keep the values they were logged with.

## Features

- Quick meal entry: meat type dropdown, price, optional dish name, date, restaurant/groceries toggle, and a live offset preview
- Running offset total for the year, plus a year picker for past years
- Record donations to see how much is still left to give ("Fill remaining" pre-fills the balance)
- Breakdown of the offset by meat type
- Delete with undo, JSON export/import for backups

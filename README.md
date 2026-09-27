# Diet Offset Tracker

A single-file, local-only web app for logging meat purchases and tracking how much to donate to animal welfare causes to offset them.

Open `index.html` in any browser. No server, build step or network access needed. Everything is saved to the browser's `localStorage`.

## How the offset is calculated

Each meal's offset is the *welfare gap*, meaning the extra you would have paid if the meat had come from animals raised and slaughtered to high welfare standards:

```
offset = price paid × meat share × (humane multiplier − 1)
```

- **Humane multiplier**: how many times more the high-welfare version costs than ordinary supermarket meat. Where data exists, it compares USDA AMS 2026 averages for pasture-raised or grass-fed meat sold directly by farms with BLS average supermarket prices for the same product. Current values: chicken 3.7×, eggs 3.9×, pork 2.7×, turkey 2.4× (weak data), beef 1.55×. Meats without good price data (duck, veal, lamb, goat, fish, shrimp) are marked as estimates. Every value, its reasoning and its sources are shown in the app's settings and can be edited.
- **Meat share**: how much of the price was the meat itself. Restaurants spend about 28–35% of the menu price on all ingredients, so the default for a restaurant dish is 20%. A subsidized work cafeteria charges roughly the ingredient cost, and meat is about two-thirds of the ingredients, so cafeteria meals default to 65%. Groceries default to 100%.

The offset measures the *price* gap, not suffering. Cheap fixes like stunning fish and shrimp barely raise the price, so those offsets are small even though a dollar of fish or shrimp involves many animals.

Changing settings only affects new entries. Logged meals keep the values they were logged with.

## Features

- Quick meal entry: meat type dropdown, price, optional dish name, date, restaurant / cafeteria / groceries toggle, and a live offset preview
- Running offset total for the year, plus a year picker for past years
- Record donations to see how much is still left to give ("Fill balance" pre-fills the balance)
- Breakdown of the offset by meat type
- Delete with undo, JSON export/import for backups
- Mobile-friendly: large tap targets, no zoom-on-focus on iOS, safe-area padding for notched phones, and it can be added to the home screen

# Spreadsheet

A min-max run requires precise calculations, including selling items to earn an exact amount of G, mining and smelting Ore in exact amounts, etc. Over the course of several Year 1 Spring 1 runs, I created a [spreadsheet](min-max.ods) in [LibreOffice Calc](https://www.libreoffice.org/download/download) to track daily information, bundle fulfillment, items and professions, and more.

Note that the spreadsheet's daily tabs are not completed yet. I will update them as I complete runs. The tabs that are present likely contain data from my actual runs until I complete enough of them to be sure of the spreadsheet's robustness.

## Which cells are editable?

Generally, cells shown in red are editable. However, you are free to modify the spreadsheet however you want. Explore!

## *Daily* tab

![Daily Tab](images/daily-tab.png)

The *Daily* tab has four pieces of information, all of which may be selected from a drop-down list after selecting the cell. At the beginning of each day in your run, select the *Daily* tab and update the values as necessary.

1. *Season* indicates what season it is.
2. *Day* indicates what day it is.
3. *Tomorrow's Weather* indicates what tomorrow's weather will be, as reported by the [Television](https://stardewvalleywiki.com/Television).
4. *Today's Luck* indicates what today's luck will be, as reported by the Television.

These cells do not affect any other cells.

## *Bundles* tab

![Bundles Tab](images/bundles-tab.png)

The *Bundles* tab is used to track items you need for every bundle. Items that occur in multiple bundles are also listed to remind you to collect more than one of certain items.

## *Items and Professions* tab

![Items and Professions](images/items-and-professions-tab.png)

The *Items and Professions* tab contains all the data necessary for item tracking on daily tabs to work. The list of items are not currently exhaustive, however, so please submit an [issue](https://github.com/nathan-alden-sr/stardew-valley/issues) if you notice something missing.

In general, you will not need to use this tab except to change the profession information in red. Note that changing these professions will affect all calculations done on older daily tabs; this is unavoidable.

Prices are automatically calculated using precise formulas that include proper decimal truncation.

Different combinations of base price and tiered prices are present based on whether a particular item benefits from professions, special effects (e.g., [Bear's Knowledge](https://stardewvalleywiki.com/Bear%27s_Knowledge)), both, or neither.

## Daily tabs

Daily tabs contain many different data depending on the needs of the day. However, there are several designs that are useful for many days.

### Item tables

![Item Tables](images/item-tables.png)

Item tables appear in various forms on many daily tabs. The spreadsheet will automatically look up an item by its name after you type it in. If the item supports a quality, append `<space>S` for *Silver*, `<space>G` for *Gold*, or `<space>I` for *Iridium* to the item name and the correct quality's sell price will be used.

Note the hidden *B* and *C* columns. Be sure that when creating new rows you highlight an existing row and copy the entire row, not just the *A* and *D* columns. These hidden columns are used in the formulas that calculate qualities.

You can sort these tables any way you wish.

#### Determining the most valuable item stacks with which to fill your inventory

Sometimes, the guide requires that you fill your inventory with the most valuable items to ship. To accomplish this, fill out the table, then select the entire *Total G* column, then sort descending.

![Sorting Item Tables](images/sorting-item-tables.png)

#### Determining exactly what items must be shipped to reach a daily target G

Sometimes, the guide requires that you ship enough items to reach a certain target G for the following day. The principle is that by keeping G as close to zero as possible, a minimum amount of G will be lost due to the 10% penalty for passing out.

![Shipping Targets](images/shipping-targets.png)

The *Qty* column is the actual quantity available for selling.

The *Modified Qty* column is the quantity of the item you actually plan on selling.

The *Sum G* column keeps a running total of the sum of all items shipped. This data is primarily used in formulas.

When a *Remaining G* value goes negative, it means you will have shipped more than is necessary. Usually, this is unavoidable but careful selection of the items you ship can minimize the extra income.

Note that *Inventory G* columns are not merely numbers but are formulas. It is your responsibility to modify the formula to account for passing out or not.

### G in Inventory

Often, you will need to provide the amount of G in your inventory. On days where this number is used to calculate the next day's G total, be sure to account for the 10% penalty for passing out. Use the formula `=1234*0.9`, for example, to indicate you have 1,234g at the end of the current day but plan on passing out.

### Search

![Search](images/search.png)

Nearly all daily tabs include a search feature. Simply type in an item name and optionally a quality (using the syntax described above) and its prices will be displayed. This helps avoid the need to change tabs to the *Items and Professions* tab.

### Other calculations

There are many one-off calculations for various days. These are defined on an as-needed basis depending on what the guide requires. For example, these calculations help you know exactly how many Ore and Quartz to farm to make a precise number of Quality Sprinklers.

![Other Calculations](images/other-calculations.png)
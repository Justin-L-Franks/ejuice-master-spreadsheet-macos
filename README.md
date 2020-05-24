# DIY E-Juice Master Spreadsheet (v1.0.3)
*(Note: The contents of this file are a copy of the information in the "Instructions" sheet of the spreadsheet.)*

I initially created this spreadsheet for my own personal use, in order to create, organize, and mix e-juice recipes. Calculations for mixing both by weight and by volume are performed automatically, based on a few constants, such as the strength of the nicotine base used, the desired batch size, and the densities of each type of ingredient.

I have successfully used this as my primary means of recipe creation, organization, and mixing for some time, and figured it could be useful for other Mac users.

Various changes had to be made in order to make it suitable for a public release. For example, these instructions and notes needed to be added. But the biggest change was needed because I always mix my own juice at max VG, so in the original version, I only put in the calculations for max VG juice.

Since other mixers use different VG/PG ratios, I needed to allow setting a VG/PG ratio, and adjust the calculations to account for this. It was relatively straightforward, but definitely a lot more complex than my original private version. The tricky part was how to handle an “impossible” request, such as mixing a recipe with 15% flavor and 3% PG nicotine base, with the VG/PG ratio set to 85/15. The PG flavorings plus the PG-based nicotine makes up 18% of the recipe, leaving only 82% available for VG. Basically, the formulas are set up so that in situations like this, it will automatically “revert” to max VG for that specific recipe only. Other recipes without as much flavoring, which would allow for an 85/15 mix, are not affected, and will continue to calculate and show the correct amount of VG and PG necessary for the desired VG/PG ratio.

The default settings are fairly common ones: 70/30 VG/PG ratio, mixed at 3 mg/mL of nicotine using 100 mg/mL PG nicotine base, and a normal batch size of 30 mL, with “tester” batches of 10 mL. You can of course adjust these to your own preferences, by following the instructions in the next section.

If you find any bugs, or have any comments or suggestions, please let me know at justin.franks@gmail.com.

*I hope you find this tool as useful for you as it is for me. If you do, and would like to thank me for sharing it, you can PayPal me whatever you feel it is worth to you at https://www.paypal.me/justinlfranks, or if you already have a PayPal account, you can simply send a payment to justin.franks@gmail.com.*

## Setup
1. **Select the “Settings / Template” sheet.**
2. **In the “Mix Settings” table, enter in the desired values.** *(Just enter the number values, the units are applied automatically)*
   - **Base Nicotine Strength:** The concentration of nicotine in your nicotine base liquid (in mg/mL).
   - **Mixed Nicotine Strength:** The final nicotine concentration in your mixed juice (in mg/mL).
   - **Mixed VG Percentage:** To set the VG/PG ratio of your mixed juice. For 70/30 juice, enter “70”. For max VG juice, enter “100”. The recipes will automatically reduce the percentage of VG based on the total flavor concentration and nicotine concentration as needed. For example, say you enter in a recipe with 10% total flavor, and 3 mg/mL nicotine using 100 mg/mL base. The flavoring and nicotine adds up to 13% of the total mix. If you put 90% for the mixed VG percentage, the recipe will drop this down to 87%, since that is the maximum amount possible for that recipe. A value of 100% here will always give the maximum percentage of VG possible for each recipe, regardless of the amount of flavoring or nicotine.
   -	Default Mix Volume: Your normal batch size (in mL).
   -	Default Tester Volume: The amount you make when testing a recipe before you make a larger batch (in mL).
3. **If mixing by weight, in the “Ingredient Densities” table, adjust the values to correspond to your base ingredients.** *(Just enter the number values, the units are applied automatically)*
   -	**Propolyne glycol:** Typically 1.03 mg/mL.
   -	**Vegetable glycerin:** Typically 1.25 mg/mL.
   -	**Nicotine base:** For 100 mg/mL PG-base nicotine, typically 1.04 mg/mL.
   -	**Flavoring:** Typically 1.03 mg/mL, since the vast majority of flavors are PG base.

## Recipe Creation
1. **Select the “Settings / Template” sheet.**
2. **Click anywhere in the “Recipe Template” table, then click on the blue and gray circular icon which appears to the top and left, to select the entire table.**
3. **Copy the “Recipe Template” table to the clipboard.** *(Command + C, or right click the blue and gray circular icon and select “Copy”, or go to the “Edit” menu and select “Copy”)*
4. **Select the sheet where you want to add the recipe.**
5. **Paste the “Recipe Template” table.** *(Command + V, or right-click and select “Paste”, or go to the “Edit” menu and select “Paste”. Be sure not to have any other table partially selected, or else Numbers will try to paste the recipe template into that table instead of creating a new one)*
6. **Click anywhere on the newly-created table, then click and drag the blue and gray circular icon at the top left, to move the table to the desired location.**

## Recipe Editing
1. **The *only* cells you need to touch in a recipe are the manufacturer abbreviations, flavor names, flavor percentages, and the “Tester” checkbox. Everything else is calculated automatically based on the values in the “Settings / Template” sheet and the flavor percentage values you enter in.**
2. **You can add flavor ingredients by adding a new row in the appropriate position, by clicking on any cell in an existing flavor row, then going to the “Table” menu and selecting “Add Row Above” or “Add Row Below”.** *(Do not add a new row below the last existing flavor row, or else the “Weight” calculation for the new row will not work. This is a bug / undesired behavior in Numbers. If you accidentally do this, you can fix it by copying the “Weight” value for a different flavor, and pasting it in the new row.)*
3. **You can delete flavor ingredients by right-clicking on any cell in that row, then selecting “Delete Row”. Alternatively, you can click on any cell in that row, then go to the “Table” menu and select “Delete Row”.**
4. **When entering a flavor concentration of less than 1%, do not include the leading zero.** *(For 0.5%, enter in “.5”, not “0.5”, otherwise it will be interpreted as 50%)*
5. **The “Tester” checkbox near the bottom right of the table, above the “notes” section, will toggle between the “Default Mix Volume” and “Default Tester Volume” values in the “Settings / Template” sheet.** *(This allows you to quickly switch between a smaller batch when you are creating or refining a recipe, and a larger batch when you are mixing a completed recipe)*

## Notes / Suggestions
1. Using multiple sheets, one for each “category” of juice, helps to keep things organized when you have a large number of recipes. I’ve included several categories to get you started, which you can edit, add, or delete based on your preferences.
2. I like to keep track of the changes I make to my recipes during development, in case I want to refer to or go back to an older version. I do this by putting each version in a horizontal “row”, with the newest version all the way to the left, with each older version put further to the right.
3. A few “sample” recipes are included in the “Bakery / Dessert” category, one with multiple revisions, and one which was taken from another mixer then modified, to show how I keep my recipes organized.
4. I’ve included a “notes” section in the recipe template, which is currently set up to put in your thoughts and tasting notes after various steeping times. In “Mixing Notes”, I typically describe the target flavor profile for my own recipes, and for another mixer’s recipe, I include a link to the source. “Freshly mixed” is for tasting notes made immediately (as a “shake and vape”), “Steeped 1 Day / 3 Days / 1 Week” is for tasting notes after each length of steeping, and “Final Notes” is for ideas on how to improve the recipe for a potential newer version. If you want to use a different format, be sure to edit the recipe template in the “Settings / Template” sheet, so when you copy and paste it to add a new recipe, it uses the format you prefer.
5. When you organize multiple revisions of a recipe as I do, sometimes the number of ingredients will change between versions. This can put the revisions of other recipes below it out of alignment. To compensate for this, I adjust the heights of the “Mixing Notes” cells of the revisions with less ingredients, until the bottoms of those cells line up. A similar misalignment can also occur when the notes of some revisions are longer than the others, so the height of the corresponding notes cells in the other revisions should be adjusted to compensate. Examples of this alignment fix are included in the sample data in the “Bakery / Dessert” sheet.
6. While you can overwrite the “global” values (mix volume, nicotine strength, etc.) in an individual recipe, and the calculations will still work, it is not recommended. It is always best to edit the values in the “Settings / Template” sheet, even if it is a “one-off”, like mixing a larger batch than normal. Eventually, you will make a change in an individual recipe, and forget to change it back afterwards. Then when you do change one of the “global” values, that one recipe will not be automatically updated.

## License and Terms
This spreadsheet is licensed under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 (CC BY-NC-SA 4.0) license. What this means is that you are free to use and modify it an any way for non-commercial purposes. You may also freely share it as-is, or with any modifications you have made, with only a few restrictions. You must retain the copyright notice and licensing information at the bottom of this file. If you wish to distribute a version with any modifications you have made, your version must also be licensed under the CC BY-NC-SA 4.0 license, giving users of your version the same rights and freedoms you were granted with this original version. Your modified version must also clearly indicate that it has been modified, that it is licensed under the CC BY-NC-SA 4.0 license, that the original version was created by Justin L. Franks (justin.franks@gmail.com), and must also include a link to the GitHub repository for the original version. Including these requirements within the copyright notice and licensing information at the bottom of the "Instructions" sheet is sufficient for this purpose.

If you wish to use this spreadsheet commercially (such as by an e-liquid manufacturer, or a vape shop who mixes and sells a “house brand” of e-liquid), please contact me at justin.franks@gmail.com.

This spreadsheet is intended to facilitate the mixing of e-juice for vapor products, an action which entails inherent dangers. I am not responsible for any losses, damages, or injuries sustained while using this spreadsheet, even if caused by an error or bug in the content of this spreadsheet or the code which calculates the amounts of ingredients to be mixed. It is the sole responsibility of the user to verify that all these calculations are correct before using this spreadsheet as a mixing guide, and to continuously verify said calculations for the entire duration this spreadsheet is used.

All local laws regarding the mixing, possession, and consumption of e-juice for vapor products and its constituent ingredients, in the jurisdiction where this spreadsheet is being used, including but not limited to age restrictions and nicotine concentration limits, must be followed. I am not responsible for any criminal prosecution or other legal proceedings initiated in connection with the possession or use of this spreadsheet.
______________________________
*DIY E-Juice Master Spreadsheet for MacOS, version 1.0.3 (May 24th, 2020). Licensed under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 (CC BY-NC-SA 4.0) license. (c) 2020 by Justin L. Franks (justin.franks@gmail.com)*

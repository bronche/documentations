Changelog
=========


=====

- Bugfix
- 


=====

- 
- 
- Bugfix
- Updating the doc


=====

- Improvement of the expression tester
- Updating the repository on smart
- Bugfix

4.0.44
=====

- Improved translations (yes again).
- Bugfix.
- Improvement of backup cloud restoration.
- The cloud restoration only repatriates the local backup now leaving you the choice to download or restore it.

4.0.43
=====

- Improved translations.
- Bug fixes on scenario templates.

4.0.0
=====
- Complete redesign of themes (Core 2019 Light / Dark / Legacy).
- Possibility to change the theme automatically according to the time.
- In mobile, the theme can change depending on the brightness (Requires activating * generic extra sensor * in chrome, chrome page:// flags). <br/><br/>
- Improvement and reorganization of the main menu.
- Plugins menu : The list of categories and plugins is now sorted alphabetically.
- Tools menu : Addition of a button to access the expression tester.
- Tools menu : Addition of a button to access the variables. <br/><br/>
- Search fields now support accents.
- The search fields (dashboard, scenarios, objects, widgets, interactions, plugins) are now active when the page is opened, allowing you to type a search directly.
- Add an X button on the search fields to cancel the search.
- During a search, the * escape * key cancels the search.
- Dashboard : In edit mode, the search field and its buttons are disabled and become fixed.
- Dashboard : In edit mode, a click on an * expand * button to the right of the objects resizes the tiles of the object to the height of the highest. Ctrl + click reduces them to the height of the lowest.
- Dashboard : Order execution on a tile is now indicated by the * refresh button*. If there is none on the tile, it will appear during execution.
- Dashboard : The tiles indicate an info command (history, which will open the History window) or action on hover.
- Dashboard : The history window now allows you to open this history in Analysis / History.
- Dashboard : History window retains its position / dimensions when another history reopens.
- Command D'actualité window: Ctrl + click on &quot;Save&quot; closes the window after.
- Equipment D'actualité window: Ctrl + click on &quot;Save&quot; closes the window after.
- Adding usage information when deleting equipment.
- Objects : Added option to use custom colors.
- Objects : Add context menu on tabs (quick object change).
- Interactions : Add context menu on tabs (quick interaction change).
- Plugins : Add context menu on tabs (quick change of equipment).
- Plugins : On the Plugins management page, an orange dot indicates non-stable plugins.
- Table improvements with filter and sort option.
- Ability to assign an icon to an interaction.
- Each Jeedom page now has a title in the interface language (browser tab).
- Prevention of auto-filling on fields&#39; Access code'.
- Management of functions * Previous page / Next page * of the browser. <br/><br/>
- Widget : Redesign of the widget system (Tools / Widget menu).
- Widget : Ability to replace a widget with another on all commands using it.
- Widget : Ability to assign a widget to multiple commands.
- Widget : Add horizontal info numeric widget.
- Widget : Adding an info numeric vertical widget.
- Widget : Addition of an info numeric compass / wind widget (thanks @thanaus).
- Widget : Adding an info numeric rain widget (thanks @thanaus)
- Widget : Display of the info / action shutter widget proportional to the value. <br/><br/>
- D'actualité : Improvement and reorganization of tabs.
- D'actualité : Added many * tooltips * (help).
- D'actualité : Adding a search engine.
- D'actualité : Adding a button to empty the widget cache (Cache tab).
- D'actualité : Added option to disable widget cache (Cache tab).
- D'actualité : Ability to center the content of the tiles vertically (Interface tab).
- D'actualité : Addition of a parameter for the global purging of the histories (Tab Commands).
- D'actualité : Change from # message # to # subject # in D'actualité / Logs / Messages to avoid duplication of the message.
- D'actualité : Possibility in the summaries to add an exclusion of the orders which have not been updated for more than XX minutes (example for the calculation of the temperature averages if a sensor has not raised anything for more than 30min it will be excluded from the calculation ) <br/><br/>
- Scenario : The colorization of the blocks is no longer random, but by type of block.
- Scenario : Possibility by Ctrl + click on the button * execution * to save it, launch it, and display the log (if the log level is not on * None *).
- Scenario : Block deletion confirmation. Ctrl + click to avoid confirmation.
- Scenario : Addition of a search function in the Code blocks. Search : Ctrl + F then Enter, Next result : Ctrl + G, Previous result : Ctrl + Shift + G
- Scenario : Ability to condense blocks.
- Scenario : The &#39;Add block&#39; action switches to the Scenario tab if necessary.
- Scenario : New block copy / paste functions. Ctrl + click to cut / replace.
- Scenario : A new block is no longer added at the end of the scenario, but after the block where you were before clicking, determined by the last field in which you clicked.
- Scenario : Implementation of an Undo / Redo system (Ctrl + Shift + Z / Ctrl + Shift + Y).
- Scenario : Delete scenario sharing.
- Scenario : Improvement of the scenario templates management window. <br/><br/>
- Analysis / Equipment : Addition of a search engine (Batteries tab, search on names and parents).
- Analysis / Equipment : The calendar / days area of the equipment is now clickable to directly access the change of battery (s).
- Analysis / Equipment : Addition of a search field. <br/><br/>
- Update Center : Warning on the &#39;Core and plugins&#39; and / or &#39;Others&#39; tab if an update is available. Switch to &#39;Others&#39; if necessary.
- Update Center : differentiation by version (stable, beta, ...).
- Update Center : addition of a progress bar during the update. <br/><br/>
- Home automation summary : The deletion history is now available in a tab (Summary - History).
- Home automation summary : Complete overhaul, possibility of ordering objects, equipment, orders.
- Home automation summary : Addition of equipment and order IDs, in display and in search.
- Home automation summary : CSV export of parent object, id, equipment and their id, command.
- Home automation summary : Possibility of making visible or not one or more orders. <br/><br/>
- Design : Ability to specify the order (position) of * Designs * and * 3D Designs * (Edit, Configure Design).
- Design : Addition of a custom CSS field on the elements of * design*.
- Design : Displacement of display options in Design of the advanced configuration, in the display settings from * Design*. This in order to simplify the interface, and allow to have different parameters by * Design*.
- Design : Moving and resizing components on * Design * takes their size into account, with or without magnetization. <br/><br/>
- General reduction (css / inline styles, refactoring, etc.) and performance improvements.
- Remove Font Awesome 4 to keep only Font Awesome 5.
- Libs update : jquery 3.4.1, CodeMiror 5.46.0, tablesorter 2.31.1.
- Numerous bug fixes.
- Adding a mass configuration system (used on the Equipment page to configure Communications Alerts on them)

>**Important**
>
>If after the update you have an error on the dashboard try to restart your box so that it takes the new additions of components into account

>**Important**
>
>The widget plugin is not compatible with this version of Jeedom and will no longer be supported (because the functions have been taken over internally on the core). More information [here] (https://www.jeedom.com/blog/4368-les-widgets-en-v4)

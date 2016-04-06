# reviewer_hide_toolbar.py

## Hide Toolbar in Reviewer

**Hides the main window's toolbar when reviewing.**

The aim of the addon is to free up some vertical screen space while reviewing
cards. For me this is useful as I have many cards that contain diagrams which can
be fairly large. In addition. modern wide screen displays seem to feel more
cramped vertically than horizontally.

The toolbar is made visible again when viewing decks and the overview.

The commands that are usually found on the toolbar are added to a new
main window "Toolbar" menu. Shortcut keys should continue to function.

**Changes**

2016-04-03: use internationalization for toolbar items (thanks to comment below)

**Credits**

Reupload of reviewer_hide_toolbar.

Copyright: Steve AW ([https://github.com/steveaw/anki_addons](https://github.com/steveaw/anki_addons))
License: GNU GPL, version 3 or later; [http://www.gnu.org/copyleft/gpl.html](http://www.gnu.org/copyleft/gpl.html)

Support: None. Use at your own risk.

Uploaded by Glutanimate ([https://github.com/Glutanimate/anki-addons-misc1](https://github.com/Glutanimate/anki-addons-misc1))

# main_deck_tooltip.py

## Deck Overview Stats Tooltip

**Shows a tooltip on the main window deck browser page**

Hover over your decks to see an overview of review stats and other information on the deck.

**Screenshot**

![](https://raw.githubusercontent.com/Glutanimate/anki-addons-misc1/master/screenshots/main_deck_tooltip.png)

**Credits**

Copyright: Steve AW ([https://github.com/steveaw/anki_addons](https://github.com/steveaw/anki_addons))
License: GNU GPL, version 3 or later; http://www.gnu.org/copyleft/gpl.html

Support: None. Use at your own risk.

Makes use of MiniTip (Dual licensed under the MIT and GPL licenses)
http://goldfirestudios.com/blog/81/miniTip-jQuery-Plugin
https://github.com/goldfire/minitip

Modified und reuploaded by Glutanimate, 2016 
([https://github.com/Glutanimate/anki-addons-misc1](https://github.com/Glutanimate/anki-addons-misc1))

# browser_open_added_today.py

## Open 'Added Today' from Reviewer

**Overview**

Adds a menu item into the "History" menu of the "Add" notes dialog that opens a Browser on the 'Added Today' view with the cards ordered by their creation time.

**Credits**

Copyright: Steve AW ([https://github.com/steveaw/anki_addons](https://github.com/steveaw/anki_addons))
License: GNU GPL, version 3 or later; http://www.gnu.org/copyleft/gpl.html

Support: None. Use at your own risk.

Modified und reuploaded by Glutanimate, 2016 
([https://github.com/Glutanimate/anki-addons-misc1](https://github.com/Glutanimate/anki-addons-misc1))

# browse_card_creation.py

## Browse Card Creation

**Browse Card in its Creation Context**

Adds commands to the Reviewer "More" menu and a hotkey (*C*) to open the browser on the selected card. The browser is configured to sort based on creation date, and select the card. Enables the card to be viewed in its  "creation context" ie notes that were created before/after in the same deck.

**Credits**

Copyright: Steve AW ([https://github.com/steveaw/anki_addons](https://github.com/steveaw/anki_addons))
License: GNU GPL, version 3 or later; http://www.gnu.org/copyleft/gpl.html

Support: None. Use at your own risk.

Modified und reuploaded by Glutanimate, 2016 
([https://github.com/Glutanimate/anki-addons-misc1](https://github.com/Glutanimate/anki-addons-misc1))

# addcards_more_newcard_buttons.py

## More Answer Buttons for New Cards

**Overview**

Adds extra buttons to the Reviewer window for new cards.

**WARNING**: this addon uses custom methods to achieve its goals. Use at your own risk and keep backups.

**What it does**

Adds anywhere between 1 to 4 new buttons to the review window when reviewing a new card. The new buttons function like the exist Easy" button, but in addition, they reschedule the card to differ nterval, which is randomly assigned between a lower and upper limit that is preset by the user (see below).

By default 3 buttons are added, with intervals: "3-4d" , "5-7d" , "8-15d". This can be changed in the source code.

![screenshot](https://raw.githubusercontent.com/Glutanimate/anki-addons-misc1/master/screenshots/addcards_more_newcard_buttons.png)

I wanted this addon because many of my new cards do not need to be "Learned" as I created and added them myself, typically an hour or so before my first review session. I often add around 100-200 new cards per day, all on a related topic, and this addon allows me to spread the next review of the new cards that don't need learning out in time.

**How it works**

This addon works by intercepting the creation of the reviewer buttons and adds up to 4 extra buttons to the review window. The answer function is wrapped and the ease parameter is checked to see if it one of the new buttons. If it is, the standard answer function is used to add the card as an easy card, and then the browser 'reschedCards' function is used to reschedule it to the desired interval.

In summary, this functions as if you click the "Easy" button on a new card, and then go to the browser and reschedule the card.

**Warning**

- This completely replaces the Reviewer._answerButtons function, so any changes to that function in future updates will be lost.
- buyer beware ... The author is not a python, nor a qt programmer

**Configuration**

Open the add-on in a text editor of your choice and find the `extra_buttons` section below the header. This is a list of dicts, where each item of the list (a dict) is the data for a new button. This can be edited to suit, but **there can not be more than 4 buttons**. Values:

- Description ... appears above the button
- Label ... the label of the button
- ShortCut ... the shortcut key for the button
- ReschedMin ... same as the lower number in the Browser's "Edit/Reschedule" command
- ReschedMax ... same as the higher number in the Browser's "Edit/Reschedule" command

**Credits**

Copyright: Steve AW ([https://github.com/steveaw/anki_addons](https://github.com/steveaw/anki_addons))
License: GNU GPL, version 3 or later; http://www.gnu.org/copyleft/gpl.html

Support: None. Use at your own risk.

Modified und reuploaded by Glutanimate, 2016 
([https://github.com/Glutanimate/anki-addons-misc1](https://github.com/Glutanimate/anki-addons-misc1))

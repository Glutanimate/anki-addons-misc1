## Overview

This is a personal fork of Steve AW's Anki add-ons. While most of these haven't been updated in years they are still functional and only need an adjustment or two before being ready to be reuploaded to AnkiWeb.

## Original README:

A selection of [Anki](http://ankisrs.net/) [addons](https://ankiweb.net/shared/addons/) in various stages of development.
They are not suitable for general use, and could easily damage your Anki installation/database etc.
For addons suitable for end users, please go to: https://ankiweb.net/shared/addons/

Update 25/7/2103:
===============
It is getting close to that time of the year when uni starts back up for me. So, it is unlikely that I will update these pages or addons much until the long holidays (Dec to Feb). Therefore it seems now would be a good idea to document a few things.

Note: while I won't be doing any addon development, during semester I spend a lot of time working with Anki, 3-4 hours a day of reviewing and often 2-3 hours of card creating ... so I will be making heavy use of Anki and most of these addons.

### Addons that have been uploaded to Ankiweb in the past as shared/public addons are:

- addcards_more_newcard_buttons.py [Add more review answer buttons for new cards] (https://ankiweb.net/shared/info/468253198)
- addcards_quick_change_notes.py [Quick change Note buttons](https://ankiweb.net/shared/info/1720844055)
- browse_card_creation.py [Browse card creation] (https://ankiweb.net/shared/info/3466942638)
- browser_open_added_today.py [Open Browser from the Add Window History menu] (https://ankiweb.net/shared/info/4168112055)
- export_cards_to_csv.py [Export Browser's card list contents to CSV file](https://ankiweb.net/shared/info/1822267896)
- overview_forecast_graph.py [Forecast graph on Overview page](https://ankiweb.net/shared/info/4219926982)
- main_deck_tooltip.py [Deck window tooltip showing additional information] (https://ankiweb.net/shared/info/1819828168)
- reviewer_hide_toolbar.py [Hide toolbar while reviewing](https://ankiweb.net/shared/info/2244807260)
- reviewer_search_google.py [Search Google for selected text in Reviewer] (https://ankiweb.net/shared/info/798922495)
- reviewer_show_cardinfo.py

### The following are not suitable for addons.
 I actually uploaded some of these by mistake originally as I figured out pycharm's git integration :) However, if Anki had an "advanced options/settings" api+ui (say like firefox), then these kinds of addons could be shared in the future

- browser_ui_tweaks.py  ... change minor things in the browser.
- main_ui_tweaks.py ... ditto
- reviewer_ui_tweaks.py
- main_dont_delete_media.py ... Instead of deleting unused media (or sending it to the recycle bin), it moves the unused files to a "unused" folder. I think this is a safer option.


### The following are not ready (and may never be ready) for general public use.

Either they are too specific to my workflow, too hard to explain, or could lead to too many support emails :)

- **simple_picocc** ... This is a derivative of Tiago's (tmbb) image occlusion 2 addons. All thanks and credit to Tiago. I use image occlusion a lot for my card creation. I started work on this when it appeared the original addon was not maintained. Since then, Tiago has released a new version, so it is not necessary to release this. However, I did end up rewriting the whole addon and taking a fairly different approach to the original. This addon is far less flexible than the original, and rather than being designed to stand alone as a card creation window, it works as a modal dialog to the editor window, and makes use of that to obtain the note's deck/tags etc. The benefit of sacrificing the power and flexibility of the original is that the implementation is fairly simple, and the code comes out very cleanly (it just involves a bit of xml manipulation).
- **browser_duplicate_note.py** ... This creates a duplicate note (same content, with created timestamp just after the target note). This allows a single note to be effectively split into two, and appear in the browser next to (when sorting on creation date) the original. At this stage I don't copy across the card state, but I have other tools to do that. I will use it this semester and see how it goes.
- **browser_tag_all_suspended.py** ... I use "suspend card" as a delete function. It means that I don't have to worry if I am deleting a note that has other cards (this is actually how I think "Delete" should work in Anki). So the suspended card list serves as a kind of recycle bin for me. This addon searches through all notes to find notes which have all of their cards suspended, and then adds a tag "AllSuspended" to those notes. I can then use that tag to delete (actually delete) those notes.
- **editor_commands.py** ... this is a hodge-podge of editor commands (44 at last count!) that do various things in the editor such as: insert special (maths/stats) characters, reformat text into lists, add/remove clozes automatically, clean up text pasted in from pdfs, add references from html pastes, and also for info pasted in from my pdf viewer (the pdfx* methods), plus anything else I can think of to help create cards! A lot of this won't make sense. many of commands work hand in hand with autohotkey scripts I have setup, along with my pdf viewer. The pdfx* methods allow me to select some text in a pdf, press Win-V, and have that text copied, "cleaned" and placed into the Anki Add window along with a link back to the pdf (with page bookmark) and a screenshot of that pdf slide also inserted into another field. It works really well for me, but something like that is obviously highly personalized to my workflow.
- **editor_store_note_field_state.py** ... This contains two classes and their singletons that maintain a history of editor state. I used the first (NoteFieldEditState) heavily last semester, the other (NoteFieldPreClozeHistory) is new. The first is like a "Sticky field" except that the content it copies into the new card is the content in that field before any clozes were made. This allowed me to make some clozes, add the card, but get the original content back (without the cloze markup). Useful, but I have another command that cleans out a field of any cloze markup, so not as useful to me as it first was. The second is new. It will maintain a history list of field content state prior to any pastes/clozes or other changes (but not typing), and then allow those changes to be cycled through via undo/redo pattern. I will find out how this goes during semester.
- **reviewer_daily_rev_chart.py** ... I love this, but it is a bit buggy and the code is still very messy, and at this stage too hard coded to my personal workflow. It shows a bar chart along the bottom of the reviewer window. The x-axis is time (from 6AM to 6PM) and y-axis is # of reviews in each 2 minute interval. I use it to help motivate me to keep breaks between  reviewing sessions short. I can have up to 3-4 hours of reviewing a day towards the end of semester, and I try to concentrate and review for 7 minutes, and then have a minute of so break. Sometimes that minute can became 15 minutes :) While the y-axis scale is fixed, as I am not interesting in speeding up my reviewing rate, the chart starts plotting red "bars" after about 1 minute has passed with no reviews. I am hoping that this can cut down the total time I spend reviewing by keeping me concentrating on the task at hand, and stopping the mini breaks from dragging out. So far I really like it, and I hope it will help to keep my slogging through the review card during the coming semester. If I still like it, I will do the extra work latter in the year and release it as a public addon. A picture is worth 1000 words:
![Imgur](http://i.imgur.com/T8ZZOxr.png)
- **reviewer_track_unseen.py** ... I am using this in conjunction with cramming. It uses tags (nsN,ns1,ns2,nsX where X is the card's ordinal number) to identify a set of cards, and then as the cards are viewed, it automatically removes that card's tag from its note. The idea behind it is: Say I have an exam in a week. My goal is to review all my cards that relate to the exam over the coming week, doing bits and pieces wherever I can. In reality, I often don't get the time to do all of them, but if each day I can do a random smattering of 50-100 extra cards, that is generally good enough. I never found a good way, with the inbuilt cramming/study more tools, to reliably keep track of what cards had been crammed when cramming across multiple sessions (the changed field/ "Last reviewed" gets updated when cards are added to dynamic decks which makes it useless for my needs). This addon allows me to add the tags to those cards I want to see. I can then create dynamic decks for those tags (tag:ns*), and the tags only get removed from cards that are seen. It gives me confidence that I am not re-cramming a card, and also allows me to see how many are still "unseen". I will see how it goes this semester, but I think it is going to finally give me a good way to systematically cram.



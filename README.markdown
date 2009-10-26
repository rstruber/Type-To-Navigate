Type-to-Navigate
================

Overview
--------

Type-to-Navigate is an extension for Google Chrome / Chromium. It enables a type-to-select feature, whereupon you can select links (or any word, really) just by typing. Hitting return key follows any link in which there is a selection.

Installation
------------
1. Download [type_to_navigate.crx](http://github.com/dbergey/type_to_navigate_chrome/raw/master/type_to_navigate.crx).
2. Drag it into a Chrome / Chromium window.
3. Click all ensuing confirmation buttons.

Chrome / Chromium will automatically update Type-to-Navigate when there is a new version, so there should be continual improvements to websites that do quirky things with their fields (HELLO FACEBOOK).

Interesting Development Notes
-----------------------------

One hurdle was keeping this script from doing its magic when the user actually wanted to type in a field. An earlier version of this script used onBlur/onFocus events to add a class to every field while editing, but this broke down for sites with a preselected field, like, say, Google, since there was no chance for the script to apply the onFocus in time. I eventually found a way to use the cursor: CSS property to detect what field has focus.

I ran into another problem with editable areas that are not really fields. Facebook in particular was an offender. I think I've found a way to handle Facebook's "fields", but there may be others.

Sites With Remaining Quirks
---------------------------

- MSNBC -- nothing is selected when the user types
- GitHub -- some letters don't register, like 's', which triggers focus on the search field, and 't', which does something unspecified.
- Google search results -- Search for 'chrome' and then type 'chrome'. The search field becomes selected round about the letter R.

Future Plans
------------

- Add user-configurable website blacklist. Might be good to upload this data somewhere transparently, so as to gather data on what sites don't work and which most annoy so.
- Display keypresses and the current search string somehow.
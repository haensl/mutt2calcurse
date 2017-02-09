# mutt2calcurse
Export events from mutt to calcurse


mutt2calcurse is a fork of [Tim Hentenaar](https://github.com/thentenaar)'s 
[add_to_calcurse.sh](https://gist.github.com/thentenaar/2dd7d47a17f6527652dc#file-add_to_calcurse-sh) and is used to import `text/calendar` files into calcurse.

## Usage
This script was written in order to export iCal events from mutt to calcurse. In order to use it as such add the following to your `muttrc`:

```bash
macro index,pager \ck <pipe-entry>'mutt2calcurse'<enter> 'Add ical events to calcurse'
```

This line sets up a _macro_ on the _index_ and _pager_ views enabling the user to press `ctrl+k` when viewing an iCal event to send it to calcurse.

## Dependencies
uudeview



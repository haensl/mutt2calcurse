#!/usr/bin/env bash
#
# Import text/calendar files from mutt to calcurse
#

function addToCalcurse() {
  # Extract attachments
  local tmpDir=$(mktemp -d add-to-calcurse.XXXXXXXX)
  cat "$@" | uudeview -i -m -n -q -p $tmpDir - > /dev/null 2>&1

  # Add calendar file to calcurse
  local calFile=$(ls $tmpDir | sort -r | head -1)
  calcurse -i "$tmpDir/$calFile" > /dev/null 2>&1

  # Remove tmpDir and trigger a reload in calcurse
  rm -rf $tmpDir > /dev/null 2>&1
  # Check if calcurse is running
  if [ -f "$HOME/.calcurse/.calcurse.pid" ]; then
    kill -USR1 `cat $HOME/.calcurse/.calcurse.pid` > /dev/null 2>&1
  fi
}

addToCalcurse

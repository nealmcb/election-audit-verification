class: center, middle

### MyTitles

Neal McBurnett

2023-03-16

[Remarkjs documentation](https://remark.js.org/)

???
Slide notes here

See also README.md

Quickstart:

fn=corla-evn2023  # Adjust to current directory name == slug

To display, run `view-presentation`
To make QR code:
  echo https://bcn.boulder.co.us/~neal/talks/$fn
  test it
  qr-code-generator  # enter URL command line when prompted
  add ![QR Code](qr_code.png)

To make pdf, run: OPENSSL_CONF=/dev/null decktape http://localhost:8000/#1  $fn.pdf
To publish, run: rsync -av --exclude '.git' --exclude 'neal-ignore' ../$fn bcn:public_html/elections
To visit: google-chrome https://bcn.boulder.co.us/~neal/elections/$fn

First, change the MyTitles including <meta property... in the index.html

Use '?' hotkey for documentation

Modify the slides.md and reload browser page

---
## Neal McBurnett
* Consultant on Big Data, Election Integrity, Voting Methods
* Computer Scientist, Ex-Bell Labs
* Working on election audits and integrity since 2003
* Poll worker
* Pioneered RLAs for Boulder (2010) and Colorado's current state-wide audit
* Verified Voting Board member
* Colorado Bipartisan Election Advisory Commission member
* Speaking for myself

---
## Introduction
* Bullets...

---
## Image scaling
Untouched image overflows to the right
![Example Image](image.png)

---
## Show scaled image via HTML img tag width="750"

<img src="image.png" width="750">

Perhaps works up to width=800?

Also works:

`convert orig.png -resize 50% smaller.png`

???

---
## TODO
Tried Scaled to 50 px, from some github issue comment, but this (with leading "!") doesn't work - just get a blank screen...

[:scale 50px](image.png)

Perhaps I need to install a plugin or something?

How to change font size?

How to add a QR code to link to the online version?

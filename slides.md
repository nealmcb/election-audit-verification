class: center, middle

### Election Audit Verification

Neal McBurnett, Lori Stevens, Mike Raisch

2026-03-31

???
Slide notes here

See also README.md

Quickstart:

fn=election-audit-verification   # Adjust to current directory name == slug

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
# Election Audit Verification

- Goal
  - Enable canvass board members and the public to independently validate the tabulation of an election
  - Evidence-Based Elections
  - Software independence of and transparency of audit, rather than relying on hosted ColoradoRLA software
- What problem does this solve?
  - No public commitment to CVR before the random seed selection.
  - Parts of the RLA are opaque to canvass boards and the public.
  - Canvass board members are unable to do their own validation of the correct tabulation of ballots.

---
# Approach

- Two main verification processes will be available:
  - Canvass board members and the public will be able to attend an RLA and verify that the contest choices on audited ballots match the record of how those ballots were interpreted.
  - The public will be able to verify other aspects of the election, such as vote tabulation, based on public data.

---
# On-Premises Verification of Ballot Interpretations

- Public election verifiers at an RLA will be able to:
  - Listen to an audit board read how contests were voted on audited ballots.
  - Compare those votes to how the CVR file reports that the contests were voted.
  - Conveniently note any seeming discrepancies.
  - They must not interrupt the work of the audit board.
- The data in the CVR file will be made accessible by one or more tools (already prototyped) which will either print or display the votes of each audited ballot.
  - Observers can compare results after the RLA is complete.

---
# Targeted Ballot Comparison

- Even simpler, more direct, more transparent audit.
- Allows for a bit more verification responding to specific contests or ballots of public interest.
- Public election verifiers will also be able to:
  - Select additional paper ballots (probably ten or fewer) to be compared to their CVR entries.
    - The additional ballots can be chosen by combining possible values of tabulator, batch, and ballot number, or
    - They can be chosen directly from the ballot boxes by a county election staff member or an election judge based on a request from the public election verifier (“Pull the 10th ballot from the 3rd batch in that box there.”).
    - Election judges from the available audit teams will read how the ballot was voted so that the verifier can compare the choices to the ballot’s CVR entry.

---
# Other Election Verification Actions

- Based on public data, using an open-source application of their choice, the public can:
  - Verify that when the votes in the redacted CVR file are counted, the vote totals are the same as the reported contest results.
  - Verify that the CVR file being used is identical to the redacted CVR file that was produced before the selection of the random seed.
  - Verify that the ballots that were selected to be audited are the ballots that would have been chosen by the RLA software given the random seed.

---
# Data To Be Provided by the County

The data needed from the county in order to perform these verification tasks are:

- Before the random selection:
  - The manifest and its hash (as already available in the AuditCenter)
  - Generate the redacted cast vote record, publish the hash
  - A tool for redacting CVR files has been prototyped and will be provided.

- Before the work of the audit boards:
  - The list of ballot sheets to be audited, preferably associated with the audit board that will be reading out those ballots.
  - The summary contest results file

???
## Image scaling
Untouched image overflows to the right
![Example Image](image.png)

???
## Show scaled image via HTML img tag width="750"

<img src="image.png" width="750">

Perhaps works up to width=800?

Also works:

`convert orig.png -resize 50% smaller.png`

???

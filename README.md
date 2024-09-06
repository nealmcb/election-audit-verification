# Quickstart
1. Edit content into `slides.md`.  See [the remark.js wiki](https://github.com/gnab/remark/wiki/Markdown) for help setting up your slides
2. Customize any css in `slides.css`
3. Serve your presentation over HTTP using one of the following methods (or others)
    1. Commit your presentation to the `gh-pages` branch of a Git repository and push it to GitHub
    2. Serve the presentation from your local harddrive with Python, using either `python -m SimpleHTTPServer` or `python3 -m http.server`
	  1. The `./view-presentation` script will do this
4. For QR code: echo https://bcn.boulder.co.us/~neal/elections/$fn and run qr-code-generator 
   then add Presentation, with links online at ...
   ![QR Code](qr_code.png)

5. To make pdf, run:  OPENSSL_CONF=/dev/null decktape http://localhost:8000/#1  $fn.pdf
6. To publish, run: rsync -av --exclude '.git' --exclude 'neal-ignore' ../$fn bcn:public_html/elections
7. View online via  google-chrome https://bcn.boulder.co.us/~neal/elections/$fn
8. Enjoy the applause after presenting your amazing talk

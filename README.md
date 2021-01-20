# Apostrophe 3 demo and test project

## Instructions - nunjucks helpers not available inside of a macro

1. Be sure you have running mongodb on default port. Database `a3-helpers` will be auto-created.
1. Run the project in dev mode (see below). Ignore warnings, no need of user/session secret.
2. You should see home page rendered with additional `Helper Test` section.
3. Open `modules/@apostrophecms/home-page/views/page.html` and uncoment around line 23 `<p>{{ helper.render("Same helper called from inside of a macro will fail") }}</p>`
4. You should see error page, look at the CLI output.

Changes made to the original a3 boilerprate to reproduce the issue:
- added `helper.include.html`, `helper.macro.html`, `plain.macro.html` in `modules/@apostrophecms/home-page/views/`
- modified `modules/@apostrophecms/home-page/views/page.html` to include the macros and render additional section reproducing the issue in question
- `app.js` - shortName renamed to `a3-helpers`
- `package.json`: removed build from `npm run dev` command, added `postinstall` for initial build and better startup time

## Get started

Install dependencies: `npm install`

## Running the project

Run `npm run dev` to build the Apostrophe UI and start the site up. Remember, this is during alpha development, so we're all in "dev mode."

## You really want the docs

Right now, [all the juicy info about A3 is in the a3 docs](https://a3.docs.apostrophecms.org), so head over there and start reading! This boilerplate project is a fun introduction to the UI, but you'll want to know more to really try it out.


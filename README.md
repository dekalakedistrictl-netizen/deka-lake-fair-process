# Deka Lake mailto campaign page

This package is a static GitHub Pages site for a Deka Lake / Interlakes email campaign.

It does not use a backend, database, tracker, form processor, or third-party service. The page prepares a `mailto:` email on the visitor's own device. The visitor must review and send the email from their own email app.

## Included files

- `index.html` — the full campaign page, including styling, email copy, recipient list, mailto generator, and copy-to-clipboard tools.
- `campaign-copy.md` — campaign text in plain Markdown for easy editing or reuse.
- `social-share-copy.md` — short social posts for Facebook, community groups, or text messages.
- `README.md` — setup instructions.

## Current recipients

To:

- Lorne.Doerkson.MLA@leg.bc.ca
- planning@cariboord.ca

CC:

- edevries@cariboord.ca
- nwhitehead@cariboord.ca
- ajohnston@cariboord.ca
- mdaly@cariboord.ca

## How to publish on GitHub Pages

1. Create a new GitHub repository.
2. Upload all files from this folder into the root of the repository.
3. Go to **Settings** → **Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Choose the `main` branch and `/root` folder.
6. Save.
7. GitHub will publish the page at a URL similar to:

   `https://YOUR-USERNAME.github.io/YOUR-REPOSITORY-NAME/`

## How to edit the recipients or email copy

Open `index.html` and search for these constants near the bottom of the file:

```js
const TO = [
  "Lorne.Doerkson.MLA@leg.bc.ca",
  "planning@cariboord.ca"
];

const CC = [
  "edevries@cariboord.ca",
  "nwhitehead@cariboord.ca",
  "ajohnston@cariboord.ca",
  "mdaly@cariboord.ca"
];

const SUBJECT = "Deka Lake needs fair rules before enforcement escalates";
```

The default messages are controlled by:

```js
const standardTemplate = ({ name, connection, note }) => `...`;
const fullTemplate = ({ name, connection, note }) => `...`;
```

## Mailto limitations

A `mailto:` link cannot send email automatically. It only opens the visitor's default email app with a prepared message.

Some browsers and email apps have trouble with long `mailto:` links. This page includes a copy-to-clipboard fallback so visitors can manually copy the recipients and message into their email account.

For the fewest technical issues, keep the default message reasonably short and encourage supporters to add one or two personal sentences.

## Suggested deployment check

After publishing, test the page on:

- a desktop browser with Outlook or Apple Mail;
- Gmail in a browser;
- a mobile phone.

Confirm that:

- the email opens with the correct To and CC recipients;
- the subject line appears correctly;
- the message body is readable;
- copy-to-clipboard buttons work;
- the page looks acceptable on mobile.

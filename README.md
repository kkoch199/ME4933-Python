# NFC Digital Business Card

A "dot."-style smart business card. An NFC tag stores the URL of a hosted profile
page — someone taps the tag with their phone, the page opens, and they hit
**Save to Contacts**. No app required on their end.

There are two pieces:

1. **The page** (`index.html`) — your card, driven by one config block.
2. **The tag** — a cheap NFC sticker/card you write your page URL onto.

---

## 1. Put in your details

Open **`index.html`** and edit the `CONTACT = { ... }` block near the bottom
(it's clearly marked). That single block drives the whole page. Leave any field
as `""` and it disappears automatically.

Then update **`contact.vcf`** with the same info (this is the file that iPhones
open straight into the Contacts app when someone taps **Save to Contacts**).

Optional: drop a headshot named **`profile.jpg`** in this folder and set
`photo: "profile.jpg"`. Without one, the page shows a clean monogram of your
initials.

---

## 2. Publish the page (free, via GitHub Pages)

1. Push this repo to GitHub (see below — already done if Claude pushed it).
2. On GitHub: **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Pick branch **`main`** (or whichever branch holds these files) and folder
   **`/ (root)`**, then **Save**.
5. Wait ~1 minute. Your card goes live at:

   ```
   https://kkoch199.github.io/me4933-python/
   ```

   Open it on your phone to confirm it looks right and **Save to Contacts** works.

> Want a shorter/branded URL later (e.g. `card.yourname.com`)? You can point a
> custom domain at GitHub Pages in the same settings screen.

---

## 3. Write the URL to an NFC tag

**You need:** an NFC tag (NTAG213/215/216 stickers or cards — a few dollars on
Amazon) and a free writer app.

**iPhone (built in):**
1. Open the **Shortcuts** app → **Automation** isn't needed; instead use a
   writer app, OR use **NFC Tools** (free, App Store).
2. In **NFC Tools**: **Write → Add a record → URL/URI** → paste your Pages URL.
3. Tap **Write**, then hold the tag to the top of your iPhone until it confirms.

**Android:**
1. Install **NFC Tools** (free, Play Store).
2. **Write → Add a record → URL/URI** → paste your Pages URL → **Write**.
3. Hold the tag to the back of your phone until it confirms.

That's it. Test it: tap the tag with any modern phone — the card should pop up.

> **Tip:** After writing, use the app's **Lock** feature only if you're sure —
> locking a tag is permanent and prevents re-writing.

---

## Sharing without a tag

- **QR code:** generate a QR that encodes the same Pages URL (any free QR site)
  and print it on your paper card or slides — scanning it opens the same page.
- **Text/AirDrop:** just send the URL.

---

## Files

| File | What it is |
|------|-----------|
| `index.html` | The business card page. Edit the `CONTACT` block. |
| `contact.vcf` | The saved-contact file iPhones open on "Save to Contacts". Keep it in sync with your details. |
| `profile.jpg` | *(optional)* your headshot. |

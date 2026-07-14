# NFC Contact Card

Two files, no build step:

- `index.html` — the page the NFC tag points to. Auto-redirects to `contact.vcf` on iPhone; shows a fallback business-card page with a "Save Contact" button everywhere else.
- `contact.vcf` — your actual contact info, in vCard format.

## 1. Edit your info

Open `contact.vcf` and replace the placeholder values (name, phone, email, org, etc.) with your real info. Every line is a standard vCard field — just edit the text after each colon.

Open `index.html` and edit the sections marked `EDIT ME` in comments:
- the `<title>` tag
- the avatar initials ("FL")
- name, job title, company
- phone / email / website (remember to update both the `href="..."` and the visible text on each line)

Keep the two files' info in sync (same name/phone/email in both places).

## 2. Host on GitHub Pages

1. Create a new GitHub repo (e.g. `contact-card`).
2. Upload `index.html` and `contact.vcf` to the repo root.
3. Go to Settings → Pages → set Source to your main branch, root folder.
4. Your live URL will be: `https://yourusername.github.io/contact-card/`

## 3. Write the URL to your NFC tag

Use an NFC-writing app (e.g. **NFC Tools** on iOS/Android):
1. Add a record → type **URL/URI**.
2. Enter your GitHub Pages URL from step 2.
3. Write to your NFC card.

That's it — tapping the card opens the URL in the phone's browser, which handles the rest.

## How it behaves

- **iPhone**: Safari opens → JS instantly redirects to `contact.vcf` → iOS shows the native "Add Contact" preview → user taps "Add Contact" to save.
- **Android / desktop / anything else**: lands on the styled card page and taps "Save Contact" to download the vCard.

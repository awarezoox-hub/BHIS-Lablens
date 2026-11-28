# Selling LabLens by BHIS: step-by-step

## How the selling works
1. People open your app link and get **free trial interpretations** (you choose how many; default 3).
2. When the trial ends, the app asks for an **access code**, with buttons to pay you (Paystack/Flutterwave link) or message you on WhatsApp.
3. They pay. You make a code in the **BHIS Licence Generator** and send it to them.
4. They paste it into the app once. It then works **fully offline** until the licence date ends. After that the app asks for a renewal code.

Two types of code:
- **Personal**: for one person or family.
- **Business**: for clinics, labs and pharmacies. Their business name is printed on every report ("Prepared by …") and on copied summaries.

## Files you need (rename them exactly, no brackets or numbers)
| File | Where it goes |
|---|---|
| `index.html`, `sw.js` | GitHub (replace the old ones) |
| `licence-key.json` | GitHub (you create it in Step B below) |
| `licence-generator.html` | **Only on your laptop. Never upload it to GitHub.** |

## A. One-time setup (about 20 minutes, on your laptop)
1. **Update the app on GitHub:** upload the new `index.html` and `sw.js` (Add file → Upload files). Commit.
2. **Open `licence-generator.html`** by double-clicking it on your laptop (use Chrome).
3. **Step 1 in the tool, "Create my keys":** a backup file `BHIS-private-key-BACKUP.json` downloads. **Email it to yourself and save a copy on a USB stick.** If you lose it you cannot make new codes, and anyone who gets it can make free codes.
4. **Create your payment link** (see section C), then paste it and your WhatsApp number (with country code, e.g. 2348012345678) into Step 2 of the tool.
5. Click **Download licence-key.json** and upload that file to GitHub next to `index.html`.
6. Wait 2–3 minutes, open the app link, and refresh. A green banner "Free trial: 3 of 3 interpretations left" should appear. That means selling is switched on.

Until `licence-key.json` is on GitHub, the app stays free for everyone.

## B. Every time someone pays
1. Open `licence-generator.html` on your laptop.
2. Step 3: type the customer's name (or the business name), choose **Personal** or **Business**, choose how long (12 months is typical), click **Make access code**.
3. Click **Copy full message** and send it to the customer by WhatsApp or email.
4. The tool saves the sale in **Your sales log**. Download the CSV monthly as your record.

**Renewal:** make a new code for the next period and send it. They paste it into About → "Enter access code".

## C. Collecting money (Nigeria)
- **Paystack:** dashboard → Payment Pages (or "Payment Links") → create a page with a fixed amount, one for Personal and one for Business, or one page with a choice. Put the link into the generator.
- **Flutterwave:** dashboard → Payment Links → create a fixed-amount link.
- In the page description write: "LabLens by BHIS, 12-month licence. Your access code will be sent on WhatsApp or email within 24 hours." Collect the buyer's email and phone number.
- Check every payment in your dashboard before issuing a code.

## D. Pricing (starting suggestions, adjust to your market)
| Plan | Idea | Starting range |
|---|---|---|
| Personal, 12 months | Patients and families | ₦3,000–₦6,000 |
| Business, 12 months | One clinic, lab or pharmacy | ₦25,000–₦60,000 |
| Business plus support | Staff training session, your branding help | add ₦15,000+ |

Test two prices with your first 10 customers and keep the one that sells.

## E. Who to sell to first
- **Pharmacies and patent-medicine shops** (patients ask them to explain results).
- **Small clinics and diagnostic labs** (hand-out tool that explains results to patients, with their name on every report).
- **Women's and church health ministries** (group licences).
- **Health-conscious individuals** via WhatsApp status, Instagram and your ministry network.

## F. What to say and not say
Say: "Educational lab-result guide that explains your results and tells you which specialist to see."
Do **not** say: "diagnoses you", "replaces your doctor", or "100% accurate". Keep the disclaimers in the app.

## G. Legal and safety checklist (do before wide selling)
I am not a lawyer; please confirm these locally.
- [ ] A **licensed doctor or pharmacist reviews** the wording, ranges and urgency advice, and signs off. Since version 1.3, ask a **paediatrician** to check the newborn and child ranges and advice too. Since version 1.4, ask an **obstetrician/gynaecologist** to check the pregnancy ranges, baby-scan rules (dating, weight, fluid, cervix), diabetes-in-pregnancy and blood-pressure thresholds, hCG guidance, and the PCOS, cyst, fibroid and womb-lining advice.
- [ ] Check with **NAFDAC or a Nigerian lawyer** whether software that suggests possible conditions counts as a regulated medical device.
- [ ] Put **Terms of Use and a Privacy Notice** on a page and link them in your payment page. The app stores nothing off the device, which makes the privacy notice simple. Mention the Nigeria Data Protection Act (NDPA).
- [ ] State a **refund policy** (for example, no refunds after the code is activated).
- [ ] Consider **professional indemnity or product liability insurance** for health software.
- [ ] Keep a record of **version changes** if you correct clinical content.

## H. Honest limits of this protection
- Codes are cryptographically signed, so they **cannot be forged**, but a paying customer could share their code. Expiry limits the damage. Business codes show the business name on reports, which discourages sharing.
- Clearing the browser's data resets the free trial. It is a convenience limit, not a lock.
- Codes are made by hand. Later, a Paystack webhook can issue codes automatically; I can help set that up with Lovable and Supabase when you are ready.
- The licence date uses the phone's clock, and the app notices if the clock is set back.

## I. If something goes wrong
- **Customer says the code is not valid:** ask them to paste the whole code (it starts with `BHIS-` and has one dot in the middle). If it still fails, make a new one.
- **You lost your private key:** you can no longer make codes that match the app. Create new keys, upload the new `licence-key.json`, and reissue codes to existing customers.
- **App not asking for codes:** check that `licence-key.json` is in the same GitHub folder as `index.html`, then refresh.

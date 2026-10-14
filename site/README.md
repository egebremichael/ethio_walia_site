# Ethio Walia Soccer Club website

## Open the site

Double-click `index.html` in this folder. No installation or build step is required. All six pages, photos, navigation, forms and calendar downloads work locally. Google Fonts require an internet connection; system fonts are the fallback.

Optional web-server preview: from this folder run `python3 -m http.server 8000`, then open `http://localhost:8000`. A static host can serve this whole folder unchanged. Nothing has been published to the internet.

## Edit content

All club content is in `data/*.json`:

| File | Content |
|---|---|
| club.json | Club story, mission, values, contact, images, stats and Home action cards |
| youth.json | Planned youth program, details and FAQ |
| players.json | Adult squad overview, roster and staff |
| donate.json | Donation message, allocation, amount choices, currency and the single paymentUrl value |
| tryouts.json | Form options and unconfirmed tryout details |
| schedule.json | Upcoming/past events, dates, locations, type and home/away |
| gallery.json | All 33 photo records, captions, alt text, category and sizes |
| config.json | Routes, gallery labels and footer tagline |

On a web server, refresh after editing JSON. When opening by double-click, browsers prevent automatically reading adjacent JSON files. The site therefore ships with a complete JSON snapshot inside index.html. To apply your edited JSON without touching code: open **Content tools** in the footer, select one or more edited data JSON files, and close the dialog. Imported changes persist in that browser. Use **Reset imported content** to return to the packaged defaults or load fresh hosted JSON.

For a new portable package with updated defaults, replace the JSON text inside the `initial-data` script in index.html with an object containing the eight JSON files, keyed by filename without `.json`. This is optional; the import flow requires no code changes or build step. Imported content is browser-local and does not rewrite files or propagate to other devices. For shared updates, host the folder and edit the JSON files there.

Gallery filenames stay relative to this folder: `assets/images/filename.jpg`. Add an image file, then add a gallery record with unique id, src, caption, meaningful alt, category, width and height. Do not use unknown player identities as captions. `image-placement.csv` maps every supplied image to its filename and site placement.

## Schedule and calendars

The training plan is tentative: Tuesday, Thursday and Sunday, 5:30–7:30 p.m. Toronto time, outside winter. Location: Regent Park Athletic Grounds, 480 Shuter Street, Toronto, Ontario, Canada. Map links use the location supplied by the owner. Contact the club before attending.

Weekly training cards have a weekday rather than an invented calendar date. Dated events can still be added to schedule.json with a unique id, title, type, ISO start/end values with timezone offsets, and location. Dated events retain month grouping, Upcoming/Past views, .ics downloads and the Home countdown. Weekly cards provide map links. No winter dates are generated.

## Forms and privacy

Donation forms record pledges only. No money is collected; Monthly does not create a recurring payment. The one payment URL lives in `data/donate.json`. If populated, a separate link appears; the pledge handler still never charges a payment.

Tryout and pledge submissions are stored only in the browser's localStorage. They are not transmitted to the club. After signup, an optional **Share by email** link opens a prefilled draft for the visitor to review and send. Team signups accept players aged 16 and older. Youth interest is for ages 6–12, for the program coming summer 2027. All under-18 visitors must supply a parent/guardian name, including 16- and 17-year-old team players. Ages 13–15 do not fit either signup option.

Storage keys: `ethio-walia-signups`, `ethio-walia-pledges`, `ethio-walia-theme`, `ethio-walia-content-v2`. Clearing site data removes these records. This site has no server, payment integration, shared registration database or administrator account. Before accepting live registrations across devices, connect a submission service and replace the local-only copy.

## Extracted club facts

Source: supplied four-page district membership package, read in full and visually inspected.

| Information | Confirmed content |
|---|---|
| Official name | Ethio-Walia Sport Club |
| Established / location | 2017 / Toronto, Ontario |
| Status / community | Non-profit; Ethiopian and Eritrean communities |
| Mission / values | Competitive soccer, player development, teamwork, leadership, discipline, respect, community involvement |
| Squad | More than 25 adult players, ages 18+; former professional experience within team and staff |
| Achievement | TSSL Championship in 2021; several other cup and tournament victories |
| Development | Structured training, coaching capacity, youth teams in the future, local partnerships; seeking district membership |
| Coach | Ephrem Wondwossen Gebremaryam; CAF B Coaching Diploma; issued 25 May 2025 |
| Contact | Abel Gebrehiwet; 647-937-5446; Gebrehiwetabel241@gmail.com; Instagram @ethio_walia |

The PDF does not supply individual player names, leadership titles or current event dates. No identities were inferred from photographs. The owner’s update sets team signup eligibility to 16+ and announces the youth program for ages 6–12, coming summer 2027.

## Design decisions

1. Crest green `#094a0a` and deep navy `#062352` come from saturated logo color samples.
2. Mountain blue `#1f649d` and warm ibex gold `#926a41` supply secondary accents.
3. Off-white surfaces, generous spacing and a 1280px maximum content width create a clean editorial layout.
4. Barlow Condensed headlines and Inter body text set a clear type hierarchy.
5. Large real photography, a six-link hamburger drawer, restrained transform/opacity motion and reduced-motion support guide the experience.

Arsenal's live site returned HTTP 403 during reference access; the design follows the editorial characteristics specified in the supplied brief.

## Owner update

The Home hero uses the newly supplied team photo. The youth photo and all other gallery images are unchanged. TikTok @ethio.walia sits beside Instagram in the footer and menu. Missing player/leadership profiles and unsupported donation allocation details have been removed. The payment page remains a local pledge form with a contact link; no payment URL was invented. All draft filler text has been removed from the site.

Youth program details: ages 6–12, coming summer 2027, more information to come soon. Team signup: ages 16+. Tentative training: Tuesday, Thursday and Sunday, 5:30–7:30 p.m., outside winter, at Regent Park Athletic Grounds in Toronto.

## Verification

All six routes were checked at 375px, 768px, 1024px and 1440px with no horizontal overflow. Browser checks covered direct file opening, menu focus trap and Escape/focus return, theme changes, gallery category filters and lightbox keyboard navigation, FAQ toggles, inline validation, guardian visibility, device-local signup and pledge records, upcoming/past schedule views, JSON import and .ics download for an isolated test event. Test records were saved only in isolated browser profiles and are not included in this package. Revision checks cover the new age limits, youth announcement, supplied map links, TikTok links and the absence of draft filler.

Visual review includes desktop and mobile. There are no application JavaScript runtime dependencies, build tools or production test fixtures. The nine HEIC photos were decoded to JPEG and all 33 photos were inspected. Image dimensions are declared, large photos are capped at 1920px and deferred photos use lazy loading. Browser storage failures show an explicit error instead of reporting successful submission.

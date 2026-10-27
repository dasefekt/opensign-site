# Open Sign — site brief for Codex

You are taking over `index.html`, a one-page presentation site for **Open Sign**, a small web studio in Cape Town, South Africa. The page is complete and works; your job is to make it **more visual and more premium** without changing its structure, copy, prices or rules. English only.

## What Open Sign is
- A Cape Town studio that builds **websites, booking/ordering systems and social media** for small businesses with a weak online presence: guesthouses & B&Bs, restaurants & bars, equipment & party hire, trades & services, shops & studios, funeral homes.
- Offer: **free mockup first** (client sees their own site before paying), **live in 7 days** after approval once photos and prices are in, **client owns domain and site**, **one contact on WhatsApp**.
- Packages (fixed, same for every trade): Website R 8,500 once · Website + bookings or orders R 15,000 once · Online presence R 3,500 per month. Half on approval, half at go-live.
- Portfolio (client work; all live): capeaura.co.za, vistablu.co.za, seaviu.co.za (three Camps Bay guesthouses), artessy.co.za (furniture studio), Expandable Homes SA (modular homes, link to be added).

## Brand
- Name: **Open Sign**. Concept: the neon "OPEN" sign in a shop window. Online, that sign is a website people can find, trust and book on at any hour. Tagline on the page: "Put the open sign up online."
- Logo: the word OPEN in a small neon-outlined badge (already in the header, CSS only). Keep it; you may refine it (an SVG version is welcome).
- Palette (CSS tokens in `:root`): pale paper `--bg #f6f7f4`, ink `--fg #101c2b`, dark band `--ink #0f2238`, kelp accent `--accent #0d7a6b`, gold `--gold #d9a441`, **neon `--neon #4fe3c1`** for the sign only. Dark theme tokens exist under `prefers-color-scheme: dark` and `[data-theme="dark"]`; keep both in sync if you add colors. Every color must be a token; no literal colors in components.
- Type: Bricolage Grotesque (display) + Figtree (body), via Google Fonts. Keep them.
- Tone: plain, confident, no hype words ("boost", "grow", "unlock"), no exclamation marks. The funeral-home sector copy must stay sober.

## Hard rules (do not break)
1. **Never show a person's name or imply ownership.** The studio speaks as "we". Portfolio sites are described as client work only. No founder, no "I".
2. Do not invent testimonials, client quotes, review counts, logos of clients, or statistics. The only numbers on the page are the prices and the 15% OTA commission example.
3. Keep all copy as is unless you are fixing grammar. Keep the section order: header → hero → trust strip → Who it's for → Work → How it works (7 days) → Prices (+ per-trade table) → guesthouse commission example → FAQ → About/Contact → footer.
4. Contact placeholders stay until replaced: WhatsApp `+27 72 507 3392` (will change), email `hello@opensign.co.za`.
5. Mobile first: must work at 360–400 px wide with no horizontal scroll; keep the 16 px side gutters and `env(safe-area-inset-*)` paddings; keep `prefers-reduced-motion` handling; keep visible focus states.
6. Single file is preferred (inline CSS/JS). If you split files, keep relative paths. No frameworks needed; no tracking scripts.
7. Images: use real photos only where the owner supplies them (see below). Until then, keep placeholders as CSS gradients; never pull stock photos of real businesses or copyrighted logos.

## What to improve (in priority order)
1. **Portfolio screenshots.** The "Work" cards use browser frames with gradient placeholders. Replace the gradient `.shot` blocks with real screenshots of each site (the owner will provide `cape-aura.jpg`, `vistablu.jpg`, `seaviu.jpg`, `artessy.jpg`, `expandable-homes.jpg`, desktop + mobile crops). Show a desktop frame with a phone frame overlapping the corner, like agency portfolio tiles. Lazy-load, `object-fit: cover`, keep aspect 16/10.
2. **Hero.** Make the neon OPEN sign feel like a real sign: tube-style letters (SVG with stroke + glow filter), subtle hum animation, a faint reflection on the "glass" beneath. Keep the two-phone "Today / With Open Sign" illustration, but render it more realistically (notch, status bar, soft shadow, slight tilt).
3. **Sector cards.** Each has a line icon; make the icons consistent (same stroke width, same optical size) and add a hover state that reveals the three bullet points more clearly on desktop. On mobile, cards stack.
4. **7-day timeline.** Turn the four `.day` boxes into a horizontal timeline with a progress rail; the "Days 1–2" step is the client's part and stays highlighted in `--accent-soft`.
5. **Pricing cards.** The middle card is the recommended one; make it visibly elevated (not just a border). Add a small "Most chosen" tag to it.
6. **Micro-interactions.** Copy buttons already work; add a subtle success state. Smooth-scroll for in-page anchors. Nothing that autoplays sound or blocks the page.
7. **Performance.** Keep total page weight under ~1.5 MB with screenshots; compress images to WebP ≤ 200 KB each.

## Assets the owner will add
- Screenshots of the five portfolio sites (desktop + mobile).
- One hero photo per guesthouse (pool / sea view / sunset) for optional card backgrounds.
- Final WhatsApp number and confirmation that `opensign.co.za` is registered.

## Definition of done
- Lighthouse mobile ≥ 90 performance, ≥ 95 accessibility.
- Light and dark themes both readable (toggle `data-theme="dark"` on `<html>` to test).
- Every section visible on first load (no content hidden behind scroll animations).
- The page still reads as a studio, not a person.

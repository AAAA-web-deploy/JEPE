# Jensen Pepe ($JEPE)

A standalone cinematic, responsive Ethereum meme-project website, adapted from the supplied PushEthereum source. The site is a fictional parody, not affiliated with or endorsed by Jensen Huang or NVIDIA.

## Launch locally

Extract the complete ZIP into one folder. Open `index.html` in a browser, or for local HTTP testing run:

```sh
python -m http.server 8000
```

Visit `http://localhost:8000`. No npm install, build process, external JavaScript, or API keys are required.

## Configure before publishing

Edit `site-config.js` only. Replace each `null` with the verified value in quotation marks when available:

```js
window.JEPE_CONFIG = {
  contract: null,
  x: null,
  telegram: null
};
```

- `contract`: actual Ethereum mainnet token contract address (0x followed by 40 hexadecimal characters).
- `x`: full HTTPS X profile URL.
- `telegram`: full HTTPS Telegram community URL.

The website ships with all three values unset. The contract displays Coming soon; copy controls and pending social links remain disabled until a valid value is entered. The app checks address format, not the deployed contract or ownership of links. Confirm all values independently. Clipboard support is best on HTTPS or localhost. No token supply, tax, ownership or DEX claim has been invented.

Deploy the contents of this folder to a static host, such as GitHub Pages. Keep the folder structure intact. For social sharing after deployment, update the `og:image` and `twitter:image` tags in `index.html` to the full public HTTPS URL of `assets/art/social-banner.webp`; add a canonical URL and `og:url` using your actual domain if desired.

## Site structure

- Hero: Jensen Pepe pushing the stone uphill.
- The Beginning: the first push toward the summit.
- The Bear Market: interactive pressure/storm toggle.
- The Night Watch: campfire and AI builder's vision.
- The Summit: a fictional victory scene at sunrise.
- The Token: animated parchment with name, ticker, network and contract.
- Footer: social links and unofficial-project disclaimer.

The original scroll-controlled trail, rotation, dust particles, bear toggle, campfire glow, scroll-opening animation and responsive layout are retained. Reduced-motion preferences are supported. Artwork is optimized to WebP; the rolling stone is a transparent PNG. The original font assets and their licenses remain with the website.

## Checks

Run these commands from the extracted website folder with Node.js installed:

```sh
node --check app.js
node tests/interaction.test.cjs
```

The simulated-DOM suite passes stone movement and rotation, dust emission, bear toggle, opening parchment, reduced motion, contract validation, social validation and clipboard handler tests. Desktop (1440 × 900) and mobile (390 × 844) in-memory Chromium previews were rendered and tested for horizontal overflow, script errors and the bear/scroll interactions. Local URL navigation was blocked in the test environment; therefore verify the deployed site and actual clipboard permissions in your own browser before launch.

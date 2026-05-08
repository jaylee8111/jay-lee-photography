# Personal Bio Website

A minimal, mobile-responsive personal bio site built with plain HTML, CSS, and JavaScript — no frameworks, no build step.

## Project structure

```
Week 1/
├── index.html      # single-page layout (Hero + About)
├── styles.css      # mobile-first styling, breakpoint at 768px
├── script.js       # sets footer year
└── README.md       # you are here
```

## Site architecture

```mermaid
flowchart TD
    A[index.html] -->|links| B[styles.css]
    A -->|defers| C[script.js]
    A --> D[Header / Logo]
    A --> E[Hero Section]
    A --> F[About Section]
    A --> G[Footer]
    C -.->|injects year| G
    B -.->|styles all| D
    B -.->|styles all| E
    B -.->|styles all| F
    B -.->|styles all| G
```

## Page flow

```mermaid
sequenceDiagram
    participant U as User
    participant B as Browser
    participant H as index.html
    participant S as styles.css
    participant J as script.js

    U->>B: visits site
    B->>H: requests index.html
    H-->>B: HTML structure
    B->>S: requests styles.css
    S-->>B: applies minimal/clean styles
    B->>J: loads script.js (deferred)
    J-->>B: fills footer year
    B-->>U: renders Hero + About
```

## Run locally

Open `index.html` directly, or serve the folder:

```bash
python3 -m http.server 8000
```

Then visit <http://localhost:8000>.

## Deploy

- **Netlify:** drag the `Week 1` folder onto <https://app.netlify.com/drop> for an instant URL
- **Vercel:** run `npx vercel` from the folder, or push to GitHub and import via vercel.com

## Customizing

Replace these placeholder tokens in `index.html`:

- `[Your Name]`
- `[Your Title / Tagline]`
- `[Your Bio]`

Tweak colors and spacing via the CSS custom properties at the top of `styles.css`:

```css
:root {
  --bg: #fdfdfc;
  --fg: #1a1a1a;
  --muted: #6b6b6b;
  --accent: #2a6df4;
}
```

## Roadmap

- [ ] Replace placeholders with real content
- [ ] Add social/contact links
- [ ] Optional: dark mode toggle
- [ ] Optional: portfolio/gallery section

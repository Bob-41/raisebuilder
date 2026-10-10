# Raise a Builder Page

A personal portfolio site for [Pixl](https://pixl.hackclub.com), built for Hack Club's Raise a Builder. It has three pages — home, projects, and donations — with a dark teal theme. It's plain HTML and CSS: no framework, no dependencies, and no build step.

![Home page](docs/screenshots/home.png)

## Description

The site is a small portfolio for the projects I'm building as a Pixl Maker. The home page introduces me and links out to GitHub and Pixl. The projects page lists the things I've made, most notably [Relay](https://github.com/Bob-41/Relay), a tool that lets you upload code to a First Tech Challenge Rev Robotics Control Hub over your local Wi-Fi instead of connecting to the robot's own network, plus [my team website](https://quantumcoders.kozow.com) with data about our FTC team, Quantum Coders. The donate page embeds a Hack Club Bank donation form so visitors can support the team directly.

Everything is plain static HTML and CSS. Each page is a separate file that shares one stylesheet, and navigation is plain `<a>` tags between them. The donation page is the only part that reaches outside the repo as it is just a HCB donate url embed for my FTC robotics team.


## Getting Started

### Dependencies

None. There's no `package.json`, no `node_modules`, and nothing to install.

- Any modern web browser (Chrome, Firefox, Safari, Edge)
- Optionally Python 3, only if you want to serve it locally instead of opening the file directly
- No OS requirement — it's a static site, so it runs the same on Windows, macOS, and Linux

### Installing

Clone the repo and open it:

```bash
git clone https://github.com/Bob-41/raisebuilder.git
cd raisebuilder
```

That gives you the whole site:

```
raisebuilder/
├── index.html     # Home
├── about.html     # Projects
├── donate.html    # Donations
├── style.css      # All styling, shared by every page
├── robots.txt
└── readme.md
```

To view it locally, serve the folder rather than opening `index.html` directly — this keeps the links between pages behaving the same as they do once deployed:

```bash
python3 -m http.server 8000
```

Then go to <http://localhost:8000>.

No files need to be modified to run it. To publish it, upload this folder to any static host — GitHub Pages, Netlify, Cloudflare Pages, or plain object storage all work without a build command.

### Modifying the site

- **Colors** — all of them live at the top of `style.css`: the page background is `#09242c`, cards and the nav are `#08242a`, the gold link color is `#e5a93c`, and the border highlight is `#4b94cb`.
- **Navigation** — the `<nav>` block is repeated in all three HTML files, so adding a page means editing each one and adding the new file to the folder.
- **Project list** — the entries on the projects page are plain `<li>` items in `about.html` under `<ul id="projects">`.
- **Donation form** — swap the `src` on the `<iframe>` in `donate.html` for a different Hack Club Bank URL. Keep the `/donations/start/` part of the path.
- **Crawlers** — `robots.txt` is set to `Disallow: /`, so search engines are kept out. Remove that file if you'd rather be listed.

### Executing the program

1. Start a local server from inside the `raisebuilder` folder:
   ```bash
   python3 -m http.server 8000
   ```
2. Open <http://localhost:8000> for the home page.
3. Use the nav links to move between Home, Projects, and Donate.
4. The Donate page loads the Hack Club Bank form inside the page; it needs an internet connection.
5. Stop the server with `Ctrl+C`.

To iterate on the styling, edit `style.css` and reload — there's nothing to rebuild, and every page picks up the change at once.
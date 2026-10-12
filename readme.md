# Raise a Builder Page

My personalproject site for raise a builder for hackclub customized with my own theme.

It's plain HTML and CSS.

![Home page](images/home.png)

## Description

This is a small portfolio for the projects I'm building as a Pixl Maker.

- **Home** introduces me and links out to GitHub and Pixl.
- **Projects** lists the things I've made, most notably [Relay](https://github.com/Bob-41/Relay) — a tool that uploads code to a First Tech Challenge Rev Robotics Control Hub over your local Wi-Fi, so you no longer have to go stand next to the robot holding your laptop like it's 2009. Also includes [my team website](https://quantumcoders.kozow.com) with data about our FTC team, Quantum Coders.
- **Donate** embeds a Hack Club Bank donation form so visitors can support the team directly. This is the only part of the site that touches the outside internet.

Each page is a separate file sharing one stylesheet, and navigation is plain `<a>` tags between them. That's it. There's no clever routing layer. The `<a>` tags do the work.

### Screenshots

| Home | Projects | Donate |
| --- | --- | --- |
| ![Home page](images/home.png) | ![Projects page](images/projects.png) | ![Donate page](images/donate.png) |


### Modifying the site

- **Colors** — all of them live at the top of `style.css`: page background `#09242c`, cards and nav `#08242a`, gold link color `#e5a93c`, border highlight `#4b94cb`.
- **Navigation** — the `<nav>` block is repeated in all three HTML files, so adding a page means editing each one and adding the new file to the folder. Yes, copy-paste. That's the whole pattern.
- **Project list** — the entries on the projects page are plain `<li>` items in `about.html` under `<ul id="projects">`.
- **Donation form** — swap the `src` on the `<iframe>` in `donate.html` for a different Hack Club Bank URL. Keep the `/donations/start/` part of the path.


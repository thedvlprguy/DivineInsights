# DivineInsights 📄

![DivineInsights](public/DivineInsights-og.jpg)

DivineInsights is a minimal, responsive, accessible, and SEO-friendly Astro blog theme. This theme is designed and crafted based on a personal blog.

This theme follows best practices and provides accessibility out of the box. Light and dark mode are supported by default. Moreover, additional color schemes can also be configured.

This theme is self-documented, which means articles/posts in this theme can also be considered as documentation.

## 🔥 Features

- type-safe markdown
- super fast performance
- accessible (Keyboard/VoiceOver)
- responsive (mobile ~ desktops)
- SEO-friendly
- light & dark mode
- fuzzy search
- draft posts & pagination
- sitemap & rss feed
- followed best practices
- highly customizable
- dynamic OG image generation for blog posts

_Note: I've tested screen-reader accessibility of DivineInsights using **VoiceOver** on Mac and **TalkBack** on Android. I couldn't test all other screen-readers out there. However, accessibility enhancements in DivineInsights should be working fine on others as well._

## ✅ Lighthouse Score

![DivineInsights Lighthouse Score](DivineInsights-lighthouse-score.svg)

## 🚀 Project Structure

Inside of DivineInsights, you'll see the following folders and files:

```bash
/
├── public/
│   ├── assets/
│   │   └── logo.svg
│   │   └── logo.png
│   └── favicon.svg
│   └── DivineInsights-og.jpg
│   └── robots.txt
│   └── toggle-theme.js
├── src/
│   ├── assets/
│   │   └── socialIcons.ts
│   ├── components/
│   ├── content/
│   │   |  blog/
│   │   |    └── some-blog-posts.md
│   │   └── config.ts
│   ├── layouts/
│   └── pages/
│   └── styles/
│   └── utils/
│   └── config.ts
│   └── types.ts
└── package.json
```

Astro looks for `.astro` or `.md` files in the `src/pages/` directory. Each page is exposed as a route based on its file name.

Any static assets, like images, can be placed in the `public/` directory.

All blog posts are stored in `src/content/blog` directory.

## 📖 Documentation

Documentation can be read in two formats: markdown & blog post.

- Configuration
- Add Posts
- Customize Color Schemes
- Predefined Color Schemes

## 💻 Tech Stack

**Main Framework** - Astro  
**Type Checking** - TypeScript  
**Component Framework** - ReactJS  
**Styling** - TailwindCSS  
**UI/UX** - Figma  
**Fuzzy Search** - FuseJS  
**Icons** - Boxicons | Tablers  
**Code Formatting** - Prettier  
**Deployment** - Cloudflare Pages  
**Illustration in About Page** - Free SVG Illustration  
**Linting** - ESLint

## 👨🏻‍💻 Running Locally

You can start using this project locally by running the following command in your desired directory:

```bash
# npm 6.x
npm create astro@latest --template ascendantaditya/divineinsights

# npm 7+, extra double-dash is needed:
npm create astro@latest -- --template ascendantaditya/divineinsights

# yarn
yarn create astro --template ascendantaditya/divineinsights

# pnpm
pnpm dlx create-astro --template ascendantaditya/divineinsights
```

> **_Warning!_** If you're using `yarn 1`, you might need to install `sharp` as a dependency.

Then start the project by running the following commands:

```bash
# install dependencies
npm run install

# start running the project
npm run dev
```

As an alternative approach, if you have Docker installed, you can use Docker to run this project locally. Here's how:

```bash
# Build the Docker image
docker build -t DivineInsights .

# Run the Docker container
docker run -p 4321:80 DivineInsights
```

## Google Site Verification (optional)

You can easily add your Google Site Verification HTML tag in DivineInsights using an environment variable. This step is optional. If you don't add the following environment variable, the google-site-verification tag won't appear in the HTML `<head>` section.

```bash
# in your environment variable file (.env)
PUBLIC_GOOGLE_SITE_VERIFICATION=your-google-site-verification-value
```

## 🧞 Commands

All commands are run from the root of the project, from a terminal:

> **_Note!_** For `Docker` commands we must have it installed in your machine.

| Command                              | Action                                                                                                                           |
| :----------------------------------- | :------------------------------------------------------------------------------------------------------------------------------- |
| `npm install`                        | Installs dependencies                                                                                                            |
| `npm run dev`                        | Starts local dev server at `localhost:4321`                                                                                      |
| `npm run build`                      | Build your production site to `./dist/`                                                                                          |
| `npm run preview`                    | Preview your build locally, before deploying                                                                                     |
| `npm run format:check`               | Check code format with Prettier                                                                                                  |
| `npm run format`                     | Format codes with Prettier                                                                                                       |
| `npm run sync`                       | Generates TypeScript types for all Astro modules.                                                                                |
| `npm run lint`                       | Lint with ESLint                                                                                                                 |
| `docker compose up -d`               | Run DivineInsights on docker, You can access with the same hostname and port informed on `dev` command.                           |
| `docker compose run app npm install` | You can run any command above into the docker container.                                                                         |
| `docker build -t DivineInsights .`   | Build Docker image for DivineInsights.                                                                                           |
| `docker run -p 4321:80 DivineInsights`| Run DivineInsights on Docker. The website will be accessible at `http://localhost:4321`.                                         |

> **_Warning!_** Windows PowerShell users may need to install the concurrently package if they want
| `npm run dev`                        | Starts local dev server at `localhost:4321`                                                                                      |
| `npm run build`                      | Build your production site to `./dist/`                                                                                          |
| `npm run preview`                    | Preview your build locally, before deploying                                                                                     |
| `npm run format:check`               | Check code format with Prettier                                                                                                  |
| `npm run format`                     | Format codes with Prettier                                                                                                       |
| `npm run sync`                       | Generates TypeScript types for all Astro modules. [Learn more](https://docs.astro.build/en/reference/cli-reference/#astro-sync). |
| `npm run lint`                       | Lint with ESLint                                                                                                                 |
| `docker compose up -d`               | Run DivineInsights on docker, You can access with the same hostname and port informed on `dev` command.                              |
| `docker compose run app npm install` | You can run any command above into the docker container.                                                                         |
| `docker build -t DivineInsights .`       | Build Docker image for DivineInsights.                                                                                               |
| `docker run -p 4321:80 DivineInsights`   | Run DivineInsights on Docker. The website will be accessible at `http://localhost:4321`.                                             |

> **_Warning!_** Windows PowerShell users may need to install the [concurrently package](https://www.npmjs.com/package/concurrently) if they want to [run diagnostics](https://docs.astro.build/en/reference/cli-reference/#astro-check) during development (`astro check --watch & astro dev`). For more info, see [this issue](https://github.com/ascendantaditya/divineinsights/issues/113).

## ✨ Feedback & Suggestions

If you have any suggestions/feedback, you can contact me via [my email](mailto:contact@ascendantaditya.dev). Alternatively, feel free to open an issue if you find bugs or want to request new features.

## 📜 License

Licensed under the MIT License, Copyright © 2023

---

Made with 🤍 by [Aditya Tomar](https://ascendantaditya.dev) 👨🏻‍💻 and [contributors](https://github.com/ascendantaditya/divineinsights/graphs/contributors).

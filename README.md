# francois.bertet.dev

[![CI/CD pipeline](https://img.shields.io/github/actions/workflow/status/fbertet/francois.bertet.dev/.github%2Fworkflows%2Fhugo.yaml)](https://github.com/fbertet/francois.bertet.dev/deployments/github-pages)
[![Status](https://img.shields.io/uptimerobot/status/m802173803-cee45eb58af2526583346b90?label=Status)](https://stats.uptimerobot.com/eniLI7gU6f)
[![30-day Uptime](https://img.shields.io/uptimerobot/ratio/m802173803-cee45eb58af2526583346b90?label=30-day%20Uptime)](https://stats.uptimerobot.com/eniLI7gU6f)
[![GitHub License](https://img.shields.io/github/license/fbertet/francois.bertet.dev?label=License)](LICENSE)

<p align="center">
  <img src="docs/preview.png" alt="Website preview" width="600">
</p>

My [**personal website**](https://francois.bertet.dev) built with [Hugo](https://gohugo.io/) framework and [Congo](https://github.com/jpanther/congo) theme.


## Local Development

To preview changes locally before deploying:

```bash
https://github.com/fbertet/francois.bertet.dev && cd francois.bertet.dev
hugo serve
```

Then visit `localhost:1313` in your browser. The site will automatically reload when you make changes to the source files.

NB: In case of problems, please make sure you use Hugo version `0.111.3`.

## Deployment

This static website is hosted on Github pages.

Changes are automatically deployed via [Github Actions](https://github.com/fbertet/francois.bertet.dev/deployments/github-pages) whenever changes are pushed to the main branch.

The custom domain `francois.bertet.dev` is configured through a CNAME DNS record pointing to GitHub Pages.


## License

This project is licensed under the Creative Commons Attribution-ShareAlike 4.0 International License (CC-BY-SA-4.0) – see the [LICENSE](LICENSE) file for details.

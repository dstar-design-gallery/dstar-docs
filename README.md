# Get Started

Clone `dstar-docs` from the repository.

```bash
git clone https://github.com/dstar-design-gallery/dstar-docs.git
```

You will need [docsify](https://docsify.js.org/) to run the docs. It is recommended to install `docsify-cli` globally, which helps initializing and previewing the website locally.

:warning: make sure that `node` and `npm` are [installed](https://nodejs.org/en/download/).

```bash
npm i docsify-cli -g
```

Run the local server with `docsify serve`. You can preview your site in your browser on `http://localhost:3000`.

```bash
docsify serve
```

To add new pages, add them to `_sidebar.md`:

```markdown
* [Get Started](/)
* [Introduction](introduction.md)
* [Your New Page](yourNewPage.md)
```

Images should be located under `media` folder.

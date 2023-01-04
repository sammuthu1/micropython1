# SamsBlog
**SamsBlog, created with the Micro-Site Builder**

[Click here](https://github.com/pages/sammuthu1/SamsBlog) to view your new site!

Below are some steps to run your new MkDocs site locally, but you do not necessarily have to do this to get started. [Click here to read more documentation](https://microsite-docscom), but the main actions to take from here would be:
1. Update your content, which can be done in GitHub
2. Redeploy your site, which [can be done many ways](https://microsite-docs.optum.com/getting-started/deploy)

## Getting Started

### Prerequisites
In order to run your MkDocs page locally, you'll need Python installed on your machine, as well as the Python package manager, pip. You can check if you have these already installed from the command line:

```zsh
python --version
pip --version
```

Install the `mkdocs` package using pip, as well as other dependencies, such as the theme this template uses:

```zsh
pip install -r requirements.txt
```

### Development
To start working on your documentation locally, you will need to clone this repo:

```zsh
git clone https://github.com/sammuthu1/SamsBlog.git
cd SamsBlog
```

To start up the server, run this command:

```zsh
mkdocs serve
```

Open http://127.0.0.1:8000 in a browser to see the documentation page you have created! 🎉

## Project layout
Your repository will resemble the directory structure here:

    mkdocs.yml    # The configuration file
    docs/
        index.md  # The documentation homepage
        img/      # Image directory
        ...       # Other directories with Markdown pages

## Deployment
Micro-Sites are hosted with GitHub Pages and do not need any other type of infrastructure other than your GitHub repository. MkDocs will build your `master` branch into a static website that will be pushed to the `gh-pages` branch and your changes are live! You can manually redeploy or configure automation to redeploy with every change to `master`.

### Manually
To manually redeploy your documentation changes:

```zsh
mkdocs gh-deploy
```

This will rebuild your `master` branch and then push the built website to the `gh-pages` branch.

### Automatically
You can also use Jenkins to continuously redeploy your documentation changes. See [this page] for more details.

## Collaboration
To continue driving better documentation for your customers, other contributers will be able to improve or build upon your page through this repository. Read more about pull requests and other ways to collaborate [right here]!

## Reference
Refer to [this site] for more documentation.

<!-- external links -->
[this page]: https://microsite-docs.optum.com/getting-started/deploy
[this site]: https://microsite-docs.optum.com
[right here]: https://microsite-docs.optum.com/getting-started/collaborate

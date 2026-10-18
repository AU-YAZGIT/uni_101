# YAZGİT University 101

[Türkçe](README.md) | **English**

[![Deploy](https://github.com/AU-YAZGIT/uni_101/actions/workflows/deploy.yml/badge.svg)](https://github.com/AU-YAZGIT/uni_101/actions/workflows/deploy.yml)
[![Check](https://github.com/AU-YAZGIT/uni_101/actions/workflows/check.yml/badge.svg)](https://github.com/AU-YAZGIT/uni_101/actions/workflows/check.yml)

An open-source university and developer guide for new and current students, created by **YAZGİT (the Artificial Intelligence and Image Processing Community)**. The guide itself is currently written in Turkish.

🌐 **Live site:** <https://au-yazgit.github.io/uni_101/>

## How can I contribute?

This guide grows with student contributions. If you spot a wrong or missing piece of information:

1. **Quick fix:** Click the edit (pencil) icon at the top right of any page on the site, make your change on GitHub, and open a PR.
2. **New content:** Browse the [open issues](https://github.com/AU-YAZGIT/uni_101/issues). Issues labeled `good first issue` are a good place to start.
3. **Rules:** Read the [contributing guide](CONTRIBUTING.md) before opening a PR. PR titles follow [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) (e.g. `docs: update the campuses page`).

## Running locally

Requirement: Python 3.10 or newer.

```bash
git clone https://github.com/AU-YAZGIT/uni_101.git
cd uni_101

python -m venv venv
source venv/bin/activate        # Windows PowerShell: .\venv\Scripts\Activate.ps1

pip install -r requirements.txt
mkdocs serve
```

The site opens at `http://127.0.0.1:8000` and reloads as you save files. After every merge to `main`, the site is published automatically with GitHub Actions.

Before opening a PR, run these checks (CI runs the same ones):

```bash
mkdocs build --strict
npx markdownlint-cli2
```

## Contact

- GitHub: [AU-YAZGIT](https://github.com/AU-YAZGIT)
- Instagram: [@au_yazgit](https://www.instagram.com/au_yazgit/)

## License

This project is released under the license in the [LICENSE](LICENSE) file.
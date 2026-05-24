# Contributing

Thank you for considering contributing to **mapa-contatos-historia**. This project maps History courses and institutional contacts across Brazilian public universities using INEP open data. We welcome contributions that improve data accuracy, expand coverage, or enhance the tooling.

## Code of Conduct

This project adheres to the [Contributor Covenant](https://www.contributor-covenant.org/) code of conduct. By participating, you are expected to uphold this code. Please report unacceptable behavior to the repository maintainer.

## Getting Started

1. Fork the repository.
2. Clone your fork:
   ```bash
   git clone git@github.com:YOUR_USERNAME/mapa-contatos-historia.git
   cd mapa-contatos-historia
   ```
3. Set up a virtual environment and install dependencies:
   ```bash
   python -m venv .venv
   source .venv/bin/activate
   pip install -r requirements.txt
   pip install ruff
   ```
4. Create a branch for your work (see branch naming below).

## Branch Naming

Use descriptive prefixes followed by a short summary:

| Prefix     | Purpose                       |
|------------|-------------------------------|
| `feature/` | New functionality             |
| `fix/`     | Bug fixes                     |
| `docs/`    | Documentation changes         |
| `chore/`   | Maintenance, tooling, CI      |

Examples: `feature/add-northeast-sprint`, `fix/encoding-issue`, `docs/update-metodologia`.

## Commit Messages

We follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>: <short description>

[optional body]
```

Types: `feat`, `fix`, `docs`, `chore`, `refactor`, `test`, `ci`.

Examples:
- `feat: add email lookup for Northeast universities`
- `fix: correct column mapping in CINE_ROTULO filter`
- `docs: add dicionario-de-dados for new fields`

## Pull Requests

- Open a PR against the `main` branch.
- Use the provided [pull request template](.github/PULL_REQUEST_TEMPLATE.md) if one exists.
- Keep PRs focused on a single concern. Split large changes into separate PRs.
- Ensure CI passes (lint, import checks).

## Testing

- If adding new Python logic, include tests using `pytest`.
- Place test files in a `tests/` directory with the `test_` prefix.
- Run tests locally before opening a PR:
  ```bash
  python -m pytest
  ```

## Code Style

- Formatting and linting are enforced by `ruff`.
- Run the linter before committing:
  ```bash
  ruff check scripts/
  ```
- Use type hints for new functions.

## Data Contributions

- **New contact emails**: Add them to the XLSX via the appropriate sprint sheet. Include the source URL and verification date.
- **Corrections**: Update the relevant cell and mark the change in `observacoes`.
- **New data sources**: Add the source to the `Fontes` sheet and update `docs/dados-e-reprodutibilidade.md`.

## Questions

Open a [GitHub Discussion](https://github.com/pedrofernando0/mapa-contatos-historia/discussions) or file an issue.

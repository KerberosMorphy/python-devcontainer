# Dev Container - Python 3

Dev Container pour VS Code permettant le développement d'application Python et Django avec [PDM](https://pdm.fming.dev/).

## Prérequis

- VS Code
- Docker
- [Remote - Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

## Contenu de l'environnement

### Extensions VS Code

- [change-case](https://marketplace.visualstudio.com/items?itemName=wmaurer.change-case)
- [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
- [Pylance](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance)
- [Code Runner](https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner)
- [Docker](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker)
- [Todo Tree](https://marketplace.visualstudio.com/items?itemName=gruntfuggly.todo-tree)
- [GitLens — Git supercharged](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
- [indent-rainbow](https://marketplace.visualstudio.com/items?itemName=oderwat.indent-rainbow)
- [TOML Language Support](https://marketplace.visualstudio.com/items?itemName=be5invis.toml)
- [YAML](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml)
- [Django](https://marketplace.visualstudio.com/items?itemName=batisteo.vscode-django)
- [Prettier - Code formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)

### PIP

Pour gérer les outils installés depuis PyPI, `pipx` à été intégré à l'environnement.
Voir la section [PIPX](#pipx) pour la liste des outils installés par défaut.

### PIPX

- `pre-commit`
- `flake9`
  Incluant les plugins:
  - `pep8-naming`
  - `flake8-isort`
  - `flake8-black`
  - `flake8-bandit`
  - `flake8-django`
  - `flake8-bugbear`
  - `flake8-simplify`
  - `flake8-pytest-style`
  - `flake8-cognitive-complexity`
  - `flake8-expression-complexity`
- `black`
- `isort`
- `mypy`
- `tox`
  Incluant les plugins:
  - `tox-pdm`
- `pdm` avec PEP-582 activé
- `virtualenv`

### Docker

L'environnement est lié au Docker de l'hôte, vous pouvez donc déployer des images dockers et les gérer directement sur l'hôte.

### Credentials

Par défaut, l'agent SSH est partagé avec l'environnement. Vous pouvez donc utiliser git clone sur un dépôt privé pour lequel vous avez un accès SSH.

Pour partager des accès utilisant `.netrc`, allez dans `.devcontainer/docker-compose.yml` et décommenter les lignes concernant `.netrc`.

```yml
volumes:
  # ...
  # Uncomment the next three line and adjust the source if you want to share .netrc credentials
  - type: bind
    source: ../.netrc
    target: /root/.netrc
```

Par défaut `../.netrc` pointe à la racine du projet.
Assurez-vous que le fichier existe bel et bien avant de démarrer le `devcontainer`. La raison est que s'il n'existe pas, Docker va le créer automatiquement en tant que dossier.

## Configuration par défaut

Dans `.devcontainer/devcontainer.json`, plusieurs configurations par défaut ont été inclus.

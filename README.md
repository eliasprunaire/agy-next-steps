# agy-next-steps

Collection de plugins natifs KISS pour Antigravity CLI (`agy`), Antigravity App et Antigravity IDE.

## Plugins disponibles

| Plugin | Dossier | Rôle |
| :--- | :--- | :--- |
| `follow-ups` | `plugins/follow-ups/` | Propose 1 à 3 suites actionnables en fin de réponse avec mise en avant `(Recommandé)` et multi-sélection (`1+2`, `1, 3`). |

## Installation

Depuis GitHub :

```bash
agy plugin install https://github.com/eliasprunaire/agy-next-steps/tree/main/plugins/follow-ups
```

Depuis un clone local :

```bash
agy plugin validate --strict ./plugins/follow-ups
agy plugin install ./plugins/follow-ups
```

## Licence

MIT (voir [LICENSE](./LICENSE)).

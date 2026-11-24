# Plugin Antigravity `follow-ups`

Plugin natif KISS (sans MCP ni hook) qui propose en fin de réponse 1 à 3 suites actionnables, avec mise en avant du choix recommandé en position 1, rendu Markdown propre sur Antigravity IDE/App et Antigravity CLI, et support natif de la multi-sélection (`1+2`, `1, 3`, `1 2 3`).

## Structure

- `plugin.json` : manifeste du plugin (`name: "follow-ups"`).
- `assets/logo.svg` : icône SVG `128x128`.
- `rules/AGENTS.md` : règle toujours active tant que le plugin est activé.

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

## Éviter les doublons

Si tu as déjà une ancienne règle de suivi de trajectoire (ou un plugin similaire activé), désactive-la ou retire-la une fois `follow-ups` activé pour éviter deux blocs de suggestions en fin de réponse.

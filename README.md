# ia-memory

Backup de la memoria de Claude Code (usuario kaelen-phoenix) para restaurar en otra PC/entorno.

## Contenido
- `MEMORY.md` — índice de memorias
- `project_pausaya.md` — contexto del proyecto PausaYa
- `reference_tools.md` — herramientas disponibles en el entorno
- `user_profile.md` — perfil del usuario

## Cómo restaurar esto en una PC nueva

1. Instalar Claude Code en la PC nueva.
2. Clonar este repo:
   ```
   gh repo clone kaelen-phoenix/ia-memory
   ```
3. Copiar los archivos `.md` (menos este README) a la carpeta de memoria de Claude Code para el working directory que uses. Si el working directory es `/home/dev` (igual que en el entorno original), la carpeta es:
   ```
   /root/.claude/projects/-home-dev/memory/
   ```
   Si el path de trabajo en la PC nueva es distinto, Claude Code genera esa carpeta la primera vez que le pidas que use memoria ahí — copiá los `.md` a esa carpeta equivalente.
   ```
   mkdir -p /root/.claude/projects/-home-dev/memory
   cp ~/ia-memory/*.md /root/.claude/projects/-home-dev/memory/
   rm /root/.claude/projects/-home-dev/memory/README.md 2>/dev/null
   ```

## Repos de trabajo a descargar (todos en GitHub, cuenta kaelen-phoenix)

Estos repos ya están en git y tienen remote en GitHub, así que se clonan directo:

```
gh repo clone kaelen-phoenix/ADHD-Regulator
gh repo clone kaelen-phoenix/claude
gh repo clone kaelen-phoenix/fluxa
gh repo clone kaelen-phoenix/ia-memory
```

> Nota: las carpetas `fake-hack`, `hola-mundo` y `varios` del entorno original **no están versionadas en git** y no se incluyen en esta migración.

## Requisitos previos en la PC nueva
- `gh` CLI instalado y autenticado (`gh auth login`) con la misma cuenta de GitHub.
- Git instalado.

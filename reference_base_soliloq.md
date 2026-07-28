---
name: reference-base-soliloq
description: Cómo conectarse a la base Postgres de Supabase del proyecto soliloq, y dónde vive la credencial
metadata:
  node_type: memory
  type: reference
---

## Consultar la base de soliloq

El procedimiento completo está en el propio repo, en
`soliloq/.claude/skills/consultar-base/SKILL.md`. Claude Code lo carga solo cuando se trabaja
en ese working directory, así que **no hace falta pedirlo**: alcanza con preguntar por datos
reales de la base.

Lo que importa recordar desde afuera del repo:

- La cadena de conexión vive en `~/.soliloq-deploy/db-url.txt`, **fuera de git**. Es lo único
  que hay que restaurar a mano en una PC nueva; se saca del dashboard de Supabase, en
  Project Settings → Database → Connection string (URI).
- **Nunca** copiar esa cadena a un archivo versionado. Este repo (`ia-memory`) es **público**,
  y `soliloq` también. Por eso acá no va ni el host, ni el id del proyecto, ni la contraseña.
- Requisito único: `npm i -g pg`. `psql` no está instalado y la CLI de Supabase no está
  autenticada contra la Management API, así que sólo sirven los comandos que aceptan
  `--db-url`.
- La conexión entra como superusuario `postgres` y **saltea RLS**. Sirve para saber si un dato
  existe, no para saber si alguien lo ve. Para eso hay que simular el JWT o ir por PostgREST.

Ver también [[project-soliloq]] si en algún momento se escribe el contexto del proyecto.

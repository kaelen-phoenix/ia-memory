---
name: reference-tools
description: Herramientas instaladas y disponibles en el entorno Android/Termux del usuario
metadata: 
  node_type: memory
  type: reference
  originSessionId: 90ccfbb8-db8f-4d61-807b-484845f75bdc
---

## Disponible en este entorno (proot-distro Debian en Android)

- `java` / `keytool` — OpenJDK 21 (instalado via `apt install default-jdk`)
- `gh` — GitHub CLI v2.93.0 (instalado via apt repo oficial de GitHub), autenticado como `kaelen-phoenix`
- `git` — disponible
- `curl` — disponible
- `python3` + `pip3` — Python 3.13 (PyNaCl NO funciona por conflicto con libs de Android)
- `apt` funciona como root; `pkg` NO funciona (falla con "Cannot run as root")

## Repositorio GitHub Actions
- Secrets ya configurados: `KEYSTORE_BASE64`, `STORE_PASSWORD`, `KEY_ALIAS`, `KEY_PASSWORD`
- Workflow en `.github/workflows/build.yml` compila AAB firmado en cada push a main

# Levelcast Plugin Store Index (public)

Índice público de la tienda de plugins. Los servidores Levelcast lo consumen
vía `PLUGIN_REGISTRY_URL=https://raw.githubusercontent.com/levelcast-app/plugins-registry/main/index.json`:

- `GET /api/v1/plugins/store` → pestaña Tienda en `/plugins`.
- Cron diario `pluginUpdateCheck` → pestaña Actualizaciones + aviso.

## Añadir / actualizar un plugin

1. Publicar el release en su repo (`plugin.tgz` + `plugin.tgz.sig` firmados).
2. Añadir/actualizar su entrada en `index.json`:
   `id`, `version`, `displayName`, `description`, `tarballUrl`, `signature`, `price`.
3. Commit a `main`. Sin CI: el core lee el raw de esta rama.

Solo referencias (URLs + firmas). El código vive en cada repo `levelcast-plugin-*`.

# Laboratorio de Deployment: GitHub Pages con GitHub Actions

Este repositorio implementa un pipeline de despliegue continuo (CD) hacia **GitHub Pages** utilizando **GitHub Actions** y **GitHub Environments**.

## Requisitos de la Tarea

1. **Crear un Environment `github-pages`**:
   - En GitHub, los environments permiten gestionar reglas de protección, secretos y registrar el historial de despliegues.
   - GitHub Pages crea y vincula automáticamente el environment `github-pages` al desplegar mediante GitHub Actions.
   - También puede preconfigurarse o revisarse en:
     `Settings` > `Environments` > `github-pages`.

2. **Crear un Pipeline de Deployment**:
   - Definido en [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml).
   - Utiliza las acciones oficiales de GitHub (`actions/configure-pages`, `actions/upload-pages-artifact` y `actions/deploy-pages`).
   - Apunta explícitamente al environment `github-pages`.
   - Se ejecuta automáticamente ante cada `push` a la rama `main` y de forma manual mediante `workflow_dispatch`.

3. **Ejecutar el Deployment**:
   - Para ejecutar el despliegue basta con subir el código a la rama `main` de GitHub (`git push origin main`) o activar el workflow manualmente en la pestaña **Actions**.

---

## Configuración previa en GitHub

Para que GitHub Pages admita despliegues desde GitHub Actions:
1. Dirígete a tu repositorio en GitHub: `https://github.com/FelipeMiranda1201/github_deployment`.
2. Ve a la pestaña **Settings** > **Pages** (en el menú lateral izquierdo).
3. En la sección **Build and deployment** > **Source**, selecciona:
   - **GitHub Actions**
4. Una vez guardado, cada ejecución del pipeline desplegará el contenido del sitio en la URL asignada a tu usuario/organización (por ejemplo: `https://felipemiranda1201.github.io/github_deployment/`).

# 📄 LaTeX Online Editor — Template

Editor de LaTeX online, gratuito y autoalojado en GitHub.
Cada fork es un entorno independiente con su propio compilador.

## ⚡ Cómo usar este template

### 1. Crear tu repo

Haz clic en **"Use this template"** (botón verde arriba) o:

```bash
gh repo create mi-latex --template <este-repo> --public
```

### 2. Activar GitHub Pages

En tu repo → **Settings → Pages → Source: GitHub Actions** (o branch `main`, carpeta `/web`).

> O simplemente abre `web/index.html` directamente en el navegador.

### 3. Generar un Personal Access Token

Ve a [github.com/settings/tokens](https://github.com/settings/tokens/new?scopes=repo,workflow) y crea un token con permisos:
- ✅ `repo` (leer y escribir archivos)
- ✅ `workflow` (lanzar GitHub Actions)

### 4. Conectar el editor

Abre el editor (GitHub Pages de tu repo), introduce:
- Tu **token** de GitHub
- Tu **repo** en formato `usuario/nombre-repo`

¡Listo! Ya puedes editar y compilar.

---

## 📁 Estructura del repo

```
├── .github/
│   └── workflows/
│       └── compile.yml     ← Compilador (tectonic vía GitHub Actions)
├── src/
│   └── main.tex            ← Tu documento LaTeX principal
├── out/
│   └── main.pdf            ← PDF generado (auto-actualizado)
└── web/
    └── index.html          ← Editor web (sirve desde GitHub Pages)
```

## 🔧 Personalizar

### Cambiar el compilador
El workflow usa [Tectonic](https://tectonic-typesetting.github.io/), que descarga automáticamente los paquetes necesarios. Si necesitas `pdflatex` o `xelatex` puedes cambiar la acción en `.github/workflows/compile.yml`.

### Múltiples archivos `.tex`
Añade tus archivos en `src/` e importalos desde `main.tex` con `\input{}`.

### Bibliografía
Coloca tu `.bib` en `src/` y usa `biber` o `bibtex` — Tectonic los procesa automáticamente.

---

## ⏱ Tiempos de compilación

| Documento          | Tiempo aprox. |
|--------------------|---------------|
| Simple (< 10 pág)  | 30–45 seg     |
| Con bibliografía   | 45–90 seg     |
| Complejo (> 50 pág)| 2–4 min       |

Los tiempos incluyen el tiempo de arranque del runner de GitHub Actions (~20 seg).

---

## 🛠 Tecnologías

- **Editor**: [Monaco Editor](https://microsoft.github.io/monaco-editor/) (el motor de VS Code)
- **Compilador**: [Tectonic](https://tectonic-typesetting.github.io/) vía GitHub Actions
- **Almacenamiento**: GitHub API (Content API + Actions API)
- **Preview**: PDF.js integrado en el navegador
- **Hosting**: GitHub Pages (gratuito)

---

## 📝 Licencia

MIT — úsalo, modifícalo y compártelo libremente.

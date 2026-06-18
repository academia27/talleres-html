# Academia Principia — Guía para publicar talleres

## Contexto
Los talleres son archivos HTML interactivos que se publican en GitHub Pages para que los estudiantes los abran directamente desde el navegador sin descargar nada.

- **Repositorio:** https://github.com/academia27/talleres-html
- **URL pública:** https://academia27.github.io/talleres-html/
- **Usuario GitHub:** academia27
- **Email:** gitarreivanaguilar@gmail.com
- **Carpeta local:** `C:\Users\ivana\OneDrive\Escritorio\talleres\talleres`

---

## Cómo montar un nuevo taller

Cuando la usuaria comparte un archivo HTML nuevo, seguir estos pasos en orden:

### 1. Guardar el archivo en la carpeta local
Colocar el archivo en `C:\Users\ivana\OneDrive\Escritorio\talleres\talleres\` con nombre limpio, sin espacios ni paréntesis. Usar el formato:
```
06_NombreTaller.html
07_NombreTaller.html
```

### 2. Actualizar el index.html
Agregar una tarjeta nueva al menú principal (`index.html`) con este bloque HTML dentro del `<div class="grid">`:
```html
<!-- Taller N -->
<a class="card" href="0N_NombreTaller.html" target="_blank">
  <div class="card-num">Taller 0N</div>
  <div class="card-icon">🔷</div>
  <div class="card-body">
    <div class="card-title">Nombre del Taller</div>
    <div class="card-desc">Descripción breve del taller.</div>
  </div>
</a>
```

### 3. Subir a GitHub con Git
Ejecutar en PowerShell desde la carpeta del proyecto:
```powershell
cd "C:\Users\ivana\OneDrive\Escritorio\talleres\talleres"
git add .
git commit -m "Agregar taller: NombreTaller"
git push origin main
```

> El credential helper ya está configurado. No hace falta token en cada push.
> Si el helper pide credenciales, el token se guarda en `~/.git-credentials`.

### 4. Esperar 1-2 minutos
GitHub Pages tarda un momento en publicar los cambios.

### 5. Entregar el link
```
https://academia27.github.io/talleres-html/0N_NombreTaller.html
```

---

## Links actuales (para compartir con estudiantes)

| # | Taller | Link |
|---|--------|------|
| — | Menú principal | https://academia27.github.io/talleres-html/ |
| — | Hoja de Ruta | https://academia27.github.io/talleres-html/Hoja%20de%20Ruta%20-%20Standalone.html |
| 01 | Operador Experto | https://academia27.github.io/talleres-html/01_TallerOperadorExperto.html |
| 02 | Portafolios Cripto | https://academia27.github.io/talleres-html/02_TallerPortafolios.html |
| 03 | TradingView | https://academia27.github.io/talleres-html/03_TallerTradingView.html |
| 04 | CeDeFi | https://academia27.github.io/talleres-html/04_TallerCeDeFi.html |
| 05 | CMC OnChain | https://academia27.github.io/talleres-html/05_CMCOnChain.html |

---

## Notas técnicas

- Git ya está inicializado en la carpeta local y conectado al repo remoto.
- El `credential.helper store` guarda las credenciales en `~/.git-credentials`.
- Si hay conflicto al hacer push (error "fetch first"), usar:
  ```powershell
  git pull origin main --allow-unrelated-histories --no-edit
  git push origin main
  ```
- Los archivos con espacios en el nombre se acceden con `%20` en la URL (ej: `Hoja%20de%20Ruta`). Mejor usar nombres sin espacios.

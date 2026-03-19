# PoC Autofill - Roadmap

## Almacenamiento
- Usar **SQLite** para persistir resultados de tests entre sesiones y navegadores.

---

## Orden de implementacion

### 1. Score de vulnerabilidad
- [ ] Resumen visual tipo "Tu navegador es vulnerable a X/9 tecnicas"
- [ ] Barra de progreso o gauge con color segun severidad
- [ ] Mostrar arriba de la tabla comparativa tras probar al menos 1 tecnica

### 2. Boton "Reset"
- [ ] Limpiar todos los resultados acumulados
- [ ] Resetear tabla comparativa y colores de tabs
- [ ] Resetear formulario activo

### 3. Mas tecnicas CSS
- [ ] `content-visibility: hidden`
- [ ] `contain: strict`
- [ ] `pointer-events: none` + `opacity: 0`
- [ ] Campo dentro de un `<details>` cerrado
- [ ] Evaluar otras tecnicas emergentes

### 4. Deteccion de extensiones / password managers
- [ ] Detectar si 1Password, Bitwarden, LastPass u otros estan activos
- [ ] Registrar si el comportamiento del autofill cambia con extension activa
- [ ] Mostrar en la tabla comparativa como columna adicional o nota

### 5. QR code
- [ ] Generar QR code con la URL del servidor local
- [ ] Mostrar en un modal o esquina para testear rapido en celulares
- [ ] Util para comparar navegadores moviles (Chrome Android, Safari iOS)

### 6. Recomendaciones al usuario
- [ ] Seccion final con tips de proteccion:
  - Desactivar autofill en el navegador
  - Usar extensiones de seguridad
  - Revisar permisos de autocompletado por sitio
  - No guardar tarjetas de credito en el navegador
- [ ] Mostrar recomendaciones personalizadas segun los resultados obtenidos

### 7. Modo presentacion
- [ ] Vista simplificada para charlas / workshops de seguridad
- [ ] Ocultar instrucciones y detalles tecnicos
- [ ] Tipografia mas grande, alto contraste
- [ ] Navegacion con flechas del teclado entre tecnicas

---

## Backlog (sin prioridad definida)

### Exportar resultados
- [ ] Exportar tabla comparativa como JSON
- [ ] Exportar como PNG/screenshot
- [ ] Exportar como CSV para analisis

### Vista "All-in-one"
- [ ] 9 formularios en grid para probar todos de una pasada
- [ ] Sin necesidad de cambiar tabs
- [ ] Resumen consolidado al final

### Historial entre navegadores (SQLite)
- [ ] Guardar cada test con: navegador, version, engine, plataforma, fecha, resultados
- [ ] Comparar lado a lado Chrome vs Firefox vs Brave vs Safari
- [ ] Visualizar tendencias entre versiones del mismo navegador

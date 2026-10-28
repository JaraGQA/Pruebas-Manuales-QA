# Portfolio de QA Testing: Gonzalo Jara

Proyectos de testing sobre la tienda online de Playmobil Argentina (https://tiendaplaymobil.com/), realizados durante mi formación en QA.
Incluye testing manual (proyecto final del curso de Coderhouse) y un primer acercamiento a pruebas HTTP con Postman.

Estoy en transición a QA tras años de experiencia en control de calidad textil: detección y clasificación de defectos por gravedad, búsqueda de causa raíz y documentación precisa. Busco mi primer rol como QA Tester junior.

## Estructura del repositorio

```
├── manual-testing/
│   ├── Jara_Gonzalo_-_Casos_de_prueba_-_Proyecto_Final.xlsx
│   ├── Gonzalo_Jara-_Reporte_de_bugs_-_Proyecto_Final_Testing.xlsx
│   └── Gonzalo_Jara_-_Reporte_de_pruebas_-_Proyecto_Final_Testing.pdf
├── api-testing/
│   └── api-testing-primer-acercamiento.pdf
└── README.md
```

---

## 1. Testing manual: Playmobil Argentina

Proyecto final del curso de QA Testing Manual (Coderhouse). Pruebas funcionales, de componentes y visuales sobre el sitio.

### Resumen
- **Casos de prueba ejecutados:** 10 (6 pasaron, 4 fallaron)
- **Defectos reportados:** 4
- **Tipos de prueba:** funcional, de componentes y visual
- **Casos positivos y negativos:** con datos válidos e inválidos

### Alcance
| Sección | Qué se probó |
|---|---|
| Registro / Login | Alta de cuenta con datos correctos, inicio de sesión con datos incorrectos, límite de caracteres en el campo usuario |
| Novedades | Filtros por precio (ascendente y rango fuera de límites) y orden alfabético |
| Combos | Agregar al carrito, links del footer (ubicación y contacto telefónico) |
| Inicio | Calidad de imágenes del slider |

### Defectos encontrados
| ID | Defecto | Tipo | Criticidad |
|---|---|---|---|
| 003 | El campo usuario del login no tiene límite de caracteres | Componente | Baja |
| 005 | El filtro "A-Z" ordena por número de artículo, no alfabéticamente | Componente | Baja |
| 009 | El ícono de contacto telefónico del footer abre la app de llamadas con un número incorrecto | Componente | Alta |
| 010 | Imágenes del slider de inicio con baja calidad (se notan píxeles) | Visual | Baja |

### Entornos de prueba
- Windows 10 LTSC 64 bits, Brave (Asus Zenbook 14)
- iOS 16.3, Brave (iPhone 12 Pro)
- Android 11, Brave (TCL 20 SE 5G)

### Archivos
- `Jara_Gonzalo_-_Casos_de_prueba_-_Proyecto_Final.xlsx`: casos de prueba con pasos, resultado esperado y obtenido.
- `Gonzalo_Jara-_Reporte_de_bugs_-_Proyecto_Final_Testing.xlsx`: reportes detallados de cada defecto (pasos para reproducir, resultado actual vs. esperado, entorno, evidencia).
- `Gonzalo_Jara_-_Reporte_de_pruebas_-_Proyecto_Final_Testing.pdf`: reporte final con métricas y conclusiones.

### Conclusión
No se encontraron defectos críticos para la compra: el carrito y los filtros de precio funcionan correctamente y el sitio se adapta bien a distintas resoluciones. El hallazgo más relevante fue en los canales de contacto con el cliente (número telefónico incorrecto en el footer).

---

## 2. Pruebas HTTP con Postman (primer acercamiento)

Mi primer contacto con Postman, realizado en enero de 2023, durante el mismo curso que el proyecto de testing manual y antes de tener formación formal en APIs.
Se publica **sin modificaciones**, como punto de partida de mi aprendizaje.

- **Documento:** `api-testing/api-testing-primer-acercamiento.pdf`
- **Alcance:** 5 requests GET sobre tiendaplaymobil.com (novedades, filtro por edades, seguimiento de envío y dos productos)
- **Resultados:** 4 respuestas 200 y 1 respuesta 404
- **Herramienta:** Postman

### Mirando este trabajo hoy
Con lo que sé ahora, identifico qué haría distinto:
- Las respuestas eran HTML, no JSON: probé páginas web, no una API propiamente dicha. Hoy buscaría endpoints reales con las DevTools del navegador (pestaña Network, filtro Fetch/XHR).
- No definí el resultado esperado antes de ejecutar cada request.
- La query 3 devolvió 404 sin sesión iniciada. Hoy confirmaría si ese comportamiento es un defecto o es lo esperado antes de marcarlo como fallo.
- Medí un tiempo de respuesta una sola vez. Hoy repetiría la medición y definiría un umbral.
- Validé los resultados a ojo; hoy los automatizaría con tests en Postman.

### Próximos pasos
- [ ] Completar curso de Postman / APIs
- [ ] Probar endpoints que devuelvan JSON y validar sus campos
- [ ] Escribir tests automatizados y exportar la colección a este repositorio

---

## Notas
- El sitio fue testeado en 2023 y puede haber cambiado desde entonces.
- Algunos links de evidencia (capturas en Dropbox) pueden no estar disponibles.

## Contacto
Gonzalo Jara · [LinkedIn](https://www.linkedin.com/in/gonmajara/)


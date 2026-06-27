# Skill: Gestionar días del itinerario España 2026

Este skill agrega o elimina días en `/Users/davidosorio/ClaudeCode/Aplicaciones/espana-travel/index.html`.

## Contexto del proyecto
- PWA de viaje España 2026 (Dave, Kelly, Jacobo) — 28 jun al 16 jul
- Archivo único: `index.html` con todo el HTML/CSS/JS
- Los días viven en dos arrays JavaScript: `ITINERARIO` y `GASTOS_BASE`

## Estructura de un día en ITINERARIO
```js
{
  dia: 20,                        // número de día (siguiente al último)
  fecha: 'Vie 17 jul',            // formato: 'Día DD mes'
  ciudad: 'Barcelona',            // ciudad principal
  titulo: 'Día libre en Barcelona',
  desc: 'Descripción breve del día.',
  viaje: 'AVE Barcelona → Madrid 14:00' // opcional — omitir si no hay viaje
}
```

## Estructura de gastos en GASTOS_BASE
```js
{ dia: 20, nombre: 'Almuerzo', categoria: 'Comida', valor: 40, moneda: 'EUR' },
{ dia: 20, nombre: 'Hotel', categoria: 'Alojamiento', valor: 120, moneda: 'EUR' },
```

## Categorías válidas
`Vuelo`, `Transporte`, `Alojamiento`, `Comida`, `Actividad`, `Compras`, `Seguro`, `Varios`

## Monedas válidas
`EUR`, `USD`

## Instrucciones según el argumento recibido

### Si el argumento es "agregar" o no se especifica:
1. Pregunta al usuario: número de día, fecha, ciudad, título, descripción, si hay viaje (y cuál), y lista de gastos con nombre/categoría/valor/moneda.
2. Lee el archivo para encontrar el último día en ITINERARIO y el último gasto en GASTOS_BASE.
3. Inserta la nueva entrada al final de `ITINERARIO` (antes del `];`) y los nuevos gastos al final de `GASTOS_BASE` (antes del `];`).
4. Confirma con el número de día y total de gastos agregados.

### Si el argumento es "eliminar":
1. Pregunta qué número de día eliminar.
2. Lee el archivo, muestra los datos de ese día (título, gastos) y pide confirmación.
3. Elimina la entrada de `ITINERARIO` y todos los gastos de `GASTOS_BASE` con ese `dia`.
4. Confirma cuántos gastos fueron eliminados.

### Si el argumento es "listar":
1. Lee el archivo y muestra todos los días con: número, fecha, ciudad, total de gastos EUR y USD.

## Importante
- Preserva el formato y la indentación existente.
- No modifiques ningún otro array ni función.
- Después de editar, indica al usuario que recargue la PWA.

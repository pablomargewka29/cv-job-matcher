# CV Job Matcher

Workflow de [n8n](https://n8n.io/) que evalúa ofertas laborales contra un CV personal usando IA, asigna un puntaje de match y notifica vía mail las mejores oportunidades.

Funciona junto con [hiring-room-scraper](#) (scraper en Python) como sistema completo de búsqueda laboral automatizada.

## Qué hace

1. Toma como input un Excel de ofertas laborales (generado por el scraper).
2. Por cada oferta, le pasa a la IA el CV del usuario + la oferta y le pide un puntaje de match (1-10) con justificación.
3. Filtra las ofertas que superan un umbral configurable.
4. Manda un mail al usuario con las mejores oportunidades y el detalle de por qué matchean.

## Stack

- n8n (self-hosted o cloud)
- Modelo de IA vía API (compatible con OpenAI / Anthropic / Gemini)
- Gmail / SMTP para notificaciones

## Cómo importarlo

1. Abrí n8n.
2. **Workflows → Import from File** → seleccioná `workflow.json`.
3. Configurá las credenciales:
   - API del modelo de IA.
   - Cuenta de mail para enviar notificaciones.
4. Subí tu CV (PDF o texto) en el nodo de input.
5. Ejecutá manualmente o programá un trigger.

## Configuración

En el workflow podés ajustar:

- **Umbral de match**: puntaje mínimo para considerar una oferta relevante (por defecto: 7/10).
- **Mail de destino**: dónde recibir las notificaciones.
- **Prompt de evaluación**: criterios que la IA usa para puntuar (por ejemplo, peso de habilidades técnicas vs experiencia).

## Notas

- El JSON exportado no incluye credenciales — hay que reconfigurarlas al importar.
- El costo por corrida depende del modelo de IA y la cantidad de ofertas evaluadas.

---

Creado por [Pablo Margewka](https://www.linkedin.com/in/<tu-perfil>).

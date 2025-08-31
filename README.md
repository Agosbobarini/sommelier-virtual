#  Sommelier Virtual: experiencias de cata guiada personalizadas con IA  

## Introducción  

### Nombre del proyecto  
**Sommelier Virtual: experiencias de cata guiada personalizadas con IA**  

### Problema a abordar  
Las catas de vino hogareñas o íntimas suelen enfrentar limitaciones:  
- Falta de **personalización** según el grupo de asistentes.  
- Escasa **visualidad atractiva** que acompañe la experiencia.  
- Dificultad para transmitir **narrativas y curiosidades** de manera ágil.  
- Limitaciones para **replicar y escalar** experiencias con la misma calidad.  

### Propuesta de solución  
Un **Sommelier Virtual** basado en *Prompt Engineering* que:  
- Recomiende vinos y maridajes adaptados a cada grupo.  
- Genere **guiones de cata** ajustados al nivel del público.  
- Cree **recursos visuales** (fichas sensoriales, mapas, ilustraciones).  
- Compile resúmenes y sugerencias post-evento.  

 Se utilizan técnicas de **Fast Prompting** (role prompting, few-shot, encadenamiento) para optimizar el flujo de interacción y reducir consultas innecesarias a la API.  

### Justificación de viabilidad  
- **Técnica:** viable con ChatGPT y generadores de imagen (DALL·E, NightCafe, Leonardo AI).  
- **Recursos:** conocimiento en catas, catálogos de bodegas, material visual.  
- **Tiempo:** 4 semanas → diseño, prueba, refinamiento, entrega final.  
- **Impacto:** experiencias más personalizadas, inmersivas y memorables.  

---

##  Objetivos  
- Diseñar un **Sommelier Virtual** que mejore catas hogareñas y privadas.  
- Aplicar **Fast Prompting** para optimizar generación de recomendaciones y materiales.  
- Integrar prompts de texto e imagen en un flujo coherente.  
- Desarrollar una **POC en Jupyter Notebook**.  

---

##  Metodología  
1. Definir escenarios: antes, durante y después de la cata.  
2. Diseñar prompts base para cada etapa.  
3. Aplicar **Fast Prompting**:  
   - *Role prompting*: “Actúa como un sommelier experto en vinos argentinos…”  
   - *Few-shot prompting*: ejemplos de descripciones adaptadas a principiantes/avanzados.  
   - *Encadenamiento*: unir recomendaciones, guión y visualización en un solo flujo.  
4. Implementar una POC en Jupyter Notebook.  
5. Probar y ajustar con distintos escenarios.  

---

##  Herramientas y tecnologías  
- **Texto-texto:** ChatGPT (recomendaciones, guiones, narrativa).  
- **Texto-imagen:** DALL·E / NightCafe (fichas sensoriales, ilustraciones).  
- **Fast Prompting:** role prompting, few-shot, encadenamiento.  
- **Entorno:** Jupyter Notebook en Visual Studio Code.  

---

##  Implementación  

La POC está disponible en:  
 `notebooks/Sommelier_Virtual_FastPrompting_POC.ipynb`  

Ejemplo de flujo de prompts:  

```python
# Prompt 1: recomendación de vinos
prompt_recomendacion = f"""
Actúa como un sommelier experto en vinos argentinos.
Tengo una cata para 6 personas, principiantes, con un menú de carnes rojas.
Sugiere 3 vinos tintos argentinos con breve descripción de notas de cata y rango de precio accesible.
"""

# Prompt 2: guión de cata encadenado
prompt_guion = f"""
A partir de la recomendación previa, genera un guión breve de cata que incluya:
- Introducción amigable para principiantes
- Descripción sensorial de cada vino
- Preguntas disparadoras para los invitados
"""

# Prompt 3: visualización (texto → imagen)
prompt_imagen = """
Ilustra un set minimalista de tres copas de vino tinto con notas sensoriales flotando
(frutas rojas, especias, madera), estilo line art en color borgoña profundo (#6B0F1A).
"""

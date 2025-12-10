# Workflow UGC Mock - n8n

Workflow-ul generează un videoclip mock care simulează un clip UGC promoțional. În exemplul nostru: 

- Produsul promovat este un **sneakers alb sport**.  
- Prezentatorul este un tânăr fictiv, **Andrei**, 20–30 ani, activ și interesat de produs.  
- Scriptul este generat automat pe baza obiectului și a persona, de exemplu: „Salut! Sunt Andrei, am 20–30 de ani și caut sneakers albi sport. Acești pantofi sunt perfecți pentru un stil modern și activ.”  
- Workflow-ul returnează un **URL mock de video** și un JSON cu toate datele, simulând logica prezentată în videoclipurile originale.  


---

## Noduri folosite

1. **Manual Trigger**  
   - Punctul de start al workflow-ului. Permite rularea manuală pentru test.

2. **Function (AI Vision Mock)**  
   - Simulează un API de recunoaștere a obiectelor și stilului.  
   - Exemplu de output:

```json
{
  "detected_object": "sneakers albi sport",
  "style": "modern, urban",
  "target_audience": "tineri activi"
}
```
Function (Generate Persona)

Creează un persona fictiv folosind datele de la AI Vision Mock.

Output: nume, vârstă, interese și referință la datele vizuale.

Function (Generate Script)

Generează un scurt script text bazat pe persona și obiectul detectat.

Output: short_script + referințe la persona și vision.

Function (Generate Video URL)

Mock pentru generarea unui URL de videoclip.

Output: link video fictiv + metadatele primite.

Function (Output Result)

Agregă toate datele finale într-un singur JSON pentru ieșire.

Output: success, video_url, created_at, details.

Structura workflow-ului
```txt
[Manual Trigger]
       ↓
[AI Vision Mock]
       ↓
[Generate Persona]
       ↓
[Generate Script]
       ↓
[Generate Video URL]
       ↓
[Output Result]
```

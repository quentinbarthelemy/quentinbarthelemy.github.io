---
layout: page
permalink: /teaching/
title: Enseignement
description:
nav: true
nav_order: 1
calendar: true
---

### Devoirs  

**Pour le lundi 21/9 :**  
- *EPS :* Répondre à la question : *Comment améliorer ma performance en course de durée ?*  
- *Grammaire et orthographe grammaticale (GRAM) :* Apprendre la leçon sur les groupes dans la phrase.  

**Pour le mardi 22/9 :**  
- Préparer la dictée flash 3.  
- *Procédures de calcul mental (PCM) :* Apprendre la leçon sur ajouter ou soustraire 8, 9, 18, 19, 28, 29, 38, 39.  

**Pour le jeudi 24/9 :**  
- Corriger la dictée flash 3 pour préparer la dictée bilan 3.  

### Scores des maisons
<!-- Style des sabliers Harry Potter -->
<style>
  .hp-compteurs-container {
    display: flex;
    justify-content: center;
    align-items: flex-end;
    gap: 30px;
    margin: 40px auto;
    font-family: 'Georgia', serif;
    flex-wrap: wrap;
  }

  .hp-maison {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 110px;
  }

  .hp-nom-maison {
    font-weight: bold;
    font-size: 1.1rem;
    margin-bottom: 12px;
    color: #333;
    text-align: center;
  }

  /* Structure du sablier / tube de verre */
  .hp-sablier {
    position: relative;
    width: 65px;
    height: 220px;
    background: rgba(255, 255, 255, 0.2);
    border: 4px solid #4a3b2c; /* Cadre en bois/laiton */
    border-radius: 30px;
    box-shadow: inset 0 0 10px rgba(0,0,0,0.3), 0 4px 10px rgba(0,0,0,0.15);
    overflow: hidden;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
  }

  /* Support supérieur et inférieur */
  .hp-sablier::before, .hp-sablier::after {
    content: '';
    position: absolute;
    left: -8px;
    width: 81px;
    height: 12px;
    background: #3a2b1c;
    border-radius: 4px;
    z-index: 2;
  }
  .hp-sablier::before { top: -2px; }
  .hp-sablier::after { bottom: -2px; }

  /* Effet de reflet de verre */
  .hp-sablier-verre {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(115deg, rgba(255,255,255,0.4) 0%, rgba(255,255,255,0) 40%, rgba(255,255,255,0.1) 100%);
    z-index: 3;
    pointer-events: none;
  }

  /* Remplissage de gemmes/sable */
  .hp-gemmes {
    width: 100%;
    height: 0%; /* Animé par le script */
    transition: height 1.5s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative;
    box-shadow: 0 -2px 8px rgba(0,0,0,0.2);
  }

  /* Couleurs des maisons */
  .maison-1 .hp-gemmes {
    background: linear-gradient(180deg, #ff6b6b, #c0392b); /* Rouge (ex: Gryffondor) */
  }
  .maison-2 .hp-gemmes {
    background: linear-gradient(180deg, #2ecc71, #27ae60); /* Vert (ex: Serpentard) */
  }
  .maison-3 .hp-gemmes {
    background: linear-gradient(180deg, #48dbfb, #2980b9); /* Bleu (ex: Serdaigle) */
  }

  /* Score numérique sous le sablier */
  .hp-score {
    margin-top: 12px;
    font-size: 1.2rem;
    font-weight: bold;
    color: #2c3e50;
    background: #f8f9fa;
    padding: 4px 12px;
    border-radius: 15px;
    border: 1px solid #ddd;
  }
</style>

<!-- Structure HTML des 3 sabliers -->
<div class="hp-compteurs-container">
  
  <!-- Maison 1 -->
  <div class="hp-maison maison-1">
    <div class="hp-nom-maison">Phénix</div>
    <div class="hp-sablier">
      <div class="hp-sablier-verre"></div>
      <div class="hp-gemmes" id="gemmes-m1"></div>
    </div>
    <div class="hp-score" id="score-m1">0 pts</div>
  </div>

  <!-- Maison 2 -->
  <div class="hp-maison maison-2">
    <div class="hp-nom-maison">Pégase</div>
    <div class="hp-sablier">
      <div class="hp-sablier-verre"></div>
      <div class="hp-gemmes" id="gemmes-m2"></div>
    </div>
    <div class="hp-score" id="score-m2">0 pts</div>
  </div>

  <!-- Maison 3 -->
  <div class="hp-maison maison-3">
    <div class="hp-nom-maison">Sphinx</div>
    <div class="hp-sablier">
      <div class="hp-sablier-verre"></div>
      <div class="hp-gemmes" id="gemmes-m3"></div>
    </div>
    <div class="hp-score" id="score-m3">0 pts</div>
  </div>

</div>

<!-- Script de mise à jour des scores -->
<script>
  // 1. DÉFINISSEZ VOS SCORES ET LE SCORE MAXIMUM ICI :
  const maxPoints = 100; // Le score qui remplit le sablier à 100%
  
  const scores = {
    m1: 24, // Score Maison 1
    m2: 24,  // Score Maison 2
    m3: 24  // Score Maison 3
  };

  // 2. Application dynamique avec animation
  function mettreAJourSabliers() {
    for (let m in scores) {
      let score = scores[m];
      let pourcentage = Math.min(Math.max((score / maxPoints) * 100, 0), 100);
      
      document.getElementById(`gemmes-${m}`).style.height = pourcentage + '%';
      document.getElementById(`score-${m}`).innerText = score + ' pts';
    }
  }

  // Lancement après le chargement du DOM
  document.addEventListener('DOMContentLoaded', mettreAJourSabliers);
</script>

### Emploi du temps en période 1  
{% include figure.liquid loading="eager" path="assets/img/edt.jpg" class="img-fluid rounded z-depth-1" %}  

<!-- {% include calendar.liquid calendar_id='test@gmail.com' timezone='Asia/Shanghai' %} -->

<!-- {% include courses.liquid %} -->

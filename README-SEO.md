# README SEO — PronoEuroX (à l'attention de Zine)

> Ce document liste toutes les actions SEO à exécuter après la mise en ligne du site vitrine https://pronoeurox.github.io et de la vidéo YouTube TTS FR.
> Toutes les étapes sont découpées en sous-actions concrètes, durées estimées et outils gratuits.
> Pré-requis : être connecté au compte Google (`pronoeurox.stats@proton.me` ou équivalent Google), au compte Bing Webmaster, et disposer d'un accès admin sur le repo GitHub `pronoeurox.github.io`.

---

## 1. Soumettre le sitemap à Google Search Console

### Préparation

- URL du sitemap : `https://pronoeurox.github.io/sitemap.xml`
- URL du robots.txt : `https://pronoeurox.github.io/robots.txt`

### Étapes exactes

1. Aller sur **https://search.google.com/search-console/** et se connecter avec un compte Google.
2. Cliquer sur **« Ajouter une propriété »** → choisir **« Préfixe d'URL »** → saisir `https://pronoeurox.github.io/` → **Continuer**.
3. Vérification : cocher **« Balise HTML »** (méthode la plus simple pour GitHub Pages).
4. GitHub → repo `pronoeurox.github.io` → fichier `index.html` → ajouter dans `<head>` la balise :
   ```html
   <meta name="google-site-verification" content="CODE_DONNE_PAR_GSC" />
   ```
5. Revenir sur GSC → cliquer **« Vérifier »**. Validation sous 1 min.
6. Menu gauche → **« Sitemaps »** → champ **« Ajouter un sitemap »** → saisir `sitemap.xml` → **Envoyer**.
7. Statut attendu : `Réussite` sous 24-48 h. Si erreur 404, attendre 24 h que GitHub Pages propage le sitemap.

### Suivi

- **Indexation > Pages** : voir quelles URLs sont indexées, demander une indexation manuelle pour les 3 vitrines FR/EN/ES.
- **Expérience > Pages principales (Core Web Vitals)** : surveiller LCP < 2,5 s, CLS < 0,1, INP < 200 ms.

---

## 2. Soumettre le sitemap à Bing Webmaster Tools

### Pourquoi

Bing représente ~10 % du trafic FR mais alimente DuckDuckGo et la plupart des assistants vocaux (Cortana, Alexa via Bing). Indispensable pour capter les recherches conversationnelles 2026.

### Étapes exactes

1. Aller sur **https://www.bing.com/webmasters** et se connecter avec un compte Microsoft.
2. **« Ajouter un site »** → saisir `https://pronoeurox.github.io/` → **Ajouter**.
3. Vérification : **« Balise Meta »** recommandée. Ajouter dans `<head>` du `index.html` :
   ```html
   <meta name="msvalidate.01" content="CODE_BING" />
   ```
4. **« Sitemaps »** → **« Envoyer un sitemap »** → `https://pronoeurox.github.io/sitemap.xml` → **Envoyer**.

### Bonus : indexation rapide

- **« Soumettre des URL »** → saisir manuellement les 3 vitrines FR/EN/ES pour accélérer l'indexation initiale (jusqu'à 10 URLs/jour).

---

## 3. Vérifier l'indexation des 3 vitrines

### Test direct

Dans Google, saisir :
```
site:pronoeurox.github.io
```

Résultat attendu : 3 à 5 URLs indexées (les 3 vitrines + éventuellement `faq.html` + `installation.html`).

### Test par langue

```
site:pronoeurox.github.io inurl:en
site:pronoeurox.github.io inurl:es
```

### Si non indexé après 7 jours

- Aller dans GSC → **« Inspection de l'URL »** → coller `https://pronoeurox.github.io/en/` → **« Demander une indexation »**.
- Idem pour `/es/`, `/faq.html`, `/installation.html`.
- Vérifier que les balises `<link rel="alternate" hreflang="...">` sont bien présentes dans le `<head>` de chaque version (déjà OK sur `index.html`).

---

## 4. Uploader la vidéo YouTube (titre/description/tags/sous-titres)

### Fichier source

Toutes les métadonnées sont prêtes dans `script-youtube-FR-SEO.md` (titre §1, description §2, tags §3, miniature §4, sous-titres §7, commentaire épinglé §8).

### Étapes d'upload

1. Aller sur **https://studio.youtube.com/** → bouton **« Créer »** → **« Importer des vidéos »**.
2. Sélectionner le fichier `.mp4` (1920×1080, H.264, < 8 min 30 s, < 2 Go).
3. **Détails** :
   - **Titre** : copier-coller depuis §1 (66 caractères).
   - **Description** : copier-coller depuis §2 (intégralité).
   - **Miniature** : uploader le PNG 1280×720 créé selon §4.
   - **Playlist** : créer une playlist « Statistiques Euromillions » et y ajouter la vidéo.
   - **Langue** : Français (France).
   - **Catégorie** : `Éducation` (recommandé) ou `Science & Technology`.
   - **Public** : ⚠️ mettre **« Non répertoriée »** pour le premier test → vérifier rendu, miniature, sous-titres → puis basculer sur **« Publique »**.
4. **Sous-titres** : attendre la fin de l'upload → menu gauche **« Sous-titres »** → **« Ajouter une langue »** → **Français** → **« Importer un fichier »** → choisir `.srt` → **Publier**.
5. **Tags** : dans le champ **« Tags »** (en haut de l'écran Détails), copier-coller les tags de §3 (489 caractères).
6. **Publier** (après bascule de visibilité).

### Actions post-upload (dans les 5 minutes)

- Poster immédiatement le **commentaire épinglé** de §8 (texte verbatim).
- Cliquer sur les 3 points du commentaire → **« Épingler »**.
- Partager le lien sur Bluesky / Reddit (compte préchauffé ≥ 30 jours) / Developpez.net.

---

## 5. Backlinks à obtenir en priorité

Les backlinks sont le facteur de classement #1 pour les requêtes concurrentielles 2026. Voici la liste priorisée, du plus fort impact au plus opportuniste.

### Priorité 1 (fort impact, à exécuter en premier)

| Source | Type | Effort | Délai |
|--------|------|--------|-------|
| Reddit r/dataisbeautiful | Post heatmap OC | 2 h | S+5 (après préchauffage 30 j) |
| Hacker News Show HN | Post + commentaire | 1 h | S+9 |
| r/SideProject + r/frenchtech | Post format « I built X » | 2 h | S+12 |
| Developpez.net forum Projets | Post technique | 1 h | S+6 |
| Reddit r/france (compte 30+ j) | Data drop + commentaire LS 30 min après | 1 h | S+7 |

### Priorité 2 (impact moyen)

| Source | Type | Effort | Délai |
|--------|------|--------|-------|
| Bluesky thread FR | 5 posts | 1 h | S+8 |
| JVC topic Euromillions | Post conversationnel | 1 h | S+16 (compte 6+ mois obligatoire) |
| Substack | Newsletter hebdo tirages | 2 h/sem | Continu |
| Product Hunt | Lancement coordonné | 4 h | S+10 |

### Priorité 3 (ES / international)

| Source | Type | Effort |
|--------|------|--------|
| ForoCoches (ES) | Topic análisis estadístico Euromillones | 1 h |
| Foro de Euromillones (ES) | Post technique data | 1 h |
| Reddit r/spain | Data drop ES | 1 h |
| Xataka (ES) — si contact | Pitch journaliste tech | 2 h |

### Backlinks spontanés (à surveiller)

- Citations Hacker News / Reddit → deviennent backlinks si profil public PronoEuroX stable.
- Re-posts Medium / Dev.to de l'article SEO (canonical vers vitrine).
- Forks GitHub du repo → backlink automatique dans GitHub Insights.

---

## 6. Requêtes Google à monitorer (top 5 target)

### France (FR)

```
1. logiciel statistiques euromillions
2. logiciel euromillions
3. analyse statistique euromillions
4. application euromillions
5. logiciel fdj euromillions
```

### International (EN/ES)

```
6. euromillions statistics software
7. euromillions analyzer
8. software análisis euromillones
9. estadísticas euromillones
10. loteria euromillones programa
```

### Longue traîne (moins concurrentiel, conversion plus haute)

```
11. fréquence numéros euromillions depuis 2004
12. logiciel réduire combinaisons euromillions
13. numéros chauds euromillions analyse
14. heatmap tirages euromillions
15. écart-type numéros euromillions
```

### Comment monitorer

- Google Search Console → **« Performances »** → ajouter les 15 requêtes ci-dessus dans les filtres.
- Bing Webmaster → **« Performances de recherche »** → idem.
- Ubersuggest gratuit (https://neilpatel.com/ubersuggest/) → checker la position FR quotidienne.

---

## 7. Outils gratuits de suivi de position

### Indispensables (gratuits)

| Outil | Usage | URL |
|-------|-------|-----|
| **Google Search Console** | Indexation, requêtes, CTR, position moyenne | https://search.google.com/search-console/ |
| **Bing Webmaster Tools** | Idem côté Bing + indexation rapide | https://www.bing.com/webmasters |
| **Google Analytics 4** | Trafic, sources, conversions LS | https://analytics.google.com/ |
| **Ubersuggest Free** | Suivi de position quotidien (3 requêtes/jour gratuites) | https://neilpatel.com/ubersuggest/ |
| **Google PageSpeed Insights** | Core Web Vitals | https://pagespeed.web.dev/ |
| **Pangram** | Détection IA du texte publié | https://www.pangram.com/ |

### Bonus (optionnels mais utiles)

| Outil | Usage | URL |
|-------|-------|-----|
| **Ahrefs Webmaster Tools** (gratuit pour le propriétaire) | Backlinks, mots-clés, audit technique | https://ahrefs.com/webmaster-tools |
| **Google Trends** | Tendance des requêtes (saisonnalité Euromillions) | https://trends.google.com/ |
| **AnswerThePublic** | Idées de mots-clés longue traîne | https://answerthepublic.com/ |
| **Screaming Frog SEO Spider** (gratuit < 500 URLs) | Audit technique on-page | https://www.screamingfrog.co.uk/seo-spider/ |
| **Schema Markup Validator** | Validation des balises JSON-LD | https://validator.schema.org/ |

### Fréquence de monitoring recommandée

- **Quotidien** : GSC + Bing (vérification des erreurs).
- **Hebdomadaire** : Ubersuggest (positions), Ahrefs (backlinks), Analytics (trafic).
- **Mensuel** : PageSpeed, Schema Validator, audit Screaming Frog.

---

## 8. Estimation du temps pour ranker top 5

### Scénario optimiste (backlinks OK dès S+6)

| Requête | Position initiale | Top 5 estimé | Commentaire |
|---------|-------------------|--------------|-------------|
| `logiciel statistiques euromillions` | >100 | **2-3 mois** | Concurrence faible, niche précise |
| `logiciel euromillions` | >100 | **1-3 mois** | Très faible concurrence 2026 |
| `analyse statistique euromillions` | >100 | **2-3 mois** | Mots-clés longue traîne faciles |
| `application euromillions` | >100 | **1-2 mois** | Très peu de résultats FR qualifiés |
| `logiciel fdj euromillions` | >100 | **2-4 mois** | Concurrence FDJ + sites de prédiction |

### Scénario pessimiste (peu de backlinks)

| Requête | Top 5 estimé | Commentaire |
|---------|--------------|-------------|
| `logiciel statistiques euromillions` | **6-12 mois** | Sans backlinks, progression lente |
| `logiciel euromillions` | **6-12 mois** | Idem |

### Facteurs accélérateurs

- ✅ Backlinks depuis Hacker News, Reddit r/dataisbeautiful, Developpez.net → boost x3 sur la vitesse de ranking.
- ✅ Vidéo YouTube indexée par Google Vidéo → trafic dès S+1 sur les requêtes informationnelles.
- ✅ Article SEO Medium + Dev.to cross-posté avec canonical vers vitrine → autorité thématique renforcée.
- ✅ Balisage FAQPage JSON-LD (déjà présent sur `index.html`) → featured snippets probables sur les requêtes « comment… ».

### KPIs à surveiller

- **Mois 1** : 0 à 5 clics/jour GSC, position moyenne > 50.
- **Mois 2-3** : 5 à 30 clics/jour, position moyenne 20-50.
- **Mois 3-6** : 30 à 150 clics/jour, position moyenne 5-20.
- **Mois 6-12** : 150+ clics/jour, position moyenne top 10 sur 5+ requêtes.

---

## 9. Actions SEO récurrentes (to-do mensuel)

- [ ] **M+1** : Soumettre le sitemap à GSC + Bing (cf. §1, §2).
- [ ] **M+1** : Uploader vidéo YouTube avec métadonnées optimisées (cf. §4).
- [ ] **M+1** : Publier post Reddit r/dataisbeautiful avec heatmap.
- [ ] **M+2** : Publier post Hacker News Show HN.
- [ ] **M+2** : Publier post Developpez.net forum Projets.
- [ ] **M+2** : Cross-poster l'article SEO Medium + Dev.to avec canonical.
- [ ] **M+3** : Premier post-mortem Indie Hackers (M+1 chiffres de vente).
- [ ] **M+3** : Vérifier positions Ubersuggest → ajuster contenu vitrine si besoin.
- [ ] **M+4** : Lancement Product Hunt coordonné.
- [ ] **M+6** : Audit Screaming Frog complet + corrections techniques.
- [ ] **M+6** : JVC topic Euromillions (compte préchauffé 6+ mois).
- [ ] **Continu** : Newsletter Substack hebdo sur les tirages.

---

## 10. Risques et pièges à éviter

- ❌ **Keyword stuffing** dans la description YouTube → Google pénalise depuis Hummingbird (2013) + Helpful Content Update (2024).
- ❌ **Achats de backlinks** Fiverr/BlackHat → pénalité Penguin algorithmique.
- ❌ **Contenu dupliqué** entre les 3 vitrines FR/EN/ES → utiliser `hreflang` correctement (déjà OK) + canonical unique.
- ❌ **Redirections multiples** sur GitHub Pages → éviter les 301 en chaîne, garder une structure plate `/`, `/en/`, `/es/`.
- ❌ **Vidéo YouTube bloquée SmartScreen** : ne pas faire de pub pour SmartScreen dans la vidéo, juste informer en description.
- ❌ **Trop d'affiliation** : la description YouTube ne doit pas contenir d'autres liens commerciaux que LS.
- ❌ **Anonymat cassé** : aucun backlink depuis un profil Google personnel, aucun nom dans les screenshots YouTube.

---

*Fin du README SEO — à exécuter dans l'ordre, sans brûler les étapes. Pré-chauffage d'abord, contenu ensuite, backlinks en S+5 minimum.*

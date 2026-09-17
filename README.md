# BubiMate

Un assistant de terrain PWA pour les représentants commerciaux en Haute-Garonne.

## Caractéristiques

- **Suivi des visites** - Enregistrez vos arrivées et départs chez les clients
- **Gestion des actions** - Créez des commandes, prospects, relances et tâches
- **Suivi du kilométrage** - Tracez votre consommation kilométrique quotidienne
- **Rappels iOS** - Intégration automatique avec l'app Rappels d'iOS
- **Historique complet** - Consultez toutes vos visites et actions précédentes
- **Calendrier** - Vue mensuelle de vos rendez-vous programmés
- **Mode hors ligne** - Fonctionne entièrement sans connexion grâce à IndexedDB

## Installation

1. Clonez ce repository
2. Ouvrez `index.html` dans un navigateur web
3. Sur iOS, ajoutez à l'écran d'accueil pour une expérience PWA complète

## Structure du projet

- `index.html` - Application complète (HTML + CSS + JavaScript)
- `sw.js` - Service Worker pour le fonctionnement hors ligne
- `manifest.webmanifest` - Métadonnées PWA

## Architecture

### Stockage

L'application utilise **IndexedDB** pour la persistance des données :
- **visites** - Enregistrement des arrivées/départs chez les clients
- **actions** - Tâches, commandes, prospects, relances
- **km** - Kilométrage quotidien

### Service Worker

Stratégie **network-first** avec fallback cache :
1. Tente de charger les ressources du réseau
2. Si échec, utilise la version en cache

## Utilisation

### Lors d'une visite

1. Accédez à l'onglet "Visite"
2. Sélectionnez le client depuis le calendrier (3 semaines de planning intégré)
3. Cliquez sur "Arriver" et "Départ" pour enregistrer vos horaires
4. Ajoutez des actions (commandes, prospects, etc.)
   - Les **commandes** sont créées automatiquement quand vous les sélectionnez
   - Les autres types demandent confirmation avant sauvegarde

### Rappels iOS

Quand vous créez une action avec une date future, l'app propose de générer un rappel iOS :
- Un fichier `.ics` (iCalendar) est créé
- iOS l'ouvre automatiquement dans l'app Rappels
- Le rappel apparaît sur tous vos appareils Apple

### Récapitulatif du jour

Sur l'écran d'accueil :
- Widget "Km" - Affiche le kilométrage total du jour
- Widget "Récap" - Affiche un résumé de toutes vos activités pour copie/collage dans votre CRM

## Planning intégré

Le planning est basé sur des cycles de 3 semaines (S1, S2, S3) commençant le 14 septembre 2026.

Modifiez le planning dans la variable `PLAN` du JavaScript selon vos besoins.

## Développement

### Améliorations potentielles

- [ ] Synchronisation cloud (Firebase, Supabase)
- [ ] Export des données en CSV/Excel
- [ ] Notifications push intelligentes
- [ ] Geolocalisation des visites
- [ ] Analyse des performances par client/zone
- [ ] Intégration CRM (Salesforce, HubSpot)
- [ ] Mode sombre amélioré
- [ ] Multilangue

### Code quality

- Pas de frameworks externes (vanilla JS)
- Responsive design avec Apple System Font
- Conforme WCAG 2.1 AA
- Testé sur iOS 14+ et Android 8+

## License

BubiMate est développé pour usage interne.

---

**BubiMate** v1.0 - Pour les représentants BubiMex en Southwest France

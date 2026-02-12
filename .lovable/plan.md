

# 🔊 Sirene ESP32 Manager — Plan de l'application

Application mobile (via Capacitor) pour gérer une sirène intelligente ESP32. Design clair et minimaliste, données simulées en attendant l'API réelle.

---

## 🎨 Design & Thème
- Style **clair, minimaliste et professionnel**
- Palette : blanc, gris clair, avec des accents bleus pour les actions
- Icônes simples (Lucide), typographie épurée
- Responsive mobile-first, optimisé pour smartphones

---

## 📱 Écrans de l'application

### 1. Écran de connexion WiFi guidée
- Instructions visuelles étape par étape pour se connecter au hotspot ESP32
- Champ de saisie du mot de passe WiFi
- Indicateur de statut de connexion (connecté / déconnecté)
- Bouton "Se connecter"

### 2. Écran d'authentification par code
- Saisie d'un code unique (champ OTP à 6 chiffres)
- Bouton de validation
- Message d'erreur en cas de code invalide
- Données simulées : le code "123456" sera accepté

### 3. Dashboard principal
- **Statut du device** : connecté/déconnecté, niveau batterie (simulé), version firmware
- **Fichier MP3 actuel** : nom du fichier, taille, durée
- **Actions rapides** : boutons pour uploader un MP3 et tester la lecture
- Carte récapitulative avec l'état général de la sirène

### 4. Upload fichier MP3
- Zone de glisser-déposer ou bouton de sélection de fichier
- Vérification du format (MP3 uniquement) et de la taille (max 5 MB)
- Barre de progression pendant l'upload
- Confirmation de succès ou message d'erreur
- Données simulées : l'upload sera simulé avec un délai artificiel

### 5. Test de lecture audio
- Bouton "Tester le message" sur le dashboard
- Animation visuelle pendant la lecture (simulée)
- Bouton d'arrêt
- Feedback de confirmation

### 6. Paramètres
- **Changer le mot de passe** WiFi du hotspot
- **Changer le code d'authentification**
- **Informations du device** : modèle, version firmware, adresse IP, MAC
- Bouton de déconnexion

---

## 🔧 Architecture technique
- **Navigation** : React Router avec 4 routes principales (connexion WiFi → auth → dashboard → paramètres)
- **Données simulées** : service mock qui imite les réponses de l'API REST ESP32
- **Capacitor** : configuration pour générer des builds Android (APK) et iOS
- **État** : React state local + React Query pour la gestion des appels API simulés

---

## 📋 Écrans & navigation

```
Connexion WiFi → Authentification code → Dashboard
                                            ├── Upload MP3
                                            ├── Test lecture
                                            └── Paramètres
```


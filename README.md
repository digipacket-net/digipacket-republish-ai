# Digipacket RePublish AI

Extension WordPress qui réécrit automatiquement vos nouveaux articles avec l'IA Google Gemini (offre gratuite), puis les publie sur un second site WordPress via l'API REST — **en conservant les images à l'identique**.

[![Version](https://img.shields.io/badge/version-1.1.2-2271b1)](https://github.com/digipacket-net/digipacket-republish-ai/releases/latest)
[![WordPress](https://img.shields.io/badge/WordPress-5.8%2B-21759b)](https://wordpress.org/)
[![PHP](https://img.shields.io/badge/PHP-7.4%2B-777bb4)](https://www.php.net/)
[![Licence](https://img.shields.io/badge/licence-GPL--2.0--or--later-green)](LICENSE)

---

## 📥 Téléchargement

**[⬇️ Télécharger la dernière version](https://github.com/digipacket-net/digipacket-republish-ai/releases/latest/download/digipacket-republish-ai.zip)**

---

## 🚀 Installation

### Méthode 1 — En SSH (recommandé)

Connectez-vous à votre serveur, puis :

```bash
cd /chemin/vers/wordpress/wp-content/plugins

wget https://github.com/digipacket-net/digipacket-republish-ai/releases/latest/download/digipacket-republish-ai.zip

unzip -o digipacket-republish-ai.zip
rm digipacket-republish-ai.zip
```

Activez ensuite l'extension depuis **Extensions** dans l'administration WordPress.

> Si `wget` n'est pas disponible, utilisez `curl -L -O <url>`.

### Méthode 2 — En SSH avec WP-CLI

Une seule commande, activation comprise :

```bash
wp plugin install https://github.com/digipacket-net/digipacket-republish-ai/releases/latest/download/digipacket-republish-ai.zip --activate
```

### Méthode 3 — Depuis l'administration WordPress

1. Téléchargez le fichier `.zip` avec le lien ci-dessus.
2. **Extensions → Ajouter → Téléverser une extension**.
3. Sélectionnez le `.zip` → **Installer maintenant** → **Activer**.

### Mise à jour

Reprenez la même commande : `unzip -o` écrase les anciens fichiers. Vos réglages et votre journal sont conservés.

---

## ⚙️ Configuration en 5 minutes

Cette extension s'installe sur **les deux sites**.

### Sur le SITE B (destination) — à faire en premier

1. **RePublish AI → Mode récepteur** → cocher **« Ce site est un site de destination »** → Enregistrer.
2. **Utilisateurs → Profil → Mots de passe d'application** : créer un mot de passe nommé `Digipacket RePublish`, puis le copier.

> Le site B doit être en **HTTPS**, sinon WordPress masque les mots de passe d'application.

### Sur le SITE A (source)

1. Obtenir une clé API Gemini gratuite sur **[Google AI Studio](https://aistudio.google.com/app/apikey)**.
2. **RePublish AI → Intelligence artificielle** : coller la clé → Enregistrer → **Tester Google Gemini**.
3. **RePublish AI → Site B (destination)** : URL, identifiant et mot de passe d'application → Enregistrer → **Tester le site B**.
4. Commencer avec **Statut sur le site B : Brouillon** le temps de valider la qualité des réécritures.

---

## ✨ Fonctionnalités

- **Détection automatique** de chaque nouvel article publié.
- **Réécriture par l'IA** : nouveau titre, nouvelle introduction, corps reformulé, métadonnées SEO et étiquettes.
- **Images garanties intactes** — extraites et remplacées par des marqueurs avant l'envoi à l'IA, puis réinjectées à l'identique. L'IA ne voit jamais leur code et ne peut ni les altérer ni les perdre.
- **Traitement asynchrone** : la publication n'est jamais ralentie.
- **Réessais automatiques** en respectant le délai imposé par Google en cas de quota atteint.
- **Catégories conservées** depuis le site d'origine, créées automatiquement si absentes.
- **Multilingue** : la langue et l'alphabet d'origine sont conservés (arabe, français…), URL comprise. Peut aussi traduire.
- **SEO** : compatible Yoast SEO, Rank Math, All in One SEO et SEOPress.
- **Anti-boucle et anti-doublon** : un article reçu ne repart jamais, un article déjà envoyé est mis à jour.
- **Journal complet** de chaque étape, avec durées et messages d'erreur.

---

## 📋 Prérequis

| | |
|---|---|
| WordPress | 5.8 ou supérieur |
| PHP | 7.4 ou supérieur |
| Site B | HTTPS, API REST accessible (`/wp-json/`) |
| Compte site B | Rôle Éditeur ou Administrateur |
| Clé API | Google Gemini — [offre gratuite](https://aistudio.google.com/app/apikey) |

---

## 🆘 Support

Un problème, une question : **[digipacket.net/contact](https://digipacket.net/contact)**

Joignez les lignes concernées de l'onglet **Journal** : elles contiennent le code HTTP et le message exact, ce qui permet un diagnostic immédiat.

---

## 📄 Licence

GPL-2.0-or-later — © [Digipacket](https://digipacket.net)

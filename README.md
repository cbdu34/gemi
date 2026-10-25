# ♊ Gemini Interpreter

Une interface web locale et légère qui permet à **Google Gemini (gratuit)** de contrôler votre terminal Linux et d'exécuter du code Python/Bash étape par étape, sans avoir besoin de clé API payante.

*Inspiré d'Open Interpreter, mais propulsé par l'interface web de Gemini via Playwright.*

![Licence](https://shields.io)
![Stars](https://shields.io)

---

## ✨ Fonctionnalités

- 🆓 **100% Gratuit :** Utilise l'interface web standard de Gemini. Pas besoin de crédit Google Cloud ni de clé API.
- 💻 **Boucle d'exécution locale :** Gemini écrit le code, votre machine l'exécute, et renvoie le résultat à Gemini jusqu'à ce que la tâche soit résolue.
- ⚙️ **Mode Automatique :** Laissez l'agent enchaîner les étapes tout seul (désactivable pour valider le code manuellement).
- 🛡️ **Sécurité intégrée :** Détection automatique des commandes destructrices (`rm -rf /`, `sudo`, etc.) avec demande de confirmation obligatoire.
- 📊 **Interface Moderne :** Un dashboard web complet avec Terminal temps réel et Éditeur de code intégré.

---

## 🚀 Installation & Lancement

### Prérequis
- Une machine sous **Linux (Ubuntu/Debian recommandé)**
- **Python 3.8+** et Google Chrome installé

### 1. Cloner le projet & Installer les dépendances
```bash
git clone https://github.com
cd gemini-interpreter
pip install flask playwright
playwright install chromium
```

### 2. Lancer l'application
```bash
python gemini_web.py
```
L'application va automatiquement ouvrir votre navigateur sur `http://127.0.0.1:5000`.

> 💡 **Note importante lors du premier lancement :** Le script ouvre une instance Chrome isolée (votre profil personnel n'est pas touché). Connectez-vous à votre compte Google sur l'interface Gemini pour que l'agent puisse fonctionner. La session sera sauvegardée localement pour les fois suivantes.

---

## 🛠️ Exemples d'utilisation

Vous pouvez demander à l'interface de réaliser des tâches complexes directement sur votre système :
- *"Trouve tous les fichiers PDF de mon dossier Téléchargements et compresse-les dans un zip."*
- *"Télécharge les 3 dernières vidéos de cette playlist YouTube (avec yt-dlp) et convertis-les en MP3."*
- *"Analyse les logs système du jour et fais-moi un résumé des erreurs critiques."*

---

## 🔒 Sécurité et bac à sable (Sandbox)

Ce projet interagit directement avec votre système d'exploitation. 
- Les scripts sont exécutés avec les privilèges de votre utilisateur Linux actuel (`cwd: $HOME`).
- Un filtre par expressions régulières (**DANGEROUS_PATTERNS**) intercepte les commandes à risque.
- **Utilisez ce projet avec précaution.** Ne l'exécutez pas en tant que `root`.

---

## 🤝 Collaboration & Projets

Si vous aimez ce projet et que vous cherchez un développeur pour **collaborer sur d'autres outils basés sur les IA, l'automatisation ou le développement web**, n'hésitez pas à me contacter ! 

Je suis ouvert aux opportunités et aux projets passionnants.

📬 **Me contacter par email :** 
[![Email](https://shields.io)](mailto:boitardclement28@gmail.com)

---

## 🛠️ Dépannage (Troubleshooting)

Si Playwright ne parvient pas à lancer le navigateur ou si vous rencontrez des erreurs de dépendances système sous Linux, exécutez la commande suivante pour installer les bibliothèques manquantes :

```bash
playwright install-deps
```

---

## 🤝 Contribution

Les contributions sont les bienvenues ! Comme ce projet repose sur le scraping de l'interface web de Gemini, **si Google met à jour son design, les sélecteurs Playwright peuvent casser**. N'hésitez pas à ouvrir une *Issue* ou une *Pull Request* pour mettre à jour les sélecteurs si nécessaire.

## 📄 Licence

Distribué sous la licence MIT. Voir le fichier `LICENSE` pour plus d'informations.

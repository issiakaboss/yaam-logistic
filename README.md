# 🚚 Yam Logistics - Site Officiel

Ce dépôt contient le code source du site vitrine de **Yam Logistics**, une entreprise de services logistiques et de livraison.

Le projet est conçu avec une architecture moderne, rapide et optimisée pour le SEO, connectée à un système de déploiement continu (CI/CD).

---

## 🏗️ Architecture Technique

L'application s'appuie sur un écosystème d'outils performants et découplés :
* **Frontend :** [Astro](https://astro.build/) (générateur de site statique ultra-rapide).
* **Formulaire de contact :** [Web3Forms](https://web3forms.com/) (gestion des soumissions de formulaires sans backend dédié).
* **Hébergement & CI/CD :** [Netlify](https://www.netlify.com/) (déploiement automatique à chaque `git push` sur la branche principale).
* **Nom de domaine & Messagerie :** [Hostinger](https://www.hostinger.fr/) (gestion du domaine `yamlogistic.com` et de la boîte mail professionnelle `info@yamlogistic.com`).

---

## 🔧 Configuration & Sécurité DNS (Netlify)

Pour que le site fonctionne et que les e-mails professionnels soient sécurisés (évitant d'atterrir dans les spams de Gmail), les enregistrements DNS suivants sont configurés sur notre zone DNS Netlify :

### 1. Pointage Web
* `NETLIFY` (Alias) ➔ Pointe le domaine principal `yamlogistic.com` vers les serveurs de rendu Netlify.

### 2. Serveurs de Messagerie (MX)
* `MX` (Priorité 10) ➔ `mx1.hostinger.com.`
* `MX` (Priorité 20) ➔ `mx2.hostinger.com.`

### 3. Authentification des E-mails (TXT)
* **SPF (Sender Policy Framework) :**
  * **Type :** `TXT`
  * **Nom :** `yamlogistic.com` (ou `@`)
  * **Valeur :** `v=spf1 include:_spf.mail.hostinger.com ~all` *(Autorise Hostinger à envoyer des e-mails pour notre compte)*.
* **DKIM (DomainKeys Identified Mail) :**
  * **Type :** `TXT`
  * **Nom :** `hostingermail1._domainkey.yamlogistic.com`
  * **Valeur :** Clé de chiffrement publique générée par Hostinger *(Valide la signature de nos e-mails auprès de Gmail/Outlook)*.

---

## 💻 Développement Local

### Prerequis
* [Node.js](https://nodejs.org/) (Version LTS recommandée)

### Commandes utiles

| Commande | Action |
| :--- | :--- |
| `npm install` | Installe toutes les dépendances du projet |
| `npm run dev` | Lance le serveur de développement local sur `http://localhost:4321` |
| `npm run build` | Compile le projet pour la production dans le dossier `./dist/` |
| `npm run preview` | Permet de tester le build de production localement avant déploiement |

---

## 👥 Flux de Communication

* **Formulaire de contact :** Les messages saisis par les visiteurs du site web sont envoyés via Web3Forms directement à l'adresse **`info@yamlogistic.com`**.
* **Webmail Pro :** Accessible en ligne via [mail.hostinger.com](https://mail.hostinger.com) ou synchronisé sur l'application Mail (iPhone/Android) en utilisant les serveurs IMAP/SMTP d'Hostinger.

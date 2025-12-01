# Portfolio Statique - Assoumani Moudjahidy

Ce dépôt contient les fichiers sources d'un portfolio personnel statique, codé en HTML et CSS pur (sans framework). Le site est conçu pour être responsive, accessible et facile à maintenir.

## 🚀 Déploiement sur GitHub Pages

Le déploiement est très simple grâce à GitHub Pages.

### Étapes de déploiement

1.  **Créer un dépôt :** Créez un nouveau dépôt sur GitHub (ex: `portfolio-assoumani`).
2.  **Pousser les fichiers :** Clonez ce dépôt localement et poussez tous les fichiers sur la branche `main`.
    ```bash
    git clone [URL_DU_DEPOT]
    cd portfolio-assoumani
    # Copier tous les fichiers ici
    git add .
    git commit -m "Initial commit: Portfolio V1"
    git push origin main
    ```
3.  **Activer GitHub Pages :**
    - Rendez-vous sur votre dépôt GitHub.
    - Allez dans **Settings** (Paramètres) -> **Pages**.
    - Sous "Build and deployment" (Construction et déploiement), assurez-vous que **Source** est réglé sur **Deploy from a branch**.
    - Sélectionnez la branche **`main`** et le dossier **`/root`** (ou `/ (root)`).
    - Cliquez sur **Save** (Enregistrer).

Le site sera disponible en quelques minutes à l'adresse suivante :
`https://<username>.github.io/portfolio-assoumani/`

## ✍️ Mise à Jour du Contenu et Maintenance

Pour maintenir le caractère statique du site et sa facilité de mise à jour, toute modification de contenu ou ajout de fichier se fait par la modification et le push sur le dépôt GitHub.

### Remplacer le CV (index.html)

Pour mettre à jour le CV affiché sur la page d'accueil :

1.  **Emplacement :** Placez votre nouveau fichier PDF dans le dossier : `assets/cv/`.
2.  **Nom de fichier :** Il est **fortement recommandé** de conserver le nom de fichier existant : `Assoumani_Moudjahidy_CV.pdf`.
    - Si vous devez changer le nom (ex: `Mon_CV_v2.pdf`), n'oubliez pas de mettre à jour **le lien dans le fichier `index.html`** (à la fois pour l'attribut `data` de la balise `<object>` et l'attribut `href` du bouton de téléchargement).
3.  **Commit & Push :** Poussez le nouveau fichier sur GitHub. Le site se mettra à jour automatiquement.

### Ajouter ou Remplacer des Documents (Projets & Documentation)

Pour ajouter des rapports, schémas ou autres documents :

1.  **Emplacement :** Placez le nouveau fichier dans le dossier approprié (ex: `assets/docs/`, `assets/docs/m2l/`, `assets/veille/`).
2.  **Ajouter le lien :** Modifiez manuellement le fichier HTML correspondant (`projets.html`, `documentation.html`, ou `veille.html`) en ajoutant un nouvel élément `<a>` ou une nouvelle `<article>` et en pointant l'attribut `href` vers le chemin de votre nouveau fichier.
    - **Exemple dans `documentation.html` :**
      ```html
      <a
        href="assets/docs/mon_nouveau_doc.pdf"
        download="Nom_du_Document.pdf"
        class="button download-button"
      >
        Télécharger (PDF)
      </a>
      ```
3.  **Commit & Push :** Poussez les fichiers mis à jour sur GitHub.

### Modifier les Coordonnées (Footer)

Les coordonnées affichées dans le `<footer class="site-footer">` se trouvent dans **tous les fichiers HTML**. Vous devez modifier la section `contact-info` dans chaque fichier (ex: `index.html`, `projets.html`, etc.) pour refléter vos vraies informations de contact.

---

## ⚙️ Note Technique : Gestion des Fichiers Statiques

Ce site est **statique**.

- **GitHub Pages** sert uniquement des fichiers HTML, CSS, JavaScript et assets (images, PDF, etc.) existants.
- **Il n'est pas possible** d'avoir une fonction "d'upload" dynamique (côté serveur) pour ajouter des documents directement depuis le site web sans passer par Git.

### Solutions d'Upload Dynamique (Avancé)

Si l'ajout de documents sans passer par Git est un jour nécessaire, deux options populaires pour les sites statiques sont :

1.  **Netlify CMS + Netlify Identity :** Netlify CMS est un outil qui permet d'éditer le contenu et d'ajouter des fichiers via une interface d'administration simple. Il se connecte à votre dépôt GitHub et committe les changements à votre place.
2.  **Firebase Storage + Firebase Auth :** Implémenter un script JavaScript sur le site pour gérer l'authentification (`Firebase Auth`) et l'envoi direct de fichiers vers un service de stockage Cloud (`Firebase Storage`). Le site devrait alors lister ces documents dynamiquement via JS.

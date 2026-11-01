<img width="904" height="493" alt="Capture d&#39;écran 2026-10-31 233520" src="https://github.com/user-attachments/assets/75236faf-0d64-4b2b-adb8-d86a56d3d29e" />
<img width="917" height="485" alt="Capture d&#39;écran 2026-10-31 234748" src="https://github.com/user-attachments/assets/beb700a8-f4db-4a4e-9111-2762ec83b296" />
<img width="959" height="539" alt="Capture d&#39;écran 2026-10-31 234851" src="https://github.com/user-attachments/assets/d5f63171-c328-4d9e-b7bd-b5c345e072bf" />
<img width="955" height="539" alt="Capture d&#39;écran 2026-10-31 235555" src="https://github.com/user-attachments/assets/080be99a-a3f0-4278-9b11-e9f121f490b9" />
<img width="520" height="314" alt="Capture d&#39;écran 2026-10-31 235928" src="https://github.com/user-attachments/assets/8896bfcf-e654-4109-b91b-9547551fb19d" />
<img width="797" height="419" alt="Capture d&#39;écran 2026-10-31 235940" src="https://github.com/user-attachments/assets/d889bfc8-6d3e-436c-8eea-553d8be4d959" />
<img width="959" height="515" alt="Capture d&#39;écran 2026-10-31 235948" src="https://github.com/user-attachments/assets/dc3b68f6-3650-4c41-b03f-8164dbf4ee95" />
<img width="946" height="522" alt="Capture d&#39;écran 2026-11-01 000620" src="https://github.com/user-attachments/assets/54244baa-8fa9-4244-a48d-cfdef501b43a" />
<img width="930" height="494" alt="Capture d&#39;écran 2026-11-01 001620" src="https://github.com/user-attachments/assets/831b995b-696f-4138-b8cf-035981327616" />
# Lab SQL - Projet de Gestion d'Utilisateurs

Ce projet présente la mise en place d'une base de données MySQL structurée selon les exigences du lab.

---

### Étape 1 : Création de la base de données
* **Description :** Création de la base de données `testdb` avec l'encodage `utf8mb4` pour supporter tous les caractères spéciaux et les accents, suivie de sa sélection avec la commande `USE`.
* **Capture d'écran :**
  ![Étape 1](chemin_vers_image1.png)

---

### Étape 2 : Création de la table
* **Description :** Création de la table `utilisateur` contenant les colonnes `id` (clé primaire auto-incrémentée), `nom`, et `email` (unique), en utilisant le moteur de stockage `InnoDB`.
* **Capture d'écran :**
  ![Étape 2](chemin_vers_image2.png)

---

### Étape 3 : Insertion des données
* **Description :** Insertion de trois enregistrements de test (utilisateurs) dans la table `utilisateur` pour valider la structure et le bon fonctionnement des insertions.
* **Capture d'écran :**
  ![Étape 3](chemin_vers_image3.png)

---

### Étape 4 : Création des index
* **Description :** Création d'un index (`idx_email`) sur la colonne `email` afin d'optimiser et d'accélérer la vitesse des recherches et des requêtes.
* **Capture d'écran :**
  ![Étape 4](chemin_vers_image4.png)

---

### Étape 5 : Gestion des privilèges
* **Description :** Création d'un utilisateur dédié `app_user` et attribution de privilèges restreints (`SELECT`, `INSERT`, `UPDATE`, `DELETE`) uniquement sur la base `testdb` pour des raisons de sécurité.
* **Capture d'écran :**
  ![Étape 5](chemin_vers_image5.png)

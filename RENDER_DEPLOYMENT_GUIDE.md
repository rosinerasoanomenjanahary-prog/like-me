# 🚀 GUIDE DE DÉPLOIEMENT SUR RENDER

## Étapes pour mettre ton site en ligne :

### **Étape 1️⃣ : Crée un compte MongoDB Atlas (Base de données gratuite)**

1. Va sur https://www.mongodb.com/cloud/atlas
2. Clique sur **"Sign Up"** (gratuit)
3. Crée un compte avec email
4. Crée un **nouveau projet** : "like-me"
5. Clique sur **"Create a Deployment"**
6. Choisis **"Free Tier"**
7. Crée un **utilisateur** (username + password)
8. Ajoute ton IP : Clique sur **"Add My Current IP"**
9. Copie l'URL de connexion (Connection String)

**Ça ressemble à :**
```
mongodb+srv://username:password@cluster.mongodb.net/like-me?retryWrites=true&w=majority
```

---

### **Étape 2️⃣ : Prépare ton code pour Render**

✅ **Déjà fait !** J'ai ajouté :
- `Procfile` - Pour dire à Render comment lancer l'app
- `server.js` mis à jour - Sert le frontend + backend
- `package.json` avec scripts de build
- `client/package.json` configuré

---

### **Étape 3️⃣ : Crée un compte sur Render**

1. Va sur https://render.com
2. Clique sur **"Sign Up"**
3. Inscris-toi avec GitHub ou email
4. Connecte ton compte GitHub à Render (si pas déjà fait)

---

### **Étape 4️⃣ : Déploie sur Render**

1. Va sur https://dashboard.render.com
2. Clique sur **"New +"** → **"Web Service"**
3. Cherche le repo `like-me` et sélectionne-le
4. Remplis les champs :
   - **Name** : `like-me` (ou ton choix)
   - **Environment** : `Node`
   - **Build Command** : 
   ```
   npm install && npm run build
   ```
   - **Start Command** : 
   ```
   node server.js
   ```

5. Scroll down et clique sur **"Advanced"**
6. Ajoute les **Environment Variables** :
   - **Key** : `MONGODB_URI`
   - **Value** : (Colle l'URL MongoDB Atlas que tu as copié)
   - Clique **"Add"**

7. Ajoute une 2ème variable :
   - **Key** : `MARGIN`
   - **Value** : `5`
   - Clique **"Add"**

8. Clique sur **"Create Web Service"**

---

### **Étape 5️⃣ : Attends le déploiement** ⏳

Render va :
1. Cloner ton code GitHub
2. Installer les dépendances
3. Builder le frontend React
4. Lancer le serveur

**C'est normal que ça prenne 5-10 minutes la première fois !**

---

### **Étape 6️⃣ : Ton site est en ligne ! 🎉**

Une fois déployé, tu vas recevoir une URL comme :
```
https://like-me-xxxxx.onrender.com
```

**C'est ton lien ! Partage-le avec tes clients ! 💰**

---

## 📝 Pour les mises à jour futures

À chaque fois que tu push du code sur GitHub :
```bash
git add .
git commit -m "Mise à jour"
git push origin main
```

**Render redéploiera automatiquement !** ✅

---

## 🆘 Troubleshooting

**Si ça ne marche pas :**

1. **Vérifie les logs** : Dans le dashboard Render, clique sur ton service → **"Logs"**
2. **MongoDB connection error ?** 
   - Vérifie l'URL MongoDB Atlas
   - Ajoute ton IP dans MongoDB Atlas
3. **Port error ?**
   - Render choisit le port automatiquement, c'est normal

---

## ✅ Résumé rapide

1. ✅ MongoDB Atlas (gratuit) - Done
2. ✅ Code préparé - Done
3. ⏳ Crée compte Render
4. ⏳ Connecte GitHub à Render
5. ⏳ Déploie le repo `like-me`
6. ⏳ Ajoute MONGODB_URI en variable
7. 🎉 Ton site est LIVE !

---

**Questions ? Besoin d'aide ? Dis-moi !** 🚀

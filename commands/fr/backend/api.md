---
description: Générer des endpoints d'API REST avec validation et gestion d'erreurs
allowed-tools: Read, Edit, Write, Bash(npm:*, yarn:*)
---

## Votre tâche

Générer des endpoints d'API REST avec validation appropriée, gestion d'erreurs et documentation suivant les principes RESTful.

### Processus de développement d'API

1. **Concevoir la structure de l'API** : Définir les routes, méthodes et flux de données
2. **Créer les gestionnaires de routes** : Implémenter les fonctions de contrôleur pour chaque endpoint
3. **Ajouter la validation** : Implémenter la validation des entrées en utilisant les bibliothèques appropriées
4. **Gestion d'erreurs** : Créer un middleware complet de gestion d'erreurs
5. **Ajouter la documentation** : Générer la documentation OpenAPI/Swagger
6. **Créer les tests** : Écrire des tests unitaires et d'intégration pour tous les endpoints

### Directives d'implémentation

- Suivre les conventions de nommage RESTful
- Utiliser les codes de statut HTTP appropriés
- Implémenter une authentification et autorisation appropriées
- Ajouter la limitation de taux et les en-têtes de sécurité
- Utiliser des middleware pour les préoccupations transversales
- Suivre les motifs et conventions existants du projet

### Exemple de structure d'API

```javascript
// routes/utilisateurs.js
const express = require('express');
const { body, validationResult } = require('express-validator');
const router = express.Router();

// GET /api/utilisateurs
router.get('/', async (req, res) => {
  try {
    const utilisateurs = await Utilisateur.find({});
    res.json({ succes: true, donnees: utilisateurs });
  } catch (erreur) {
    res.status(500).json({ succes: false, erreur: erreur.message });
  }
});

// POST /api/utilisateurs
router.post('/', [
  body('email').isEmail().normalizeEmail(),
  body('nom').isLength({ min: 2 }).trim(),
], async (req, res) => {
  const erreurs = validationResult(req);
  if (!erreurs.isEmpty()) {
    return res.status(400).json({ succes: false, erreurs: erreurs.array() });
  }
  
  try {
    const utilisateur = new Utilisateur(req.body);
    await utilisateur.save();
    res.status(201).json({ succes: true, donnees: utilisateur });
  } catch (erreur) {
    res.status(500).json({ succes: false, erreur: erreur.message });
  }
});

module.exports = router;
```

Cette commande aide à créer des endpoints d'API cohérents, sécurisés et bien documentés qui suivent les meilleures pratiques de l'industrie.
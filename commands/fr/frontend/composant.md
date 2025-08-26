---
description: Générer des composants React avec des définitions TypeScript
allowed-tools: Read, Edit, Write, Bash(npm:*)
---

## Votre tâche

Générer des composants React avec des définitions TypeScript appropriées, en suivant les meilleures pratiques pour le développement React moderne.

### Processus de création de composant

1. **Analyser les exigences** : Examiner les spécifications et exigences du composant
2. **Créer la structure du composant** : Générer le fichier principal du composant avec les imports et exports appropriés
3. **Ajouter les définitions TypeScript** : Créer des définitions de types complètes pour les props et l'état
4. **Générer les tests** : Créer des tests unitaires pour le composant en utilisant Jest et React Testing Library
5. **Ajouter les histoires Storybook** : Créer des histoires Storybook pour la documentation du composant
6. **Mettre à jour les exports** : Ajouter le composant aux fichiers d'index appropriés

### Directives d'implémentation

- Utiliser des composants fonctionnels avec des hooks
- Suivre les conventions de nommage React
- Implémenter des limites d'erreur appropriées si nécessaire
- Ajouter des attributs d'accessibilité (labels ARIA, rôles)
- Inclure PropTypes pour la validation à l'exécution
- Utiliser des modules CSS ou styled-components pour le style
- Suivre le style de code et les motifs existants du projet

### Exemple de structure de composant

```tsx
import React from 'react';
import { ComponentProps } from './types';

export const MonComposant: React.FC<ComponentProps> = ({
  titre,
  children,
  variante = 'defaut',
  ...props
}) => {
  return (
    <div className={`composant composant--${variante}`} {...props}>
      <h2>{titre}</h2>
      {children}
    </div>
  );
};
```

Cette commande aide à créer des composants React cohérents et bien structurés qui suivent les pratiques de développement modernes.
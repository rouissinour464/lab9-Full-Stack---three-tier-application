# LAB9 - Application Kubernetes Three-Tier

## Description du projet

Ce projet est une application web simple déployée sur Kubernetes, avec une architecture **three-tier** :  

1. **Frontend** : interface utilisateur (Flask / HTML)  
2. **Backend/API** : service de gestion des données et logique métier  
3. **Database** : PostgreSQL avec persistance (PV/PVC), Secrets et ConfigMaps  

Le projet inclut :  
- Déploiements Kubernetes pour frontend, backend et base de données  
- Services pour exposer les pods  
- Job Kubernetes pour initialiser la base de données  
- Secrets pour sécuriser les credentials  
- ConfigMaps pour config non sensible  

---

## Comparaison Two-Tier vs Three-Tier

| Critère                  | Two-Tier (Frontend + DB)      | Three-Tier (Frontend + Backend + DB) |
|---------------------------|------------------------------|-------------------------------------|
| **Architecture**         | 2 couches : UI + DB          | 3 couches : UI + API + DB           |
| **Séparation des responsabilités** | Faible, logique métier dans le frontend | Élevée, logique métier dans le backend |
| **Scalabilité**           | Limité, difficile de scaler le backend séparément | Très scalable, on peut scaler frontend et backend indépendamment |
| **Sécurité**              | Moins sécurisé, la DB peut être exposée indirectement | Plus sécurisé, la DB n’est accessible qu’au backend |
| **Maintenance / Extensibilité** | Difficile à maintenir et faire évoluer | Facile à maintenir et étendre |
| **Déploiement**           | Simple mais rigide           | Plus complexe mais flexible         |

---

## Installation et déploiement

1. Cloner le projet :  git clone https://github.com/ton-compte/LAB9-k8s.git
```bash
2. Déployer la base de données
3. Déployer le backend
4. Déployer le frontend
5. Vérifier les pods et services
Conclusion

Cette architecture three-tier permet :
- Une meilleure séparation des responsabilités
- Une scalabilité indépendante des différentes couches
- Une sécurité améliorée pour la base de données
- Une maintenance et évolution plus facile de l’application

git clone https://github.com/ton-compte/LAB9-k8s.git
cd LAB9-k8s

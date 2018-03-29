---
title: Planification pour le Gestionnaire de statistiques pour Skype pour Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 5/23/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur le Gestionnaire de statistiques pour Skype pour Business Server 2015.'
ms.openlocfilehash: 63f064f9a6632250f3cfadddbcbb5fca2120f07b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server-2015"></a>Planification pour le Gestionnaire de statistiques pour Skype pour Business Server 2015
 
**Résumé :** Lisez cette rubrique pour en savoir plus sur le Gestionnaire de statistiques pour Skype pour Business Server 2015.
  
 Le Gestionnaire de statistiques pour Skype pour Business Server est un outil puissant qui vous permet d’afficher les Skype pour les données de santé et les performances de serveur d’entreprise en temps réel. Vous pouvez interroger les données de performance sur des centaines de serveurs toutes les quelques secondes et afficher les résultats d’instantanément sur le site Web du Gestionnaire de statistiques.
  
Gestionnaire de statistiques vous permet d’identifier les problèmes de performances en cours, afficher les résultats de la modification prévue à votre environnement, assurer le suivi de la résolution des pannes et bien plus encore. Prêts à l’emploi, le Gestionnaire de statistiques est configuré avec des seuils d’indicateur d’état clé (KHI) et peut être personnalisé pour répondre aux besoins spécifiques de votre déploiement. 
  
Vous pouvez déployer des statistiques Manager dans un déploiement sur site dans lequel un seul serveur héberge tous les composants du Gestionnaire de statistiques côté serveur. Pour plus d’informations sur le déploiement du Gestionnaire de statistiques, voir [Déployer des statistiques responsable Skype pour Business Server 2015](deploy.md). Si vous disposez déjà d’un déploiement existant de gestionnaire de statistiques, mais vous ne disposez pas encore mis à niveau vers version 1.1, consultez [Nouveautés de version 1.1](plan.md#BKMK_WhatsNew) et de [Mettre à niveau le Gestionnaire de statistiques pour Skype pour Business Server 2015](upgrade.md).
  
Cette rubrique contient les sections suivantes :
  
- [Fonctions et fonctionnalités](http://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Features)
    
- [Quelles sont les nouveautés dans la version 1.1](plan.md#BKMK_WhatsNew)
    
- [Composants](http://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Components)
    
- [Déploiement sur site](plan.md#BKMK_DeploymentOptions)
    
- [Configuration requise](http://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Requirements)
    
- [Considérations sur la sécurité](plan.md#BKMK_Security)
    
## <a name="features-and-capabilities"></a>Fonctions et fonctionnalités
<a name="BKMK_Features"> </a>

Gestionnaire de statistiques vous permet de :
  
- Permet d’afficher les données brutes pour tous les serveurs en temps réel. (Données sont échantillonnées à un taux très élevé et envoyées sur le site Web en moins d’une seconde).
    
- Afficher les données rassemblées pour un rôle spécifique ; par exemple, serveur frontal, serveur de médiation, serveur de transport Edge et ainsi de suite.
    
- Effectuer un zoom avant afin d’afficher les données pour certains sites, des pools spécifiques au sein du site et serveurs puis spécifiques au sein du pool.
    
- Créer des graphiques personnalisés afin que choisi les compteurs sont affichés par défaut.
    
- Zoom et panoramique sur les deux les axes x - et y- ou sur l’axe.
    
- Utiliser les plages de dates ou de points dans le temps pour filtrer les données. 
    
- Afficher les performances de serveur basé sur établissement les principaux indicateurs de fonctionnement (KHIs). KHIs représentent un ensemble de compteurs de performance avec une plage définie de saine. 
    
- Permet d’afficher des mesures détaillées pour chaque compteur.
    
- Comparer les données entre plusieurs serveurs ou populations.
    
- Afficher les rapports de compteur latente pour identifier les agents qui n'effectuent pas de rapports des données en cours pour le service de tableau de bord.
    
- Enregistrer une instance particulière de données de graphique dans un fichier.
    
- KHIs d’afficher en temps réel, y compris les mises à jour. Si l’affichage de l’historique est activée, seuls les échecs nouvelles sont affichés.
    
  - Permet d’afficher simultanément tous les KHIs
    
  - KHIs d’affichage par serveur (mode paysage)
    
  - Afficher les définitions de KHI
    
## <a name="whats-new-in-release-11"></a>Quelles sont les nouveautés dans la version 1.1
<a name="BKMK_WhatsNew"> </a>

La section suivante décrit quelles sont les nouveautés dans la version 1.1. Si vous avez un déploiement existant de gestionnaire de statistiques et que vous n’avez pas encore mis à niveau, voir [Mettre à niveau le Gestionnaire de statistiques pour Skype pour Business Server 2015](upgrade.md).
  
- Vues de scénario ont été ajoutées pour bord Media, santé du Fabric, Pool de scénarios de basculement et d’enregistrement.
    
- PerfAgentStorageManager.exe ligne de commande (installé avec l’écouteur) pouvez désormais exporter des données du compteur sous la forme d’un fichier CSV.
    
- De nombreux nouveaux compteurs ont été ajoutés pour les serveurs SQL, compteurs Windows Fabric, plus Skype pour les compteurs d’utilisation métier et ainsi de suite.
    
- Intégration de nœud de l’Observateur de le Manager de statistiques Agent - si l’Agent est installé sur un nœud de l’Observateur, il communiquera statistiques des transactions synthétiques comme les compteurs de statistiques dans le Gestionnaire de périphériques.
    
- Nombreuses améliorations de la fiabilité et les performances.
    
Pour vérifier la version du Gestionnaire de statistiques de site Web vous exécutez :
  
- Dans l’Explorateur de fichiers, ouvrez (répertoire par défaut) Files\Skype C:\Program pour Business Server StatsMan WebSite\bin
    
- Cliquez avec le bouton droit sur StatsManHubWebSite.dll et affichez ses propriétés
    
- La version du produit s’affiche dans les détails de la description.
    
## <a name="components"></a>Composants
<a name="BKMK_Components"> </a>

Gestionnaire de statistiques comprend les éléments suivants :
  
- **Agent.** Un légère de l’agent qui s’exécute sur chaque serveur analysé. L’Agent permet d’interrogation configurable taux élevé de compteurs de performance avec une agrégation locale.
    
- **Port d’écoute.** L’API côté serveur qui reçoit les données de tous les Agents et regroupe les données sur les populations.
    
- **Concentrateur.** Sert de l’API cliente pour le système, s’exécute sur les serveurs web et fournit des mises à jour des données en temps réel aux clients connectés via le site Web. (Le concentrateur est automatiquement installé dans le cadre de msi site Web).
    
- **Site Web.** Une interface utilisateur qui regroupe toutes les fonctions disponibles dans le système.
    
En outre, le Gestionnaire de statistiques nécessite **Redis**, un serveur de structure de données de source ouverte pour la mise en cache en mémoire. Pour plus d’informations sur le téléchargement de Redis, consultez [Déploiement de gestionnaire de statistiques](deploy.md#BKMK_Deploy) .
  
## <a name="on-premises-deployment"></a>Déploiement sur site
<a name="BKMK_DeploymentOptions"> </a>

Dans un déploiement sur site, un seul serveur héberge tous les composants du Gestionnaire de statistiques côté serveur. 
  
Le diagramme suivant illustre un déploiement sur site, dans lequel le site Web Gestionnaire de statistiques, Hub, écouteur et Redis la mise en cache de système sont hébergés sur un seul ordinateur. Gestionnaire de statistiques est surveillance Skype trois serveurs d’entreprise, qui ont un seul Agent de transmission des données à l’écouteur. Les utilisateurs se connectent à un site Web pour afficher toutes les données sont agrégées par le Gestionnaire de statistiques :
  
![Déploiement sur site du gestionnaire de statistiques](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)
  
## <a name="requirements"></a>Conditions requises
<a name="BKMK_Requirements"> </a>

Vous devez tenir compte des besoins matériels, logiciels et réseau suivants avant de déployer le Gestionnaire de statistiques. 
  
### <a name="software-requirements"></a>Configuration logicielle requise

- Windows Server 2012 R2
    
- IIS (automatiquement installés)
    
- Redis
    
- Services Gestionnaire de statistiques (automatiquement installés)
    
- PSExec - nécessaire pour effectuer le déploiement de l’agent à distance
    
- .NET 4.5 (incluse dans 2012 R2) - requis pour les composants côté serveur
    
- .NET 4.0 - requise pour les agents
    
### <a name="networking-requirements"></a>Exigences de mise en réseau


|**Serveur d’hébergement**|**Agents**|**Port d’écoute**|
|:-----|:-----|:-----|
|Gestion de réseau gigabit minimale en duplex intégral.  <br/> |8443 (numéro de port personnalisables) pour communiquer avec le port d’écoute du port TCP sortant.  <br/> |Le port d’écoute doit être le même sur tous les serveurs.  <br/> |
|Le port TCP 80 ou 443 ouvert pour héberger le site Web de trafic entrant.  <br/> |||
|Le port TCP 8443 (numéro de port personnalisables) de trafic entrant pour les agents de communiquer avec lui.  <br/> |||
   
Lors de l’installation, les ports de pare-feu pour le récepteur et le site Web sont créés automatiquement. Pour les Agents, l’installation suppose que les connexions TCP sortantes sont autorisées par défaut.
  
### <a name="hardware-requirements"></a>Configuration matérielle requise

Dans un déploiement sur site, dans laquelle un seul serveur héberge tous les composants du Gestionnaire de statistiques côté serveur, un serveur avec 16 Go de RAM et 4 processeur doit être en mesure de prendre en charge environ 150 échantillons par seconde en moyenne. Pour déterminer le nombre des compteurs/agents, vous pouvez prendre en charge, utilisez le calcul suivant : 
  
100 serveurs \*compteurs de 80 \* 1 échantillon par minute de chaque agent / 60 secondes = ~ 133 par seconde.
  
## <a name="security-considerations"></a>Considérations sur la sécurité
<a name="BKMK_Security"> </a>

Tout le trafic entre les serveurs est chiffré. 
  
- Le trafic HTTPS chiffré recevrez via le port 8443 (par défaut) de l’Agent au serveur récepteur.
    
- L’Agent vérifie l’empreinte de SSL sur le serveur pour que le serveur récepteur soit le destinataire prévu. Notez que l’agent utilise la vérification de l’empreinte de certificat (au lieu de la vérification de la chaîne). Il n’effectue pas de validation de certificat complète, car il est possible d’utiliser des certificats auto-signés.
    
- Une fois que l’Agent est satisfait, l’écouteur est authentique, un mot de passe sera présentée par l’Agent qui est ensuite vérifiée par le récepteur. 
    
- L’Agent commence la transmission des données de performances sur la connexion à l’écouteur.
    
## <a name="for-more-information"></a>Pour plus d'informations
<a name="BKMK_Security"> </a>

Pour plus d'informations, voir les articles suivants :
  
- [Déployer le Gestionnaire de statistiques pour Skype pour Business Server 2015](deploy.md)
    
- [Mise à jour des statistiques responsable Skype pour Business Server 2015](upgrade.md)
    
- [Résoudre les problèmes de statistiques responsable Skype pour Business Server 2015](troubleshoot.md)
    
- [Skype pour Business Server Manager statistiques de blog](https://blogs.technet.microsoft.com/skypestatsman/)
    


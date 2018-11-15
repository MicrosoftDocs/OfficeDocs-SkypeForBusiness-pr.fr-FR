---
title: Planifier Business Server pour le Gestionnaire de statistiques de Skype
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur le Gestionnaire de statistiques de Skype pour Business Server.'
ms.openlocfilehash: 7b4c45bf3fe230c331725a4510a2a8a499300bef
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531080"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>Planifier Business Server pour le Gestionnaire de statistiques de Skype

**Résumé :** Lisez cette rubrique pour en savoir plus sur le Gestionnaire de statistiques de Skype pour Business Server.

 Gestionnaire de statistiques pour Skype pour Business Server est un outil puissant qui vous permet d’afficher Skype pour les données de performances et d’intégrité Business Server en temps réel. Vous pouvez interroger les données de performance sur des centaines de serveurs après quelques secondes et afficher les résultats instantanément sur le site Web de gestionnaire de statistiques.

Vous pouvez utiliser le Gestionnaire de statistiques pour identifier les problèmes de performances en cours, afficher les résultats d’une modification planifiée dans votre environnement, effectuer le suivi de la résolution des pannes et bien plus encore. L’emploi, Gestionnaire de statistiques est configuré avec les seuils d’indicateur de l’intégrité de clé (KHI) et peuvent être personnalisé en fonction des besoins de votre déploiement.

Vous pouvez déployer le Gestionnaire de statistiques dans un déploiement sur site dans lequel un seul serveur héberge tous les composants du Gestionnaire de statistiques côté serveur. Pour plus d’informations sur le déploiement du Gestionnaire de statistiques, voir [Déployer des statistiques responsable Skype pour Business Server](deploy.md). Si vous disposez déjà d’un déploiement existant du Gestionnaire de statistiques, mais vous ne disposez pas encore mis à niveau vers version 2.0, voir [Nouveautés de version 2.0](plan.md#BKMK_WhatsNew) et la [Mise à niveau du Gestionnaire de statistiques pour Skype pour Business Server](upgrade.md).

Cette rubrique contient les sections suivantes :

- [Fonctions et fonctionnalités](plan.md#BKMK_Features)

- [Quelles sont les nouveautés dans la version 2.0](plan.md#BKMK_WhatsNew)

- [Composants](plan.md#BKMK_Components)

- [Déploiement local](plan.md#BKMK_DeploymentOptions)

- [Configuration requise](plan.md#BKMK_Requirements)

- [Considérations relatives à la sécurité](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>Fonctions et fonctionnalités
<a name="BKMK_Features"> </a>

Gestionnaire de statistiques vous permet de :

- Afficher les données brutes pour tous les serveurs en temps réel. (Données sont l’objet d’un taux très élevé et envoyées au site Web en moins d’une seconde).

- Afficher les données qui sont regroupées pour un rôle spécifique ; par exemple, serveur frontal, serveur de médiation, serveur Edge et ainsi de suite.

- Accéder à afficher les données pour des sites spécifiques, des pools spécifiques au sein du site et serveurs puis spécifiques au sein du pool.

- Créer des graphiques personnalisés afin que choisi compteurs sont affichées par défaut.

- Zoom et panoramique sur les deux - axes x et y- ou sur l’axe.

- Utiliser des plages de dates ou de points dans le temps pour filtrer les données.

- Afficher les performances du serveur en fonction des indicateurs d’intégrité de clé établie (KHIs). KHIs représentent une collection de compteurs de performance avec une plage définie saine.

- Visualiser les mesures détaillées pour chaque compteur.

- Comparer les données entre plusieurs populations ou plusieurs serveurs.

- Afficher les rapports de compteur latent pour identifier les agents qui sont reporting pas de données actuelles pour le service de tableau de bord.

- Enregistrer une instance spécifique de données de graphique dans un fichier.

- Affichage KHIs en temps réel, y compris les mises à jour. Si l’affichage de l’historique est activée, seuls les échecs nouveau sont affichés.

  - Afficher tous les KHIs en même temps

  - Vue KHIs par le serveur (mode paysage)

  - Définitions d’affichage KHI

## <a name="whats-new-in-release-20"></a>Quelles sont les nouveautés dans la version 2.0
<a name="BKMK_WhatsNew"> </a>

La section suivante décrit les nouveautés dans la version 2.0. Si vous avez un déploiement existant de statistiques Manager et vous n’avez pas encore mis à niveau, voir [Mise à niveau du Gestionnaire de statistiques pour Skype pour Business Server](upgrade.md).

- Vues de scénario ont été ajoutées pour le média Edge, d’intégrité Fabric, le basculement et scénarios d’inscription.

- Nombre de nouveaux compteurs ont été ajoutées pour les serveurs SQL, plus Skype pour des compteurs d’utilisation de Business et ainsi de suite.

- Intégration de nœud observateur pour l’Agent de gestionnaire de statistiques - si l’Agent est installé sur un nœud Observateur, il renverra un compte-rendu statistiques sur les transactions synthétiques en tant que compteurs au Gestionnaire de statistiques.

- Nombreuses améliorations de la fiabilité et les performances.

Pour vérifier la version du Gestionnaire de statistiques de site Web vous exécutez :

- Dans l’Explorateur de fichiers, ouvrez (répertoire par défaut) C:\Program Files\Skype pour Business Server StatsMan WebSite\bin

- Cliquez avec le bouton droit sur StatsManHubWebSite.dll et afficher ses propriétés

- La version du produit s’affiche dans les détails de la description.

## <a name="components"></a>Composants
<a name="BKMK_Components"> </a>

Gestionnaire de statistiques comprend les composants suivants :

- **Agent.** Un agent léger qui s’exécute sur chaque serveur analysé. L’Agent permet d’interrogation configurable taux élevé de compteurs de performances avec l’agrégation de locale.

- **Port d’écoute.** L’API côté serveur qui reçoit les données de tous les Agents et regroupe les données entre les populations.

- **Hub.** Sert de l’API cliente pour le système, s’exécute sur l’ou les serveurs web et fournit des mises à jour des données en temps réel aux clients connectés via le site Web. (Le Hub est installé automatiquement dans le cadre d’un site Web msi).

- **Site Web.** Une interface utilisateur qui regroupe toutes les fonctionnalités disponibles dans le système.

En outre, le Gestionnaire de statistiques nécessite **Redis**, un serveur de structure de données source ouverte pour la mise en cache en mémoire. Pour plus d’informations sur le téléchargement Redis, voir [Déployer le gestionnaire statistiques](deploy.md#BKMK_Deploy) .

## <a name="on-premises-deployment"></a>Déploiement local
<a name="BKMK_DeploymentOptions"> </a>

Dans un déploiement sur site, un seul serveur héberge tous les composants du Gestionnaire de statistiques côté serveur.

Le diagramme suivant illustre un déploiement sur site, dans lequel le site Web du gestionnaire statistiques, Hub, port d’écoute et Redis mise en cache du système sont hébergés sur un seul ordinateur. Gestionnaire de statistiques de surveillance Skype trois serveurs d’entreprise, chacun d'entre eux ont un seul Agent de transmission de données vers le port d’écoute. Utilisateurs se connectent à un site Web pour afficher toutes les données sont agrégées par le Gestionnaire de statistiques :

![Déploiement sur site du gestionnaire de statistiques](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>Conditions requises
<a name="BKMK_Requirements"> </a>

Vous devez prendre en compte la configuration requise matérielle, logicielle et réseau suivante avant de déployer le Gestionnaire de statistiques.

### <a name="software-requirements"></a>Configuration logicielle requise

- Windows Server 2016 et 2019

- IIS (installé automatiquement)

- Redis

- Services Gestionnaire de statistiques (installés automatiquement)

- PSExec - nécessaire pour exécuter le déploiement de l’agent à distance

- .NET 4.5 (inclus avec 2012 R2) - requis pour les agents et les composants côté serveur

### <a name="networking-requirements"></a>Exigences de mise en réseau


|**Serveur d’hébergement**|**Agents**|**Port d’écoute**|
|:-----|:-----|:-----|
|Gestion de réseau gigabit minimale en duplex intégral.  <br/> |Port TCP sortant 8443 (numéro de port personnalisable) pour communiquer avec le port d’écoute.  <br/> |Le port d’écoute doit être identiques sur tous les serveurs.  <br/> |
|Le port TCP 80 ou 443 ouvert pour héberger le site Web de trafic entrant.  <br/> |||
|Entrante 8443 (numéro de port personnalisables) le port TCP pour les agents de communiquer avec lui.  <br/> |||

Pendant l’installation, les ports de pare-feu pour le port d’écoute et le site Web sont créés automatiquement. Pour les Agents, l’installation suppose que les connexions TCP sortantes sont autorisées par défaut.

### <a name="hardware-requirements"></a>Configuration matérielle requise

Dans un déploiement sur site, dans laquelle un seul serveur héberge tous les composants du Gestionnaire de statistiques côté serveur, un serveur avec 16 Go de RAM et 4 processeurs doit pouvoir prendre en charge environ 150 échantillons par seconde en moyenne. Pour déterminer combien compteurs/agents, vous pouvez prendre en charge, utilisez le calcul suivant :

100 serveurs \*80 compteurs \* 1 exemple par minute de chaque agent / 60 secondes = ~ 133 par seconde.

## <a name="security-considerations"></a>Considérations relatives à la sécurité
<a name="BKMK_Security"> </a>

Tout le trafic entre les serveurs est chiffré.

- Le trafic HTTPS chiffré recevrez via le port 8443 (par défaut) à partir de l’Agent sur le serveur de port d’écoute.

- L’Agent vérifie l’empreinte de SSL sur le serveur afin de garantir le serveur écoute le destinataire prévu. Notez que l’agent utilise la vérification de l’empreinte de certificat (au lieu de la vérification de la chaîne). Il n’effectue pas de validation de certificat complète, car il est possible d’utiliser des certificats auto-signés.

- Une fois que l’Agent est satisfait le port d’écoute est authentique, un mot de passe est présentée par l’Agent qui est ensuite vérifiée par le récepteur.

- L’Agent commence la transmission de données de performances sur la connexion à l’écouteur.

## <a name="for-more-information"></a>Pour plus d’informations
<a name="BKMK_Security"> </a>

Pour plus d’informations, voir les articles suivants :

- [Déployer des statistiques responsable Skype pour Business Server](deploy.md)

- [Mise à niveau du Gestionnaire de statistiques pour Skype pour Business Server](upgrade.md)

- [Résoudre les statistiques du gestionnaire pour Skype pour Business Server](troubleshoot.md)

- [Blog du gestionnaire de statistiques de Skype Entreprise Server ](https://blogs.technet.microsoft.com/dodeitte/2015/10/24/skype-for-business-server-real-time-statistics-manager)



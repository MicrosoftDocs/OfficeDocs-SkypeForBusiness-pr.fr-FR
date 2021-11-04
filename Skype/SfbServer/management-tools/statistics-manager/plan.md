---
title: Planifier le Gestionnaire de statistiques pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur le Gestionnaire de statistiques pour Skype Entreprise Server.'
ms.openlocfilehash: 79f8bc38169d6cba52160772cd9ba0869e761b30
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778144"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>Planifier le Gestionnaire de statistiques pour Skype Entreprise Server

**Résumé :** Lisez cette rubrique pour en savoir plus sur le Gestionnaire de statistiques Skype Entreprise Server.

 Le Gestionnaire de statistiques Skype Entreprise Server est un outil puissant qui vous permet d’afficher Skype Entreprise Server données d’état et de performances en temps réel. Vous pouvez sonder les données de performances sur des centaines de serveurs toutes les quelques secondes et afficher les résultats instantanément sur le site web du Gestionnaire de statistiques.

Vous pouvez utiliser le Gestionnaire de statistiques pour identifier les problèmes de performances en cours, afficher les résultats d’une modification planifiée de votre environnement, suivre la résolution des pannes et bien plus encore. Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment’s unique needs.

Vous pouvez déployer le Gestionnaire de statistiques dans un déploiement local dans lequel un seul serveur héberge tous les composants du gestionnaire de statistiques côté serveur. Pour plus d’informations sur le déploiement du Gestionnaire de statistiques, voir [Deploy Statistics Manager for Skype Entreprise Server](deploy.md). Si vous avez déjà un déploiement existant du Gestionnaire de statistiques, mais que vous n’avez pas encore mis à niveau vers la version 2.0, consultez Les nouveautés de la version [2.0](plan.md#BKMK_WhatsNew) et le Gestionnaire de statistiques de mise à niveau pour [Skype Entreprise Server](upgrade.md).

Cette rubrique comprend les sections suivantes :

- [Produits et fonctionnalités](plan.md#BKMK_Features)

- [Nouveautés de la version 2.0](plan.md#BKMK_WhatsNew)

- [Composants](plan.md#BKMK_Components)

- [Déploiement local](plan.md#BKMK_DeploymentOptions)

- [Configuration requise](plan.md#BKMK_Requirements)

- [Considérations relatives à la sécurité](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>Produits et fonctionnalités
<a name="BKMK_Features"> </a>

Le Gestionnaire de statistiques vous permet de :

- Afficher les données brutes de tous les serveurs en temps réel. (Les données sont échantillon données à un taux très élevé et envoyées au site web en moins d’une seconde.)

- Afficher les données agrégées pour un rôle spécifique ; par exemple, serveur frontal, serveur de médiation, serveur Edge, etc.

- Descendre pour afficher les données pour des sites spécifiques, des pools spécifiques au sein du site, puis des serveurs spécifiques au sein du pool.

- Créez des graphiques personnalisés afin que les compteurs choisis soient affichés par défaut.

- Zoom et panoramique sur les axes x et y ou sur l’axe x uniquement.

- Utilisez des plages de dates ou des points dans l’heure pour filtrer les données.

- Afficher les performances du serveur en fonction des indicateurs d’état de santé clés établis. Les khis représentent une collection de compteurs de performance avec une plage saine définie.

- Afficher des mesures détaillées pour chaque compteur.

- Comparez les données entre plusieurs populations ou serveurs.

- Afficher les rapports de compteur latents pour identifier les agents qui ne signalent pas les données actuelles au service de tableau de bord.

- Enregistrez une instance particulière de données de graphique dans un fichier.

- Afficher les KHIs en temps réel, y compris les mises à jour. Si l’affichage Historique est activé, seuls les nouveaux échecs sont affichés.

  - Afficher toutes les khis en même temps

  - Afficher les KHIs par serveur (mode Paysage)

  - Afficher les définitions KHI

## <a name="whats-new-in-release-20"></a>Nouveautés de la version 2.0
<a name="BKMK_WhatsNew"> </a>

Ce qui suit décrit les nouveautés de la version 2.0. Si vous avez un déploiement existant du Gestionnaire de statistiques et que vous n’avez pas encore mis à niveau, consultez Upgrade [Statistics Manager pour Skype Entreprise Server](upgrade.md).

- Des affichages de scénario ont été ajoutés pour les scénarios edge media, Fabric Health, Pool Failover et Registration.

- De nombreux nouveaux compteurs ont été ajoutés pour SQL serveurs, d’autres compteurs Skype Entreprise’utilisation, etc.

- Intégration du nœud de l’observeur pour l’agent du gestionnaire de statistiques : si l’agent est installé sur un nœud observeur, il signale les statistiques de transaction synthétique sous forme de compteurs au Gestionnaire de statistiques.

- De nombreuses améliorations en matière de fiabilité et de performances.

Pour vérifier la version du site web du Gestionnaire de statistiques que vous exécutez :

- Dans l’Explorateur de fichiers, ouvrez (répertoire par défaut) C:\Program Files\Skype Entreprise Server StatsMan WebSite\bin

- Cliquez avec le bouton droit StatsManHubWebSite.dll et affichez ses propriétés

- La version du produit s’affiche dans les détails de description.

## <a name="components"></a>Composants
<a name="BKMK_Components"> </a>

Le Gestionnaire de statistiques se compose des composants suivants :

- **Agent.** Agent léger qui s’exécute sur chaque serveur surveillé. L’agent permet l’interrogation à taux élevé configurable des compteurs de performance avec l’agrégation locale.

- **Listener.** API côté serveur qui reçoit des données de tous les agents et regroupe les données entre les populations.

- **Hub.** Sert d’API cliente pour le système, s’exécute sur les serveurs web et fournit des mises à jour de données en temps réel aux clients connectés via le site web. (Le Hub est automatiquement installé dans le cadre du site web msi.)

- **Site web.** Interface utilisateur qui rassemble toutes les fonctionnalités disponibles dans le système.

En outre, le gestionnaire de statistiques requiert **Redis**, un serveur de structure de données open source pour la mise en cache en mémoire. Pour plus d’informations sur le téléchargement de Redis, voir [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .

## <a name="on-premises-deployment"></a>Déploiement sur site
<a name="BKMK_DeploymentOptions"> </a>

Dans un déploiement local, un seul serveur héberge tous les composants du Gestionnaire de statistiques côté serveur.

Le diagramme suivant illustre un déploiement local, dans lequel le site web du gestionnaire de statistiques, le système de mise en cache Hub, Listener et Redis sont hébergés sur un seul ordinateur. Le Gestionnaire de statistiques surveille trois serveurs Skype Entreprise, chacun d’eux avec un seul agent transmettant des données à l’écoute. Les utilisateurs se connectent à un site web unique pour afficher toutes les données agrégées par le Gestionnaire de statistiques :

![Déploiement local du gestionnaire des statistiques.](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>Configuration requise
<a name="BKMK_Requirements"> </a>

Vous devez prendre en compte les configurations logicielle, réseau et matérielle suivantes avant de déployer le Gestionnaire de statistiques.

### <a name="software-requirements"></a>Configuration logicielle requise

- Windows Server 2016 et 2019

- IIS (installé automatiquement)

- Redis

- Services du Gestionnaire de statistiques (installé automatiquement)

- PSExec - Obligatoire pour le déploiement d’agent distant

- .NET 4.5 (inclus avec 2012 R2) : requis pour les agents et les composants côté serveur
- Télécharger le [Skype Entreprise Server, Real-Time Statistics Manager (64 bits)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)

### <a name="networking-requirements"></a>Configuration de réseau requise


|**Serveur d’hébergement**|**Agents**|**Listener**|
|:-----|:-----|:-----|
|Réseau duplex complet gigabit minimum.  <br/> |Port TCP sortant 8443 (numéro de port personnalisable) pour communiquer avec l’port d’écoute.  <br/> |Le port d’écoute doit être le même sur tous les serveurs.  <br/> |
|Le port TCP entrant 80 ou 443 s’ouvre pour héberger le site web.  <br/> |||
|Port TCP entrant 8443 (numéro de port personnalisable) pour que les agents communiquent avec lui.  <br/> |||

Pendant l’installation, les ports de pare-feu pour l’port d’écoute et le site web sont automatiquement créés. Pour les agents, l’installation suppose que les connexions TCP sortantes sont autorisées par défaut.

### <a name="hardware-requirements"></a>Configuration matérielle requise

Dans un déploiement local, dans lequel un seul serveur héberge tous les composants du Gestionnaire de statistiques côté serveur, un serveur avec 16 Go de RAM et 4 processeurs doit pouvoir prendre en charge environ 150 échantillons par seconde en moyenne. Pour déterminer le nombre de compteurs/agents que vous pouvez prendre en charge, utilisez le calcul suivant :

100 serveurs 80 compteurs 1 échantillon par minute de chaque \* \* agent / 60 secondes = ~ 133 échantillons par seconde.

## <a name="security-considerations"></a>Considérations en matière de sécurité
<a name="BKMK_Security"> </a>

Tout le trafic entre les serveurs est chiffré.

- Le trafic HTTPS chiffré sera envoyé sur le port 8443 (par défaut) de l’Agent vers le serveur d’écoute.

- L’agent vérifie l’empreinte SSL sur le serveur pour s’assurer que le serveur d’écoute est le destinataire attendu. Notez que l’agent utilise la vérification de l’empreinte numérique du certificat (au lieu de la vérification de chaîne). Il n’aura pas la validation complète du certificat, car il est possible d’utiliser des certificats auto-signés.

- Une fois que l’agent est satisfait que l’écoute est authentifiée, un mot de passe est présenté par l’agent qui est ensuite vérifié par l’écoute.

- L’agent commence à transmettre les données de performances sur la connexion à l’écoute.

## <a name="for-more-information"></a>Pour plus d'informations
<a name="BKMK_Security"> </a>

Pour plus d'informations, consultez les articles suivants :

- [Déploiement du gestionnaire de statistiques pour Skype Entreprise Server](deploy.md)

- [Mise à niveau du gestionnaire de statistiques pour Skype Entreprise Server](upgrade.md)

- [Dépannage du gestionnaire de statistiques pour Skype Entreprise Server](troubleshoot.md)

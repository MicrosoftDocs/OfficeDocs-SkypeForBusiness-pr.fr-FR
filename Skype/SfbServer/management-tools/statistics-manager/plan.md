---
title: Planifier le gestionnaire de statistiques pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Résumé : cette rubrique vous explique en savoir plus sur le gestionnaire de statistiques pour Skype entreprise Server.'
ms.openlocfilehash: 0bf7a5366047a0f4435a98cd8bca75eeb3ebc8d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816233"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>Planifier le gestionnaire de statistiques pour Skype Entreprise Server

**Résumé :** Consultez cette rubrique pour en savoir plus sur le gestionnaire de statistiques pour Skype entreprise Server.

 Le Gestionnaire de statistiques pour Skype Entreprise Server est un outil puissant qui permet de consulter Skype pour l’état et les performances des données entreprise Server en temps réel. Vous pouvez interroger les données de performances sur des centaines de serveurs à des intervalles de quelques secondes et afficher les résultats instantanément sur le site Web de Gestionnaire de Statistiques.

Vous pouvez utiliser le gestionnaire de statistiques pour identifier les problèmes de performances en cours, afficher les résultats d’un changement planifié pour votre environnement, suivre la résolution des pannes et bien plus encore. Le gestionnaire de statistiques est configuré à l’aide des seuils d’indicateur d’intégrité clé (KHI) et peut être personnalisé pour répondre aux besoins uniques de votre déploiement.

Vous pouvez déployer le gestionnaire de statistiques dans un déploiement local dans lequel un serveur unique héberge tous les composants gestionnaires de statistiques côté serveur. Pour plus d’informations sur le déploiement du gestionnaire de statistiques, voir [déploiement de statistiques pour Skype entreprise Server](deploy.md). Si vous disposez déjà d’un déploiement de Statistics Manager, mais que vous n’avez pas encore effectué la mise à niveau vers la version 2,0, voir [Nouveautés de la version 2,0](plan.md#BKMK_WhatsNew) et [mise à niveau du gestionnaire de statistiques pour Skype entreprise Server](upgrade.md).

Cette rubrique contient les sections suivantes :

- [Fonctionnalités et fonctionnalités](plan.md#BKMK_Features)

- [Nouveautés de la version 2,0](plan.md#BKMK_WhatsNew)

- [Composants](plan.md#BKMK_Components)

- [Déploiement local](plan.md#BKMK_DeploymentOptions)

- [Configuration requise](plan.md#BKMK_Requirements)

- [Considérations en matière de sécurité](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>Fonctionnalités et fonctionnalités
<a name="BKMK_Features"> </a>

Le gestionnaire de statistiques vous permet d’effectuer les opérations suivantes :

- Affichez des données brutes pour tous les serveurs en temps réel. (Les données sont échantillonnées à un tarif très élevé et envoyées au site Web en moins d’une seconde.)

- Afficher des données agrégées pour un rôle spécifique ; par exemple, serveur frontal, serveur de médiation, serveur Edge, etc.

- Explorez les données vers le bas pour afficher les données de sites spécifiques, des pools spécifiques au sein du site, puis des serveurs spécifiques au sein de la liste.

- Créez des graphiques personnalisés de telle sorte que les compteurs sélectionnés apparaissent par défaut.

- Effectuer un zoom et un panoramique sur les axes x et y ou sur l’axe x uniquement.

- Utiliser des plages de dates ou des points dans le temps pour filtrer des données.

- Affichez les performances du serveur sur la base des indicateurs d’État clés (KHIs). KHIs représenter une collection de compteurs de performance avec une plage correcte définie.

- Affichez des mesures détaillées pour chaque compteur.

- Comparer les données entre plusieurs populations ou serveurs.

- Afficher les rapports de compteurs latent pour identifier les agents qui ne signalent pas de données actuelles au service de tableau de bord.

- Enregistrez une instance particulière de données de graphique dans un fichier.

- Affichez KHIs en temps réel, y compris les mises à jour. Si la vue historique est activée, seules les nouvelles erreurs sont affichées.

  - Afficher tous les KHIs en une seule fois

  - Afficher KHIs par serveur (vue paysage)

  - Afficher les définitions KHI

## <a name="whats-new-in-release-20"></a>Nouveautés de la version 2,0
<a name="BKMK_WhatsNew"> </a>

Les rubriques suivantes décrivent les nouveautés de la version 2,0. Si vous avez un déploiement de Statistics Manager et que vous n’avez pas encore effectué la mise à niveau, reportez-vous à la rubrique [mise à niveau du gestionnaire de statistiques pour Skype entreprise Server](upgrade.md).

- Des affichages de scénario ont été ajoutés pour des scénarios de média, d’intégrité de fabrique et de basculement de pool.

- De nombreux nouveaux compteurs ont été ajoutés pour les serveurs SQL Server, d’autres compteurs d’utilisation Skype entreprise, etc.

- Intégration de nœud d’observateur pour l’agent gestionnaire de statistiques-si l’agent est installé sur un nœud de l’observateur, il signalera les statistiques de transaction synthétique en tant que compteurs aux statistiques Manager.

- De nombreuses améliorations liées à la fiabilité et aux performances.

Pour vérifier la version du site Web du gestionnaire de statistiques que vous exécutez :

- Dans l’Explorateur de fichiers, ouvrez (répertoire par défaut) C:\Program Files\Skype entreprise Server Stats WebSite\bin

- Cliquer avec le bouton droit sur StatsManHubWebSite. dll et afficher ses propriétés

- La version du produit s’affiche dans les détails de la description.

## <a name="components"></a>Composants
<a name="BKMK_Components"> </a>

Le gestionnaire de statistiques comprend les composants suivants :

- **Représentant.** Un agent léger qui s’exécute sur chaque serveur surveillé. L’agent autorise une interrogation de haut débit configurable des compteurs de performance avec une agrégation locale.

- **Écouteur.** API côté serveur qui reçoit les données de tous les agents et agrège les données entre les populations.

- **Raccord.** Sert d’API client pour le système, s’exécute sur le ou des serveurs Web et fournit des mises à jour de données en temps réel aux clients connectés via le site Web. (Le concentrateur est automatiquement installé en même temps que le site Web msi.)

- **Associates.** Une interface utilisateur qui rassemble toutes les fonctionnalités disponibles dans le système.

De plus, le gestionnaire de statistiques nécessite des **ReDim**, un serveur de structure de données en source d’ouverture pour la mise en cache en mémoire. Pour plus d’informations sur le téléchargement de ReDim, voir [déploiement de statistiques](deploy.md#BKMK_Deploy) .

## <a name="on-premises-deployment"></a>Déploiement local
<a name="BKMK_DeploymentOptions"> </a>

Dans un déploiement local, un serveur unique héberge tous les composants du gestionnaire de statistiques côté serveur.

Le diagramme suivant illustre un déploiement local, dans lequel le site Web du gestionnaire de statistiques, le concentrateur, l’écouteur et le système de mise en cache de ReDim sont hébergés sur un seul ordinateur. Le gestionnaire de statistiques analyse trois serveurs Skype entreprise, chacun d’eux disposant d’un seul agent pour transmettre des données à l’écouteur. Les utilisateurs se connectent à un site Web unique pour afficher toutes les données agrégées par le gestionnaire de statistiques :

![Déploiement sur site du gestionnaire de statistiques](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>Configuration requise
<a name="BKMK_Requirements"> </a>

Avant de déployer Statistics Manager, vous devez tenir compte des éléments suivants concernant le logiciel, la mise en réseau et la configuration matérielle requise.

### <a name="software-requirements"></a>Configuration logicielle requise

- Windows Server 2016 et 2019

- IIS (installé automatiquement)

- Redis géré

- Services du gestionnaire de statistiques (installés automatiquement)

- PSExec-requis pour le déploiement d’agent distant

- .NET 4,5 (inclus avec 2012 R2)-requis pour les agents et les composants côté serveur
- Télécharger [Skype entreprise Server, gestionnaire de statistiques en temps réel (64)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)

### <a name="networking-requirements"></a>Configuration réseau requise


|**Serveur d’hébergement**|**Agents**|**Écouteur**|
|:-----|:-----|:-----|
|Mise en réseau Gigabit duplex intégral minimum.  <br/> |Port TCP sortant 8443 (numéro de Port personnalisable) pour communiquer avec l’écouteur.  <br/> |Le port d’écoute doit être le même sur tous les serveurs.  <br/> |
|Port TCP entrant 80 ou 443 ouvert pour héberger le site Web.  <br/> |||
|Port TCP entrant 8443 (numéro de Port personnalisable) pour que les agents puissent communiquer avec lui.  <br/> |||

Lors de l’installation, les ports de pare-feu pour l’écouteur et le site Web sont automatiquement créés. Pour les agents, l’installation part du principe que les connexions TCP sortantes sont autorisées par défaut.

### <a name="hardware-requirements"></a>Configuration matérielle requise

Dans un déploiement local, dans lequel un serveur unique héberge tous les composants gestionnaires de statistiques côté serveur, un serveur doté de 16 Go de mémoire vive (RAM) et de 4 UC doit être en mesure de prendre en charge des exemples de 150 par seconde en moyenne. Pour déterminer le nombre de compteurs/agents pris en charge, procédez comme suit :

100 serveurs \*80 compteurs \* 1 exemple par minute de chaque agent/60 secondes = ~ 133 exemples par seconde.

## <a name="security-considerations"></a>Considérations en matière de sécurité
<a name="BKMK_Security"> </a>

Tout le trafic entre les serveurs est crypté.

- Le trafic HTTPs chiffré sera envoyé via le port 8443 (par défaut) de l’agent au serveur d’écouteur.

- L’agent vérifie l’empreinte SSL du serveur pour vérifier que le serveur de l’écouteur est le destinataire attendu. Notez que l’agent utilise la vérification de l’empreinte de certificat (au lieu de la vérification de la chaîne). Il n’effectue pas de validation de certificat complète, car il est possible d’utiliser des certificats auto-signés.

- Dès lors que l’agent est satisfait, l’écouteur est authentifié et un mot de passe est présenté par l’agent qui est ensuite vérifié par l’écouteur.

- L’agent commence à transmettre les données de performances par le biais de la connexion à l’écouteur.

## <a name="for-more-information"></a>Pour plus d'informations
<a name="BKMK_Security"> </a>

Pour plus d'informations, voir les articles suivants :

- [Déploiement du gestionnaire de statistiques pour Skype Entreprise Server](deploy.md)

- [Mise à niveau du gestionnaire de statistiques pour Skype Entreprise Server](upgrade.md)

- [Dépannage du gestionnaire de statistiques pour Skype Entreprise Server](troubleshoot.md)

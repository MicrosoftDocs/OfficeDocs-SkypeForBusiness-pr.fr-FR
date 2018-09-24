---
title: Interopérabilité vidéo cloud pour les équipes Microsoft
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: srividhc
description: Nuage vidéo Interop permet de tiers équipements de salle pour participer à des réunions Teams Microsoft de la réunion.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3ff5cd20c490e69f2c18487f8aaf42905870597
ms.sourcegitcommit: 2d76fad92b6d6c5d1bd223a717fd6c534ecaa5be
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/24/2018
ms.locfileid: "24974422"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Interopérabilité vidéo cloud pour les équipes Microsoft

Nuage vidéo Interop permet de tiers équipements de salle pour participer à des réunions Teams Microsoft de la réunion.

Vidéoconférence avec la collaboration de contenu vous permettra de tirer le meilleur parti des réunions. Salle de réunion, toutefois, les systèmes et périphériques sont coûteux en termes de mise à niveau. Interopérabilité de vidéo dans le nuage pour Microsoft Teams fonctionne avec les systèmes et offre une expérience de réunion natif pour tous les participants – dans les salles de réunion ou à l’intérieur clients équipes. 

## <a name="partners-certified-for-microsoft-teams"></a>Partenaires certifiés pour les équipes Microsoft

Les partenaires suivants ont des solutions d’interopérabilité vidéo pour Microsoft Teams. Votre société peut choisir de travailler avec n’importe quelle combinaison de ces partenaires au sein de votre entreprise. 


|Partenaire|Solution d’un partenaire|Disponibilité|
|----|---|----|
|![RealConnect de Polycom](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Polycom RealConnect pour Office 365</a> |Désormais disponible|
|![Infini Pexip](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Infini Pexip pour les équipes Microsoft</a> | 19 octobre 2018|
|![Passerelle blueJeans](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">Passerelle blueJeans pour les équipes Microsoft</a> | 31 octobre 2018|

## <a name="partner-solutions"></a>Solutions de partenaires

Nos partenaires ont développé des solutions de passerelle pour connecter des périphériques tiers basés sur des normes SIP et H.323 aux réunions Microsoft Teams.  
 
**Certifié et pris en charge par Microsoft**

- Disponible uniquement via les Solutions de partenaires certifiés
- CO-conçu avec Microsoft
- Client TAP avant de certification

**Prêt d’entreprise**

- Vidéo HD (1080p) et contenu (VBSS)
- Prise en charge H.323 et équipements de salle de réunion de SIP-équipes/Exchange Native planification - conception de passerelle au lieu de VMR

**Évolutivité pour le cloud**

- Déployée et gérée dans Azure
- À l’échelle automatique avec des solutions de nuage

 
## <a name="reference-architecture"></a>Architecture de référence

Le diagramme suivant décrit l’architecture de haut niveau d’une solution de partenaire équipes.

![Solution d’un partenaire en nuage vidéo Interop équipes](media/teams-cloud-video-interop-partner-solution.png)

## <a name="key-business-considerations"></a>Considérations relatives à la clé d’entreprise

**Microsoft Teams à côté de l’infrastructure vidéo 3P**

- Avez-vous besoin d’un déploiement important des périphériques vidéo 3P ?
- Existe-t-il un 3P contrôleur d’appel dans votre organisation ?
- Vous prévoyez de conserver votre contrôleur d’appel en cours avec Microsoft Teams
- Vous souhaitez exécuter votre propre vidéo infra ou hébergée ? 
- Avez-vous prévu sur le déploiement de systèmes de salle équipes ? Quand ?

**Préexistant certifié fournisseur d’interopérabilité de base**

- Vous souhaitez poursuivre votre partenaire certifié actuel ?
- Avez-vous besoin continuer la prise en charge de l’environnement intégré (Exchange, une numérotation tactile) ?

**Autres composants requis**

- Avez-vous besoin de surveillance en temps réel, dépannage et fonctionnalités de création de rapports ?
- Vous devez être disponibles dans les nuages souverains ou gouvernement ?
- Avez-vous besoin de participer à des réunions de vos équipes de sociétés externes ? 

## <a name="business-workflow-scenarios"></a>Les scénarios de flux de travail

- **Skype pour Business Server -> équipes Microsoft :** Votre organisation dispose de périphériques tiers et transfert des Skype pour Business sur prem server vers Microsoft Teams  
- **Skype pour les entreprises-en ligne > Microsoft Teams :** Votre organisation est migré vers Microsoft Teams Skype pour Business Online.
- **Cisco UC -> équipes Microsoft :** Votre organisation est déplacé à partir de Cisco à Microsoft Teams, mais pas prêt à remplacer vos périphériques Cisco.
- **Englobant des systèmes -> équipes Microsoft :** Votre organisation dispose de plusieurs systèmes dans votre environnement côte à côte (Cisco, BroadSoft, SfB Server, SfBO).
- **Un autre fournisseur de conférence dans le nuage -> Microsoft Teams :** Votre organisation a été d’un utilisateur pour un autre fournisseur de conférence dans le nuage migration vers Microsoft Teams.


Après avoir choisi un partenaire ou partenaires, vous êtes prêt à [configurer sur le nuage vidéo Interop pour les équipes Microsoft](cloud-video-interop-for-teams-set-up.md). 
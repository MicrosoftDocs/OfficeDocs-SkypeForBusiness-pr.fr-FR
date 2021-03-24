---
title: Étude de cas Teams voix Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Étude de cas Voix Teams pour une entreprise multinationale
appliesto:
- Microsoft Teams
ms.openlocfilehash: b0da56bc0da083654a0cd694bd5983f2fe4fe515
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093724"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Étude de cas Contoso : plan de mise à niveau de Teams

En souhaitant migrer Skype Entreprise vers Teams, Contoso souhaitait offrir une expérience de transition facile aux utilisateurs finaux. Au lieu de basculer tout le monde vers Teams en même temps, ils ont décidé de configurer la connectivité hybride et d’utiliser la méthode des capacités superposées pour déplacer les utilisateurs vers Teams. Cela permettait aux utilisateurs de Teams et de Skype Entreprise sur site de partager les informations de présence et de communication. Lorsque les utilisateurs ont entré le pilote du système téléphonique, ils ont été déplacés en mode Teams uniquement.

Pour comprendre les concepts fondamentaux de la mise à niveau, des méthodes et des modes, Contoso lit les articles suivants :

- [Prise en main de votre mise à niveau de Microsoft Teams](upgrade-start-here.md)
- [Stratégies de mise à niveau pour les administrateurs informatiques](upgrade-to-teams-on-prem-implement.md) 
- [Conseils sur la migration et l’interopérabilité](migration-interop-guidance-for-teams-with-skype.md)
 
Contoso a également participé à la session Ignite 2019 concevant votre chemin de [Skype Entreprise à Teams.](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions) Contoso a appris les sujets :

- Concepts fondamentaux tels que l’interopérabilité, la fédération et le comportement de mise à niveau 

- Modes de coexistence et gestion basés sur TeamsUpgradePolicy 

- Expérience utilisateur final pour : 

  - Conversation et appels 

  - Planification de réunions 

  - Disponibilité de la fonctionnalité de collaboration dans les clients Teams 

Pour planifier et configurer la connectivité hybride, la première étape du déplacement de leur [](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) environnement local [](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) vers le cloud, Contoso lit Planifier la connectivité hybride et Configurer la connectivité hybride pour comprendre comment : 

  - Configurez leur service d’environnement local de manière à ce qu’il se fédérera avec Office 365. 

  - Configurer leur environnement local pour faire confiance à Office 365 et activer l’espace d’adressare SIP partagé avec Office 365 

  - Activez l’espace d’adresse SIP partagé dans son client Office 365.

  - Utilisez le mode Îles pendant le pilote technique.

  - Basculez les utilisateurs en mode TeamsOnly une fois que l’utilisateur est activé pour Phone System. Le mode TeamsOnly est requis pour le plan d’appel et le routage direct.
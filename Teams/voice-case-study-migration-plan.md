---
title: Teams plan de mise à niveau de l’étude de cas contoso vocale
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
description: 'Teams étude de cas de voix pour une société multinationale : Planification de la mise à niveau.'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39cfd66f0ff34fb0f8792871ddfdcceebb2b9961
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/01/2022
ms.locfileid: "65822983"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Étude de cas Contoso : plan de mise à niveau Teams

Lors de la décision de migrer de Skype Entreprise vers Teams, Contoso souhaitait offrir une expérience de transition facile aux utilisateurs finaux. Au lieu de basculer tout le monde vers Teams en même temps, ils ont décidé de configurer la connectivité hybride et d’utiliser la méthode des fonctionnalités qui se chevauchent pour déplacer les utilisateurs vers Teams. Cela a permis aux utilisateurs dans Teams et Skype Entreprise localement de partager la présence et de communiquer. Lorsque les utilisateurs sont entrés dans le pilote pour Système téléphonique, ils ont été déplacés vers Teams mode Uniquement.

Pour comprendre les concepts fondamentaux de la mise à niveau, des méthodes et des modes, Contoso lit les articles suivants :

- [Prise en main de votre mise à niveau de Microsoft Teams](upgrade-start-here.md)
- [Stratégies de mise à niveau pour les administrateurs informatiques](upgrade-to-teams-on-prem-implement.md) 
- [Guide de migration et d’interopérabilité](migration-interop-guidance-for-teams-with-skype.md)
 
Contoso a également participé à la session Ignite 2019 [Concevoir votre chemin d’Skype Entreprise à Teams](https://myignite.microsoft.com/archives/IG20-OD251). Contoso a découvert les informations suivantes :

- Concepts fondamentaux tels que l’interopérabilité, la fédération et le comportement de mise à niveau 

- Modes de coexistence et gestion basés sur TeamsUpgradePolicy 

- Expérience de l’utilisateur final pour : 

  - Conversation et appel 

  - Planification des réunions 

  - Disponibilité des fonctionnalités de collaboration dans les clients Teams 

Pour planifier et configurer la connectivité hybride, première étape du déplacement de son environnement local vers le cloud, Contoso lit [Plan hybrid connectivity](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) et [Configure hybrid connectivity](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) pour comprendre comment : 

  - Configurez leur service d’environnement local pour qu’il se fédère avec Office 365. 

  - Configurez leur environnement local pour approuver Office 365 et activer l’espace d’adressage SIP partagé avec Office 365 

  - Activez l’espace d’adressage SIP partagé dans son locataire Office 365.

  - Utilisez le mode Îles pendant le pilote technique.

  - Basculez les utilisateurs en mode TeamsOnly une fois que l’utilisateur est activé pour Système téléphonique. Le mode TeamsOnly est requis pour le plan d’appel et le routage direct.

---
title: Teams de mise à niveau d’étude de cas Contoso voix
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
description: 'Teams cas de voix pour une entreprise multinationale : planification de la mise à niveau.'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c2d64e93e8f9ab53cd2a696af69de4b7f0d4f7348fec27a189b60896ee1ec02
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54350176"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Étude de cas Contoso : planifier Teams mise à niveau

En décision de migrer d’Skype Entreprise à Teams, Contoso souhaitait offrir une expérience de transition facile aux utilisateurs finaux. Au lieu de basculer tout le monde Teams en même temps, ils ont décidé de configurer la connectivité hybride et d’utiliser la méthode des capacités superposées pour déplacer les utilisateurs vers Teams. Cela permettait aux utilisateurs Teams et Skype Entreprise de communiquer en local et de communiquer. Lorsque les utilisateurs ont entré le pilote pour Système téléphonique, ils ont été déplacés en Teams mode Seul.

Pour comprendre les concepts fondamentaux de la mise à niveau, des méthodes et des modes, Contoso lit les articles suivants :

- [Prise en main de votre mise à niveau de Microsoft Teams](upgrade-start-here.md)
- [Stratégies de mise à niveau pour les administrateurs informatiques](upgrade-to-teams-on-prem-implement.md) 
- [Conseils sur la migration et l’interopérabilité](migration-interop-guidance-for-teams-with-skype.md)
 
Contoso a également participé à la session Ignite 2019 Concevant votre chemin d’accès de [Skype Entreprise à Teams.](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions) Contoso a appris les sujets :

- Concepts fondamentaux tels que l’interopérabilité, la fédération et le comportement de mise à niveau 

- Modes de coexistence et gestion basés sur TeamsUpgradePolicy 

- Expérience utilisateur final pour : 

  - Conversation et appel 

  - Planification de réunions 

  - Disponibilité de la fonctionnalité de collaboration dans Teams clients 

Pour planifier et configurer la connectivité hybride, la première étape du déplacement de leur [](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) environnement local [](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) vers le cloud, Contoso lit Planifier la connectivité hybride et Configurer la connectivité hybride pour comprendre comment : 

  - Configurez leur service d’environnement local de manière à ce qu’il Office 365. 

  - Configurez leur environnement local pour faire confiance à des utilisateurs Office 365 et activer l’espace d’adresse SIP partagé avec Office 365 

  - Activez l’espace d’adresse SIP partagé dans Office 365 client.

  - Utilisez le mode Îles pendant le pilote technique.

  - Basculez les utilisateurs en mode TeamsOnly une fois que l’utilisateur est activé pour Système téléphonique. Le mode TeamsOnly est requis pour le plan d’appels et le routage direct.

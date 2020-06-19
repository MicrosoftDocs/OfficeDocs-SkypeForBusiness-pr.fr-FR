---
title: Étude de cas de voix contoso teams
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
description: Étude de cas de voix dans teams pour les entreprises à plusieurs nationaux
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786020"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Étude de cas contoso : plan de mise à niveau des équipes

Dans la décision de migrer de Skype entreprise vers Teams, contoso voulait offrir une interface de transition facile pour les utilisateurs finaux. Au lieu de basculer tous les membres vers teams en même temps, ils ont décidé de configurer une connectivité hybride et de recourir à la méthode de superposition pour déplacer des utilisateurs vers Teams. Cela permettait aux utilisateurs de Microsoft teams et de Skype entreprise local de partager leur présence et de communiquer avec eux. Lorsque les utilisateurs ont entré le pilote pour le système téléphonique, ils ont été déplacés vers le mode équipes uniquement.

Pour comprendre les concepts fondamentaux liés à la mise à niveau, aux méthodes et aux modes, Contoso a lu les articles suivants :

- [Prise en main de votre mise à niveau de Microsoft Teams](upgrade-start-here.md)
- [Mise à niveau de Skype Entreprise vers Teams](upgrade-to-teams-on-prem-overview.md) 
- [Recommandations en matière de migration et d’interopérabilité](migration-interop-guidance-for-teams-with-skype.md)
 
Contoso a également participé à la session d’enflammer 2019 [qui concevait votre chemin entre Skype entreprise et teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions). Contoso a appris ce qui suit :

- Concepts de base, tels que le comportement d’interopérabilité, de Fédération et de mise à niveau 

- Modes et gestion de coexistence basés sur TeamsUpgradePolicy 

- Utilisation de l’utilisateur final pour : 

  - Discussions et appels 

  - Planification de réunions 

  - Disponibilité des fonctionnalités de collaboration dans les clients teams 

Pour planifier et configurer une connectivité hybride, vous devez commencer par déplacer son environnement local vers le Cloud, contoso lire le [plan de connexion hybride](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) et [configurer une connectivité hybride](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) pour comprendre comment : 

  - Configurez son service d’environnement local pour qu’il se fédérer avec Office 365. 

  - Configurer son environnement local pour faire confiance à Office 365 et activer l’espace d’adressage SIP partagé avec Office 365 

  - Activez l’espace d’adressage SIP partagé dans le client Office 365.

  - Utiliser le mode insulaire lors du pilotage technique.

  - Basculer les utilisateurs vers le mode TeamsOnly une fois l’utilisateur activé pour le système téléphonique. Le mode TeamsOnly est requis pour le plan d’appel et le routage direct. 

---
title: Effectuer une mise à niveau vers teams à partir d’un déploiement local de Skype entreprise-Microsoft teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Mise à niveau de Skype Entreprise vers Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cf034969c2b6ca030eede72ff358a517fafe501f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533591"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a>Considérations en matière de mise à niveau pour les organisations avec Skype entreprise Server en local &mdash; pour les administrateurs informatiques

Cet article décrit des considérations supplémentaires pour les organisations avec Skype entreprise Server en local. Cet article est le quatrième d’une description de la mise à niveau et de l’implémentation pour les administrateurs informatiques.  

- [Vue d’ensemble](upgrade-to-teams-on-prem-overview.md)
- [Méthodes de mise à niveau](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Outils de gestion de votre mise à niveau](upgrade-to-teams-on-prem-tools.md)
- **Remarques supplémentaires pour les organisations avec Skype entreprise local** (cet article)
- [Implémentation de votre mise à niveau](upgrade-to-teams-on-prem-implement.md)
- [Considérations relatives au réseau téléphonique public commuté (RTC)](upgrade-to-teams-on-prem-pstn-considerations.md)

De plus, les articles suivants décrivent des concepts importants de mise à niveau et des comportements de coexistence :

- [Coexistence des équipes et de Skype entreprise](upgrade-to-teams-on-prem-coexistence.md)
- [Modes de coexistence-référence](migration-interop-guidance-for-teams-with-skype.md)
- [Expérience client Teams et conformité aux modes coexistence](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Remarques concernant les organisations avec Skype entreprise Server en local

- La configuration de Skype entreprise hybride est une condition préalable à la migration vers le mode TeamsOnly. Même s’il est possible d’utiliser les équipes en mode d’îlot sans qu’elles soient hybrides, la transition vers le mode TeamsOnly ne peut pas être effectuée tant que l’utilisateur n’est pas transféré de Skype entreprise sur site à Skype entreprise Online (via [Move-Csuser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)). Pour plus d’informations, voir [configurer une connectivité hybride](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).

- Si votre organisation possède Skype entreprise Server et que vous n’avez pas configuré une connectivité hybride, mais que vous voulez toujours utiliser Teams, vous devez utiliser un compte administratif doté d’un domaine. onmicrosoft.com pour gérer les fonctionnalités d’équipe. 

- Les utilisateurs teams disposant d’un compte Skype entreprise local (autrement dit, ils n’ont pas encore été déplacés vers le Cloud à l’aide de Move-CsUser) ne peuvent pas interagir avec des utilisateurs de Skype entreprise, et ne peuvent pas être fédérer avec des utilisateurs externes. Cette fonctionnalité n’est disponible que lorsque les utilisateurs sont déplacés vers le Cloud (en mode îlot ou en tant qu’utilisateurs TeamsOnly). 

- Si vous avez des utilisateurs avec des comptes Skype entreprise en local, vous ne pouvez pas affecter le mode TeamsOnly au niveau du client. Vous devez tout d’abord déplacer tous les utilisateurs disposant d’un compte Skype entreprise local dans le Cloud à l’aide de `Move-CsUser` , puis [désactiver l’environnement hybride pour terminer la migration vers le Cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` ne fonctionnera pas au niveau du client si un enregistrement DNS lyncdiscover est détecté et pointe vers un emplacement autre qu’Office 365.

- Vous devez vous assurer que vos utilisateurs sont correctement synchronisés avec Azure AD avec les attributs Skype entreprise appropriés. Ces attributs sont des préfixes avec « msRTCSIP- ». Si les utilisateurs ne sont pas synchronisés correctement avec Azure AD, les outils de gestion dans Teams ne seront pas en mesure de gérer ces utilisateurs. Par exemple, vous ne serez pas en mesure d’affecter des stratégies d’équipe aux utilisateurs locaux, sauf si vous synchronisez correctement ces attributs. Pour plus d’informations, reportez-vous à la rubrique [configuration d’Azure ad Connect pour les équipes et Skype entreprise](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).

- Pour créer un nouveau TeamsOnly ou un utilisateur de Skype entreprise Online au sein d’une organisation hybride, *vous devez d’abord activer l’utilisateur dans Skype entreprise Server en local*, puis déplacer l’utilisateur de local vers le Cloud à l’aide de Move-Csuser.  La création de l’utilisateur sur site permet de s’assurer que tous les autres utilisateurs Skype entreprise restants pourront diriger vers l’utilisateur nouvellement créé. Une fois tous les utilisateurs déplacés en ligne, il n’est plus nécessaire d’activer d’abord les utilisateurs en local.

- Lorsque l’utilisateur passe du Cloud local, les réunions organisées par cet utilisateur sont déplacées vers Skype entreprise Online ou Teams, selon que le commutateur-MoveToTeams est ou non spécifié.

- Si vous souhaitez afficher les notifications dans le client Skype entreprise pour les utilisateurs locaux, vous devez utiliser TeamsUpgradePolicy dans l’ensemble d’outils local. Seul le paramètre NotifySfbUsers est pertinent pour les utilisateurs locaux.  Les utilisateurs sur site reçoivent leur mode provenant des instances en ligne d’TeamsUpgradePolicy. Voir les remarques dans [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). 

>[!NOTE]
> Tout nouveau client créé après le 3 septembre 2019 est créé en tant que client TeamsOnly, sauf si l’organisation a déjà un déploiement local de Skype entreprise Server. Microsoft utilise des enregistrements DNS pour identifier les organisations serveur Skype entreprise locales. Si votre organisation possède un serveur Skype entreprise local sans aucune entrée DNS publique, vous devrez appeler le support Microsoft pour que votre nouveau client soit mis à niveau. 













## <a name="related-links"></a>Liens connexes

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md) 

[Configurer une connectivité hybride entre Skype entreprise Server et Microsoft 365 ou Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Utiliser le service de migration de réunion (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)


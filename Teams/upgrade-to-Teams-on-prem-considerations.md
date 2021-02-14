---
title: Mise à niveau vers Teams à partir d’un déploiement local de Skype Entreprise - Microsoft Teams
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
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a>Considérations en cas de mise à niveau pour les organisations avec Skype Entreprise Server sur site &mdash; pour les administrateurs informatiques

Cet article décrit des considérations supplémentaires pour les organisations qui utilisent Skype Entreprise Server en local. Cet article est le quatrième de ceux qui décrivent les concepts de mise à niveau et d’implémentation pour les administrateurs informatiques.  

- [Vue d’ensemble](upgrade-to-teams-on-prem-overview.md)
- [Méthodes de mise à niveau](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Outils de gestion de votre mise à niveau](upgrade-to-teams-on-prem-tools.md)
- **Considérations supplémentaires pour les organisations avec Skype Entreprise en local** (cet article)
- [Mise en œuvre de votre mise à niveau](upgrade-to-teams-on-prem-implement.md)
- [Considérations sur le réseau téléphonique commuté (PSTN)](upgrade-to-teams-on-prem-pstn-considerations.md)

De plus, les articles suivants décrivent les concepts de mise à niveau et les comportements de coexistence importants :

- [Coexistence de Teams et de Skype Entreprise](upgrade-to-teams-on-prem-coexistence.md)
- [Modes de coexistence - Référence](migration-interop-guidance-for-teams-with-skype.md)
- [Expérience client Teams et conformité aux modes coexistence](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Considérations pour les organisations avec Skype Entreprise Server en local

- La configuration de Skype Entreprise hybride est une condition préalable pour migrer vers le mode TeamsOnly. S’il est possible d’utiliser Teams en mode Îles sans utiliser le mode hybride, la transition vers le mode TeamsOnly ne peut pas être réalisée tant que l’utilisateur n’a pas été déplacé de Skype Entreprise en local vers Skype Entreprise Online (à l’aide de [Move-CsUser).](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) Pour plus d’informations, [voir Configurer la connectivité hybride.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)

- Si votre organisation dispose de Skype Entreprise Server et que vous n’avez pas configuré de connectivité hybride, mais que vous souhaitez continuer à utiliser Teams, pour gérer la fonctionnalité Teams, vous devez utiliser un compte d’administration avec un domaine .onmicrosoft.com. 

- Les utilisateurs de Teams qui ont un compte Skype Entreprise en local (autrement dit, ils n’ont pas encore été déplacés vers le cloud à l’aide de Move-CsUser) ne peuvent pas interopérables avec les utilisateurs Skype Entreprise et ne peuvent pas se fédérer avec des utilisateurs externes. Cette fonctionnalité n’est disponible que lorsque les utilisateurs sont déplacés vers le cloud (soit en mode Îles, soit en tant qu’utilisateurs de TeamsOnly). 

- Si des utilisateurs ont des comptes Skype Entreprise en local, vous ne pouvez pas affecter le mode TeamsOnly au niveau du client. Vous devez d’abord déplacer tous les utilisateurs utilisant des comptes Skype Entreprise locaux vers le cloud, puis désactiver la migration hybride vers `Move-CsUser` [le cloud.](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` ne fonctionne pas au niveau du client si un enregistrement DNS lyncdiscover est détecté qui pointe vers un emplacement autre qu’Office 365.

- Vous devez vous assurer que vos utilisateurs sont correctement synchronisés dans Azure AD avec les attributs Skype Entreprise appropriés. Ces attributs sont tous des préfixes avec « msRTCSIP- ». Si les utilisateurs ne sont pas correctement synchronisés avec Azure AD, les outils de gestion dans Teams ne pourront pas gérer ces utilisateurs. (Par exemple, vous ne pourrez pas affecter de stratégies Teams à des utilisateurs locaux, sauf si vous synchronisez correctement ces attributs.) Pour plus d’informations, [consultez Configurer Azure AD Connect pour Teams et Skype Entreprise.](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)

- Pour créer un utilisateur TeamsOnly ou Skype Entreprise Online dans une organisation hybride, vous devez d’abord activer l’utilisateur dans Skype Entreprise *Server* sur site, puis le déplacer de l’utilisateur de l’environnement local vers le cloud à l’aide de Move-CsUser.  La création de l’utilisateur sur site garantit d’abord que tout autre utilisateur de Skype Entreprise local restant pourra router vers l’utilisateur nouvellement créé. Une fois tous les utilisateurs déplacés en ligne, il n’est plus nécessaire d’activer les utilisateurs en local.

- Lorsqu’un utilisateur est déplacé du cloud en local, les réunions organisées par cet utilisateur sont déplacées vers Skype Entreprise Online ou Teams, selon que le commutateur -MoveToTeams est spécifié ou non.

- Si vous souhaitez afficher les notifications dans le client Skype Entreprise pour les utilisateurs locaux, vous devez utiliser TeamsUpgradePolicy dans le groupe d’outils local. Seul le paramètre NotifySfbUsers est pertinent pour les utilisateurs locaux.  Les utilisateurs sur site reçoivent leur mode depuis les instances en ligne de TeamsUpgradePolicy. Consultez les notes [dans Grant-CsTeamsUpgradePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) 

>[!NOTE]
> Les nouveaux clients créés après le 3 septembre 2019 sont créés en tant que clients TeamsOnly, sauf si l’organisation dispose déjà d’un déploiement local de Skype Entreprise Server. Microsoft utilise les enregistrements DNS pour identifier les organisations Skype Entreprise Server locales. Si votre organisation a un serveur Skype Entreprise local sans entrée DNS publique, vous devez appeler le Support Microsoft pour que votre nouveau client soit rétrogradé. 













## <a name="related-links"></a>Liens connexes

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md) 

[Configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Utilisation du service Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)


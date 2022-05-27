---
title: Mettre à niveau Skype Entreprise localement vers Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Découvrez comment mettre à niveau votre organisation vers Microsoft Teams à partir d’un déploiement local Skype Entreprise.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4b233978b9f9edf0aabbdfb8f9b24ff55a234cc
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681365"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Effectuer une mise à niveau de Skype Entreprise localement vers Teams

![Diagramme de parcours de mise à niveau, mettant l’accent sur le déploiement et l’implémentation.](media/upgrade-banner-deployment.png "Étapes du parcours de mise à niveau, en mettant l’accent sur la phase de déploiement et d’implémentation")

Cet article fait partie de l’étape déploiement et implémentation de votre parcours de mise à niveau. Avant de continuer, vérifiez que vous avez terminé les activités suivantes :

- [Inscription des parties prenantes de votre projet](upgrade-enlist-stakeholders.md)
- [Définition de l’étendue de votre projet](./upgrade-define-project-scope.md)
- [Compréhension de la coexistence et de l’interopérabilité des Skype Entreprise et des Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Choix de votre parcours de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Préparer votre environnement](./upgrade-prepare-environment.md)
- [Préparation de votre organisation](./upgrade-prepare-organization.md)
- [Conduite d’un projet pilote](./pilot-essentials.md)

Si vous avez déployé Skype Entreprise Server ou Microsoft Lync Server en local et que votre organisation souhaite effectuer une mise à niveau vers Teams, suivez les instructions de cet article. Vous devez configurer la connectivité hybride avec votre organisation Microsoft 365, comme décrit dans [Planifier la connectivité hybride entre Skype Entreprise Server et Teams](/skypeforbusiness/hybrid/plan-hybrid-connectivity).

Avant de commencer, vous devez également passer en revue [les considérations importantes pour les organisations avec Skype Entreprise Server localement](#important-considerations-for-organizations-with-skype-for-business-server-on-premises) plus loin dans cet article.

> [!IMPORTANT]
> Skype Entreprise Online a pris sa retraite le 31 juillet 2021. Pour optimiser la réalisation des avantages et vous assurer que votre organisation dispose du temps nécessaire pour implémenter votre mise à niveau, nous vous encourageons à commencer votre parcours vers Microsoft Teams aujourd’hui. N’oubliez pas qu’une mise à niveau réussie aligne la préparation technique et utilisateur. Veillez donc à tirer parti de ces conseils lorsque vous naviguez vers Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Étape 1 : Configurer la connectivité hybride

La configuration requise pour la mise à niveau de vos utilisateurs locaux vers Teams consiste à configurer la connectivité hybride pour votre Skype Entreprise Server déploiement local.

Commencez par lire [Planifier la connectivité hybride](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json), puis suivez les tâches décrites dans [Configurer la connectivité hybride](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).

## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Étape 2 : Définir le mode de coexistence transitoire (facultatif)

La coexistence et l’interopérabilité entre les clients et les utilisateurs Skype Entreprise et Teams sont définies par des [modes de coexistence](migration-interop-guidance-for-teams-with-skype.md). Les organisations hybrides sont par défaut en mode Îles. Le mode Îles permet aux utilisateurs d’utiliser les clients Teams et Skype Entreprise côte à côte. Les organisations peuvent éventuellement utiliser d’autres modes de coexistence pour fournir une expérience prévisible aux utilisateurs finaux lorsque les organisations passent de Skype Entreprise à Teams. Quel que soit le mode utilisé par une organisation pour ses utilisateurs locaux, lorsque ces utilisateurs sont déplacés de l’environnement local vers le cloud, ils deviennent TeamsOnly (et ne peuvent pas avoir d’autre mode).  Tant que les utilisateurs utilisent toujours Skype Entreprise Server, ils peuvent se faire attribuer n’importe quel mode autre que TeamsOnly. Si nécessaire, les utilisateurs TeamsOnly peuvent être redéployés en local, ce qui les amène à recevoir la stratégie globale du locataire de TeamsUpgradePolicy.

Lorsqu’un utilisateur se trouve dans l’un des modes Skype Entreprise, tous les appels et conversations entrants sont acheminés vers le client Skype Entreprise de l’utilisateur. Pour éviter toute confusion de l’utilisateur final et garantir les fonctionnalités de routage, d’appel et de conversation appropriées dans le client Teams est *désactivée pour un utilisateur qui se voit attribuer l’un des modes Skype Entreprise*. La planification des réunions dans Teams est désactivée quand les utilisateurs sont dans les modes SfBOnly ou SfBWithTeamsCollab, et *activée* lorsqu’un utilisateur est en mode SfBWithTeamsCollabAndMeetings.

Selon vos besoins, vous pouvez attribuer le mode de coexistence approprié en fonction du chemin de mise à niveau choisi par votre organisation. Pour plus d’informations, consultez [les conseils sur la migration et l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md) et [définir vos paramètres de coexistence et de mise à niveau](./setting-your-coexistence-and-upgrade-settings.md).

## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Étape 3 : Déplacer les utilisateurs d’Skype Entreprise localement vers Teams uniquement

Microsoft a récemment simplifié le processus de déplacement des utilisateurs vers TeamsOnly. Ce processus est maintenant une étape unique, quelle que soit la version de Skype Entreprise Server ou Lync Server 2013 que vous utilisez. Pour plus d’informations, consultez [Déplacer des utilisateurs entre l’environnement local et le cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud), et [Déplacer des utilisateurs d’un site local vers Teams](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams).

## <a name="step-4-complete-your-migration-to-the-cloud-by-disabling-hybrid-and-decommissioning-on-premises-skype-for-business"></a>Étape 4 : Terminer votre migration vers le cloud en désactivant l’hybride et en désaffectant Skype Entreprise

Une fois que vous avez déplacé tous les utilisateurs de l’environnement local vers le cloud, vous pouvez désactiver le déploiement Skype Entreprise local. Pour plus d’informations, consultez [Désactiver votre environnement Skype Entreprise local](/skypeforbusiness/hybrid/decommission-on-prem-overview).

## <a name="phone-system-and-pstn-connectivity-options"></a>options de connectivité Système téléphonique et RTC

Système téléphonique avec Teams est pris en charge une fois que l’utilisateur est en mode TeamsOnly. (Si l’utilisateur est en mode Îles, Système téléphonique est uniquement pris en charge avec Skype Entreprise.)

### <a name="pstn-connectivity-options"></a>Options de connectivité RTC

Lorsque vous envisagez d’utiliser les options de connectivité rtc (RTC), il existe deux scénarios possibles lors du passage du mode Skype Entreprise local au mode TeamsOnly :

- Utilisateur en Skype Entreprise local avec Voix Entreprise, qui passera en ligne et utilisera un plan d’appel Microsoft. La migration de cet utilisateur vers Teams nécessite le déplacement du compte Skype Entreprise local de l’utilisateur vers le cloud, et la coordination de ce déplacement avec le port du numéro de téléphone de cet utilisateur vers un plan d’appel Microsoft ou B) en affectant un nouveau numéro d’abonné à partir des régions disponibles.  Pour plus d’informations, consultez [From Skype Entreprise Server on-premises, with Voix Entreprise, to Microsoft Calling Plan](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan).

- Un utilisateur dans Skype Entreprise local avec Voix Entreprise, qui passera en ligne et conservera la connectivité RTC locale. La migration de cet utilisateur vers Teams nécessite le déplacement du compte Skype Entreprise local de l’utilisateur vers le cloud et la coordination de ce déplacement avec la migration de l’utilisateur vers le routage direct. Pour plus d’informations, consultez [From Skype Entreprise Server on-premises, with Voix Entreprise, to Direct Routing](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing).

## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Considérations importantes pour les organisations avec Skype Entreprise Server locales

- La configuration Skype Entreprise hybride est un prérequis pour migrer vers le mode TeamsOnly. Il est possible pour les utilisateurs Skype Entreprise Server locaux d’utiliser Teams en mode Islands sans hybride. Toutefois, la transition vers le mode TeamsOnly ne peut pas être effectuée sans déplacer l’utilisateur vers le cloud à l’aide de [Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud), pour lequel une connectivité hybride est requise. Pour plus d’informations, consultez [Configurer la connectivité hybride](/skypeforbusiness/hybrid/configure-hybrid-connectivity). La prochaine mise hors service de Skype Entreprise Online ne modifiera pas cette exigence. Pour que les organisations passent de Skype Entreprise Server à Teams, elles doivent toujours configurer l’hybride à l’aide du même ensemble d’outils, *exactement comme avant la mise hors service*.

- Pour déplacer un utilisateur local vers le cloud, utilisez `Move-CsUser` les outils d’administration locaux. Vous n’avez plus besoin de spécifier le `-MoveToTeams` commutateur pour déplacer les utilisateurs directement de l’environnement local vers TeamsOnly. Le mode TeamsOnly est automatiquement attribué aux utilisateurs et leurs réunions locales sont automatiquement converties en réunions Teams, que le `-MoveToTeams` commutateur soit spécifié ou non.

- Si votre organisation a Skype Entreprise Server et que vous n’avez pas configuré la connectivité hybride, mais que vous souhaitez toujours utiliser Teams, pour administrer Teams fonctionnalité, vous devez utiliser un compte d’administration doté d’un domaine .onmicrosoft.com. Sans connectivité hybride, les outils d’administration ne reconnaîtront pas vos domaines locaux.

- Teams utilisateurs qui disposent d’un compte Skype Entreprise local (autrement dit, ils n’ont pas encore été déplacés vers le cloud à l’aide de Move-CsUser) ne peuvent pas interagir avec des utilisateurs Skype Entreprise, ni se fédérer avec des utilisateurs externes. Cette fonctionnalité n’est disponible qu’une fois que les utilisateurs sont déplacés vers le cloud et qu’ils sont des utilisateurs TeamsOnly.

- Si vous avez des utilisateurs avec Skype Entreprise comptes en local ou si vous disposez toujours d’un enregistrement DNS de découverte lync pour un déploiement local, vous ne pouvez pas attribuer le mode TeamsOnly au niveau du locataire. Vous devez d’abord déplacer tous les utilisateurs disposant de comptes Skype Entreprise locaux vers le cloud à l’aide `Move-CsUser`de . Suivez ensuite les étapes décrites dans [Désactiver l’hybride pour terminer la migration vers le cloud](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid), ce qui inclut la suppression des entrées DNS. `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`ne fonctionne pas au niveau du locataire si un enregistrement DNS de découverte lync est détecté qui pointe vers un emplacement autre que Office 365.

- Vous devez vous assurer que vos utilisateurs sont correctement synchronisés avec Azure AD avec les attributs de Skype Entreprise appropriés. Ces attributs sont tous des préfixes avec « msRTCSIP- ». Si les utilisateurs ne sont pas correctement synchronisés avec Azure AD, les outils de gestion dans Teams ne pourront pas gérer ces utilisateurs. (Par exemple, vous ne pourrez pas affecter de stratégies Teams aux utilisateurs locaux, sauf si vous synchronisez correctement ces attributs.) Pour plus d’informations, consultez [Configurer azure AD Connecter pour Teams et Skype Entreprise](/SkypeForBusiness/hybrid/configure-azure-ad-connect).

- Pour créer un TeamsOnly dans une organisation hybride, *vous devez d’abord activer l’utilisateur dans Skype Entreprise Server local*, puis déplacer l’utilisateur d’un site local vers le cloud à l’aide de Move-CsUser.  La création de l’utilisateur en local garantit d’abord que tous les autres utilisateurs locaux restants Skype Entreprise seront en mesure d’acheminer vers l’utilisateur nouvellement créé. Une fois *que tous les* utilisateurs ont été déplacés en ligne, il n’est plus nécessaire d’activer d’abord les utilisateurs en local.

- Si vous souhaitez afficher des notifications dans le client Skype Entreprise pour les utilisateurs locaux, vous devez utiliser TeamsUpgradePolicy dans l’ensemble d’outils local. Seul le paramètre NotifySfbUsers est pertinent pour les utilisateurs locaux.  Les utilisateurs locaux reçoivent leur mode des instances en ligne de TeamsUpgradePolicy. Consultez les notes dans [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy).

> [!NOTE]
> Tous les nouveaux locataires créés après le 3 septembre 2019 sont créés en tant que locataires TeamsOnly, sauf si l’organisation dispose déjà d’un déploiement local de Skype Entreprise Server. Microsoft utilise des enregistrements DNS pour identifier les organisations Skype Entreprise Server locales. Pour plus d’informations, consultez [les implications DNS pour les organisations locales qui deviennent hybrides](/SkypeForBusiness/hybrid/configure-hybrid-connectivity#dns-implications-for-on-premises-organizations-that-become-hybrid).

- Les articles suivants décrivent les concepts de mise à niveau importants et les comportements de coexistence :
  - [Coexistence de Teams et de Skype Entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
  - [Modes de coexistence - Référence](migration-interop-guidance-for-teams-with-skype.md)
  - [Expérience client Teams et conformité aux modes coexistence](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="related-links"></a>Liens connexes

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md)

[Configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Utilisation du service de migration de réunion (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

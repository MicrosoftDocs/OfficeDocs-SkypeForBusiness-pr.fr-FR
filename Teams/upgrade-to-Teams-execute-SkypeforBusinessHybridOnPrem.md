---
title: Mettre Skype Entreprise niveau vers une version Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Découvrez comment mettre à niveau votre organisation vers Microsoft Teams à partir d Skype Entreprise déploiement local.
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
ms.openlocfilehash: d5ad5bc82771a3a8f020600a48848a074b88aec4
ms.sourcegitcommit: d3c48f0c147cf0c47d5eb4ea1128b5bca13be718
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2022
ms.locfileid: "62299059"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Mettre à niveau Skype Entreprise locaux vers Teams

![Diagramme de voyage de mise à niveau mettant en relief le déploiement et l’implémentation.](media/upgrade-banner-deployment.png "Étapes du parcours de mise à niveau, avec l’accentuation sur l’étape déploiement et implémentation")

Cet article fait partie de la phase déploiement et implémentation de votre voyage de mise à niveau. Avant de poursuivre, confirmez que vous avez effectué les activités suivantes :

-   [Demandez aux parties prenantes de votre projet](upgrade-enlist-stakeholders.md)
-   [Étendue définie de votre projet](./upgrade-define-project-scope.md)
-   [Coexistence et interopérabilité comprises entre les systèmes Skype Entreprise et Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
-   [Nous avons choisi votre chemin de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Préparé votre environnement](./upgrade-prepare-environment.md)
-   [Préparé votre organisation](./upgrade-prepare-organization.md)
-   [Conduite d’un pilote](./pilot-essentials.md)

Si vous avez déployé Skype Entreprise Server ou Microsoft Lync Server en local et que votre organisation souhaite mettre à niveau vers Teams, suivez les instructions de cet article. Vous devez configurer une connectivité hybride avec votre organisation Microsoft 365, comme décrit dans la formule hybride de connectivité entre les Skype Entreprise Server [et Teams](/skypeforbusiness/hybrid/plan-hybrid-connectivity).

Avant de commencer, vous devez également prendre en compte les [considérations importantes pour les organisations ayant Skype Entreprise Server localement](#important-considerations-for-organizations-with-skype-for-business-server-on-premises) plus loin dans cet article.

> [!IMPORTANT]
> Skype Entreprise Online a été retiré le 31 juillet 2021. Pour optimiser l’utilisation des avantages et vous assurer que votre organisation dispose du temps approprié pour implémenter votre mise à niveau, nous vous encourageons à commencer votre chemin vers Microsoft Teams aujourd’hui. N’oubliez pas qu’une mise à niveau réussie aligne les niveaux de préparation technique et utilisateur. N’oubliez pas de tirer parti de ces conseils lorsque vous naviguez dans Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Étape 1 : configurer la connectivité hybride 

La configuration requise pour mettre à niveau vos utilisateurs locaux vers Teams consiste à configurer la connectivité hybride pour votre déploiement Skype Entreprise Server local. 

Commencez par lire  [La connectivité hybridePlan](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json), puis suivez les tâches décrites dans [Configurer la connectivité hybride](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Étape 2 : définir le mode de coexistence de transition (facultatif)

La coexistence et l’interopérabilité entre Skype Entreprise et Teams clients et utilisateurs sont définis par [les modes de coexistence](migration-interop-guidance-for-teams-with-skype.md). Les organisations hybrides sont par défaut en mode Îles. Le mode Îles permet aux utilisateurs d’utiliser Teams et Skype Entreprise clients côte à côte. Les organisations peuvent éventuellement utiliser d’autres modes de coexistence afin de fournir une expérience prévisible aux utilisateurs finaux au cours de la transition des Skype Entreprise vers Teams. Quel que soit le mode utilisé par une organisation pour ses utilisateurs locaux, le fait de déplacer ces utilisateurs du cloud local vers le cloud devient TeamsOnly (et ne peut pas avoir d’autre mode).  Tant que les utilisateurs utilisent toujours Skype Entreprise Server, ils peuvent se voir attribuer n’importe quel mode autre que TeamsOnly. Si nécessaire, les utilisateurs de TeamsOnly peuvent être déplacés vers un environnement local, ce qui leur donnerait accès à la stratégie globale de TeamsUpgradePolicy du client.

Lorsqu’un utilisateur est dans l’un des modes Skype Entreprise, toutes les conversations et appels entrants sont acheminés vers le client de messagerie Skype Entreprise’utilisateur. Pour éviter la confusion des utilisateurs finaux et garantir un routage approprié, les fonctionnalités d’appel et de conversation dans le client Teams sont désactivées pour un utilisateur affecté à l’un des *modes Skype Entreprise.* La planification de réunion dans Teams est désactivée lorsque les utilisateurs sont dans les modes SfBOnly ou SfBWithTeamsCollab et est  activé lorsqu’un utilisateur est en mode SfBWithTeamsCollabAndMeetings.

Selon vos besoins, vous pouvez affecter le mode de coexistence approprié en fonction du chemin de mise à niveau choisi par votre organisation. Pour plus d’informations, consultez les conseils sur la [migration et l’interopérabilité](migration-interop-guidance-for-teams-with-skype.md) pour les organisations qui utilisent Teams avec Skype Entreprise et définir vos [paramètres de coexistence et de mise à niveau](./setting-your-coexistence-and-upgrade-settings.md).


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Étape 3 : déplacer les utilisateurs du Skype Entreprise local vers Teams uniquement

Microsoft a récemment simplifié le processus de déplacement des utilisateurs vers TeamsOnly. Ce processus est désormais une étape unique, quelle que soit la version de Skype Entreprise Server ou de Lync Server 2013 que vous utilisez. Pour plus d’informations, voir  [Déplacer des utilisateurs](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) entre le cloud local et le cloud et déplacez des [utilisateurs](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) d’un site à l’Teams. 

## <a name="step-4-complete-your-migration-to-the-cloud-by-disabling-hybrid-and-decommissioning-on-premises-skype-for-business"></a>Étape 4 : finalisation de la migration vers le cloud en désactivant l’hybride et la désaffectation des données Skype Entreprise

Une fois que vous avez déplacé tous les utilisateurs de l’installation en local vers le cloud, vous pouvez désaffecter le déploiement Skype Entreprise local. Pour plus d’informations, [voir Désaffecter votre environnement local Skype Entreprise local](/skypeforbusiness/hybrid/decommission-on-prem-overview).


## <a name="phone-system-and-pstn-connectivity-options"></a>Système téléphonique options de connectivité PSTN et Système téléphonique’autres options

Système téléphonique avec Teams est pris en charge lorsque l’utilisateur est en mode TeamsOnly. (Si l’utilisateur est en mode Îles, Système téléphonique n’est pris en charge qu’avec Skype Entreprise.) 

### <a name="pstn-connectivity-options"></a>Options de connectivité PSTN

Lorsque vous envisagez d’envisager des options de connectivité de réseau téléphonique commuté (PSTN), deux scénarios peuvent s’offrent à vous lorsque vous basculez de Skype Entreprise en local vers le mode TeamsOnly :

- Un utilisateur sur Skype Entreprise site avec Voix Entreprise, qui passe au service en ligne et utilise un plan d’appel Microsoft. La migration de cet utilisateur vers Teams nécessite le déplacement du compte Skype Entreprise local de l’utilisateur vers le cloud et la coordination du déplacement avec l’un des A) du port du numéro de téléphone de cet utilisateur vers un plan d’appels Microsoft ou B) et l’affectation d’un nouveau numéro d’abonné à partir des régions disponibles.  Pour plus d’informations, [voir De Skype Entreprise Server, en local, avec Voix Entreprise, à Microsoft Calling Plan](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan).

- Un utilisateur sur Skype Entreprise sur site avec Voix Entreprise, qui passe à la connexion en ligne et maintient la connectivité RSTN sur site. La migration de cet utilisateur vers Teams nécessite le déplacement du compte Skype Entreprise local de l’utilisateur vers le cloud, et la coordination de ce déplacement avec la migration de l’utilisateur vers le routage direct. Pour plus d’informations, [voir à partir Skype Entreprise Server, en local, avec Voix Entreprise, vers un routage direct](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing).


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Considérations importantes pour les organisations Skype Entreprise Server locales

- La configuration d Skype Entreprise hybride est une condition préalable pour migrer vers le mode TeamsOnly. Il est possible pour les utilisateurs locaux Skype Entreprise Server d’utiliser Teams en mode Îles sans utiliser d’hybride. Toutefois, la transition vers le mode TeamsOnly ne peut pas être réalisée sans déplacer l’utilisateur vers le cloud à l’aide de [Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud), pour lequel une connectivité hybride est requise. Pour plus d’informations, [voir Configurer la connectivité hybride](/skypeforbusiness/hybrid/configure-hybrid-connectivity). L’abandon prochaine Skype Entreprise Online ne modifiera pas cette exigence. Pour que les organisations passe d’Skype Entreprise Server à Teams, elles doivent tout de même configurer et configurer le hybride à l’aide du même jeu d’outils, exactement comme avant *la retraite*.

- Pour déplacer un utilisateur local vers le cloud, `Move-CsUser` utilisez les outils d’administration locaux. Vous n’avez plus besoin de spécifier le `-MoveToTeams` commutateur pour déplacer les utilisateurs directement de l’local vers TeamsOnly. Les utilisateurs `-MoveToTeams` se voit automatiquement attribuer le mode TeamsOnly et leurs réunions sur site sont automatiquement converties en réunions Teams, que le changement soit spécifié ou non.

- Si votre organisation Skype Entreprise Server et que vous n’avez pas configuré de connectivité hybride, mais que vous souhaitez continuer à utiliser Teams, pour administrer la fonctionnalité de Teams, vous devez utiliser un compte d’administration avec un domaine .onmicrosoft.com. Sans connectivité hybride, les outils d’administration ne reconnaîtront pas vos domaines locaux. 

- Teams les utilisateurs qui ont un compte Skype Entreprise en local (autrement dit, ils n’ont pas encore été déplacés vers le cloud à l’aide de Move-CsUser) ne peuvent pas interopérables avec les utilisateurs de Skype Entreprise et ne peuvent pas se fédérer avec des utilisateurs externes. Cette fonctionnalité n’est disponible que lorsque les utilisateurs sont déplacés vers le cloud et sont des utilisateurs de TeamsOnly. 

- Si des utilisateurs ont des comptes Skype Entreprise locaux ou si vous avez toujours un enregistrement DNS lyncdiscover pour un déploiement local, vous ne pouvez pas affecter le mode TeamsOnly au niveau du client. Vous devez tout d’abord déplacer tous les utilisateurs avec des comptes Skype Entreprise vers le cloud à l’aide `Move-CsUser`de . Suivez ensuite la procédure décrite dans [La désactivation](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid) de l’hybride pour achever la migration vers le cloud, ce qui inclut la suppression des entrées DNS. `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`ne fonctionne pas au niveau du client si un enregistrement DNS lyncdiscover est détecté qui pointe vers un emplacement autre que Office 365.

- Vous devez vous assurer que vos utilisateurs sont correctement synchronisés dans Azure AD avec les attributs Skype Entreprise appropriés. Ces attributs sont tous des préfixes avec « msRTCSIP- ». Si les utilisateurs ne sont pas correctement synchronisés avec Azure AD, les outils de gestion de Teams ne pourront pas gérer ces utilisateurs. (Par exemple, vous ne pourrez pas affecter de stratégies Teams aux utilisateurs locaux, sauf si vous synchronisez correctement ces attributs.) Pour plus d’informations, voir [Configurer Azure AD Connecter’Teams et Skype Entreprise](/SkypeForBusiness/hybrid/configure-azure-ad-connect).

- Pour créer une version de TeamsOnly dans une organisation hybride, vous devez d’abord activer l’utilisateur dans *Skype Entreprise Server* local, puis le déplacer de l’environnement local vers le cloud à l’aide de Move-CsUser.  La création de l’utilisateur en local garantit tout d’abord que les autres utilisateurs du site Skype Entreprise routent vers l’utilisateur nouvellement créé. Une *fois tous* les utilisateurs déplacés en ligne, il n’est plus nécessaire d’activer les utilisateurs en local.

- Si vous souhaitez afficher des notifications dans le client Skype Entreprise pour les utilisateurs locaux, vous devez utiliser TeamsUpgradePolicy dans le groupe d’outils local. Seul le paramètre NotifySfbUsers est pertinent pour les utilisateurs locaux.  Les utilisateurs sur site reçoivent leur mode depuis les instances en ligne de TeamsUpgradePolicy. Consultez les notes [dans Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). 

>[!NOTE]
> Tous les nouveaux locataires créés après le 3 septembre 2019 sont créés en tant que locataires TeamsOnly, sauf si l’organisation dispose déjà d’un déploiement local d’Skype Entreprise Server. Microsoft utilise les enregistrements DNS pour identifier les organisations Skype Entreprise Server locales. Pour plus d’informations, voir les [implications DNS pour les organisations locales hybrides](/SkypeForBusiness/hybrid/configure-hybrid-connectivity#dns-implications-for-on-premises-organizations-that-become-hybrid). 

- Les articles suivants décrivent les concepts de mise à niveau et les comportements de coexistence importants :
    - [Coexistence de Teams et d Skype Entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
    - [Modes de coexistence - Référence](migration-interop-guidance-for-teams-with-skype.md)
    - [Expérience client Teams et conformité aux modes coexistence](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="related-links"></a>Liens connexes

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md) 

[Configurer la connectivité hybride entre les Skype Entreprise Server et les Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Utilisation du service Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

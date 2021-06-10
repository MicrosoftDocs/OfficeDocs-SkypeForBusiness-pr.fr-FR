---
title: Déplacer des utilisateurs entre l’environnement local et le cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Résumé : Dans un déploiement local de Skype Entreprise Server activé pour un environnement hybride, vous pouvez déplacer des utilisateurs entre l’environnement local et le cloud (qu’il s’agit de Microsoft Teams ou de Skype Entreprise Online avant son retrait).'
ms.openlocfilehash: 998adf068dbfd360cb5a3e279320d1fee96f761f
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855943"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Déplacer des utilisateurs entre l’environnement local et le cloud

Dans un déploiement local de Skype Entreprise Server activé pour l’environnement hybride, vous pouvez déplacer des utilisateurs entre l’environnement local et le cloud (qu’il s’agit de Microsoft Teams ou de Skype Entreprise Online avant son retrait). La présence d’un utilisateur local ou dans le Cloud est appelée page d’accueil Skype Entreprise de l’utilisateur :

- Les utilisateurs qui sont sur site interagissent avec les serveurs Skype Entreprise locaux.
- Les utilisateurs hébergés en ligne interagissent avec d'autres services en ligne de Skype Entreprise Online.

*Les utilisateurs de Teams ont par nature un accueil Skype Entreprise, qu’ils utilisent Skype Entreprise ou non.* Si vous avez des utilisateurs Skype Entreprise locaux qui utilisent également Teams (côte à côte), ces utilisateurs sont locaux. Teams les utilisateurs avec Skype Entreprise locaux n’ont pas la possibilité d’interopérer avec les utilisateurs Skype Entreprise à partir de leur client Teams, ni de communiquer à partir de Teams avec les utilisateurs d’une organisation fédérée. Ces fonctionnalités sont entièrement disponibles uniquement une fois que l’utilisateur est Skype Entreprise en local vers teamsOnly en ligne. Lorsque vous déplacez un utilisateur vers Online, vous pouvez soit l’autoriser à utiliser Skype Entreprise Online (et, éventuellement, Teams), soit les mettre en Teams Only. Il est vivement recommandé de déplacer vos utilisateurs vers le mode Teams Uniquement, ce qui garantit que le routage de toutes les conversations et appels entrants arrive dans leur client Teams. Pour plus d’informations, voir [Teams coexistence](/microsoftteams/coexistence-chat-calls-presence) avec Skype Entreprise et les instructions de migration et d’interopérabilité pour les organisations qui utilisent Teams avec [Skype Entreprise](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

## <a name="prerequisites"></a>Configuration requise

Conditions préalables au déplacement d’un utilisateur vers le cloud (que ce soit Teams mode Uniquement ou Skype Entreprise Online avant son retrait) :

- L’organisation doit avoir azure AD Connecter correctement configuré et synchroniser tous les attributs pertinents pour l’utilisateur, comme décrit dans [Configurer Azure AD Connecter](configure-azure-ad-connect.md).
- Skype Entreprise hybride doit être configuré, comme décrit dans La configuration [Skype Entreprise hybride](configure-federation-with-skype-for-business-online.md).
- Une licence doit être attribuée à l’utilisateur pour Teams et Skype Entreprise Online (Plan 2). Même après le retrait de Skype Entreprise Online, la licence Skype Entreprise Online est toujours requise.  De plus :
    - Si l’utilisateur est activé pour la conférence rendez-vous en local, par défaut, l’utilisateur doit également avoir une licence d’audioconférence attribuée dans Teams avant de déplacer l’utilisateur en ligne. Une fois la migration vers le Cloud effectuée, l’utilisateur est configuré pour la conférence audio dans le Cloud. Si, pour une raison quelconque, vous souhaitez déplacer un utilisateur vers le cloud, mais que vous n’utilisez pas la fonctionnalité d’audioconférence, vous pouvez remplacer cette vérification en spécifiant le paramètre `BypassAudioConferencingCheck` dans `Move-CsUser` .
    - Si l’utilisateur est activé pour Voix Entreprise en local, l’utilisateur doit par défaut avoir une licence Système téléphonique attribuée dans Teams avant de déplacer l’utilisateur en ligne. Une fois la migration vers le Cloud effectuée, l’utilisateur est configuré pour le système téléphonique dans le Cloud. Si, pour une raison quelconque, vous souhaitez déplacer un utilisateur vers le cloud sans utiliser la fonctionnalité Système téléphonique, vous pouvez remplacer cette vérification en spécifiant le paramètre `BypassEnterpriseVoiceCheck` dans `Move-CsUser` .


## <a name="moving-users"></a>Déplacement d’utilisateurs

Lorsqu’un utilisateur est déplacé d’un environnement local vers le cloud :

- Teams utilisateurs sont activés pour l’interopérabilité avec Skype Entreprise utilisateurs, et s’ils sont TeamsOnly, ils peuvent également se fédérer avec d’autres organisations.
- L’utilisateur commence à utiliser les services Skype Entreprise Online disponibles dans le cloud pour toutes les fonctionnalités de Skype Entreprise.
- Les contacts locaux sont déplacés vers le cloud (vers Teams ou Skype Entreprise Online).
- Les réunions existantes qu’ils ont organisées et qui sont prévues à l’avenir sont migrées vers le site en ligne : si les utilisateurs sont déplacés directement vers TeamsOnly (voir ci-dessous), les réunions sont converties en réunions Teams, sinon les réunions restent Skype Entreprise mais seront migrées de sorte qu’elles soient hébergées en ligne plutôt que sur site.  La migration des réunions se produit de façon asynchrone et commence environ 90 minutes après le déplacement de l’utilisateur.  Pour déterminer l’état de la migration de la réunion, vous pouvez utiliser [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). Notez que les contenus téléchargés avant la réunion ne seront pas migrés.

Pour déplacer des utilisateurs entre l’ordinateur local et le cloud (que ce soit Teams ou Skype Entreprise Online), utilisez la cmdlet Move-CsUser ou le Panneau de contrôle d’administration Skype Entreprise, qui sont tous deux des outils locaux. Ces outils prennent en charge trois chemins de déplacement différents :

- [De Skype Entreprise Server (local)](move-users-from-on-premises-to-teams.md) directement à Teams uniquement (qui les déplace également vers Skype Entreprise Online).  Le comportement à déplacer directement de l’local vers Teams Seul est désormais automatique, quelle que soit la version de Skype Entreprise Server ou de Lync Server utilisée. Il n’est plus nécessaire de spécifier le `-MoveToTeams` commutateur pour obtenir ce comportement.  
- [De Skype Entreprise Server (local) à Skype Entreprise Online.](move-users-from-on-premises-to-skype-for-business-online.md) Les clients qui doivent toujours déplacer des utilisateurs vers Skype Entreprise Online sans devenir TeamsOnly peuvent y parvenir en déplaçant d’abord l’utilisateur vers le cloud avec le mode TeamsOnly, puis en mettant à jour le mode de l’utilisateur pour qu’il soit autre que TeamsOnly à l’aide de l’un ou de l’autre ou du Centre d’administration `Grant-CsTeamsUpgradePolicy` Teams. Cette option n’est plus disponible une fois Skype Entreprise Online est retiré.
- [À partir de la ligne (Teams uniquement ou non), vers l’local.](move-users-from-the-cloud-to-on-premises.md)

> [!NOTE] 
> Il n’est plus nécessaire de spécifier le commutateur -MoveToTeams dans Move-CsUser pour déplacer les utilisateurs directement de l’local vers TeamsOnly. Auparavant, si ce commutateur n’était pas spécifié, les utilisateurs passaient du mode d’accueil Skype Entreprise Server local à Skype Entreprise Online, et leur mode était inchangé. À présent, lors du déplacement d’un utilisateur de l’local vers le cloud avec Move-CsUser, le mode TeamsOnly est automatiquement affecté aux utilisateurs et leurs réunions à partir de l’ordinateur local sont automatiquement converties en réunions Teams, comme si le commutateur avait été spécifié, que le commutateur soit réellement spécifié `-MoveToTeams` ou non. 
> 

## <a name="required-administrative-credentials"></a>Identifiants administratifs requis

Pour déplacer des utilisateurs entre l’environnement local et le cloud, vous devez utiliser un compte avec des privilèges suffisants à la fois dans l’environnement Skype Entreprise Server local et dans l’organisation Teams. Vous pouvez utiliser un compte qui dispose de tous les privilèges nécessaires ou utiliser deux comptes, auquel cas vous accéderiez aux outils locaux à l’aide d’informations d’identification sur site, puis dans ces outils, vous fourniriez des informations d’identification supplémentaires pour un compte d’administration Teams.  

- Dans l’environnement local, l’utilisateur qui effectue le déplacement doit avoir le rôle CSServerAdministrator dans Skype Entreprise Server.
- Dans Teams, l’utilisateur qui effectue le déplacement doit répondre à l’un des critères suivants :
  - L’utilisateur est membre du rôle Administrateur général.
  - L’utilisateur est membre des rôles Administrateur Teams et Administrateur utilisateur.
  - L’utilisateur est membre des rôles Administrateur Skype Entreprise et Administrateur utilisateur.  

    > [!Important]
    > - Si vous utilisez le Panneau de Skype Entreprise admin, vous serez invité à fournir les informations d’identification d’un compte Microsoft 365 avec les rôles appropriés, comme indiqué ci-dessus. Vous devez fournir un compte qui se termine par .onmicrosoft.com. Si ce n’est pas possible, utilisez l'Move-CsUser cmdlet.
    >- Si vous utilisez Move-CsUser dans PowerShell, vous pouvez utiliser un compte qui se termine par .onmicrosoft.com ou utiliser n’importe quel compte local synchronisé dans Azure AD, à condition que vous spécifiant également le paramètre HostedMigrationOverrideUrl dans l’cmdlet. La valeur de l’URL de remplacement de migration hébergée est une variante de l’URL suivante : https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Dans l’URL ci-dessus, remplacez la XX par deux ou trois caractères, déterminés comme suit :
    >   - Dans une session Teams PowerShell, exécutez l’cmdlet suivante :<br>`Get-CsTenant|ft identity`
    >   - La valeur résultante sera au format suivant :<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >   - Le code à deux ou trois chiffres est le XX contenu dans la section DC=lyncXX001. S’il s’agit d’un code à deux caractères, il s’agit d’un chiffre suivi d’un nombre (par exemple, 0a). S’il s’agit d’un code à trois caractères, il s’agit de deux lettres suivies d’un chiffre (par exemple, jp1). Dans tous les cas, vous verrez 001 immédiatement après le code XX.


## <a name="voice-configuration-requirements"></a>Configuration requise pour la voix

Si les utilisateurs sont configurés pour la voix d’entreprise en local, vous devez coordonner la mise à jour de leur configuration vocale lorsque vous les déplacez en ligne, ou vous pouvez également les migrer sans fonctionnalités téléphoniques. Les options disponibles varient selon que l’utilisateur utilise le client Teams ou Skype Entreprise une fois qu’il est en ligne :

- Vous pouvez mettre à jour le fournisseur de téléphonie d’un utilisateur pour utiliser un [forfait d’appels Microsoft.](/microsoftteams/calling-plans-for-office-365) Il s’agit d’une option selon que les utilisateurs utiliseront Teams ou Skype Entreprise clients.
- Vous pouvez continuer à utiliser votre fournisseur PSTN local :
  - Les utilisateurs vocaux qui utiliseront Teams doivent être configurés pour [le routage direct.](/microsoftteams/direct-routing-plan) Le routage direct n’est disponible qu’une fois que l’utilisateur est déplacé de l’ordinateur local vers le réseau en ligne.
  - Les utilisateurs vocaux qui utiliseront le client Skype Entreprise une fois qu’ils seront déplacés en ligne doivent être configurés pour Skype Entreprise hybride Fonctionnalités vocales.

Pour plus d’informations sur les options de téléphonie dans les environnements hybrides, ainsi qu’une matrice de prise en charge, voir Comptes d’utilisateur dans un environnement hybride avec connectivité [PSTN.](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)

## <a name="other-considerations"></a>Autres considérations

Dans les environnements locaux et cloud, les stratégies (telles que le contrôle de la messagerie, des réunions et du comportement d’appel) sont indépendantes. Vous pouvez envisager de configurer des stratégies dans l’environnement et de les affecter à l’utilisateur avant de le déplacer de l’environnement local vers le cloud, afin qu’il soit configuré correctement dès qu’il est migré vers le cloud.

## <a name="see-also"></a>Voir aussi

[Déplacer des utilisateurs de l’environnement local vers Teams](move-users-from-on-premises-to-teams.md)

[Déplacer les utilisateurs de l’environnement local vers Skype Entreprise Online](move-users-from-on-premises-to-skype-for-business-online.md)

[Configuration de Meeting Migration Service (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planifier le routage direct](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)

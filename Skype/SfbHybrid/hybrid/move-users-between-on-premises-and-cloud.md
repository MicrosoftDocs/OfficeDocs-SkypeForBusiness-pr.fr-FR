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
description: 'Résumé : dans un déploiement local de Skype entreprise Server activé pour l’environnement hybride, vous pouvez déplacer des utilisateurs entre l’environnement local et le Cloud (pour Microsoft teams ou Skype entreprise Online)..'
ms.openlocfilehash: eede6062bd9d03a2d9d6062a6dacb861ce37e14c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221124"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Déplacer des utilisateurs entre l’environnement local et le cloud

Dans un déploiement local de Skype Entreprise Server activé pour le déploiement hybride, vous pouvez déplacer des utilisateurs entre l’environnement local et le Cloud (de Microsoft Teams ou de Skype Entreprise Online). La présence d’un utilisateur local ou dans le Cloud est appelée page d’accueil Skype Entreprise de l’utilisateur :

- Les utilisateurs hébergés sur site interagissent avec les serveurs Skype entreprise locaux.
- Les utilisateurs hébergés en ligne peuvent interagir avec le service Skype Entreprise Online.

*Les utilisateurs de teams disposent par essence d’un domicile Skype entreprise, qu’ils utilisent Skype entreprise ou non.* Si vous disposez d’utilisateurs Skype entreprise locaux qui utilisent également Teams (côte à côte), ces utilisateurs sont hébergés sur site. Les utilisateurs de teams avec Skype entreprise en local n’ont pas la possibilité d’interagir avec les utilisateurs de Skype entreprise à partir de leur client Teams, ni de communiquer avec des utilisateurs d’une organisation fédérée. Cette fonctionnalité n’est disponible qu’une fois que l’utilisateur a été déplacé de Skype entreprise local vers la version en ligne. Lorsque vous déplacez un utilisateur vers Online, vous pouvez soit l’autoriser à utiliser Skype Entreprise Online (et, éventuellement, Teams), soit les mettre en Teams Only. Si votre organisation utilise déjà Teams, nous vous recommandons vivement de déplacer l’utilisateur vers le mode Teams uniquement afin de veiller à ce que les conversations et les appels entrants soient tous acheminés vers son client Teams. Pour plus d’informations, reportez-vous à la rubrique [coexistence entre teams avec Skype entreprise](/microsoftteams/coexistence-chat-calls-presence) et [l’aide à la migration et à l’interopérabilité pour les organisations qui utilisent teams avec Skype entreprise](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

## <a name="prerequisites"></a>Conditions préalables

Conditions préalables pour déplacer un utilisateur vers le Cloud (en mode Skype entreprise uniquement ou teams uniquement) :

- La configuration d’Azure AD Connect doit être correctement configurée pour l’organisation et la synchronisation de tous les attributs pertinents pour l’utilisateur, comme décrit dans la rubrique [configure Azure ad Connect](configure-azure-ad-connect.md).
- Skype entreprise hybride doit être configuré, comme décrit dans [configure Skype for Business Hybrid](configure-federation-with-skype-for-business-online.md).
- L’utilisateur doit disposer d’une licence pour Skype Entreprise Online (plan 2), et s’il utilise Teams, il doit également avoir une licence de Teams.  De plus :
    - Si l’utilisateur est activé pour la Conférence rendez-vous sur site, par défaut, l’utilisateur doit également avoir une licence d’audioconférence affectée dans Microsoft 365 ou Office 365 avant d’exécuter le déplacement de l’utilisateur en ligne. Une fois la migration vers le Cloud effectuée, l’utilisateur est configuré pour la conférence audio dans le Cloud. Si, pour une raison quelconque, vous souhaitez déplacer un utilisateur vers le Cloud, mais pas utiliser la fonctionnalité d’audioconférence, vous pouvez remplacer cette vérification en spécifiant le `BypassAudioConferencingCheck` paramètre dans `Move-CsUser` .
    - Si l’utilisateur est activé pour voix entreprise sur site, par défaut, l’utilisateur doit disposer d’une licence de système téléphonique attribuée dans Microsoft 365 ou Office 365 avant de déplacer l’utilisateur en ligne. Une fois la migration vers le Cloud effectuée, l’utilisateur est configuré pour le système téléphonique dans le Cloud. Si, pour une raison quelconque, vous souhaitez déplacer un utilisateur vers le Cloud, mais pas utiliser la fonctionnalité de système téléphonique, vous pouvez remplacer cette vérification en spécifiant le `BypassEnterpriseVoiceCheck` paramètre dans `Move-CsUser` .


## <a name="moving-users"></a>Déplacement d’utilisateurs

Lorsqu’un utilisateur est déplacé d’un environnement local vers le cloud :

- L’utilisateur commence à utiliser les services Skype Entreprise Online disponibles dans le cloud pour toutes les fonctionnalités de Skype Entreprise.
- Les utilisateurs de Teams peuvent désormais interagir avec les utilisateurs de Skype Entreprise. Ils peuvent également se fédérer avec d’autres organisations.
- Les contacts de en local sont déplacés vers le Cloud (Skype entreprise ou Teams).
- Les réunions existantes organisées qui sont planifiées à l’avenir sont migrées vers le service en ligne : si les utilisateurs sont déplacés directement vers TeamsOnly (voir ci-dessous), les réunions sont converties en réunions Teams, sinon les réunions restent Skype entreprise, mais elles sont migrées afin d’être hébergées en ligne au lieu d’être en local.  La migration des réunions se produit de façon asynchrone et commence environ 90 minutes après le déplacement de l’utilisateur.  Pour déterminer l’état de la migration de la réunion, vous pouvez utiliser [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). Notez que les contenus téléchargés avant la réunion ne seront pas migrés.

Pour déplacer des utilisateurs entre le Cloud local et le Cloud (vers teams ou Skype entreprise Online), utilisez l’applet de commande Move-CsUser ou le panneau de configuration d’administration Skype entreprise, tous deux des outils locaux. Ces outils prennent en charge trois chemins de déplacement différents :

- [De Skype entreprise Server (en local) à Skype entreprise Online](move-users-from-on-premises-to-skype-for-business-online.md).
- [Depuis Skype entreprise Server (en local) directement vers teams uniquement](move-users-from-on-premises-to-teams.md) (qui les déplace également vers Skype entreprise Online).  L’option permettant de passer directement de l’installation locale à teams est disponible dans Skype entreprise Server 2019, ainsi que dans la mise à jour cumulative 8 pour Skype entreprise Server 2015. Les organisations qui utilisent des versions antérieures de Skype Entreprise Server ne peuvent déplacer des utilisateurs vers le mode Teams uniquement qu’en les déplaçant d’abord vers Skype Entreprise Online, puis en leur attribuant le mode Teams uniquement une fois qu’ils sont dans le cloud.
- À [partir de Online (uniquement en équipe ou non), sur site local](move-users-from-the-cloud-to-on-premises.md).

## <a name="required-administrative-credentials"></a>Identifiants administratifs requis

Pour déplacer des utilisateurs entre l’environnement local et le Cloud, vous devez utiliser un compte disposant de privilèges suffisants dans l’environnement local de Skype entreprise Server et dans l’organisation Microsoft 365 ou Office 365. Vous pouvez utiliser un compte qui dispose de tous les privilèges nécessaires, ou vous pouvez utiliser deux comptes, auquel cas vous accédez aux outils sur site à l’aide des informations d’identification locales, puis, dans ces outils, vous fournissez des informations d’identification supplémentaires pour un compte d’administrateur Microsoft 365 ou Office 365.  

- Dans l’environnement local, l’utilisateur qui exécute le déplacement doit disposer du rôle CSServerAdminstrator au sein de Skype Entreprise Server.
- Dans Microsoft 365 et Office 365, l’utilisateur qui effectue le déplacement doit être un administrateur général ou avoir des rôles Administrateur Skype entreprise et administrateur d’utilisateur.  

    > [!Important]
    > - Si vous utilisez le panneau de configuration d’administration de Skype entreprise, vous serez invité à fournir des informations d’identification pour un compte Microsoft 365 ou Office 365 avec les rôles appropriés, comme indiqué ci-dessus. Vous devez indiquer un compte qui se termine par. onmicrosoft.com. Si cela n’est pas possible, utilisez la cmdlet Move-CsUser.
    >- Si vous utilisez Move-CsUser dans PowerShell, vous pouvez utiliser un compte qui se termine par. onmicrosoft.com, ou vous pouvez utiliser n’importe quel compte local synchronisé dans Azure AD, à condition que vous spécifiez également le paramètre HostedMigrationOverrideUrl dans l’applet de commande. La valeur de l’URL de remplacement de la migration hébergée est une variante de l’URL suivante :https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Dans l’URL ci-dessus, remplacez XX par deux ou trois caractères, déterminé comme suit :
    >   - Dans une session PowerShell Skype entreprise Online, exécutez l’applet de commande suivante :<br>`Get-CsTenant|ft identity`
    >    - La valeur résultante sera au format suivant :<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - Le code à deux ou trois chiffres est le XX contenu dans la section DC = lyncXX001. S’il s’agit d’un code à deux caractères, il sera un chiffre suivi d’un nombre (par exemple, 0A). S’il s’agit d’un code à trois caractères, il sera deux lettres suivies d’un chiffre (par exemple, JP1). Dans tous les cas, vous verrez 001 immédiatement après le code XX.


## <a name="voice-configuration-requirements"></a>Configuration requise pour la configuration vocale

Si les utilisateurs sont configurés pour voix entreprise dans l’environnement local, vous devez coordonner la mise à jour de leur configuration vocale lorsque vous les déplacez vers le service en ligne ou vous pouvez également les migrer sans fonctionnalité de téléphonie. Les options disponibles varient selon que l’utilisateur utilisera ou non le client teams ou Skype entreprise une fois qu’il sera en ligne :

- Vous pouvez mettre à jour le fournisseur de téléphonie d’un utilisateur pour qu’il utilise un [plan d’appel Microsoft](/microsoftteams/calling-plans-for-office-365). Cette option indique si les utilisateurs doivent utiliser teams ou les clients Skype entreprise.
- Vous pouvez continuer à utiliser votre fournisseur RTC local :
  - Les utilisateurs de la voix qui utiliseront teams doivent être configurés pour le [routage direct](/microsoftteams/direct-routing-plan). Le routage direct est uniquement disponible une fois que l’utilisateur est déplacé de local vers en ligne.
  - Les utilisateurs de la voix qui utiliseront le client Skype entreprise après avoir été déplacés en ligne doivent être configurés pour la fonctionnalité de voix hybride Skype entreprise.

Pour plus d’informations sur les options de téléphonie dans les environnements hybrides, ainsi qu’une matrice de prise en charge, reportez-vous à la rubrique [comptes d’utilisateur dans un environnement hybride avec une connectivité RTC](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Autres considérations

Dans les environnements locaux et cloud, les stratégies (telles que le contrôle de la messagerie, des réunions et du comportement d’appel) sont indépendantes. Vous pouvez envisager de configurer des stratégies dans l’environnement et de les affecter à l’utilisateur avant de déplacer cet utilisateur de local vers le Cloud, de sorte qu’il dispose de la configuration correcte dès qu’il est migré vers le service en ligne.

## <a name="see-also"></a>Voir aussi

[Déplacer les utilisateurs de l’environnement local vers Skype Entreprise Online](move-users-from-on-premises-to-skype-for-business-online.md)

[Déplacer des utilisateurs de l’environnement local vers Teams](move-users-from-on-premises-to-teams.md)

[Configuration de Meeting Migration Service (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planifier le routage direct](/microsoftteams/direct-routing-plan)

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)

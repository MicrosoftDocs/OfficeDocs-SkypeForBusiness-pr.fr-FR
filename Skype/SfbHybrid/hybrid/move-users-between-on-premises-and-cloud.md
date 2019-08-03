---
title: Déplacer des utilisateurs entre les sites et le Cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
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
description: 'Résumé: dans un déploiement local de Skype entreprise Server activé pour l’environnement hybride, vous pouvez déplacer des utilisateurs entre l’environnement local et le Cloud (pour Microsoft teams ou Skype entreprise Online)..'
ms.openlocfilehash: b7e3ecc46af5a3043848d9291394c0bff7835883
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160504"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Déplacer des utilisateurs entre les sites et le Cloud

Dans un déploiement local de Skype entreprise Server activé pour l’environnement hybride, vous pouvez déplacer des utilisateurs entre l’environnement local et le Cloud (pour Microsoft teams ou Skype entreprise Online). Si un utilisateur est situé sur site ou dans le Cloud, il s’agit de la maison Skype entreprise de l’utilisateur:

- Les utilisateurs hébergés sur site interagissent avec les serveurs Skype entreprise locaux.
- Les utilisateurs hébergés en ligne peuvent interagir avec le service Skype entreprise online.

*Les utilisateurs de teams disposent par essence d’un domicile Skype entreprise, qu’ils utilisent Skype entreprise ou non.* Si vous disposez d’utilisateurs Skype entreprise locaux qui utilisent également Teams (côte à côte), ces utilisateurs sont hébergés sur site. Les utilisateurs de teams avec Skype entreprise en local n’ont pas la possibilité d’interagir avec les utilisateurs de Skype entreprise à partir de leur client Teams, ni de communiquer avec des utilisateurs d’une organisation fédérée. Cette fonctionnalité n’est disponible qu’une fois que l’utilisateur a été déplacé de Skype entreprise local vers la version en ligne. Lorsque vous déplacez un utilisateur vers la version en ligne, vous pouvez soit lui autoriser d’utiliser Skype entreprise Online (et, éventuellement, Teams), soit lui faire teams uniquement. Si votre organisation utilise déjà Teams, il est vivement recommandé de les déplacer vers le mode teams uniquement, ce qui garantit le routage de toutes les conversations et appels entrants dans leur client Teams. Pour plus d’informations, reportez-vous à la rubrique [coexistence entre teams avec Skype entreprise](/microsoftteams/coexistence-chat-calls-presence) et [l’aide à la migration et à l’interopérabilité pour les organisations qui utilisent teams avec Skype entreprise](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

## <a name="prerequisites"></a>Conditions préalables

Conditions préalables pour déplacer un utilisateur vers le Cloud (en mode Skype entreprise uniquement ou teams uniquement):

- La configuration d’Azure AD Connect doit être correctement configurée pour l’organisation et la synchronisation de tous les attributs pertinents pour l’utilisateur, comme décrit dans la rubrique [configure Azure ad Connect](configure-azure-ad-connect.md).
- Skype entreprise hybride doit être configuré, comme décrit dans [configure Skype for Business Hybrid](configure-federation-with-skype-for-business-online.md).
- L’utilisateur doit disposer d’une licence pour Skype entreprise Online (plan 2) et s’il utilisera Teams, il doit également disposer d’une licence Teams.  De plus :
    - Si l’utilisateur est activé pour la Conférence rendez-vous sur site, par défaut, l’utilisateur doit également disposer d’une licence d’audioconférence affectée dans Office 365 avant d’exécuter le déplacement de l’utilisateur en ligne. Une fois la migration vers le Cloud effectuée, l’utilisateur est configuré pour l’audioconférence dans le Cloud. Si, pour une raison quelconque, vous souhaitez déplacer un utilisateur vers le Cloud, mais pas utiliser la fonctionnalité d’audioconférence, vous pouvez remplacer cette vérification en `BypassAudioConferencingCheck` spécifiant `Move-CsUser`le paramètre dans.
    - Si l’utilisateur est activé pour voix entreprise sur site, par défaut, l’utilisateur doit disposer d’une licence de système téléphonique attribuée dans Office 365 avant de déplacer l’utilisateur en ligne. Une fois la migration vers le Cloud effectuée, l’utilisateur est configuré pour le système téléphonique dans le Cloud. Si, pour une raison quelconque, vous souhaitez déplacer un utilisateur vers le Cloud, mais pas utiliser la fonctionnalité de système téléphonique, vous pouvez remplacer cette `BypassEnterpriseVoiceCheck`vérification en `Move-CsUser`spécifiant le paramètre dans.


## <a name="moving-users"></a>Migration des utilisateurs

Lorsqu’un utilisateur est déplacé de l’organisation locale vers le Cloud:

- L’utilisateur commence à utiliser les services Skype entreprise Online dans le Cloud pour toutes les fonctionnalités de Skype entreprise.
- Les utilisateurs de teams sont activés pour l’interopérabilité avec les utilisateurs de Skype entreprise, et ils peuvent également se fédérer avec d’autres organisations.
- Les contacts de en local sont déplacés vers le Cloud (Skype entreprise ou Teams).
- Les réunions existantes organisées qui sont planifiées à l’avenir sont migrées vers le service en ligne: si les utilisateurs sont déplacés directement vers TeamsOnly (voir ci-dessous), les réunions sont converties en réunions Teams, sinon les réunions restent Skype entreprise, mais elles sont migrées de sorte qu’elles soient hébergé en ligne au lieu de local.  La migration des réunions se produit de manière asynchrone et commence approximativement 90 minutes après le transfert de l’utilisateur.  Pour déterminer l’état de la migration de réunion, vous pouvez utiliser [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). Notez que tout contenu téléchargé avant la réunion n’est pas déplacé.

Pour déplacer des utilisateurs entre le Cloud local et le Cloud (vers teams ou Skype entreprise Online), utilisez l’applet de commande Move-CsUser ou le panneau de configuration d’administration Skype entreprise, tous deux des outils locaux. Ces outils prennent en charge trois chemins de déplacement différents:

- [De Skype entreprise Server (en local) à Skype entreprise Online](move-users-from-on-premises-to-skype-for-business-online.md).
- [À partir de Skype entreprise Server (en local) directement vers teams uniquement](move-users-from-on-premises-to-teams.md) (qui les déplace également vers Skype entreprise Online).  L’option permettant de passer directement de l’installation locale à teams est disponible dans Skype entreprise Server 2019, ainsi que dans la mise à jour cumulative 8 pour Skype entreprise Server 2015. Les organisations qui utilisent des versions antérieures de Skype entreprise Server peuvent déplacer les utilisateurs vers teams uniquement en les déplaçant d’abord vers Skype entreprise Online, puis en appliquant le mode TeamsOnly à ces utilisateurs une fois qu’ils sont en ligne.
- À [partir de Online (uniquement en équipe ou non), sur site local](move-users-from-the-cloud-to-on-premises.md).

## <a name="required-administrative-credentials"></a>Informations d’identification administratives requises

Pour déplacer des utilisateurs entre le Cloud local et le Cloud, vous devez utiliser un compte disposant de privilèges suffisants dans l’environnement local de Skype entreprise Server et dans le client Office 365. Vous pouvez utiliser un compte qui dispose de tous les privilèges nécessaires, ou vous pouvez utiliser deux comptes, auquel cas vous accédez aux outils sur site à l’aide des informations d’identification locales, puis, dans ces outils, vous fournissez des informations d’identification supplémentaires pour Office 365 compte d’administrateur.  

- Dans l’environnement local, l’utilisateur qui effectue le déplacement doit disposer du rôle CSServerAdminstrator dans Skype entreprise Server.
- Dans Office 365, l’utilisateur qui effectue le déplacement doit être un administrateur général ou avoir des rôles Administrateur Skype entreprise et administrateur d’utilisateur.  

    > [!Important]
    > - Si vous utilisez le panneau de configuration d’administration de Skype entreprise, vous serez invité à fournir des informations d’identification pour un compte Office 365 avec les rôles appropriés, comme indiqué ci-dessus. Vous devez indiquer un compte qui se termine par. onmicrosoft.com. Si cela n’est pas possible, utilisez la cmdlet Move-CsUser.
    >- Si vous utilisez Move-CsUser dans PowerShell, vous pouvez utiliser un compte qui se termine par. onmicrosoft.com, ou vous pouvez utiliser n’importe quel compte local synchronisé dans Azure AD, à condition que vous spécifiez également le paramètre HostedMigrationOverrideUrl dans l’applet de commande. . La valeur de l’URL de remplacement de la migration hébergée est une variante de l’URL suivante:https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Dans l’URL ci-dessus, remplacez XX par deux ou trois caractères, déterminé comme suit:
    >   - Dans une session PowerShell Skype entreprise Online, exécutez l’applet de commande suivante:<br>`Get-CsTenant|ft identity`
    >    - La valeur résultante sera au format suivant:<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - Le code à deux ou trois chiffres est le XX contenu dans la section DC = lyncXX001. S’il s’agit d’un code à deux caractères, il sera un chiffre suivi d’un nombre (par exemple, 0A). S’il s’agit d’un code à trois caractères, il sera deux lettres suivies d’un chiffre (par exemple, JP1). Dans tous les cas, vous verrez 001 immédiatement après le code XX.


## <a name="voice-configuration-requirements"></a>Configuration requise pour la configuration vocale

Si les utilisateurs sont configurés pour voix entreprise dans l’environnement local, vous devez coordonner la mise à jour de leur configuration vocale lorsque vous les déplacez vers le service en ligne ou vous pouvez également les migrer sans fonctionnalité de téléphonie. Les options disponibles varient selon que l’utilisateur utilisera ou non le client teams ou Skype entreprise une fois qu’il sera en ligne:

- Vous pouvez mettre à jour le fournisseur de téléphonie d’un utilisateur pour qu’il utilise un [plan d’appel Microsoft](/microsoftteams/calling-plans-for-office-365). Cette option indique si les utilisateurs doivent utiliser teams ou les clients Skype entreprise.
- Vous pouvez continuer à utiliser votre fournisseur RTC local:
  - Les utilisateurs de la voix qui utiliseront teams doivent être configurés pour le [routage direct](/microsoftteams/direct-routing-plan). Le routage direct est uniquement disponible une fois que l’utilisateur est déplacé de local vers en ligne.
  - Les utilisateurs de la voix qui utiliseront le client Skype entreprise après avoir été déplacés en ligne doivent être configurés pour la fonctionnalité de voix hybride Skype entreprise.

Pour plus d’informations sur les options de téléphonie dans les environnements hybrides, ainsi qu’une matrice de prise en charge, reportez-vous à la rubrique [comptes d’utilisateur dans un environnement hybride avec une connectivité RTC](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Autres considérations

Les stratégies (telles que la gestion de la messagerie, de la réunion et du comportement d’appel) dans les environnements locaux et en ligne sont indépendantes. Vous pouvez envisager de configurer des stratégies dans l’environnement et de les affecter à l’utilisateur avant de déplacer cet utilisateur de local vers le Cloud, de sorte qu’il dispose de la configuration correcte dès qu’il est migré vers le service en ligne.

## <a name="see-also"></a>Voir aussi

[Déplacer des utilisateurs de l’organisation locale vers Skype entreprise Online](move-users-from-on-premises-to-skype-for-business-online.md)

[Déplacer des utilisateurs de l’organisation locale vers teams](move-users-from-on-premises-to-teams.md)

[Configuration du service de migration de réunion (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planifier le routage direct](/microsoftteams/direct-routing-plan)

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)

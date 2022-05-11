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
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Résumé : Dans un déploiement local de Skype Entreprise Server qui est activé pour l’hybride, vous pouvez déplacer des utilisateurs entre l’environnement local et le cloud.'
ms.openlocfilehash: 15e237fdf54854a86216bc3890ae26209449c146
ms.sourcegitcommit: d847256fca80e4e8954f767863c880dc8472ca04
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2022
ms.locfileid: "65304002"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Déplacer des utilisateurs entre l’environnement local et le cloud

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Dans un déploiement local de Skype Entreprise Server qui est activé pour l’hybride, vous pouvez déplacer des utilisateurs entre l’environnement local et Teams. La présence d’un utilisateur local ou dans le Cloud est appelée page d’accueil Skype Entreprise de l’utilisateur :

- Les utilisateurs hébergés localement interagissent avec les serveurs Skype Entreprise locaux.
- Les utilisateurs hébergés en ligne peuvent interagir avec le service Teams.

*Teams les utilisateurs ont par nature une Skype Entreprise maison, qu’ils utilisent Skype Entreprise ou non.* Si vous avez des utilisateurs Skype Entreprise locaux qui utilisent également Teams (côte à côte), ces utilisateurs sont hébergés localement. Teams les utilisateurs avec Skype Entreprise locaux ne peuvent pas interagir avec Skype Entreprise utilisateurs de leur client Teams, ni communiquer à partir de Teams avec les utilisateurs d’une organisation fédérée. Ces fonctionnalités ne sont entièrement disponibles qu’après le déplacement de l’utilisateur de Skype Entreprise local vers la version en ligne et l’utilisation de TeamsOnly. Il est recommandé de déplacer vos utilisateurs vers le mode TeamsOnly, ce qui garantit que le routage de toutes les conversations et appels entrants atterrit dans leur client Teams. Pour plus d’informations, consultez [Teams coexistence avec Skype Entreprise](/microsoftteams/coexistence-chat-calls-presence) et [des conseils sur la migration et l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

## <a name="prerequisites"></a>Conditions requises

Conditions préalables pour déplacer un utilisateur en mode TeamsOnly :

- L’organisation doit disposer d’Azure AD Connecter correctement configuré et synchroniser tous les attributs pertinents pour l’utilisateur, comme décrit dans [Configurer Azure AD Connecter](configure-azure-ad-connect.md).
- Skype Entreprise hybride doit être configuré, comme décrit dans [Configurer Skype Entreprise hybride](configure-federation-with-skype-for-business-online.md).
- Une licence doit être attribuée à l’utilisateur pour Teams et Skype Entreprise Online (Plan 2). Même après la mise hors service de Skype Entreprise Online, la licence Skype Entreprise Online est toujours requise.  De plus :
    - Si l’utilisateur est activé pour la conférence rendez-vous localement, il doit également disposer d’une licence Audioconférence attribuée dans Teams avant de déplacer l’utilisateur en ligne. Une fois la migration vers le Cloud effectuée, l’utilisateur est configuré pour la conférence audio dans le Cloud. 
    - Si l’utilisateur est activé pour Voix Entreprise en local, une licence Système téléphonique doit être attribuée à l’utilisateur dans Teams avant de déplacer l’utilisateur en ligne. Une fois migré vers le cloud, l’utilisateur est approvisionné pour Système téléphonique dans le cloud. 


## <a name="moving-users"></a>Déplacement d’utilisateurs

Lorsqu’un utilisateur est déplacé d’un environnement local vers le cloud :

- Teams utilisateurs sont activés pour l’interopérabilité avec Skype Entreprise utilisateurs, et s’ils sont TeamsOnly, ils peuvent également se fédérer avec d’autres organisations.

- Les contacts locaux sont déplacés vers Teams.

- Les réunions existantes qu’ils ont organisées et planifiées à l’avenir sont converties en réunions Teams. La migration des réunions se produit de façon asynchrone et commence environ 90 minutes après le déplacement de l’utilisateur.  Pour déterminer l’état de la migration de la réunion, vous pouvez utiliser [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). Tout contenu qui a été chargé avant la réunion n’est pas déplacé.

Pour déplacer les utilisateurs vers Teams, utilisez l’applet de commande Move-CsUser ou l’Panneau de configuration d’administration Skype Entreprise, qui sont tous deux des outils locaux. Ces outils prennent en charge les chemins de déplacement suivants :

- [De Skype Entreprise Server (localement) directement à Teams uniquement](move-users-from-on-premises-to-teams.md).  Le comportement de passer directement d’un emplacement local à Teams Uniquement est désormais automatique, quelle que soit la version de Skype Entreprise Server ou Lync Server utilisée. Il n’est plus nécessaire de spécifier le `-MoveToTeams` commutateur pour obtenir ce comportement.  
- [En ligne (que ce soit Teams uniquement ou non) à l’emplacement local](move-users-from-the-cloud-to-on-premises.md).

> [!NOTE] 
> Il n’est plus nécessaire de spécifier le commutateur -MoveToTeams dans Move-CsUser pour déplacer les utilisateurs directement de l’environnement local vers TeamsOnly. Auparavant, si ce commutateur n’était pas spécifié, les utilisateurs sont passés de Skype Entreprise Server local à Skype Entreprise Online, et leur mode est resté inchangé. Maintenant, lors du déplacement d’un utilisateur local vers le cloud avec Move-CsUser, les utilisateurs reçoivent automatiquement le mode TeamsOnly et leurs réunions locales sont automatiquement converties en réunions Teams, comme si le `-MoveToTeams` commutateur avait été spécifié, que le commutateur ait été spécifié ou non. 
> 

## <a name="required-administrative-credentials"></a>Identifiants administratifs requis

Pour déplacer des utilisateurs entre le site local et le cloud, vous devez utiliser un compte disposant de privilèges suffisants à la fois dans l’environnement Skype Entreprise Server local et dans l’organisation Teams. Vous pouvez soit utiliser un compte disposant de tous les privilèges nécessaires, soit utiliser deux comptes. Si vous utilisez deux comptes, vous accédez aux outils locaux à l’aide d’informations d’identification locales, puis, dans ces outils, vous fournissez des informations d’identification supplémentaires pour un compte d’administration Teams.  

- Dans l’environnement local, l’utilisateur effectuant le déplacement doit disposer des rôles CSServerAdministrator, CsUserAdministrator et RTCUniversalUserAdmins dans Skype Entreprise Server.
- Dans Teams, l’utilisateur effectuant le déplacement doit être membre d’au moins l’un des rôles suivants :
  - Rôle Administrateur général
  - rôle d’administrateur Teams
  - Skype Entreprise rôle Administrateur.  

    > [!Important]
    > - Si vous utilisez le Panneau de configuration d’administration Skype Entreprise, vous êtes invité à fournir des informations d’identification pour un compte Microsoft 365 avec les rôles appropriés, comme indiqué ci-dessus. Vous devez fournir un compte qui se termine par .onmicrosoft.com. Si ce n’est pas possible, utilisez l’applet de commande Move-CsUser.
    >- Si vous utilisez Move-CsUser dans PowerShell, vous pouvez soit utiliser un compte qui se termine par .onmicrosoft.com, soit utiliser n’importe quel compte local synchronisé dans Azure AD, à condition de spécifier également le paramètre HostedMigrationOverrideUrl dans l’applet de commande. La valeur de l’URL de remplacement de la migration hébergée est une variante de l’URL suivante : https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Dans l’URL ci-dessus, remplacez le XX par deux ou trois caractères, déterminés comme suit :
    >   - Dans une session PowerShell Teams, exécutez l’applet de commande suivante :<br>`Get-CsTenant | ft ServiceInstance`
    >   - La valeur obtenue sera au format suivant :<br>`MicrosoftCommunicationsOnline/YYYY-XX-ZZ`
    >   - Le code à deux ou trois caractères est le XX contenu dans la section YYYY-XX-ZZ. S’il s’agit d’un code à deux caractères, il s’agit d’un chiffre suivi d’un nombre (par exemple, 4A). S’il s’agit d’un code à trois caractères, il s’agit de deux lettres suivies d’un chiffre (par exemple, JP1). NoAM-4A-S7 en est un exemple.


## <a name="voice-configuration-requirements"></a>Configuration vocale requise

Si les utilisateurs sont configurés pour la voix d’entreprise en local, vous devez coordonner la mise à jour de leur configuration vocale lorsque vous les déplacez vers la ligne. Vous pouvez également les migrer sans fonctionnalités de téléphonie. Les options disponibles varient selon que l’utilisateur utilisera le client Teams ou Skype Entreprise une fois qu’il sera en ligne :

- Vous pouvez mettre à jour le fournisseur de téléphonie d’un utilisateur pour utiliser un [forfait d’appels Microsoft](/microsoftteams/calling-plans-for-office-365). Il s’agit d’une option indiquant si les utilisateurs utiliseront Teams ou Skype Entreprise clients.
- Vous pouvez continuer à utiliser votre fournisseur RTC local :
  - Les utilisateurs vocaux qui utiliseront Teams doivent être configurés pour le [routage direct](/microsoftteams/direct-routing-plan). Le routage direct n’est disponible qu’une fois que l’utilisateur est déplacé d’un emplacement local vers un emplacement en ligne.
  - Les utilisateurs vocaux qui utiliseront le client Skype Entreprise après leur déplacement en ligne doivent être configurés pour Skype Entreprise hybride fonctionnalités vocales.

Pour plus d’informations sur les options de téléphonie dans les environnements hybrides, notamment une matrice de prise en charge, consultez [Comptes d’utilisateur dans un environnement hybride avec connectivité RTC](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Autres considérations

Dans les environnements locaux et cloud, les stratégies (telles que le contrôle de la messagerie, des réunions et du comportement d’appel) sont indépendantes. Vous pouvez envisager de configurer des stratégies dans l’environnement et de les affecter à l’utilisateur avant de déplacer cet utilisateur d’un emplacement local vers le cloud, afin qu’il dispose de la configuration appropriée dès qu’il est migré en ligne.

## <a name="see-also"></a>Voir aussi

[Déplacer des utilisateurs de l’environnement local vers Teams](move-users-from-on-premises-to-teams.md)

[Configuration de Meeting Migration Service (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planifier le routage direct](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)

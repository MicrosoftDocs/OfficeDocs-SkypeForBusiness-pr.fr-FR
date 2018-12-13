---
title: Déplacer des utilisateurs entre local et le nuage
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Résumé : Dans un déploiement local de Skype pour Business Server qui est activé pour l’environnement hybride, vous pouvez déplacer des utilisateurs entre l’environnement local et le nuage (s’il faut Teams Microsoft ou Skype pour Business Online)...'
ms.openlocfilehash: 492a2a7d14af77bc0b90afe03f0d36de0f830129
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247648"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Déplacer des utilisateurs entre local et le nuage

Dans un déploiement local de Skype pour Business Server qui est activé pour l’environnement hybride, vous pouvez déplacer des utilisateurs entre l’environnement local et le nuage (s’il faut Teams Microsoft ou Skype pour Business Online). Si un utilisateur se trouve sur site ou dans le nuage est appelé Skype de l’utilisateur pour les professionnels particuliers :

- Les utilisateurs qui sont hébergés sur site interagissent avec Skype locaux des serveurs d’entreprise.
- Les utilisateurs hébergés en ligne peuvent interagir avec Skype pour le service Business en ligne.

*Les utilisateurs des équipes ont un Skype pour les professionnels particuliers, si elles utilisent Skype pour les entreprises ou non.* Si vous avez Skype sur site pour les utilisateurs professionnels qui utilisent également des équipes (côte à côte), ces utilisateurs sont hébergés sur site. Utilisateurs d’équipes avec Skype pour les entreprises en local n’ont pas la possibilité d’interagir avec Skype pour les utilisateurs professionnels à partir du client de leurs équipes, ni peuvent leur communiquer des équipes avec les utilisateurs d’une organisation fédérée. Cette fonctionnalité est disponible uniquement une fois que l’utilisateur est déplacé de Skype pour les entreprises dans les locaux à en ligne. Lorsque vous déplacez un utilisateur en ligne, vous pouvez soit les autoriser à utiliser Skype pour Business Online (et, éventuellement, les équipes) ou vous pouvez les rendre équipes uniquement. Si votre organisation utilise déjà des équipes, il est recommandé de déplacer les équipes uniquement en mode, qui permet de garantir que le routage de toutes les conversations entrantes et les appels arrive dans le client de leurs équipes. Pour plus d’informations, voir [conseils d’interopérabilité pour les organisations à l’aide des équipes avec Skype pour les entreprises et de Migration](/microsoftteams/migration-interop-guidance-for-teams-with-skype)et [coexistence équipes avec Skype pour les entreprises](/microsoftteams/coexistence-chat-calls-presence) .

## <a name="prerequisites"></a>Conditions requises

Conditions préalables pour déplacer un utilisateur vers le nuage (s’il faut Skype pour le mode entreprise uniquement ou équipes uniquement) :

- L’organisation doit avoir Azure AD se connecter correctement configurée et à la synchronisation de tous les attributs pertinents pour l’utilisateur comme décrit dans [Azure configurer AD connexion](configure-azure-ad-connect.md).
- Skype pour un environnement hybride Business doit être configuré, comme décrit dans [Configurer le Skype pour un environnement hybride Business](configure-federation-with-skype-for-business-online.md).
- L’utilisateur doit être attribué une licence pour Skype pour Business Online (Plan 2), et si elles doivent utiliser des équipes, ils doivent également avoir une licence d’équipes.  De plus, :
    - Si l’utilisateur est activé pour la conférence rendez-vous dans localement, par défaut, que l’utilisateur doit avoir également une licence de conférence Audio affectée dans Office 365 avant d’exécuter déplacer l’utilisateur en ligne. Une fois la migration vers le nuage, l’utilisateur sera mis en service pour l’audioconférence dans le nuage. Si pour une raison quelconque, vous souhaitez déplacer un utilisateur vers le nuage, mais n’utilisez pas les fonctionnalités de conférence audio, vous pouvez remplacer cette vérification en spécifiant le `BypassAudioConferencingCheck` paramètre dans `Move-CsUser`.
    - Si l’utilisateur est activé pour Enterprise Voice dans localement, par défaut l’utilisateur doit avoir une licence système téléphonique dans Office 365 avant de déplacer l’utilisateur en ligne. Une fois migrée vers le nuage, l’utilisateur sera mis en service pour le système téléphonique dans le nuage. Si pour une raison quelconque, vous souhaitez déplacer un utilisateur vers le nuage, mais pas utiliser les fonctionnalités de système téléphonique, vous pouvez remplacer cette vérification en spécifiant le `BypassEnterpriseVoiceCheck`paramètre dans `Move-CsUser`.


## <a name="moving-users"></a>Déplacement d’utilisateurs

Lorsqu’un utilisateur est déplacé sur site vers le nuage :

- L’utilisateur commence à l’aide de Skype pour Business Online services dans le nuage pour n’importe quel Skype pour les fonctionnalités d’entreprise.
- Les utilisateurs équipes deviennent activés pour l’interopérabilité avec Skype pour les utilisateurs professionnels, et ils peuvent également fédérer avec d’autres organisations.
- Contacts dans les locaux sont déplacés vers le nuage (Skype pour les entreprises) ou équipes.
- Des réunions existantes qu'ils organisés qui sont planifiées dans le futur sont migrées vers en ligne. Migration des réunions qui se produit de façon asynchrone et commence à environ 90 minutes après le déplacement de l’utilisateur.  Pour déterminer l’état de la migration de la réunion, vous pouvez utiliser [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). Notez que tout contenu qui a été téléchargé avant la réunion n’est pas déplacé.

Pour déplacer des utilisateurs entre sur site et le nuage (s’il faut équipes ou Skype pour Business en ligne), utilisez l’applet de commande Move-CsUser ou le Skype pour le panneau de configuration d’administration Business, qui sont tous deux outils locale. Ces outils prennent en charge les chemins d’accès de trois move différents :

- [À partir de Skype pour Business Server (localement) Skype pour Business Online](move-users-from-on-premises-to-skype-for-business-online.md).
- [À partir de Skype pour Business Server (localement) directement aux équipes uniquement](move-users-from-on-premises-to-teams.md) (qui également les déplace vers Skype pour Business Online).  Permet de passer directement à partir du site à équipes uniquement est disponible dans Skype pour Business Server 2019 ainsi que 8 de mise à jour Cumulative pour Skype pour Business Server 2015. Les organisations qui utilisent des versions antérieures de Skype pour Business Server pouvant déplacer des utilisateurs aux équipes uniquement en premier en les déplaçant vers Skype pour Business en ligne, puis en appliquant le mode TeamsOnly à ces utilisateurs lorsqu’ils sont en ligne.
- [à partir d’online (si les équipes uniquement ou non), à localement](move-users-from-the-cloud-to-on-premises.md).

## <a name="required-administrative-credentials"></a>Informations d’identification administratives requises

Pour déplacer des utilisateurs entre sur site et le nuage, vous devez utiliser un compte disposant de privilèges suffisants dans les deux le Skype locale pour environnement Business Server, ainsi que dans le client Office 365. Vous pouvez utiliser un compte qui possède les privilèges nécessaires, ou vous pouvez utiliser deux comptes, auquel cas vous pouvez accéder aux outils locale à l’aide locale informations d’identification, et dans ces outils vous devez fournir les informations d’identification supplémentaires pour un Office 365 compte d’administration.  

- Dans l’environnement local, l’utilisateur effectue le déplacement doit avoir le rôle CSServerAdminstrator dans Skype pour Business Server.
- Dans Office 365, l’utilisateur qui effectue le déplacement doit être un administrateur Global ou il doit avoir les deux Skype pour les rôles d’administrateur d’entreprise et administrateur d’utilisateurs.  

    > [!Important]
    > - Si vous utilisez le Skype pour le panneau de configuration d’administration Business, vous devrez fournir les informations d’identification d’un compte Office 365 avec les rôles appropriés, comme indiqué ci-dessus. Vous devez fournir un compte qui se termine de. onmicrosoft.com. Si ce n’est pas possible, puis utilisez l’applet de commande Move-CsUser.
    >- Si vous utilisez Move-CsUser dans PowerShell, vous pouvez utiliser un compte qui se termine par. onmicrosoft.com, ou vous pouvez utiliser n’importe quel compte local est synchronisé dans Azure AD, à condition que vous spécifiez également le paramètre HostedMigrationOverrideUrl dans l’applet de commande . La valeur de l’URL de substitution de migration hébergé est une variante de l’URL suivante :https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Dans l’URL ci-dessus, remplacez la XX avec deux ou trois caractères, déterminées comme suit :
    >   - Dans un Skype pour session Business Online PowerShell, exécutez l’applet de commande suivante :<br>`Get-CsTenant|ft identity`
    >    - La valeur résultante sera dans le format suivant :<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - Le code à deux ou trois chiffres est XX contenue dans la section, DC = lyncXX001. S’il s’agit d’un code de deux caractères, il sera un chiffre suivi d’un nombre (par exemple, 0). S’il s’agit d’un code de trois caractères, il sera deux lettres suivis d’un chiffre (par exemple, jp1). Dans tous les cas, vous verrez 001 immédiatement après le code XX.


## <a name="voice-configuration-requirements"></a>Configuration requise de voix

Si les utilisateurs sont configurés pour enterprise voice dans sur site, vous devrez coordonner la mise à jour de leur configuration vocale lorsque vous déplacer vers en ligne, ou vous pourriez également les migrer sans fonctionnalités de téléphonie. Les options disponibles dépendent de savoir si l’utilisateur utilisera les équipes ou Skype pour client d’entreprise lorsqu’ils sont en ligne :

- Vous pouvez mettre à jour le fournisseur de téléphonie d’un utilisateur pour utiliser un [Plan de l’appel de Microsoft](/microsoftteams/calling-plans-for-office-365). Il s’agit d’une option si les utilisateurs utiliseront des équipes ou Skype pour les clients d’entreprise.
- Vous pouvez continuer à utiliser votre fournisseur de RTC local :
  - Les utilisateurs de voix qui utiliseront les équipes doivent être configurés pour le [Routage Direct](/microsoftteams/direct-routing-plan). Routage direct est uniquement disponible une fois que l’utilisateur est déplacé à partir de site en ligne.
  - Les utilisateurs de voix qui utiliseront le Skype pour client d’entreprise une fois qu’ils sont déplacés en ligne doivent être configurés pour Skype pour la fonctionnalité de voix hybride de Business.

Pour plus d’informations sur les options de téléphonie dans les environnements hybrides, ainsi que d’une matrice de prise en charge, voir [comptes d’utilisateurs dans un environnement hybride avec une connectivité PSTN](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Autres considérations

Les stratégies (telle que le contrôle de messagerie, de la réunion et le comportement de l’appel) dans les locaux et en ligne des environnements sont indépendants. Vous pouvez configurer des stratégies dans l’environnement et de les affecter à l’utilisateur avant de déplacer cet utilisateur à partir de sur site vers le nuage, afin qu’ils aient la bonne configuration dès qu’ils sont migrés vers en ligne.

## <a name="see-also"></a>Voir aussi

[Déplacer les utilisateurs vers Skype Entreprise Online](move-users-from-on-premises-to-skype-for-business-online.md)

[Déplacer les utilisateurs locaux vers des équipes](move-users-from-on-premises-to-teams.md)

[Configuration de Meeting Migration Service (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planifier le routage direct](/microsoftteams/direct-routing-plan)

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)
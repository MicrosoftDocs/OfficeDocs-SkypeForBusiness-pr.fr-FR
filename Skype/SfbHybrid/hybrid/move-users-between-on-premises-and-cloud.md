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
ms.openlocfilehash: ac32c4037cf275d9a6a7545701c1899742d8fd12
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705873"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Déplacer des utilisateurs entre l’environnement local et le cloud

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Dans un déploiement local de Skype Entreprise Server, les utilisateurs de Skype Entreprise peuvent également utiliser Teams, mais toutes les fonctionnalités Teams ne sont pas disponibles pour ces utilisateurs tant qu’ils sont configurés pour utiliser le déploiement Skype Entreprise Server local. Ces utilisateurs sont dits « hébergés » localement, et certaines fonctionnalités teams ne sont pas disponibles alors que ces utilisateurs sont hébergés localement, par exemple :
- Les appels fédérés et les conversations via le client Teams de l’utilisateur avec des utilisateurs d’autres organisations ne sont pas disponibles
- Interop communication via le client Teams de l’utilisateur avec d’autres utilisateurs de l’organisation qui utilisent Skype Entreprise client.
- Fonctionnalité d’appel RTC (si une licence système téléphonique est attribuée à l’utilisateur).

Pour bénéficier d’une fonctionnalité Teams complète, ces utilisateurs doivent être déplacés de Skype Entreprise localement vers le cloud, auquel cas l’utilisateur devient TeamsOnly. Le déplacement d’un utilisateur d’un environnement local vers le cloud définit le mode de coexistence de l’utilisateur sur TeamsOnly. Une fois que les utilisateurs sont déplacés vers le cloud, ils sont TeamsOnly, ce qui signifie que toutes les conversations et appels entrants arrivent dans leur client Teams. Pour plus d’informations, consultez [la coexistence de Teams avec Skype Entreprise](/microsoftteams/coexistence-chat-calls-presence) et [la migration et des conseils d’interopérabilité pour les organisations utilisant Teams avec Skype Entreprise](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

Pour déplacer des utilisateurs du déploiement Skype Entreprise Server local vers le cloud, vous devez configurer [Skype Entreprise hybride](/skypeforbusiness/hybrid/plan-hybrid-connectivity).  Une fois le déploiement activé pour le déploiement hybride, vous pouvez déplacer les utilisateurs de l’environnement local vers le cloud pour les rendre TeamsOnly comme décrit ci-dessous. Si nécessaire, vous pouvez également déplacer les utilisateurs TeamsOnly vers le déploiement Skype for Bsuiness local. 



## <a name="prerequisites"></a>Prerequisites

Conditions préalables pour déplacer un utilisateur en mode TeamsOnly :

- Azure AD Connect doit être correctement configuré pour l’organisation et synchroniser tous les attributs pertinents pour l’utilisateur, comme décrit dans [Configurer Azure AD Connect](configure-azure-ad-connect.md).
- Skype Entreprise hybride doit être configuré, comme décrit dans [Configurer Skype Entreprise hybride](configure-federation-with-skype-for-business-online.md).
- Une licence pour Teams et Skype Entreprise Online (Plan 2) doit être attribuée à l’utilisateur. Même après la mise hors service de Skype Entreprise Online, la licence Skype Entreprise Online est toujours requise.  De plus :
    - Si l’utilisateur est activé pour la conférence rendez-vous localement, il doit également disposer d’une licence d’audioconférence attribuée dans Teams avant de déplacer l’utilisateur en ligne. Une fois la migration vers le Cloud effectuée, l’utilisateur est configuré pour la conférence audio dans le Cloud. 
    - Si l’utilisateur est activé pour Téléphonie –  Grandes entreprises en local, une licence De téléphone Teams doit être attribuée à l’utilisateur dans Teams avant de le déplacer en ligne. Une fois migré vers le cloud, l’utilisateur est approvisionné pour le système téléphonique dans le cloud. 
  
À compter du 31 juillet 2022, pour déplacer des utilisateurs entre un déploiement local et le cloud, vous devez utiliser la version minimale suivante de Skype Entreprise Server ou Lync Server :

</br>
</br>

|Produit local|Version minimale requise|Build minimale requise|
|---|---|---|
|Skype Entreprise Server 2019| CU6 |7.0.2046.385|
|Skype Entreprise Server 2015| CU12|6.0.9319.619|
|Lync Server 2013| CU10 avec correctif logiciel 7|5.0.8308.1182|

</br>
</br>

## <a name="moving-users"></a>Déplacement d’utilisateurs

Lorsqu’un utilisateur est déplacé d’un environnement local vers le cloud :

- L’utilisateur devient un utilisateur TeamsOnly, ce qui signifie que l’utilisateur :
   -  Reçoit et lance toutes les conversations et appels dans le client Teams.
   -  Planifie toutes les réunions dans Teams.
   -  Impossible de lancer des conversations ou des appels, ni de planifier des réunions dans Skype Entreprise.
   -  Peut participer Skype Entreprise réunions qu’ils ont déjà ou recevoir à l’avenir. Toutefois, une fois que Microsoft a supprimé l’infrastructure Skype Entreprise Online pour un utilisateur TeamsOnly donné, les utilisateurs TeamsOnly peuvent uniquement participer à Skype Entreprise réunions de manière anonyme. À compter d’octobre 2022, les utilisateurs déplacés de l’environnement local vers Teams uniquement dans les organisations hybrides ne seront plus approvisionnés avec l’infrastructure Skype Entreprise Online. Si ces utilisateurs sont invités à une réunion Skype Entreprise, ils doivent participer de manière anonyme. Pour plus d’informations, consultez [Conseils pour les organisations avec des déploiements locaux de Skype Entreprise Server](/MicrosoftTeams/skype-for-business-online-retirement.md#guidance-for-organizations-with-on-premises-deployments-of-skype-for-business-server).

- Les utilisateurs sont activés pour l’interopérabilité avec Skype Entreprise utilisateurs et peuvent également se fédérer avec d’autres organisations.
- Les contacts locaux sont déplacés vers Teams.
- Les réunions existantes qu’ils ont organisées et qui sont planifiées à l’avenir sont converties en réunions Teams. La migration des réunions se produit de façon asynchrone et commence environ 90 minutes après le déplacement de l’utilisateur.  Pour déterminer l’état de la migration de la réunion, vous pouvez utiliser [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). Tout contenu qui a été chargé avant la réunion n’est pas déplacé.
- Les utilisateurs auxquels une licence Teams Phone est attribuée peuvent accéder à la fonctionnalité RTC une fois qu’ils sont correctement configurés.
 
Pour déplacer des utilisateurs vers Teams, utilisez l’applet de commande Move-CsUser ou le Skype Entreprise Administration Panneau de configuration, qui sont tous deux des outils locaux. Ces outils prennent en charge les chemins de déplacement suivants :

- [De Skype Entreprise Server (localement) à Teams uniquement](move-users-from-on-premises-to-teams.md).
- [De la version en ligne (teams uniquement ou non) à l’environnement local](move-users-from-the-cloud-to-on-premises.md).


> [!NOTE] 
>  Le comportement à déplacer directement d’un site local vers Teams uniquement est automatique, quelle que soit la version de Skype Entreprise Server ou de Lync Server utilisée. Il n’est plus nécessaire de spécifier le `-MoveToTeams` commutateur `Move-CsUser` pour déplacer les utilisateurs directement de l’environnement local vers TeamsOnly. Auparavant, si ce commutateur n’était pas spécifié, les utilisateurs sont passés de Skype Entreprise Server local à Skype Entreprise Online, et leur mode est resté inchangé. Maintenant, lors du déplacement d’un utilisateur local vers le cloud avec `Move-CsUser`, les utilisateurs se voient automatiquement attribuer le mode TeamsOnly et leurs réunions locales sont automatiquement converties en réunions Teams, comme si le `-MoveToTeams` commutateur avait été spécifié, que le commutateur ait été spécifié ou non. 


## <a name="required-administrative-credentials"></a>Identifiants administratifs requis

Pour déplacer des utilisateurs entre le site local et le cloud, vous devez utiliser un compte disposant de privilèges suffisants à la fois dans l’environnement Skype Entreprise Server local et dans l’organisation Teams. Vous pouvez soit utiliser un compte disposant de tous les privilèges nécessaires, soit utiliser deux comptes. Si vous utilisez deux comptes, vous accédez aux outils locaux à l’aide d’informations d’identification locales, puis, dans ces outils, vous fournissez des informations d’identification supplémentaires pour un compte d’administration Teams.  

- Dans l’environnement local, l’utilisateur effectuant le déplacement doit disposer des rôles CSServerAdministrator, CsUserAdministrator et RTCUniversalUserAdmins dans Skype Entreprise Server.
- Dans Teams, l’utilisateur effectuant le déplacement doit être membre d’au moins l’un des rôles suivants :
  - Rôle Administrateur général
  - Rôle d’administrateur Teams
  - Skype Entreprise rôle Administrateur.  

    > [!Important]
    > - Si vous utilisez le Skype Entreprise Administration Panneau de configuration, vous êtes invité à fournir les informations d’identification d’un compte Microsoft 365 avec les rôles appropriés, comme indiqué ci-dessus. Vous devez fournir un compte qui se termine par .onmicrosoft.com. Si ce n’est pas possible, utilisez l’applet de commande Move-CsUser.
    >- Si vous utilisez Move-CsUser dans PowerShell, vous pouvez soit utiliser un compte qui se termine par .onmicrosoft.com, soit utiliser n’importe quel compte local synchronisé dans Azure AD, à condition de spécifier également le paramètre HostedMigrationOverrideUrl dans l’applet de commande. La valeur de l’URL de remplacement de la migration hébergée est une variante de l’URL suivante : https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Dans l’URL ci-dessus, remplacez le XX par deux ou trois caractères, déterminés comme suit :
    >   - Dans une session Teams PowerShell, exécutez l’applet de commande suivante :<br>`Get-CsTenant | ft ServiceInstance`
    >   - La valeur obtenue sera au format suivant :<br>`MicrosoftCommunicationsOnline/YYYY-XX-ZZ`
    >   - Le code à deux ou trois caractères est le XX contenu dans la section YYYY-XX-ZZ. S’il s’agit d’un code à deux caractères, il s’agit d’un chiffre suivi d’un nombre (par exemple, 4A). S’il s’agit d’un code à trois caractères, il s’agit de deux lettres suivies d’un chiffre (par exemple, JP1). NoAM-4A-S7 en est un exemple.


## <a name="voice-configuration-requirements"></a>Configuration vocale requise

Si les utilisateurs sont configurés pour la voix d’entreprise en local, vous devez coordonner la mise à jour de leur configuration vocale lorsque vous les déplacez vers la ligne. Vous pouvez également les migrer sans fonctionnalités de téléphonie. 
- Vous pouvez mettre à jour le fournisseur de téléphonie d’un utilisateur pour utiliser un [forfait d’appels Microsoft](/microsoftteams/calling-plans-for-office-365). Il s’agit d’une option indiquant si les utilisateurs utiliseront Teams ou Skype Entreprise clients.
- Vous pouvez continuer à utiliser votre fournisseur RTC local :
  - Les utilisateurs vocaux qui utiliseront Teams doivent être configurés pour le [routage direct](/microsoftteams/direct-routing-plan). Le routage direct n’est disponible qu’une fois que l’utilisateur est déplacé d’un emplacement local vers un emplacement en ligne.

Pour plus d’informations sur les options de téléphonie dans les environnements hybrides, notamment une matrice de prise en charge, consultez [Comptes d’utilisateur dans un environnement hybride avec connectivité RTC](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Autres considérations

Dans les environnements locaux et cloud, les stratégies (telles que le contrôle de la messagerie, des réunions et du comportement d’appel) sont indépendantes. Vous pouvez envisager de configurer des stratégies dans l’environnement et de les affecter à l’utilisateur avant de déplacer cet utilisateur d’un emplacement local vers le cloud, afin qu’il dispose de la configuration appropriée dès qu’il est migré en ligne.

## <a name="see-also"></a>Voir aussi

[Déplacer des utilisateurs de l’environnement local vers Teams](move-users-from-on-premises-to-teams.md)

[Configuration de Meeting Migration Service (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planifier le routage direct](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)

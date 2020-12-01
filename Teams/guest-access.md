---
title: Accès invité dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
search.appverid: MET150
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
description: L'accès invité dans Microsoft Teams permet aux équipes de votre organisation de collaborer avec des personnes extérieures en leur accordant l'accès aux équipes et aux canaux.
ms.openlocfilehash: 266830f29f98d517450f4062ff23de9a7582a24f
ms.sourcegitcommit: 207e6aa97867e3fd80734cc839c0c5858bca24c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/30/2020
ms.locfileid: "49476993"
---
# <a name="guest-access-in-microsoft-teams"></a>Accès invité dans Microsoft Teams

Avec l’accès invité, vous pouvez fournir l’accès aux équipes, documents dans les canaux, ressources, conversations et applications aux personnes externes à votre organisation, tout en conservant le contrôle de vos données d’entreprise.

Un invité est une personne qui n'est ni un employé, ni un étudiant ni un membre de votre organisation. Il ne dispose pas d'aucun compte scolaire ni professionnel lié à votre organisation. Il peut par exemple s'agir de partenaires, sous-traitants, fournisseurs ou consultants. Toute personne qui ne fait pas partie de votre organisation peut être ajouté en tant qu’invité dans Teams. Cela signifie que toute personne disposant d’un compte professionnel (c’est-à-dire, d’un compte Azure Active Directory) ou d’un compte de messagerie grand public (avec Outlook.com, Gmail.com, etc.) peut participer en tant qu’invité dans Teams, avec l’accès aux équipes et aux expériences de canal.

Les invités dans teams sont couverts par la même protection de conformité et d’audit que le reste de Microsoft 365 et peuvent être gérés dans Azure AD. L’accès invité est soumis à Azure AD et aux limites de service Microsoft 365 ou Office 365.

L’expérience des invités comporte des limitations de par sa conception. Pour obtenir la liste complète des fonctionnalités qu’un invité peut et ne peut pas faire dans Microsoft Teams, voir [comparaison des fonctionnalités des membres d’équipe et des invités](guest-experience.md#comparison-of-team-member-and-guest-capabilities).

> [!IMPORTANT]
> Les utilisateurs invités suivent les paramètres de niveau organisation Teams pour le mode de mise à niveau de coexistence. Il n’est pas possible de modifier cela.

Pour configurer l’accès invité, voir [collaborer avec des invités dans une équipe](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team). 

Pour comparer l’accès externe (fédération) avec l’accès invité (et décider de celui que vous devez utiliser), lisez [Communiquer avec des utilisateurs d’autres organisations dans Teams](communicate-with-users-from-other-organizations.md).

## <a name="set-up-guest-access"></a>Configurer l’accès invité

L’accès invité dans teams doit configurer d’autres paramètres dans Microsoft 365, y compris les paramètres d’Azure AD, des groupes Microsoft 365 et SharePoint. Si vous êtes prêt à commencer à inviter des invités à des équipes, consultez l’une des rubriques suivantes :

- Pour configurer l’accès invité pour les équipes pour une utilisation générale, voir [collaborer avec des invités dans une équipe](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).
- Pour collaborer avec une organisation de partenaire qui utilise Azure Active Directory et permettre aux invités d’être automatiquement inscrits pour l’accès à l’équipe, voir [créer un extranet B2B avec des invités gérés](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).

L’accès invité dans teams est un paramètre à l’échelle de l’organisation qui est désactivé par défaut. Vous pouvez contrôler l’accès invité aux équipes individuelles à l’aide d' [étiquettes de sensibilité](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

## <a name="how-a-guest-becomes-a-member-of-a-team"></a>Comment un invité peut devenir membre d'une équipe

1. Un propriétaire d’équipe ou un administrateur 365 Microsoft [ajoute un invité à une équipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. L'invité reçoit un e-mail de bienvenue de la part du propriétaire de l’équipe, ainsi que des informations sur l’équipe et sur ce à quoi s'attendre en tant que membre.
3. L'invité accepte l'invitation.
  Les utilisateurs invités disposant d’un compte professionnel ou scolaire dans Azure Active Directory peuvent accepter l’invitation et s’authentifier directement. Les autres utilisateurs reçoivent un code de passage unique pour valider leur identité ([authentification à code unique](https://docs.microsoft.com/azure/active-directory/external-identities/one-time-passcode) requise).
4. Après avoir accepté l'invitation, l'invité peut [participer à l'équipe et aux canaux](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499), recevoir et répondre à des messages de canal, [accéder aux fichiers dans les canaux](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), participer aux conversations, rejoindre des réunions, collaborer sur des documents, etc. 

Dans Teams, les invités sont clairement identifiés. Le nom d'utilisateur d'un invité comprend l'étiquette **(Invité)**, et un canal inclut une icône indiquant qu’il y a des invités dans l’équipe. Pour obtenir plus d'informations, voir [À quoi ressemble l’expérience des invités](guest-experience.md).
  
Les invités peuvent quitter l’équipe Teams à tout moment. Pour plus d'informations, reportez-vous à l'article [Comment quitter une équipe ?](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)

> [!NOTE]
> La sortie de l’équipe n’entraîne pas la suppression du compte invité de l’annuaire de votre organisation. Pour cela, vous devez disposer d’un administrateur global Microsoft 365 ou d’un administrateur Azure AD.

## <a name="licensing-for-guest-access"></a>Gestion des licences pour l’accès invité

L’accès invité est inclus dans tous les abonnements Microsoft 365 Business standard, Microsoft 365 entreprise et Microsoft 365 éducation. Aucune licence Microsoft 365 supplémentaire n’est nécessaire. Teams ne limite pas le nombre d’invités que vous pouvez ajouter. Cependant, le nombre total d’invités pouvant être ajoutés à votre client peut être limité par les fonctionnalités payantes d’Azure AD. Pour plus d’informations, reportez-vous à la section [modèle de facturation d’identités externes Azure ad](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).

> [!NOTE]
> Les utilisateurs de votre organisation qui ont des plans d’abonnement Microsoft 365 autonomes, tels qu’Exchange Online plan 2, ne peuvent pas être invités en tant qu’invités à votre organisation, car teams les considère comme appartenant à la même organisation. Pour que ces utilisateurs puissent utiliser des équipes, une offre Microsoft 365 Business Standard, Office 365 Entreprise ou Office 365 Éducation doivent leur être attribuée. 

## <a name="guest-access-reviews"></a>Avis sur l’accès invité

Vous pouvez utiliser Azure AD pour créer une révision d’accès pour les membres du groupe ou les utilisateurs assignés à une application. La création d’avis périodiques peut vous permettre de gagner du temps. Si vous avez besoin de passer en revue régulièrement les utilisateurs qui ont accès à une application, une équipe ou qui sont membres d’un groupe, vous pouvez définir la fréquence de ces avis. 

Vous pouvez effectuer une révision par accès invité vous-même, demander aux invités de passer en revue leur appartenance ou demander à un propriétaire d’application ou à un concepteur de décision d’entreprise de procéder à la révision. Utiliser le portail Azure pour effectuer des révisions de l’accès invité. Pour plus d’informations, voir [gérer l’accès invité avec les avis sur Azure ad Access](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).

## <a name="related-topics"></a>Voir aussi

[Collaborer avec des personnes extérieures à votre organisation](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Bloquer les utilisateurs invités d’un groupe Microsoft 365 spécifique ou d’une équipe Microsoft teams](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Créer un environnement de partage d’invité sécurisé](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

[Contacter le support relatif aux produits d’entreprises- Aide de l’administrateur](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[Configurer teams avec trois niveaux de protection](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)

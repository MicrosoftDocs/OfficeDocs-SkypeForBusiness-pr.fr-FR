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
ms.openlocfilehash: 09090cc2061c3d138af2b3092e987293255a1134
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662039"
---
# <a name="guest-access-in-microsoft-teams"></a>Accès invité dans Microsoft Teams

L’accès invité vous permet d’accéder à Teams, aux documents dans des canaux, aux ressources, aux conversations et aux applications pour les personnes extérieures à votre organisation, tout en gardant le contrôle sur vos données d’entreprise.

Un invité est une personne qui n'est ni un employé, ni un étudiant ni un membre de votre organisation. Il ne dispose pas d'aucun compte scolaire ni professionnel lié à votre organisation. Il peut par exemple s'agir de partenaires, sous-traitants, fournisseurs ou consultants. Toute personne qui ne fait pas partie de votre organisation peut être ajouté en tant qu’invité dans Teams. Cela signifie que tout le monde avec un compte professionnel (autrement dit, un compte Azure Active Directory) ou un compte de messagerie consommateur (avec Outlook.com, Gmail.com ou d’autres personnes) peut participer en tant qu’invité dans Teams, avec un accès à des équipes et des expériences de canal.

Les invités dans Teams bénéficient de la même protection en matière de conformité et d’audit que les autres utilisateurs de Microsoft 365, et les invités peuvent être gérés dans Azure AD. L’accès invité est soumis à Azure AD et aux limites de service Microsoft 365 ou Office 365.

L’expérience des invités comporte des limitations de par sa conception. Pour consulter la liste complète de ce qu’un invité peut et ne peut pas faire dans Teams, consultez [comparaison des fonctionnalités des membres d’équipe et des invités](guest-experience.md#comparison-of-team-member-and-guest-capabilities).

> [!IMPORTANT]
> Les invités suivent les paramètres à l’échelle de l’Organisation pour le mode de mise à niveau de coexistence. Il n’est pas possible de modifier cela.

Pour configurer l’accès invité, consultez [Collaborer avec des invités dans une équipe](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team). 

Pour comparer l’accès externe (fédération) avec l’accès invité (et décider de celui que vous devez utiliser), lisez [Communiquer avec des utilisateurs d’autres organisations dans Teams](communicate-with-users-from-other-organizations.md).

## <a name="set-up-guest-access"></a>Configurer l’accès invité

L’accès invité dans Teams nécessite la configuration d’autres paramètres dans Microsoft 365, notamment les paramètres dans Azure AD, les groupes Microsoft 365 et SharePoint. Si vous êtes prêt à commencer à inviter des personnes à faire partie d'une équipe, lisez ce qui suit :

- Pour configurer l’accès invité pour Teams à des fins d’utilisation générale, consultez [Collaborer avec des invités dans une équipe](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).
- Pour collaborer avec une organisation partenaire qui utilise Azure Active Directory et autoriser les invités à s’inscrire automatiquement pour l’accès d’équipe, consultez [créer un extranet B2B avec des invités gérés](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).

L'accès invité dans Teams est un paramètre qui s'applique à toute l'organisation et qui est désactivé par défaut. Vous pouvez contrôler l’accès invité à des équipes individuelles à l’aide d’[étiquettes de confidentialité](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

## <a name="how-a-guest-becomes-a-member-of-a-team"></a>Comment un invité peut devenir membre d'une équipe

1. Un propriétaire d'équipe ou un administrateur Microsoft 365 [ajoute un invité à une équipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. L'invité reçoit un e-mail de bienvenue de la part du propriétaire de l’équipe, ainsi que des informations sur l’équipe et sur ce à quoi s'attendre en tant que membre.
3. L'invité accepte l'invitation.
  Les invités disposant d’un compte professionnel ou scolaire dans Azure Active Directory peuvent accepter l’invitation et s’authentifier directement. Les autres utilisateurs reçoivent un code d’accès unique pour valider leur identité ([Authentification à code secret unique](https://docs.microsoft.com/azure/active-directory/external-identities/one-time-passcode) obligatoire).
4. Après avoir accepté l'invitation, l'invité peut [participer à l'équipe et aux canaux](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499), recevoir et répondre à des messages de canal, [accéder aux fichiers dans les canaux](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), participer aux conversations, rejoindre des réunions, collaborer sur des documents, etc. 

Dans Teams, les invités sont clairement identifiés. Le nom d’un invité inclut l’étiquette **(invité)** et un canal inclut une icône pour indiquer qu’il existe des invités sur l’équipe. Pour obtenir plus d'informations, voir [À quoi ressemble l’expérience des invités](guest-experience.md).
  
Les invités peuvent quitter l’équipe Teams à tout moment. Pour plus d'informations, reportez-vous à l'article [Comment quitter une équipe ?](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)

> [!NOTE]
> Quitter l’équipe ne signifie pas que le compte Invité est supprimé de votre l’organisation. Cette opération doit être effectuée par un administrateur général Microsoft 365 ou un administrateur Azure AD.

## <a name="licensing-for-guest-access"></a>Gestion des licences pour l’accès invité

L’accès invité est inclus dans tous les abonnements Office 365 Business Premium, Microsoft 365 Enterprise et Microsoft 365 Éducation. Aucune licence Microsoft 365 supplémentaire n'est requise. Teams ne limite pas le nombre d’invités que vous pouvez ajouter. Cependant, le nombre total d’invités pouvant être ajoutés à votre client peut être limité par les fonctionnalités payantes d’Azure AD. Pour plus d’informations, consultez [Modèle de facturation pour Azure Active Directory for External Identities](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).

> [!NOTE]
> Les utilisateurs de votre organisation qui ont uniquement des offres d’abonnement Microsoft 365 autonomes, telles que Exchange Online Plan 2, ne peuvent pas être invités en tant qu’invités à votre organisation, car les équipes considèrent ces utilisateurs comme membres de la même organisation. Pour que ces utilisateurs puissent utiliser des équipes, une offre Office 365 Business Premium, Office 365 Entreprise ou Office 365 Éducation doivent leur être attribuée. 

## <a name="guest-access-reviews"></a>Révisions de l’accès invité

Vous pouvez utiliser Azure AD pour créer une révision d’accès pour les membres du groupe ou les utilisateurs affectés à une application. La création de critiques d’accès récurrents vous permet de gagner du temps. Si vous devez examiner régulièrement les utilisateurs qui ont accès à une application, à une équipe ou sont membres d’un groupe, vous pouvez définir la fréquence de ces révisions. 

Vous pouvez effectuer une révision de l’accès invité vous-même, demander aux invités de passer en revue leur propre appartenance, ou demander au propriétaire de l’application ou au décideur d’entreprise d’effectuer la révision d’accès. Utilisez le portail Azure pour effectuer des révisions de l’accès invité. Pour plus d’information, consultez [Gérer l’accès invité avec les révisions d’accès Azure AD](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).

## <a name="related-topics"></a>Voir aussi

[Collaborer avec des personnes extérieures à votre organisation](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Bloquer des invités d’un groupe Microsoft 365 spécifique ou d’une équipe Microsoft teams](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Créer un environnement de partage sécurisé avec des invités](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

[Contacter le support relatif aux produits d’entreprises - Aide de l’administrateur](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[Configurer Teams avec trois niveaux de protection](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)

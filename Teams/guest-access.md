---
title: Accès invité dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
search.appverid: MET150
ms.localizationpriority: high
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.guestaccess.overview
- chat-teams-channels-revamp
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
description: L'accès invité dans Microsoft Teams permet aux équipes de votre organisation de collaborer avec des personnes extérieures en leur accordant l'accès aux équipes et aux canaux.
ms.openlocfilehash: 399cd1c0aecb7377292810b26cd123873405f547
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198466"
---
# <a name="guest-access-in-microsoft-teams"></a>Accès invité dans Microsoft Teams

L’accès invité vous permet d’accéder à Teams, aux documents dans des canaux, aux ressources, aux conversations et aux applications pour les personnes extérieures à votre organisation, tout en gardant le contrôle sur vos données d’entreprise. Voir [Configurer une collaboration sécurisée avec Microsoft 365 et Microsoft Teams ](/microsoft-365/solutions/setup-secure-collaboration-with-teams). L'accès invité dans Teams est un paramètre à l'échelle de l'organisation et est activé par défaut. Vous pouvez contrôler l’accès invité à des équipes individuelles à l’aide d’[étiquettes de confidentialité](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

> [!NOTE]
> Si vous voulez simplement rechercher, appeler, discuter et configurer des réunions avec des personnes d’autres organisations, utilisez [Accès externe](manage-external-access.md).

Un invité est une personne qui n’a pas de compte scolaire ou professionnel avec votre organisation. Il peut par exemple s'agir de partenaires, sous-traitants, fournisseurs ou consultants. Toute personne qui ne fait pas partie de votre organisation peut être ajouté en tant qu’invité dans Teams. Cela signifie que tout le monde avec un compte professionnel (autrement dit, un compte Azure Active Directory) ou un compte de messagerie consommateur (avec Outlook.com, Gmail.com ou d’autres personnes) peut participer en tant qu’invité dans Teams, avec un accès à des équipes et des expériences de canal.

When you invite a guest to Teams, a guest account is created for them in Azure Active Directory and they are covered by the same compliance and auditing protection as other Microsoft 365 users. Guest access is subject to Azure AD and Microsoft 365 service limits.

The guest experience has limitations by design. For a full list of what a guest can and can't do in Teams, see [Guest access in Microsoft Teams](guest-experience.md).

> [!IMPORTANT]
> Guests follow Teams Org-wide settings for the coexistence Upgrade mode. This can't be changed.

Pour comparer l’accès externe (fédération) avec l’accès invité (et décider de celui que vous devez utiliser), lisez [Communiquer avec des utilisateurs d’autres organisations dans Teams](communicate-with-users-from-other-organizations.md).

Shared channels offer an alternative to guest access, allowing you to invite people outside your organization without requiring a guest account in Azure AD. To compare guest access with shared channels, see [Plan external collaboration](/microsoft-365/solutions/plan-external-collaboration).

Pour configurer l’accès invité, consultez [Collaborer avec des invités dans une équipe](/microsoft-365/solutions/collaborate-as-team). 

## <a name="set-up-guest-access"></a>Configurer l’accès invité

L’accès invité dans Teams nécessite la configuration d’autres paramètres dans Microsoft 365, notamment les paramètres dans Azure AD, les groupes Microsoft 365 et SharePoint. Si vous êtes prêt à commencer à inviter des personnes à faire partie d'une équipe, lisez ce qui suit :

- Pour configurer l’accès invité pour Teams à des fins d’utilisation générale, consultez [Collaborer avec des invités dans une équipe](/microsoft-365/solutions/collaborate-as-team).
- Pour collaborer avec une organisation partenaire qui utilise Azure Active Directory et autoriser les invités à s’inscrire automatiquement pour l’accès d’équipe, consultez [créer un extranet B2B avec des invités gérés](/microsoft-365/solutions/b2b-extranet).

> [!NOTE]
> Si vous êtes un administrateur et que vous rencontrez des problèmes avec l'accès invité dans Microsoft Teams, sélectionnez **Exécuter les tests** ci-dessous, qui remplira le diagnostic d'accès invité dans le centre d’Administration Microsoft 365. Ces tests vérifieront votre configuration et recommanderont rapidement les prochaines étapes pour activer l'accès invité pour votre locataire.
>> [!div class="nextstepaction"]
>> [Exécuter des tests : accès invité](https://aka.ms/TeamsGuestAccessDiagDMC)

## <a name="how-a-guest-gets-added-to-a-team"></a>Comment un invité est ajouté à une équipe

1. Un propriétaire d'équipe ou un administrateur Microsoft 365 [ajoute un invité à une équipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. L'invité reçoit un courriel de bienvenue du propriétaire de l'équipe, avec des informations sur l'équipe et ce à quoi il peut s'attendre maintenant qu'il a été ajouté.
3. L'invité accepte l'invitation.
  Les invités disposant d’un compte professionnel ou scolaire dans Azure Active Directory peuvent accepter l’invitation et s’authentifier directement. Les autres utilisateurs reçoivent un code d’accès unique pour valider leur identité ([Authentification à code secret unique](/azure/active-directory/external-identities/one-time-passcode) obligatoire).
4. Après avoir accepté l'invitation, l'invité peut [participer à l'équipe et aux canaux](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499), recevoir et répondre à des messages de canal, [accéder aux fichiers dans les canaux](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), participer aux conversations, rejoindre des réunions, collaborer sur des documents, etc. 

Dans Teams, les invités sont clairement identifiés. Le nom d'un invité comprend l'étiquette **(Invité)**, et un canal inclut une icône indiquant qu’il y a des invités dans l’équipe. Pour obtenir plus d'informations, voir [À quoi ressemble l’expérience des invités](guest-experience.md).
  
Les invités peuvent quitter l’équipe Teams à tout moment. Pour plus d'informations, reportez-vous à l'article [Comment quitter une équipe ?](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)

> [!NOTE]
> Quitter l’équipe ne signifie pas que le compte Invité est supprimé de votre l’organisation. Cette opération doit être effectuée par un administrateur général Microsoft 365 ou un administrateur Azure AD.

## <a name="licensing-for-guest-access"></a>Gestion des licences pour l’accès invité

L’accès invité peut être utilisé avec tous les abonnements Microsoft 365 Business Standard, Microsoft 365 Entreprise; et Microsoft 365 Éducation. Aucune licence Microsoft 365 supplémentaire n'est requise. Le [modèle de facturation pour Azure AD External Identities](/azure/active-directory/b2b/licensing-guidance) s’applique aux invités dans Microsoft 365. Seules les personnes extérieures à votre organisation peuvent être invitées en tant qu’invités.

> [!NOTE]
> La conversion d'un compte invité en un compte membre Azure AD ou la conversion d'un compte membre Azure AD en un invité n'est pas prise en charge par Teams.

## <a name="guest-access-reviews"></a>Révisions de l’accès invité

Vous pouvez utiliser Azure AD pour créer une révision d’accès pour les utilisateurs qui se trouvent dans des groupes ou qui ont été affectés à une application. La création de critiques d’accès récurrents vous permet de gagner du temps. Si vous devez examiner régulièrement les utilisateurs qui ont accès à une application, une équipe ou un groupe, vous pouvez définir la fréquence de ces révisions. 

Vous pouvez effectuer une révision d’accès invité vous-même, demander aux invités de vérifier leur propre accès ou demander à un propriétaire d’application ou à un décideur d’entreprise d’effectuer la révision d’accès. Utilisez le portail Azure pour effectuer des révisions de l’accès invité. Pour plus d’information, consultez [Gérer l’accès invité avec les révisions d’accès Azure AD](/azure/active-directory/governance/manage-guest-access-with-access-reviews).

## <a name="related-topics"></a>Voir aussi

[Collaborer avec des personnes extérieures à votre organisation](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Bloquer des invités d’un groupe Microsoft 365 spécifique ou d’une équipe Microsoft Teams](/microsoft-365/solutions/per-group-guest-access)

[Créer un environnement de partage sécurisé avec des invités](/microsoft-365/solutions/create-secure-guest-sharing-environment)

[Contacter le support relatif aux produits d’entreprises - Aide de l’administrateur](/microsoft-365/admin/contact-support-for-business-products)

[Configurer Teams avec trois niveaux de protection](/microsoft-365/solutions/configure-teams-three-tiers-protection)

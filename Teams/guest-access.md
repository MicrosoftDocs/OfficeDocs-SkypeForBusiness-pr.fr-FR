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
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
description: L'accès invité dans Microsoft Teams permet aux équipes de votre organisation de collaborer avec des personnes extérieures en leur accordant l'accès aux équipes et aux canaux.
ms.openlocfilehash: 80c1fcb9012efbc1809b1d1d4252c9801d148ba9
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/22/2021
ms.locfileid: "60537085"
---
# <a name="guest-access-in-microsoft-teams"></a>Accès invité dans Microsoft Teams

L’accès invité vous permet d’accéder à Teams, aux documents dans des canaux, aux ressources, aux conversations et aux applications pour les personnes extérieures à votre organisation, tout en gardant le contrôle sur vos données d’entreprise. Voir [Configurer une collaboration sécurisée avec Microsoft 365 et Microsoft Teams ](/microsoft-365/solutions/setup-secure-collaboration-with-teams). L'accès invité dans Teams est un paramètre à l'échelle de l'organisation et est activé par défaut. Vous pouvez contrôler l’accès invité à des équipes individuelles à l’aide d’[étiquettes de confidentialité](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

> [!NOTE]
> Si vous voulez simplement rechercher, appeler, discuter et configurer des réunions avec des personnes d’autres organisations, utilisez [Accès externe](manage-external-access.md).

Un invité est une personne qui n'est ni un employé, ni un étudiant ni un membre de votre organisation. Il ne dispose pas d'aucun compte scolaire ni professionnel lié à votre organisation. Il peut par exemple s'agir de partenaires, sous-traitants, fournisseurs ou consultants. Toute personne qui ne fait pas partie de votre organisation peut être ajouté en tant qu’invité dans Teams. Cela signifie que tout le monde avec un compte professionnel (autrement dit, un compte Azure Active Directory) ou un compte de messagerie consommateur (avec Outlook.com, Gmail.com ou d’autres personnes) peut participer en tant qu’invité dans Teams, avec un accès à des équipes et des expériences de canal.

Les invités dans Teams bénéficient de la même protection en matière de conformité et d’audit que les autres utilisateurs de Microsoft 365, et les invités peuvent être gérés dans Azure AD. L’accès invité est soumis à Azure AD et aux limites de service Microsoft 365 ou Office 365.

L'expérience client a des limites de par sa conception. Pour obtenir une liste complète de ce qu'un invité peut et ne peut pas faire dans Teams, consultez [la comparaison des capacités des membres de l'équipe et des invités](guest-experience.md#comparison-of-team-member-and-guest-capabilities).

> [!IMPORTANT]
> Les invités suivent les paramètres à l’échelle de l’organisation Teams pour le mode de mise à niveau de coexistence. Cela ne peut pas être modifié.

Pour configurer l’accès invité, consultez [Collaborer avec des invités dans une équipe](/microsoft-365/solutions/collaborate-as-team). 

Pour comparer l’accès externe (fédération) avec l’accès invité (et décider de celui que vous devez utiliser), lisez [Communiquer avec des utilisateurs d’autres organisations dans Teams](communicate-with-users-from-other-organizations.md).

## <a name="set-up-guest-access"></a>Configurer l’accès invité

L’accès invité dans Teams nécessite la configuration d’autres paramètres dans Microsoft 365, notamment les paramètres dans Azure AD, les groupes Microsoft 365 et SharePoint. Si vous êtes prêt à commencer à inviter des personnes à faire partie d'une équipe, lisez ce qui suit :

- Pour configurer l’accès invité pour Teams à des fins d’utilisation générale, consultez [Collaborer avec des invités dans une équipe](/microsoft-365/solutions/collaborate-as-team).
- Pour collaborer avec une organisation partenaire qui utilise Azure Active Directory et autoriser les invités à s’inscrire automatiquement pour l’accès d’équipe, consultez [créer un extranet B2B avec des invités gérés](/microsoft-365/solutions/b2b-extranet).

> [!NOTE]
> Si vous êtes un administrateur et que vous rencontrez des problèmes avec l'accès invité dans Microsoft Teams, sélectionnez **Exécuter les tests** ci-dessous, qui remplira le diagnostic d'accès invité dans le centre d’Administration Microsoft 365. Ces tests vérifieront votre configuration et recommanderont rapidement les prochaines étapes pour activer l'accès invité pour votre locataire.
>> [!div class="nextstepaction"]
>> [Exécuter des tests : accès invité](https://aka.ms/TeamsGuestAccessDiagDMC)

### <a name="turning-guest-access-off"></a>Désactivation de l’accès invité

Si vous désactivez l’accès invité dans Teams, les invités existants perdent l’accès à leur équipe. Toutefois, ils ne sont pas supprimés de l’équipe. Ils sont toujours visibles par les membres de l’équipe et peuvent être @mentioned. Si vous réactivez l’accès invité Teams, celui-ci retrouvera l’accès.

Si vous envisagez de laisser l’accès invité désactivé, vous pouvez conseiller aux propriétaires de votre équipe de supprimer manuellement les comptes invités de leurs équipes. Bien que ces invités n’aient pas accès, le fait d’avoir leurs comptes visibles dans l’équipe peut entraîner une confusion pour d’autres membres de l’équipe.

## <a name="how-a-guest-becomes-a-member-of-a-team"></a>Comment un invité peut devenir membre d'une équipe

1. Un propriétaire d'équipe ou un administrateur Microsoft 365 [ajoute un invité à une équipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. L'invité reçoit un e-mail de bienvenue de la part du propriétaire de l’équipe, ainsi que des informations sur l’équipe et sur ce à quoi s'attendre en tant que membre.
3. L'invité accepte l'invitation.
  Les invités disposant d’un compte professionnel ou scolaire dans Azure Active Directory peuvent accepter l’invitation et s’authentifier directement. Les autres utilisateurs reçoivent un code d’accès unique pour valider leur identité ([Authentification à code secret unique](/azure/active-directory/external-identities/one-time-passcode) obligatoire).
4. Après avoir accepté l'invitation, l'invité peut [participer à l'équipe et aux canaux](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499), recevoir et répondre à des messages de canal, [accéder aux fichiers dans les canaux](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), participer aux conversations, rejoindre des réunions, collaborer sur des documents, etc. 

Dans Teams, les invités sont clairement identifiés. Le nom d'un invité comprend l'étiquette **(Invité)**, et un canal inclut une icône indiquant qu’il y a des invités dans l’équipe. Pour obtenir plus d'informations, voir [À quoi ressemble l’expérience des invités](guest-experience.md).
  
Les invités peuvent quitter l’équipe Teams à tout moment. Pour plus d'informations, reportez-vous à l'article [Comment quitter une équipe ?](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)

> [!NOTE]
> Quitter l’équipe ne signifie pas que le compte Invité est supprimé de votre l’organisation. Cette opération doit être effectuée par un administrateur général Microsoft 365 ou un administrateur Azure AD.

## <a name="licensing-for-guest-access"></a>Gestion des licences pour l’accès invité

L’accès invité peut être utilisé avec tous les abonnements Microsoft 365 Business Standard, Microsoft 365 Entreprise; et Microsoft 365 Éducation. Aucune licence Microsoft 365 supplémentaire n'est requise. Le [modèle de facturation pour Azure AD External Identities](/azure/active-directory/b2b/licensing-guidance) s’applique aux invités dans Microsoft 365. Seules les personnes extérieures à votre organisation peuvent être invitées en tant qu’invités.

## <a name="guest-access-reviews"></a>Révisions de l’accès invité

Vous pouvez utiliser Azure AD pour créer une révision d’accès pour les membres du groupe ou les utilisateurs affectés à une application. La création de critiques d’accès récurrents vous permet de gagner du temps. Si vous devez examiner régulièrement les utilisateurs qui ont accès à une application, à une équipe ou sont membres d’un groupe, vous pouvez définir la fréquence de ces révisions. 

Vous pouvez effectuer une révision de l’accès invité vous-même, demander aux invités de passer en revue leur propre appartenance, ou demander au propriétaire de l’application ou au décideur d’entreprise d’effectuer la révision d’accès. Utilisez le portail Azure pour effectuer des révisions de l’accès invité. Pour plus d’information, consultez [Gérer l’accès invité avec les révisions d’accès Azure AD](/azure/active-directory/governance/manage-guest-access-with-access-reviews).

## <a name="related-topics"></a>Voir aussi

[Collaborer avec des personnes extérieures à votre organisation](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Bloquer des invités d’un groupe Microsoft 365 spécifique ou d’une équipe Microsoft Teams](/microsoft-365/solutions/per-group-guest-access)

[Créer un environnement de partage sécurisé avec des invités](/microsoft-365/solutions/create-secure-guest-sharing-environment)

[Contacter le support relatif aux produits d’entreprises - Aide de l’administrateur](/microsoft-365/admin/contact-support-for-business-products)

[Configurer Teams avec trois niveaux de protection](/microsoft-365/solutions/configure-teams-three-tiers-protection)

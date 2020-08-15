---
title: Accès invité dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
description: L'accès invité dans Microsoft Teams permet aux équipes de votre organisation de collaborer avec des personnes extérieures en leur accordant l'accès aux équipes et aux canaux.
ms.openlocfilehash: f04fce7f75df32111b2577119c12b14eadf963b9
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761240"
---
# <a name="guest-access-in-microsoft-teams"></a>Accès invité dans Microsoft Teams

L'accès invité permet aux équipes de votre organisation de collaborer avec des personnes extérieures à votre organisation en leur accordant l'accès aux équipes et aux canaux existants dans Teams. Toute personne disposant d’un compte de messagerie professionnel ou professionnel (par exemple, Microsoft 365, Outlook, Gmail, etc.) peut participer en tant qu’invité dans une équipe disposant d’un accès complet aux discussions d’équipe, aux réunions et aux fichiers. En tant qu’administrateur Teams, vous contrôlez les fonctionnalités que les invités peuvent (et ne peuvent pas) utiliser dans les équipes : consultez [Gérer l’accès invité](manage-guests.md).

Pour comparer l’accès externe (fédération) avec l’accès invité (et décider de celui que vous devez utiliser), lisez [Communiquer avec des utilisateurs d’autres organisations dans Teams](communicate-with-users-from-other-organizations.md).

L'accès invité est un paramètre de niveau organisation dans Teams, désactivé par défaut. (Vous pouvez contrôler l’accès invité aux équipes individuelles à l’aide d' [étiquettes de sensibilité](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).)

Si vous êtes prêt à commencer à inviter des invités à des équipes, consultez l’une des rubriques suivantes :

- Pour configurer l’accès invité pour les équipes pour une utilisation générale, voir [collaborer avec des invités dans une équipe](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).
- Pour collaborer avec une organisation de partenaire qui utilise Azure Active Directory et permettre aux invités d’être automatiquement inscrits pour l’accès à l’équipe, voir [créer un extranet B2B avec des invités gérés](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).

L’accès invité est soumis à Azure AD et aux limites de service Microsoft 365 ou Office 365.

> [!IMPORTANT]
> Les utilisateurs invités suivent les paramètres de niveau organisation Teams pour le mode de mise à niveau de coexistence. Il n’est pas possible de modifier cela.

## <a name="licensing-for-guest-access"></a>Gestion des licences pour l’accès invité

L’accès invité est inclus dans tous les abonnements Microsoft 365 Business Standard, Office 365 Enterprise et Office 365 Éducation. Aucune licence Microsoft 365 ou Office 365 supplémentaire n'est requise. Teams ne limite pas le nombre d’invités que vous pouvez ajouter. Cependant, le nombre total d’invités pouvant être ajoutés à votre client peut être limité par les fonctionnalités payantes d’Azure AD. Pour plus d’informations, consultez l’article [Affectation de licences Azure Active Directory B2B Collaboration](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).


> [!NOTE]
> Les utilisateurs de votre organisation qui ont uniquement des offres d’abonnement Microsoft 365 ou Office 365 autonomes, telles que Exchange Online Plan 2, ne peuvent pas être invités en tant qu’invités à votre organisation, car les équipes considèrent ces utilisateurs comme membres de la même organisation. Pour que ces utilisateurs puissent utiliser des équipes, une offre Microsoft 365 Business Standard, Office 365 Entreprise ou Office 365 Éducation doivent leur être attribuée. 

## <a name="who-is-a-guest"></a>Qu’est-ce qu’un invité ?

Un invité est une personne qui n'est ni un employé, ni un étudiant ni un membre de votre organisation. Il ne dispose pas d'aucun compte scolaire ni professionnel lié à votre organisation. Il peut par exemple s'agir de partenaires, sous-traitants, fournisseurs ou consultants. Toute personne qui ne fait pas partie de votre organisation peut être ajouté en tant qu’invité dans Teams. Cela signifie que tout le monde avec un compte professionnel (autrement dit, un compte Azure Active Directory) ou un compte de messagerie consommateur (avec Outlook.com, Gmail.com ou d’autres personnes) peut participer en tant qu’invité dans Teams, avec un accès complet à des équipes et des expériences de canal.

Pour en savoir plus sur ce qu’un invité peut et ne peut pas faire, lisez [Autoriser l’accès invité dans Microsoft Teams](teams-dependencies.md). Sinon, consultez le tableau de [comparaison des fonctionnalités des membres d’équipe et des invités](guest-experience.md#comparison-of-team-member-and-guest-capabilities). 

Pour finir, tous les invités dans teams sont couverts par la même protection de conformité et d’audit que le reste de Microsoft 365 et peuvent être gérés dans Azure AD.

## <a name="why-use-guest-access"></a>Pourquoi utiliser l’accès invité?

Grâce à l’accès invité, les organisations qui utilisent Teams peuvent fournir à leurs partenaires un accès aux équipes, documents dans les canaux, ressources, conversations et applications, tout en conservant le contrôle total de leurs propres données d'entreprise. 

## <a name="understand-the-limitations-for-guests"></a>Comprendre les limitations pour les invités

L’expérience des invités comporte des limitations de par sa conception. Assurez-vous de bien comprendre l’expérience des invités de manière à ne pas essayer de résoudre un problème qui n’en est pas un. Vous trouverez ci-dessous une liste de fonctionnalités qui ne sont pas disponibles pour un invité dans Microsoft teams :

- OneDrive
- Recherche de personnes à l’extérieur de Teams
- Calendrier, réunions planifiées ou détails de la réunion
- PSTN
- Organigramme hiérarchique
- Créer ou réviser une équipe
- Rechercher une équipe
- Télécharger des fichiers dans une conversation de personne à personne
- Pour l’instant, teams prend uniquement en charge [les types d’utilisateurs invités État 1 et 2](https://docs.microsoft.com/azure/active-directory/b2b/user-properties) .

Pour consulter la liste complète de ce qu’un invité peut et ne peut pas faire dans Teams, voir tableau [comparaison des fonctionnalités des membres d’équipe et des invités](guest-experience.md#comparison-of-team-member-and-guest-capabilities). Pour en savoir plus sur l’accès invité au niveau Microsoft 365, voir [collaborer avec des personnes extérieures à votre organisation](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization).


## <a name="related-topics"></a>Voir aussi

[Contacter le support relatif aux produits d’entreprises- Aide de l’administrateur](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[Configurer teams avec trois niveaux de protection](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)

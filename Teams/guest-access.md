---
title: Accès invité dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
description: L'accès invité dans Microsoft Teams permet aux équipes de votre organisation de collaborer avec des personnes extérieures en leur accordant l'accès aux équipes et aux canaux.
localization_priority: Priority
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a0bba0c8893ee706061b989f95d4e22619fa4f9
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753279"
---
<a name="guest-access-in-microsoft-teams"></a>Accès invité dans Microsoft Teams
======================================

L’accès invité vous permet d’ajouter des utilisateurs individuels situés hors de votre organisation à vos équipes et canaux dans Microsoft Teams. 

Pour comparer l’accès externe (fédération) avec l’accès invité (et décider de celui que vous devez utiliser), lisez [Communiquer avec des utilisateurs d’autres organisations dans Teams](communicate-with-users-from-other-organizations.md).

Si vous êtes prêt à activer l’accès invité au sein de votre organisation, commencez par le [liste de vérification de l’accès invité](guest-access-checklist.md).

## <a name="guest-access-overview"></a>Vue d’ensemble de l’accès invité

L'accès invité permet aux équipes de votre organisation de collaborer avec des personnes extérieures à votre organisation en leur accordant l'accès aux équipes et aux canaux existants dans Teams. Toutes les personnes ayant un compte de messagerie professionnel ou de particulier tel que Outlook, Gmail, etc. peuvent participer en tant qu’invitées dans Teams, avec un accès complet aux conversations, réunions et fichiers des équipes. En tant qu’administrateur Teams, vous contrôlez les fonctionnalités que les invités peuvent (et ne peuvent pas) utiliser dans les équipes : consultez [Gérer l’accès invité](manage-guests.md).

L'accès invité est un paramètre de niveau organisation dans Teams, désactivé par défaut. L’accès invité est soumis à Azure AD et aux limites de service Office 365.


> [!IMPORTANT]
> Les utilisateurs invités suivent les paramètres de niveau organisation Teams pour le mode de mise à niveau de coexistence. Il n’est pas possible de modifier cela.

## <a name="licensing-for-guest-access"></a>Gestion des licences pour l’accès invité

L'accès invité est fourni avec tous les abonnements Office 365 Business Premium, Office 365 Entreprise et Office 365 Education. Aucune licence Office 365 supplémentaire n'est requise. Teams ne limite pas le nombre d’invités que vous pouvez ajouter. Toutefois, le nombre total d’invités pouvant être ajoutés à votre client dépend de ce que votre licence Azure AD autorise (généralement 5 invités par utilisateur sous licence). Pour plus d’informations, consultez l’article [Affectation de licences Azure Active Directory B2B Collaboration](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).


> [!NOTE]
> Les utilisateurs de votre organisation qui ont uniquement des offres d’abonnement Office 365 autonomes, telles que Exchange Online Plan 2, ne peuvent pas être invités en tant qu’invités à votre organisation, car les équipes considèrent ces utilisateurs comme membres de la même organisation. Pour ces utilisateurs utilisant Teams, un abonnement Office 365 Business Premium, Office 365 Entreprise ou Office 365 éducation doivent leur être attribués. 

## <a name="who-is-a-guest"></a>Qu’est-ce qu’un invité ?

Un invité est une personne qui n'est ni un employé, ni un étudiant ni un membre de votre organisation. Il ne dispose pas d'aucun compte scolaire ni professionnel lié à votre organisation. Il peut par exemple s'agir de partenaires, sous-traitants, fournisseurs ou consultants. Toute personne qui ne fait pas partie de votre organisation peut être ajouté en tant qu’invité dans Teams. Cela signifie que tout le monde avec un compte professionnel (autrement dit, un compte Azure Active Directory) ou un compte de messagerie consommateur (avec Outlook.com, Gmail.com ou d’autres personnes) peut participer en tant qu’invité dans Teams, avec un accès complet à des équipes et des expériences de canal.

Pour en savoir plus sur ce qu’un invité peut et ne peut pas faire, lisez [Autoriser l’accès invité dans Microsoft Teams](teams-dependencies.md). Sinon, consultez le tableau de [comparaison des fonctionnalités des membres d’équipe et des invités](guest-experience.md#comparison-of-team-member-and-guest-capabilities). 

Finalement, tous les invités dans Teams bénéficient de la même protection en matière de conformité et d’audit que les autres utilisateurs d’Office 365, et les invités peuvent être gérés en toute sécurité dans Azure AD.

## <a name="why-use-guest-access"></a>Pourquoi utiliser l’accès invité?

Grâce à l’accès invité, les organisations qui utilisent Teams peuvent fournir à leurs partenaires un accès aux équipes, documents dans les canaux, ressources, conversations et applications, tout en conservant le contrôle total de leurs propres données d'entreprise. Tous les invités dans Teams bénéficient de la même protection en matière de conformité et d’audit que les autres utilisateurs d’Office 365, et les invités peuvent être gérés en toute sécurité dans Azure AD.  

## <a name="understand-the-limitations-for-guests"></a>Comprendre les limitations pour les invités

L’expérience des invités comporte des limitations de par sa conception. Assurez-vous de bien comprendre l’expérience des invités de manière à ne pas essayer de résoudre un problème qui n’en est pas un. Par exemple, voici une liste de certaines des fonctionnalités qui ne sont pas disponibles pour un invité dans Microsoft Teams :

- OneDrive Entreprise
- Recherche de personnes à l’extérieur de Teams
- Calendrier, réunions planifiées ou détails de la réunion
- PSTN
- Organigramme hiérarchique
- Créer ou réviser une équipe
- Rechercher une équipe
- Télécharger des fichiers dans une conversation de personne à personne
- Les invités peuvent toujours rechercher et trouver des utilisateurs (à l’extérieur de leur équipe) s’ils connaissent l’ID d’e-mail complet de l’utilisateur. Pour empêcher cela, les administrateurs informatiques peuvent utiliser des modèles tels que [la recherche étendue dans l’annuaire](teams-scoped-directory-search.md) qui ont la possibilité de restreindre les invités à leur propre LAG virtuelle.

Pour consulter la liste complète de ce qu’un invité peut et ne peut pas faire dans Teams, voir tableau [comparaison des fonctionnalités des membres d’équipe et des invités](guest-experience.md#comparison-of-team-member-and-guest-capabilities). Pour en savoir plus sur l’accès invité au niveau Office 365, lisez [Ajout d’invités à des groupes Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).

## <a name="how-does-external-access-federation-compare-to-guest-access"></a>Qu’est-ce que l’accès externe (fédération) par rapport à l’accès invité ?

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>Plus d’informations

[Contacter le support relatif aux produits d’entreprises- Aide de l’administrateur](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)  
[Accès invité dans les Groupes Office 365](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  

---
title: Accès invité dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/25/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
description: L'accès invité dans Microsoft Teams permet aux équipes de votre organisation de collaborer avec des personnes extérieures en leur accordant l'accès aux équipes et aux canaux.
localization_priority: Priority
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: adf4f9068cffa2fa3af5026f1003075e57d98bfc
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244081"
---
<a name="guest-access-in-microsoft-teams"></a>Accès invité dans Microsoft Teams
======================================

L’accès Invité est l’une des fonctions les plus demandées par les clients. Pour vous tenir au courant de notre progression et nous faire part de vos commentaires :

- Si vous rencontrez des problèmes avec l’accès invité, consultez les [Problèmes connus pour Microsoft Teams](Known-issues.md).
- Vous trouverez des informations sur les fonctionnalités à venir, nouvelles ou mises à jour, dans la [Feuille de route de Teams](https://aka.ms/teamsroadmap).
- Indiquez-nous ce que vous souhaitez dans [Teams UserVoice](https://aka.ms/TeamsUserVoice).
- Partagez votre expérience dans la section Commentaires ci-dessous.

## <a name="guest-access-overview"></a>Vue d’ensemble de l’accès invité

L’accès invité permet aux équipes de votre organisation de collaborer avec des personnes à l’extérieur de votre organisation en leur accordant l'accès aux équipes et aux canaux. Toutes les personnes ayant un compte de messagerie professionnel ou de particulier tel que Outlook, Gmail, etc. peuvent participer en tant qu’invitées dans Teams, avec un accès complet aux conversations, réunions et fichiers des équipes.

L’accès invité est inclus dans de nombreux abonnements Office 365 sans nécessiter de licence supplémentaire. Pour plus d’informations sur les licences, voir [le guide de licence de collaboration Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).

L'accès invité est un paramètre de niveau client dans Microsoft Teams, désactivé par défaut. L’accès invité est soumis à Azure AD et aux limites de service Office 365.

> [!NOTE]
> Les utilisateurs de votre organisation qui ont uniquement des offres d’abonnement Office 365 autonomes, telles que Exchange Online Plan 2, ne peuvent pas être invités en tant qu’invités à votre organisation, car les équipes considèrent ces utilisateurs comme membres de la même organisation. Pour ces utilisateurs utilisant Teams, un abonnement Office 365 Business Premium, Office 365 Entreprise ou Office 365 éducation doivent leur être attribués. 

## <a name="who-is-a-guest"></a>Qu’est-ce qu’un invité ?

Un invité est une personne qui n'est ni un employé, ni un étudiant ni un membre de votre organisation. Il ne dispose pas d'aucun compte scolaire ni professionnel lié à votre organisation. Il peut par exemple s'agir de partenaires, sous-traitants, fournisseurs ou consultants. Toute personne qui ne fait pas partie de votre organisation peut être ajouté en tant qu’invité dans Teams. Cela signifie que tout le monde avec un compte professionnel (autrement dit, un compte Azure Active Directory) ou un compte de messagerie consommateur (avec Outlook.com, Gmail.com ou d’autres personnes) peut participer en tant qu’invité dans Teams, avec un accès complet à des équipes et des expériences de canal. (Vous pouvez lire les informations relatives aux restrictions d’invité dans[Autorisation de l’accès invité dans Microsoft Teams](teams-dependencies.md).) Tous les invités dans Teams bénéficient de la même protection en matière de conformité et d’audit que les autres utilisateurs d’Office 365, et les invités peuvent être gérés en toute sécurité dans Azure AD.

## <a name="why-use-guest-access"></a>Pourquoi utiliser l’accès invité?

Grâce à l’accès invité, les organisations qui utilisent Teams peuvent fournir à leurs partenaires un accès externe aux équipes, documents dans les canaux, ressources, conversations et applications, tout en conservant le contrôle total de leurs propres données d'entreprise. Tous les invités dans Teams bénéficient de la même protection en matière de conformité et d’audit que les autres utilisateurs d’Office 365, et les invités peuvent être gérés en toute sécurité dans Azure AD.  

Teams est basé sur les Groupes Office 365 et offre un nouveau moyen pour accéder aux ressources partagées d'un groupe Office 365. Teams est la meilleure solution de conversation permanente parmi les membres d'un groupe ou d'une équipe. Les groupes Office 365 sont un service disponible sous la forme d'un abonnement inter-applications qui donne accès à un ensemble de ressources partagées, telles qu'un site SharePoint ou un tableau de bord Power BI, pour permettre à l'équipe de collaborer efficacement et en toute sécurité. 

## <a name="how-does-guest-access-compare-to-external-access-federation"></a>Quelle est l’accès invité et quel est l’accès externe (fédération) ?

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>Plus d’informations

[Contacter le support relatif aux produits d’entreprises- Aide de l’administrateur](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)  
[Accès invité dans les Groupes Office 365](https://support.office.com/fr-FR/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  

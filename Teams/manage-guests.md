---
title: Gérer l'accès invité dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: Apprenez-en davantage sur la création de vos premières équipes et canaux, les premiers adoptateurs, surveiller l’utilisation et les commentaires, et obtenir des ressources pour planifier le déploiement à l’échelle de l’organisation.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fa45c5c307e33188548353a9a4d36086d804b278
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46655935"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Gérer l'accès invité dans Microsoft Teams
======================================

> [!IMPORTANT]
> Il est possible que vous deviez patienter quelques heures avant que les modifications soient prises en compte. 

**Guest** est un type d’utilisateur dans Microsoft Teams, inclus dans l’ensemble des abonnements Microsoft 365 entreprise, Office 365 entreprise, Microsoft 365 entreprise basique et Office 365 éducation. Aucune licence Microsoft 365 ou Office 365 supplémentaire n'est requise. En savoir plus sur la gestion des [licences d’accès invité](#guest-access-licensing-limits) ci-dessous.

L'accès invité de Teams est un paramètre de niveau client et est désactivé par défaut. Pour plus d’informations sur l’activation de l’accès invité, voir Activation ou désactivation de l' [accès invité aux équipes](set-up-guests.md)ou utilisation de la liste de vérification de l' [accès invité ](guest-access-checklist.md) pour vous guider dans la procédure d’installation.

Une fois que l’accès invité est activé, vous pouvez configurer les paramètres pour les invités en utilisant les contrôles décrits dans [gérer les paramètres d’équipe pour votre organisation](enable-features-office-365.md) et [gérer les équipes lors de la transition vers le nouveau centre d’administration Microsoft teams](manage-teams-skypeforbusiness-admin-center.md).     
    
Les administrateurs informatiques peuvent ajouter des invités au niveau du client, définir et gérer les stratégies et les autorisations des utilisateurs invités, et extraire des rapports sur l’activité des utilisateurs invités. Ces contrôles sont disponibles dans le centre d’administration Teams. Le contenu et les activités des utilisateurs invités sont soumis à la même protection de conformité et d’audit que le reste de Microsoft 365 ou d’Office 365.

Les propriétaires d’équipe peuvent inviter de nouveaux invités et ajouter des utilisateurs invités à leurs équipes dans le centre d’administration Teams. Identifiez les utilisateurs invités **sur la**  >  page de**gestion des équipes** et définissez les fonctionnalités liées aux canaux pour les invités dans la **Org-wide settings**  >  page**accès invité** des paramètres à l’échelle de l’organisation. Les paramètres permettent aux invités de créer, mettre à jour et supprimer des canaux, comme le montre l’illustration suivante.

![Paramètres des autorisations invité dans teams](media/manage-guest-access-image1.png)
  
Vous pouvez utiliser le portail Azure Active Directory (Azure AD) pour gérer les invités et leur accès aux ressources Microsoft 365 ou Office 365 et Teams. L’accès invité teams utilise les fonctionnalités de collaboration d’Azure AD Business-to-Business (B2B) comme infrastructure sous-jacente pour le stockage des informations de principes de sécurité, tels que les propriétés d’identité, l’appartenance et les paramètres d’authentification multifacteur. Pour en savoir plus sur Azure AD B2B, reportez-vous à la rubrique [qu’est-ce qu’Azure ad B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=853011) et [FAQ sur Azure Active Directory B2B](https://go.microsoft.com/fwlink/p/?linkid=853020).

> [!NOTE]
> Microsoft teams respecte toujours les paramètres externes Azure AD pour autoriser ou empêcher les ajouts d’utilisateurs invités au client. Pour plus d’informations, voir [autoriser l’accès invité dans Microsoft teams](Teams-dependencies.md).


## <a name="guest-access-licensing-limits"></a>Limites de licence d’accès invité

Teams ne limite pas le nombre d’invités que vous pouvez ajouter. Toutefois, le nombre total d’invités pouvant être ajoutés à votre client dépend de ce que votre licence Azure AD autorise (généralement 5 invités par utilisateur sous licence). Pour plus d’informations, consultez l’article [Affectation de licences Azure Active Directory B2B Collaboration](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).

En raison de ces limitations de licence (et pour garder votre client à jour), vous devez examiner régulièrement l’accès invité pour identifier les utilisateurs qui ont accès sans avoir besoin d’y accéder. Vous pouvez utiliser Azure AD pour créer une révision d’accès pour les membres du groupe ou les utilisateurs assignés à une application. La création d’avis périodiques peut vous permettre de gagner du temps. Si vous avez besoin de vérifier régulièrement les utilisateurs qui ont accès à une application ou qui sont membres d’un groupe, vous pouvez définir la fréquence de ces avis. 

Vous pouvez effectuer une révision par accès invité vous-même, demander aux invités de passer en revue leur appartenance ou demander à un propriétaire d’application ou à un concepteur de décision d’entreprise de procéder à la révision. Utiliser le portail Azure pour effectuer des révisions de l’accès invité. Pour plus d’informations, voir [gérer l’accès invité avec les avis sur Azure ad Access](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).

###  <a name="prerequisites-for-azure-ad-access-reviews"></a>Conditions préalables pour les avis sur Azure AD Access

Les avis sur l’accès sont disponibles avec l’édition Premium d’Azure AD, qui est incluse dans Microsoft entreprise Mobility + Security, E5. Pour plus d’informations, reportez-vous à la rubrique [éditions d’Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis). Chaque utilisateur qui interagit avec cette fonctionnalité en créant un avis, en remplissant un avis ou en confirmant son accès, doit disposer d’une licence.



## <a name="lag-time-for-guest-access-settings-to-take-effect"></a>Temps d’attente pour que les paramètres d’accès invités soient appliqués

Pour les paramètres d’accès invité dans Azure Active Directory, il faut quelques heures pour que les modifications prennent effet dans Microsoft 365 ou Office 365. Si un utilisateur voit le message « contactez votre administrateur » lorsqu’il essaye d’ajouter un invité à son équipe, c’est probablement parce que la fonction invité n’a pas été activée ou que les paramètres ne sont pas encore effectifs. Pour obtenir de l’aide sur les problèmes de configuration de l’accès invité, voir [résoudre les problèmes d’accès invité dans teams](troubleshoot-guest-access.md).

  
## <a name="external-access-federation-vs-guest-access"></a>Accès externe (fédération) et accès invité

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>Plus d’informations

Pour plus d’informations sur l’utilisation de PowerShell pour gérer l’accès invité, voir [Utiliser PowerShell pour contrôler l’accès invité à une équipe](guest-access-powershell.md).



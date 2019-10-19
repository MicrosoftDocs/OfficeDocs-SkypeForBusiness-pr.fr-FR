---
title: Gérer l'accès invité dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Les administrateurs informatiques peuvent ajouter des invités au niveau du client, définir et gérer les stratégies d'utilisateurs invités et les autorisations, déterminer quels utilisateurs peuvent convier des invités et extraire des rapports sur l'activité des utilisateurs invités.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7db3d42a8d4ae44364ee56f6c7f31ce501a34137
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2019
ms.locfileid: "37567618"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Gérer l'accès invité dans Microsoft Teams
======================================

**Guest** est un type d’utilisateur/de licence dans Microsoft teams inclus dans tous les abonnements Office 365 Business Premium, Office 365 entreprise et Office 365 éducation. Aucune licence Office 365 supplémentaire n'est requise. L'accès invité de Teams est un paramètre de niveau client et est désactivé par défaut. Pour plus d’informations sur l’activation de l’accès invité, voir [activation ou désactivation de l’accès invité à Microsoft teams](set-up-guests.md).

Une fois que le type d’utilisateur/licence **invité** est activé, vous pouvez configurer les paramètres pour les invités via les contrôles décrits dans [gérer les paramètres de Microsoft teams pour votre organisation](enable-features-office-365.md) et [gérer les équipes lors de la transition vers le nouveau Microsoft teams Centre d’administration](manage-teams-skypeforbusiness-admin-center.md).     
    
Les administrateurs informatiques peuvent ajouter des invités au niveau du client, définir et gérer les stratégies et les autorisations des utilisateurs invités, et extraire des rapports sur l’activité des utilisateurs invités. Ces contrôles sont disponibles par le biais du centre d’administration Microsoft Teams. Le contenu et les activités des utilisateurs invités font l'objet de la même protection en matière de conformité et de vérification que le reste d'Office 365.

Les propriétaires d’équipe peuvent inviter de nouveaux invités et ajouter des utilisateurs invités à leurs équipes. Les propriétaires d’équipe peuvent identifier les utilisateurs invités par le biais d' **équipes** > **gérer les équipes**et définir les fonctionnalités liées aux canaux pour les invités via**l’accès invité**des **paramètres** > à l’échelle de l’organisation, y compris permettre aux invités de créer, mettre à jour et Supprimez des canaux, comme le montre l’illustration suivante.

![Paramètres des autorisations invité dans teams](media/manage-guest-access-image1.png)
  
Vous pouvez utiliser le portail Azure Active Directory (Azure AD) pour gérer les invités et leur accès aux ressources d’Office 365 et de teams. L’accès invité teams utilise les fonctionnalités de collaboration d’Azure AD Business-to-Business (B2B) comme infrastructure sous-jacente pour le stockage des informations de principes de sécurité, tels que les propriétés d’identité, l’appartenance et les paramètres d’authentification multifacteur. Pour en savoir plus sur Azure AD B2B, reportez-vous à la rubrique [qu’est-ce qu’Azure ad B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=853011) et [FAQ sur Azure Active Directory B2B](https://go.microsoft.com/fwlink/p/?linkid=853020).

> [!NOTE]
> Microsoft teams respecte toujours les paramètres externes Azure AD pour autoriser ou empêcher les ajouts d’utilisateurs invités au client. Pour plus d’informations, voir [autoriser l’accès invité dans Microsoft teams](Teams-dependencies.md).
  
## <a name="guest-access-vs-external-access-federation"></a>Accès invité et accès externe (fédération)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="review-guest-access-periodically"></a>Réviser l’accès invité périodiquement

Dans Teams, vous pouvez ajouter 5 invités à chaque utilisateur sous licence. En raison de cette limitation, ou si vous souhaitez que votre client reste à jour, vous devez examiner régulièrement l’accès invité pour identifier les utilisateurs qui ont accès sans avoir besoin d’y accéder. Vous pouvez utiliser Azure AD pour créer une révision d’accès pour les membres du groupe ou les utilisateurs assignés à une application. La création d’avis périodiques peut vous permettre de gagner du temps. Si vous avez besoin de vérifier régulièrement les utilisateurs qui ont accès à une application ou qui sont membres d’un groupe, vous pouvez définir la fréquence de ces avis. 

Vous pouvez effectuer une révision par accès invité vous-même, demander aux invités de passer en revue leur appartenance ou demander à un propriétaire d’application ou à un concepteur de décision d’entreprise de procéder à la révision. Le portail Azure vous permet d’effectuer des révisions de l’accès invité. Pour plus d’informations, voir [gérer l’accès invité avec les avis sur Azure ad Access](https://docs.microsoft.com/en-us/azure/active-directory/governance/manage-guest-access-with-access-reviews).

###  <a name="prerequisites"></a>Conditions requises

Les avis sur l’accès sont disponibles avec l’édition Premium d’Azure AD, qui est incluse dans Microsoft entreprise Mobility + Security, E5. Pour plus d’informations, reportez-vous à la rubrique [éditions d’Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis). Chaque utilisateur qui interagit avec cette fonctionnalité en créant un avis, en remplissant un avis ou en confirmant son accès, doit disposer d’une licence.

Teams ne limite pas le nombre d’invités que vous pouvez ajouter. Toutefois, le nombre total d’invités qui peuvent être ajoutés à votre client est basé sur ce que votre licence AAD autorise. Pour plus d’informations, reportez-vous à la rubrique [licences de collaboration Azure ad B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).

## <a name="guest-access-latencies"></a>Latences d’accès invité

Les paramètres d’invité sont définis dans Azure AD. Il faut environ 2 à 24 heures pour que les modifications prennent effet dans votre organisation Office 365. Si un utilisateur voit le message « Contactez votre administrateur » lorsqu'il essaye d'ajouter un invité à son équipe, il est probable que la fonctionnalité d'invité ne soit pas activée ou que les paramètres ne sont pas encore actifs.

## <a name="more-information"></a>Plus d’informations

Pour plus d’informations sur l’utilisation de PowerShell pour gérer l’accès invité, voir [Utiliser PowerShell pour contrôler l’accès invité à une équipe](guest-access-powershell.md).



---
title: Gérer l'accès invité dans Microsoft Teams
author: LolaJacobsen
ms.author: rramesan
manager: serdars
ms.date: 11/13/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: rramesan
search.appverid: MET150
description: Les administrateurs informatiques peuvent ajouter des invités au niveau du client, définir et gérer les stratégies d'utilisateurs invités et les autorisations, déterminer quels utilisateurs peuvent convier des invités et extraire des rapports sur l'activité des utilisateurs invités.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 143170c6a7a174d35300b73693f0a828336b7d32
ms.sourcegitcommit: 5d8b5dee1dea84494aea92bbce568dea10752af9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/14/2018
ms.locfileid: "26510567"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Gérer l'accès invité dans Microsoft Teams
======================================

**Invité** est un type de licence d’utilisateur dans Microsoft Teams qui est inclus avec tous les abonnements Office 365 entreprise Premium, Office 365 pour entreprises et Office 365 éducation. Aucune licence Office 365 supplémentaire n'est requise. L'accès invité de Teams est un paramètre de niveau client et est désactivé par défaut. Pour plus d’informations sur la façon d’activer l’accès invité, voir [Activer ou désactiver l’accès invité aux équipes de Microsoft](set-up-guests.md).

Une fois que le type de licence d’utilisateur **invité** est activé, vous pouvez configurer les paramètres pour les invités via les contrôles décrites dans [les fonctionnalités de gérer les équipes Microsoft dans votre organisation Office 365](enable-features-office-365.md) et [gérer des équipes pendant la transition vers le nouveau Microsoft Les équipes et Skype pour le centre d’administration de Business](manage-teams-skypeforbusiness-admin-center.md).     
    
Les administrateurs informatiques peuvent ajouter des invités au niveau du client, définir et gérer les stratégies d'utilisateurs invités et les autorisations, déterminer quels utilisateurs peuvent convier des invités et extraire des rapports sur l'activité des utilisateurs invités. Ces contrôles sont disponibles via le Centre d'administration d'Office 365. Le contenu et les activités des utilisateurs invités font l'objet de la même protection en matière de conformité et de vérification que le reste d'Office 365.

Propriétaires de l’équipe peuvent inviter de nouveaux invités et ajoutez utilisateurs invité existant à leurs équipes. En outre, les propriétaires de l’équipe pouvant définir fonctionnalités canal pour les visiteurs par le biais de **Gérer les équipes** > **autorisations Invité**, y compris autorisant les invités à créer, mettre à jour et supprimer des chaînes, comme illustré dans la capture d’écran suivante :

![Paramètres d’autorisation invité dans les équipes.](media/view-guests-guest-permissions.png)
  

Vous pouvez également utiliser le portail Azure Active Directory pour gérer les invités et leur accès aux ressources Office 365 et Teams. L'accès invité Teams utilise les fonctionnalités de collaboration entre entreprises (B2B) d'Azure Active Directory comme infrastructure sous-jacente pour stocker les informations relatives aux principes de sécurité telles que les propriétés d'identité, l'appartenance à un groupe et les paramètres d'authentification multifacteur. Pour en savoir plus sur Azure Active Directory B2B, reportez-vous aux rubriques [Qu'est-ce que Azure AD B2B Collaboration ?](https://go.microsoft.com/fwlink/p/?linkid=853011) et [Forums aux questions sur Azure Active Directory B2B Collaboration](https://go.microsoft.com/fwlink/p/?linkid=853020).
> [!NOTE]
> Microsoft Teams respecte toujours les paramètres externes Azure Active Directory pour autoriser ou empêcher les ajouts d’utilisateur invité au client. Pour plus d’informations, voir [Autoriser l’accès invité dans les équipes Microsoft](Teams-dependencies.md).
  
## <a name="guest-access-latencies"></a>Latences d’accès invité

Les paramètres d'invité sont définis dans Azure Active Directory. Il faut environ 2 à 24 heures pour que les modifications prennent effet dans votre organisation Office 365. Si un utilisateur voit le message « Contactez votre administrateur » lorsqu’ils essaient d’ajouter un invité à leur équipe, il est probable que la fonctionnalité invité n’a pas été activée ou que les paramètres ne sont pas encore efficaces.
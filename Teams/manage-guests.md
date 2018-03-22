---
title: Gérer l'accès invité dans Microsoft Teams
author: LolaJacobsen
ms.author: rramesan
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: Les administrateurs informatiques peuvent ajouter des invités au niveau du client, définir et gérer les stratégies d'utilisateurs invités et les autorisations, déterminer quels utilisateurs peuvent convier des invités et extraire des rapports sur l'activité des utilisateurs invités.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 02faf85d91657c487c02503b69b08078b81c88de
ms.sourcegitcommit: 70fc5217f588e10ab0edb400f329ea597efaab52
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2018
---
<a name="manage-guest-access-in-microsoft-teams"></a>Gérer l'accès invité dans Microsoft Teams
======================================

**Invité** est un type de licence d’utilisateur dans Microsoft Teams qui est inclus avec tous les abonnements Office 365 Business Premium et Office 365 formation Office 365 Enterprise. Aucune licence Office 365 supplémentaire n'est requise. L'accès invité de Teams est un paramètre de niveau client et est désactivé par défaut. Pour plus d’informations sur la façon d’activer l’accès invité, voir [Activer ou désactiver l’accès invité pour les équipes de Microsoft](set-up-guests.md).

Une fois le type de licence d’utilisateur **invité** est activé, vous pouvez configurer des paramètres pour les visiteurs via les contrôles décrits dans [des fonctionnalités de gestion des équipes de Microsoft dans votre organisation d’Office 365](enable-features-office-365.md#settings-by-userlicense-type).     
    
Les administrateurs informatiques peuvent ajouter des invités au niveau du client, définir et gérer les stratégies d'utilisateurs invités et les autorisations, déterminer quels utilisateurs peuvent convier des invités et extraire des rapports sur l'activité des utilisateurs invités. Ces contrôles sont disponibles via le Centre d'administration d'Office 365. Le contenu et les activités des utilisateurs invités font l'objet de la même protection en matière de conformité et de vérification que le reste d'Office 365.

Propriétaires d’équipe peuvent inviter de nouveaux invités et ajoutez des utilisateurs invités existant à leurs équipes. En outre, les propriétaires d’équipe peuvent définir liés à la couche de fonctionnalités pour les invités par **les équipes de gestion** > des**autorisations Invité**, notamment autoriser les invités à créer, mettre à jour et supprimer des canaux, comme le montre la capture d’écran suivante :

![Paramètres des autorisations invité dans des équipes.](media/view-guests-guest-permissions.png)
  

Vous pouvez également utiliser le portail Azure Active Directory pour gérer les invités et leur accès aux ressources Office 365 et Teams. L'accès invité Teams utilise les fonctionnalités de collaboration entre entreprises (B2B) d'Azure Active Directory comme infrastructure sous-jacente pour stocker les informations relatives aux principes de sécurité telles que les propriétés d'identité, l'appartenance à un groupe et les paramètres d'authentification multifacteur. Pour en savoir plus sur Azure Active Directory B2B, reportez-vous aux rubriques [Qu'est-ce que Azure AD B2B Collaboration ?](https://go.microsoft.com/fwlink/p/?linkid=853011) et [Forums aux questions sur Azure Active Directory B2B Collaboration](https://go.microsoft.com/fwlink/p/?linkid=853020).
> [!NOTE]
> Teams Microsoft respecte toujours les paramètres externe Azure Active Directory pour autoriser ou empêcher l’ajout de l’utilisateur invité au locataire. Pour plus d’informations, reportez-vous à la section [Autoriser l’accès invité dans des équipes de Microsoft](Teams-dependencies.md).
  

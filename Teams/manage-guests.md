---
title: Gérer l'accès invité dans Microsoft Teams
author: LolaJacobsen
ms.author: rramesan
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: rramesan
search.appverid: MET150
description: Les administrateurs informatiques peuvent ajouter des invités au niveau du client, définir et gérer les stratégies d'utilisateurs invités et les autorisations, déterminer quels utilisateurs peuvent convier des invités et extraire des rapports sur l'activité des utilisateurs invités.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 091215e37af012c2e2203b451e3df4dd9cf6480f
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016724"
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
> Microsoft Teams respecte toujours les paramètres externes Azure Active Directory pour autoriser ou empêcher l’ajout de l’utilisateur invité pour le client. Pour plus d’informations, voir [Autoriser l’accès invité dans les équipes Microsoft](Teams-dependencies.md).
  

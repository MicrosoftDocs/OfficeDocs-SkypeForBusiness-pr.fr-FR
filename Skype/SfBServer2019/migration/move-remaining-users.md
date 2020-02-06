---
title: Déplacer les utilisateurs restants
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Vous pouvez déplacer des utilisateurs vers le nouveau déploiement de Skype entreprise Server 2019 à l’aide du panneau de configuration Skype entreprise Server ou de Skype entreprise Server Management Shell. Vous devez respecter certaines exigences pour garantir une transition fluide vers Skype entreprise Server 2019. Pour plus d’informations sur les conditions préalables à l’exécution des procédures décrites dans cette rubrique, voir Configurer des clients pour la migration. Pour plus d’informations sur le déplacement des utilisateurs, voir phase 4 : déplacer les utilisateurs de test vers le pool de pilotes.'
ms.openlocfilehash: ac384e9f9e4aaaa534f5b646f1d847485dbb4c23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813262"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>Déplacer les utilisateurs restants vers Skype entreprise Server 2019

Vous pouvez déplacer des utilisateurs vers le nouveau déploiement de Skype entreprise Server 2019 à l’aide du panneau de configuration Skype entreprise Server ou de Skype entreprise Server Management Shell. Vous devez respecter certaines exigences pour garantir une transition fluide vers Skype entreprise Server 2019. Pour plus d’informations sur les conditions préalables à l’exécution des procédures décrites dans cette rubrique, voir [configurer des clients pour la migration](configure-clients-for-migration.md). Pour plus d’informations sur le déplacement des utilisateurs, voir [phase 4 : déplacer les utilisateurs de test vers le pool de pilotes](phase-4-move-test-users-to-the-pilot-pool.md).
  
> [!IMPORTANT]
> Vous ne pouvez pas utiliser le composant logiciel enfichable utilisateurs et ordinateurs Active Directory ou les outils d’administration hérités pour déplacer des utilisateurs de votre environnement hérité vers Skype entreprise Server 2019. 
  
Lorsque vous déplacez un utilisateur vers un pool Skype entreprise Server 2019, les données de l’utilisateur sont déplacées vers la base de données principale associée au nouveau pool. 
  
> [!IMPORTANT]
> Cela inclut les réunions actives créées par l’ancien utilisateur. Par exemple, si un utilisateur hérité a configuré une conférence **ma réunion** , celle-ci sera toujours disponible dans le nouveau pool Skype entreprise Server 2019 après que l’utilisateur a été déplacé. Les détails permettant d’accéder à cette réunion seront toujours les mêmes **URL et ID de conférence**. La seule différence réside dans le fait que la Conférence est désormais hébergée dans le pool 2019 de Skype entreprise Server et non dans le pool hérité. 
  
> [!NOTE]
> L’hébergement d’utilisateurs sur Skype entreprise Server 2019 ne nécessite pas le déploiement simultané de clients mis à niveau. Les nouvelles fonctionnalités ne seront accessibles qu’aux utilisateurs qui ont procédé à la mise à niveau vers le nouveau logiciel client. 
  
### <a name="post-migration-task"></a>Tâche après migration

1. Après le déplacement des utilisateurs, vérifiez la stratégie de conférence qui leur est affectée. 
    
2. Pour vous assurer que les réunions organisées par les utilisateurs hébergés sur Skype entreprise Server 2019 fonctionnent en toute transparence avec les utilisateurs fédérés qui sont hébergés sur une installation héritée, la stratégie de conférence affectée aux utilisateurs migrés devrait permettre aux participants anonymes.
    
3. Les stratégies de conférence autorisant les participants anonymes ont **autorisé les participants à inviter les utilisateurs anonymes** sélectionnés dans skype entreprise 2019 Server AllowAnonymousParticipantsInMeetings panneau de configuration et ont configuré **** sur **true** dans la sortie de l’applet de commande **Get-CsConferencingPolicy** dans Skype entreprise Server Management Shell. 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    


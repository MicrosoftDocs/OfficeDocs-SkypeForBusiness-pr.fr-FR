---
title: Déplacer les utilisateurs restants
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Vous pouvez déplacer des utilisateurs vers le nouveau Skype pour Business Server 2019 déploiement à l’aide de deux Skype pour le panneau de configuration serveur Business ou Skype pour Business Server Management Shell. Vous devez satisfaire des exigences d’assurer une transition en douceur vers Skype à Business Server 2019. Pour plus d’informations sur les conditions préalables pour les procédures de cette rubrique, consultez Configurer les clients pour la migration. Pour obtenir la procédure détaillée sur le déplacement d’utilisateurs, voir Phase 4 : test de déplacer les utilisateurs vers le pool pilote.'
ms.openlocfilehash: 9f984b7fac919decce521c6dafc587a4ac86de50
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878322"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>Déplacer les utilisateurs restants vers Skype pour Business Server 2019

Vous pouvez déplacer des utilisateurs vers le nouveau Skype pour Business Server 2019 déploiement à l’aide de deux Skype pour le panneau de configuration serveur Business ou Skype pour Business Server Management Shell. Vous devez satisfaire des exigences d’assurer une transition en douceur vers Skype à Business Server 2019. Pour plus d’informations sur les conditions préalables pour les procédures de cette rubrique, consultez [configurer les clients pour la migration](configure-clients-for-migration.md). Pour obtenir la procédure détaillée sur le déplacement d’utilisateurs, voir [Phase 4 : test de déplacer les utilisateurs vers le pool pilote](phase-4-move-test-users-to-the-pilot-pool.md).
  
> [!IMPORTANT]
> Vous ne pouvez pas utiliser le composant logiciel enfichable Utilisateurs et ordinateurs ou les outils d’administration hérités pour déplacer les utilisateurs de votre environnement hérité vers Skype pour Business Server 2019. 
  
Lorsque vous déplacez un utilisateur vers un Skype pour Business Server 2019 pool, les données de l’utilisateur sont déplacées vers la base de données principale associée au nouveau pool. 
  
> [!IMPORTANT]
> Cela inclut les réunions actives créées par l’utilisateur hérité. Par exemple, si un utilisateur hérité a configuré une conférence **Ma réunion** , cette conférence sera toujours disponible dans la nouvelle Skype pour Business Server 2019 pool après que l’utilisateur a été déplacé. Les détails pour accéder à cette réunion sera toujours le même **ID de conférence et les URL de la conférence**. La seule différence est que la conférence est maintenant hébergée dans le Skype pour le pool d’entreprise Server 2019 et non dans le pool hérité. 
  
> [!NOTE]
> Simultané des utilisateurs sur Skype pour Business Server 2019 ne nécessite pas de déployer des clients mis à niveau en même temps. Nouvelle fonctionnalité sera disponible pour les utilisateurs uniquement lorsqu’ils ont mis à niveau vers le nouveau logiciel client. 
  
### <a name="post-migration-task"></a>Tâche post-migration

1. Une fois que vous déplacez des utilisateurs, vérifiez la stratégie de conférence qui leur est attribuée. 
    
2. Pour vous assurer que les réunions organisées par les utilisateurs hébergement sur Skype pour Business Server 2019 travailler en toute transparence avec les utilisateurs fédérés qui sont hébergés sur installation héritée, la stratégie de conférence assignée aux utilisateurs migrés doit autoriser des participants anonymes.
    
3. Stratégies de conférence qui autorisent les participants anonymes ont **Autoriser les participants à inviter des utilisateurs anonymes** sélectionné dans Skype pour Business Server 2019 le panneau de configuration et **AllowAnonymousParticipantsInMeetings** définissent sur **True** dans le sortie de l’applet de commande **Get-CsConferencingPolicy** dans la Skype pour Business Server Management Shell. 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    


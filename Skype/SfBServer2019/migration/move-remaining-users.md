---
title: Déplacer les utilisateurs restants
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 'Vous pouvez déplacer des utilisateurs vers le nouveau déploiement Skype Entreprise Server 2019 à l’aide du Panneau de Skype Entreprise Server ou de Skype Entreprise Server Management Shell. Vous devez répondre à certaines exigences pour garantir une transition en douceur vers Skype Entreprise Server 2019. Pour plus d’informations sur les conditions préalables à la réalisation des procédures de cette rubrique, voir Configure clients for migration. Pour obtenir la procédure détaillée de déplacement des utilisateurs, voir Phase 4 : Déplacer des utilisateurs de test vers le pool pilote.'
ms.openlocfilehash: 60742068bc684470d181593e94615da2a8d79ff6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623106"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>Déplacer les utilisateurs restants vers Skype Entreprise Server 2019

Vous pouvez déplacer des utilisateurs vers le nouveau déploiement Skype Entreprise Server 2019 à l’aide du Panneau de Skype Entreprise Server ou de Skype Entreprise Server Management Shell. Vous devez répondre à certaines exigences pour garantir une transition en douceur vers Skype Entreprise Server 2019. Pour plus d’informations sur les conditions préalables à la réalisation des procédures de cette rubrique, voir [Configurer les clients pour la migration.](configure-clients-for-migration.md) Pour obtenir la procédure détaillée de déplacement des utilisateurs, voir Phase 4 : Déplacer les utilisateurs [de test vers le pool pilote.](phase-4-move-test-users-to-the-pilot-pool.md)
  
> [!IMPORTANT]
> Vous ne pouvez pas utiliser le logiciel en ligne Utilisateurs et ordinateurs Active Directory ou les outils d’administration hérités pour déplacer des utilisateurs de votre environnement hérité vers Skype Entreprise Server 2019. 
  
Lorsque vous déplacez un utilisateur vers un pool Skype Entreprise Server 2019, les données de l’utilisateur sont déplacées vers la base de données principale associée au nouveau pool. 
  
> [!IMPORTANT]
> Cela comprend des réunions actives créées par l’utilisateur hérité. Par exemple, si un utilisateur hérité **a** configuré une conférence de réunion, cette conférence sera toujours disponible dans le nouveau pool Skype Entreprise Server 2019 une fois que l’utilisateur a été déplacé. Les détails permettant d’accéder à cette réunion seront encore les mêmes **URL de conférence et ID de conférence**. La seule différence est que la conférence est désormais hébergée dans le pool Skype Entreprise Server 2019, et non dans le pool hérité. 
  
> [!NOTE]
> L’Skype Entreprise Server utilisateurs sur Skype Entreprise Server 2019 ne nécessite pas de déployer des clients mis à niveau en même temps. Les nouvelles fonctionnalités sont disponibles pour les utilisateurs uniquement lorsqu’ils ont effectué la mise à niveau vers le nouveau logiciel client. 
  
### <a name="post-migration-task"></a>Tâche post-migration

1. Une fois que vous avez déplacé des utilisateurs, vérifiez la stratégie de conférence qui leur est attribuée. 
    
2. Pour garantir que les réunions organisées par des utilisateurs sur Skype Entreprise Server 2019 fonctionnent en toute transparence avec les utilisateurs fédérés qui sont installés sur l’installation héritée, la stratégie de conférence attribuée aux utilisateurs migrés doit autoriser les participants anonymes.
    
3. Les stratégies de conférence qui autorisent les **participants** anonymes ont pour effet d’autoriser les participants à inviter des utilisateurs anonymes sélectionnés dans le Panneau de Skype Entreprise Server 2019 et **allowAnonymousParticipantsInMeetings** a la valeur **True** dans la sortie de l’cmdlet **Get-CsConferencingPolicy** dans l’environnement de ligne de commande Skype Entreprise Server Management Shell. 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    


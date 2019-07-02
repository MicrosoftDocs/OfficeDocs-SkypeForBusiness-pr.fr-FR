---
title: Surveillance, lancement et arrête des services de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Résumé: Découvrez comment démarrer, arrêter et surveiller les services de chat permanent dans Skype entreprise Server 2015.'
ms.openlocfilehash: 9d2edf0e05a6efcd6e9354696cceade8265abbac
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418690"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>Surveillance, lancement et arrête des services de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé:** Découvrez comment démarrer, arrêter et surveiller les services de chat permanent dans Skype entreprise Server 2015.
  
Les services de chat permanent et de conformité des conversations permanent font partie de la topologie de Skype entreprise Server et peuvent donc être surveillés, arrêtés et démarrés en utilisant les applets de commande suivantes:
  
|||
|:-----|:-----|
|get-CsWindowsService  <br/> |Renvoie des informations détaillées sur les composants de Skype entreprise Server 2015 qui s’exécutent en tant que services Windows.  <br/> |
|start-CsWindowsService  <br/> |Démarre le service.  <br/> |
|stop-CsWindowsService  <br/> |Arrête le service.  <br/> |
   
> [!NOTE]
> La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique mise [en route de Microsoft teams](/microsoftteams/upgrade-start-here). Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015. 

Pour plus d’informations sur la manière d’utiliser les applets de commande, voir [Skype for Business Server 2015 Management Shell](../management-shell.md).
  


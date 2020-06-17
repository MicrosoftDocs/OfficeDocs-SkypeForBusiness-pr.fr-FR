---
title: Supprimer un serveur frontal d’un pool
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Le serveur frontal ne peut pas exister en tant qu’ordinateur autonome. Il doit être défini en tant que pool frontal, même s’il n’y a qu’un seul ordinateur dans le pool.
ms.openlocfilehash: 7675ba119fa2937d765d5f4e497fca0a040b3b62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752316"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>Supprimer un serveur frontal d’un pool

Le serveur frontal ne peut pas exister en tant qu’ordinateur autonome. Il doit être défini en tant que pool frontal, même s’il n’y a qu’un seul ordinateur dans le pool.
  
Cette rubrique vous guide tout au long du processus de suppression d’un serveur frontal individuel d’un pool frontal existant. Si le serveur frontal est le dernier serveur du pool ou si vous supprimez complètement le pool, reportez-vous à la rubrique [supprimer un pool frontal ou un serveur Standard Edition](remove-front-end-pool-or-standard-edition-server.md). Il n’est pas nécessaire de supprimer les serveurs frontaux individuels avant de supprimer le pool frontal. Lorsque vous supprimez le pool, vous supprimez tous les serveurs frontaux.
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>Pour supprimer un serveur frontal d’un pool

1. Sur le serveur frontal Skype entreprise Server 2019, ouvrez le générateur de topologie.
    
2. Naviguez jusqu’au nœud d’installation hérité.
    
3. Développez **Pools frontaux Enterprise Edition**, développez le pool frontal avec le serveur frontal que vous souhaitez supprimer, cliquez avec le bouton droit sur le serveur frontal que vous souhaitez supprimer, puis cliquez sur **supprimer**.
    


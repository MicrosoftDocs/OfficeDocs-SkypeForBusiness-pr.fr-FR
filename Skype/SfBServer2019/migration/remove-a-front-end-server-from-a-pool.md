---
title: Supprimer un serveur frontal d’un pool
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Le serveur frontal ne peut exister qu’un ordinateur autonome. Il doit être défini comme un pool frontal, même si le pool ne contient qu’un seul ordinateur.
ms.openlocfilehash: a9f0adc991355b6f79b20365795ffaf92fa230e2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028942"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>Supprimer un serveur frontal d’un pool

Le serveur frontal ne peut exister qu’un ordinateur autonome. Il doit être défini comme un pool frontal, même si le pool ne contient qu’un seul ordinateur.
  
Cette rubrique vous guide tout au long du processus de suppression d’un serveur frontal individuels à partir d’un pool frontal existant. Si le serveur frontal est le dernier serveur du pool ou si vous supprimez entièrement le pool, voir [Supprimer le pool frontal ou Standard Edition server](remove-front-end-pool-or-standard-edition-server.md). Il n’est pas nécessaire de supprimer les serveurs frontaux individuels avant de supprimer le pool frontal. Lorsque vous supprimez le pool, vous supprimez chaque serveur frontal.
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>Pour supprimer un serveur frontal d’un pool

1. Sur Skype pour Business Server 2019 serveur frontal, ouvrez le Générateur de topologie.
    
2. Accédez au nœud installer hérité.
    
3. Développez **pools frontaux Enterprise Edition**, développez le pool frontal avec le serveur frontal que vous souhaitez supprimer, cliquez sur le serveur frontal que vous souhaitez supprimer, puis cliquez sur **Supprimer**.
    


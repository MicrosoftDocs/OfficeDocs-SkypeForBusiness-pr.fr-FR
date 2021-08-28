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
ms.localizationpriority: medium
description: Le serveur frontal ne peut pas exister en tant qu’ordinateur autonome. Il doit être défini comme un pool frontal, même s’il n’y a qu’un seul ordinateur dans le pool.
ms.openlocfilehash: b52954421034d83191e479e59d1efeeda8972868
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594998"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>Supprimer un serveur frontal d’un pool

Le serveur frontal ne peut pas exister en tant qu’ordinateur autonome. Il doit être défini comme un pool frontal, même s’il n’y a qu’un seul ordinateur dans le pool.
  
Cette rubrique vous guide tout au long du processus de suppression d’un serveur frontal individuel d’un pool frontal existant. Si le serveur frontal est le dernier serveur du pool ou si vous supprimez complètement le pool, voir Supprimer le pool frontal ou [Édition Standard serveur.](remove-front-end-pool-or-standard-edition-server.md) Il n’est pas nécessaire de supprimer les serveurs frontux individuels avant de supprimer le pool frontal. Lorsque vous supprimez le pool, vous supprimez chaque serveur frontal.
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>Pour supprimer un serveur frontal d’un pool

1. Sur le Skype Entreprise Server frontal 2019, ouvrez le Générateur de topologie.
    
2. Accédez au nœud d’installation hérité.
    
3. Développez **Êdition Entreprise pools** frontux, développez le pool frontal avec le serveur frontal à supprimer, cliquez avec le bouton droit sur le serveur frontal à supprimer, puis cliquez sur **Supprimer.**
    


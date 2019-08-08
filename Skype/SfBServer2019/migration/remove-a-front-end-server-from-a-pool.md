---
title: Supprimer un serveur frontal d’un pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Le serveur frontal ne peut pas exister en tant qu’ordinateur autonome. Elle doit être définie en tant que pool frontal, même s’il n’y a qu’un seul ordinateur dans le pool.
ms.openlocfilehash: 64f0c4134f690005815591bce88b8d058c1bd007
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244294"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>Supprimer un serveur frontal d’un pool

Le serveur frontal ne peut pas exister en tant qu’ordinateur autonome. Elle doit être définie en tant que pool frontal, même s’il n’y a qu’un seul ordinateur dans le pool.
  
Cette rubrique vous guide tout au long du processus de suppression d’un serveur frontal individuel d’un pool frontal existant. Si le serveur frontal est le dernier serveur du pool ou si vous supprimez entièrement le pool, voir supprimer le [pool frontal ou le serveur Standard Edition Server](remove-front-end-pool-or-standard-edition-server.md). Il n’est pas nécessaire de supprimer les serveurs front-end individuels avant de supprimer le pool frontal. Lorsque vous supprimez le pool, vous supprimez chaque serveur frontal.
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>Pour supprimer un serveur frontal d’un pool

1. Sur le serveur frontal Skype entreprise Server 2019, ouvrez le générateur de topologie.
    
2. Accédez au nœud d’installation hérité.
    
3. Développez **Pools front-end Enterprise Edition**, développez le pool frontal du serveur frontal que vous voulez supprimer, cliquez avec le bouton droit sur le serveur frontal que vous voulez supprimer, puis cliquez sur **supprimer**.
    


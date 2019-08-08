---
title: Supprimer un pool frontal ou un serveur Standard Edition
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cette rubrique vous guide dans le processus de suppression d’un pool frontal ou d’un serveur frontal Standard Edition. Lorsque vous supprimez un pool frontal, vous supprimez chaque serveur frontal qui appartient au pool dans le cadre du processus de suppression du pool. Lorsque vous supprimez un serveur frontal Standard Edition, vous devez supprimer la définition du SQL Store du générateur de topologie.
ms.openlocfilehash: 57679fb248c9281b79c12be98b7fd5246c9afd38
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244266"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Supprimer un pool frontal ou un serveur Standard Edition

Cet article vous guide tout au long du processus de suppression d’un pool frontal ou d’un serveur frontal Standard Edition. Lorsque vous supprimez un pool frontal, vous supprimez chaque serveur frontal qui appartient au pool dans le cadre du processus de suppression du pool. Lorsque vous supprimez un serveur frontal Standard Edition, vous devez supprimer la définition du SQL Store du générateur de topologie.
  
## <a name="to-remove-a-front-end-server-pool"></a>Pour supprimer un pool de serveurs frontal

1. Ouvrez le générateur de topologie.
    
2. Accédez au nœud hérité.
    
3. Développez **Pools front end Enterprise Edition**, développez le pool frontal, cliquez avec le bouton droit sur le pool frontal que vous voulez supprimer, puis cliquez sur **supprimer**.
    
4. Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement hérité selon vos besoins. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Pour supprimer un serveur frontal Standard Edition

1. Ouvrez le générateur de topologie.
    
2. Accédez au nœud installations héritées.
    
3. Développez **serveurs front-end standard**, cliquez avec le bouton droit sur le serveur frontal que vous voulez supprimer, puis cliquez sur **supprimer**.
    
4. Développez **magasins SQL**, cliquez avec le bouton droit sur la base de données SQL Server associée au serveur frontal Standard Edition, puis cliquez sur **supprimer**.
    
    > [!IMPORTANT]
    > Vous devez supprimer la définition des bases de données SQL Server colocalisées du serveur frontal Standard Edition. 
  
5. Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement selon vos besoins. 
    


---
title: Supprimer un pool frontal ou un serveur Standard Edition
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cette rubrique vous guide tout au long du processus de suppression d’un pool frontal ou un serveur Standard Edition serveur frontal. Lorsque vous supprimez un pool frontal, vous supprimez chaque serveur frontal qui appartient au pool dans le cadre du processus de suppression de pool. Lorsque vous supprimez un serveur Standard Edition serveur frontal, vous devez supprimer la définition d’un magasin SQL du Générateur de topologie.
ms.openlocfilehash: 394edcd6f5c89478ed98abebe0be29720d009107
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872716"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Supprimer un pool frontal ou un serveur Standard Edition

Cet article vous guide tout au long du processus de suppression d’un pool frontal ou un serveur Standard Edition serveur frontal. Lorsque vous supprimez un pool frontal, vous supprimez chaque serveur frontal qui appartient au pool dans le cadre du processus de suppression de pool. Lorsque vous supprimez un serveur Standard Edition serveur frontal, vous devez supprimer la définition d’un magasin SQL du Générateur de topologie.
  
## <a name="to-remove-a-front-end-server-pool"></a>Pour supprimer un pool de serveurs frontaux

1. Ouvrez le Générateur de topologie.
    
2. Naviguez jusqu’au nœud hérité.
    
3. Développez **pools frontaux Enterprise Edition**, développez le pool frontal, cliquez sur le pool frontal que vous souhaitez supprimer, puis cliquez sur **Supprimer**.
    
4. Publiez la topologie, vérifier l’état de réplication, puis exécutez l’Assistant de déploiement hérité selon vos besoins. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Pour supprimer un serveur frontal Standard Edition

1. Ouvrez le Générateur de topologie.
    
2. Naviguez jusqu’au nœud de l’installation héritée.
    
3. Développez **serveurs frontaux Standard Edition**, cliquez sur le serveur frontal que vous souhaitez supprimer, puis cliquez sur **Supprimer**.
    
4. Développez **SQL stocke**, avec le bouton droit de la base de données SQL Server qui est associé avec le serveur Standard Edition serveur frontal, puis cliquez sur **Supprimer**.
    
    > [!IMPORTANT]
    > Vous devez supprimer la définition des bases de données SQL Server COLOCALISÉES de Standard Edition serveur frontal. 
  
5. Publiez la topologie, vérifier l’état de réplication, puis exécutez l’Assistant Déploiement selon vos besoins. 
    


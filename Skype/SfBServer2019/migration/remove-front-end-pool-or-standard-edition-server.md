---
title: Supprimer un pool frontal ou un serveur Standard Edition
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
description: Cette rubrique vous guide tout au long du processus de suppression d’un pool frontal ou d’un serveur frontal Standard Edition. Lorsque vous supprimez un pool frontal, vous supprimez chaque serveur frontal qui appartient au pool dans le cadre du processus de suppression du pool. Lorsque vous supprimez un serveur frontal Standard Edition, vous devez supprimer la définition SQL Store du Générateur de topologies.
ms.openlocfilehash: 305a353ced45fe7e21ba479c0c3571df236aa09b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752276"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Supprimer un pool frontal ou un serveur Standard Edition

Cet article vous guide tout au long du processus de suppression d’un pool frontal ou d’un serveur frontal Standard Edition. Lorsque vous supprimez un pool frontal, vous supprimez chaque serveur frontal qui appartient au pool dans le cadre du processus de suppression du pool. Lorsque vous supprimez un serveur frontal Standard Edition, vous devez supprimer la définition SQL Store du Générateur de topologies.
  
## <a name="to-remove-a-front-end-server-pool"></a>Pour supprimer un pool de serveurs frontaux

1. Ouvrez le Générateur de topologie.
    
2. Accédez au nœud hérité.
    
3. Développez les pools frontux **Enterprise Edition,** développez le pool frontal, cliquez avec le bouton droit sur le pool frontal à supprimer, puis cliquez sur **Supprimer.**
    
4. Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement hérité si nécessaire. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Pour supprimer un serveur frontal Standard Edition

1. Ouvrez le Générateur de topologie.
    
2. Accédez au nœud d’installation hérité.
    
3. Développez **les serveurs frontux Standard Edition,** cliquez avec le bouton droit sur le serveur frontal à supprimer, puis cliquez sur **Supprimer.**
    
4. Développez **SQL** magasins, cliquez avec le bouton droit sur la base de données SQL Server qui est associée au serveur frontal Standard Edition, puis cliquez sur **Supprimer.**
    
    > [!IMPORTANT]
    > Vous devez supprimer la définition des bases de données SQL Server de données c colloquées du serveur frontal Standard Edition. 
  
5. Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement si nécessaire. 
    


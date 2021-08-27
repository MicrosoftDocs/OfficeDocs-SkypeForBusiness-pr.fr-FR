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
ms.localizationpriority: medium
description: Cette rubrique vous guide tout au long du processus de suppression d’un pool frontal ou d’Édition Standard serveur frontal. Lorsque vous supprimez un pool frontal, vous supprimez chaque serveur frontal qui appartient au pool dans le cadre du processus de suppression du pool. Lorsque vous supprimez un Édition Standard frontal, vous devez supprimer la définition SQL Store du Générateur de topologies.
ms.openlocfilehash: 04ff2120fcbbe0c914a0a105669083eeb13a8347
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589248"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Supprimer un pool frontal ou un serveur Standard Edition

Cet article vous guide tout au long du processus de suppression d’un pool frontal ou d’Édition Standard serveur frontal. Lorsque vous supprimez un pool frontal, vous supprimez chaque serveur frontal qui appartient au pool dans le cadre du processus de suppression du pool. Lorsque vous supprimez un Édition Standard frontal, vous devez supprimer la définition SQL Store du Générateur de topologies.
  
## <a name="to-remove-a-front-end-server-pool"></a>Pour supprimer un pool de serveurs frontaux

1. Ouvrez le Générateur de topologie.
    
2. Accédez au nœud hérité.
    
3. Développez **Êdition Entreprise pools** frontux, développez le pool frontal, cliquez avec le bouton droit sur le pool frontal à supprimer, puis cliquez sur **Supprimer.**
    
4. Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement hérité si nécessaire. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Pour supprimer un serveur frontal Standard Edition

1. Ouvrez le Générateur de topologie.
    
2. Accédez au nœud d’installation hérité.
    
3. Développez **Édition Standard serveurs frontux,** cliquez avec le bouton droit sur le serveur frontal à supprimer, puis cliquez sur **Supprimer.**
    
4. Développez **SQL** magasins, cliquez avec le bouton droit sur la base de données SQL Server associée au serveur frontal Édition Standard, puis cliquez sur **Supprimer.**
    
    > [!IMPORTANT]
    > Vous devez supprimer la définition des bases de données SQL Server de données c Édition Standard serveur frontal. 
  
5. Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement si nécessaire. 
    


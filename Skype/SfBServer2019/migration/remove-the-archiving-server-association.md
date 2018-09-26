---
title: Supprimer l’association du serveur d’archivage
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Pour supprimer un serveur d’archivage, vous devez modifier ou supprimer la dépendance au pool frontal associé, le serveur frontal, Survivable Branch Appliance et serveur Survivable Branch Server. Vous modifiez les propriétés du pool frontal, serveur frontal et serveur Survivable Branch Server Survivable Branch Appliance pour supprimer la dépendance. Une fois que vous désactivez la dépendance et vous supprimez le serveur dans le Générateur de topologie, vous êtes averti que l’objet de magasin de base de données associée dans le Générateur de topologie est également supprimé.
ms.openlocfilehash: 7438145f5822de8f95e881f114983fdb9351d4b9
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028872"
---
# <a name="remove-the-archiving-server-association"></a>Supprimer l’association du serveur d’archivage

Pour supprimer un serveur d’archivage, vous devez modifier ou supprimer la dépendance associée Front-End pool, serveur frontal, Survivable Branch Appliance, les Survivable Branch Server. Vous modifiez les propriétés du pool frontal, serveur frontal, Survivable Branch Appliance et serveur Survivable Branch Server permet de supprimer la dépendance. Une fois que vous désactivez la dépendance et supprimez le serveur dans le Générateur de topologie, vous êtes averti que l’objet de magasin de base de données associée dans le Générateur de topologie est également supprimé.
  
### <a name="to-remove-the-archiving-server-association"></a>Pour supprimer l’association du serveur d’archivage

1. Sur Skype pour Business Server 2019 serveur frontal, ouvrez le Générateur de topologie.
    
2. Accédez au nœud installer hérité.
    
3. Dans le Générateur de topologie, développez **pools frontaux Enterprise Edition**, **Standard Edition serveurs frontaux**ou **sites de succursale**, selon l’emplacement où le serveur d’archivage est défini.
    
4. Si vous avez un serveur Survivable Branch Server associé, développez **sites de succursale**, développez le nom de site de succursale, puis développez **Survivable Branch Appliances**.
    
    > [!NOTE]
    > **Survivable Branch Appliances** dans l’interface utilisateur s’applique à la fois un serveur Survivable Branch Server et Survivable Branch Appliance. 
  
5. Cliquez sur le pool, le serveur ou le périphérique qui est associé avec le serveur d’archivage, puis cliquez sur **Modifier les propriétés**.
    
6. Dans **Modifier les propriétés**, sous **Général** > **Associations**, désactivez la case à cocher **Associer un serveur d’archivage** , puis cliquez sur **OK**.
    
7. Répétez l’étape précédente pour tout autre pool, serveur ou périphérique associé avec le serveur d’archivage que vous souhaitez supprimer.
    
8. Cliquez sur le serveur d’archivage, puis cliquez sur **Supprimer**.
    
9. **Supprimer les magasins dépendants**, cliquez sur **OK**.
    
10. Publier la topologie, vérifiez le statut de réplication et exécutez le Skype pour l’Assistant de déploiement Business Server selon vos besoins. 
    


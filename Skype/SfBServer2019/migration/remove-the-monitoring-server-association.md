---
title: Supprimer l’association au serveur de surveillance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Pour supprimer le serveur de surveillance, vous devez modifier ou supprimer la dépendance au pool frontal associé, le serveur frontal, Survivable Branch Appliance et serveur Survivable Branch Server. Vous modifiez les propriétés du pool frontal, serveur frontal et serveur Survivable Branch Server Survivable Branch Appliance pour supprimer la dépendance. Une fois que vous désactivez la dépendance et supprimez le serveur dans le Générateur de topologie, vous êtes averti que l’objet de magasin de base de données associée dans le Générateur de topologie est également supprimé.
ms.openlocfilehash: 854e95969d08d14d626bb374073091ae4ae39630
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892701"
---
# <a name="remove-the-monitoring-server-association"></a>Supprimer l’association au serveur de surveillance

Pour supprimer le serveur de surveillance, vous devez modifier ou supprimer la dépendance associée Front-End pool, serveur frontal, Survivable Branch Appliance, les Survivable Branch Server. Vous modifiez les propriétés du pool frontal, serveur frontal, Survivable Branch Appliance et serveur Survivable Branch Server permet de supprimer la dépendance. Une fois que vous désactivez la dépendance et supprimez le serveur dans le Générateur de topologie, vous êtes averti que l’objet de magasin de base de données associée dans le Générateur de topologie est également supprimé.
  
### <a name="to-remove-the-monitoring-server-association"></a>Pour supprimer l’association du serveur de surveillance

1. Sur Skype pour Business Server 2019 serveur frontal, ouvrez le Générateur de topologie.
    
2. Naviguez jusqu’au nœud de l’installation héritée.
    
3. Dans le Générateur de topologie, développez **pools frontaux Enterprise Edition**, **Standard Edition serveurs frontaux**ou **sites de succursale**, selon l’emplacement où le serveur de surveillance est défini.
    
4. Si vous avez un serveur Survivable Branch Server associé, développez **sites de succursale**, développez le nom de site de succursale, puis développez **Survivable Branch Appliances**.
    
    > [!NOTE]
    > **Survivable Branch Appliances** dans l’interface utilisateur s’applique à la fois un serveur Survivable Branch Server et Survivable Branch Appliance. 
  
5. Cliquez sur le pool, le serveur ou le périphérique qui est associé avec le serveur de surveillance, puis cliquez sur **Modifier les propriétés**.
    
6. Dans **Modifier les propriétés**, sous **Général** > **Associations**, désactivez la case à cocher **Associer un serveur de surveillance** , puis cliquez sur **OK**.
    
7. Répétez l’étape précédente pour tout autre pool, serveur ou périphérique associé avec le serveur de surveillance.
    
8. Cliquez sur le serveur de surveillance, puis cliquez sur **Supprimer**. 
    
9. **Supprimer les magasins dépendants**, cliquez sur **OK**.
    
10. Publiez la topologie, vérifiez le statut de réplication et exécuter la Skype pour l’Assistant de déploiement de serveur Business selon vos besoins. 
    


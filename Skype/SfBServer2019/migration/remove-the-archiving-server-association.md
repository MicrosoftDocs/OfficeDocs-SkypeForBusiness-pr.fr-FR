---
title: Supprimer l’association au serveur d’archivage
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
description: Pour supprimer un serveur d’archivage, vous devez modifier ou supprimer la dépendance sur le pool frontal associé, le serveur frontal, le Survivable Branch appliance et le serveur Survivable Branch Server. Vous modifiez les propriétés du pool frontal, du serveur frontal, du Survivable Branch appliance et du serveur Survivable Branch Server pour supprimer la dépendance. Une fois que vous avez effacé la dépendance et supprimé le serveur dans le générateur de topologies, vous êtes informé que l’objet de magasin de bases de données associé dans le générateur de topologies est également supprimé.
ms.openlocfilehash: bba21dadc70f5c9f62fea5073ef5bf815c8b35a1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752136"
---
# <a name="remove-the-archiving-server-association"></a>Supprimer l’association au serveur d’archivage

Pour supprimer un serveur d’archivage, vous devez modifier ou supprimer la dépendance sur le pool frontal associé, le serveur frontal, le Survivable Branch appliance et le serveur Survivable Branch Server. Vous modifiez les propriétés du pool frontal, le serveur frontal, le Survivable Branch appliance et le serveur Survivable Branch Server pour supprimer la dépendance. Une fois que vous avez effacé la dépendance et supprimé le serveur dans le générateur de topologies, vous êtes informé que l’objet de magasin de bases de données associé dans le générateur de topologies est également supprimé.
  
### <a name="to-remove-the-archiving-server-association"></a>Pour supprimer l’association au serveur d’archivage

1. Sur le serveur frontal Skype entreprise Server 2019, ouvrez le générateur de topologie.
    
2. Naviguez jusqu’au nœud d’installation hérité.
    
3. Dans le générateur de topologies, développez **Pools frontaux Enterprise Edition**, **serveurs frontaux Standard Edition**ou **sites de succursale**, en fonction de l’emplacement où est défini le serveur d’archivage.
    
4. Si vous avez un serveur Survivable Branch Server associé, développez **sites de succursale**, développez le nom du site de succursale, puis développez **Survivable Branch Appliances**.
    
    > [!NOTE]
    > **Survivable Branch Appliances** dans l’interface utilisateur s’applique aux serveurs Survivable Branch Server et Survivable Branch appliance. 
  
5. Cliquez avec le bouton droit sur le pool, le serveur ou le périphérique associé au serveur d’archivage, puis cliquez sur **modifier les propriétés**.
    
6. Dans **modifier les propriétés**, **General**sous  >  **associations**générales, désactivez la case à cocher associer un **serveur d’archivage** , puis cliquez sur **OK**.
    
7. Répétez l’étape précédente pour tout autre pool, serveur ou appareil associé au serveur d’archivage que vous souhaitez supprimer.
    
8. Cliquez avec le bouton droit sur le serveur d’archivage, puis cliquez sur **supprimer**.
    
9. Dans **Supprimer les magasins dépendants**, cliquez sur **OK**.
    
10. Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement de Skype entreprise Server selon vos besoins. 
    


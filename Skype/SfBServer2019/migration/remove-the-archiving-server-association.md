---
title: Supprimer l’association au serveur d’archivage
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Pour supprimer un serveur d’archivage, vous devez modifier ou effacer la dépendance sur le pool frontal associé, le serveur frontal, l’unité de branchement Survivable et le serveur de succursales survivant. Vous pouvez modifier les propriétés du pool frontal, du serveur frontal, de l’unité de branchement Survivable et du serveur de succursales survivant pour supprimer la dépendance. Une fois que vous avez effacé les dépendances et que vous avez supprimé le serveur dans le générateur de topologie, vous êtes informé que l’objet du magasin de base de données associé dans le générateur de topologie sera également supprimé.
ms.openlocfilehash: 7b6e35131005866feed04a4e9b68c43558b6c1e1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812972"
---
# <a name="remove-the-archiving-server-association"></a>Supprimer l’association au serveur d’archivage

Pour supprimer un serveur d’archivage, vous devez modifier ou effacer le niveau de dépendance du pool frontal associé, du serveur frontal, de l’unité de branchement Survivable et du serveur de succursales survivant. Vous pouvez modifier les propriétés du pool frontal, du serveur frontal, de l’unité de branchement survivant et du serveur de succursales survivant pour supprimer la dépendance. Dès lors que vous effacez la dépendance et que vous avez supprimé le serveur dans le générateur de topologie, vous êtes informé que l’objet magasin de base de données associé dans le générateur de topologie sera également supprimé.
  
### <a name="to-remove-the-archiving-server-association"></a>Pour supprimer l’Association du serveur d’archivage

1. Sur le serveur frontal Skype entreprise Server 2019, ouvrez le générateur de topologie.
    
2. Accédez au nœud d’installation hérité.
    
3. Dans le générateur de topologie, développez **Pools front end Edition**, **serveurs front end Standard Edition**ou **sites de succursales**, selon l’emplacement de définition du serveur d’archivage.
    
4. Si vous avez un serveur de succursales Survivable associé, développez **sites de succursales**, développez le nom du site de la succursale, puis développez **appareils de branchement survivables**.
    
    > [!NOTE]
    > Les **appareils de branchement survivables** dans l’interface utilisateur s’appliquent à la fois au serveur de succursales survivant et au dispositif de branchement survivant. 
  
5. Cliquez avec le bouton droit sur le pool, le serveur ou l’appareil associé au serveur d’archivage, puis cliquez sur **modifier les propriétés**.
    
6. Dans la boîte de **dialogue Modifier les propriétés**, sous**associations** **générales** > , désactivez la case à cocher **Associate Server** , puis cliquez sur **OK**.
    
7. Répétez l’étape précédente pour tout autre serveur ou pool associé au serveur d’archivage que vous voulez supprimer.
    
8. Cliquez avec le bouton droit sur le serveur d’archivage, puis cliquez sur **supprimer**.
    
9. Sur **Supprimer les magasins dépendants**, cliquez sur **OK**.
    
10. Publiez la topologie, vérifiez l’état de la connexion, puis exécutez l’Assistant Déploiement de Skype entreprise Server selon vos besoins. 
    


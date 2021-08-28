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
ms.localizationpriority: medium
description: Pour supprimer un serveur d’archivage, vous devez modifier ou effacer la dépendance vis-à-vis du pool frontal, du serveur frontal, du Survivable Branch Appliance et du serveur Survivable Branch Server associés. Vous modifiez les propriétés du pool frontal, du serveur frontal, du Survivable Branch Appliance et du serveur Survivable Branch Server pour supprimer la dépendance. Après avoir effacé la dépendance et supprimé le serveur dans le Générateur de topologies, vous êtes informé que l’objet magasin de bases de données associé dans le Générateur de topologies sera également supprimé.
ms.openlocfilehash: 489eeb276b495598ec2f11fc9b4502935beedf30
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617070"
---
# <a name="remove-the-archiving-server-association"></a>Supprimer l’association au serveur d’archivage

Pour supprimer un serveur d’archivage, vous devez modifier ou effacer la dépendance vis-à-vis du pool frontal, du serveur frontal, du Survivable Branch Appliance et du serveur Survivable Branch Server associés. Vous modifiez les propriétés du pool frontal, du serveur frontal, du Survivable Branch Appliance et du serveur Survivable Branch Server pour supprimer la dépendance. Après avoir effacé la dépendance et supprimé le serveur dans le Générateur de topologie, vous êtes informé que l’objet magasin de bases de données associé dans le Générateur de topologie sera également supprimé.
  
### <a name="to-remove-the-archiving-server-association"></a>Pour supprimer l’association au serveur d’archivage

1. Sur le Skype Entreprise Server frontal 2019, ouvrez le Générateur de topologie.
    
2. Accédez au nœud d’installation hérité.
    
3. Dans le Générateur de topologie, développez Êdition Entreprise **pools** frontux, **Édition Standard** serveurs frontux ou **sites** de succursale, en fonction de l’emplacement où le serveur d’archivage est défini.
    
4. Si vous avez un serveur Survivable Branch Server associé, développez sites de **succursale,** développez le nom du site de succursale, puis développez **Survivable Branch Appliances**.
    
    > [!NOTE]
    > **Les Survivable Branch Appliances de** l’interface utilisateur s’appliquent au Serveur Survivable Branch Server et au Survivable Branch Appliance. 
  
5. Cliquez avec le bouton droit sur le pool, le serveur ou l’appareil associé au serveur d’archivage, puis cliquez sur **Modifier les propriétés.**
    
6. Dans **Modifier les propriétés,** sous **Associations**  >  **générales,** cochez la case Associer un serveur d’archivage, puis cliquez sur **OK.** 
    
7. Répétez l’étape précédente pour tout autre pool, serveur ou périphérique associé au serveur d’archivage à supprimer.
    
8. Cliquez avec le bouton droit sur le serveur d’archivage, puis cliquez sur **Supprimer.**
    
9. Dans **Supprimer les magasins dépendants**, cliquez sur **OK**.
    
10. Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Skype Entreprise Server déploiement si nécessaire. 
    


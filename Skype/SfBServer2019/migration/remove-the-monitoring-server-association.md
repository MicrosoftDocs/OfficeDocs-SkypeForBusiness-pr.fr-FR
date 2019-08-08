---
title: Supprimer l’association au serveur de surveillance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Pour supprimer le serveur de surveillance, vous devez modifier ou effacer la dépendance sur le pool frontal associé, le serveur frontal, l’unité de branchement Survivable et le serveur de succursales survivant. Vous pouvez modifier les propriétés du pool frontal, du serveur frontal, de l’unité de branchement Survivable et du serveur de succursales survivant pour supprimer la dépendance. Dès lors que vous effacez la dépendance et que vous avez supprimé le serveur dans le générateur de topologie, vous êtes informé que l’objet magasin de base de données associé dans le générateur de topologie sera également supprimé.
ms.openlocfilehash: ecad0a447bacacf2a894bdb735b97b3a8593b1c8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244122"
---
# <a name="remove-the-monitoring-server-association"></a>Supprimer l’association au serveur de surveillance

Pour supprimer le serveur de surveillance, vous devez modifier ou effacer la dépendance sur le pool frontal associé, le serveur frontal, l’unité de branchement Survivable et le serveur de succursales survivant. Vous pouvez modifier les propriétés du pool frontal, du serveur frontal, de l’unité de branchement survivant et du serveur de succursales survivant pour supprimer la dépendance. Dès lors que vous effacez la dépendance et que vous avez supprimé le serveur dans le générateur de topologie, vous êtes informé que l’objet magasin de base de données associé dans le générateur de topologie sera également supprimé.
  
### <a name="to-remove-the-monitoring-server-association"></a>Pour supprimer l’Association du serveur de surveillance

1. Sur le serveur frontal Skype entreprise Server 2019, ouvrez le générateur de topologie.
    
2. Accédez au nœud installations héritées.
    
3. Dans le générateur de topologie, développez **Pools front end Edition**, **serveurs front end Standard Edition**ou **sites de succursale**, selon l’endroit où le serveur de surveillance est défini.
    
4. Si vous avez un serveur de succursales Survivable associé, développez **sites**de succursales, développez le nom du site de la succursale, puis développez **appareils de branchement survivables**.
    
    > [!NOTE]
    > Les **appareils de branchement survivables** dans l’interface utilisateur s’appliquent à la fois au serveur de succursales survivant et au dispositif de branchement survivant. 
  
5. Cliquez avec le bouton droit sur le pool, le serveur ou l’appareil associé au serveur de surveillance, puis cliquez sur **modifier les propriétés**.
    
6. Dans la boîte de **dialogue Modifier les propriétés**, sous**associations** **générales** > , désactivez la case à cocher **associer le serveur de suivi** , puis cliquez sur **OK**.
    
7. Répétez l’étape précédente pour tout autre serveur ou pool associé au serveur de surveillance.
    
8. Cliquez avec le bouton droit sur le serveur de surveillance, puis cliquez sur **supprimer**. 
    
9. Sur **Supprimer les magasins**dépendants, cliquez sur **OK**.
    
10. Publiez la topologie, vérifiez l’état de la réplication et exécutez l’Assistant Déploiement de Skype entreprise Server selon vos besoins. 
    


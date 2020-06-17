---
title: Supprimer l’association au serveur de surveillance
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
description: Pour supprimer le serveur de surveillance, vous devez modifier ou supprimer la dépendance sur le pool frontal associé, le serveur frontal, le Survivable Branch appliance et le serveur Survivable Branch Server. Vous modifiez les propriétés du pool frontal, du serveur frontal, du Survivable Branch appliance et du serveur Survivable Branch Server pour supprimer la dépendance. Une fois que vous avez effacé la dépendance et supprimé le serveur dans le générateur de topologies, vous êtes informé que l’objet de magasin de bases de données associé dans le générateur de topologies est également supprimé.
ms.openlocfilehash: dafbeb88773330164a5daf2144988d1afb2776a8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753416"
---
# <a name="remove-the-monitoring-server-association"></a>Supprimer l’association au serveur de surveillance

Pour supprimer le serveur de surveillance, vous devez modifier ou supprimer la dépendance sur le pool frontal associé, le serveur frontal, le Survivable Branch appliance et le serveur Survivable Branch Server. Vous modifiez les propriétés du pool frontal, le serveur frontal, le Survivable Branch appliance et le serveur Survivable Branch Server pour supprimer la dépendance. Une fois que vous avez effacé la dépendance et supprimé le serveur dans le générateur de topologies, vous êtes informé que l’objet de magasin de bases de données associé dans le générateur de topologies est également supprimé.
  
### <a name="to-remove-the-monitoring-server-association"></a>Pour supprimer l’association du serveur de surveillance

1. Sur le serveur frontal Skype entreprise Server 2019, ouvrez le générateur de topologie.
    
2. Accédez au nœud installations héritées.
    
3. Dans le générateur de topologies, développez **Pools frontaux Enterprise Edition**, **serveurs frontaux Standard Edition**ou **sites de succursale**, en fonction de l’emplacement où est défini le serveur de surveillance.
    
4. Si vous avez un serveur Survivable Branch Server associé, développez **sites de succursale**, développez le nom du site de succursale, puis développez **Survivable Branch Appliances**.
    
    > [!NOTE]
    > **Survivable Branch Appliances** dans l’interface utilisateur s’applique aux serveurs Survivable Branch Server et Survivable Branch appliance. 
  
5. Cliquez avec le bouton droit sur le pool, le serveur ou le périphérique associé au serveur de surveillance, puis cliquez sur **modifier les propriétés**.
    
6. Dans **modifier les propriétés**, **General**sous  >  **associations**générales, désactivez la case à cocher associer un **serveur de surveillance** , puis cliquez sur **OK**.
    
7. Répétez l’étape précédente pour tout autre pool, serveur ou périphérique associé au serveur de surveillance.
    
8. Cliquez avec le bouton droit sur le serveur de surveillance, puis cliquez sur **supprimer**. 
    
9. Dans **Supprimer les magasins dépendants**, cliquez sur **OK**.
    
10. Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement de Skype entreprise Server selon vos besoins. 
    


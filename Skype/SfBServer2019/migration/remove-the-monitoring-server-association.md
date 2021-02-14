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
description: Pour supprimer le serveur de surveillance, vous devez modifier ou effacer la dépendance sur le pool frontal, le serveur frontal, le Survivable Branch Appliance et le serveur Survivable Branch Server associés. Vous modifiez les propriétés du pool frontal, du serveur frontal, du Survivable Branch Appliance et du serveur Survivable Branch Server pour supprimer la dépendance. Après avoir effacé la dépendance et supprimé le serveur dans le Générateur de topologie, vous êtes informé que l’objet magasin de bases de données associé dans le Générateur de topologie sera également supprimé.
ms.openlocfilehash: dafbeb88773330164a5daf2144988d1afb2776a8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753416"
---
# <a name="remove-the-monitoring-server-association"></a>Supprimer l’association au serveur de surveillance

Pour supprimer le serveur de surveillance, vous devez modifier ou effacer la dépendance vis-à-vis du pool frontal, du serveur frontal, du Survivable Branch Appliance et du serveur Survivable Branch Server associés. Vous modifiez les propriétés du pool frontal, du serveur frontal, du Survivable Branch Appliance et du serveur Survivable Branch Server pour supprimer la dépendance. Après avoir effacé la dépendance et supprimé le serveur dans le Générateur de topologie, vous êtes informé que l’objet magasin de bases de données associé dans le Générateur de topologie sera également supprimé.
  
### <a name="to-remove-the-monitoring-server-association"></a>Pour supprimer l’association du serveur de surveillance

1. Sur le serveur frontal Skype Entreprise Server 2019, ouvrez le Générateur de topologie.
    
2. Accédez au nœud d’installation hérité.
    
3. Dans le Générateur de topologie, développez les pools frontux **Enterprise Edition,** les serveurs frontux **Standard Edition** ou les **sites** de succursale, en fonction de l’emplacement où le serveur de surveillance est défini.
    
4. Si vous avez un serveur Survivable Branch Server associé, développez sites de **succursale,** développez le nom du site de succursale, puis développez **Survivable Branch Appliances**.
    
    > [!NOTE]
    > **Les Survivable Branch Appliances de** l’interface utilisateur s’appliquent au Serveur Survivable Branch Server et au Survivable Branch Appliance. 
  
5. Cliquez avec le bouton droit sur le pool, le serveur ou l’appareil associé au serveur de surveillance, puis cliquez sur **Modifier les propriétés.**
    
6. Dans **Modifier les propriétés,** sous **Associations**  >  **générales,** cochez la case Associer un serveur de surveillance, puis cliquez sur **OK.** 
    
7. Répétez l’étape précédente pour tout autre pool, serveur ou périphérique associé au serveur de surveillance.
    
8. Cliquez avec le bouton droit sur le serveur de surveillance, puis cliquez sur **Supprimer.** 
    
9. Dans **Supprimer les magasins dépendants**, cliquez sur **OK**.
    
10. Publiez la topologie, vérifiez l’état de la réplication et exécutez l’Assistant Déploiement de Skype Entreprise Server si nécessaire. 
    


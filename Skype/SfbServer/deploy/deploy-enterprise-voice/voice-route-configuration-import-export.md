---
title: Exporter ou importer un fichier de configuration d’itinéraire de voix dans Skype pour les entreprises
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Résumé : Découvrez comment exporter ou importer un fichier de configuration de routage voix dans Skype pour Business Server à l’aide de la Skype pour le panneau de configuration serveur Business.'
ms.openlocfilehash: 8f0d8f4e221cbe23ac37c4126a9d26aac46e6d53
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874842"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>Exporter ou importer un fichier de configuration d’itinéraire de voix dans Skype pour les entreprises
 
**Résumé :** Découvrez comment exporter ou importer un fichier de configuration de routage voix dans Skype pour Business Server à l’aide de la Skype pour le panneau de configuration serveur Business.
  
Si vous souhaitez enregistrer la configuration du routage des communications vocales sans la publier, suivez cette procédure pour enregistrer et extraire une capture instantanée de votre configuration du routage des communications vocales. 
  
Lorsque vous importez un fichier de configuration de routage voix (.vcfg), mais les modifications ont été apportées à la voix configuration du routage sur le serveur dans le même temps, les pages du groupe de **Routage des communications vocales** dans Skype pour le panneau de configuration serveur Business indiquera qu’il sont des modifications non validées à la voix de routage. Ces modifications non validées représentent les différences entre les deux configurations qui doivent être rapprochées.
  
Si vous avez apporté des modifications non validées aux paramètres de n’importe quelle page au sein du groupe, les modifications sont enregistrées dans le fichier de configuration vocale exporté (.vcfg). Cela vous permet de vous permettent d’effectuer le routage des modifications de configuration au cours de plusieurs sessions avant de publier les modifications de communications vocales. 
  
### <a name="to-export-a-voice-routing-configuration"></a>Pour exporter une configuration du routage des communications vocales

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou CsAdministrator.
    
2. Ouvrez le panneau de configuration serveur Business Skype.
    
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.
    
4. Dans le menu **Actions**, cliquez sur **Exporter la configuration**.
    
5. Spécifiez un emplacement et un nom de fichier, puis cliquez sur **Enregistrer**.
    
### <a name="to-import-a-voice-routing-configuration"></a>Pour importer une configuration du routage des communications vocales

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.
    
2. Ouvrez le panneau de configuration serveur Business Skype.
    
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.
    
4. Dans le menu **Actions**, cliquez sur **Importer la configuration**.
    
5. Recherchez le fichier de configuration à importer, puis cliquez sur **Ouvrir**.
    
6. Cliquez sur **Valider**, puis sur **Tout valider**.
    
    > [!NOTE]
    > Chaque fois que vous importez un fichier de configuration des communications vocales, vous devez exécuter la commande **Tout valider** pour publier la modification de la configuration. Pour plus d’informations, voir [Publier en attente apportées à la configuration de routage voix dans Skype pour les entreprises](voice-route-config-changes.md) dans la documentation des opérations.
  


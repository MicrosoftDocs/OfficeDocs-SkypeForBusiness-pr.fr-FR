---
title: Exportation ou importation d’un fichier de configuration du routage des communications vocales dans Skype Entreprise 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Résumé : Découvrez comment exporter ou importer un fichier de configuration de routage voix dans Skype pour Business Server 2015 à l’aide de la Skype pour le panneau de configuration serveur Business.'
ms.openlocfilehash: ba16e68ec3218a06d1baf21c238b14e3f566f630
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business-2015"></a>Exportation ou importation d’un fichier de configuration du routage des communications vocales dans Skype Entreprise 2015
 
**Résumé :** Découvrez comment exporter ou importer un fichier de configuration de routage voix dans Skype pour Business Server 2015 à l’aide de la Skype pour le panneau de configuration serveur Business.
  
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
    > Chaque fois que vous importez un fichier de configuration des communications vocales, vous devez exécuter la commande **Tout valider** pour publier la modification de la configuration. Pour plus d’informations, voir [Publier en attente apportées à la configuration de routage voix dans Skype pour Business 2015](voice-route-config-changes.md) dans la documentation des opérations.
  


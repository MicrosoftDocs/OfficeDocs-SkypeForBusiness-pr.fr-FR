---
title: Expanseur des paramètres du service de médiation pour Lync Server 2010
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 'Vous modifiez les propriétés du service de médiation en définissant les propriétés suivantes :'
ms.openlocfilehash: 2eeda1d6746f4b09c16fb56deafca11a1dbd005e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778394"
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a>Expandeur des paramètres du service de médiation pour Lync Server 2010
 
Vous modifiez les propriétés du service de médiation en définissant les propriétés suivantes :
  
- **Ports d’écoute** : définissez le port **TLS** sur lequel le service de médiation écoutera. Par défaut, la valeur du port est TCP 5067 sur TLS
    
    Éventuellement, vous définissez la valeur du port **TCP**. Par défaut, la valeur du port TCP est 5068.
    
    > [!NOTE]
    > Le paramètre de la valeur du port TCP est activé en sélectionnant **Activer le port TCP**. Vous devriez consulter la documentation de votre passerelle de réseau téléphonique commuté (PSTN) ou de votre système IP-PBX pour obtenir la configuration requise des paramètres du port pour communiquer avec le service de médiation. 
  
- Vous pouvez **activer le port TCP** pour définir la valeur du port des communications TCP à partir de votre passerelle PSTN ou de votre système IP-PBX.
    
- Une liste d’éléments existants et actuellement associés en matière de **Jonction** (c’est-à-dire, jonctions SIP (Session Initiation Protocol)), de **Passerelle** (passerelle PSTN ou système IP-PBX) et de **Site** (site configuré pour la jonction et la passerelle).
    
- Sélectionnez une jonction, une passerelle et un site, puis cliquez sur **Utiliser par défaut** pour définir la sélection en tant que valeur par défaut pour ce service de médiation. Sélectionnez la valeur par défaut actuelle, puis cliquez sur **Annuler Par défaut** pour supprimer la sélection en tant que valeur par défaut actuelle. Sélectionnez ensuite une nouvelle valeur par défaut, puis cliquez sur **Utiliser par défaut**.
    
  **OK** permet d’accepter et de valider les modifications de la boîte de dialogue.
  
  **Annuler** permet d’annuler les modifications et de fermer la boîte de dialogue.
  
  **Aide** permet d’afficher cet écran d’aide.
  


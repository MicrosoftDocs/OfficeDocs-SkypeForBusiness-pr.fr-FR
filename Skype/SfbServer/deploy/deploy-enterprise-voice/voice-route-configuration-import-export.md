---
title: Exporter ou importer un fichier de configuration d’itinéraire de voix dans Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Résumé : Découvrez comment exporter ou importer un fichier de configuration du routage des voix dans Skype Entreprise Server à l’aide du Panneau de configuration de Skype Entreprise Server.'
ms.openlocfilehash: df5ca58ebc7b92fea5236b957f4819ed3602d896
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830354"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>Exporter ou importer un fichier de configuration d’itinéraire de voix dans Skype Entreprise
 
**Résumé :** Découvrez comment exporter ou importer un fichier de configuration du routage des voix dans Skype Entreprise Server à l’aide du Panneau de configuration de Skype Entreprise Server.
  
Si vous souhaitez enregistrer votre configuration de routage des voix sans la publier, suivez ces étapes pour enregistrer et récupérer un instantané de votre configuration de routage des voix. 
  
Lorsque vous importez un fichier de configuration du routage des voix (.vcfg), mais que des modifications  ont été apportées à la configuration du routage des voix sur le serveur entre-temps, les pages du groupe de routage des voix du Panneau de configuration de Skype Entreprise Server indiquent que des modifications non prises en compte ont été apportées au routage des voix. Ces modifications non validées représentent les différences entre les deux configurations qui doivent être rapprochées.
  
Si vous avez apporté des modifications non omises aux paramètres d’une page du groupe, les modifications sont enregistrées dans le fichier de configuration vocale exporté (.vcfg). Cela vous permet d’apporter des modifications à la configuration du routage des voix au cours de plusieurs sessions avant de publier les modifications. 
  
### <a name="to-export-a-voice-routing-configuration"></a>Pour exporter une configuration du routage des communications vocales

1. Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins, ou en tant que membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.
    
2. Ouvrez le Panneau de contrôle Skype Entreprise Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.
    
4. Dans le menu **Actions**, cliquez sur **Exporter la configuration**.
    
5. Spécifiez un emplacement et un nom de fichier, puis cliquez sur **Enregistrer**.
    
### <a name="to-import-a-voice-routing-configuration"></a>Pour importer une configuration du routage des communications vocales

1. Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins, ou en tant que membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.
    
2. Ouvrez le Panneau de contrôle Skype Entreprise Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.
    
4. Dans le menu **Actions**, cliquez sur **Importer la configuration**.
    
5. Recherchez le fichier de configuration que vous voulez importer, puis cliquez sur **Ouvrir**.
    
6. Cliquez sur **Valider**, puis sur **Valider tout**.
    
    > [!NOTE]
    > Chaque fois que vous importez un fichier de configuration des communications vocales, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, voir Publier les modifications en attente de la configuration du [routage](voice-route-config-changes.md) des voix dans Skype Entreprise dans la documentation des opérations.
  


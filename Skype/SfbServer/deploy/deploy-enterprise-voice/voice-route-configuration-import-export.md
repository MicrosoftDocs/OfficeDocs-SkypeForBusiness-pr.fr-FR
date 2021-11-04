---
title: Exporter ou importer un fichier de configuration d’itinéraire des Skype Entreprise
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Résumé : Découvrez comment exporter ou importer un fichier de configuration du routage des Skype Entreprise Server à l’aide du Skype Entreprise Server de configuration.'
ms.openlocfilehash: 7b3b0ae7e7fe49b645fd5a6ee6b6b4d9fcc1affd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773224"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>Exporter ou importer un fichier de configuration d’itinéraire des Skype Entreprise
 
**Résumé :** Découvrez comment exporter ou importer un fichier de configuration du routage des Skype Entreprise Server à l’aide Skype Entreprise Server panneau de configuration.
  
Si vous souhaitez enregistrer votre configuration de routage des voix sans la publier, suivez ces étapes pour enregistrer et récupérer un instantané de votre configuration de routage des voix. 
  
Lorsque vous importez un fichier de configuration du routage des voix (.vcfg), mais que des modifications  ont été apportées à la configuration du routage des voix sur le serveur entre-temps, les pages du groupe de routage des voix du Panneau de configuration Skype Entreprise Server indiquent que des modifications non prises en main ont été apportées au routage des voix. Ces modifications non validées représentent les différences entre les deux configurations qui doivent être rapprochées.
  
Si vous avez apporté des modifications non omises aux paramètres d’une page du groupe, les modifications sont enregistrées dans le fichier de configuration vocale exporté (.vcfg). Cela vous permet d’apporter des modifications à la configuration du routage des voix au cours de plusieurs sessions avant de publier les modifications. 
  
### <a name="to-export-a-voice-routing-configuration"></a>Pour exporter une configuration du routage des communications vocales

1. Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins, ou en tant que membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.
    
2. Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.
    
4. Dans le menu **Actions**, cliquez sur **Exporter la configuration**.
    
5. Spécifiez un emplacement et un nom de fichier, puis cliquez sur **Enregistrer**.
    
### <a name="to-import-a-voice-routing-configuration"></a>Pour importer une configuration du routage des communications vocales

1. Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins, ou en tant que membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.
    
2. Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.
    
4. Dans le menu **Actions**, cliquez sur **Importer la configuration**.
    
5. Recherchez le fichier de configuration que vous voulez importer, puis cliquez sur **Ouvrir**.
    
6. Cliquez sur **Valider**, puis sur **Valider tout**.
    
    > [!NOTE]
    > Chaque fois que vous importez un fichier de configuration des communications vocales, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, voir [Publish pending changes to the voice routing configuration in Skype Entreprise](voice-route-config-changes.md) in the Operations documentation.
  


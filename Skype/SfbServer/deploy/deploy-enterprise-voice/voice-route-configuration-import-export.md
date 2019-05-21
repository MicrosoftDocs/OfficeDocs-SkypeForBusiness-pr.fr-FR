---
title: Exporter ou importer un fichier de configuration de l’itinéraire vocal dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Résumé: Découvrez comment exporter ou importer un fichier de configuration de l’acheminement vocal dans Skype entreprise Server à l’aide du panneau de configuration Skype entreprise Server.'
ms.openlocfilehash: 14637694e5604419fcd344b43af98263588f117a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300879"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>Exporter ou importer un fichier de configuration de l’itinéraire vocal dans Skype entreprise
 
**Résumé:** Découvrez comment exporter ou importer un fichier de configuration de l’acheminement vocal dans Skype entreprise Server à l’aide du panneau de configuration Skype entreprise Server.
  
Si vous souhaitez enregistrer la configuration du routage des communications vocales sans la publier, suivez cette procédure pour enregistrer et extraire une capture instantanée de votre configuration du routage des communications vocales. 
  
Lorsque vous importez un fichier de configuration de l’acheminement vocal (. VCFG), mais que des modifications ont été apportées à la configuration de l’acheminement du message sur le serveur, les pages du groupe de routage de la **voix** du panneau de configuration Skype entreprise Server indiquent qu’il y a les modifications non validées apportées au routage de la voix. Ces modifications non validées représentent les différences entre les deux configurations qui doivent être rapprochées.
  
Si vous avez apporté des modifications non validées aux paramètres sur n’importe quelle page du groupe, les modifications sont enregistrées dans le fichier de configuration de la voix exporté (. VCFG). Cela vous permet de procéder à des modifications de la configuration de l’acheminement des messages pendant plusieurs sessions avant de publier les modifications. 
  
### <a name="to-export-a-voice-routing-configuration"></a>Pour exporter une configuration du routage des communications vocales

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou CsAdministrator.
    
2. Ouvrez le panneau de configuration Skype entreprise Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.
    
4. Dans le menu **Actions**, cliquez sur **Exporter la configuration**.
    
5. Spécifiez un emplacement et un nom de fichier, puis cliquez sur **Enregistrer**.
    
### <a name="to-import-a-voice-routing-configuration"></a>Pour importer une configuration du routage des communications vocales

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.
    
2. Ouvrez le panneau de configuration Skype entreprise Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.
    
4. Dans le menu **Actions**, cliquez sur **Importer la configuration**.
    
5. Recherchez le fichier de configuration à importer, puis cliquez sur **Ouvrir**.
    
6. Cliquez sur **Valider**, puis sur **Tout valider**.
    
    > [!NOTE]
    > Chaque fois que vous importez un fichier de configuration des communications vocales, vous devez exécuter la commande **Tout valider** pour publier la modification de la configuration. Pour plus d’informations, reportez-vous [à la rubrique publier des modifications en attente sur la configuration de la messagerie dans Skype entreprise](voice-route-config-changes.md) dans la documentation sur les opérations.
  


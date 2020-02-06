---
title: Développeur des paramètres du service de médiation frontal pour Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'Dans cette boîte de dialogue, vous pouvez modifier les propriétés des paramètres de la passerelle RTC du serveur de médiation. Vous définissez les paramètres suivants :'
ms.openlocfilehash: dfe3defeb7cdce787321a401ca2a5450ee6b4ab8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819876"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Développeur des paramètres du service de médiation frontal pour Lync Server 2010
 
Dans cette boîte de dialogue, vous pouvez modifier les propriétés des paramètres de la **passerelle RTC du serveur de médiation** . Vous définissez les paramètres suivants :
  
- Sélectionnez le **serveur de médiation en option activé** si vous voulez Collocate le serveur de médiation avec ce serveur frontal ou les listes frontales.
    
- **Ports d’écoute**: définissez les ports que le serveur de médiation va écouter. Vous pouvez définir un port pour **TLS ou TLS** (Transport Layer Security), ou **TCP**ou protocole de contrôle de transport. Pour que l’entrée de port du protocole TCP soit disponible, vous devez activer la case à cocher **activer le port TCP**. 
    
    > [!IMPORTANT]
    > Reportez-vous à la documentation et aux paramètres de configuration de votre passerelle RTC (réseau téléphonique commuté) pour déterminer si vous devez activer et définir des valeurs de port TLS, TCP ou les deux. TLS est un protocole plus sécurisé, qui utilise des certificats pour chiffrer le trafic entre le serveur de médiation et la passerelle PSTN. Les passerelles RTC ne prennent pas en charge le protocole TLS. 
  
- Une liste répertorie les **jonctions** (jonctions SIP [Session Initiation Protocol]), la **passerelle** (passerelle RTC ou système IP-PBX) et le **site** (site configuré pour la jonction et la passerelle).
    
- Sélectionnez une jonction, une passerelle et un site et cliquez sur **Utiliser par défaut** pour définir la sélection comme valeur par défaut pour ce service de médiation. Sélectionnez la valeur par défaut actuelle, puis cliquez sur **Annuler par défaut** pour supprimer la sélection comme valeur par défaut actuelle. Sélectionnez ensuite une nouvelle valeur par défaut et cliquez sur **Utiliser par défaut**.
    
  **OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.
  
  **Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.
  
  **Aide** : permet d’afficher cet écran d’aide.
  


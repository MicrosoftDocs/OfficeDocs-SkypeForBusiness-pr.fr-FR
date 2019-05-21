---
title: Configuration d’une voie vocale E9-1-1 dans Skype entreprise Server
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
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Configurez des itinéraires vocaux E9-1-1 dans Skype entreprise Server Voice.
ms.openlocfilehash: 0ef8b1ba2b64c74cb2166c90dfdccf134df42252
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303453"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a>Configuration d’une voie vocale E9-1-1 dans Skype entreprise Server
 
Configurez des itinéraires vocaux E9-1-1 dans Skype entreprise Server Voice. 
  
Pour déployer E9-1-1, vous devez d’abord configurer un itinéraire des communications vocales pour les appels d’urgence. Pour plus d’informations sur la création d’itinéraires vocaux, voir [créer ou modifier un itinéraire vocal dans Skype entreprise](create-or-modify-a-voice-route.md). Vous pouvez définir plusieurs itinéraires si, par exemple, votre déploiement comporte une jonction SIP (Session Initiation Protocol) principale et une jonction SIP secondaire. 
  
> [!NOTE]
> Pour inclure des informations d’emplacement dans une invitation E9-1-1, vous devez configurer le Trunk SIP qui se connecte au fournisseur de services E9-1-1 pour diriger les appels d’urgence par le biais de la passerelle. Pour ce faire, définissez l’indicateur EnablePIDFLOSupport sur la cmdlet **Set-CsTrunkConfiguration** sur true. La valeur par défaut de EnablePIDFLOSupport est false. Par exemple: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` il n’est pas nécessaire d’activer les emplacements de réception pour les passerelles de réseau téléphonique commuté (RTC) et les passerelles d’identification d’emplacement d’urgence (Elin).
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>Pour configurer un itinéraire des communications vocales E9-1-1

1. Ouvrez une session sur l’ordinateur à l’aide d’un compte membre du groupe RTCUniversalServerAdmins ou du rôle d’administration CsVoiceAdministrator.
    
2.  Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
3. Exécutez l’applet de commande ci-dessous pour créer un enregistrement d’utilisation RTC. 
    
    Ce nom doit être identique à celui que vous utiliserez pour le paramètre **RTC** de la stratégie d’emplacement. Si votre déploiement comporte plusieurs enregistrements d’utilisation téléphonique, l’exemple ci-dessous ajoute « Emergency Usage » (Utilisation d’urgence) à la liste actuelle des utilisations RTC disponibles. Pour plus d’informations, reportez-vous à la rubrique [Configuration des stratégies vocales, des enregistrements d’utilisation RTC et des itinéraires vocaux dans Skype entreprise](voice-and-pstn.md).
    
   ```
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. Exécutez l’applet de commande ci-dessous pour créer un itinéraire des communications vocales à l’aide de l’enregistrement d’utilisation RTC créé lors de l’étape précédente.
    
    Le modèle de numéro doit être identique à celui utilisé dans le paramètre **Chaîne de numérotation d’urgence** de la stratégie d’emplacement. Le signe "+" est requis, car Skype entreprise ajoute "+" aux appels d’urgence. « Co1-pstngateway-1 » est l’ID du service de jonction SIP (Session Initiation Protocol) pour le fournisseur de services E9-1-1 ou l’ID du service de passerelle ELIN. L’exemple ci-dessous utilise « EmergencyRoute » comme nom de l’itinéraire des communications vocales.
    
   ```
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. Si vous le souhaitez, pour les connexions SIP Trunk, nous vous conseillons d’exécuter l’applet de commande suivante pour créer un itinéraire local pour les appels qui ne sont pas gérés par le Trunk SIP du fournisseur de services E9-1-1. Cet itinéraire est utilisé si la connexion au fournisseur de services E9-1-1 n’est pas disponible. 
    
    L’exemple ci-dessous part du principe que l’utilisateur a une utilisation « locale » dans sa stratégie de voix.
    
   ```
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```



---
title: Configuration d’un itinéraire des communications vocales E9-1-1 dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Configurer les itinéraires de communications vocales E9-1-1 dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: c31ac7c264fb931c127375eca5a383d10998c3f1
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server-2015"></a>Configuration d’un itinéraire des communications vocales E9-1-1 dans Skype Entreprise Server 2015
 
Configurer les itinéraires de communications vocales E9-1-1 dans Skype pour Business Server Enterprise Voice. 
  
Pour déployer E9-1-1, vous devez d’abord configurer un itinéraire des communications vocales pour les appels d’urgence. Pour plus d’informations sur la création d’itinéraires de communications vocales, voir [créer ou modifier un itinéraire de communications vocales dans Skype pour Business 2015](create-or-modify-a-voice-route.md). Vous pouvez définir plusieurs itinéraires si, par exemple, votre déploiement comporte une jonction SIP (Session Initiation Protocol) principale et une jonction SIP secondaire. 
  
> [!NOTE]
> Pour inclure des informations sur l’emplacement dans un inviter E9-1-1, vous devez configurer la jonction SIP qui se connecte au fournisseur de services E9-1-1 pour acheminer les appels d’urgence via la passerelle. Pour ce faire, définissez l’indicateur EnablePIDFLOSupport sur l’applet de commande **Set-CsTrunkConfiguration** sur True. La valeur par défaut pour EnablePIDFLOSupport a la valeur False. Par exemple : `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` n’est pas nécessaire d’activer la réception des emplacements de secours commuté téléphone PSTN (réseau) passerelles et urgence ELIN Location Identification Number ().
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>Pour configurer un itinéraire des communications vocales E9-1-1

1. Ouvrez une session sur l’ordinateur à l’aide d’un compte membre du groupe RTCUniversalServerAdmins ou du rôle d’administration CsVoiceAdministrator.
    
2.  Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. Exécutez l’applet de commande ci-dessous pour créer un enregistrement d’utilisation RTC. 
    
    Ce nom doit être identique à celui que vous utiliserez pour le paramètre **RTC** de la stratégie d’emplacement. Si votre déploiement comporte plusieurs enregistrements d’utilisation téléphonique, l’exemple ci-dessous ajoute « Emergency Usage » (Utilisation d’urgence) à la liste actuelle des utilisations RTC disponibles. Pour plus d’informations, voir [configurer les stratégies de voix, les enregistrements d’utilisation PSTN et les itinéraires de communications vocales dans Skype pour Business 2015](voice-and-pstn.md).
    
   ```
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. Exécutez l’applet de commande ci-dessous pour créer un itinéraire des communications vocales à l’aide de l’enregistrement d’utilisation RTC créé lors de l’étape précédente.
    
    Le modèle de numéro doit être identique à celui utilisé dans le paramètre **Chaîne de numérotation d’urgence** de la stratégie d’emplacement. Un signe « + » est nécessaire car Skype pour les entreprises ajoute « + » pour les appels d’urgence. « Co1-pstngateway-1 » est l’ID du service de jonction SIP (Session Initiation Protocol) pour le fournisseur de services E9-1-1 ou l’ID du service de passerelle ELIN. L’exemple ci-dessous utilise « EmergencyRoute » comme nom de l’itinéraire des communications vocales.
    
   ```
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

   ```

5. Si vous le souhaitez, pour les connexions de jonction SIP, nous vous recommandons d’exécuter la cmdlet suivante pour créer un itinéraire local pour les appels qui ne sont pas gérés par la jonction SIP du fournisseur de services E9-1-1. Cet itinéraire est utilisé si la connexion au fournisseur de services E9-1-1 n’est pas disponible. 
    
    L’exemple ci-dessous part du principe que l’utilisateur a une utilisation « locale » dans sa stratégie de voix.
    
   ```
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```



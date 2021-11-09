---
title: Configurer un itinéraire de messagerie vocale E9-1-1 dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Configurez les itinéraires de voix E9-1-1 dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 86904c32db6ae43b9fa1b6f184048d3b9f419089
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833950"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a>Configurer un itinéraire de messagerie vocale E9-1-1 dans Skype Entreprise Server
 
Configurez les itinéraires de voix E9-1-1 dans Skype Entreprise Server Voix Entreprise. 
  
Pour déployer E9-1-1, vous devez d’abord configurer un itinéraire des communications vocales pour les appels d’urgence. Pour plus d’informations sur la création d’itinéraires de communication vocale, voir [Create or modify a voice route in Skype Entreprise](create-or-modify-a-voice-route.md). Vous pouvez définir plusieurs itinéraires si, par exemple, votre déploiement comporte une jonction SIP principale et une jonction SIP secondaire. 
  
> [!NOTE]
> Pour inclure les informations d’emplacement dans une E9-1-1 INVITE, vous devez configurer la jonction SIP qui établit la connexion avec le fournisseur de services E9-1-1 pour acheminer les appels d’urgence par l’intermédiaire de la passerelle. Pour ce faire, affectez à l’indicateur EnablePIDFLOSupport de l’applet de commande **Set-CsTrunkConfiguration** la valeur True. La valeur par défaut de EnablePIDFLOSupport est False. Par exemple : il n’est pas nécessaire d’activer la réception d’emplacements pour les passerelles de réseau téléphonique commuté (PSTN) de secours et les `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` passerelles ELIN (Emergency Location Identification Number).
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>Pour configurer un itinéraire des communications vocales E9-1-1

1. Ouvrez une session sur l’ordinateur à l’aide d’un compte membre du groupe RTCUniversalServerAdmins ou du rôle d’administration CsVoiceAdministrator.
    
2.  Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
3. Exécutez l’applet de commande suivante pour créer un nouvel enregistrement d’utilisation PSTN. 
    
    Ce nom doit être identique à celui que vous utiliserez pour le paramètre **PSTN** de la stratégie d’emplacement. Si votre déploiement comporte plusieurs enregistrements d’utilisation téléphonique, l’exemple suivant ajoute « Emergency Usage » (Utilisation d’urgence) à la liste actuelle des utilisations PSTN disponibles. Pour plus d’informations, voir [Configure voice policies, PSTN usage records, and voice routes in Skype Entreprise](voice-and-pstn.md).
    
   ```powershell
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. Exécutez l’applet de commande suivante pour créer un itinéraire des communications vocales à l’aide de l’enregistrement d’utilisation PSTN créé à l’étape précédente.
    
    Le modèle de numéro doit être identique à celui utilisé dans le paramètre **Chaîne de numérotation d’urgence** de la stratégie d’emplacement. Un signe « + » est nécessaire, Skype Entreprise ajoute « + » aux appels d’urgence. « Co1-pstngateway-1 » est l’ID du service de jonction SIP pour le fournisseur de services E9-1-1 ou l’ID du service de passerelle ELIN. L’exemple suivant utilise « EmergencyRoute » comme nom de l’itinéraire des communications vocales.
    
   ```powershell
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. Si vous le souhaitez, pour les connexions de trunk SIP, nous vous recommandons d’exécuter l’cmdlet suivante pour créer un itinéraire local pour les appels qui ne sont pas gérés par la connexion SIP du fournisseur de services E9-1-1. Cet itinéraire est utilisé si la connexion au fournisseur de services E9-1-1 n’est pas disponible. 
    
    L’exemple suivant part du principe que l’utilisateur a une utilisation « locale » dans sa stratégie de voix.
    
   ```powershell
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```



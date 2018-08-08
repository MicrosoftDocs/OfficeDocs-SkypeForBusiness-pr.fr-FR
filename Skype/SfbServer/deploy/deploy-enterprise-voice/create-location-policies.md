---
title: Créer des stratégies d’emplacement dans Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: Lisez cette rubrique pour savoir comment configurer améliorée des stratégies d’emplacement de service d’urgence (E9-1-1) dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 525c0a1a7a22a31e129c50ebebd68483a31cb87c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20987263"
---
# <a name="create-location-policies-in-skype-for-business-server"></a>Créer des stratégies d’emplacement dans Skype pour Business Server
 
Lisez cette rubrique pour savoir comment configurer améliorée des stratégies d’emplacement de service d’urgence (E9-1-1) dans Skype pour Business Server Enterprise Voice. 
  
Skype pour Business Server utilise une stratégie d’emplacement pour activer Skype pour les clients d’entreprise pour E9-1-1 au cours de l’inscription du client. Une stratégie d’emplacement contient les paramètres qui définissent les modalités de mise en œuvre du système E9-1-1. Pour plus d’informations, voir [planifier des stratégies d’emplacement pour Skype pour Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).
  
Vous définissez des stratégies d’emplacement à l’aide de la Skype pour Business le panneau de configuration ou à l’aide de l’applet de commande [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) .
  
> [!NOTE]
> Skype pour Business Server prend désormais en charge la configuration de plusieurs numéros d’urgence pour un client. Si vous souhaitez configurer plusieurs numéros d’urgence, vous devez suivre les informations de [planifier plusieurs numéros d’urgence dans Skype pour Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) et [configurer plusieurs numéros d’urgence dans Skype pour les entreprises](configure-multiple-emergency-numbers.md). 
  
Vous pouvez modifier la stratégie d’emplacement globale et créer des stratégies d’emplacement avec balise. Un client obtient une stratégie globale lorsqu’il ne se situe pas dans un sous-réseau auquel une stratégie d’emplacement est associée ou lorsque le client n’a pas été affecté directement à une stratégie d’emplacement. Les stratégies avec balise sont affectées aux sous-réseaux ou aux utilisateurs.   
  
Pour créer une stratégie d’emplacement, vous devez utiliser un compte membre du groupe RTCUniversalServerAdmins, membre du rôle administratif CsVoiceAdministrator ou possédant des droits et des autorisations d’administrateur équivalents.
  
Pour plus d’informations, voir [planifier des stratégies d’emplacement pour Skype pour Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md). Les applets de commande dans cette procédure utilisent une stratégie d'emplacement définie à l'aide des valeurs suivantes. Pour obtenir une description complète des paramètres de l’applet de commande et les valeurs, voir [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).
  
|**Élément**|**Valeur**|
|:-----|:-----|
|EnhancedEmergencyServicesEnabled  <br/> |**True** <br/> |
|LocationRequired  <br/> |**Clause d’exclusion** <br/> |
|EnhancedEmergencyServiceDisclaimer  <br/> |La stratégie de votre société exige que vous définissiez un emplacement. Si vous ne le faites pas, les services d’urgence ne pourront pas vous localiser en cas d’urgence. Définissez un emplacement.  <br/> |
|UseLocationForE911Only  <br/> |**False** <br/> |
|PstnUsage  <br/> |**EmergencyUsage** <br/> |
|EmergencyDialString  <br/> |**911** <br/> |
|EmergencyDialMask  <br/> |**112** <br/> |
|NotificationUri  <br/> |**SIP:Security@litwareinc.com** <br/> |
|ConferenceUri  <br/> |**SIP:+14255550123@litwareinc.com** <br/> |
|ConferenceMode  <br/> |**twoway** <br/> |
|LocationRefreshInterval  <br/> |**2** <br/> |
   
### <a name="to-create-location-policies"></a>Pour créer des stratégies d’emplacement

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
    > [!NOTE]
    > CsLocationPolicy échouera si le paramètre pour **PstnUsage** ne figure pas déjà dans la liste Global de PstnUsages.
  
2. Si vous le souhaitez, exécutez l’applet de commande ci-dessous pour modifier la stratégie d’emplacement globale :
    
   ```
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. Pour créer une stratégie d’emplacement avec balise, exécutez l’opération ci-dessous.
    
   ```
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. Exécutez l’applet de commande ci-dessous pour appliquer la stratégie d’emplacement avec balise créée lors de l’étape 3 à une stratégie d’utilisateur.
    
   ```
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```
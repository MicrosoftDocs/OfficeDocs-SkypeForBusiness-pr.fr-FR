---
title: Création de stratégies d’emplacement dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: Lisez cette rubrique pour savoir comment configurer améliorée des stratégies d’emplacement de service d’urgence (E9-1-1) dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 7635199810e21f33bdbe30d5bf6f229987fa8c77
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-location-policies-in-skype-for-business-server-2015"></a>Création de stratégies d’emplacement dans Skype Entreprise Server 2015
 
Lisez cette rubrique pour savoir comment configurer améliorée des stratégies d’emplacement de service d’urgence (E9-1-1) dans Skype pour Business Server Voix Entreprise. 
  
Skype pour Business Server utilise une stratégie de l’emplacement pour activer Skype pour les clients d’entreprise pour E9-1-1 lors de l’enregistrement du client. Une stratégie d’emplacement contient les paramètres qui définissent les modalités de mise en œuvre du système E9-1-1. Pour plus d’informations, voir [planifier des stratégies d’emplacement pour Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).
  
Vous définissez des stratégies de l’emplacement à l’aide de la Skype pour le panneau d’entreprise ou à l’aide de l’applet de commande [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) .
  
> [!NOTE]
> Skype pour Business Server prend désormais en charge la configuration de plusieurs numéros d’urgence pour un client. Si vous souhaitez configurer plusieurs numéros d’urgence, vous devez suivre les informations de [planifier plusieurs numéros d’urgence dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) et [configurer plusieurs numéros d’urgence dans Skype pour entreprise 2015](configure-multiple-emergency-numbers.md). 
  
Vous pouvez modifier la stratégie d’emplacement globale et créer des stratégies d’emplacement avec balise. Un client obtient une stratégie globale lorsqu’il ne se situe pas dans un sous-réseau auquel une stratégie d’emplacement est associée ou lorsque le client n’a pas été affecté directement à une stratégie d’emplacement. Les stratégies avec balise sont affectées aux sous-réseaux ou aux utilisateurs.   
  
Pour créer une stratégie d’emplacement, vous devez utiliser un compte membre du groupe RTCUniversalServerAdmins, membre du rôle administratif CsVoiceAdministrator ou possédant des droits et des autorisations d’administrateur équivalents.
  
Pour plus d’informations, voir [planifier des stratégies d’emplacement pour Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/location-policies.md). Les applets de commande dans cette procédure utilisent une stratégie d'emplacement définie à l'aide des valeurs suivantes. Pour une description complète des paramètres de l’applet de commande et des valeurs, reportez-vous à la section [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).
  
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



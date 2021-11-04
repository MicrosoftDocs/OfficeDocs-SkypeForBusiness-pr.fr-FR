---
title: Créer des stratégies d’emplacement dans Skype Entreprise Server
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
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: Lisez cette rubrique pour découvrir comment configurer des stratégies d’emplacement de service d’urgence amélioré (E9-1-1) dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 889a20e0b48955be1ce0ba8c891d6c4825b79dab
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741440"
---
# <a name="create-location-policies-in-skype-for-business-server"></a>Créer des stratégies d’emplacement dans Skype Entreprise Server

Lisez cette rubrique pour découvrir comment configurer des stratégies d’emplacement de service d’urgence amélioré (E9-1-1) dans Skype Entreprise Server Voix Entreprise. 

Skype Entreprise Server utilise une stratégie d’emplacement pour activer Skype Entreprise clients pour E9-1-1 lors de l’inscription du client. Une stratégie d’emplacement contient les paramètres qui définissent la façon dont E9-1-1 sera implémenté. Pour plus d’informations, voir [Planifier les stratégies d’emplacement Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).

Vous définissez des stratégies d’emplacement à l’Skype Entreprise panneau de Skype Entreprise ou à l’aide de l';cmdlet [New-CsLocationPolicy.](/powershell/module/skype/new-cslocationpolicy?view=skype-ps)

> [!NOTE]
> Skype Entreprise Server prend désormais en charge la configuration de plusieurs numéros d’urgence pour un client. Si vous souhaitez configurer plusieurs numéros d’urgence, vous devez suivre les informations de la zone Planifier plusieurs numéros d’urgence dans [Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) et configurer plusieurs numéros d’urgence dans [Skype Entreprise](configure-multiple-emergency-numbers.md). 

Vous pouvez modifier la stratégie d’emplacement globale et créer des stratégies d’emplacement marquées. Un client obtient une stratégie globale lorsqu’il n’est pas situé dans un sous-réseau avec une stratégie d’emplacement associée, ou lorsqu’il n’a pas été directement affecté à une stratégie d’emplacement. Les stratégies marquées sont affectées à des sous-réseaux ou à des utilisateurs. 

Pour créer une stratégie d’emplacement, vous devez utiliser un compte membre du groupe RTCUniversalServerAdmins ou membre du rôle d’administrateur CsVoiceAdministrator, ou qui dispose de droits et d’autorisations d’administrateur équivalents.

Pour plus d’informations, voir [Planifier les stratégies d’emplacement Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md). Les cmdlets de cette procédure utilisent une stratégie d’emplacement définie à l’aide des valeurs suivantes. Pour obtenir une description complète des paramètres et des valeurs d’une cmdlet, voir [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps).


| **Élément**                               | **Valeur**                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| EnhancedEmergencyServicesEnabled  <br/>   | **True** <br/>                                                                                                                                                                     |
| LocationRequired  <br/>                   | **Clause d’exclusion de responsabilité** <br/>                                                                                                                                                               |
| EnhancedEmergencyServiceDisclaimer  <br/> | Votre stratégie d’entreprise exige que vous définissez un emplacement. Si vous ne définissez pas d’emplacement, les services d’urgence ne pourront pas vous localiser en cas d’urgence. Veuillez définir un emplacement.  <br/> |
| UseLocationForE911Only  <br/>             | **False** <br/>                                                                                                                                                                    |
| PstnUsage  <br/>                          | **EmergencyUsage** <br/>                                                                                                                                                           |
| EmergencyDialString  <br/>                | **911** <br/>                                                                                                                                                                      |
| EmergencyDialMask  <br/>                  | **112** <br/>                                                                                                                                                                      |
| NotificationUri  <br/>                    | <strong>sip:security@litwareinc.com</strong> <br/>                                                                                                                                 |
| ConferenceUri  <br/>                      | <strong>sip:+14255550123@litwareinc.com</strong> <br/>                                                                                                                             |
| ConferenceMode  <br/>                     | **twoway** <br/>                                                                                                                                                                   |
| LocationRefreshInterval  <br/>            | **2** <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a>Pour créer des stratégies d’emplacement

1. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**

    > [!NOTE]
    > CsLocationPolicy échoue si le paramètre **PstnUsage** ne figure pas déjà dans la liste globale des PstnUsages.

2. Éventuellement, exécutez l’cmdlet suivante pour modifier la stratégie d’emplacement globale :

   ```powershell
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. Exécutez la liste suivante pour créer une stratégie d’emplacement marquée.

   ```powershell
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. Exécutez l’cmdlet suivante pour appliquer la stratégie d’emplacement balisé créée à l’étape 3 à une stratégie utilisateur.

   ```powershell
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```
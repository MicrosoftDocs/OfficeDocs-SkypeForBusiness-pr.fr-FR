---
title: Affectation d’une stratégie de routage des communications vocales
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Résumé : Lisez cette rubrique pour savoir comment attribuer une stratégie de voix pour les utilisateurs à l’aide du système téléphonique dans Office 365 avec une connectivité PSTN sur site.'
ms.openlocfilehash: fc11fabeb7f6a8bacc0f3a6dd48d6ed24edd3403
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="assign-a-voice-routing-policy"></a>Affectation d’une stratégie de routage des communications vocales
 
**Résumé :** Lisez cette rubrique pour savoir comment attribuer une stratégie de voix pour les utilisateurs à l’aide du système téléphonique dans Office 365 avec une connectivité PSTN sur site.
  
Une fois qu’un utilisateur est sur Skype Business en ligne et l’utilisation de système téléphonique dans Office 365 avec une connectivité PSTN sur site, deux stratégies de voix leur seront appliquée. Une est une stratégie de routage voix locale que vous affecterez localement. Cette stratégie peut être globale ou spécifique à l’utilisateur et définit les enregistrements d’utilisation PSTN associées à l’utilisateur. Cette rubrique explique comment affecter cette stratégie.
  
L’autre stratégie de voix définit les fonctionnalités d’appel sont disponibles à l’utilisateur. Cette stratégie de voix est définie par Microsoft et est identique pour tous les système téléphonique dans Office 365 avec des utilisateurs de connectivité PSTN sur site. Il est automatiquement affecté au système téléphonique dans les utilisateurs d’Office 365.
  
||**Utilisateur local**|**Système téléphonique dans Office 365 avec l’utilisateur de connectivité PSTN sur site**|
|:-----|:-----|:-----|
|Fonctionnalités d’appel définies dans  <br/> |Stratégie vocale  <br/> |Prédéfinis stratégie de voix, affectée automatiquement lorsque l’utilisateur possède une licence de système téléphonique dans Office 365.  <br/> |
|Enregistrements d’utilisation RTC associés à  <br/> |Stratégie vocale  <br/> |Stratégie de routage des communications vocales, affectée alors que l’utilisateur est encore hébergé en local.  <br/> |
   
Vous effectuez les étapes suivantes à l’aide de votre déploiement sur site, tandis que l’utilisateur est toujours hébergé dans le déploiement local.
  
## <a name="using-a-global-voice-routing-policy"></a>Utilisation d’une stratégie globale de routage des communications vocales

Avant d’utiliser une stratégie de routage voix globale pour votre système téléphonique dans Office 365 avec des utilisateurs de connectivité PSTN sur site, vous devez ajouter des enregistrements d’utilisation PSTN à la stratégie.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>Pour affecter des enregistrements d’utilisation RTC à la stratégie globale de routage des communications vocales

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. Ajouter les enregistrements d’utilisation PSTN à la stratégie :
    
  ```
  Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 

  ```

    Par exemple :
    
  ```
  Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 

  ```

## <a name="creating-a-new-voice-routing-policy"></a>Création d’une stratégie de routage des communications vocales

### <a name="to-create-a-new-voice-routing-policy"></a>Pour créer une stratégie de routage des communications vocales

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. Créez une stratégie de routage des communications vocales :
    
  ```
  New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
  ```

    Par exemple :
    
  ```
  New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
  ```

Cet exemple crée une stratégie de routage des communications vocales appelée « HybridVoice », à laquelle sont associées deux utilisations RTC.
  
## <a name="assigning-a-voice-routing-policy"></a>Affectation d’une stratégie de routage des communications vocales

Que vous utilisiez la stratégie globale de routage des communications vocales ou des stratégies spécifiques aux utilisateurs, procédez comme suit pour affecter cette stratégie à un utilisateur.
  
### <a name="to-assign-the-voice-routing-policy"></a>Pour affecter la stratégie de routage des communications vocales

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. Affectez une stratégie de voix existante à un utilisateur :
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
  ```

    Par exemple :
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
  ```

Dans cet exemple, l’utilisateur Bob Kelly est affecté à la stratégie de voix « HybridVoice » créée précédemment.
  
Pour plus d’informations sur les stratégies de routage voix, voir [créer ou modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Skype pour Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)et [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).
  


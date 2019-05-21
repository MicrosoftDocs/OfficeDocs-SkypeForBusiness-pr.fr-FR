---
title: Affectation d’une stratégie de routage des communications vocales
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Résumé: cette rubrique vous explique comment affecter une stratégie vocale aux utilisateurs de l’utilisation d’un système téléphonique dans Office 365 avec une connectivité PSTN locale.'
ms.openlocfilehash: 0d310378b77c09b427836f0d9bceb60a14982071
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294431"
---
# <a name="assign-a-voice-routing-policy"></a>Affectation d’une stratégie de routage des communications vocales
 
**Résumé:** Pour plus d’informations sur l’affectation d’une stratégie vocale aux utilisateurs de l’utilisation d’un système téléphonique dans Office 365 avec une connectivité PSTN locale, lisez cette rubrique. 
  
Une fois qu’un utilisateur est connecté à Skype entreprise Online et utilise le système téléphonique dans Office 365 avec la connectivité PSTN locale, deux politiques vocales y sont appliquées. Il s’agit d’une stratégie de routage téléphonique locale que vous allez attribuer en local. Ce paramètre peut être défini sur le niveau global ou spécifique de l’utilisateur et définit les enregistrements d’utilisation RTC associés à l’utilisateur. Cette rubrique explique comment affecter cette stratégie.
  
L’autre stratégie vocale définit les fonctionnalités d’appel qui sont disponibles pour l’utilisateur; Cette politique vocale est définie par Microsoft et est identique pour tous les systèmes téléphoniques dans Office 365 avec les utilisateurs de connectivité RTC sur site. Ce service est automatiquement attribué au système téléphonique des utilisateurs d’Office 365.
  
||**Utilisateur du déploiement local**|**Système téléphonique dans Office 365 avec un utilisateur de connectivité RTC sur site**|
|:-----|:-----|:-----|
|Fonctionnalités d’appel définies dans  <br/> |Stratégie de voix  <br/> |Politique vocale prédéfinie, attribuée automatiquement lorsque l’utilisateur est titulaire d’une licence pour un système téléphonique dans Office 365.  <br/> |
|Enregistrements d’utilisation RTC associés à  <br/> |Stratégie vocale  <br/> |Stratégie de routage des communications vocales, affectée alors que l’utilisateur est encore hébergé en local.  <br/> |
   
Pour effectuer les étapes suivantes à l’aide de votre déploiement local, l’utilisateur est toujours hébergé dans le déploiement local.
  
## <a name="using-a-global-voice-routing-policy"></a>Utilisation d’une stratégie globale de routage des communications vocales

Avant d’utiliser une politique générale de routage de la voix pour votre système téléphonique dans Office 365 avec les utilisateurs de connectivité PSTN locale, vous devez ajouter des enregistrements d’utilisation RTC à la stratégie.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>Pour affecter des enregistrements d’utilisation RTC à la stratégie globale de routage des communications vocales

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
3. Ajoutez les enregistrements d’utilisation RTC à la stratégie:
    
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
    
2. Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
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
    
2. Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
3. Affectez une stratégie de voix existante à un utilisateur :
    
   ```
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Par exemple :
    
   ```
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

Dans cet exemple, l’utilisateur Bob Kelly est affecté à la stratégie de voix « HybridVoice » créée précédemment.
  
Pour plus d’informations sur les stratégies de routage de messagerie vocale, consultez [la rubrique créer ou modifier une stratégie vocale et configurer les enregistrements d’utilisation RTC dans Skype entreprise 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [nouveau-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)et [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).
  


---
title: Affectation d’une stratégie de routage des communications vocales
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Résumé : Lisez cette rubrique pour savoir comment attribuer une stratégie voice pour les utilisateurs à l’aide du système téléphonique dans Office 365 avec la connectivité RTPC sur site.'
ms.openlocfilehash: bcc4102157a3689208c45d7430a7954ce9a1e3f9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="assign-a-voice-routing-policy"></a>Affectation d’une stratégie de routage des communications vocales
 
**Résumé :** Lisez cette rubrique pour savoir comment attribuer une stratégie voice pour les utilisateurs à l’aide du système téléphonique dans Office 365 avec la connectivité RTPC sur site.
  
Une fois qu’un utilisateur est sur Skype pour entreprise en ligne et à l’aide du système téléphonique dans Office 365 avec la connectivité RTPC sur site, deux stratégies voice seront appliquent à eux. L’une est une stratégie de routage voix sur site auquel vous souhaitez affecter dans les locaux. Cette stratégie peut être globale ou spécifique à l’utilisateur et définit les enregistrements d’utilisation RTPC sont associés à l’utilisateur. Cette rubrique explique comment affecter cette stratégie.
  
L’autre stratégie voice définit les fonctionnalités d’appel sont disponibles à l’utilisateur. Cette stratégie voice est défini par Microsoft et est identique pour tous les systèmes de téléphone dans Office 365 avec les utilisateurs de connectivité RTPC locaux. Il est automatiquement affecté au système téléphonique dans les utilisateurs d’Office 365.
  
||**Utilisateur sur site**|**Système de téléphone dans Office 365 à l’utilisateur de connectivité RTPC sur site**|
|:-----|:-----|:-----|
|Fonctionnalités d’appel définies dans  <br/> |Stratégie vocale  <br/> |Prédéfinis stratégie voice, affectée automatiquement lorsque l’utilisateur est concédé sous licence pour le système téléphonique dans Office 365.  <br/> |
|Enregistrements d’utilisation RTC associés à  <br/> |Stratégie vocale  <br/> |Stratégie de routage des communications vocales, affectée alors que l’utilisateur est encore hébergé en local.  <br/> |
   
Vous effectuez les opérations suivantes à l’aide de votre déploiement sur site, tandis que l’utilisateur est toujours hébergée dans le déploiement sur site.
  
## <a name="using-a-global-voice-routing-policy"></a>Utilisation d’une stratégie globale de routage des communications vocales

Avant d’utiliser une stratégie de routage voix global pour votre système téléphonique dans Office 365 avec des utilisateurs de connectivité RTPC sur site, vous devez ajouter des enregistrements d’utilisation de TLS à la stratégie.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>Pour affecter des enregistrements d’utilisation RTC à la stratégie globale de routage des communications vocales

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. Ajoutez les enregistrements d’utilisation de TLS pour la stratégie :
    
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
  
Pour plus d’informations sur les stratégies de routage voix, consultez [créer ou modifier une stratégie de voix et configurer les enregistrements d’utilisation de TLS dans Skype pour entreprise 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [Nouvelle-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)et [CsVoicePolicy de la subvention](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).
  


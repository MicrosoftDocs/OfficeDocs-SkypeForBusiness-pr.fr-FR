---
title: Affecter une stratégie de routage des communications vocales
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Résumé : consultez cette rubrique pour savoir comment attribuer une stratégie de voix pour les utilisateurs utilisant un système téléphonique avec une connectivité RTC locale.'
ms.openlocfilehash: 5d56d4f88e30b605276296b35cd9f316348342ca
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359320"
---
# <a name="assign-a-voice-routing-policy"></a>Affecter une stratégie de routage des communications vocales
 
> [!Important]
> Skype entreprise Online sera supprimé le 31 juillet 2021 après lequel le service ne sera plus accessible.  De plus, la connectivité PSTN entre votre environnement local, que ce soit via Skype entreprise Server ou Cloud Connector Edition et Skype entreprise Online, ne sera plus prise en charge.  Découvrez comment connecter votre réseau téléphonique local à teams à l’aide du [routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

**Résumé :** Lisez cette rubrique pour découvrir comment attribuer une stratégie de voix pour les utilisateurs utilisant un système téléphonique avec une connectivité RTC locale. 
  
Une fois qu’un utilisateur est sur Skype entreprise Online et qu’il utilise un système téléphonique avec une connectivité RTC locale, deux stratégies de voix s’appliquent à celles-ci. L’une est une stratégie de routage des communications vocales locale que vous allez attribuer sur site. Cette stratégie peut être globale ou spécifique à l’utilisateur et définit les enregistrements d’utilisation PSTN associés à l’utilisateur. Cette rubrique explique comment affecter cette stratégie.
  
Les autres stratégies de voix définissent les fonctionnalités d’appel disponibles pour l’utilisateur ; Cette stratégie de voix est définie par Microsoft et est identique pour tous les systèmes téléphoniques avec des utilisateurs de connectivité RTC locale. Il est automatiquement attribué aux utilisateurs du système téléphonique.
  
||**Utilisateur sur site**|**Système téléphonique avec utilisateur de connectivité RTC sur site**|
|:-----|:-----|:-----|
|Fonctionnalités d’appel définies dans  <br/> |Stratégie de la voix  <br/> |Stratégie de voix prédéfinie, attribuée automatiquement lorsque l’utilisateur dispose d’une licence pour le système téléphonique.  <br/> |
|Enregistrements d’utilisation RTC associés à  <br/> |Stratégie de la voix  <br/> |Stratégie de routage des communications vocales, affectée pendant que l’utilisateur est toujours hébergé en local.  <br/> |
   
Vous effectuez les étapes suivantes à l’aide de votre déploiement local, tandis que l’utilisateur est toujours hébergé dans le déploiement local.
  
## <a name="using-a-global-voice-routing-policy"></a>Utilisation d’une stratégie de routage des communications vocales globale

Avant d’utiliser une stratégie globale de routage des communications vocales pour votre système téléphonique avec des utilisateurs de connectivité RTC sur site, vous devez ajouter des enregistrements d’utilisation PSTN à la stratégie.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>Pour affecter des enregistrements d’utilisation PSTN à la stratégie globale de routage des communications vocales

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise 2015**, puis sur **Skype entreprise Server Management Shell**.
    
3. Ajoutez les enregistrements d’utilisation RTC à la stratégie :
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    Par exemple :
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>Création d’une stratégie de routage des communications vocales

### <a name="to-create-a-new-voice-routing-policy"></a>Pour créer une stratégie de routage des communications vocales

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise 2015**, puis sur **Skype entreprise Server Management Shell**.
    
3. Créez une stratégie de routage des communications vocales :
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    Par exemple :
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

Cet exemple crée une stratégie de routage des communications vocales appelée HybridVoice, qui a deux utilisations RTC associées.
  
## <a name="assigning-a-voice-routing-policy"></a>Affectation d’une stratégie de routage des communications vocales

Quelle que soit l’utilisation de la stratégie globale de routage des communications vocales ou de l’utilisateur, procédez comme suit pour affecter la stratégie à un utilisateur.
  
### <a name="to-assign-the-voice-routing-policy"></a>Pour affecter la stratégie de routage des communications vocales

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise 2015**, puis sur **Skype entreprise Server Management Shell**.
    
3. Affecter une stratégie de voix existante à un utilisateur :
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Par exemple :
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

Dans cet exemple, l’utilisateur portant le nom d’affichage Bob Kelly est affecté à la stratégie de voix précédemment créée avec le nom HybridVoice.
  
Pour plus d’informations sur les stratégies de routage des communications vocales, voir [Create or Modify a Voice Policy and configure PSTN usage Records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)et [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).
  


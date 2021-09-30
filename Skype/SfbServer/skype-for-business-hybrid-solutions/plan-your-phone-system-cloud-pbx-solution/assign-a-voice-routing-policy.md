---
title: Affecter une stratégie de routage des voix
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
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Résumé : Lisez cette rubrique pour découvrir comment affecter une stratégie de voix pour les utilisateurs qui utilisent Système téléphonique avec une connectivité PSTN sur site.'
ms.openlocfilehash: aa31624921aefd1065b0719966af1df9d2b38793
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013168"
---
# <a name="assign-a-voice-routing-policy"></a>Affecter une stratégie de routage des voix
 
> [!Important]
> Skype Entreprise Online sera retiré le 31 juillet 2021, après quoi le service ne sera plus accessible.  En outre, la connectivité PSTN entre votre environnement local via Skype Entreprise Server ou Cloud Connector Edition et Skype Entreprise Online ne sera plus prise en charge.  Découvrez comment connecter votre réseau téléphonique local à Teams l’aide du [routage direct.](/MicrosoftTeams/direct-routing-landing-page)

**Résumé :** Lisez cette rubrique pour découvrir comment affecter une stratégie de voix pour les utilisateurs qui utilisent Système téléphonique avec une connectivité PSTN sur site. 
  
Lorsqu’un utilisateur est sur Skype Entreprise Online et utilise Système téléphonique avec une connectivité PSTN sur site, deux stratégies de voix s’appliquent à lui. L’une d’entre elle est une stratégie de routage des voix sur site que vous allez affecter en local. Cette stratégie peut être spécifique à l’utilisateur ou globale et définit les enregistrements d’utilisation PSTN associés à l’utilisateur. Cette rubrique explique comment affecter cette stratégie.
  
L’autre stratégie de voix définit les fonctionnalités d’appel disponibles pour l’utilisateur . Cette stratégie de voix est définie par Microsoft et est identique pour tous les Système téléphonique avec des utilisateurs de connectivité PSTN locaux. Il est automatiquement attribué aux utilisateurs Système téléphonique utilisateurs.
  
|&nbsp;|Utilisateur local|Système téléphonique avec un utilisateur de connectivité PSTN local|
|:-----|:-----|:-----|
|Fonctionnalités d’appel définies dans   |Stratégie de la voix   |Stratégie de voix prédéfinée, attribuée automatiquement lorsque l’utilisateur est titulaire d’une licence Système téléphonique.   |
|Enregistrements d’utilisation PSTN associés à   |Stratégie de la voix   |Stratégie de routage des voix, attribuée alors que l’utilisateur est toujours en local.   |
   
Vous effectuez les étapes suivantes à l’aide de votre déploiement local, tandis que l’utilisateur est toujours homed dans le déploiement local.
  
## <a name="using-a-global-voice-routing-policy"></a>Utilisation d’une stratégie globale de routage des voix

Avant d’utiliser une stratégie de routage des voix globale pour votre Système téléphonique avec des utilisateurs de connectivité PSTN locaux, vous devez ajouter des enregistrements d’utilisation PSTN à la stratégie.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>Pour affecter des enregistrements d’utilisation PSTN à la stratégie globale de routage des voix

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
3. Ajoutez les enregistrements d’utilisation PSTN à la stratégie :
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    Par exemple :
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>Création d’une stratégie de routage des voix

### <a name="to-create-a-new-voice-routing-policy"></a>Pour créer une stratégie de routage des voix

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
3. Créez une stratégie de routage des voix :
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    Par exemple :
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

Cet exemple crée une stratégie de routage des voix appelée HybridVoice, qui est associée à deux utilisations PSTN.
  
## <a name="assigning-a-voice-routing-policy"></a>Affectation d’une stratégie de routage des voix

Que vous utilisiez la stratégie globale de routage des voix ou des stratégies spécifiques à l’utilisateur, utilisez les étapes suivantes pour affecter la stratégie à un utilisateur.
  
### <a name="to-assign-the-voice-routing-policy"></a>Pour affecter la stratégie de routage des voix

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
3. Affectez une stratégie de voix existante à un utilisateur :
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Par exemple :
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

Dans cet exemple, l’utilisateur avec le nom complet Bob Kelly est affecté à la stratégie de voix créée précédemment avec le nom HybridVoice.
  
Pour plus d’informations sur les stratégies de routage des voix, voir Créer ou modifier une stratégie de voix et configurer les enregistrements d’utilisation [PSTN dans Skype Entreprise 2015,](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy)et [Grant-CsVoicePolicy](/powershell/module/skype/grant-csvoicepolicy).

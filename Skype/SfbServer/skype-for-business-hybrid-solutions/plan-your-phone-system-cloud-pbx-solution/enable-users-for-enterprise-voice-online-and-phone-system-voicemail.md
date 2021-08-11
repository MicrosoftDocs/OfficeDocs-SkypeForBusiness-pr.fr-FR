---
title: Activation des utilisateurs pour la version en ligne de Voix Entreprise et de la messagerie vocale du Système téléphonique
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
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
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Découvrez comment activer Système téléphonique services vocaux pour vos Skype Entreprise utilisateurs.
ms.openlocfilehash: fea5da3bb82281c05edd73ce8e69c7164440513080b7aa804b31abc5d4c65ba7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289072"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a>Activation des utilisateurs pour la version en ligne de Voix Entreprise et de la messagerie vocale du Système téléphonique
 
> [!Important]
> Skype Entreprise Online sera retiré le 31 juillet 2021, après quoi le service ne sera plus accessible.  En outre, la connectivité PSTN entre votre environnement local via Skype Entreprise Server ou Cloud Connector Edition et Skype Entreprise Online ne sera plus prise en charge.  Découvrez comment connecter votre réseau téléphonique local à Teams l’aide du [routage direct.](/MicrosoftTeams/direct-routing-landing-page)

Découvrez comment activer Système téléphonique services vocaux pour vos Skype Entreprise utilisateurs.
  
La dernière étape du déploiement de Système téléphonique avec une connectivité PSTN sur site consiste à activer vos utilisateurs pour Système téléphonique messagerie vocale. Pour activer ces fonctionnalités, vous devez être un utilisateur avec le rôle Administrateur général et être en mesure d’exécuter PowerShell à distance. Vous devez suivre les étapes de cette rubrique pour tous les comptes d’utilisateurs pour Voix Entreprise activés pour Skype Entreprise Online.
  
## <a name="enable-phone-system-voice-services"></a>Activer Système téléphonique services vocaux

Pour activer un utilisateur pour Système téléphonique Voice et la messagerie vocale, vous devez effectuer certaines étapes initiales, comme vérifier si le connecteur Skype Entreprise Online est déployé sur vos serveurs et activer vos utilisateurs pour la messagerie vocale hébergée.
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a>Pour activer vos utilisateurs pour Système téléphonique messagerie vocale et vocale

> [!NOTE]
> Skype Entreprise Online Connector fait actuellement partie de la dernière version Teams module PowerShell.
> Si vous utilisez la dernière version publique [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.

1. Avant de commencer, vérifiez que le module Teams PowerShell est installé sur vos serveurs frontux. Si ce n’est pas le cas, installez-le en suivant les instructions [Teams’installation du module PowerShell.](/microsoftteams/teams-powershell-install)
    
2. Commencez Windows PowerShell en tant qu’administrateur.
    
3. Tapez ce qui suit et appuyez sur Entrée :
    
 ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

  
4. Utilisez la cmdlet Set-CsUser pour affecter les propriétés $EnterpriseVoiceEnabled et $HostedVoiceMail à votre utilisateur comme suit :
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    Par exemple :
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > Vous pouvez également spécifier un utilisateur par son adresse SIP, son nom d’utilisateur principal (UPN), son nom de domaine et son nom d’utilisateur (domaine \nom d’utilisateur) et son nom d’affichage dans Active Directory (« Bob Kelly »). 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a>Mettre à jour l’URI de ligne et le plan de numérotation pour les utilisateurs activés pour Système téléphonique

Cette section décrit comment mettre à jour l’URI de ligne et le plan de numérotation pour les utilisateurs activés pour Système téléphonique. 
  
### <a name="to-update-the-line-uri"></a>Pour mettre à jour l’URI de ligne

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2. Utilisez le raccourci menu Démarrer bureau ou de bureau pour ouvrir Skype Entreprise Server panneau de Skype Entreprise Server de contrôle.
    
    > [!NOTE]
    > Vous pouvez également ouvrir une fenêtre de navigateur, puis entrer l’URL de l’administrateur pour ouvrir Skype Entreprise Server panneau de contrôle. 
  
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.
    
5. Dans le tableau, cliquez sur le Skype Entreprise d’utilisateur dont vous souhaitez modifier l’URI de ligne.
    
6. Cliquez **sur URI** de ligne et tapez un numéro de téléphone unique et normal (par exemple, tel:+14255550200). Cliquez ensuite sur **Valider.**
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>Mettre à jour le plan de numérotation à l’aide d’Windows PowerShell cmdlets

Vous pouvez affecter des plans de numérotation par utilisateur Windows PowerShell et l’cmdlet [Grant-CsDialPlan.](/powershell/module/skype/grant-csdialplan?view=skype-ps) Vous pouvez exécuter cette cmdlet à partir de la Skype Entreprise Server 2015 ou d’une session distante de Windows PowerShell.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Pour affecter un plan de numérotation par utilisateur à un seul utilisateur

- Utilisez [l’cmdlet Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) pour affecter le plan de numérotation par utilisateur RedmondDialPlan à l’utilisateur Ken Myer :
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Pour affecter un plan de numérotation par utilisateur à plusieurs utilisateurs

- La commande suivante affecte le plan de numérotation par utilisateur RedmondDialPlan à tous les utilisateurs qui travaillent dans la ville de Redmond. Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, voir la documentation de l';cmdlet [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) :
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> Vous pouvez utiliser des plans de numérotation globaux ou utilisateur pour les utilisateurs en ligne. Les plans de numérotation de site ne peuvent pas être utilisés, car ils s’appliquent uniquement aux utilisateurs hébergés sur site et affectés à un site local. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>Pour désattribuer un plan de numérotation par utilisateur

- Utilisez [l’cmdlet Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) pour supprimer l’affectation d’un plan de numérotation par utilisateur précédemment affecté à Ken Myer. Une fois que le plan de numérotation par utilisateur n’est plus attribué, Ken Myer est automatiquement géré à l’aide du plan de numérotation global ou du plan de numérotation d’étendue service affecté à son bureau d’enregistrement ou à sa passerelle PSTN. Un plan de numérotation d’étendue service est prioritaire sur le plan de numérotation global :
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>Mettre à jour les stratégies de routage des voix à l’aide d’Windows PowerShell cmdlets sur site

Cette section décrit comment mettre à jour les stratégies de routage des voix pour les utilisateurs activés pour Système téléphonique.
  
Système téléphonique utilisateurs doivent avoir une stratégie de routage des voix qui leur est attribuée pour que les appels routent correctement. Cela diffère des utilisateurs de voix d’entreprise locaux qui requièrent qu’une stratégie de voix leur soit attribuée pour permettre aux appels d’être acheminés correctement. La stratégie de routage des voix doit contenir des utilisations PSTN qui définissent les appels et itinéraires autorisés pour Système téléphonique utilisateurs. Vous pouvez copier ces utilisations PSTN des stratégies de voix existantes vers les nouvelles stratégies de routage des voix. Pour plus d’informations, [voir New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).
  
> [!NOTE]
> Tous Système téléphonique utilisateurs se voit attribuer la même stratégie de voix en ligne nommée BusinessVoice qui définit les fonctionnalités d’appel autorisées . par exemple, Autoriser l’anneau simultané. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>Pour affecter une stratégie de routage des voix par utilisateur à un seul utilisateur

- Utilisez [l’cmdlet Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) pour affecter la stratégie de routage des voix par utilisateur RedmondVoiceRoutingPolicy à l’utilisateur Ken Myer :
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>Pour affecter une stratégie de routage des voix par utilisateur à plusieurs utilisateurs

- La commande suivante affecte la stratégie de routage des voix par utilisateur RedmondVoiceRoutingPolicy à tous les utilisateurs qui travaillent dans la ville de Redmond. Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, voir [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > Vous pouvez utiliser des stratégies de routage des voix globales ou utilisateur pour les utilisateurs en ligne. Les stratégies de routage des voix de site ne peuvent pas être utilisées, car elles s’appliquent uniquement aux utilisateurs hébergés sur site et affectés à un site local. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>Pour désattribuer une stratégie de routage des voix par utilisateur

- Utilisez la Grant-CsVoiceRoutingPolicy pour désattribuer une stratégie de routage des voix par utilisateur précédemment affectée à Ken Myer. Une fois la stratégie de routage des voix par utilisateur non résignée, Ken Myer est automatiquement géré à l’aide de la stratégie globale de routage des voix.
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    Pour plus d’informations, [voir Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).

---
title: Permettre aux utilisateurs de Voix Entreprise en ligne et le système téléphonique de messagerie vocale de Office 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Découvrez comment activer le système téléphonique dans les services de voix d’Office 365 pour votre Skype pour les utilisateurs professionnels.
ms.openlocfilehash: 72c3ea49394fd1b7d25b041a0f4423639753b523
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a>Permettre aux utilisateurs de Voix Entreprise en ligne et le système téléphonique de messagerie vocale de Office 365
 
Découvrez comment activer le système téléphonique dans les services de voix d’Office 365 pour votre Skype pour les utilisateurs professionnels.
  
La dernière étape de déploiement de système téléphonique dans Office 365 avec la connectivité RTPC sur site est de permettre à vos utilisateurs de système téléphonique dans Office 365 et de la messagerie vocale. Pour activer ces fonctionnalités, vous devez disposer du rôle d’administrateur global Office 365, puis exécuter une session PowerShell distante. Vous devez suivre la procédure présentée dans cette rubrique pour les comptes d’utilisateur pour lesquels la fonctionnalité Voix Entreprise n’est pas activée dans Skype Entreprise Online.
  
## <a name="enable-phone-system-in-office-365-voice-services"></a>Activer le système téléphonique de services de téléphonie Office 365

Pour activer un utilisateur pour système de téléphone dans Office 365 vocale et la messagerie vocale, vous devez exécuter certaines étapes initiales, comme la vérification de la Skype pour Business en ligne Connector est déployé sur vos serveurs et permettre à vos utilisateurs pour la messagerie vocale hébergé.
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a>Pour permettre à vos utilisateurs pour le système téléphonique de messagerie vocale et vocale d’Office 365

1. Avant de commencer, vérifiez que le Skype pour connecteur de Business Online (module de Windows PowerShell) est déployée sur vos serveurs frontaux. S’il n’est pas le cas, vous pouvez le télécharger à partir [du centre de téléchargement](https://www.microsoft.com/en-us/download/details.aspx?id=39366). Vous trouverez plus d’informations sur l’utilisation de ce module au niveau de la [configuration de votre ordinateur pour Skype pour la gestion d’entreprise en ligne](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).
    
2. Démarrez Windows PowerShell en tant qu’administrateur.
    
3. Tapez la commande ci-dessous, puis appuyez sur Entrée :
    
  ```
  Import-Module skypeonlineconnector
  ```

4. Tapez la commande ci-dessous, puis appuyez sur Entrée :
    
  ```
  $cred = Get-Credential
  ```

    Lorsque vous appuyez sur Entrée, la boîte de dialogue d’informations d’identification Windows PowerShell s’affiche.
    
5. Tapez votre nom d’utilisateur et votre mot de passe d’administrateur des clients, puis cliquez sur **OK**.
    
6. Dans la fenêtre PowerShell, tapez la commande ci-dessous, puis appuyez sur Entrée :
    
  ```
  $Session = New-CsOnlineSession -Credential $cred -Verbose
  ```

7. Importez la session en tapant l’applet de commande suivante :
    
  ```
  Import-PSSession $Session -AllowClobber
  ```

    Lors de l’exécution de PowerShell sur un Skype pour Business Server, le local Skype pour les applets de commande entreprise sont déjà chargés lors de l’ouverture de PowerShell. Vous devez spécifier le paramètre - AllowClobber pour autoriser les applets de commande en ligne remplacer les applets de commande locale portant le même nom.
    
8. Utilisez l’applet de commande Set-CsUser pour affecter les propriétés $EnterpriseVoiceEnabled et $HostedVoiceMail à votre utilisateur comme suit :
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
  ```

    Par exemple :
    
  ```
  Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
  ```

    > [!NOTE]
    > Vous pouvez également spécifier un utilisateur par son adresse SIP, nom d’utilisateur principal (UPN), nom de domaine et nom d’utilisateur (domaine\nom d’utilisateur) et le nom d’affichage dans Active Directory (« Bob Kelly »). 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a>Mise à jour de l’URI de la ligne et numérotation de plan pour les utilisateurs activés pour système de téléphone dans Office 365

Cette section décrit comment mettre à jour de l’URI de la ligne et numérotation de plan pour les utilisateurs activés pour système de téléphone dans Office 365. 
  
### <a name="to-update-the-line-uri"></a>Pour mettre à jour l’URI de ligne

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Utilisez le menu Démarrer ou le raccourci bureau pour ouvrir le Panneau de configuration de Skype Entreprise Server.
    
    > [!NOTE]
    > Vous pouvez également ouvrir une fenêtre de navigateur, puis saisir l’URL de l’administrateur pour ouvrir le Panneau de configuration de Skype Entreprise Server 
  
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur à activer, puis cliquez sur **Rechercher**.
    
5. Dans le tableau, cliquez sur le compte d’utilisateur de Skype Entreprise dont vous souhaitez modifier l’URI de ligne.
    
6. Cliquez sur l’**URI de ligne**, puis saisissez un numéro de téléphone normalisé unique (par exemple, tél :+14255550200). Ensuite, cliquez sur **Valider**.
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>Mise à jour du plan de numérotation à l’aide d’applets de commande Windows PowerShell locales

Vous pouvez affecter par utilisateur avec Windows PowerShell et l’applet de commande de [CsDialPlan de la subvention](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) , les plans de numérotation. Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server 2015, ou à partir d’une session à distance de Windows PowerShell.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Pour affecter un plan de numérotation par utilisateur à un seul utilisateur

- Pour affecter le plan de numérotation RedmondDialPlan par l’utilisateur pour l’utilisateur Ken Myer, utilisez l’applet de commande [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) :
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Pour affecter un plan de numérotation par utilisateur à plusieurs utilisateurs

- La commande suivante affecte le plan de numérotation par utilisateur RedmondDialPlan à tous les utilisateurs qui travaillent dans la ville de Redmond. Pour plus d’informations sur le paramètre FiltreLDAP utilisé dans cette commande, consultez la documentation de l’applet de commande [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

  ```

> [!NOTE]
> Vous pouvez utiliser les plans de numérotation de l’utilisateur ou globaux pour les utilisateurs en ligne. Les plans de numérotation du site ne peuvent pas être utilisés, car ils s’appliquent uniquement aux utilisateurs hébergés localement et affectés à un site local. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>Pour annuler l’affectation d’un plan de numérotation par utilisateur

- Pour annuler l’affectation de tout plan de numérotation par utilisateur précédemment affecté à Ken Myer, utilisez l’applet de commande [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) . Une fois l’affectation du plan de numérotation par utilisateur annulée, Ken Myer sera géré automatiquement à l’aide du plan de numérotation global ou du plan de numérotation à l’échelle du service affecté à son serveur d’inscriptions ou à sa passerelle PSTN. Un plan de numérotation à l’échelle du service est prioritaire par rapport à tout plan de numérotation global.
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>Mise à jour des stratégies de routage des communications vocales à l’aide d’applets de commande locales Windows PowerShell

Cette section décrit comment mettre à jour les stratégies de routage voix pour les utilisateurs de système téléphonique dans Office 365.
  
Système de téléphone dans Office 365 utilisateurs doit avoir une stratégie de routage voix qui leur sont affectées pour router correctement les appels. Cette affectation diffère de l’affectation d’une stratégie de voix aux utilisateurs professionnels de communications vocales, également nécessaire pour que les appels soient acheminés correctement. La stratégie de routage voix doit contenir les utilisations RTPC qui définissent des appels autorisés et des itinéraires pour le système téléphonique dans les utilisateurs d’Office 365. Vous pouvez copier les utilisations PSTN des stratégies de voix existantes pour les nouvelles stratégies de routage des communications vocales. Pour plus d’informations, consultez [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).
  
> [!NOTE]
> Système de téléphone tous les utilisateurs d’Office 365 sont affectés à la même stratégie de voix en ligne nommé BusinessVoice qui définit les fonctionnalités d’appel autorisées ; par exemple, autoriser la sonnerie simultanée. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>Pour affecter une stratégie de routage des communications vocales par utilisateur à un seul utilisateur

- Pour affecter la stratégie de routage RedmondVoiceRoutingPolicy voix par utilisateur à l’utilisateur Ken Myer, utilisez l’applet de commande [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) :
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>Pour affecter une stratégie de routage des communications vocales par utilisateur à plusieurs utilisateurs

- La commande suivante affecte la stratégie de routage des communications vocales par utilisateur RedmondVoiceRoutingPolicy à tous les utilisateurs travaillant dans la ville de Redmond. Pour plus d’informations sur le paramètre FiltreLDAP utilisé dans cette commande, reportez-vous à la section [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > Vous pouvez utiliser les stratégies de routage des communications vocales de l’utilisateur ou globales pour les utilisateurs en ligne. Les stratégies de routage des communications vocales du site ne peuvent pas être utilisées, car elles s’appliquent uniquement aux utilisateurs hébergés localement et affectés à un site local. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>Pour annuler l’affectation d’une stratégie de routage des communications vocales par utilisateur

- La subvention-CsVoiceRoutingPolicy permet de supprimer l’attribution d’une stratégie de routage voix par utilisateur précédemment affectée à Ken Myer. Une fois l’affectation de la stratégie de routage des communications vocales par utilisateur annulée, Ken Myer sera automatiquement géré à l’aide de la stratégie globale de routage des communications vocales.
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    Pour plus d’informations, consultez [Attribution-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).
    


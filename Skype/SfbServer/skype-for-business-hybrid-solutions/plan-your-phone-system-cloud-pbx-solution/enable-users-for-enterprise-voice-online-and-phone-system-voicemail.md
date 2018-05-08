---
title: Activer les utilisateurs pour Enterprise Voice en ligne et le système téléphonique dans la messagerie Office 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
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
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Découvrez comment activer le système téléphonique dans les services de téléphonie Office 365 pour votre Skype pour les utilisateurs professionnels.
ms.openlocfilehash: 1810be3f891e1f66e724133732ed16e94a1d8015
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a>Activer les utilisateurs pour Enterprise Voice en ligne et le système téléphonique dans la messagerie Office 365
 
Découvrez comment activer le système téléphonique dans les services de téléphonie Office 365 pour votre Skype pour les utilisateurs professionnels.
  
La dernière étape de déploiement système téléphonique dans Office 365 avec une connectivité PSTN local doit permettre à vos utilisateurs pour le système téléphonique dans Office 365 et de la messagerie vocale. Pour activer ces fonctionnalités, vous devez disposer du rôle d’administrateur global Office 365, puis exécuter une session PowerShell distante. Vous devez suivre la procédure présentée dans cette rubrique pour les comptes d’utilisateur pour lesquels la fonctionnalité Voix Entreprise n’est pas activée dans Skype Entreprise Online.
  
## <a name="enable-phone-system-in-office-365-voice-services"></a>Activer le système téléphonique dans les services de téléphonie Office 365

Pour activer un utilisateur pour le système téléphonique dans Office 365 Voice et de la messagerie vocale, vous devez effectuer certaines étapes initiales, comme la vérification de voir de la Skype pour Business Connector en ligne est déployé sur vos serveurs et de permettre à vos utilisateurs pour la messagerie vocale hébergée.
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a>Pour autoriser les utilisateurs pour le système téléphonique dans la messagerie vocale et vocale d’Office 365

1. Avant de commencer, vérifiez que le Skype pour Business Connector en ligne (module Windows PowerShell) est déployée sur vos serveurs frontaux. S’il n’est pas le cas, vous pouvez le télécharger à partir [du centre de téléchargement](https://www.microsoft.com/en-us/download/details.aspx?id=39366). Vous trouverez plus d’informations sur l’utilisation de ce module sur la [configuration de votre ordinateur pour Skype pour la gestion de l’entreprise en ligne](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).
    
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

    Lors de l’exécution de PowerShell sur un Skype pour Business Server, le Skype local pour les applets de commande Business sont déjà chargés lorsque vous ouvrez PowerShell. Vous devez spécifier le paramètre - AllowClobber pour autoriser les applets de commande en ligne remplacer les applets de commande locale portant le même nom.
    
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
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a>Mettre à jour de l’URI de ligne et de numérotation de plan pour les utilisateurs activés pour le système téléphonique dans Office 365

Cette section décrit comment mettre à jour l’URI de ligne et de numérotation de plan pour les utilisateurs activés pour le système téléphonique dans Office 365. 
  
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

Plans de numérotation avec Windows PowerShell et l’applet de commande [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) , vous pouvez assigner par utilisateur. Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server 2015 ou d’une session à distance de Windows PowerShell.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Pour affecter un plan de numérotation par utilisateur à un seul utilisateur

- Utilisez l’applet de commande [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) pour affecter le plan de numérotation par utilisateur RedmondDialPlan à l’utilisateur Ken Myer :
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Pour affecter un plan de numérotation par utilisateur à plusieurs utilisateurs

- La commande suivante affecte le plan de numérotation par utilisateur RedmondDialPlan à tous les utilisateurs qui travaillent dans la ville de Redmond. Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, voir la documentation de l’applet de commande [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

  ```

> [!NOTE]
> Vous pouvez utiliser les plans de numérotation de l’utilisateur ou globaux pour les utilisateurs en ligne. Les plans de numérotation du site ne peuvent pas être utilisés, car ils s’appliquent uniquement aux utilisateurs hébergés localement et affectés à un site local. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>Pour annuler l’affectation d’un plan de numérotation par utilisateur

- Utilisez l’applet de commande [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) pour annuler l’affectation d’un plan de numérotation par utilisateur préalablement attribuée à Ken Myer. Une fois l’affectation du plan de numérotation par utilisateur annulée, Ken Myer sera géré automatiquement à l’aide du plan de numérotation global ou du plan de numérotation à l’échelle du service affecté à son serveur d’inscriptions ou à sa passerelle PSTN. Un plan de numérotation à l’échelle du service est prioritaire par rapport à tout plan de numérotation global.
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>Mise à jour des stratégies de routage des communications vocales à l’aide d’applets de commande locales Windows PowerShell

Cette section décrit comment mettre à jour des stratégies de routage voix pour les utilisateurs activés pour le système téléphonique dans Office 365.
  
Système téléphonique dans la zone utilisateurs Office 365 doit avoir une stratégie de routage voix affectée pour acheminer correctement les appels. Cette affectation diffère de l’affectation d’une stratégie de voix aux utilisateurs professionnels de communications vocales, également nécessaire pour que les appels soient acheminés correctement. La stratégie de routage voix doit contenir les utilisations PSTN qui définissent des appels autorisés et les itinéraires pour le système téléphonique dans les utilisateurs d’Office 365. Vous pouvez copier les utilisations PSTN des stratégies de voix existantes pour les nouvelles stratégies de routage des communications vocales. Pour plus d’informations, voir [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).
  
> [!NOTE]
> Tous les système téléphonique dans Office 365 des utilisateurs sont affectés à la même stratégie de voix en ligne nommé BusinessVoice qui définit les fonctionnalités d’appel autorisées ; par exemple, autoriser la sonnerie simultanée. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>Pour affecter une stratégie de routage des communications vocales par utilisateur à un seul utilisateur

- Utilisez l’applet de commande [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) pour attribuer la stratégie de routage RedmondVoiceRoutingPolicy voix par utilisateur à l’utilisateur Ken Myer :
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>Pour affecter une stratégie de routage des communications vocales par utilisateur à plusieurs utilisateurs

- La commande suivante affecte la stratégie de routage des communications vocales par utilisateur RedmondVoiceRoutingPolicy à tous les utilisateurs travaillant dans la ville de Redmond. Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, voir [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > Vous pouvez utiliser les stratégies de routage des communications vocales de l’utilisateur ou globales pour les utilisateurs en ligne. Les stratégies de routage des communications vocales du site ne peuvent pas être utilisées, car elles s’appliquent uniquement aux utilisateurs hébergés localement et affectés à un site local. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>Pour annuler l’affectation d’une stratégie de routage des communications vocales par utilisateur

- Utilisez le Grant-CsVoiceRoutingPolicy pour annuler l’affectation de toute stratégie de routage voix par utilisateur préalablement attribuée à Ken Myer. Une fois l’affectation de la stratégie de routage des communications vocales par utilisateur annulée, Ken Myer sera automatiquement géré à l’aide de la stratégie globale de routage des communications vocales.
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    Pour plus d’informations, voir [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).
    


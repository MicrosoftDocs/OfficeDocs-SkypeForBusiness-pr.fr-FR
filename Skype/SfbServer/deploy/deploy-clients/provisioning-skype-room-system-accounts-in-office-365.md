---
title: Mise en service de comptes Skype Room System dans Microsoft 365 et Office 365
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Lisez cette rubrique pour en savoir plus sur la mise en service de comptes Skype Room System dans Microsoft 365 ou Office 365.
ms.openlocfilehash: 94390effb246a37745d797289c1146ed3d347604
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093518"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>Mise en service de comptes Skype Room System dans Microsoft 365 et Office 365
 
Lisez cette rubrique pour en savoir plus sur la mise en service de comptes Skype Room System dans Microsoft 365 ou Office 365.
  
La section suivante traite de la mise en service des comptes Skype Room System.
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Conditions préalables pour Microsoft 365 et Office 365

Votre client en ligne doit respecter les conditions suivantes :
  
- L’offre Microsoft 365 ou Office 365 doit inclure Skype Entreprise Online Plan 2 ou Office 365 E1, E3 ou E5. <br/>Pour plus d’informations sur les plans Skype Entreprise Online, voir la [description du service Skype Entreprise Online.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)
    
- La fonctionnalité de conférence de Skype Entreprise doit être activée pour votre client.
    
- Exchange Online doit être activé pour votre client. 
    
- Votre administrateur distant client doit avoir l’accès PowerShell suivant :
    
  - Accès à PowerShell à distance Exchange
    
  - Accès PowerShell à distance Skype Entreprise Online
    
  - Windows Azure module Active Directory pour Windows PowerShell accès à l’annuaire Microsoft 365 ou Office 365
    
Pour le compte Skype Room, les licences suivantes sont requises :
  
- Une licence Skype Entreprise Online Plan 2 ou Office 365 E1 ou E3 est nécessaire pour activer les réunions Skype.
    
- Pour activer la salle avec la fonctionnalité Voix Entreprise afin que la salle puisse être activée avec un numéro de téléphone, un plan Skype Entreprise Online 2 avec licence de système téléphonique ou Office 365 E5 est requis (1).
    
- Si vous avez besoin de fonctionnalités de numérotation à partir d’une réunion, vous aurez besoin d’une licence de système téléphonique et d’audioconférence.  Si vous avez besoin de fonctionnalités d’appel sortant à partir d’une réunion, vous aurez besoin d’un forfait d’appels national ou national et international. 
    
- Une licence Exchange Online n’est pas requise pour le compte Skype Room, car le compte doit être configuré en tant que compte de boîte aux lettres de ressources.
    
## <a name="provisioning-overview"></a>Vue d’ensemble de l’approvisionnement

Le diagramme suivant fournit une vue d’ensemble du flux de mise en service du compte Skype Room System.
  
![Étapes de mise en service de Skype Room System](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identifier une nouvelle salle de conférence

Vous disposez peut-être déjà d’une boîte aux lettres de salle de ressources dans Exchange qui fournit la fonctionnalité de planification, ou vous créez peut-être une boîte aux lettres de ressources pour la première fois pour faciliter le déploiement de Skype Room System. Dans tous les cas, vous devez identifier un compte de salle à utiliser dans votre client. Les sections Exchange Online Provision et Skype Entreprise Provision fournissent des conseils pour les deux types de comptes. Par exemple, supposons que vous disposez des deux salles suivantes et que vous souhaitez déployer Skype Room System pour les deux salles :
  
- Compte de boîte aux lettres de ressources existant : confrm1@contoso.onmicrosoft.com
    
- Nouveau compte de boîte aux lettres de ressources : confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Approvisionnement Exchange Online

Tout d’abord, connectez-vous à Exchange Online PowerShell en suivant les instructions de la rubrique, [Connectez-vous à Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
  
Pour définir un compte de boîte aux lettres de salle de ressources existant pour Skype Room System, exécutez les commandes suivantes dans Exchange Online PowerShell :
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Pour créer un compte de boîte aux lettres de ressources Exchange pour Skype Room System, exécutez les commandes suivantes dans Exchange Online PowerShell :
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Les commandes précédentes permettent de configurer ou de créer un compte de boîte aux lettres de ressources Exchange pour l’utilisation de Skype Room System en activant le compte.
  
Après avoir créé la boîte aux lettres, vous pouvez utiliser la cmdlet Set-CalendarProcessing dans Exchange Online PowerShell pour configurer la boîte aux lettres. Pour plus d’informations, reportez-vous aux étapes 3 à 6 sous Déploiements locaux à forêt unique

## <a name="assigning-a-skype-for-business-online-license"></a>Attribution d’une licence Skype Entreprise Online

Vous pouvez maintenant attribuer une licence Skype Entreprise Online (Plan 2) ou Skype Entreprise Online (Plan 3) à l’aide du portail d’administration Microsoft 365, comme décrit dans La procédure d’attribution ou de suppression de licences pour [Microsoft 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) entreprise ou dans la gestion des licences de modules [add-on Skype](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)Entreprise. 
  
Après avoir attribué une licence pour Skype Entreprise Online, vous pourrez vous connecter et vérifier que le compte est actif à l’aide de n’importe quel client Skype Entreprise.
  
## <a name="skype-for-business-online-provisioning"></a>Mise en service de Skype Entreprise Online

Une fois qu’un compte de boîte aux lettres de salle de ressources a été créé et activé comme indiqué précédemment, et que vous avez sous licence le compte pour Skype Entreprise Online, le compte sera synchronisé à partir de la forêt Exchange Online avec la forêt Skype Entreprise Online à l’aide de la forêt Active Directory Windows Azure. Les étapes suivantes sont nécessaires pour mettre en service le compte Skype Room System dans le pool Skype Entreprise Online. Ces étapes sont les mêmes pour un compte de boîte aux lettres de ressources existant ou un compte nouvellement créé (confrm1 ou confrm2), car une fois qu’ils sont activés dans Exchange Online, ces deux comptes sont synchronisés avec Skype Entreprise Online de la même manière :
  
1. Créez une session PowerShell distante. Notez que vous devrez télécharger le [module PowerShell Teams.](/microsoftteams/teams-powershell-install)
    
  ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
  ```

2. Pour activer un compte Skype Room System pour Skype Entreprise, exécutez la commande suivante :
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Vous pouvez obtenir l’adresse RegistrarPool dans laquelle vos utilisateurs Skype Entreprise sont élevés à partir de l’un de vos comptes existants à l’aide de la commande suivante pour retourner cette propriété :
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>L’authentification multifacteur (MFA) n’est pas prise en charge pour les comptes Skype Room System. 

## <a name="password-expiration"></a>Expiration du mot de passe

Dans Microsoft 365 ou Office 365, la stratégie d’expiration de mot de passe par défaut pour tous vos comptes d’utilisateurs est de 90 jours, sauf si vous configurez une stratégie d’expiration de mot de passe différente. Pour les comptes Skype Room System, vous pouvez sélectionner le paramètre Mot de passe n’expire jamais en suivant les étapes ci-après.
  
1. Créez une session Active Directory Windows Azure à l’aide de vos informations d’identification d’administrateur général client.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Définissez le paramètre Mot de passe n’expire jamais pour le compte de salle Skype Room System créé précédemment à l’aide de la commande suivante :
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Pour plus d’informations, voir [Configurer votre ordinateur pour Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="validate"></a>Valider

Pour la validation, vous devez être en mesure d’utiliser n’importe quel client Skype Entreprise pour vous inscrire au compte que vous avez créé.
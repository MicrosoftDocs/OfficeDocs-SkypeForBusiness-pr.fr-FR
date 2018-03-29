---
title: Mise en service de comptes Skype Room System dans Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Consultez cette rubrique pour en savoir plus sur la mise en service de comptes Skype Room System dans Office 365.
ms.openlocfilehash: be90831eba5f16f5a3b41f4c74c26333bf728926
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a>Mise en service de comptes Skype Room System dans Office 365
 
Consultez cette rubrique pour en savoir plus sur la mise en service de comptes Skype Room System dans Office 365.
  
La section suivante décrit le compte système local de Skype mise en service d’un client Office 365.
  
## <a name="office-365-prerequisites"></a>Conditions préalables Office 365

Votre client en ligne doit répondre aux conditions suivantes :
  
- Le plan d’Office 365 doit inclure Skype pour Business en ligne Plan 2, Plan 3, Office 365 E1, E3 ou E5.
    
- Votre client doit avoir la capacité de la conférence de Skype pour entreprise activé.
    
- Votre client doit avoir Exchange Online activé. 
    
- Votre administrateur client distant doit avoir les accès PowerShell suivants :
    
  - Accès PowerShell distant Exchange
    
  - Skype pour accès de PowerShell distant de professionnels en ligne
    
  - Windows Azure Active Directory Module pour Windows PowerShell pour l’accès à l’annuaire accès Office 365
    
Pour le compte Skype Room, la licence suivante est requise :
  
- Un Skype pour Business Plan en ligne de 2 ou Office 365 E1 ou E3 licence est nécessaire pour permettre de réunions Skype.
    
- Autorisant la pièce avec la fonctionnalité Voix Entreprise afin que la pièce peut être activée avec un numéro de téléphone, un Skype pour entreprise en ligne Plan 2 avec le module complémentaire de nuage PBX ou Office 365 E5 est requise (1).
    
- La disponibilité du droit à la conférence RTC dans une réunion donnée est déterminée par la licence de l’organisateur de la réunion.
    
- Une licence Exchange Online n’est pas requise pour le compte Skype Room car le compte doit être configuré comme un compte de boîte aux lettres de ressource.
    
## <a name="provisioning-overview"></a>Vue d’ensemble de la mise en service

Le diagramme suivant fournit une vue d’ensemble du compte système local de Skype mise en service de flux dans Office 365.
  
![Procédures de déploiement de Skype Room System pour Office 365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identifier une nouvelle salle de conférence

Vous disposez peut-être déjà une boîte aux lettres de salle de ressources Exchange qui fournit la fonctionnalité de planification, ou vous pouvez créer une boîte aux lettres de ressources pour la première fois afin de faciliter le déploiement d’un système de salle de Skype. Dans tous les cas, vous devez identifier un compte de salle à utiliser dans votre client. La fourniture en ligne d’Exchange et Skype pour les sections de la disposition de l’entreprise fournissent des instructions pour les deux types de comptes. Par exemple, supposons que vous avez deux pièces suivants, et que vous souhaitez déployer le système d’espace Skype pour les deux :
  
- Compte de boîte aux lettres de ressources existant : confrm1@contoso.onmicrosoft.com
    
- Nouveau compte de boîte aux lettres de ressources : confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Mise en service d’Exchange Online

Tout d’abord se connecter à Exchange Online PowerShell en suivant les instructions de la rubrique, [se connecter à Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
  
Pour définir un compte de boîte aux lettres de salle ressource existant pour système de salle Skype, exécutez les commandes suivantes dans Exchange Online PowerShell :
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Pour créer un nouveau compte de boîte aux lettres de ressources Exchange pour système de salle Skype, exécutez les commandes suivantes dans Exchange Online PowerShell :
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Les commandes précédentes définir ou créer un nouveau compte de boîte aux lettres de ressources Exchange pour l’utilisation du système de salle de Skype en activant le compte.
  
Après avoir créé la boîte aux lettres, vous pouvez utiliser l’applet de commande Set-CalendarProcessing dans Exchange Online PowerShell pour configurer la boîte aux lettres. Reportez-vous aux étapes 3 à 6 sous Déploiements locaux d’une forêt unique pour plus d’informations
  
## <a name="skype-for-business-online-provisioning"></a>Mise en service de Skype Entreprise Online

Une fois un compte de boîte aux lettres de salle de ressource a été créé et activé comme indiqué précédemment, le compte est synchronisées à partir de la forêt Exchange Online dans Skype pour Business Online de la forêt à l’aide de la forêt Active Directory de Windows Azure. Les étapes suivantes sont nécessaires pour mettre en service le compte système de salle de Skype dans le Skype pour le pool d’entreprise en ligne. Ces étapes sont les mêmes pour un compte de boîte aux lettres de ressources existant ou un compte nouvellement créé (confrm1 ou confrm2), étant donné que lorsqu’elles sont activées dans Exchange en ligne, les deux de ces comptes seront synchronisés avec Skype pour l’activité en ligne de la même manière :
  
1. Créez une session PowerShell distante. Notez que vous devrez télécharger Skype pour Module de connecteur Business en ligne et Assistant Microsoft Online Services Sign-In et vous assurer que votre ordinateur est configuré. Pour plus d’informations, consultez [Configuration de votre ordinateur pour la gestion de Lync Online](http://technet.microsoft.com/library/bca143e2-659a-4161-9220-59ffd9fc2874.aspx).
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Pour activer un compte système local de Skype pour Skype pour entreprise, exécutez la commande suivante :
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Vous pouvez obtenir le RegistrarPool renvoie de l’adresse où votre Skype pour les utilisateurs professionnels sont hébergés à partir d’un de vos comptes existants à l’aide de la commande suivante pour cette propriété :
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

## <a name="assigning-a-skype-for-business-online-license"></a>Attribution d’une licence Skype Entreprise Online

Après avoir activé un compte système local de Skype dans Skype pour les entreprises, vous pouvez affecter un Skype pour Business Online (Plan 2) ou Skype pour licence Business Online (Plan 3) à l’aide du portail d’administration d’Office 365, comme décrit dans [affecter ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) ou dans [Skype pour la licence de module complémentaire Business](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7). 
  
Après avoir attribué une licence pour Skype pour professionnels en ligne, vous serez en mesure de se connecter et valider que le compte est actif à l’aide de n’importe quel Skype pour client d’entreprise.
  
## <a name="password-expiration"></a>Expiration du mot de passe

Dans Office 365, la stratégie d’expiration du mot de passe par défaut pour tous vos comptes d’utilisateur est de 90 jours, sauf si vous configurez une stratégie différente d’expiration du mot de passe. Pour les comptes du système de salle de Skype, vous pouvez sélectionner le mot de passe n’expire jamais paramètre avec les étapes suivantes.
  
1. Créez une session Windows Azure Active Directory à l’aide de vos informations d’identification d’administrateur client global.
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Définir le mot de passe n’expire jamais paramètre pour le compte de salle Skype espace système créé précédemment à l’aide de la commande suivante :
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Pour plus d’informations, consultez [L’aide de Windows PowerShell pour gérer Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).
  


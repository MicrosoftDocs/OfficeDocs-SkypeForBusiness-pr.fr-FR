---
title: Mise en service de comptes Skype Room System dans Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Consultez cette rubrique pour en savoir plus sur la mise en service de comptes Skype Room System dans Office 365.
ms.openlocfilehash: 5df77e9a9e5e3ca67eb831596c12516457a15c45
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235064"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a>Mise en service de comptes Skype Room System dans Office 365
 
Consultez cette rubrique pour en savoir plus sur la mise en service de comptes Skype Room System dans Office 365.
  
La section suivante décrit la mise en service de compte dans le système de salle Skype pour un client Office 365.
  
## <a name="office-365-prerequisites"></a>Conditions préalables Office 365

Votre client en ligne doit répondre aux conditions suivantes :
  
- Le plan Office 365 doit inclure Skype entreprise Online plan 2 ou Office 365 E1, E3 ou E5. <br/>Pour plus d’informations sur les offres Skype entreprise Online, reportez-vous à la [Description du service Skype entreprise Online](https://technet.microsoft.com/library/jj822172.aspx).
    
- Votre client doit avoir activé la fonctionnalité de conférence de Skype entreprise.
    
- Votre client doit avoir Exchange Online activé. 
    
- Votre administrateur client distant doit avoir les accès PowerShell suivants :
    
  - Accès PowerShell distant Exchange
    
  - Accès PowerShell à distance de Skype entreprise Online
    
  - Module Windows Azure Active Directory pour Windows PowerShell permettant d’accéder à l’annuaire Office 365
    
Pour le compte Skype Room, la licence suivante est requise :
  
- Un plan 2 de Skype entreprise Online ou Office 365 E1 ou E3 est requis pour permettre la réunion Skype.
    
- Pour que vous puissiez faire titre de la pièce à l’aide de la fonctionnalité voix entreprise et permettre l’activation de la salle avec un numéro de téléphone, vous devez disposer de Skype entreprise Online plan 2 avec la licence du système téléphonique ou d’Office 365 E5 (1).
    
- Si vous avez besoin de fonctionnalités de connexion à une réunion, vous avez besoin d’une licence de système téléphonique et de téléconférence.  Si vous avez besoin de fonctionnalités de numérotation d’une réunion, vous aurez besoin d’un forfait d’appels nationaux ou internationaux. 
    
- Une licence Exchange Online n’est pas requise pour le compte Skype Room car le compte doit être configuré comme un compte de boîte aux lettres de ressource.
    
## <a name="provisioning-overview"></a>Vue d’ensemble de la mise en service

Le diagramme suivant fournit une vue d’ensemble du flux de configuration du compte système de salle Skype dans Office 365.
  
![Procédures de déploiement de Skype Room System pour Office 365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identifier une nouvelle salle de conférence

Il est possible que vous ayez déjà une boîte aux lettres de salle de ressources dans Exchange qui fournit la fonctionnalité de planification ou que vous deviez créer une boîte aux lettres de ressources pour faciliter le déploiement du système de salle Skype. Dans tous les cas, vous devez identifier un compte de salle à utiliser dans votre client. Les sections de configuration d’Exchange Online et de configuration de Skype entreprise fournissent des instructions pour les deux types de comptes. Par exemple, imaginons que vous ayez les deux pièces suivantes et que vous souhaitez déployer le système de salle Skype pour les deux:
  
- Compte de boîte aux lettres de ressources existant : confrm1@contoso.onmicrosoft.com
    
- Nouveau compte de boîte aux lettres de ressources : confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Mise en service d’Exchange Online

Tout d’abord, connectez-vous à Exchange Online PowerShell en suivant les instructions de la rubrique [connexion à Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
  
Pour définir un compte de boîte aux lettres de salle de ressources existant pour Skype Room System, exécutez les commandes suivantes dans Exchange Online PowerShell:
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Pour créer un compte de boîte aux lettres de ressources Exchange pour le système de salle Skype, exécutez les commandes suivantes dans Exchange Online PowerShell:
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Les commandes précédentes configurent ou créent un nouveau compte de boîte aux lettres de ressources Exchange pour l’utilisation du système de salle Skype en activant le compte.
  
Après la création de la boîte aux lettres, vous pouvez utiliser l’applet de connexion Set-CalendarProcessing dans Exchange Online PowerShell pour configurer la boîte aux lettres. Reportez-vous aux étapes 3 à 6 sous Déploiements locaux d’une forêt unique pour plus d’informations

## <a name="assigning-a-skype-for-business-online-license"></a>Attribution d’une licence Skype Entreprise Online

Vous pouvez désormais affecter une licence Skype entreprise Online (plan 2) ou Skype entreprise Online (plan 3) à l’aide du portail d’administration Office 365, comme décrit dans la section [attribuer ou supprimer des licences pour Office 365 entreprise](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) ou dans [le module complémentaire Skype entreprise. ](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)gestion des licences. 
  
Dès lors que vous attribuez une licence à Skype entreprise Online, vous pourrez vous connecter et vérifier que le compte est actif à l’aide de n’importe quel client Skype entreprise.
  
## <a name="skype-for-business-online-provisioning"></a>Mise en service de Skype Entreprise Online

Une fois qu’un compte de boîte aux lettres a été créé et activé comme indiqué précédemment et que vous disposez d’une licence pour Skype entreprise Online, le compte est synchronisé entre la forêt Exchange Online et la forêt Skype entreprise Online à l’aide de l’option Forêt Active Directory Windows Azure. Les étapes suivantes sont nécessaires pour approvisionner le compte de système de salle Skype dans la liste de Skype entreprise online. Ces étapes sont identiques pour un compte de boîte aux lettres de ressources existant ou un compte nouvellement créé (confrm1 ou confrm2), car une fois qu’ils sont activés dans Exchange Online, les deux comptes seront synchronisés avec Skype entreprise Online de la même façon:
  
1. Créez une session PowerShell distante. Notez que vous devrez télécharger le module Skype entreprise Online Connector et l’Assistant de connexion Microsoft Online Services pour vous assurer que votre ordinateur est configuré. Pour plus d’informations, voir [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Pour activer un compte système de salle Skype pour Skype entreprise, exécutez la commande suivante:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Vous pouvez obtenir l’adresse RegistrarPool dans laquelle les utilisateurs de Skype entreprise sont hébergés à partir de l’un de vos comptes existants en utilisant la commande suivante pour renvoyer cette propriété:
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a>Expiration du mot de passe

Dans Office 365, la stratégie d’expiration du mot de passe par défaut pour tous vos comptes d’utilisateur est de 90 jours, sauf si vous configurez une stratégie différente d’expiration du mot de passe. Pour les comptes de systèmes de salle Skype, vous pouvez sélectionner le paramètre le mot de passe n’expire jamais en procédant comme suit.
  
1. Créez une session Windows Azure Active Directory à l’aide de vos informations d’identification d’administrateur client global.
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Définissez le paramètre mot de passe n’expire jamais pour le compte de la salle de salle Skype créé précédemment en utilisant la commande suivante:
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Pour plus d’informations, voir [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
## <a name="validate"></a>Invalidé

Pour la validation, vous devriez être en mesure d’utiliser n’importe quel client Skype entreprise pour vous connecter au compte que vous avez créé.


---
title: Mise en service des comptes Skype Room System dans Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Consultez cette rubrique pour en savoir plus sur la mise en service des comptes Skype Room System dans Office 365.
ms.openlocfilehash: 141c833bcbdd744a7577c0762cb8ba55dd3d5c54
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037724"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a>Mise en service des comptes Skype Room System dans Office 365
 
Consultez cette rubrique pour en savoir plus sur la mise en service des comptes Skype Room System dans Office 365.
  
La section suivante traite de la mise en service des comptes Skype Room System pour un client Office 365.
  
## <a name="office-365-prerequisites"></a>Conditions préalables pour Office 365

Votre client en ligne doit remplir les conditions suivantes :
  
- Le plan Office 365 doit inclure Skype entreprise Online plan 2 ou Office 365 E1, E3 ou E5. <br/>Pour plus d’informations sur les offres Skype entreprise Online, voir la [Description du service Skype entreprise Online](https://technet.microsoft.com/library/jj822172.aspx).
    
- La fonctionnalité de conférence de Skype entreprise doit être activée pour votre client.
    
- Votre client doit avoir Exchange Online activé. 
    
- L’administrateur distant de votre client doit disposer de l’accès PowerShell suivant :
    
  - Accès à PowerShell à distance Exchange
    
  - Accès PowerShell à distance Skype entreprise Online
    
  - Module Windows Azure Active Directory pour Windows PowerShell pour accéder à l’accès à l’annuaire Office 365
    
Pour le compte Skype Room, la licence suivante est requise :
  
- Une licence Skype entreprise Online plan 2 ou Office 365 E1 ou E3 est requise pour activer les réunions Skype.
    
- Pour permettre à la salle de prendre en charge la fonctionnalité voix entreprise de sorte que la salle puisse être activée avec un numéro de téléphone, un site Skype entreprise Online plan 2 avec la licence du système téléphonique ou Office 365 E5 est requis (1).
    
- Si vous avez besoin de fonctionnalités de rendez-vous à partir d’une réunion, vous aurez besoin d’une licence d’audioconférence et de système téléphonique.  Si vous avez besoin de fonctionnalités d’appels sortants à partir d’une réunion, vous aurez besoin d’un forfait d’appels nationaux ou internationaux. 
    
- Une licence Exchange Online n’est pas requise pour le compte de la salle Skype car le compte doit être configuré en tant que compte de boîte aux lettres de ressources.
    
## <a name="provisioning-overview"></a>Vue d’ensemble de la mise en service

Le diagramme suivant fournit une vue d’ensemble du flux de mise en service du compte Skype Room System dans Office 365.
  
![Étapes de mise en service de Skype Room System pour O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identifier une nouvelle salle de conférence

Vous disposez peut-être déjà d’une boîte aux lettres de salle de ressources dans Exchange qui fournit la fonctionnalité de planification, ou vous pouvez créer une boîte aux lettres de ressources pour la première fois afin de faciliter le déploiement de Skype Room System. Dans tous les cas, vous devez identifier un compte de salle à utiliser dans votre client. Les sections Exchange Online provision and Skype for Business provision fournissent des conseils pour les deux types de comptes. Par exemple, supposons que vous disposez des deux salles suivantes et que vous souhaitez déployer Skype Room System pour les deux :
  
- Compte de boîte aux lettres de ressources existant : confrm1@contoso.onmicrosoft.com
    
- Nouveau compte de boîte aux lettres de ressources : confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Mise en service d’Exchange Online

Tout d’abord, connectez-vous à Exchange Online PowerShell en suivant les instructions de la rubrique, [Connectez-vous à Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
  
Pour définir un compte de boîte aux lettres de salle de ressources existant pour Skype Room System, exécutez les commandes suivantes dans Exchange Online PowerShell :
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Pour créer un nouveau compte de boîte aux lettres de ressource Exchange pour Skype Room System, exécutez les commandes suivantes dans Exchange Online PowerShell :
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Les commandes précédentes configurent ou créent un nouveau compte de boîte aux lettres de ressources Exchange pour l’utilisation de Skype Room System en activant le compte.
  
Après avoir créé la boîte aux lettres, vous pouvez utiliser la cmdlet Set-CalendarProcessing dans Exchange Online PowerShell pour configurer la boîte aux lettres. Reportez-vous aux étapes 3 à 6 sous déploiements locaux d’une forêt unique pour plus d’informations

## <a name="assigning-a-skype-for-business-online-license"></a>Affectation d’une licence Skype entreprise Online

À présent, vous pouvez attribuer une licence Skype entreprise Online (plan 2) ou Skype entreprise Online (plan 3) à l’aide du portail d’administration Office 365, comme décrit dans la rubrique [attribuer ou supprimer des licences pour office 365 pour les entreprises](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) ou dans les [licences de module complémentaire Skype entreprise](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7). 
  
Après avoir attribué une licence pour Skype entreprise Online, vous serez en mesure de vous connecter et de confirmer que le compte est actif à l’aide de n’importe quel client Skype entreprise.
  
## <a name="skype-for-business-online-provisioning"></a>Mise en service de Skype entreprise Online

Une fois qu’un compte de boîte aux lettres de salle de ressources a été créé et activé comme indiqué précédemment, et que vous disposez d’une licence pour le compte de Skype entreprise Online, le compte sera synchronisé entre la forêt Exchange Online et la forêt Skype entreprise Online à l’aide du Forêt Windows Azure Active Directory. Les étapes suivantes sont nécessaires pour mettre en service le compte Skype Room System dans le pool Skype entreprise online. Ces étapes sont les mêmes pour un compte de boîte aux lettres de ressource existant ou un compte nouvellement créé (confrm1 ou confrm2), car une fois qu’elles sont activées dans Exchange Online, ces deux comptes sont synchronisés avec Skype entreprise Online de la même manière :
  
1. Créez une session PowerShell distante. Notez que vous devrez télécharger le module du connecteur Skype entreprise Online et l’Assistant de connexion Microsoft Online Services et vous assurer que votre ordinateur est configuré. Pour plus d’informations, reportez-vous à [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Pour activer un compte Skype Room System pour Skype entreprise, exécutez la commande suivante :
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Vous pouvez obtenir l’adresse RegistrarPool où vos utilisateurs Skype entreprise sont hébergés à partir de l’un de vos comptes existants à l’aide de la commande suivante pour renvoyer cette propriété :
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>L’authentification multifacteur (MFA) n’est pas prise en charge pour les comptes Skype Room System. 

## <a name="password-expiration"></a>Expiration du mot de passe

Dans Office 365, la stratégie d’expiration de mot de passe par défaut pour tous vos comptes d’utilisateur est de 90 jours, sauf si vous configurez une stratégie d’expiration de mot de passe différente. Pour les comptes Skype Room System, vous pouvez sélectionner le paramètre le mot de passe n’expire jamais en suivant les étapes ci-dessous.
  
1. Créez une session Windows Azure Active Directory à l’aide de vos informations d’identification d’administrateur général de client.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Définissez le paramètre le mot de passe n’expire jamais pour le compte de la salle des salles Skype créé précédemment à l’aide de la commande suivante :
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Pour plus d’informations, reportez-vous à [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
## <a name="validate"></a>Valider

Pour la validation, vous devriez être en mesure d’utiliser n’importe quel client Skype entreprise pour vous connecter au compte que vous avez créé.


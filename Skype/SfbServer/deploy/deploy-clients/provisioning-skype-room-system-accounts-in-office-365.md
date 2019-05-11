---
title: Mise en service de comptes Skype Room System dans Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Consultez cette rubrique pour en savoir plus sur la mise en service de comptes Skype Room System dans Office 365.
ms.openlocfilehash: 658b5c29cd357bb8e7828b17f8722d5d017de24b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895248"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a>Mise en service de comptes Skype Room System dans Office 365
 
Consultez cette rubrique pour en savoir plus sur la mise en service de comptes Skype Room System dans Office 365.
  
La section suivante traite de compte Skype salle système de mise en service pour un client Office 365.
  
## <a name="office-365-prerequisites"></a>Conditions préalables Office 365

Votre client en ligne doit répondre aux conditions suivantes :
  
- Le plan Office 365 doit inclure Skype pour Business Online Plan 2, ou Office 365 E1, E3 ou E5. <br/>Pour plus d’informations sur Skype pour Business Online Plans, voir le [Skype pour Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).
    
- Votre client doit avoir la fonctionnalité de conférence de Skype pour les entreprises activé.
    
- Votre client doit avoir Exchange Online activé. 
    
- Votre administrateur client distant doit avoir les accès PowerShell suivants :
    
  - Accès PowerShell distant Exchange
    
  - Skype pour l’accès Business Online PowerShell à distance
    
  - Windows Azure Active Directory Module pour Windows PowerShell à l’accès à l’annuaire access Office 365
    
Pour le compte Skype Room, la licence suivante est requise :
  
- Un Skype pour Business Online Plan 2 ou Office 365 E1 ou E3 licence est nécessaire pour activer les réunions Skype.
    
- Autorisant la salle avec la fonctionnalité voix entreprise afin que la salle peut être activée avec un numéro de téléphone, un Skype pour Business Online Plan 2 avec la licence de système téléphonique ou Office 365 E5 est requise (1).
    
- Si vous avez besoin des fonctionnalités de rendez-vous à partir d’une réunion, vous devez une conférence audio et la licence du système téléphonique.  Si vous avez besoin des fonctionnalités d’appel sortant à partir d’une réunion, vous devez a internes ou nationales et internationales appelant Plan. 
    
- Une licence Exchange Online n’est pas requise pour le compte Skype Room car le compte doit être configuré comme un compte de boîte aux lettres de ressource.
    
## <a name="provisioning-overview"></a>Vue d’ensemble de la mise en service

Le diagramme suivant fournit une vue d’ensemble du compte Skype salle système mise en service des flux dans Office 365.
  
![Procédures de déploiement de Skype Room System pour Office 365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identifier une nouvelle salle de conférence

Est peut-être déjà une boîte aux lettres de salle de ressource dans Exchange qui fournit la fonctionnalité de planification, ou vous pouvez créer une boîte aux lettres de ressources pour la première fois faciliter le déploiement du système de salle Skype. Dans tous les cas, vous devez identifier un compte de salle à utiliser dans votre client. La mise en service en ligne Exchange et Skype pour les sections de la mise en service de l’entreprise fournissent des instructions pour les deux types de comptes. Par exemple, supposons que vous avez les deux locaux suivants, et vous souhaitez déployer salle Skype pour chacun d'entre eux :
  
- Compte de boîte aux lettres de ressources existant : confrm1@contoso.onmicrosoft.com
    
- Nouveau compte de boîte aux lettres de ressources : confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Mise en service d’Exchange Online

Tout d’abord, connectez-vous à Exchange Online PowerShell en suivant les instructions fournies dans la rubrique, [se connecter à Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
  
Pour configurer un compte de boîte aux lettres de salle ressource existant pour Skype salle système, exécutez les commandes suivantes dans Exchange Online PowerShell :
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Pour créer un nouveau compte de boîte aux lettres de ressources Exchange pour Skype salle système, exécutez les commandes suivantes dans Exchange Online PowerShell :
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Les commandes précédentes définir ou créer un nouveau compte de boîte aux lettres de ressources Exchange pour l’utilisation du système de salle Skype à l’activation du compte.
  
Après avoir créé la boîte aux lettres, vous pouvez utiliser l’applet de commande Set-CalendarProcessing dans Exchange Online PowerShell pour configurer la boîte aux lettres. Reportez-vous aux étapes 3 à 6 sous Déploiements locaux d’une forêt unique pour plus d’informations

## <a name="assigning-a-skype-for-business-online-license"></a>Attribution d’une licence Skype Entreprise Online

Maintenant vous pouvez assigner un Skype pour Business Online (Plan 2) ou Skype licence entreprise Online (Plan 3) à l’aide du portail d’administration d’Office 365, comme décrit dans [affecter ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) ou [Skype pour le module complémentaire Business gestion des licences](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7). 
  
Après avoir attribué une licence pour Skype pour Business Online, vous serez en mesure de se connecter et vérifier que le compte est actif à l’aide de n’importe quel Skype pour client d’entreprise.
  
## <a name="skype-for-business-online-provisioning"></a>Mise en service de Skype Entreprise Online

Après une salle de ressource compte de boîte aux lettres a été créé et activé comme indiqué précédemment, et le compte d’avoir une licence pour Skype pour Business Online le compte seront synchronisées à partir de la forêt Exchange Online dans Skype pour la forêt Business Online à l’aide de la Forêt de Windows Azure Active Directory. Les étapes suivantes sont nécessaires pour mettre en service le compte de système de salle Skype dans le Skype pour le pool d’entreprise en ligne. Ces étapes sont les mêmes pour un compte de boîte aux lettres de ressources existant ou un compte nouvellement créé (confrm1 ou confrm2), car une fois qu’ils sont activés dans Exchange Online, les deux de ces comptes seront synchronisés avec Skype pour Business Online de la même manière :
  
1. Créez une session PowerShell distante. Notez que vous devrez télécharger Skype pour Module connecteur en ligne d’entreprise et Microsoft Online Services Assistant de connexion et assurez-vous que votre ordinateur est configuré. Pour plus d’informations, voir [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Pour activer un compte de système de salle Skype pour Skype pour les entreprises, exécutez la commande suivante :
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Vous pouvez obtenir RegistrarPool renvoie adresse où votre Skype pour les utilisateurs sont hébergés à partir d’un de vos comptes existants à l’aide de la commande suivante pour cette propriété :
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a>Expiration du mot de passe

Dans Office 365, la stratégie d’expiration du mot de passe par défaut pour tous vos comptes d’utilisateur est de 90 jours, sauf si vous configurez une stratégie différente d’expiration du mot de passe. Pour les comptes Skype salle système, vous pouvez sélectionner le mot de passe n’expire jamais paramètre avec les étapes suivantes.
  
1. Créez une session Windows Azure Active Directory à l’aide de vos informations d’identification d’administrateur client global.
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Définir le mot de passe n’expire jamais paramètre pour le compte de salle Skype salle système précédemment créé à l’aide de la commande suivante :
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Pour plus d’informations, voir [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
## <a name="validate"></a>Valider

Pour la validation, vous devez être en mesure d’utiliser n’importe quel Skype pour client d’entreprise pour vous connecter au compte que vous avez créé.


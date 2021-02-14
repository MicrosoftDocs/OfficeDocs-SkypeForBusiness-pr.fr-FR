---
title: Déployer des salles Microsoft Teams avec Skype Entreprise Server
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Lisez cette rubrique pour plus d’informations sur le déploiement de salles Microsoft Teams avec Skype Entreprise Server.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ee33ec1ded7e8461f629c4552236ee60828a168
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662259"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Déployer des salles Microsoft Teams avec Skype Entreprise Server
  
Cette rubrique explique comment ajouter un compte d’appareil pour salles Microsoft Teams lorsque vous disposez d’un déploiement sur site à une seule forêt.
  
Si vous utilisez un déploiement sur site dans une seule forêt avec Exchange 2013 SP1 ou une date ultérieure et Skype Entreprise Server 2015 ou une date ultérieure, vous pouvez utiliser les scripts Windows PowerShell fournis pour créer des comptes d’appareil. Si vous utilisez un déploiement en forêts multiples, vous pouvez utiliser des cmdlets équivalentes qui produit les mêmes résultats. Ces applets de commande sont décrites dans cette section.

  
Avant de commencer à déployer des salles Microsoft Teams, assurez-vous que vous disposez des autorisations autorisées pour exécuter les cmdlets associées.
  

   ``` Powershell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

   Notez $strExchangeServer est le nom de domaine complet (FQDN) de votre serveur Exchange et $strLyncFQDN est le nom de domaine complet de votre déploiement Skype Entreprise Server.

2. Après avoir établi une session, vous allez créer une boîte aux lettres et l’activer en tant que compte RoomMailboxAccount, ou modifier les paramètres d’une boîte aux lettres de salle existante. Cela permet au compte de s’authentifier aux salles Microsoft Teams.

    Si vous modifiez une boîte aux lettres de ressource :

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Si vous créez une boîte aux lettres de ressources :

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Vous pouvez définir différentes propriétés Exchange sur le compte d’appareil pour améliorer l’expérience de réunion pour les personnes. Vous pouvez consulter les propriétés qui doivent être définies dans la section Propriétés Exchange.

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. Si vous décidez que le mot de passe n’expire pas, vous pouvez le définir avec des Windows PowerShell également. Pour plus d’informations, reportez-vous à la section Gestion des mots de passe.

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Activez le compte dans Active Directory afin qu’il s’authentifiera aux salles Microsoft Teams.

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Activez le compte d’appareil avec Skype Entreprise Server en activant votre compte Microsoft Teams Salles Active Directory sur un pool Skype Entreprise Server :

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    Vous devrez utiliser l’adresse SIP (Session Initiation Protocol) et le contrôleur de domaine du projet.

7. **Facultatif**. Vous pouvez également autoriser les salles Microsoft Teams à passer et recevoir des appels téléphoniques de réseau téléphonique commuté (PSTN) en activant les Voix Entreprise pour votre compte. Voix Entreprise n’est pas obligatoire pour les salles Microsoft Teams, mais si vous souhaitez utiliser la fonctionnalité de numérotation PSTN pour le client Salles Microsoft Teams, voici comment l’activer :

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   Une fois encore, vous devrez remplacer les exemples de contrôleur de domaine et de numéro de téléphone fournis par vos propres informations. La valeur du paramètre $true demeure identique.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Exemple : configuration d’un compte de salle dans Exchange et Skype Entreprise Server en local

``` Powershell
New-Mailbox -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force)
-UserPrincipalName rigel1@contoso.com

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false
-RemovePrivateProperty $false
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

Enable-CsMeetingRoom -Identity rigel1@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity rigel1 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -PolicyName dk -Identity rigel1
Grant-CsDialPlan -PolicyName e15dp2.contoso.com -Identity rigel1
```

## <a name="related-topics"></a>Sujets associés

[Configurer des comptes pour les salles Microsoft Teams](rooms-configure-accounts.md)

[Planifier les Salles Microsoft Teams](rooms-plan.md)
  
[Déployer les Salles Microsoft Teams](rooms-deploy.md)
  
[Configurer une console des salles Microsoft Teams](console.md)
  
[Gérer les Salles Microsoft Teams](rooms-manage.md)

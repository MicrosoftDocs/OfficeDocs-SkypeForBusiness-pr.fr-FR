---
title: Déploiement de salles de Microsoft teams avec Skype entreprise Server
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
description: Pour plus d’informations sur le déploiement de salles de Microsoft teams avec Skype entreprise Server, reportez-vous à cette rubrique.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ee33ec1ded7e8461f629c4552236ee60828a168
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662259"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Déploiement de salles de Microsoft teams avec Skype entreprise Server
  
Cette rubrique explique comment ajouter un compte d’appareil pour les salles Microsoft teams lorsque vous disposez d’un déploiement local de forêt et de forêt unique.
  
Si vous avez un déploiement local de forêt unique avec Exchange 2013 SP1 ou une version ultérieure et Skype entreprise Server 2015 ou une version ultérieure, vous pouvez utiliser les scripts Windows PowerShell fournis pour créer des comptes d’appareil. Si vous utilisez un déploiement à plusieurs forêts, vous pouvez utiliser les applets de requête équivalentes qui produisent les mêmes résultats. Ces applets de commande sont décrites dans cette section.

  
Avant de commencer à déployer des salles de Microsoft Teams, vérifiez que vous disposez des autorisations appropriées pour exécuter les applets de cmdlet associées.
  

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

   Notez que $strExchangeServer est le nom de domaine complet (FQDN) de votre serveur Exchange, et que $strLyncFQDN est le FQDN du déploiement de Skype entreprise Server.

2. Après avoir établi une session, vous pouvez créer une nouvelle boîte aux lettres et l’activer en tant que RoomMailboxAccount, ou changer les paramètres d’une boîte aux lettres de salle existante. Cela permettra au compte d’s’authentifier auprès des salles de Microsoft Teams.

    Si vous modifiez une boîte aux lettres de ressource :

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Si vous créez une nouvelle boîte aux lettres de ressources :

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Vous pouvez définir diverses propriétés Exchange sur le compte de l’appareil pour améliorer l’interface utilisateur de la réunion. Vous pouvez consulter les propriétés qui doivent être définies dans la section Propriétés Exchange.

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. Si vous décidez que le mot de passe n’expire pas, vous pouvez également définir ce comportement avec les applets de cmdlet Windows PowerShell. Pour plus d’informations, reportez-vous à la section Gestion des mots de passe.

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Activez le compte dans Active Directory de manière à ce qu’il s’authentifie aux salles de Microsoft Teams.

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Activez le compte de l’appareil avec Skype entreprise Server en activant votre compte Active Directory de Microsoft teams sur un pool Skype entreprise Server :

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    Vous devrez utiliser l’adresse SIP (Session Initiation Protocol) et le contrôleur de domaine du projet.

7. **Facultatif**. Vous pouvez également permettre aux salles de Microsoft teams de passer et de recevoir des appels téléphoniques du réseau téléphonique commuté (PSTN) en activant Enterprise Voice pour votre compte. L’application voix entreprise n’est pas obligatoire pour les salles de Microsoft Teams, mais si vous voulez utiliser la fonctionnalité de numérotation PSTN pour le client Microsoft Teams, voici comment l’activer :

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   Une fois encore, vous devrez remplacer les exemples de contrôleur de domaine et de numéro de téléphone fournis par vos propres informations. La valeur du paramètre $true demeure identique.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Exemple : configuration de compte salle dans Exchange et Skype entreprise Server en local

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

[Configurer des comptes pour les salles de Microsoft teams](rooms-configure-accounts.md)

[Planifier les Salles Microsoft Teams](rooms-plan.md)
  
[Déployer les Salles Microsoft Teams](rooms-deploy.md)
  
[Configurer une console des salles Microsoft Teams](console.md)
  
[Gérer les Salles Microsoft Teams](rooms-manage.md)

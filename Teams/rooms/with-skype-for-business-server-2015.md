---
title: Déployer Salles Microsoft Teams avec Skype Entreprise Server
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Lisez cette rubrique pour plus d’informations sur le déploiement de Salles Microsoft Teams avec Skype Entreprise Server.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 53903052efe28a85400ba8b418bd8869ef2dec4e
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271679"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Déployer Salles Microsoft Teams avec Skype Entreprise Server
  
Cette rubrique explique comment ajouter un compte de ressource pour Salles Microsoft Teams lorsque vous disposez d’un déploiement local à forêt unique.
  
Si vous disposez d’un déploiement local à forêt unique avec Exchange 2013 SP1 ou version ultérieure et Skype Entreprise Server 2015 ou version ultérieure, vous pouvez utiliser les scripts Windows PowerShell fournis pour créer des comptes d’appareil. Si vous utilisez un déploiement multi-forêts, vous pouvez utiliser des applets de commande équivalentes qui produisent les mêmes résultats. Ces applets de commande sont décrites dans cette section.
  
Avant de commencer à déployer Salles Microsoft Teams, assurez-vous que vous disposez des autorisations appropriées pour exécuter les applets de commande associées.
  

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

   Notez que $strExchangeServer est le nom de domaine complet (FQDN) de votre serveur Exchange et $strLyncFQDN est le nom de domaine complet de votre déploiement Skype Entreprise Server.

2. Après avoir établi une session, vous allez créer une boîte aux lettres et l’activer en tant que RoomMailboxAccount, ou modifier les paramètres d’une boîte aux lettres de salle existante. Cela permet au compte de s’authentifier auprès de Salles Microsoft Teams.

    Si vous modifiez une boîte aux lettres de ressource :

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoome01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Si vous créez une boîte aux lettres de ressources :

   ``` Powershell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Alias ConferenceRoom01 -Name "Conference Room 01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Vous pouvez définir différentes propriétés Exchange sur le compte de ressource salles Teams afin d’améliorer l’expérience de réunion pour les personnes. Vous pouvez consulter les propriétés qui doivent être définies dans la section Propriétés Exchange.

   ``` Powershell
   Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"
   ```

4. Désactivez l’expiration du mot de passe sur le compte de ressource.

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -PasswordNeverExpires $true
   ```

5. Activez le compte de ressource dans Active Directory pour qu’il s’authentifie auprès de Salles Microsoft Teams.

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -Enabled $true
   ```

6. Activez le compte de ressource avec Skype Entreprise Server en activant votre compte Active Directory Salles Microsoft Teams sur un pool de Skype Entreprise Server :

   ``` Powershell
   Enable-CsMeetingRoom -Identity ConferenceRoom01 -SipAddress sip:ConferenceRoom01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com 
   ```

    Remplacez les `-DomainController` attributs par `-RegistrarPool` des valeurs appropriées pour votre environnement.

7. **Facultatif**. Vous pouvez également autoriser Salles Microsoft Teams à passer et recevoir des appels téléphoniques commutés publics (RTC) en activant Voix Entreprise pour votre compte. Voix Entreprise n’est pas obligatoire pour Salles Microsoft Teams, mais si vous souhaitez une fonctionnalité de numérotation RTC pour Salles Microsoft Teams, voici comment l’activer :

   ``` Powershell
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName VP1
   Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName DP1
   ```

   Une fois encore, vous devrez remplacer les exemples de contrôleur de domaine et de numéro de téléphone fournis par vos propres informations. La valeur du paramètre $true demeure identique. Vous devez également remplacer la stratégie vocale et les noms de stratégie de plan de numérotation.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Exemple : configuration du compte de salle dans Exchange et Skype Entreprise Server localement

``` Powershell
New-Mailbox -Alias ConferenceRoom01 -Name "Conference Room 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force) -UserPrincipalName ConferenceRoom01@contoso.com

Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"

Enable-CsMeetingRoom -Identity ConferenceRoom01@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity ConferenceRoom01 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName dk
Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName e15dp2.contoso.com
```

## <a name="related-topics"></a>Voir aussi

[Configurer des comptes pour Salles Microsoft Teams](rooms-configure-accounts.md)

[Planifier les Salles Microsoft Teams](rooms-plan.md)
  
[Déployer les Salles Microsoft Teams](rooms-deploy.md)
  
[Configurer une console des salles Microsoft Teams](console.md)
  
[Gérer les Salles Microsoft Teams](rooms-manage.md)

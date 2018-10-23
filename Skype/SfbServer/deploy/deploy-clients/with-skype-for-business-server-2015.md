---
title: Déployer la salle Skype systèmes v2 avec Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Lisez cette rubrique pour plus d’informations sur la façon de déployer des systèmes de salle Skype v2 avec Skype pour Business Server.
ms.openlocfilehash: 891f716be3a2b7d8479af83b57dfccd70500e50d
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699379"
---
# <a name="deploy-skype-room-systems-v2-with-skype-for-business-server"></a>Déployer la salle Skype systèmes v2 avec Skype pour Business Server
  
Cette rubrique explique comment vous ajoutez un compte de périphériques pour les systèmes de salle Skype v2 lorsque vous avez un déploiement local de forêt unique.
  
Si vous avez une forêt unique, le déploiement local avec Exchange 2013 SP1 ou version ultérieure et le Skype pour Business Server 2015 ou version ultérieure, vous pouvez utiliser les scripts Windows PowerShell fournis pour créer des comptes de l’appareil. Si vous utilisez un déploiement à forêts multiples, vous pouvez utiliser les applets de commande équivalente qui produit le même résultat. Ces applets de commande sont décrites dans cette section.

Pour configurer des comptes d’utilisateurs, la plus simple consiste à configurer à l’aide de Windows PowerShell à distance. Microsoft propose [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aide à créer des comptes d’utilisateur ou de valider les comptes de ressource existant dont vous disposez afin de vous aider à les transformer en comptes d’utilisateurs v2 Skype salle systèmes compatibles. Si vous préférez, vous pouvez suivre les étapes ci-dessous pour configurer les comptes utilisés par votre appareil v2 de systèmes de salle Skype.
  
## <a name="deploy-skype-room-systems-v2-with-skype-for-business-server"></a>Déployer la salle Skype systèmes v2 avec Skype pour Business Server

Avant de déployer des systèmes de salle Skype v2 avec Skype pour Business Server, assurez-vous que vous remplissez les conditions. Pour plus d’informations, reportez-vous à la rubrique [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Avant de commencer à déployer des systèmes de salle Skype v2, assurez-vous que les autorisations appropriées pour exécuter les applets de commande associée.
  
1. Démarrer une session Windows PowerShell à distance à partir d’un PC et se connecter à Exchange. 
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
 
   ```

   Notez que $strExchangeServer est le nom de domaine complet (FQDN) de votre serveur Exchange et $strLyncFQDN est le nom de domaine complet de votre Skype pour le déploiement de serveur d’entreprise.
    
2. Après avoir établi une session, vous allez créer une nouvelle boîte aux lettres et activer comme un RoomMailboxAccount, soit modifier les paramètres d’une boîte aux lettres de salle existante. Ainsi, le compte de s’authentifier sur les systèmes de salle Skype v2.
    
    Si vous modifiez une boîte aux lettres de ressource :
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Si vous créez une nouvelle boîte aux lettres de ressources :
    
   ```
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room 
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Vous pouvez définir diverses propriétés Exchange sur le compte de l’appareil pour améliorer l’expérience des personnes. Vous pouvez consulter les propriétés qui doivent être définies dans la section Propriétés Exchange.
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. Si vous décidez d’avoir le mot de passe n'expire pas, vous pouvez également définir qui avec les applets de commande Windows PowerShell. Pour plus d’informations, reportez-vous à la section Gestion des mots de passe.
    
   ```
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Activez le compte dans Active Directory pour authentifie à Skype salle systèmes v2.
    
   ```
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Activer le compte de l’appareil avec Skype pour Business Server grâce à votre compte d’Active Directory v2 Skype salle systèmes sur un Skype pour le pool de serveurs d’entreprise :
    
   ```
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com 
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    Vous devrez utiliser l’adresse SIP (Session Initiation Protocol) et le contrôleur de domaine du projet. 
    
7. **Facultatif**. Vous pouvez également permettre Skype salle systèmes v2 émettre et recevoir des appels téléphoniques de réseau téléphonique commuté public en activant Enterprise Voice de votre compte. Enterprise Voice n’est pas une condition requise pour les systèmes de salle Skype v2, mais si vous souhaitez composer le numéro PSTN pour le client de v2 Skype salle systèmes, voici comment l’activer :
    
   ```
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   Une fois encore, vous devrez remplacer les exemples de contrôleur de domaine et de numéro de téléphone fournis par vos propres informations. La valeur du paramètre $true demeure identique.
    
## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Exemple : configuration de compte salle dans Exchange et Skype pour Business Server sur site

```
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

## <a name="see-also"></a>Voir aussi

[Configurer des comptes pour les systèmes de salle Skype v2](room-systems-v2-configure-accounts.md)

[Plan for Skype Room Systems v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Déploiement de Skype Room System v2](room-systems-v2.md)
  
[Configuration d’une console Skype Room Systems v2](console.md)
  
[Gestion de Skype Room System v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
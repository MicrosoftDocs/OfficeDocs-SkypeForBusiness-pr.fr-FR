---
title: Déploiement de Skype Room Systems v2 avec Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Lisez cette rubrique pour plus d’informations sur le déploiement de v2 Skype salle systèmes avec Skype pour Business Server 2015.
ms.openlocfilehash: 904835e766283791f52c0dc1d1221a0d7253e3e1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-with-skype-for-business-server-2015"></a>Déploiement de Skype Room Systems v2 avec Skype Entreprise Server 2015
 
Lisez cette rubrique pour plus d’informations sur le déploiement de v2 Skype salle systèmes avec Skype pour Business Server 2015.
  
Cette rubrique explique comment vous ajoutez un compte de dispositif pour systèmes de salle Skype v2 lorsque vous disposez d’un déploiement sur site de forêt unique.
  
Si vous avez une forêt unique, déploiement sur site avec Exchange 2013 SP1 ou version ultérieure et Skype pour Business Server 2015 ou version ultérieure, vous pouvez utiliser les scripts Windows PowerShell fournis pour créer les comptes de périphérique. Si vous utilisez un déploiement de plusieurs forêt, vous pouvez utiliser des applets de commande équivalente qui produira les mêmes résultats. Ces applets de commande sont décrites dans cette section.
  
## <a name="deploy-skype-room-systems-v2-with-skype-for-business-server-2015"></a>Déploiement de Skype Room Systems v2 avec Skype Entreprise Server 2015

Avant de déployer v2 Skype salle systèmes avec Skype pour Business Server 2015, veillez à ce que vous avez satisfait les exigences. Pour plus d’informations, consultez [v2 Skype pièce requise](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Avant de commencer à déployer des systèmes de salle Skype v2, assurez-vous que vous disposez des autorisations appropriées pour exécuter les applets de commande associé.
  
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

   Notez que $strExchangeServer est le nom de domaine pleinement qualifié (FQDN) de votre serveur Exchange, et $strLyncFQDN est le nom de domaine complet de votre Skype pour le déploiement de Business Server 2015.
    
2. Après l’établissement d’une session, vous allez créer une nouvelle boîte aux lettres et activer comme un RoomMailboxAccount, soit modifier les paramètres d’une boîte aux lettres de salle existante. Ainsi, le compte pour s’authentifier sur des systèmes de salle Skype v2.
    
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

3. Vous pouvez définir différentes propriétés de Exchange sur le compte de dispositif pour améliorer l’expérience de la réunion pour les personnes. Vous pouvez consulter les propriétés qui doivent être définies dans la section Propriétés Exchange.
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. Si vous souhaitez que le mot de passe n'expire pas, vous pouvez également définir qu’avec les applets de commande Windows PowerShell. Pour plus d’informations, reportez-vous à la section Gestion des mots de passe.
    
   ```
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Activer le compte dans Active Directory afin qu’il va authentifier pour systèmes de salle Skype v2.
    
   ```
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Activer le compte de dispositif avec Skype pour Business Server 2015 par l’activation de votre compte d’Active Directory v2 systèmes de salle Skype sur un Skype pour Business Server 2015 pool :
    
   ```
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com 
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    Vous devrez utiliser l’adresse SIP (Session Initiation Protocol) et le contrôleur de domaine du projet. 
    
7. **Facultatif**. Vous pouvez également autoriser v2 de systèmes de salle Skype à effectuer et de recevoir des appels téléphoniques de réseau téléphonique public commuté par l’activation de Voix Entreprise pour votre compte. Voix Entreprise n’est pas une condition requise pour les systèmes de salle Skype v2, mais si vous souhaitez que la numérotation PSTN fonctionnalités du client v2 de systèmes de salle Skype, voici comment l’activer :
    
   ```
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01

   ```

   Une fois encore, vous devrez remplacer les exemples de contrôleur de domaine et de numéro de téléphone fournis par vos propres informations. La valeur du paramètre $true demeure identique.
    
## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-2015-on-premises"></a>Exemple : salle de compte paramétré dans Exchange et Skype pour 2015 de serveur d’entreprise dans les locaux

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

#### 

[Plan de salle de Skype systèmes v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Déployer Skype salle systèmes v2](room-systems-v2.md)
  
[Configurer une console v2 de systèmes de salle de Skype](console.md)
  
[Gérer l’espace de Skype systèmes v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)


---
title: Déploiement de Skype Room Systems v2 avec Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lisez cette rubrique pour plus d’informations sur le déploiement de v2 Skype salle systèmes avec Office 365.
ms.openlocfilehash: b05afbf973e814c5adf7b8a8490aefa0cbb04886
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a>Déploiement de Skype Room Systems v2 avec Office 365 
 
Lisez cette rubrique pour plus d’informations sur le déploiement de v2 Skype salle systèmes avec Office 365.
  
Cette rubrique décrit comment ajouter un compte de dispositif pour systèmes de salle Skype v2 lorsque vous disposez d’un déploiement en ligne d’Office 365.
  
## <a name="deploy-skype-room-systems-v2-with-office-365"></a>Déploiement de Skype Room Systems v2 avec Office 365 

Avant de déployer v2 Skype salle systèmes avec Office 365, veillez à ce que vous avez satisfait les exigences. Pour plus d’informations, consultez [v2 Skype pièce requise](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Pour activer Skype pour entreprise, vous devez disposer des éléments suivants :
  
- Skype pour Business Online (Plan 2) ou version ultérieure dans votre plan d’Office 365. Le plan doit prendre en charge la fonctionnalité de conférence.
    
- Si vous avez besoin de Voix Entreprise (téléphonie RTPC) à l’aide des fournisseurs de service de téléphonie pour systèmes de salle Skype v2 vous devez Skype pour Business Online (Plan 3).
    
- Les utilisateurs de clients doivent avoir des boîtes aux lettres Exchange.
    
- Votre compte v2 de systèmes de salle Skype nécessite Skype pour Business Online (Plan 2) ni Skype pour licence Business Online (Plan 3), mais il ne nécessite pas une licence Exchange en ligne.
    
### <a name="add-a-device-account"></a>Ajout d’un compte d’appareil

1. Démarrer une session à distance de Windows PowerShell sur un PC et se connecter à Exchange. Assurez-vous de disposer des autorisations adéquates pour exécuter les applets de commande associées. Voici quelques exemples d’applets de commande pouvant être utilisés et modifiés dans votre environnement.
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential 
   $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. Après l’établissement d’une session, vous allez créer une nouvelle boîte aux lettres et activer comme un RoomMailboxAccount, soit modifier les paramètres d’une boîte aux lettres de salle existante. Ainsi, le compte pour s’authentifier sur des systèmes de salle Skype v2.
    
  Si vous modifiez une boîte aux lettre de ressource :
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

  Si vous créez une nouvelle boîte aux lettres de ressources :
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 
-Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Plusieurs propriétés Exchange doivent être définies sur le compte d’appareil pour optimiser l’expérience de réunion. Vous pouvez consulter les propriétés qui doivent être définies dans la section Propriétés Exchange.
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
   -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

   ```

4. Vous devrez vous connecter à Azure Active Directory pour appliquer certains paramètres de compte. Pour vous connecter à Azure AD, exécutez l’applet de commande suivante :
    
   ```
   Connect-MsolService -Credential $cred
   ```

5. 	Pour empêcher l’expiration du mot de passe, exécutez l’applet de commande Set-MsolUser cmdlet avec l’option Le mot de passe n’expire jamais, comme suit :   
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
   ```

   Vous pouvez également définir un numéro de téléphone pour la salle comme suit :
    
   ```
   Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
   ```

6. Le compte de périphérique doit posséder une licence valide de Office 365, ou Exchange et Skype pour entreprise ne fonctionneront pas. Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte. Vous pouvez utiliser Get-MsolAccountSku pour récupérer une liste de références disponibles pour vos clients d’Office 365, comme suit :
    
   ```
   Get-MsolAccountSku
   ```

   Puis, vous pouvez ajouter une licence à l’aide de l’applet de commande Set-MsolUserLicense. Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

7. Ensuite, vous devez activer le compte de dispositif avec Skype pour les entreprises. Assurez-vous que votre environnement répond aux exigences définies dans les [exigences en matière de systèmes de salle Skype v2](../../plan-your-deployment/clients-and-devices/requirements.md).
    
   Démarrez une session Windows PowerShell à distance comme suit (veillez à installer Skype pour les composants Business Online PowerShell) :
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   Ensuite, activez votre compte v2 de systèmes de salle de Skype pour Skype pour Business Server en exécutant l’applet de commande suivante :
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   Obtenir les informations RegistrarPool de nouveau compte d’utilisateur en cours d’installation, comme indiqué dans cet exemple :
    
    ```
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > Nouveaux comptes d’utilisateurs ne soient pas créées dans le même pool de Registre en tant que comptes d’utilisateur existants dans le locataire. La commande ci-dessus évitera que des erreurs dans le programme d’installation de compte en raison de cette situation. 
  
Une fois que vous avez terminé les étapes précédentes pour activer votre compte de v2 de systèmes de salle Skype dans Skype pour professionnels en ligne, vous devez attribuer une licence à dispositif de systèmes de salle Skype v2. À l’aide du portail d’administration d’Office 365, affecter soit un Skype d’entreprise en ligne (Plan 2) ou un Skype pour licence Business Online (Plan 3) pour le périphérique.
  
### <a name="assign-a-license-to-your-account"></a>Affectation d’une licence à votre compte

1. Connexion en tant qu’un administrateur de clients, ouvrez le portail d’administration de Office 365 et cliquez sur l’application d’administration.
    
2. Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.
    
3. Sélectionnez le compte de v2 Skype salle systèmes, puis cliquez sur ou cliquez sur l’icône de plume, ce qui signifie modifier.
    
4. Cliquez sur l’option **Licences**.
    
5. Dans la section **attribution de licences** , vous devez sélectionner Skype pour Business Online (Plan 2) ou Skype pour Business Online (Plan 3), en fonction de votre licence et que vous avez décidé en ayant besoin de Voix Entreprise. Vous devrez utiliser une licence 3 de Plan si vous souhaitez utiliser le nuage PBX sur les systèmes de salle Skype v2. Vous aurez au moins besoin de CloudPBX pour la connectivité vocale. Puis, configurez la voix hybride ou la fonction d’appel RTC sur la méthode de connectivité RTC.
    
6. Cliquez sur **Enregistrer** pour terminer la tâche.
    
## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>Exemple : Compte de l’espace d’installation dans Exchange Online et Skype pour professionnels en ligne

```
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com
 -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true
 -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force)
 
Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept 
-AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
$false -DeleteSubject $false -RemovePrivateProperty $false
 
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true 
-AdditionalResponse "This is a Rigel room!"
 
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
 
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
 
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress

```

> [!NOTE]
> Ceci ajoute CloudPBX et PSTNCallingDomesticAndInternational. De plus, vous devrez utiliser l’interface administrative pour affecter un numéro de téléphone. 
  
## <a name="see-also"></a>Voir aussi

#### 

[Plan de salle de Skype systèmes v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Déployer Skype salle systèmes v2](room-systems-v2.md)
  
[Configurer une console v2 de systèmes de salle de Skype](console.md)
  
[Gérer l’espace de Skype systèmes v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)


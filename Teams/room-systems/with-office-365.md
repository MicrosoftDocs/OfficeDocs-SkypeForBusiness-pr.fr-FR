---
title: Déployer des Salles Microsoft Teams avec Office 365 ProPlus
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lisez cette rubrique pour plus d’informations sur la façon de déployer Microsoft équipes salles avec Office 365.
ms.openlocfilehash: ed95eb489cad7ebea95a96a069e58421aff61380
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33916416"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a>Déployer des Salles Microsoft Teams avec Office 365 ProPlus

Lisez cette rubrique pour plus d’informations sur la façon de déployer Microsoft équipes salles avec Office 365, où Microsoft Teams ou Skype pour les entreprises et Exchange sont en ligne.

Pour configurer des comptes d’utilisateurs, la plus simple consiste à configurer à l’aide de Windows PowerShell à distance. Microsoft propose [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aide à créer des comptes d’utilisateur ou de valider les comptes de ressource existant dont vous disposez afin de vous aider à les transformer en comptes d’utilisateurs locaux des équipes Microsoft compatibles. Si vous préférez, vous pouvez suivre les étapes ci-dessous pour configurer les comptes utilisés par votre périphérique Microsoft équipes salles.

## <a name="requirements"></a>Configuration requise

Avant de déployer Microsoft équipes salles avec Office 365, assurez-vous que vous remplissez les conditions. Pour plus d’informations, consultez [Configuration requise de salles d’équipes Microsoft](requirements.md).

Pour activer Skype pour les entreprises, vous devez disposer les éléments suivants :

- Skype pour Business Online (Plan 2 ou un plan d’entreprise) ou supérieure dans votre plan Office 365. Le plan doit autoriser les fonctions de conférence rendez-vous.

- Si vous avez besoin des fonctionnalités de rendez-vous à partir d’une réunion, vous devez une conférence audio et la licence du système téléphonique.  Si vous avez besoin des fonctionnalités d’appel sortant à partir d’une réunion, vous devez a internes ou nationales et internationales appelant Plan.

- Les utilisateurs de client doivent avoir des boîtes aux lettres Exchange.

- Votre compte Microsoft équipes salles requiert au minimum un Skype pour la licence entreprise Online (Plan 2), mais il ne nécessite pas une licence Exchange Online. Pour plus d’informations, voir [licences salles d’équipes Microsoft](skype-room-systems-v2.md) .

Pour plus d’informations sur Skype pour Business Online Plans, voir le [Skype pour Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).

### <a name="add-a-device-account"></a>Ajout d’un compte d’appareil

1. Connexion à Exchange Online PowerShell. Pour plus d’informations, voir [se connecter à Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

2. Dans Exchange Online PowerShell, créez une nouvelle boîte aux lettres de salle ou modifier une boîte aux lettres de salle existante. Par défaut, les boîtes aux lettres de salle ne disposent pas des comptes associés, afin que vous aurez besoin d’ajouter un compte lorsque vous créez ou modifiez une boîte aux lettres de salle qui lui permet de s’authentifier avec des systèmes de salle Skype v2.

   - Pour créer une nouvelle boîte aux lettres de salle, utilisez la syntaxe suivante :

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Cet exemple crée une nouvelle boîte aux lettres de salle avec les paramètres suivants :

     - Nom : Project-Rigel-01.

     - Alias : ProjectRigel01

     - Compte : ProjectRigel01@contoso.onmicrosoft.com

     - Mot de passe de compte : P@$$W0rd5959

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Pour modifier une boîte aux lettres de salle existante, utilisez la syntaxe suivante :

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Cet exemple active le compte pour la boîte aux lettres de salle existante qui a la valeur d’alias ProjectRigel02 et définit le mot de passe 9898P@$$W0rd. Notez que le compte sera ProjectRigel02@contoso.onmicrosoft.com en raison de la valeur d’alias existante.

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Pour détaillées sur la syntaxe et les informations sur les paramètres, voir [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) et [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).


3. Dans Exchange Online PowerShell, configurez les paramètres suivants dans la boîte aux lettres de salle pour améliorer l’expérience de réunion :

   - AutomateProcessing : AutoAccept (organisateurs de réunion recevoir la décision de réservation de salles directement sans intervention humaine : libre = accepter ; occupé = refuser.)

   - AddOrganizerToSubject : $false (l’organisateur de la réunion n’est pas ajouté à l’objet de la demande de réunion).

   - DeleteComments : $false (conserver le texte dans le corps du message de demandes de réunion entrantes).

   - DeleteSubject : $false (conserver l’objet de demandes de réunion entrantes).

   - RemovePrivateProperty : $false (garantit la demande de l’indicateur privé qui a été envoyé par l’organisateur de la réunion d’origine reste comme indiqué).

   - AddAdditionalResponse : $true (le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion).

   - AdditionalResponse : « Ceci est une salle de réunion Skype ! » (Texte supplémentaire à ajouter à la demande de réunion.)

   Cet exemple configure ces paramètres dans la boîte aux lettres de salle nommé Project-Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Pour détaillées sur la syntaxe et les informations sur les paramètres, voir [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Se connecter à MS Online PowerShell pour rendre les paramètres Active Directory en exécutant la `Connect-MsolService -Credential $cred` applet de commande powershell.   Pour plus d’informations sur Active Directory, voir [Azure Active Directory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) n’est pas pris en charge. 

5. Si vous ne souhaitez pas que le mot de passe à expiration, utilisez la syntaxe suivante :

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   Cet exemple montre comment définir le mot de passe pour le compte ProjectRigel01@contoso.onmicrosoft.com n’expire jamais.

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   Vous pouvez également définir un numéro de téléphone pour le compte en exécutant la commande suivante :

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. Le compte de l’appareil doit avoir une licence Office 365 ou Exchange et Microsoft Teams ou Skype pour les entreprises ne fonctionne pas. Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte. Vous pouvez utiliser`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> pour récupérer une liste de références disponibles pour votre client Office 365 comme suit :

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Ensuite, vous pouvez ajouter une licence à l’aide du`Set-MsolUserLicense` <!--Set-AzureADUserLicense --> applet de commande. Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).

  ``` PowerShell
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
  ``` 
<!-- 
   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   Pour obtenir des instructions détaillées, consultez la rubrique [attribution de licences pour les comptes d’utilisateurs avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

7. Ensuite, vous devez activer le compte de l’appareil avec Skype pour les entreprises. Assurez-vous que votre environnement répond aux exigences définies dans les [salles d’équipes Microsoft requise](requirements.md).

   Démarrer une [session Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) à distance comme suit (veillez à [installer Skype pour les composants Business Online PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)) :

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   Ensuite, activer votre compte Microsoft équipes salles pour Skype pour Business Server en exécutant l’applet de commande suivante :

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   Obtenir les informations de RegistrarPool à partir du nouveau compte d’utilisateur en cours d’installation, comme indiqué dans cet exemple :

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > Nouveaux comptes d’utilisateur ne peuvent pas être créés sur le même pool de serveurs d’inscriptions en tant que comptes d’utilisateurs existants dans le client. La commande ci-dessus empêchera les erreurs de configuration de compte en raison de cette situation.

Une fois que vous avez terminé les étapes précédentes pour activer votre compte Microsoft équipes salles dans Microsoft Teams ou Skype pour Business Online, vous devez attribuer une licence à un périphérique de salles d’équipes Microsoft. À l’aide du portail d’administration d’Office 365, assignez un soit Skype Business Online (Plan 2) ou une Skype licence entreprise Online (Plan 3) à l’appareil.

### <a name="assign-a-license-to-your-account"></a>Affectation d’une licence à votre compte

1. Ouverture de session en tant qu’un administrateur client, ouvrez le portail d’administration d’Office 365, puis cliquez sur l’application d’administration.

2. Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.

3. Sélectionnez le compte Microsoft équipes locaux, puis cliquez ou appuyez sur l’icône crayon, ce qui signifie que modifier.

4. Cliquez sur l’option **Licences**.

5. Dans la section **attribution de licences** , vous devez sélectionner Skype pour Business Online (Plan 2) ou Skype pour Business Online (Plan 3), en fonction de vos licences et vous avez décidé en termes de devoir Enterprise Voice. Vous devrez utiliser une licence 3 planifier si vous souhaitez utiliser dans le nuage PBX sur salles d’équipes Microsoft. Vous aurez au moins besoin de CloudPBX pour la connectivité vocale. Puis, configurez la voix hybride ou la fonction d’appel RTC sur la méthode de connectivité RTC. Pour plus d’informations, voir [licences salles d’équipes Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) .

6. Cliquez sur **Enregistrer** pour terminer la tâche.

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>Exemple : Compte salle du programme d’installation dans Exchange Online et Skype pour Business Online

Commandes Exchange Online PowerShell :

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

Commandes Azure Active Directory PowerShell :

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

Skype pour commande PowerShell d’entreprise :

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> Ceci ajoute CloudPBX et PSTNCallingDomesticAndInternational. En outre, vous devez utiliser l’interface d’administration pour affecter un numéro de téléphone.

## <a name="validate"></a>Valider

Pour la validation, vous devez être en mesure d’utiliser n’importe quel Skype pour client d’entreprise pour vous connecter au compte que vous avez créé.

## <a name="see-also"></a>Voir aussi

[Configurer des comptes pour les salles d’équipes Microsoft](room-systems-v2-configure-accounts.md)

[Planifier des équipes Microsoft salles](skype-room-systems-v2-0.md)

[Déployer les équipes Microsoft salles](room-systems-v2.md)

[Configurer une console Microsoft équipes salles](console.md)

[Gérer Microsoft Teams Rooms](skype-room-systems-v2.md)

[Salles de gestion des licences des équipes de Microsoft](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)

---
title: Déploiement de salles Microsoft teams avec Microsoft 365 ou Office 365
ms.author: v-lanac
author: lanachin
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
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Consultez cette rubrique pour plus d’informations sur le déploiement de salles de Microsoft teams avec Microsoft 365 ou Office 365, où teams ou Skype entreprise et Exchange sont tous deux en ligne.
ms.openlocfilehash: 9a4ee558cfa9901566afc7f30f1f64a8b745331b
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666136"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Déploiement de salles Microsoft teams avec Microsoft 365 ou Office 365

Consultez cette rubrique pour plus d’informations sur le déploiement de salles de Microsoft teams avec Microsoft 365 ou Office 365, où Microsoft teams ou Skype entreprise et Exchange sont tous deux en ligne.

Le moyen le plus simple de configurer des comptes d’utilisateurs consiste à les configurer à l’aide de Windows PowerShell distant. Microsoft fournit [SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous permet de créer de nouveaux comptes d’utilisateur, ou de valider des comptes de ressources existants dont vous disposez pour vous aider à les convertir en comptes d’utilisateurs de salles Microsoft teams compatibles. Si vous le souhaitez, vous pouvez suivre les étapes ci-dessous afin de configurer des comptes que votre appareil de salle Microsoft teams utilisera.

## <a name="requirements"></a>Configuration requise

Avant de déployer des salles Microsoft teams avec Microsoft 365 ou Office 365, assurez-vous que vous remplissez les conditions requises. Pour plus d’informations, voir la [Configuration requise pour Microsoft teams salles](requirements.md).

Pour activer Skype entreprise, vous devez disposer des éléments suivants :

- Skype entreprise Online (plan 2 ou plan d’entreprise) ou version ultérieure dans votre plan Microsoft 365 ou Office 365. Le plan doit permettre l’accès aux fonctionnalités de conférence rendez-vous.

- Si vous avez besoin de fonctionnalités de connexion à une réunion, vous avez besoin d’une licence de système téléphonique et de téléconférence.  Si vous avez besoin de fonctionnalités de numérotation d’une réunion, vous aurez besoin d’une licence de conférence audio.

- Les utilisateurs de votre client doivent avoir des boîtes aux lettres Exchange.

- Votre compte Microsoft teams Room nécessite au moins une licence Skype entreprise Online (plan 2), mais il ne nécessite pas de licence Exchange Online. Pour plus d’informations, consultez la rubrique [licences Microsoft teams](rooms-licensing.md) .

Pour plus d’informations sur les offres Skype entreprise Online, reportez-vous à la [Description du service Skype entreprise Online](https://technet.microsoft.com/library/jj822172.aspx).

### <a name="add-a-device-account"></a>Ajout d’un compte d’appareil

1. Connectez-vous à Exchange Online PowerShell. Pour obtenir des instructions, voir [se connecter à Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

2. Dans Exchange Online PowerShell, créez une nouvelle boîte aux lettres de salle ou modifiez une boîte aux lettres de salle existante. Par défaut, les boîtes aux lettres de salle n’ont pas de compte associé, vous devez donc ajouter un compte lorsque vous créez ou modifiez une boîte aux lettres de salle qui lui permet de s’authentifier auprès des systèmes de salle Skype v2.

   - Pour créer une boîte aux lettres de salle, utilisez la syntaxe suivante :

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Cet exemple crée une boîte aux lettres de salle avec les paramètres suivants :

     - Nom : Rigel-01

     - Alias : Rigel1

     - Compte : Rigel1@contoso.onmicrosoft.com

     - Mot de passe du compte : P@ $ $W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Pour modifier une boîte aux lettres de salle existante, utilisez la syntaxe suivante :

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Dans cet exemple, le compte de la boîte aux lettres de salle existante possède la valeur alias Rigel2 et le mot de passe est défini sur 9898P@ $ $W 0rd. Notez que le compte sera Rigel2@contoso.onmicrosoft.com en raison de la valeur de l’alias existant.

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Pour plus d’informations sur les paramètres de syntaxe et de paramètre, voir [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) et [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).


3. Dans Exchange Online PowerShell, configurez les paramètres suivants sur la boîte aux lettres de salle pour améliorer l’interface utilisateur :

   - AutomateProcessing : l’acceptation automatique (les organisateurs de la réunion reçoivent la décision de réservation de salle directement sans intervention humaine : gratuit = accepter ; occupé = refuser.)

   - AddOrganizerToSubject : $false (l’organisateur de la réunion n’est pas ajouté au sujet de la demande de réunion.)

   - DeleteComments : $false (conservez le texte dans le corps des demandes de réunion entrantes).

   - DeleteSubject : $false (conserver le sujet des demandes de réunion entrantes).

   - RemovePrivateProperty : $false (vérifie que l’indicateur privé qui a été envoyé par l’organisateur de la réunion dans la demande de réunion d’origine reste indiqué.)

   - AddAdditionalResponse : $true (le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion.)

   - AdditionalResponse : « il s’agit d’une salle de réunion Skype ! » (Le texte supplémentaire à ajouter à la demande de réunion.)

   Cet exemple configure ces paramètres sur la boîte aux lettres de salle nommée Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Pour obtenir une syntaxe détaillée et des informations relatives aux paramètres, voir [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Connectez-vous à MS Online PowerShell pour créer des paramètres Active Directory en exécutant l’applet de contrôle `Connect-MsolService -Credential $cred` PowerShell.   Pour plus d’informations sur Active Directory, voir [Azure ActiveDirectory (MSONLINE,) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) n’est pas pris en charge. 

5. Si vous ne souhaitez pas que le mot de passe expire, utilisez la syntaxe suivante :

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   Cet exemple définit le mot de passe du compte Rigel1@contoso.onmicrosoft.com pour qu’il n’expire jamais.

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName Rigel1@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   Vous pouvez également définir un numéro de téléphone pour le compte en exécutant la commande suivante :

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. Le compte d’appareil doit avoir une licence Microsoft 365 ou Office 365 valide ou Exchange et Microsoft teams ou Skype entreprise ne fonctionnera pas. Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte. Vous pouvez utiliser`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> pour récupérer la liste des références SKU disponibles pour votre organisation Microsoft 365 ou Office 365, procédez comme suit :

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Vous pouvez ensuite ajouter une licence à l’aide du`Set-MsolUserLicense` <!--Set-AzureADUserLicense --> applet. Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).

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

   Pour obtenir des instructions détaillées, voir [attribuer des licences à des comptes d’utilisateurs avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

7. Ensuite, vous devez activer le compte de l’appareil avec Skype entreprise. Assurez-vous que votre environnement répond à la configuration requise définie dans les [exigences de Microsoft teams salles](requirements.md).

   Démarrez une [session Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) distante comme suit (veillez à [installer les composants PowerShell de Skype entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)) :

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   Activez ensuite votre compte Microsoft teams pour Skype entreprise Server en exécutant l’applet de commande suivante :

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   Obtenez les informations RegistrarPool à partir du nouveau compte d’utilisateur configuré, comme le montre l’exemple suivant :

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > Les nouveaux comptes d’utilisateur ne peuvent pas être créés sur le même pool de bureau d’enregistrement que les comptes d’utilisateurs existants dans le client. Dans le cas présent, la commande ci-dessus empêche les erreurs dans la configuration du compte.

Après avoir suivi les étapes ci-dessous pour activer votre compte Microsoft teams dans Microsoft teams ou Skype entreprise Online, vous devez attribuer une licence à l’appareil Microsoft Teams. À l’aide du centre d’administration Microsoft 365, attribuez une licence Skype entreprise Online (plan 2) ou une licence Skype entreprise Online (plan 3) à l’appareil.

### <a name="assign-a-license-to-your-account"></a>Affectation d’une licence à votre compte

1. Connectez-vous en tant qu’administrateur client, ouvrez le centre d’administration Microsoft 365, puis cliquez sur l’application Administration.

2. Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.

3. Sélectionnez le compte Microsoft teams Room, puis cliquez ou appuyez sur l’icône de stylet, c’est-à-dire modifier.

4. Cliquez sur l’option **Licences**.

5. Dans la section **attribuer des licences** , vous devez sélectionner Skype entreprise Online (plan 2) ou Skype entreprise Online (plan 3), en fonction de votre licence et de ce que vous avez choisi pour l’entreprise. Vous devez utiliser une licence de plan 3 Si vous souhaitez utiliser PBX Cloud sur les salles de Microsoft Teams. Vous aurez au moins besoin de CloudPBX pour la connectivité vocale. Puis, configurez la voix hybride ou la fonction d’appel RTC sur la méthode de connectivité RTC. Pour plus d’informations, consultez la rubrique [licences Microsoft teams](rooms-licensing.md)

6. Cliquez sur **Enregistrer** pour terminer la tâche.

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>Exemple : configuration de compte salle dans Exchange Online et Skype entreprise Online

Commandes PowerShell Exchange Online :

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

Commandes PowerShell d’Azure Active Directory :

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.onmicrosoft.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

Commande PowerShell Skype entreprise :

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> Ceci ajoute CloudPBX et PSTNCallingDomesticAndInternational. Par ailleurs, vous devez utiliser l’interface administrateur pour attribuer un numéro de téléphone.

## <a name="validate"></a>Invalidé

Pour la validation, vous devriez être en mesure d’utiliser n’importe quel client Skype entreprise pour vous connecter au compte que vous avez créé.

## <a name="see-also"></a>Voir aussi

[Configurer des comptes pour les salles de Microsoft teams](rooms-configure-accounts.md)

[Planifier les Salles Microsoft Teams](rooms-plan.md)

[Déployer les Salles Microsoft Teams](rooms-deploy.md)

[Configurer une console des salles Microsoft Teams](console.md)

[Gérer les Salles Microsoft Teams](rooms-manage.md)

[Gestion des licences Microsoft teams](rooms-licensing.md)

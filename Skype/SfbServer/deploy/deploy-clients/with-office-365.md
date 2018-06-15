---
title: Déploiement de Skype Room Systems v2 avec Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lisez cette rubrique pour plus d’informations sur le déploiement de systèmes de salle Skype v2 avec Office 365.
ms.openlocfilehash: bf23da871b3e736bd9fce2ee821b716fc43830b1
ms.sourcegitcommit: 4e9f4e2297cea3372a97f4ea178eb75ba6f8753f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/14/2018
ms.locfileid: "19887904"
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a><span data-ttu-id="adb6d-103">Déploiement de Skype Room Systems v2 avec Office 365 </span><span class="sxs-lookup"><span data-stu-id="adb6d-103">Deploy Skype Room Systems v2 with Office 365</span></span>
 
<span data-ttu-id="adb6d-104">Lisez cette rubrique pour plus d’informations sur le déploiement de systèmes de salle Skype v2 avec Office 365, où Skype pour les entreprises et Exchange sont en ligne.</span><span class="sxs-lookup"><span data-stu-id="adb6d-104">Read this topic for information on how to deploy Skype Room Systems v2 with Office 365, where Skype for Business and Exchange are both online.</span></span> 

<span data-ttu-id="adb6d-105">Pour configurer des comptes d’utilisateurs, la plus simple consiste à configurer à l’aide de Windows PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="adb6d-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="adb6d-106">Microsoft propose [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aide à créer des comptes d’utilisateur ou de valider les comptes de ressource existant dont vous disposez afin de vous aider à les transformer en comptes d’utilisateurs v2 Skype salle systèmes compatibles.</span><span class="sxs-lookup"><span data-stu-id="adb6d-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="adb6d-107">Si vous préférez, vous pouvez suivre les étapes ci-dessous pour configurer les comptes utilisés par votre appareil v2 de systèmes de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="adb6d-107">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-office-365"></a><span data-ttu-id="adb6d-108">Déploiement de Skype Room Systems v2 avec Office 365 </span><span class="sxs-lookup"><span data-stu-id="adb6d-108">Deploy Skype Room Systems v2 with Office 365</span></span>

<span data-ttu-id="adb6d-109">Avant de déployer des systèmes de salle Skype v2 avec Office 365, assurez-vous que vous remplissez les conditions.</span><span class="sxs-lookup"><span data-stu-id="adb6d-109">Before you deploy Skype Room Systems v2 with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="adb6d-110">Pour plus d’informations, voir [v2 Skype salle requise](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="adb6d-110">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="adb6d-111">Pour activer Skype pour les entreprises, vous devez disposer les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="adb6d-111">To enable Skype for Business, you must have the following:</span></span>
  
- <span data-ttu-id="adb6d-112">Skype pour Business Online (Plan 2) ou supérieure dans votre plan Office 365.</span><span class="sxs-lookup"><span data-stu-id="adb6d-112">Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="adb6d-113">Le plan doit prendre en charge la fonctionnalité de conférence.</span><span class="sxs-lookup"><span data-stu-id="adb6d-113">The plan needs to support conferencing capability.</span></span>
    
- <span data-ttu-id="adb6d-114">Si vous avez besoin d’Enterprise Voice (téléphonie TLS) à l’aide de fournisseurs de services de téléphonie pour les systèmes de salle Skype v2 vous devez Skype pour Business Online (Plan 3).</span><span class="sxs-lookup"><span data-stu-id="adb6d-114">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Skype Room Systems v2 you need Skype for Business Online (Plan 3).</span></span>
    
- <span data-ttu-id="adb6d-115">Les utilisateurs de client doivent avoir des boîtes aux lettres Exchange.</span><span class="sxs-lookup"><span data-stu-id="adb6d-115">Your tenant users must have Exchange mailboxes.</span></span>
    
- <span data-ttu-id="adb6d-116">Votre compte v2 de systèmes de salle Skype requiert Skype pour Business Online (Plan 2) ni Skype licence entreprise Online (Plan 3), mais il ne nécessite pas une licence Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="adb6d-116">Your Skype Room Systems v2 account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>
    
### <a name="add-a-device-account"></a><span data-ttu-id="adb6d-117">Ajout d’un compte d’appareil</span><span class="sxs-lookup"><span data-stu-id="adb6d-117">Add a device account</span></span>

1. <span data-ttu-id="adb6d-118">Démarrer une session Windows PowerShell à distance sur un PC et se connecter à Exchange.</span><span class="sxs-lookup"><span data-stu-id="adb6d-118">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="adb6d-119">Assurez-vous de disposer des autorisations adéquates pour exécuter les applets de commande associées.</span><span class="sxs-lookup"><span data-stu-id="adb6d-119">Be sure you have the right permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="adb6d-120">Voici quelques exemples d’applets de commande pouvant être utilisés et modifiés dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="adb6d-120">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential 
   $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. <span data-ttu-id="adb6d-121">Après avoir établi une session, vous allez créer une nouvelle boîte aux lettres et activer comme un RoomMailboxAccount, soit modifier les paramètres d’une boîte aux lettres de salle existante.</span><span class="sxs-lookup"><span data-stu-id="adb6d-121">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="adb6d-122">Ainsi, le compte de s’authentifier sur les systèmes de salle Skype v2.</span><span class="sxs-lookup"><span data-stu-id="adb6d-122">This will allow the account to authenticate to Skype Room Systems v2.</span></span>
    
  <span data-ttu-id="adb6d-123">Si vous modifiez une boîte aux lettre de ressource :</span><span class="sxs-lookup"><span data-stu-id="adb6d-123">If you are changing an existing resource mailbox:</span></span>
    
```
Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

  <span data-ttu-id="adb6d-124">Si vous créez une nouvelle boîte aux lettres de ressources :</span><span class="sxs-lookup"><span data-stu-id="adb6d-124">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 
-Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="adb6d-p106">Plusieurs propriétés Exchange doivent être définies sur le compte d’appareil pour optimiser l’expérience de réunion. Vous pouvez consulter les propriétés qui doivent être définies dans la section Propriétés Exchange.</span><span class="sxs-lookup"><span data-stu-id="adb6d-p106">Various Exchange properties must be set on the device account to improve the meeting experience. You can see which properties need to be set in the Exchange properties section.</span></span>
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
   -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

   ```

4. <span data-ttu-id="adb6d-127">Vous devrez vous connecter à Azure Active Directory pour appliquer certains paramètres de compte.</span><span class="sxs-lookup"><span data-stu-id="adb6d-127">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="adb6d-128">Pour vous connecter à Azure AD, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="adb6d-128">To connect to Azure AD, run the following cmdlet:</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

5. <span data-ttu-id="adb6d-129">	Pour empêcher l’expiration du mot de passe, exécutez l’applet de commande Set-MsolUser cmdlet avec l’option Le mot de passe n’expire jamais, comme suit :  </span><span class="sxs-lookup"><span data-stu-id="adb6d-129">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
   ```

   <span data-ttu-id="adb6d-130">Vous pouvez également définir un numéro de téléphone pour la salle comme suit :</span><span class="sxs-lookup"><span data-stu-id="adb6d-130">You can also set a phone number for the room as follows:</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

6. <span data-ttu-id="adb6d-131">Le compte de l’appareil doit avoir une licence Office 365 ou Exchange et Skype pour les entreprises ne fonctionnent pas.</span><span class="sxs-lookup"><span data-stu-id="adb6d-131">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="adb6d-132">Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte.</span><span class="sxs-lookup"><span data-stu-id="adb6d-132">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="adb6d-133">Vous pouvez utiliser Get-MsolAccountSku pour récupérer une liste de références disponibles pour votre client Office 365 comme suit :</span><span class="sxs-lookup"><span data-stu-id="adb6d-133">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>
    
   ```
   Get-MsolAccountSku
   ```

   <span data-ttu-id="adb6d-p109">Puis, vous pouvez ajouter une licence à l’aide de l’applet de commande Set-MsolUserLicense. Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="adb6d-p109">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

7. <span data-ttu-id="adb6d-136">Ensuite, vous devez activer le compte de l’appareil avec Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="adb6d-136">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="adb6d-137">Assurez-vous que votre environnement répond aux exigences définies dans [v2 Skype salle requise](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="adb6d-137">Be sure your environment meets the requirements defined in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
    
   <span data-ttu-id="adb6d-138">Démarrer une session Windows PowerShell à distance comme suit (veillez à installer Skype pour les composants Business Online PowerShell) :</span><span class="sxs-lookup"><span data-stu-id="adb6d-138">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="adb6d-139">Ensuite, activer votre compte v2 de systèmes de salle Skype pour Skype pour Business Server en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="adb6d-139">Next, enable your Skype Room Systems v2 account for Skype for Business Server by running the following cmdlet:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="adb6d-140">Obtenir les informations de RegistrarPool à partir du nouveau compte d’utilisateur en cours d’installation, comme indiqué dans cet exemple :</span><span class="sxs-lookup"><span data-stu-id="adb6d-140">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>
    
    ```
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="adb6d-141">Nouveaux comptes d’utilisateur ne peuvent pas être créés sur le même pool de serveurs d’inscriptions en tant que comptes d’utilisateurs existants dans le client.</span><span class="sxs-lookup"><span data-stu-id="adb6d-141">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="adb6d-142">La commande ci-dessus empêchera les erreurs de configuration de compte en raison de cette situation.</span><span class="sxs-lookup"><span data-stu-id="adb6d-142">The command above will prevent errors in account setup due to this situation.</span></span> 
  
<span data-ttu-id="adb6d-143">Une fois que vous avez terminé les étapes précédentes pour activer votre compte Skype salle systèmes v2 Skype pour Business Online, vous devez attribuer une licence à un appareil v2 de systèmes de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="adb6d-143">After you've completed the preceding steps to enable your Skype Room Systems v2 account in Skype for Business Online, you need to assign a license to Skype Room Systems v2 device.</span></span> <span data-ttu-id="adb6d-144">À l’aide du portail d’administration d’Office 365, assignez un soit Skype Business Online (Plan 2) ou une Skype licence entreprise Online (Plan 3) à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="adb6d-144">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>
  
### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="adb6d-145">Affectation d’une licence à votre compte</span><span class="sxs-lookup"><span data-stu-id="adb6d-145">Assign a license to your account</span></span>

1. <span data-ttu-id="adb6d-146">Ouverture de session en tant qu’un administrateur client, ouvrez le portail d’administration d’Office 365, puis cliquez sur l’application d’administration.</span><span class="sxs-lookup"><span data-stu-id="adb6d-146">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="adb6d-147">Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.</span><span class="sxs-lookup"><span data-stu-id="adb6d-147">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="adb6d-148">Sélectionnez le compte v2 Skype salle systèmes, puis cliquez ou appuyez sur l’icône crayon, ce qui signifie que modifier.</span><span class="sxs-lookup"><span data-stu-id="adb6d-148">Select the Skype Room Systems v2 account, and then click or tap the pen icon, which means edit.</span></span>
    
4. <span data-ttu-id="adb6d-149">Cliquez sur l’option **Licences**.</span><span class="sxs-lookup"><span data-stu-id="adb6d-149">Click on the **Licenses** option.</span></span>
    
5. <span data-ttu-id="adb6d-150">Dans la section **attribution de licences** , vous devez sélectionner Skype pour Business Online (Plan 2) ou Skype pour Business Online (Plan 3), en fonction de vos licences et vous avez décidé en termes de devoir Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="adb6d-150">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="adb6d-151">Vous devrez utiliser une licence 3 planifier si vous souhaitez utiliser dans le nuage PBX sur Skype salle systèmes v2.</span><span class="sxs-lookup"><span data-stu-id="adb6d-151">You'll have to use a Plan 3 license if you want to use Cloud PBX on Skype Room Systems v2.</span></span> <span data-ttu-id="adb6d-152">Vous aurez au moins besoin de CloudPBX pour la connectivité vocale.</span><span class="sxs-lookup"><span data-stu-id="adb6d-152">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="adb6d-153">Puis, configurez la voix hybride ou la fonction d’appel RTC sur la méthode de connectivité RTC.</span><span class="sxs-lookup"><span data-stu-id="adb6d-153">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span>
    
6. <span data-ttu-id="adb6d-154">Cliquez sur **Enregistrer** pour terminer la tâche.</span><span class="sxs-lookup"><span data-stu-id="adb6d-154">Click **Save** to complete the task.</span></span>
    
## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="adb6d-155">Exemple : Compte salle du programme d’installation dans Exchange Online et Skype pour Business Online</span><span class="sxs-lookup"><span data-stu-id="adb6d-155">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

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
> <span data-ttu-id="adb6d-p114">Ceci ajoute CloudPBX et PSTNCallingDomesticAndInternational. De plus, vous devrez utiliser l’interface administrative pour affecter un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="adb6d-p114">This adds CloudPBX and PSTNCallingDomesticAndInternational. Addtionally, you will need to use the Admin interface to assign a phone number.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="adb6d-158">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="adb6d-158">See also</span></span>

[<span data-ttu-id="adb6d-159">Configurer des comptes pour les systèmes de salle Skype v2</span><span class="sxs-lookup"><span data-stu-id="adb6d-159">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="adb6d-160">Planifier la salle Skype systèmes v2</span><span class="sxs-lookup"><span data-stu-id="adb6d-160">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="adb6d-161">Déployer la salle Skype systèmes v2</span><span class="sxs-lookup"><span data-stu-id="adb6d-161">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="adb6d-162">Configurer une console v2 de systèmes de salle de Skype</span><span class="sxs-lookup"><span data-stu-id="adb6d-162">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="adb6d-163">Gérer les salles Skype systèmes v2</span><span class="sxs-lookup"><span data-stu-id="adb6d-163">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)


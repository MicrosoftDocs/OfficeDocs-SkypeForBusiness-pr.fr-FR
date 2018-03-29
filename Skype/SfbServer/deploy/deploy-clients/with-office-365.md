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
# <a name="deploy-skype-room-systems-v2-with-office-365"></a><span data-ttu-id="72c35-103">Déploiement de Skype Room Systems v2 avec Office 365 </span><span class="sxs-lookup"><span data-stu-id="72c35-103">Deploy Skype Room Systems v2 with Office 365</span></span>
 
<span data-ttu-id="72c35-104">Lisez cette rubrique pour plus d’informations sur le déploiement de v2 Skype salle systèmes avec Office 365.</span><span class="sxs-lookup"><span data-stu-id="72c35-104">Read this topic for information on how to deploy Skype Room Systems v2 with Office 365.</span></span>
  
<span data-ttu-id="72c35-105">Cette rubrique décrit comment ajouter un compte de dispositif pour systèmes de salle Skype v2 lorsque vous disposez d’un déploiement en ligne d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="72c35-105">This topic describes how to add a device account for Skype Room Systems v2 when you have an Office 365 online deployment.</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-office-365"></a><span data-ttu-id="72c35-106">Déploiement de Skype Room Systems v2 avec Office 365 </span><span class="sxs-lookup"><span data-stu-id="72c35-106">Deploy Skype Room Systems v2 with Office 365</span></span>

<span data-ttu-id="72c35-107">Avant de déployer v2 Skype salle systèmes avec Office 365, veillez à ce que vous avez satisfait les exigences.</span><span class="sxs-lookup"><span data-stu-id="72c35-107">Before you deploy Skype Room Systems v2 with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="72c35-108">Pour plus d’informations, consultez [v2 Skype pièce requise](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72c35-108">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="72c35-109">Pour activer Skype pour entreprise, vous devez disposer des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="72c35-109">To enable Skype for Business, you must have the following:</span></span>
  
- <span data-ttu-id="72c35-110">Skype pour Business Online (Plan 2) ou version ultérieure dans votre plan d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="72c35-110">Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="72c35-111">Le plan doit prendre en charge la fonctionnalité de conférence.</span><span class="sxs-lookup"><span data-stu-id="72c35-111">The plan needs to support conferencing capability.</span></span>
    
- <span data-ttu-id="72c35-112">Si vous avez besoin de Voix Entreprise (téléphonie RTPC) à l’aide des fournisseurs de service de téléphonie pour systèmes de salle Skype v2 vous devez Skype pour Business Online (Plan 3).</span><span class="sxs-lookup"><span data-stu-id="72c35-112">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Skype Room Systems v2 you need Skype for Business Online (Plan 3).</span></span>
    
- <span data-ttu-id="72c35-113">Les utilisateurs de clients doivent avoir des boîtes aux lettres Exchange.</span><span class="sxs-lookup"><span data-stu-id="72c35-113">Your tenant users must have Exchange mailboxes.</span></span>
    
- <span data-ttu-id="72c35-114">Votre compte v2 de systèmes de salle Skype nécessite Skype pour Business Online (Plan 2) ni Skype pour licence Business Online (Plan 3), mais il ne nécessite pas une licence Exchange en ligne.</span><span class="sxs-lookup"><span data-stu-id="72c35-114">Your Skype Room Systems v2 account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>
    
### <a name="add-a-device-account"></a><span data-ttu-id="72c35-115">Ajout d’un compte d’appareil</span><span class="sxs-lookup"><span data-stu-id="72c35-115">Add a device account</span></span>

1. <span data-ttu-id="72c35-116">Démarrer une session à distance de Windows PowerShell sur un PC et se connecter à Exchange.</span><span class="sxs-lookup"><span data-stu-id="72c35-116">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="72c35-117">Assurez-vous de disposer des autorisations adéquates pour exécuter les applets de commande associées.</span><span class="sxs-lookup"><span data-stu-id="72c35-117">Be sure you have the right permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="72c35-118">Voici quelques exemples d’applets de commande pouvant être utilisés et modifiés dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="72c35-118">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential 
   $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. <span data-ttu-id="72c35-119">Après l’établissement d’une session, vous allez créer une nouvelle boîte aux lettres et activer comme un RoomMailboxAccount, soit modifier les paramètres d’une boîte aux lettres de salle existante.</span><span class="sxs-lookup"><span data-stu-id="72c35-119">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="72c35-120">Ainsi, le compte pour s’authentifier sur des systèmes de salle Skype v2.</span><span class="sxs-lookup"><span data-stu-id="72c35-120">This will allow the account to authenticate to Skype Room Systems v2.</span></span>
    
  <span data-ttu-id="72c35-121">Si vous modifiez une boîte aux lettre de ressource :</span><span class="sxs-lookup"><span data-stu-id="72c35-121">If you are changing an existing resource mailbox:</span></span>
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

  <span data-ttu-id="72c35-122">Si vous créez une nouvelle boîte aux lettres de ressources :</span><span class="sxs-lookup"><span data-stu-id="72c35-122">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 
-Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="72c35-p105">Plusieurs propriétés Exchange doivent être définies sur le compte d’appareil pour optimiser l’expérience de réunion. Vous pouvez consulter les propriétés qui doivent être définies dans la section Propriétés Exchange.</span><span class="sxs-lookup"><span data-stu-id="72c35-p105">Various Exchange properties must be set on the device account to improve the meeting experience. You can see which properties need to be set in the Exchange properties section.</span></span>
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
   -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

   ```

4. <span data-ttu-id="72c35-125">Vous devrez vous connecter à Azure Active Directory pour appliquer certains paramètres de compte.</span><span class="sxs-lookup"><span data-stu-id="72c35-125">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="72c35-126">Pour vous connecter à Azure AD, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="72c35-126">To connect to Azure AD, run the following cmdlet:</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

5. <span data-ttu-id="72c35-127">	Pour empêcher l’expiration du mot de passe, exécutez l’applet de commande Set-MsolUser cmdlet avec l’option Le mot de passe n’expire jamais, comme suit :  </span><span class="sxs-lookup"><span data-stu-id="72c35-127">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
   ```

   <span data-ttu-id="72c35-128">Vous pouvez également définir un numéro de téléphone pour la salle comme suit :</span><span class="sxs-lookup"><span data-stu-id="72c35-128">You can also set a phone number for the room as follows:</span></span>
    
   ```
   Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
   ```

6. <span data-ttu-id="72c35-129">Le compte de périphérique doit posséder une licence valide de Office 365, ou Exchange et Skype pour entreprise ne fonctionneront pas.</span><span class="sxs-lookup"><span data-stu-id="72c35-129">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="72c35-130">Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte.</span><span class="sxs-lookup"><span data-stu-id="72c35-130">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="72c35-131">Vous pouvez utiliser Get-MsolAccountSku pour récupérer une liste de références disponibles pour vos clients d’Office 365, comme suit :</span><span class="sxs-lookup"><span data-stu-id="72c35-131">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>
    
   ```
   Get-MsolAccountSku
   ```

   <span data-ttu-id="72c35-p108">Puis, vous pouvez ajouter une licence à l’aide de l’applet de commande Set-MsolUserLicense. Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="72c35-p108">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

7. <span data-ttu-id="72c35-134">Ensuite, vous devez activer le compte de dispositif avec Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="72c35-134">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="72c35-135">Assurez-vous que votre environnement répond aux exigences définies dans les [exigences en matière de systèmes de salle Skype v2](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72c35-135">Be sure your environment meets the requirements defined in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
    
   <span data-ttu-id="72c35-136">Démarrez une session Windows PowerShell à distance comme suit (veillez à installer Skype pour les composants Business Online PowerShell) :</span><span class="sxs-lookup"><span data-stu-id="72c35-136">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="72c35-137">Ensuite, activez votre compte v2 de systèmes de salle de Skype pour Skype pour Business Server en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="72c35-137">Next, enable your Skype Room Systems v2 account for Skype for Business Server by running the following cmdlet:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="72c35-138">Obtenir les informations RegistrarPool de nouveau compte d’utilisateur en cours d’installation, comme indiqué dans cet exemple :</span><span class="sxs-lookup"><span data-stu-id="72c35-138">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>
    
    ```
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="72c35-139">Nouveaux comptes d’utilisateurs ne soient pas créées dans le même pool de Registre en tant que comptes d’utilisateur existants dans le locataire.</span><span class="sxs-lookup"><span data-stu-id="72c35-139">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="72c35-140">La commande ci-dessus évitera que des erreurs dans le programme d’installation de compte en raison de cette situation.</span><span class="sxs-lookup"><span data-stu-id="72c35-140">The command above will prevent errors in account setup due to this situation.</span></span> 
  
<span data-ttu-id="72c35-141">Une fois que vous avez terminé les étapes précédentes pour activer votre compte de v2 de systèmes de salle Skype dans Skype pour professionnels en ligne, vous devez attribuer une licence à dispositif de systèmes de salle Skype v2.</span><span class="sxs-lookup"><span data-stu-id="72c35-141">After you've completed the preceding steps to enable your Skype Room Systems v2 account in Skype for Business Online, you need to assign a license to Skype Room Systems v2 device.</span></span> <span data-ttu-id="72c35-142">À l’aide du portail d’administration d’Office 365, affecter soit un Skype d’entreprise en ligne (Plan 2) ou un Skype pour licence Business Online (Plan 3) pour le périphérique.</span><span class="sxs-lookup"><span data-stu-id="72c35-142">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>
  
### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="72c35-143">Affectation d’une licence à votre compte</span><span class="sxs-lookup"><span data-stu-id="72c35-143">Assign a license to your account</span></span>

1. <span data-ttu-id="72c35-144">Connexion en tant qu’un administrateur de clients, ouvrez le portail d’administration de Office 365 et cliquez sur l’application d’administration.</span><span class="sxs-lookup"><span data-stu-id="72c35-144">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="72c35-145">Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.</span><span class="sxs-lookup"><span data-stu-id="72c35-145">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="72c35-146">Sélectionnez le compte de v2 Skype salle systèmes, puis cliquez sur ou cliquez sur l’icône de plume, ce qui signifie modifier.</span><span class="sxs-lookup"><span data-stu-id="72c35-146">Select the Skype Room Systems v2 account, and then click or tap the pen icon, which means edit.</span></span>
    
4. <span data-ttu-id="72c35-147">Cliquez sur l’option **Licences**.</span><span class="sxs-lookup"><span data-stu-id="72c35-147">Click on the **Licenses** option.</span></span>
    
5. <span data-ttu-id="72c35-148">Dans la section **attribution de licences** , vous devez sélectionner Skype pour Business Online (Plan 2) ou Skype pour Business Online (Plan 3), en fonction de votre licence et que vous avez décidé en ayant besoin de Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="72c35-148">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="72c35-149">Vous devrez utiliser une licence 3 de Plan si vous souhaitez utiliser le nuage PBX sur les systèmes de salle Skype v2.</span><span class="sxs-lookup"><span data-stu-id="72c35-149">You'll have to use a Plan 3 license if you want to use Cloud PBX on Skype Room Systems v2.</span></span> <span data-ttu-id="72c35-150">Vous aurez au moins besoin de CloudPBX pour la connectivité vocale.</span><span class="sxs-lookup"><span data-stu-id="72c35-150">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="72c35-151">Puis, configurez la voix hybride ou la fonction d’appel RTC sur la méthode de connectivité RTC.</span><span class="sxs-lookup"><span data-stu-id="72c35-151">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span>
    
6. <span data-ttu-id="72c35-152">Cliquez sur **Enregistrer** pour terminer la tâche.</span><span class="sxs-lookup"><span data-stu-id="72c35-152">Click **Save** to complete the task.</span></span>
    
## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="72c35-153">Exemple : Compte de l’espace d’installation dans Exchange Online et Skype pour professionnels en ligne</span><span class="sxs-lookup"><span data-stu-id="72c35-153">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

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
> <span data-ttu-id="72c35-p113">Ceci ajoute CloudPBX et PSTNCallingDomesticAndInternational. De plus, vous devrez utiliser l’interface administrative pour affecter un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="72c35-p113">This adds CloudPBX and PSTNCallingDomesticAndInternational. Addtionally, you will need to use the Admin interface to assign a phone number.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="72c35-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="72c35-156">See also</span></span>

#### 

[<span data-ttu-id="72c35-157">Plan de salle de Skype systèmes v2</span><span class="sxs-lookup"><span data-stu-id="72c35-157">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="72c35-158">Déployer Skype salle systèmes v2</span><span class="sxs-lookup"><span data-stu-id="72c35-158">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="72c35-159">Configurer une console v2 de systèmes de salle de Skype</span><span class="sxs-lookup"><span data-stu-id="72c35-159">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="72c35-160">Gérer l’espace de Skype systèmes v2</span><span class="sxs-lookup"><span data-stu-id="72c35-160">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)


---
title: Déployer les équipes Microsoft salles avec Exchange Online
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
- M365-voice
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Lisez cette rubrique pour plus d’informations sur la façon de déployer Microsoft équipes salles avec Exchange Online.
ms.openlocfilehash: 4bff1fb6adce254608aa9286ec080cf6677c1a48
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214827"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="bf133-103">Déployer les équipes Microsoft salles avec Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bf133-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="bf133-104">Lisez cette rubrique pour plus d’informations sur la façon de déployer les salles d’équipes Microsoft avec Exchange Online et Skype pour Business Server local.</span><span class="sxs-lookup"><span data-stu-id="bf133-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="bf133-105">Si votre organisation possède un mélange de services, avec une poignée hébergés sur site et certaines hébergées en ligne, votre configuration dépendra où se trouve chaque service.</span><span class="sxs-lookup"><span data-stu-id="bf133-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="bf133-106">Cette rubrique traite des déploiements hybrides pour les salles d’équipes Microsoft avec Exchange hébergé en ligne.</span><span class="sxs-lookup"><span data-stu-id="bf133-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="bf133-107">Il existe de nombreuses différentes variantes dans ce type de déploiement, il n’est pas possible de fournir des instructions détaillées pour toutes les.</span><span class="sxs-lookup"><span data-stu-id="bf133-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="bf133-108">Le processus suivant fonctionnera pour de nombreuses configurations.</span><span class="sxs-lookup"><span data-stu-id="bf133-108">The following process will work for many configurations.</span></span> <span data-ttu-id="bf133-109">Si le processus n’est pas bon choix pour votre configuration, nous vous recommandons d’utiliser Windows PowerShell pour atteindre le même résultat final, comme indiqué ici et pour d’autres options de déploiement.</span><span class="sxs-lookup"><span data-stu-id="bf133-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="bf133-110">Pour configurer des comptes d’utilisateurs, la plus simple consiste à configurer à l’aide de Windows PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="bf133-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="bf133-111">Microsoft propose [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aide à créer des comptes d’utilisateur ou de valider les comptes de ressource existant dont vous disposez afin de vous aider à les transformer en comptes d’utilisateurs locaux des équipes Microsoft compatibles.</span><span class="sxs-lookup"><span data-stu-id="bf133-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="bf133-112">Si vous préférez, vous pouvez suivre les étapes ci-dessous pour configurer les comptes utilisés par votre périphérique Microsoft équipes salles.</span><span class="sxs-lookup"><span data-stu-id="bf133-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="bf133-113">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="bf133-113">Requirements</span></span>

<span data-ttu-id="bf133-114">Avant de déployer Microsoft équipes salles avec Exchange Online, assurez-vous que vous remplissez les conditions.</span><span class="sxs-lookup"><span data-stu-id="bf133-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="bf133-115">Pour plus d’informations, consultez [Configuration requise de salles d’équipes Microsoft](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf133-115">For more information, see [Microsoft Teams Rooms requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="bf133-116">Pour déployer Microsoft équipes salles avec Exchange Online, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="bf133-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="bf133-117">Assurez-vous de disposer des autorisations adéquates pour exécuter les applets de commande associées.</span><span class="sxs-lookup"><span data-stu-id="bf133-117">Be sure you have the right permissions to run the associated cmdlets.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="bf133-118">Création d’un compte et définition des propriétés Exchange</span><span class="sxs-lookup"><span data-stu-id="bf133-118">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="bf133-119">Démarrer une session Windows PowerShell à distance sur un PC et se connecter à Exchange Online comme suit :</span><span class="sxs-lookup"><span data-stu-id="bf133-119">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. <span data-ttu-id="bf133-120">Après avoir établi une session, vous allez créer une nouvelle boîte aux lettres et activer comme un RoomMailboxAccount, soit modifier les paramètres d’une boîte aux lettres de salle existante.</span><span class="sxs-lookup"><span data-stu-id="bf133-120">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="bf133-121">Ainsi, le compte d’authentification dans les salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bf133-121">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="bf133-122">Si vous modifiez une boîte aux lettres de ressource :</span><span class="sxs-lookup"><span data-stu-id="bf133-122">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="bf133-123">Si vous créez une nouvelle boîte aux lettres de ressources :</span><span class="sxs-lookup"><span data-stu-id="bf133-123">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="bf133-124">Pour améliorer l’expérience de réunion, vous devez définir les propriétés Exchange sur le compte d’utilisateur comme suit :</span><span class="sxs-lookup"><span data-stu-id="bf133-124">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="bf133-125">Ajout d’une adresse e-mail pour votre compte de domaine sur site</span><span class="sxs-lookup"><span data-stu-id="bf133-125">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="bf133-126">Dans l’outil **Active Directory utilisateurs et ordinateurs Active Directory** , avec le bouton droit sur le conteneur ou l’unité d’organisation que vos salles d’équipes Microsoft comptes seront créés, cliquez sur **Nouveau**, puis cliquez sur **utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="bf133-126">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="bf133-127">Tapez le nom complet (-Identity) à partir de la cmdlet préalable (Set-Mailbox ou New-Mailbox) dans la zone **nom complet** et l’alias dans la zone **nom d’ouverture de session utilisateur** .</span><span class="sxs-lookup"><span data-stu-id="bf133-127">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="bf133-128">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bf133-128">Click **Next**.</span></span>
3. <span data-ttu-id="bf133-p107">Saisissez le mot de passe de ce compte. Vous devrez le saisir à nouveau à des fins de vérification. Vérifiez que seule l’option **Le mot de passe n’expire jamais** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="bf133-p107">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bf133-132">Sélection de **mot de passe n’expire jamais** est une condition requise pour Skype pour Business Server dans les salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bf133-132">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="bf133-133">Il est possible que des règles de votre domaine interdisent la non-expiration des mots de passe.</span><span class="sxs-lookup"><span data-stu-id="bf133-133">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="bf133-134">Dans ce cas, vous devez créer une exception pour chaque compte d’utilisateur locaux des équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bf133-134">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="bf133-135">Cliquez sur **Terminer** pour créer le compte.</span><span class="sxs-lookup"><span data-stu-id="bf133-135">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="bf133-p109">Une fois le compte créé, exécutez une synchronisation de répertoire. À l’issue de cette opération, accédez à la page d’utilisateurs et vérifiez que les deux comptes créés lors des étapes précédentes sont fusionnés.</span><span class="sxs-lookup"><span data-stu-id="bf133-p109">After you've created the account, run a directory synchronization. When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="bf133-138">Affectation d’une licence Office 365</span><span class="sxs-lookup"><span data-stu-id="bf133-138">Assign an Office 365 license</span></span>

1. <span data-ttu-id="bf133-139">Tout d’abord, connectez-vous à Azure AD pour appliquer des paramètres de compte.</span><span class="sxs-lookup"><span data-stu-id="bf133-139">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="bf133-140">Pour vous connecter, vous pouvez exécuter l’applet de commande suivante.</span><span class="sxs-lookup"><span data-stu-id="bf133-140">You can run this cmdlet to connect.</span></span>

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

2. <span data-ttu-id="bf133-141">Le compte d’utilisateur doit disposer d’une licence Office 365 valide pour vous assurer que Exchange et Skype pour Business Server fonctionnera.</span><span class="sxs-lookup"><span data-stu-id="bf133-141">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="bf133-142">Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’utilisateur ; cela permet de déterminer les SKU de licence disponibles pour votre compte.</span><span class="sxs-lookup"><span data-stu-id="bf133-142">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="bf133-143">Vous effectuerez l’affectation à une étape suivante.</span><span class="sxs-lookup"><span data-stu-id="bf133-143">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="bf133-144">Ensuite, utilisez`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="bf133-144">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="bf133-145">pour récupérer une liste de références disponibles pour votre client Office 365.</span><span class="sxs-lookup"><span data-stu-id="bf133-145">to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
4. <span data-ttu-id="bf133-146">Une fois que vous répertoriez les références, vous pouvez ajouter une licence à l’aide du`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="bf133-146">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="bf133-147">applet de commande.</span><span class="sxs-lookup"><span data-stu-id="bf133-147">cmdlet.</span></span> <span data-ttu-id="bf133-148">Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="bf133-148">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

  ```
    Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```
<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="bf133-149">Activer le compte d’utilisateur avec Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="bf133-149">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="bf133-150">Créez une session Windows PowerShell à distance à partir d’un PC comme suit :</span><span class="sxs-lookup"><span data-stu-id="bf133-150">Create a remote Windows PowerShell session from a PC as follows:</span></span>

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="bf133-151">Pour activer votre compte Microsoft équipes salles pour Skype pour Business Server, exécutez cette commande :</span><span class="sxs-lookup"><span data-stu-id="bf133-151">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="bf133-152">Si vous ne savez pas quelle valeur utiliser pour le paramètre RegistrarPool dans votre environnement, vous pouvez obtenir la valeur d’un Skype pour utilisateur Business Server à l’aide de cette commande existante</span><span class="sxs-lookup"><span data-stu-id="bf133-152">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="bf133-153">Affecter un Skype licence Business Server à votre compte Microsoft équipes salles</span><span class="sxs-lookup"><span data-stu-id="bf133-153">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="bf133-154">Connectez-vous en tant qu’administrateur client, ouvrez le portail d’administration d’Office 365 et cliquez sur l’application d’administration.</span><span class="sxs-lookup"><span data-stu-id="bf133-154">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="bf133-155">Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.</span><span class="sxs-lookup"><span data-stu-id="bf133-155">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="bf133-156">Cliquez sur le compte de salles d’équipes Microsoft, puis cliquez sur l’icône du crayon pour modifier les informations de compte.</span><span class="sxs-lookup"><span data-stu-id="bf133-156">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="bf133-157">Cliquez sur **Licences**.</span><span class="sxs-lookup"><span data-stu-id="bf133-157">Click **Licenses**.</span></span>
5. <span data-ttu-id="bf133-158">Dans la zone **Attribuer des licences**, sélectionnez Skype Entreprise (Plan 2) ou Skype Entreprise (Plan 3), en fonction de vos conditions de licence et Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="bf133-158">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="bf133-159">Vous devrez utiliser une licence 3 planifier si vous souhaitez utiliser Enterprise Voice dans les salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bf133-159">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="bf133-160">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="bf133-160">Click **Save**.</span></span>

<span data-ttu-id="bf133-161">Pour la validation, vous devez être en mesure d’utiliser n’importe quel Skype pour client d’entreprise pour vous connecter à ce compte.</span><span class="sxs-lookup"><span data-stu-id="bf133-161">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bf133-162">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bf133-162">See also</span></span>

[<span data-ttu-id="bf133-163">Configurer des comptes pour les salles d’équipes Microsoft</span><span class="sxs-lookup"><span data-stu-id="bf133-163">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="bf133-164">Planifier des équipes Microsoft salles</span><span class="sxs-lookup"><span data-stu-id="bf133-164">Plan for Microsoft Teams Rooms</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="bf133-165">Déployer les équipes Microsoft salles</span><span class="sxs-lookup"><span data-stu-id="bf133-165">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="bf133-166">Configurer une console Microsoft équipes salles</span><span class="sxs-lookup"><span data-stu-id="bf133-166">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="bf133-167">Gérer Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="bf133-167">Manage Microsoft Teams Rooms</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

---
title: Déploiement de Skype Room Systems v2 avec Exchange Online
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Lisez cette rubrique pour plus d’informations sur le déploiement de systèmes de salle Skype v2 avec Exchange Online.
ms.openlocfilehash: b413168d04123256472e6d01cb8cd1858619a714
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20974671"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-online"></a><span data-ttu-id="06ae0-103">Déploiement de Skype Room Systems v2 avec Exchange Online</span><span class="sxs-lookup"><span data-stu-id="06ae0-103">Deploy Skype Room Systems v2 with Exchange Online</span></span> 
 
<span data-ttu-id="06ae0-104">Lisez cette rubrique pour plus d’informations sur la façon de déployer v2 de systèmes de salle Skype avec Exchange Online et Skype pour Business Server local.</span><span class="sxs-lookup"><span data-stu-id="06ae0-104">Read this topic for information on how to deploy Skype Room Systems v2 with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="06ae0-105">Si votre organisation possède un mélange de services, avec une poignée hébergés sur site et certaines hébergées en ligne, votre configuration dépendra où se trouve chaque service.</span><span class="sxs-lookup"><span data-stu-id="06ae0-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="06ae0-106">Cette rubrique traite des déploiements hybrides pour systèmes de salle Skype v2 avec Exchange hébergé en ligne.</span><span class="sxs-lookup"><span data-stu-id="06ae0-106">This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted online.</span></span> <span data-ttu-id="06ae0-107">Il existe de nombreuses différentes variantes dans ce type de déploiement, il n’est pas possible de fournir des instructions détaillées pour toutes les.</span><span class="sxs-lookup"><span data-stu-id="06ae0-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="06ae0-108">Le processus suivant fonctionnera pour de nombreuses configurations.</span><span class="sxs-lookup"><span data-stu-id="06ae0-108">The following process will work for many configurations.</span></span> <span data-ttu-id="06ae0-109">Si le processus n’est pas bon choix pour votre configuration, nous vous recommandons d’utiliser Windows PowerShell pour atteindre le même résultat final, comme indiqué ici et pour d’autres options de déploiement.</span><span class="sxs-lookup"><span data-stu-id="06ae0-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span> 

<span data-ttu-id="06ae0-110">Pour configurer des comptes d’utilisateurs, la plus simple consiste à configurer à l’aide de Windows PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="06ae0-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="06ae0-111">Microsoft propose [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aide à créer des comptes d’utilisateur ou de valider les comptes de ressource existant dont vous disposez afin de vous aider à les transformer en comptes d’utilisateurs v2 Skype salle systèmes compatibles.</span><span class="sxs-lookup"><span data-stu-id="06ae0-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="06ae0-112">Si vous préférez, vous pouvez suivre les étapes ci-dessous pour configurer les comptes utilisés par votre appareil v2 de systèmes de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="06ae0-112">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>


  
## <a name="deploy-skype-room-systems-v2-with-exchange-online"></a><span data-ttu-id="06ae0-113">Déploiement de Skype Room Systems v2 avec Exchange Online</span><span class="sxs-lookup"><span data-stu-id="06ae0-113">Deploy Skype Room Systems v2 with Exchange Online</span></span>

<span data-ttu-id="06ae0-114">Avant de déployer des systèmes de salle Skype v2 avec Exchange Online, assurez-vous que vous remplissez les conditions.</span><span class="sxs-lookup"><span data-stu-id="06ae0-114">Before you deploy Skype Room Systems v2 with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="06ae0-115">Pour plus d’informations, voir [v2 Skype salle requise](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06ae0-115">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="06ae0-116">Pour déployer des systèmes de salle Skype v2 avec Exchange Online, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="06ae0-116">To deploy Skype Room Systems v2 with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="06ae0-117">Assurez-vous de disposer des autorisations adéquates pour exécuter les applets de commande associées.</span><span class="sxs-lookup"><span data-stu-id="06ae0-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="06ae0-118">Création d’un compte et définition des propriétés Exchange</span><span class="sxs-lookup"><span data-stu-id="06ae0-118">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="06ae0-119">Démarrer une session Windows PowerShell à distance sur un PC et se connecter à Exchange Online comme suit :</span><span class="sxs-lookup"><span data-stu-id="06ae0-119">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>
    
```
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. <span data-ttu-id="06ae0-120">Après avoir établi une session, vous allez créer une nouvelle boîte aux lettres et activer comme un RoomMailboxAccount, soit modifier les paramètres d’une boîte aux lettres de salle existante.</span><span class="sxs-lookup"><span data-stu-id="06ae0-120">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="06ae0-121">Ainsi, le compte de s’authentifier sur des systèmes de salle Skype v2.</span><span class="sxs-lookup"><span data-stu-id="06ae0-121">This will allow the account to authenticate into Skype Room Systems v2.</span></span>
    
   <span data-ttu-id="06ae0-122">Si vous modifiez une boîte aux lettres de ressource :</span><span class="sxs-lookup"><span data-stu-id="06ae0-122">If you're changing an existing resource mailbox:</span></span>
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="06ae0-123">Si vous créez une nouvelle boîte aux lettres de ressources :</span><span class="sxs-lookup"><span data-stu-id="06ae0-123">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="06ae0-124">Pour améliorer l’expérience de réunion, vous devez définir les propriétés Exchange sur le compte d’utilisateur comme suit :</span><span class="sxs-lookup"><span data-stu-id="06ae0-124">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

    
4. <span data-ttu-id="06ae0-p106">Vous devez vous connecter à Azure AD pour appliquer certains paramètres de compte. Pour vous connecter, vous pouvez exécuter l’applet de commande suivante.</span><span class="sxs-lookup"><span data-stu-id="06ae0-p106">You need to connect to Azure AD to apply some account settings. You can run this cmdlet to connect.</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="06ae0-127">Ajout d’une adresse e-mail pour votre compte de domaine sur site</span><span class="sxs-lookup"><span data-stu-id="06ae0-127">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="06ae0-128">Dans l’outil **Active Directory utilisateurs et ordinateurs Active Directory** , avec le bouton droit sur le dossier ou l’unité d’organisation que vos systèmes de salle Skype v2 comptes seront créés, cliquez sur **Nouveau**, puis cliquez sur **utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="06ae0-128">In **Active Directory Users and Computers AD** tool, right-click on the folder or Organizational Unit that your Skype Room Systems v2 accounts will be created in, click **New**, and the click **User**.</span></span>
    
2. <span data-ttu-id="06ae0-p107">Saisissez le nom d’affichage de l’applet de commande précédente dans le champ **Nom complet** et l’alias dans le champ **Nom d’ouverture de session de l’utilisateur**. Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="06ae0-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>


3. <span data-ttu-id="06ae0-p108">Saisissez le mot de passe de ce compte. Vous devrez le saisir à nouveau à des fins de vérification. Vérifiez que seule l’option **Le mot de passe n’expire jamais** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="06ae0-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="06ae0-134">Sélection de **mot de passe n’expire jamais** est une condition requise pour Skype pour Business Server sur les systèmes de salle Skype v2.</span><span class="sxs-lookup"><span data-stu-id="06ae0-134">Selecting **Password never expires** is a requirement for Skype for Business Server on Skype Room Systems v2.</span></span> <span data-ttu-id="06ae0-135">Il est possible que des règles de votre domaine interdisent la non-expiration des mots de passe.</span><span class="sxs-lookup"><span data-stu-id="06ae0-135">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="06ae0-136">Dans ce cas, vous devez créer une exception pour chaque compte d’utilisateur Skype salle systèmes v2.</span><span class="sxs-lookup"><span data-stu-id="06ae0-136">If so, you'll need to create an exception for each Skype Room Systems v2 user account.</span></span>
  
4. <span data-ttu-id="06ae0-137">Cliquez sur **Terminer** pour créer le compte.</span><span class="sxs-lookup"><span data-stu-id="06ae0-137">Click **Finish** to create the account.</span></span>
    
5. <span data-ttu-id="06ae0-p110">Une fois le compte créé, exécutez une synchronisation de répertoire. À l’issue de cette opération, accédez à la page d’utilisateurs et vérifiez que les deux comptes créés lors des étapes précédentes sont fusionnés.</span><span class="sxs-lookup"><span data-stu-id="06ae0-p110">After you've created the account, run a directory synchronization. When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>
    
### <a name="assign-an-office-365-license"></a><span data-ttu-id="06ae0-140">Affectation d’une licence Office 365</span><span class="sxs-lookup"><span data-stu-id="06ae0-140">Assign an Office 365 license</span></span>

1. <span data-ttu-id="06ae0-141">Le compte d’utilisateur doit disposer d’une licence Office 365 valide pour vous assurer que Exchange et Skype pour Business Server fonctionnera.</span><span class="sxs-lookup"><span data-stu-id="06ae0-141">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="06ae0-142">Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’utilisateur ; cela permet de déterminer les SKU de licence disponibles pour votre compte.</span><span class="sxs-lookup"><span data-stu-id="06ae0-142">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span>
    
2. <span data-ttu-id="06ae0-143">Ensuite, utilisez Get-MsolAccountSku pour récupérer une liste de références disponibles pour votre client Office 365.</span><span class="sxs-lookup"><span data-stu-id="06ae0-143">Next, use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
    
3. <span data-ttu-id="06ae0-p112">Une fois la liste obtenue, vous pouvez ajouter une licence à l’aide de l’applet de commande Set-MsolUserLicense. Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="06ae0-p112">Once you list out the SKUs, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```


### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="06ae0-146">Activer le compte d’utilisateur avec Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="06ae0-146">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="06ae0-147">Créez une session Windows PowerShell à distance à partir d’un PC comme suit :</span><span class="sxs-lookup"><span data-stu-id="06ae0-147">Create a remote Windows PowerShell session from a PC as follows:</span></span>
    
    ```
    Import-Module LyncOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="06ae0-148">Pour activer votre compte v2 de systèmes de salle Skype pour Skype pour Business Server, exécutez cette commande :</span><span class="sxs-lookup"><span data-stu-id="06ae0-148">To enable your Skype Room Systems v2 account for Skype for Business Server, run this command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="06ae0-149">Si vous ne savez pas quelle valeur utiliser pour le paramètre RegistrarPool dans votre environnement, vous pouvez obtenir la valeur d’un Skype pour utilisateur Business Server à l’aide de cette commande existante</span><span class="sxs-lookup"><span data-stu-id="06ae0-149">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-skype-room-systems-v2-account"></a><span data-ttu-id="06ae0-150">Affecter un Skype licence Business Server à votre compte v2 de systèmes de salle Skype</span><span class="sxs-lookup"><span data-stu-id="06ae0-150">Assign a Skype for Business Server license to your Skype Room Systems v2 account</span></span>

1. <span data-ttu-id="06ae0-151">Connectez-vous en tant qu’administrateur client, ouvrez le portail d’administration d’Office 365 et cliquez sur l’application d’administration.</span><span class="sxs-lookup"><span data-stu-id="06ae0-151">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="06ae0-152">Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.</span><span class="sxs-lookup"><span data-stu-id="06ae0-152">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="06ae0-153">Cliquez sur le compte de v2 Skype salle systèmes, puis cliquez sur l’icône du crayon pour modifier les informations de compte.</span><span class="sxs-lookup"><span data-stu-id="06ae0-153">Click the Skype Room Systems v2 account, and then click the pen icon to edit the account information.</span></span>
    
4. <span data-ttu-id="06ae0-154">Cliquez sur **Licences**.</span><span class="sxs-lookup"><span data-stu-id="06ae0-154">Click **Licenses**.</span></span>
    
5. <span data-ttu-id="06ae0-155">Dans la zone **Attribuer des licences**, sélectionnez Skype Entreprise (Plan 2) ou Skype Entreprise (Plan 3), en fonction de vos conditions de licence et Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="06ae0-155">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="06ae0-156">Vous devrez utiliser une licence 3 planifier si vous souhaitez utiliser Enterprise Voice sur votre v2 Skype salle systèmes.</span><span class="sxs-lookup"><span data-stu-id="06ae0-156">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Skype Room Systems v2.</span></span>
    
6. <span data-ttu-id="06ae0-157">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="06ae0-157">Click **Save**.</span></span>
    
<span data-ttu-id="06ae0-158">Pour la validation, vous devez être en mesure d’utiliser n’importe quel Skype pour client d’entreprise pour vous connecter à ce compte.</span><span class="sxs-lookup"><span data-stu-id="06ae0-158">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="06ae0-159">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="06ae0-159">See also</span></span>

[<span data-ttu-id="06ae0-160">Configurer des comptes pour les systèmes de salle Skype v2</span><span class="sxs-lookup"><span data-stu-id="06ae0-160">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="06ae0-161">Planification de Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="06ae0-161">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="06ae0-162">Déploiement de Skype Room System v2</span><span class="sxs-lookup"><span data-stu-id="06ae0-162">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="06ae0-163">Configuration d’une console Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="06ae0-163">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="06ae0-164">Gestion de Skype Room System v2</span><span class="sxs-lookup"><span data-stu-id="06ae0-164">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)


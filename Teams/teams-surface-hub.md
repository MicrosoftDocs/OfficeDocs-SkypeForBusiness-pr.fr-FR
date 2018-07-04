---
title: Déployer les équipes Microsoft Surface concentrateur
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 07/02/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Configurer les paramètres d’administration pour Microsoft Teams concentrateur de la surface d’exposition.
localization_priority: Normal
ms.custom:
- Devices
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 948f9f9ed32f4e5846248dfbcd2b96577a0f34ee
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192179"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="b3b2f-103">Déployer les équipes Microsoft Surface concentrateur</span><span class="sxs-lookup"><span data-stu-id="b3b2f-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="b3b2f-104">Avant de déployer Microsoft Teams Microsoft Surface concentrateur, assurez-vous que le matériel, système d’exploitation et autres conditions sont réunies.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="b3b2f-105">Pour plus d’informations, consultez le [guide d’administration de Microsoft Surface Hub](https://docs.microsoft.com/en-us/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="b3b2f-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

## <a name="set-up-user-accounts"></a><span data-ttu-id="b3b2f-106">Configurer les comptes d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="b3b2f-106">Set up user accounts</span></span>
 
<span data-ttu-id="b3b2f-107">Pour configurer des comptes d’utilisateur qui peuvent être utilisés avec les équipes de Surface concentrateur, créez le compte de périphérique comme vous le feriez pour la prise en charge avec Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-107">To set up user accounts that can be used with Teams for Surface Hub, create the device account as you would for support with Skype for Business.</span></span> <span data-ttu-id="b3b2f-108">Le compte de l’appareil doit avoir l’authentification multifacteur désactivée (pour autoriser l’ouverture de session automatique) pour les services dépendants suivants d’équipes dans Office 365 :</span><span class="sxs-lookup"><span data-stu-id="b3b2f-108">The device account needs to have multi-factor authentication disabled (to allow automatic logon) for the following dependent services of Teams in Office 365:</span></span>  
- <span data-ttu-id="b3b2f-109">Exchange</span><span class="sxs-lookup"><span data-stu-id="b3b2f-109">Exchange</span></span> 
- <span data-ttu-id="b3b2f-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="b3b2f-110">SharePoint</span></span> 
- <span data-ttu-id="b3b2f-111">Applications Office</span><span class="sxs-lookup"><span data-stu-id="b3b2f-111">Office Apps</span></span> 

## <a name="add-a-device-account"></a><span data-ttu-id="b3b2f-112">Ajout d’un compte d’appareil</span><span class="sxs-lookup"><span data-stu-id="b3b2f-112">Add a device account</span></span> 

<span data-ttu-id="b3b2f-113">1\.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-113">1\.</span></span> <span data-ttu-id="b3b2f-114">Démarrer une session Windows PowerShell à distance sur un PC et se connecter à Exchange.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-114">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="b3b2f-115">Assurez-vous que vous disposez des autorisations correctes définies pour s’exécuter les applets de commande associée.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-115">Be sure you have the correct permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="b3b2f-116">Voici quelques exemples d’applets de commande pouvant être utilisés et modifiés dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-116">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>

```
Set-ExecutionPolicy Unrestricted
$org='contoso.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ 
-Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

<span data-ttu-id="b3b2f-117">2\.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-117">2\.</span></span> <span data-ttu-id="b3b2f-118">Une fois la session établie, créez une boîte aux lettres et activez-la comme compte de boîte aux lettres pour une salle (RoomMailboxAccount), ou modifiez les paramètres d’une boîte aux lettres de salle existante.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-118">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="b3b2f-119">Ainsi, le compte pour l’authentification auprès des équipes.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-119">This will allow the account to authenticate to Teams.</span></span>

<span data-ttu-id="b3b2f-120">Si vous modifiez une boîte aux lettre de ressource :</span><span class="sxs-lookup"><span data-stu-id="b3b2f-120">If you are changing an existing resource mailbox:</span></span>

```
Set-Mailbox -Identity 'TEAMS01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="b3b2f-121">Si vous créez une boîte aux lettres de ressource :</span><span class="sxs-lookup"><span data-stu-id="b3b2f-121">If you’re creating a new resource mailbox:</span></span>

```
New-Mailbox -MicrosoftOnlineServicesID TEAMS01@contoso.com -Alias TEAMS01 
-Name "Teams-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="b3b2f-122">3\.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-122">3\.</span></span> <span data-ttu-id="b3b2f-123">Plusieurs propriétés Exchange doivent être définies sur le compte d’appareil pour optimiser l’expérience de réunion.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-123">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="b3b2f-124">Vous pouvez consulter les propriétés qui doivent être définies dans la section Propriétés Exchange.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-124">You can see which properties need to be set in the Exchange properties section.</span></span>

```
Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
 -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
```

<span data-ttu-id="b3b2f-125">4\.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-125">4\.</span></span> <span data-ttu-id="b3b2f-126">Vous devrez vous connecter à Azure Active Directory pour appliquer certains paramètres de compte.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-126">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="b3b2f-127">Pour vous connecter à Azure AD, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b3b2f-127">To connect to Azure AD, run the following cmdlet:</span></span>

```
Connect-MsolService -Credential $cred
```

<span data-ttu-id="b3b2f-128">5\.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-128">5\.</span></span> <span data-ttu-id="b3b2f-129">	Pour empêcher l’expiration du mot de passe, exécutez l’applet de commande Set-MsolUser cmdlet avec l’option Le mot de passe n’expire jamais, comme suit :  </span><span class="sxs-lookup"><span data-stu-id="b3b2f-129">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 

```
Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
```

<span data-ttu-id="b3b2f-130">Vous pouvez également définir un numéro de téléphone pour la salle comme suit :</span><span class="sxs-lookup"><span data-stu-id="b3b2f-130">You can also set a phone number for the room as follows:</span></span>

```
Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
```

<span data-ttu-id="b3b2f-131">6\.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-131">6\.</span></span> <span data-ttu-id="b3b2f-132">Le compte de l’appareil doit avoir une licence Office 365 ou Exchange et Skype pour les entreprises ne fonctionnent pas.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-132">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="b3b2f-133">Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-133">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="b3b2f-134">Vous pouvez utiliser Get-MsolAccountSku pour récupérer une liste de références disponibles pour votre client Office 365 comme suit :</span><span class="sxs-lookup"><span data-stu-id="b3b2f-134">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>
 
```
Get-MsolAccountSku
```

<span data-ttu-id="b3b2f-p109">Puis, vous pouvez ajouter une licence à l’aide de l’applet de commande Set-MsolUserLicense. Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="b3b2f-p109">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

```
Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
Get-MsolAccountSku
Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
```

<span data-ttu-id="b3b2f-137">7\.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-137">7\.</span></span> <span data-ttu-id="b3b2f-138">Ensuite, vous devez activer le compte de l’appareil avec des équipes pour le Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-138">Next, you need to enable the device account with Teams for Surface Hub.</span></span> <span data-ttu-id="b3b2f-139">Assurez-vous que votre environnement répond aux exigences définies dans le [guide d’administration de Microsoft Surface Hub](https://docs.microsoft.com/en-us/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="b3b2f-139">Be sure your environment meets the requirements defined in [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

<span data-ttu-id="b3b2f-140">Démarrer une session Windows PowerShell à distance comme suit (veillez à installer Skype pour les composants Business Online PowerShell) :</span><span class="sxs-lookup"><span data-stu-id="b3b2f-140">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>

```
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

<span data-ttu-id="b3b2f-141">Ensuite, activez vos équipes compte Hub Surface en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b3b2f-141">Next, enable your Teams for Surface Hub account by running the following cmdlet:</span></span>

```
Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
```

<span data-ttu-id="b3b2f-142">Obtenir les informations de RegistrarPool à partir du nouveau compte d’utilisateur en cours d’installation, comme indiqué dans cet exemple :</span><span class="sxs-lookup"><span data-stu-id="b3b2f-142">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

```
Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
```

> [!NOTE]
> <span data-ttu-id="b3b2f-143">Nouveaux comptes d’utilisateur ne peuvent pas être créés sur le même pool de serveurs d’inscriptions en tant que comptes d’utilisateurs existants dans le client.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-143">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="b3b2f-144">La commande ci-dessus empêchera les erreurs de configuration de compte en raison de cette situation.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-144">The command above will prevent errors in account setup due to this situation.</span></span> 

<span data-ttu-id="b3b2f-145">Une fois que vous avez terminé les étapes précédentes pour activer vos équipes compte Hub Surface, vous devez attribuer une licence à l’appareil de v2 Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-145">After you've completed the preceding steps to enable your Teams for Surface Hub account, you need to assign a license to the Surface Hub v2 device.</span></span> <span data-ttu-id="b3b2f-146">À l’aide du portail d’administration d’Office 365, attribuer une licence Hub de la surface d’exposition les équipes au périphérique.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-146">Using the Office 365 administrative portal, assign a Teams for Surface Hub license to the device.</span></span>

### <a name="assign-a-license-to-the-account"></a><span data-ttu-id="b3b2f-147">Attribuer une licence pour le compte</span><span class="sxs-lookup"><span data-stu-id="b3b2f-147">Assign a license to the account</span></span>

1. <span data-ttu-id="b3b2f-148">Ouvrez une session en tant qu’un administrateur client, ouvrez le centre d’administration Office 365 et cliquez sur l’application d’administration.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-148">Log on as a tenant administrator, open the Office 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="b3b2f-149">Cliquez sur **utilisateurs et groupes**, puis cliquez sur **Ajouter des utilisateurs, de réinitialiser les mots de passe et bien plus encore**.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-149">Click **Users and Groups**, and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="b3b2f-150">Sélectionnez les équipes pour le compte de la Surface Hub, puis cliquez ou appuyez sur l’icône crayon, ce qui signifie que modifier.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-150">Select the Teams for Surface Hub account, and then click or tap the pen icon, which means edit.</span></span>
4. <span data-ttu-id="b3b2f-151">Cliquez sur l’option de **licences** .</span><span class="sxs-lookup"><span data-stu-id="b3b2f-151">Click the **Licenses** option.</span></span>
5. <span data-ttu-id="b3b2f-152">Dans la section **attribution de licences** , vous devez sélectionner le plan, en fonction de vos licences.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-152">In the **Assign licenses** section, you need to select the plan, depending on your licensing.</span></span>
6. <span data-ttu-id="b3b2f-153">Cliquez sur **Enregistrer** pour terminer la tâche.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-153">Click **Save** to complete the task.</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="b3b2f-154">Installer des équipes pour exposer Hub à partir du magasin de Microsoft</span><span class="sxs-lookup"><span data-stu-id="b3b2f-154">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="b3b2f-155">Ces instructions sont les solutions de contournement pour l’installation des équipes concentrateur de Surface à partir de Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-155">These instructions include the current workarounds for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="b3b2f-156">Démarrez le magasin de Windows :</span><span class="sxs-lookup"><span data-stu-id="b3b2f-156">Start the Windows Store:</span></span><br>
   <span data-ttu-id="b3b2f-157">a.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-157">a.</span></span> <span data-ttu-id="b3b2f-158">Cliquez sur **Démarrer** > **toutes les applications** > **paramètres**.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-158">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="b3b2f-159">b.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-159">b.</span></span> <span data-ttu-id="b3b2f-160">Cliquez sur **compte de Surface Hub DISPOSITIF, la gestion**.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-160">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="b3b2f-161">c.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-161">c.</span></span> <span data-ttu-id="b3b2f-162">Sur la gauche, cliquez sur l’onglet **applications et fonctionnalités** .</span><span class="sxs-lookup"><span data-stu-id="b3b2f-162">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="b3b2f-163">d.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-163">d.</span></span> <span data-ttu-id="b3b2f-164">Sur la droite, appuyez sur le bouton **Ouvrir un magasin** .</span><span class="sxs-lookup"><span data-stu-id="b3b2f-164">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="b3b2f-165">Dans le Store Microsoft, recherchez les *Équipes Microsoft*.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-165">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="b3b2f-166">Les **Équipes Microsoft Surface concentrateur (Preview)** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-166">The **Microsoft Teams for Surface Hub (Preview)** will be displayed.</span></span> <span data-ttu-id="b3b2f-167">Appuyez sur le bouton **obtenir l’application** à installer.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-167">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="b3b2f-168">Une fois l’installation terminée, redémarrez le Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-168">When the installation is complete, restart the Surface Hub.</span></span> 
4. <span data-ttu-id="b3b2f-169">Après le redémarrage de la surface d’exposition Hub, vous devez être en mesure de démarrer l’application d’équipes dans le menu **Démarrer** et joindre une réunion à partir du calendrier.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-169">After the Surface Hub restarts, you should be able to start the Teams app from the **Start** menu and join a meeting from the calendar.</span></span> 

## <a name="make-teams-the-default-vtc-application"></a><span data-ttu-id="b3b2f-170">Rendre les équipes de l’application de VTC par défaut</span><span class="sxs-lookup"><span data-stu-id="b3b2f-170">Make Teams the default VTC application</span></span>

<span data-ttu-id="b3b2f-171">Équipes peuvent être définies à être application VTC par défaut au lieu de Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-171">Teams can be set up to be the default VTC application instead of Skype for Business.</span></span> <span data-ttu-id="b3b2f-172">Une stratégie de gestion de périphérique Mobile (MDM) doit être appliqué à l’appareil Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-172">A Mobile Device Management (MDM) policy needs to be applied to the Surface Hub device.</span></span> 
 
<span data-ttu-id="b3b2f-173">Il existe deux options pour configurer des stratégies de Mobile Device Manager :</span><span class="sxs-lookup"><span data-stu-id="b3b2f-173">There are two options for configuring MDM policies:</span></span> 

- <span data-ttu-id="b3b2f-174">Si vous disposez d’une stratégie configurée, ajoutez-le via l’application de gestion des périphériques.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-174">If you have a policy configured, add it via the Device management app.</span></span> 
- <span data-ttu-id="b3b2f-175">Si vous ne disposez pas d’une stratégie à distance configurée, nous disposons d’un fichier de package mis en service que vous pouvez charger sur une clé USB.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-175">If you do not have a remote policy configured, we have a provisioned package file that you can load onto an USB key.</span></span>

### <a name="device-management-configuration"></a><span data-ttu-id="b3b2f-176">Configuration de gestion des périphériques</span><span class="sxs-lookup"><span data-stu-id="b3b2f-176">Device management configuration</span></span>

<span data-ttu-id="b3b2f-177">Voici un exemple d’ajout d’une stratégie Mobile Device Manager configurée à partir d’une autorité centralisée de Mobile Device Manager.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-177">The following is an example of adding an MDM policy configured from a central MDM authority.</span></span> <span data-ttu-id="b3b2f-178">Si vous êtes sur le réseau d’entreprise, vous pouvez utiliser les instructions suivantes textuel, y compris le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-178">If you are on the corporate network, you can use the following instructions verbatim, including user account.</span></span> 
 
1. <span data-ttu-id="b3b2f-179">Dans la section **Gestion des périphériques** , cliquez sur **+**.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-179">Under the **Device Management** section, tap **+**.</span></span><br>
   <span data-ttu-id="b3b2f-180">La boîte de dialogue **se connecter à travailler ou de l’école** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-180">The **Connect to work or school** dialog box will open.</span></span> 
2. <span data-ttu-id="b3b2f-181">Entrez l’adresse de messagerie de stratégie et le mot de passe lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-181">Enter the policy e-mail address and password when prompted.</span></span><br>
   <span data-ttu-id="b3b2f-182">**Remarque :**  Il existe un bogue dans le système d’exploitation qui n’actualise automatiquement l’interface utilisateur une fois que vous avez entré votre compte de la gestion des périphériques.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-182">**NOTE:**  There's a bug in the OS that doesn't automatically refresh the UI after you've entered your device management account.</span></span> <span data-ttu-id="b3b2f-183">Vous devez fermer et rouvrir paramètres afin de voir le compte répertorié.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-183">You'll need to close and re-open settings in order to see the account listed.</span></span> 
3. <span data-ttu-id="b3b2f-184">Il vous prendre quelques minutes pour les paramètres de stratégie Mobile Device Manager à synchroniser. Si vous souhaitez forcer une synchronisation, cliquez sur le bouton **compte Mobile Device Manager** , puis appuyez sur le bouton **Info** .</span><span class="sxs-lookup"><span data-stu-id="b3b2f-184">It'll take a few minutes for the MDM policy settings to sync. If you want to force a sync, tap the **MDM account** button, and then tap the **Info** button.</span></span> <span data-ttu-id="b3b2f-185">La fenêtre Info où vous pouvez puis cliquez sur **synchronisation**s’affiche.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-185">This will bring up the Info window where you can then tap **Sync**.</span></span> 
4. <span data-ttu-id="b3b2f-186">Pour vérifier que vous avez ce dont vous avez besoin, vous pouvez vérifier le Registre.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-186">To verify that you have what you need, you can check the registry.</span></span> <span data-ttu-id="b3b2f-187">Vous devez voir deux clés sous **HKLM\Software\Microsoft\Windows\CurrentVersion\PPI\VtcCallSettings**.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-187">You should see two keys under **HKLM\Software\Microsoft\Windows\CurrentVersion\PPI\VtcCallSettings**.</span></span> <br><br>
   <span data-ttu-id="b3b2f-188">La valeur DWORD **VtcAppMeetingHandlingMode** indique que les équipes est l’application par défaut.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-188">The **VtcAppMeetingHandlingMode** DWORD value indicates that Teams is the default app.</span></span> <span data-ttu-id="b3b2f-189">Les valeurs suivantes sont reconnues.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-189">The following values are recognized.</span></span> <br><br>
    |<span data-ttu-id="b3b2f-190">Numéro</span><span class="sxs-lookup"><span data-stu-id="b3b2f-190">Number</span></span> | <span data-ttu-id="b3b2f-191">Valeur</span><span class="sxs-lookup"><span data-stu-id="b3b2f-191">Value</span></span>   |
    |-------|---------|
    |<span data-ttu-id="b3b2f-192">0</span><span class="sxs-lookup"><span data-stu-id="b3b2f-192">0</span></span>      | <span data-ttu-id="b3b2f-193">SkypePreferred</span><span class="sxs-lookup"><span data-stu-id="b3b2f-193">SkypePreferred</span></span>            |
    |<span data-ttu-id="b3b2f-194">1</span><span class="sxs-lookup"><span data-stu-id="b3b2f-194">1</span></span>      | <span data-ttu-id="b3b2f-195">VtcPreferred (équipes)</span><span class="sxs-lookup"><span data-stu-id="b3b2f-195">VtcPreferred (Teams)</span></span>      |
    |<span data-ttu-id="b3b2f-196">2</span><span class="sxs-lookup"><span data-stu-id="b3b2f-196">2</span></span>      | <span data-ttu-id="b3b2f-197">VtcExclusive (équipes uniquement)</span><span class="sxs-lookup"><span data-stu-id="b3b2f-197">VtcExclusive (Teams only)</span></span> |

    <span data-ttu-id="b3b2f-198">Le **VtcCallAppPackageId** est le nom du package équipes installé.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-198">The **VtcCallAppPackageId** is the name of the installed Teams package.</span></span> <span data-ttu-id="b3b2f-199">Si cela ne s’affiche pas, vérifiez que vous avez installé le package équipes et resynchronisation.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-199">If this doesn't show up, make sure you've installed the Teams package, and re-sync.</span></span> 
 
### <a name="configure-mdm-via-usb-key"></a><span data-ttu-id="b3b2f-200">Configurer Mobile Device Manager via une clé USB</span><span class="sxs-lookup"><span data-stu-id="b3b2f-200">Configure MDM via USB key</span></span> 
 
<span data-ttu-id="b3b2f-201">Les packages se trouvent sur cette [page de téléchargement](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span><span class="sxs-lookup"><span data-stu-id="b3b2f-201">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="b3b2f-202">Choisissez celui qui convient pour le programme que vous prévoyez d’installer et de le copier sur une clé USB.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-202">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="b3b2f-203">Le fichier .ppkg correct à utiliser dépend de package équipes qui a été installé à partir du magasin et la stratégie que vous souhaitez appliquer (Skype exclusif, Skype préféré, par défaut, les équipes exclusif équipes).</span><span class="sxs-lookup"><span data-stu-id="b3b2f-203">The correct .ppkg file to use depends on the Teams package that has been installed from the store, and the policy you'd like to apply (Skype exclusive, Skype preferred, Teams preferred, Teams exclusive).</span></span> 
 
1. <span data-ttu-id="b3b2f-204">Attacher la clé USB à l’appareil Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-204">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="b3b2f-205">Ouvrez l’application de **paramètres** sur un appareil Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-205">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="b3b2f-206">Ouvrez **gestion de compte Hub Surface périphérique**.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-206">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="b3b2f-207">Ouvrez **Gestion des périphériques**.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-207">Open **Device Management**.</span></span> 
5. <span data-ttu-id="b3b2f-208">Cliquez sur **Ajouter ou supprimer un package de mise en service**.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-208">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="b3b2f-209">Cliquez sur **Ajouter un Package**.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-209">Click **Add Package**.</span></span>
7. <span data-ttu-id="b3b2f-210">Sélectionnez l’option **Support amovible** dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-210">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="b3b2f-211">Ajouter **Allowbuildspreview.ppkg**, puis sélectionnez le package Hub Surface que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-211">Add the **Allowbuildspreview.ppkg**, and then select the Surface Hub package you want to add.</span></span> 
9. <span data-ttu-id="b3b2f-212">Redémarrez le dispositif Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-212">Restart the Surface Hub device.</span></span> 

> [!NOTE]
> <span data-ttu-id="b3b2f-213">Si votre appareil ou périphériques de votre organisation n’appartiennent pas actuellement du programme interne Windows et que vous participez à pays couverts par général règlement de Protection des données (PIBR) (ou si vous avez modifié manuellement vos paramètres de télémétrie sur de base), vous devez renouveler vérifier que vous avez autorisé la télémétrie complète avant de participer à la programme initiés.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-213">If your device or your organization's devices are not currently part of the Windows Insider Program and you are in countries covered by General Data Protection Regulation (GDPR) (or you have manually changed your telemetry settings to Basic), then you must re-check that you have permitted full telemetry before you join the Insider Program.</span></span> <span data-ttu-id="b3b2f-214">PIBR modifié le comportement par défaut des périphériques Hub de la surface d’exposition dans l’Union européenne pour définir la télémétrie de base.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-214">GDPR changed the default behavior of Surface Hub devices in the EU to set telemetry to Basic.</span></span>
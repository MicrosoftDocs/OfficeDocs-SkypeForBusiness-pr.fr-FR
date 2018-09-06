---
title: Déployer les équipes Microsoft Surface concentrateur
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/29/2018
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
ms.openlocfilehash: 17ba794c2a0b2a09081da41b5fad5df2bee5bb4c
ms.sourcegitcommit: 33966ebb9ca3d922d47aaa9b9e3a2ddd26c320ca
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2018
ms.locfileid: "23844764"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="d7ae6-103">Déployer les équipes Microsoft Surface concentrateur</span><span class="sxs-lookup"><span data-stu-id="d7ae6-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="d7ae6-104">Avant de déployer Microsoft Teams Microsoft Surface concentrateur, assurez-vous que le matériel, système d’exploitation et autres conditions sont réunies.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="d7ae6-105">Pour plus d’informations, consultez le [guide d’administration de Microsoft Surface Hub](https://docs.microsoft.com/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="d7ae6-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/surface-hub/).</span></span>

## <a name="set-up-user-accounts"></a><span data-ttu-id="d7ae6-106">Configurer les comptes d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="d7ae6-106">Set up user accounts</span></span>
 
<span data-ttu-id="d7ae6-107">Pour configurer des comptes d’utilisateur qui peuvent être utilisés avec les équipes de Surface concentrateur, créez le compte de périphérique comme vous le feriez pour la prise en charge avec Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-107">To set up user accounts that can be used with Teams for Surface Hub, create the device account as you would for support with Skype for Business.</span></span> <span data-ttu-id="d7ae6-108">Le compte de l’appareil doit avoir l’authentification multifacteur désactivée (pour autoriser l’ouverture de session automatique) pour les services dépendants suivants d’équipes dans Office 365 :</span><span class="sxs-lookup"><span data-stu-id="d7ae6-108">The device account needs to have multi-factor authentication disabled (to allow automatic logon) for the following dependent services of Teams in Office 365:</span></span>  
- <span data-ttu-id="d7ae6-109">Exchange</span><span class="sxs-lookup"><span data-stu-id="d7ae6-109">Exchange</span></span> 
- <span data-ttu-id="d7ae6-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="d7ae6-110">SharePoint</span></span> 
- <span data-ttu-id="d7ae6-111">Applications Office</span><span class="sxs-lookup"><span data-stu-id="d7ae6-111">Office Apps</span></span> 

## <a name="add-a-device-account"></a><span data-ttu-id="d7ae6-112">Ajout d’un compte d’appareil</span><span class="sxs-lookup"><span data-stu-id="d7ae6-112">Add a device account</span></span> 

<span data-ttu-id="d7ae6-113">1\.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-113">1\.</span></span> <span data-ttu-id="d7ae6-114">Démarrer une session Windows PowerShell à distance sur un PC et se connecter à Exchange.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-114">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="d7ae6-115">Assurez-vous que vous disposez des autorisations correctes définies pour s’exécuter les applets de commande associée.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-115">Be sure you have the correct permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="d7ae6-116">Voici quelques exemples d’applets de commande pouvant être utilisés et modifiés dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-116">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>

```
Set-ExecutionPolicy Unrestricted
$org='contoso.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ 
-Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

<span data-ttu-id="d7ae6-117">2\.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-117">2\.</span></span> <span data-ttu-id="d7ae6-118">Une fois la session établie, créez une boîte aux lettres et activez-la comme compte de boîte aux lettres pour une salle (RoomMailboxAccount), ou modifiez les paramètres d’une boîte aux lettres de salle existante.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-118">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="d7ae6-119">Ainsi, le compte pour l’authentification auprès des équipes.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-119">This will allow the account to authenticate to Teams.</span></span>

<span data-ttu-id="d7ae6-120">Si vous modifiez une boîte aux lettre de ressource :</span><span class="sxs-lookup"><span data-stu-id="d7ae6-120">If you are changing an existing resource mailbox:</span></span>

```
Set-Mailbox -Identity 'TEAMS01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="d7ae6-121">Si vous créez une boîte aux lettres de ressource :</span><span class="sxs-lookup"><span data-stu-id="d7ae6-121">If you’re creating a new resource mailbox:</span></span>

```
New-Mailbox -MicrosoftOnlineServicesID TEAMS01@contoso.com -Alias TEAMS01 
-Name "Teams-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="d7ae6-122">3\.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-122">3\.</span></span> <span data-ttu-id="d7ae6-123">Plusieurs propriétés Exchange doivent être définies sur le compte d’appareil pour optimiser l’expérience de réunion.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-123">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="d7ae6-124">Vous pouvez consulter les propriétés qui doivent être définies dans la section Propriétés Exchange.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-124">You can see which properties need to be set in the Exchange properties section.</span></span>

```
Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
 -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
```

<span data-ttu-id="d7ae6-125">4\.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-125">4\.</span></span> <span data-ttu-id="d7ae6-126">Vous devrez vous connecter à Azure Active Directory pour appliquer certains paramètres de compte.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-126">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="d7ae6-127">Pour vous connecter à Azure AD, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="d7ae6-127">To connect to Azure AD, run the following cmdlet:</span></span>

```
Connect-MsolService -Credential $cred
```

<span data-ttu-id="d7ae6-128">5\.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-128">5\.</span></span> <span data-ttu-id="d7ae6-129">	Pour empêcher l’expiration du mot de passe, exécutez l’applet de commande Set-MsolUser cmdlet avec l’option Le mot de passe n’expire jamais, comme suit :  </span><span class="sxs-lookup"><span data-stu-id="d7ae6-129">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 

```
Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
```

<span data-ttu-id="d7ae6-130">Vous pouvez également définir un numéro de téléphone pour la salle comme suit :</span><span class="sxs-lookup"><span data-stu-id="d7ae6-130">You can also set a phone number for the room as follows:</span></span>

```
Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
```

<span data-ttu-id="d7ae6-131">6\.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-131">6\.</span></span> <span data-ttu-id="d7ae6-132">Le compte de l’appareil doit avoir une licence Office 365 ou Exchange et Skype pour les entreprises ne fonctionnent pas.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-132">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="d7ae6-133">Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-133">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="d7ae6-134">Vous pouvez utiliser Get-MsolAccountSku pour récupérer une liste de références disponibles pour votre client Office 365 comme suit :</span><span class="sxs-lookup"><span data-stu-id="d7ae6-134">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>
 
```
Get-MsolAccountSku
```

<span data-ttu-id="d7ae6-p109">Puis, vous pouvez ajouter une licence à l’aide de l’applet de commande Set-MsolUserLicense. Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="d7ae6-p109">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

```
Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
Get-MsolAccountSku
Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
```

<span data-ttu-id="d7ae6-137">7\.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-137">7\.</span></span> <span data-ttu-id="d7ae6-138">Ensuite, vous devez activer le compte de l’appareil avec des équipes pour le Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-138">Next, you need to enable the device account with Teams for Surface Hub.</span></span> <span data-ttu-id="d7ae6-139">Assurez-vous que votre environnement répond aux exigences définies dans le [guide d’administration de Microsoft Surface Hub](https://docs.microsoft.com/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="d7ae6-139">Be sure your environment meets the requirements defined in [Microsoft Surface Hub admin guide](https://docs.microsoft.com/surface-hub/).</span></span>

<span data-ttu-id="d7ae6-140">Démarrer une session Windows PowerShell à distance comme suit (veillez à installer Skype pour les composants Business Online PowerShell) :</span><span class="sxs-lookup"><span data-stu-id="d7ae6-140">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>

```
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

<span data-ttu-id="d7ae6-141">Ensuite, activez vos équipes compte Hub Surface en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="d7ae6-141">Next, enable your Teams for Surface Hub account by running the following cmdlet:</span></span>

```
Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
```

<span data-ttu-id="d7ae6-142">Obtenir les informations de RegistrarPool à partir du nouveau compte d’utilisateur en cours d’installation, comme indiqué dans cet exemple :</span><span class="sxs-lookup"><span data-stu-id="d7ae6-142">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

```
Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
```

> [!NOTE]
> <span data-ttu-id="d7ae6-143">Nouveaux comptes d’utilisateur ne peuvent pas être créés sur le même pool de serveurs d’inscriptions en tant que comptes d’utilisateurs existants dans le client.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-143">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="d7ae6-144">La commande ci-dessus empêchera les erreurs de configuration de compte en raison de cette situation.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-144">The command above will prevent errors in account setup due to this situation.</span></span> 

<span data-ttu-id="d7ae6-145">Une fois que vous avez terminé les étapes précédentes pour activer vos équipes compte Hub Surface, vous devez attribuer une licence à l’appareil de v2 Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-145">After you've completed the preceding steps to enable your Teams for Surface Hub account, you need to assign a license to the Surface Hub v2 device.</span></span> <span data-ttu-id="d7ae6-146">À l’aide du portail d’administration d’Office 365, attribuer une licence Hub de la surface d’exposition les équipes au périphérique.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-146">Using the Office 365 administrative portal, assign a Teams for Surface Hub license to the device.</span></span>

### <a name="assign-a-license-to-the-account"></a><span data-ttu-id="d7ae6-147">Attribuer une licence pour le compte</span><span class="sxs-lookup"><span data-stu-id="d7ae6-147">Assign a license to the account</span></span>

1. <span data-ttu-id="d7ae6-148">Ouvrez une session en tant qu’un administrateur client, ouvrez le centre d’administration Office 365 et cliquez sur l’application d’administration.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-148">Log on as a tenant administrator, open the Office 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="d7ae6-149">Cliquez sur **utilisateurs et groupes**, puis cliquez sur **Ajouter des utilisateurs, de réinitialiser les mots de passe et bien plus encore**.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-149">Click **Users and Groups**, and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="d7ae6-150">Sélectionnez les équipes pour le compte de la Surface Hub, puis cliquez ou appuyez sur l’icône crayon, ce qui signifie que modifier.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-150">Select the Teams for Surface Hub account, and then click or tap the pen icon, which means edit.</span></span>
4. <span data-ttu-id="d7ae6-151">Cliquez sur l’option de **licences** .</span><span class="sxs-lookup"><span data-stu-id="d7ae6-151">Click the **Licenses** option.</span></span>
5. <span data-ttu-id="d7ae6-152">Dans la section **attribution de licences** , vous devez sélectionner le plan, en fonction de vos licences.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-152">In the **Assign licenses** section, you need to select the plan, depending on your licensing.</span></span>
6. <span data-ttu-id="d7ae6-153">Cliquez sur **Enregistrer** pour terminer la tâche.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-153">Click **Save** to complete the task.</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="d7ae6-154">Installer des équipes pour exposer Hub à partir du magasin de Microsoft</span><span class="sxs-lookup"><span data-stu-id="d7ae6-154">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="d7ae6-155">Ces instructions sont pour l’installation des équipes concentrateur de Surface à partir de Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-155">These instructions are for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="d7ae6-156">Démarrer la banque Microsoft :</span><span class="sxs-lookup"><span data-stu-id="d7ae6-156">Start the Microsoft Store:</span></span><br>
   <span data-ttu-id="d7ae6-157">a.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-157">a.</span></span> <span data-ttu-id="d7ae6-158">Cliquez sur **Démarrer** > **toutes les applications** > **paramètres**.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-158">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="d7ae6-159">b.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-159">b.</span></span> <span data-ttu-id="d7ae6-160">Cliquez sur **compte de Surface Hub DISPOSITIF, la gestion**.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-160">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="d7ae6-161">c.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-161">c.</span></span> <span data-ttu-id="d7ae6-162">Sur la gauche, cliquez sur l’onglet **applications et fonctionnalités** .</span><span class="sxs-lookup"><span data-stu-id="d7ae6-162">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="d7ae6-163">d.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-163">d.</span></span> <span data-ttu-id="d7ae6-164">Sur la droite, appuyez sur le bouton **Ouvrir un magasin** .</span><span class="sxs-lookup"><span data-stu-id="d7ae6-164">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="d7ae6-165">Dans le Store Microsoft, recherchez les *Équipes Microsoft*.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-165">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="d7ae6-166">Les **Équipes Microsoft Surface concentrateur** s’affichera.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-166">The **Microsoft Teams for Surface Hub** will be displayed.</span></span> <span data-ttu-id="d7ae6-167">Appuyez sur le bouton **obtenir l’application** à installer.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-167">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="d7ae6-168">Une fois l’installation terminée, redémarrez le Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-168">When the installation is complete, restart the Surface Hub.</span></span> 

> [!NOTE]
> <span data-ttu-id="d7ae6-169">Ne cliquez pas sur la **barre de lancement** de la page de liste des magasins.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-169">Do not tap on **Launch** from the Store listing page.</span></span>

## <a name="make-teams-the-default-calling-and-meetings-application"></a><span data-ttu-id="d7ae6-170">Rendre les équipes l’appel par défaut et l’application de réunions</span><span class="sxs-lookup"><span data-stu-id="d7ae6-170">Make Teams the default calling and meetings application</span></span>
 
<span data-ttu-id="d7ae6-171">Il existe deux options pour la configuration de la stratégie d’application appelant et réunions par défaut :</span><span class="sxs-lookup"><span data-stu-id="d7ae6-171">There are two options for configuring the default calling and meetings application policy:</span></span> 

- <span data-ttu-id="d7ae6-172">**Option 1**: configurer via une clé USB.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-172">**Option 1**: Configure via USB key.</span></span> 
- <span data-ttu-id="d7ae6-173">**Option 2**: configurer via Mobile Device Manager tels que Intune.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-173">**Option 2**: Configure via MDM such as Intune.</span></span>
 
### <a name="option-1-configure-via-usb-key"></a><span data-ttu-id="d7ae6-174">Option 1 : Configurer via une clé USB</span><span class="sxs-lookup"><span data-stu-id="d7ae6-174">Option 1: Configure via USB key</span></span> 
 
<span data-ttu-id="d7ae6-175">Les packages se trouvent sur cette [page de téléchargement](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span><span class="sxs-lookup"><span data-stu-id="d7ae6-175">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="d7ae6-176">Choisissez celui qui convient pour le programme que vous prévoyez d’installer et de le copier sur une clé USB.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-176">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="d7ae6-177">Le fichier .ppkg correct à utiliser dépend de la stratégie d’application par défaut que voulez-vous appliquer comme suit :</span><span class="sxs-lookup"><span data-stu-id="d7ae6-177">The correct .ppkg file to use depends on the default application policy you'd like to apply as follows:</span></span> 

|<span data-ttu-id="d7ae6-178">Numéro</span><span class="sxs-lookup"><span data-stu-id="d7ae6-178">Number</span></span>  |<span data-ttu-id="d7ae6-179">Description</span><span class="sxs-lookup"><span data-stu-id="d7ae6-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="d7ae6-180">0</span><span class="sxs-lookup"><span data-stu-id="d7ae6-180">0</span></span>     | <span data-ttu-id="d7ae6-181">Application préférée Skype sur l’écran de démarrage, équipes de réunions disponibles</span><span class="sxs-lookup"><span data-stu-id="d7ae6-181">Skype preferred app on the Start Screen, Teams Meetings available</span></span>        |
|<span data-ttu-id="d7ae6-182">1</span><span class="sxs-lookup"><span data-stu-id="d7ae6-182">1</span></span>     | <span data-ttu-id="d7ae6-183">Application préférée équipes sur l’écran de démarrage, Skype réunions disponibles</span><span class="sxs-lookup"><span data-stu-id="d7ae6-183">Teams preferred app on the Start Screen, Skype Meetings available</span></span>        |
|<span data-ttu-id="d7ae6-184">2</span><span class="sxs-lookup"><span data-stu-id="d7ae6-184">2</span></span>     | <span data-ttu-id="d7ae6-185">Application exclusive équipes sur l’écran d’accueil (Skype app n’est pas disponible)</span><span class="sxs-lookup"><span data-stu-id="d7ae6-185">Teams exclusive app on the Start screen (Skype app not available)</span></span>        |
 
1. <span data-ttu-id="d7ae6-186">Attacher la clé USB à l’appareil Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-186">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="d7ae6-187">Ouvrez l’application de **paramètres** sur un appareil Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-187">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="d7ae6-188">Ouvrez **gestion de compte Hub Surface périphérique**.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-188">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="d7ae6-189">Ouvrez **Gestion des périphériques**.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-189">Open **Device Management**.</span></span> 
5. <span data-ttu-id="d7ae6-190">Cliquez sur **Ajouter ou supprimer un package de mise en service**.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-190">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="d7ae6-191">Cliquez sur **Ajouter un Package**.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-191">Click **Add Package**.</span></span>
7. <span data-ttu-id="d7ae6-192">Sélectionnez l’option **Support amovible** dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-192">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="d7ae6-193">Ajoutez le package **TeamsRTMMode\*.ppkg** approprié qui a été précédemment copié à la clé USB.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-193">Add the appropriate **TeamsRTMMode\*.ppkg** package that was previously copied to the USB key.</span></span> 
9. <span data-ttu-id="d7ae6-194">Redémarrez le dispositif Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-194">Restart the Surface Hub device.</span></span> 
10. <span data-ttu-id="d7ae6-195">Après le redémarrage de l’appareil, vous devez être en mesure de démarrer l’application des équipes à partir de l’écran d’accueil et participer à une réunion à partir du calendrier.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-195">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span> 

### <a name="option-2-configure-via-mdm-such-as-intune"></a><span data-ttu-id="d7ae6-196">Option 2 : Configurer via Mobile Device Manager tels que Intune</span><span class="sxs-lookup"><span data-stu-id="d7ae6-196">Option 2: Configure via MDM such as Intune</span></span> 

<span data-ttu-id="d7ae6-197">Utilisez ce qui suit pour configurer la stratégie par défaut les réunions et les appels d’application via Intune.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-197">Use the following to configure the default calling and meetings application policy via Intune.</span></span>

<span data-ttu-id="d7ae6-198">.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-198"></span></span>

|<span data-ttu-id="d7ae6-199">Paramètre</span><span class="sxs-lookup"><span data-stu-id="d7ae6-199">Setting</span></span>   |<span data-ttu-id="d7ae6-200">Valeur</span><span class="sxs-lookup"><span data-stu-id="d7ae6-200">Value</span></span>    |<span data-ttu-id="d7ae6-201">Description</span><span class="sxs-lookup"><span data-stu-id="d7ae6-201">Description</span></span>    |
|----------|---------|---------|
|<span data-ttu-id="d7ae6-202"> Path</span><span class="sxs-lookup"><span data-stu-id="d7ae6-202">Path</span></span>      | <span data-ttu-id="d7ae6-203">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span><span class="sxs-lookup"><span data-stu-id="d7ae6-203">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span></span>        |
|<span data-ttu-id="d7ae6-204">Type de données</span><span class="sxs-lookup"><span data-stu-id="d7ae6-204">Data Type</span></span> | <span data-ttu-id="d7ae6-205">nombre entier (0-2)</span><span class="sxs-lookup"><span data-stu-id="d7ae6-205">integer (0-2)</span></span>   |<span data-ttu-id="d7ae6-206">0 - application préféré Skype sur l’écran de démarrage, équipes de réunions disponibles</span><span class="sxs-lookup"><span data-stu-id="d7ae6-206">0 - Skype preferred app on the Start Screen, Teams Meetings available</span></span><br><span data-ttu-id="d7ae6-207">1 - teams préféré application sur l’écran de démarrage, Skype réunions disponibles</span><span class="sxs-lookup"><span data-stu-id="d7ae6-207">1 - Teams preferred app on the Start Screen, Skype Meetings available</span></span><br><span data-ttu-id="d7ae6-208">2 - application exclusive d’équipes sur l’écran d’accueil (Skype app n’est pas disponible)</span><span class="sxs-lookup"><span data-stu-id="d7ae6-208">2 - Teams exclusive app on the Start screen (Skype app not available)</span></span> |
|<span data-ttu-id="d7ae6-209">Opérations</span><span class="sxs-lookup"><span data-stu-id="d7ae6-209">Operations</span></span>| <span data-ttu-id="d7ae6-210">Obtenir, définir</span><span class="sxs-lookup"><span data-stu-id="d7ae6-210">Get, Set</span></span>        |

|<span data-ttu-id="d7ae6-211">Paramètre</span><span class="sxs-lookup"><span data-stu-id="d7ae6-211">Setting</span></span>   |<span data-ttu-id="d7ae6-212">Valeur</span><span class="sxs-lookup"><span data-stu-id="d7ae6-212">Value</span></span>    |
|----------|---------|
|<span data-ttu-id="d7ae6-213"> Path</span><span class="sxs-lookup"><span data-stu-id="d7ae6-213">Path</span></span>      | <span data-ttu-id="d7ae6-214">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span><span class="sxs-lookup"><span data-stu-id="d7ae6-214">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span></span>        |
|<span data-ttu-id="d7ae6-215">Type de données</span><span class="sxs-lookup"><span data-stu-id="d7ae6-215">Data Type</span></span> | <span data-ttu-id="d7ae6-216">chaîne - ensemble chaîne aux équipes des ID de package d’application en tant que **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe ! Les équipes**</span><span class="sxs-lookup"><span data-stu-id="d7ae6-216">string - set string to Teams application package ID as **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams**</span></span> |
|<span data-ttu-id="d7ae6-217">Opérations</span><span class="sxs-lookup"><span data-stu-id="d7ae6-217">Operations</span></span>| <span data-ttu-id="d7ae6-218">Obtenir, définir</span><span class="sxs-lookup"><span data-stu-id="d7ae6-218">Get, Set</span></span>        |

<span data-ttu-id="d7ae6-219">Redémarrez le dispositif Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-219">Restart the Surface Hub device.</span></span> <span data-ttu-id="d7ae6-220">Après le redémarrage de l’appareil, vous devez être en mesure de démarrer l’application des équipes à partir de l’écran d’accueil et participer à une réunion à partir du calendrier.</span><span class="sxs-lookup"><span data-stu-id="d7ae6-220">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span>


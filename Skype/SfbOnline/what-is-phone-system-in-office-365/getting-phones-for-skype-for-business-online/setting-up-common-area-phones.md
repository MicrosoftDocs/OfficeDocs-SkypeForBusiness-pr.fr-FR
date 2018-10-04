---
title: Configuration des téléphones de zone commune
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Découvrez les étapes de déploiement pour obtenir le microprogramme approprié, mettre à jour si nécessaire, attribuer des licences et configurer les paramètres pour les téléphones en zone commune.
ms.openlocfilehash: 3faa66235f3c3364a0da6560a6dc52daa252915b
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370674"
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="a30e4-103">Configuration des téléphones de zone commune</span><span class="sxs-lookup"><span data-stu-id="a30e4-103">Set up common area phones</span></span>
<span data-ttu-id="a30e4-p101">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span><span class="sxs-lookup"><span data-stu-id="a30e4-p101">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="a30e4-107">Conditions préalables pour les téléphones de la zone commune</span><span class="sxs-lookup"><span data-stu-id="a30e4-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="a30e4-108">La première chose à faire est de confirmer que vous avez :</span><span class="sxs-lookup"><span data-stu-id="a30e4-108">The first thing you need to do is to confirm that you have the following:</span></span>

- <span data-ttu-id="a30e4-109">acheté une licence de téléphone de zone commune et un Forfait d'appels.</span><span class="sxs-lookup"><span data-stu-id="a30e4-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
- <span data-ttu-id="a30e4-110">recherché et acheté des téléphones approuvés (voir la liste [ici](deploying-skype-for-business-online-phones.md)).</span><span class="sxs-lookup"><span data-stu-id="a30e4-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>
- <span data-ttu-id="a30e4-p102">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:</span><span class="sxs-lookup"><span data-stu-id="a30e4-p102">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:</span></span>
  - <span data-ttu-id="a30e4-113">**Téléphones Polycom VVX**: accéder aux **paramètres** > **état** > **plateforme** > **Application** > **principal**.</span><span class="sxs-lookup"><span data-stu-id="a30e4-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
  - <span data-ttu-id="a30e4-114">**Téléphones Yealink**: accédez à **l’état** sur l’écran du téléphone principal.</span><span class="sxs-lookup"><span data-stu-id="a30e4-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
  - <span data-ttu-id="a30e4-115">**Téléphones AudioCodes**: accédez au **Menu** > **État du périphérique** > **version de microprogramme** à partir de l’écran d’accueil.</span><span class="sxs-lookup"><span data-stu-id="a30e4-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
  - <span data-ttu-id="a30e4-116">**Téléphones Lync Phone Edition (LPE)**: accédez au **Menu** > **Informations système** à partir de l’écran d’accueil.</span><span class="sxs-lookup"><span data-stu-id="a30e4-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="a30e4-p103">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span><span class="sxs-lookup"><span data-stu-id="a30e4-p103">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span>

    <span data-ttu-id="a30e4-p104">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span><span class="sxs-lookup"><span data-stu-id="a30e4-p104">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="a30e4-121">Configuration d’un téléphone de zone commune</span><span class="sxs-lookup"><span data-stu-id="a30e4-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="a30e4-122">Vous devrez suivre les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="a30e4-122">You will need to follow these steps:</span></span>

### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="a30e4-123">Étape 1 - Acheter les licences</span><span class="sxs-lookup"><span data-stu-id="a30e4-123">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="a30e4-124">Dans le centre d’administration Office 365, accédez à **Facturation** > **Services d’achats**, et ajouter **D’autres forfaits**.</span><span class="sxs-lookup"><span data-stu-id="a30e4-124">In the Office 365 admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP-license.png](../../images/cap-license.png)
2. <span data-ttu-id="a30e4-126">Cliquer sur **Téléphone de zone commune** > **Acheter maintenant** > sur la page **Commande** cliquez sur **Acheter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="a30e4-126">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="a30e4-p105">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span><span class="sxs-lookup"><span data-stu-id="a30e4-p105">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="a30e4-p106">You don't need a Phone System license. It's included with the **Common Area Phone** license.</span><span class="sxs-lookup"><span data-stu-id="a30e4-p106">You don't need a Phone System license. It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="a30e4-131">Pour plus d’informations sur les licences, consultez la section [Licences complémentaires pour Skype Entreprise et Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="a30e4-131">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="a30e4-132">Étape 2 - Créer un nouveau compte utilisateur pour le téléphone et attribuer les licences</span><span class="sxs-lookup"><span data-stu-id="a30e4-132">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="a30e4-133">Dans le centre d’administration Office 365, accédez à **Utilisateurs** > **Utilisateurs actifs** > **Ajouter un utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="a30e4-133">In the Office 365 admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="a30e4-134">Saisissez un **Nom d'utilisateur** comme « Réception » pour le prénom et « Principale » pour le nom.</span><span class="sxs-lookup"><span data-stu-id="a30e4-134">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="a30e4-135">Saisissez un **Nom d’affichage**, s’il n’est pas généré automatiquement, comme « Reception Principale ».</span><span class="sxs-lookup"><span data-stu-id="a30e4-135">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="a30e4-136">Saisissez un **Nom d'utilisateur** comme « RéceptionPrincipale » ou « HallPrincipal ».</span><span class="sxs-lookup"><span data-stu-id="a30e4-136">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="a30e4-p107">For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.</span><span class="sxs-lookup"><span data-stu-id="a30e4-p107">For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>

    > [!Tip]
    > <span data-ttu-id="a30e4-p108">WAIT!! Don't click **Add**!! Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user. Then on the user's properties page, click **Product licenses** and then click **Edit**. On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span><span class="sxs-lookup"><span data-stu-id="a30e4-p108">WAIT!! Don't click **Add**!! Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user. Then on the user's properties page, click **Product licenses** and then click **Edit**. On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

6. <span data-ttu-id="a30e4-p109">If you are still there, assign the licenses to this user. On the same page, click to expand **Product licenses**. Turn on the following:</span><span class="sxs-lookup"><span data-stu-id="a30e4-p109">If you are still there, assign the licenses to this user. On the same page, click to expand **Product licenses**. Turn on the following:</span></span>
   - <span data-ttu-id="a30e4-147">Téléphone de zone commune</span><span class="sxs-lookup"><span data-stu-id="a30e4-147">Common Area Phone</span></span>
   - <span data-ttu-id="a30e4-148">Ensuite, vous devez choisir soit un **Forfait d’appels nationaux** soit un **Forfait d’appels internationaux** et nationaux.</span><span class="sxs-lookup"><span data-stu-id="a30e4-148">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

     <span data-ttu-id="a30e4-149">L’attribution des licences ressemblera à :</span><span class="sxs-lookup"><span data-stu-id="a30e4-149">Assigning the licenses will look like:</span></span>

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > <span data-ttu-id="a30e4-151">Juste pour information, Le Forfait Skype Entreprise 2 est inclus avec la licence **Téléphone de zone commune**.</span><span class="sxs-lookup"><span data-stu-id="a30e4-151">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="a30e4-152">Pour plus de détails, reportez-vous à la section [Ajouter un utilisateur](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="a30e4-152">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="a30e4-153">Étape 3 - Attribuer un numéro de téléphone au compte utilisateur du téléphone de zone commune</span><span class="sxs-lookup"><span data-stu-id="a30e4-153">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="a30e4-154">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Attribution d’un numéro de téléphone à l’utilisateur en utilisant le **Centre d’administration Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="a30e4-154">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="a30e4-155">Dans le centre d’administration Office 365 > **centres d’administration** > **Skype pour les entreprises**.</span><span class="sxs-lookup"><span data-stu-id="a30e4-155">In the Office 365 admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="a30e4-156">Dans le **Centre d’administration Skype Entreprise** >  **Voix** > **Numéros de téléphone**.</span><span class="sxs-lookup"><span data-stu-id="a30e4-156">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="a30e4-157">Sélectionnez un numéro dans la liste des numéros de téléphone et cliquez sur **Attribuer**.</span><span class="sxs-lookup"><span data-stu-id="a30e4-157">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="a30e4-158">Sur la page **Attribuer**, dans la zone **Utilisateur vocal**, entrez le nom de l’utilisateur utilisé pour le téléphone, puis sélectionnez l'utilisateur dans la liste déroulante **Sélectionner un utilisateur vocal**.</span><span class="sxs-lookup"><span data-stu-id="a30e4-158">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span>
5. <span data-ttu-id="a30e4-p110">While you're there you will need to add an emergency address. Once you search, look under the **Select emergency address** to pick the right one for you.</span><span class="sxs-lookup"><span data-stu-id="a30e4-p110">While you're there you will need to add an emergency address. Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="a30e4-161">Cliquez sur **Enregistrer** et votre utilisateur devrait ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="a30e4-161">Click **Save** and your user should look like this:</span></span>

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="a30e4-p111">Users will only show up if they have a **Phone System** licence applied. If you just did this, then sometimes it takes a bit for the user to show up in the list.</span><span class="sxs-lookup"><span data-stu-id="a30e4-p111">Users will only show up if they have a **Phone System** licence applied. If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="a30e4-165">Pour plus de détails, reportez-vous à la section [Obtenir des numéros de téléphone pour vos utilisateurs](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="a30e4-165">For more stuff, see [Getting phone numbers for your users](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="a30e4-p112">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365. See, [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="a30e4-p112">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365. See, [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span></span>

### <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="a30e4-168">Étape 4 - Configuration de votre téléphone</span><span class="sxs-lookup"><span data-stu-id="a30e4-168">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="a30e4-169">**Réglage du mode sur un téléphone**</span><span class="sxs-lookup"><span data-stu-id="a30e4-169">**Setting the mode on a phone**</span></span>

<span data-ttu-id="a30e4-p113">The phone or phones you have must have the **Common Area Phone mode** turned on. You might want to check on that to make sure they do.</span><span class="sxs-lookup"><span data-stu-id="a30e4-p113">The phone or phones you have must have the **Common Area Phone mode** turned on. You might want to check on that to make sure they do.</span></span>

<span data-ttu-id="a30e4-172">**Voici un exemple de configuration d’un téléphone Polycom VVX**</span><span class="sxs-lookup"><span data-stu-id="a30e4-172">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="a30e4-173">Activez le mode de téléphone de zone commune pour le Polycom VVX en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="a30e4-173">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="a30e4-174">Dans votre navigateur, connectez-vous à l’interface Web pour pouvoir activer le mode TZC.</span><span class="sxs-lookup"><span data-stu-id="a30e4-174">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="a30e4-175">Ensuite aller sur **Réglage** et dans l’option **Paramètre Skype Entreprise**, sélectionnez **Téléphone de zone commune**.</span><span class="sxs-lookup"><span data-stu-id="a30e4-175">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="a30e4-176">Cliquez sur **OK** pour enregistrer vos paramètres.</span><span class="sxs-lookup"><span data-stu-id="a30e4-176">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="a30e4-p114">Now that CAP mode is enabled, set up the phone using the phone's display. The display should show **CaAP is enabled**. Then do the following:</span><span class="sxs-lookup"><span data-stu-id="a30e4-p114">Now that CAP mode is enabled, set up the phone using the phone's display. The display should show **CaAP is enabled**. Then do the following:</span></span>

    1. <span data-ttu-id="a30e4-180">Cliquez sur **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="a30e4-180">Click **Settings**.</span></span>
    2. <span data-ttu-id="a30e4-181">Sélectionnez **Avancé**.</span><span class="sxs-lookup"><span data-stu-id="a30e4-181">Select **Advanced**.</span></span>
    3. <span data-ttu-id="a30e4-182">Entrez le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="a30e4-182">Enter the password.</span></span>
    4. <span data-ttu-id="a30e4-183">Dans **Paramètres d’administration**, sélectionnez **Paramètres du téléphone de zone commune**.</span><span class="sxs-lookup"><span data-stu-id="a30e4-183">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="a30e4-184">Activer **TZC** et **Mode d’administration TZC**.</span><span class="sxs-lookup"><span data-stu-id="a30e4-184">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="a30e4-185">Cliquez sur **Enregistrer la configuration**.</span><span class="sxs-lookup"><span data-stu-id="a30e4-185">Click **Save Config**.</span></span>

- <span data-ttu-id="a30e4-186">Maintenant votre téléphone est prêt pour que vous puissiez vous connecter à partir de l’écran d’accueil.</span><span class="sxs-lookup"><span data-stu-id="a30e4-186">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="a30e4-187">Connectez-vous en sélectionnant **Paramètres** > **Fonctionnalités** > **Skype Entreprises.**</span><span class="sxs-lookup"><span data-stu-id="a30e4-187">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="a30e4-188">Sélectionnez **Informations d’identification de l’utilisateur**et sélectionnez **connexion Web (TZC)** pour générer un code.</span><span class="sxs-lookup"><span data-stu-id="a30e4-188">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="a30e4-189">Aller sur le [portail de provisionnement](https://aka.ms/skypecap)et connectez-vous en tant qu’**administrateur**.</span><span class="sxs-lookup"><span data-stu-id="a30e4-189">Go to the [provisioning portal](https://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="a30e4-190">Entrez le nom d’affichage (par exemple, Réception principale).</span><span class="sxs-lookup"><span data-stu-id="a30e4-190">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="a30e4-191">Si **Rechercher des téléphones de zone commune uniquement** est cochée, décochez la case et recommencez la recherche.</span><span class="sxs-lookup"><span data-stu-id="a30e4-191">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.</span></span>

    5. <span data-ttu-id="a30e4-192">Dans la fenêtre du code d'appariement, entrez le code affiché sur le téléphone et cliquez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="a30e4-192">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="a30e4-193">Après cette dernière étape, le téléphone devrait se connecter automatiquement.</span><span class="sxs-lookup"><span data-stu-id="a30e4-193">Following this last step, the phone should sign in automatically.</span></span>


> [!NOTE]
> <span data-ttu-id="a30e4-p115">The CAP provisioning site states it will reset the CAP account's password to a random password. Take note that the account the CAP is referring is the Azure Active Directory (AAD) account. If you created the account in AAD only then the process is straightforward. If you have synced an on premises Active Directory to AAD make sure to take note of the credentials you are using that will be changed by CAP provisioning.</span><span class="sxs-lookup"><span data-stu-id="a30e4-p115">The CAP provisioning site states it will reset the CAP account's password to a random password. Take note that the account the CAP is referring is the Azure Active Directory (AAD) account. If you created the account in AAD only then the process is straightforward. If you have synced an on premises Active Directory to AAD make sure to take note of the credentials you are using that will be changed by CAP provisioning.</span></span>


### <a name="related-topics"></a><span data-ttu-id="a30e4-198">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="a30e4-198">Related topics</span></span>

- <span data-ttu-id="a30e4-199">En savoir plus sur les téléphones disponibles sur [Déploiement des téléphones Skype Entreprise Online](deploying-skype-for-business-online-phones.md).</span><span class="sxs-lookup"><span data-stu-id="a30e4-199">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="a30e4-200">Obtention de numéros de téléphone pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="a30e4-200">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)



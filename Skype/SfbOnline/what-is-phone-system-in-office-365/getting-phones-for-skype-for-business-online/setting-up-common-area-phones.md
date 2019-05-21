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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Découvrez les étapes de déploiement pour obtenir le microprogramme approprié, le mettre à jour si nécessaire, affecter des licences et configurer des paramètres pour les téléphones communs.
ms.openlocfilehash: 59b681fecfe4fe6c2b9d89c7dbea875f30152340
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297987"
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="f1c22-103">Configuration des téléphones de zone commune</span><span class="sxs-lookup"><span data-stu-id="f1c22-103">Set up common area phones</span></span>
<span data-ttu-id="f1c22-p101">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span><span class="sxs-lookup"><span data-stu-id="f1c22-p101">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="f1c22-107">Conditions préalables pour les téléphones de la zone commune</span><span class="sxs-lookup"><span data-stu-id="f1c22-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="f1c22-108">La première chose à faire est de confirmer que vous avez :</span><span class="sxs-lookup"><span data-stu-id="f1c22-108">The first thing you need to do is to confirm that you have the following:</span></span>

- <span data-ttu-id="f1c22-109">acheté une licence de téléphone de zone commune et un Forfait d'appels.</span><span class="sxs-lookup"><span data-stu-id="f1c22-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
- <span data-ttu-id="f1c22-110">recherché et acheté des téléphones approuvés (voir la liste [ici](deploying-skype-for-business-online-phones.md)).</span><span class="sxs-lookup"><span data-stu-id="f1c22-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>
- <span data-ttu-id="f1c22-p102">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:</span><span class="sxs-lookup"><span data-stu-id="f1c22-p102">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:</span></span>
  - <span data-ttu-id="f1c22-113">**Polycom VVX téléphones**: accédez à \*\*\*\* > l’application**État** > de la**plateforme** > **principale**de l'**application** > .</span><span class="sxs-lookup"><span data-stu-id="f1c22-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
  - <span data-ttu-id="f1c22-114">**Numéros**de téléphone Yealink: accédez à Status ( **statut** ) sur l’écran principal.</span><span class="sxs-lookup"><span data-stu-id="f1c22-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
  - <span data-ttu-id="f1c22-115">**Téléphones AudioCodes**: accédez à l'**État** > de la**version du microprogramme** du **menu** > dans l’écran d’accueil.</span><span class="sxs-lookup"><span data-stu-id="f1c22-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
  - <span data-ttu-id="f1c22-116">**Téléphones Lync Phone Edition (LPE)**: accédez à**informations** sur le système de **menus** > dans l’écran d’accueil.</span><span class="sxs-lookup"><span data-stu-id="f1c22-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="f1c22-p103">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span><span class="sxs-lookup"><span data-stu-id="f1c22-p103">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span>

    <span data-ttu-id="f1c22-p104">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span><span class="sxs-lookup"><span data-stu-id="f1c22-p104">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="f1c22-121">Configuration d’un téléphone de zone commune</span><span class="sxs-lookup"><span data-stu-id="f1c22-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="f1c22-122">Vous devrez suivre les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="f1c22-122">You will need to follow these steps:</span></span>

### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="f1c22-123">Étape 1 - Acheter les licences</span><span class="sxs-lookup"><span data-stu-id="f1c22-123">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="f1c22-124">Dans le centre d’administration Office 365, accédez à **Facturation** > **Services d’achats**, et ajouter **D’autres forfaits**.</span><span class="sxs-lookup"><span data-stu-id="f1c22-124">In the Office 365 admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP-license.png](../../images/cap-license.png)
2. <span data-ttu-id="f1c22-126">Cliquer sur **Téléphone de zone commune** > **Acheter maintenant** > sur la page **Commande** cliquez sur **Acheter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="f1c22-126">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="f1c22-p105">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span><span class="sxs-lookup"><span data-stu-id="f1c22-p105">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="f1c22-p106">You don't need a Phone System license. It's included with the **Common Area Phone** license.</span><span class="sxs-lookup"><span data-stu-id="f1c22-p106">You don't need a Phone System license. It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="f1c22-131">Pour plus d’informations sur les licences, consultez la section [Licences complémentaires pour Skype Entreprise et Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="f1c22-131">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="f1c22-132">Étape 2 - Créer un nouveau compte utilisateur pour le téléphone et attribuer les licences</span><span class="sxs-lookup"><span data-stu-id="f1c22-132">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="f1c22-133">Dans le centre d’administration Office 365, accédez à **Utilisateurs** > **Utilisateurs actifs** > **Ajouter un utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="f1c22-133">In the Office 365 admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="f1c22-134">Saisissez un **Nom d'utilisateur** comme « Réception » pour le prénom et « Principale » pour le nom.</span><span class="sxs-lookup"><span data-stu-id="f1c22-134">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="f1c22-135">Saisissez un **Nom d’affichage**, s’il n’est pas généré automatiquement, comme « Reception Principale ».</span><span class="sxs-lookup"><span data-stu-id="f1c22-135">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="f1c22-136">Saisissez un **Nom d'utilisateur** comme « RéceptionPrincipale » ou « HallPrincipal ».</span><span class="sxs-lookup"><span data-stu-id="f1c22-136">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="f1c22-p107">For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.</span><span class="sxs-lookup"><span data-stu-id="f1c22-p107">For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="f1c22-139">Si vous êtes toujours là, attribuez les licences à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f1c22-139">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="f1c22-140">Sur la même page, cliquez pour développer **Licences produit**.</span><span class="sxs-lookup"><span data-stu-id="f1c22-140">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="f1c22-141">Activez l’élément suivant :</span><span class="sxs-lookup"><span data-stu-id="f1c22-141">Turn on the following:</span></span>
   - <span data-ttu-id="f1c22-142">Téléphone de zone commune</span><span class="sxs-lookup"><span data-stu-id="f1c22-142">Common Area Phone</span></span>
   - <span data-ttu-id="f1c22-143">Ensuite, vous devez choisir soit un **Forfait d’appels nationaux** soit un **Forfait d’appels internationaux** et nationaux.</span><span class="sxs-lookup"><span data-stu-id="f1c22-143">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

     <span data-ttu-id="f1c22-144">L’attribution des licences ressemblera à :</span><span class="sxs-lookup"><span data-stu-id="f1c22-144">Assigning the licenses will look like:</span></span>

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > <span data-ttu-id="f1c22-146">Juste pour information, Le Forfait Skype Entreprise 2 est inclus avec la licence **Téléphone de zone commune**.</span><span class="sxs-lookup"><span data-stu-id="f1c22-146">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="f1c22-147">Pour plus de détails, reportez-vous à la section [Ajouter un utilisateur](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="f1c22-147">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="f1c22-148">Étape 3 - Attribuer un numéro de téléphone au compte utilisateur du téléphone de zone commune</span><span class="sxs-lookup"><span data-stu-id="f1c22-148">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="f1c22-149">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Attribution d’un numéro de téléphone à l’utilisateur en utilisant le **Centre d’administration Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="f1c22-149">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="f1c22-150">Dans le centre d’administration Office 365 > les **centres** > **d’administration Skype entreprise**.</span><span class="sxs-lookup"><span data-stu-id="f1c22-150">In the Office 365 admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="f1c22-151">Dans le **Centre d’administration Skype Entreprise** >  **Voix** > **Numéros de téléphone**.</span><span class="sxs-lookup"><span data-stu-id="f1c22-151">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="f1c22-152">Sélectionnez un numéro dans la liste des numéros de téléphone et cliquez sur **Attribuer**.</span><span class="sxs-lookup"><span data-stu-id="f1c22-152">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="f1c22-153">Sur la page **Attribuer**, dans la zone **Utilisateur vocal**, entrez le nom de l’utilisateur utilisé pour le téléphone, puis sélectionnez l'utilisateur dans la liste déroulante **Sélectionner un utilisateur vocal**.</span><span class="sxs-lookup"><span data-stu-id="f1c22-153">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span>
5. <span data-ttu-id="f1c22-154">Pendant que vous êtes là, vous devrez ajouter une adresse d’urgence.</span><span class="sxs-lookup"><span data-stu-id="f1c22-154">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="f1c22-155">Une fois la recherche effectuée, regardez sous **Sélectionner l’adresse d’urgence** pour choisir celle qui vous convient.</span><span class="sxs-lookup"><span data-stu-id="f1c22-155">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="f1c22-156">Cliquez sur **Enregistrer** et votre utilisateur devrait ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="f1c22-156">Click **Save** and your user should look like this:</span></span>

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="f1c22-158">Les utilisateurs apparaîtront seulement s’ils possèdent une licence **Système téléphonique**.</span><span class="sxs-lookup"><span data-stu-id="f1c22-158">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="f1c22-159">Si vous venez d’attribuer, il faudra parfois attendre un moment pour que l’utilisateur apparaisse dans la liste.</span><span class="sxs-lookup"><span data-stu-id="f1c22-159">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="f1c22-160">Pour plus de détails, reportez-vous à la section [Obtenir des numéros de téléphone pour vos utilisateurs](/microsoftteams/getting-phone-numbers-for-your-users).</span><span class="sxs-lookup"><span data-stu-id="f1c22-160">For more stuff, see [Getting phone numbers for your users](/microsoftteams/getting-phone-numbers-for-your-users).</span></span>

<span data-ttu-id="f1c22-161">Sachez que vous pouvez également prendre le numéro de téléphone que vous avez avec un autre opérateur et le « *Porter* » ou le transférer sur Office 365.</span><span class="sxs-lookup"><span data-stu-id="f1c22-161">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="f1c22-162">Reportez-vous à la section [transférer des numéros de téléphone vers Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="f1c22-162">See, [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span></span>

### <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="f1c22-163">Étape 4 - Configuration de votre téléphone</span><span class="sxs-lookup"><span data-stu-id="f1c22-163">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="f1c22-164">**Réglage du mode sur un téléphone**</span><span class="sxs-lookup"><span data-stu-id="f1c22-164">**Setting the mode on a phone**</span></span>

<span data-ttu-id="f1c22-165">Le téléphone ou les téléphones que vous avez doivent avoir le **Mode de téléphone de zone commune** activé.</span><span class="sxs-lookup"><span data-stu-id="f1c22-165">The phone or phones you have must have the **Common Area Phone mode** turned on.</span></span> <span data-ttu-id="f1c22-166">Il serait interessant de vous assurer que ce mode soit bien activé.</span><span class="sxs-lookup"><span data-stu-id="f1c22-166">You might want to check on that to make sure they do.</span></span>

<span data-ttu-id="f1c22-167">**Voici un exemple de configuration d’un téléphone Polycom VVX**</span><span class="sxs-lookup"><span data-stu-id="f1c22-167">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="f1c22-168">Activez le mode de téléphone de zone commune pour le Polycom VVX en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="f1c22-168">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="f1c22-169">Dans votre navigateur, connectez-vous à l’interface Web pour pouvoir activer le mode TZC.</span><span class="sxs-lookup"><span data-stu-id="f1c22-169">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="f1c22-170">Ensuite aller sur **Réglage** et dans l’option **Paramètre Skype Entreprise**, sélectionnez **Téléphone de zone commune**.</span><span class="sxs-lookup"><span data-stu-id="f1c22-170">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="f1c22-171">Cliquez sur **OK** pour enregistrer vos paramètres.</span><span class="sxs-lookup"><span data-stu-id="f1c22-171">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="f1c22-172">Maintenant que le mode TZC est activé, configurez le téléphone en utilisant l’affichage du téléphone.</span><span class="sxs-lookup"><span data-stu-id="f1c22-172">Now that CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="f1c22-173">L’affichage devrait montrer **TZC est activé**.</span><span class="sxs-lookup"><span data-stu-id="f1c22-173">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="f1c22-174">Faites ensuite ceci :</span><span class="sxs-lookup"><span data-stu-id="f1c22-174">Then do the following:</span></span>

    1. <span data-ttu-id="f1c22-175">Cliquez sur **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="f1c22-175">Click **Settings**.</span></span>
    2. <span data-ttu-id="f1c22-176">Sélectionnez **avancé**.</span><span class="sxs-lookup"><span data-stu-id="f1c22-176">Select **Advanced**.</span></span>
    3. <span data-ttu-id="f1c22-177">Entrez le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="f1c22-177">Enter the password.</span></span>
    4. <span data-ttu-id="f1c22-178">Dans **Paramètres d’administration**, sélectionnez **Paramètres du téléphone de zone commune**.</span><span class="sxs-lookup"><span data-stu-id="f1c22-178">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="f1c22-179">Activer **TZC** et **Mode d’administration TZC**.</span><span class="sxs-lookup"><span data-stu-id="f1c22-179">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="f1c22-180">Cliquez sur **Enregistrer la configuration**.</span><span class="sxs-lookup"><span data-stu-id="f1c22-180">Click **Save Config**.</span></span>

- <span data-ttu-id="f1c22-181">Maintenant votre téléphone est prêt pour que vous puissiez vous connecter à partir de l’écran d’accueil.</span><span class="sxs-lookup"><span data-stu-id="f1c22-181">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="f1c22-182">Connectez-vous en sélectionnant **Paramètres** > **Fonctionnalités** > **Skype Entreprises.**</span><span class="sxs-lookup"><span data-stu-id="f1c22-182">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="f1c22-183">Sélectionnez **Informations d’identification de l’utilisateur**et sélectionnez **connexion Web (TZC)** pour générer un code.</span><span class="sxs-lookup"><span data-stu-id="f1c22-183">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="f1c22-184">Aller sur le [portail de provisionnement](https://aka.ms/skypecap)et connectez-vous en tant qu’**administrateur**.</span><span class="sxs-lookup"><span data-stu-id="f1c22-184">Go to the [provisioning portal](https://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="f1c22-185">Entrez le nom d’affichage (par exemple, Réception principale).</span><span class="sxs-lookup"><span data-stu-id="f1c22-185">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="f1c22-186">Si **Rechercher des téléphones de zone commune uniquement** est cochée, décochez la case et recommencez la recherche.</span><span class="sxs-lookup"><span data-stu-id="f1c22-186">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.</span></span>

    5. <span data-ttu-id="f1c22-187">Dans la fenêtre du code d'appariement, entrez le code affiché sur le téléphone et cliquez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="f1c22-187">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="f1c22-188">Après cette dernière étape, le téléphone devrait se connecter automatiquement.</span><span class="sxs-lookup"><span data-stu-id="f1c22-188">Following this last step, the phone should sign in automatically.</span></span>


> [!NOTE]
> <span data-ttu-id="f1c22-189">Le site d'attribution de privilèges d'accès CAP indique qu'il réinitialisera le mot de passe du compte CAP à un mot de passe aléatoire.</span><span class="sxs-lookup"><span data-stu-id="f1c22-189">The CAP provisioning site states it will reset the CAP account's password to a random password.</span></span> <span data-ttu-id="f1c22-190">Notez que le compte auquel fait référence le CAP est le compte Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="f1c22-190">Take note that the account the CAP is referring is the Azure Active Directory (AAD) account.</span></span> <span data-ttu-id="f1c22-191">Si vous avez créé le compte dans AAD uniquement, le processus est simple.</span><span class="sxs-lookup"><span data-stu-id="f1c22-191">If you created the account in AAD only then the process is straightforward.</span></span> <span data-ttu-id="f1c22-192">Si vous avez synchronisé un Active Directory local vers un environnement AAD et que vous utilisez un contrôle IDP ou ADFS tiers, la mise en service de la stratégie d’approvisionnement échoue.</span><span class="sxs-lookup"><span data-stu-id="f1c22-192">If you have synced an on premises Active Directory to AAD and you use a third-party IDP or ADFS, CAP provisioning will fail.</span></span> <span data-ttu-id="f1c22-193">Dans ce cas, vous ne devez utiliser qu’un compte Office 365/Azure Active Directory (par exemple, un compte avec un domaine **onmicrosoft.com** ) pour que la configuration de la fonction de mise en service de l’embout fonctionne.</span><span class="sxs-lookup"><span data-stu-id="f1c22-193">In this case, you need to use an Office 365/Azure Active Directory account only (for example, an account with **onmicrosoft.com** domain) for CAP provisioning to work.</span></span>


### <a name="related-topics"></a><span data-ttu-id="f1c22-194">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f1c22-194">Related topics</span></span>

- <span data-ttu-id="f1c22-195">En savoir plus sur les téléphones disponibles sur [Déploiement des téléphones Skype Entreprise Online](deploying-skype-for-business-online-phones.md).</span><span class="sxs-lookup"><span data-stu-id="f1c22-195">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="f1c22-196">Obtention des téléphones pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f1c22-196">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)



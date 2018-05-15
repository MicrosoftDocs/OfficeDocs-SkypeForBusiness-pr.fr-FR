---
title: Configurer des téléphones de partie commune
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
ms.openlocfilehash: bcf7d8eaf287af0b801168c62e7c22915f735aa2
ms.sourcegitcommit: 6b868f683e1f2354eb42fdf33911e77b7a3a83e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2018
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="a705b-103">Configurer des téléphones de partie commune</span><span class="sxs-lookup"><span data-stu-id="a705b-103">Set up common area phones</span></span>
<span data-ttu-id="a705b-104">Un téléphone en zone commune (CAP) est généralement placé dans une zone comme une salle d’attente ou une autre zone qui est disponible pour un grand nombre de personnes.</span><span class="sxs-lookup"><span data-stu-id="a705b-104">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people.</span></span> <span data-ttu-id="a705b-105">Par exemple, un téléphone en zone réception, salle de réunion ou de téléphone porte le téléphone majuscules sont configurés en tant que périphériques plutôt que les utilisateurs et établir automatiquement une connexion à un réseau.</span><span class="sxs-lookup"><span data-stu-id="a705b-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network.</span></span> <span data-ttu-id="a705b-106">Dans les étapes suivantes, nous allons vous aider à configurer un compte de système téléphonique avec des Plans de l’appel afin que vous pouvez déployer ces types de téléphones pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a705b-106">In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="a705b-107">Conditions requises pour les téléphones de partie commune</span><span class="sxs-lookup"><span data-stu-id="a705b-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="a705b-108">La première chose à faire consiste à vérifier que vous disposez des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a705b-108">The first thing you need to do is to confirm that you have the following:</span></span>

 - <span data-ttu-id="a705b-109">Acheter des licences téléphone en zone commune et un Plan d’appel.</span><span class="sxs-lookup"><span data-stu-id="a705b-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
 - <span data-ttu-id="a705b-110">Rechercher et téléphones approuvé (afficher la liste [ici](deploying-skype-for-business-online-phones.md)).</span><span class="sxs-lookup"><span data-stu-id="a705b-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>         
 - <span data-ttu-id="a705b-111">Mettre à jour du microprogramme de vos téléphones (voir prise en charge du microprogramme [dans cette rubrique](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="a705b-111">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md).</span></span>  <span data-ttu-id="a705b-112">Vous pouvez vérifier le microprogramme sur le téléphone vous en procédant ainsi :</span><span class="sxs-lookup"><span data-stu-id="a705b-112">You can check the firmware on you phone by doing this:</span></span>       
    - <span data-ttu-id="a705b-113">**Téléphones Polycom VVX**: accéder aux **paramètres** > **état** > **plateforme** > **Application** > **principal**.</span><span class="sxs-lookup"><span data-stu-id="a705b-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    - <span data-ttu-id="a705b-114">**Téléphones Yealink**: accédez à **l’état** sur l’écran du téléphone principal.</span><span class="sxs-lookup"><span data-stu-id="a705b-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
    - <span data-ttu-id="a705b-115">**Téléphones AudioCodes**: accédez au **Menu** > **État du périphérique** > **version de microprogramme** à partir de l’écran d’accueil.</span><span class="sxs-lookup"><span data-stu-id="a705b-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span> 
    - <span data-ttu-id="a705b-116">**Téléphones Lync Phone Edition (LPE)**: accédez au **Menu** > **Informations système** à partir de l’écran d’accueil.</span><span class="sxs-lookup"><span data-stu-id="a705b-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="a705b-117">Les mises à jour de microprogramme sont gérées par le service Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="a705b-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="a705b-118">Chaque microprogramme de téléphone certifié Skype Entreprise est chargé vers le serveur de mise à jour Skype Entreprise et la mise à jour de l'appareil est activée par défaut sur tous les téléphones.</span><span class="sxs-lookup"><span data-stu-id="a705b-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> 

    <span data-ttu-id="a705b-119">En fonction de la durée d'inactivité et des intervalles d'interrogation, les téléphones téléchargeront automatiquement les dernières versions certifiées.</span><span class="sxs-lookup"><span data-stu-id="a705b-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="a705b-120">Vous pouvez désactiver les paramètres de mise à jour des périphériques à l’aide de l’applet de commande [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) et au paramètre *EnableDeviceUpdate* `false`.</span><span class="sxs-lookup"><span data-stu-id="a705b-120">You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="a705b-121">Configuration d’un téléphone en zone commune</span><span class="sxs-lookup"><span data-stu-id="a705b-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="a705b-122">Vous devez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="a705b-122">You will need to follow these steps:</span></span>

### <a name="set-up-your-user-account-for-the-phone"></a><span data-ttu-id="a705b-123">Configurer votre compte d’utilisateur pour le téléphone</span><span class="sxs-lookup"><span data-stu-id="a705b-123">Set up your user account for the phone</span></span>

#### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="a705b-124">Étape 1 : acheter les licences</span><span class="sxs-lookup"><span data-stu-id="a705b-124">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="a705b-125">Dans le centre d’administration Office 365, accédez à la **facturation** > **services d’achat**, et ajouter **d’autres plans**.</span><span class="sxs-lookup"><span data-stu-id="a705b-125">In the Office 365 admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP-license.png](../../images/cap-license.png)
2. <span data-ttu-id="a705b-127">Cliquez sur **Téléphone en zone commune** > **acheter** > sur la page **Checkout** , cliquez sur **Acheter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="a705b-127">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="a705b-128">Cliquez sur pour les **abonnements de module complémentaire** , puis cliquez sur acheter un Plan de l’appel.</span><span class="sxs-lookup"><span data-stu-id="a705b-128">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan.</span></span> <span data-ttu-id="a705b-129">Choisissez **l’intérieur de l’appel de Plan** ou **appel nationale et International planifier**.</span><span class="sxs-lookup"><span data-stu-id="a705b-129">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="a705b-130">Vous n’avez pas besoin une licence de système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="a705b-130">You don't need a Phone System license.</span></span> <span data-ttu-id="a705b-131">Il est inclus avec la licence de **Téléphone en zone commune** .</span><span class="sxs-lookup"><span data-stu-id="a705b-131">It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="a705b-132">Pour plus d’informations sur les licences, voir [Skype pour les licences d’entreprise et les équipes Microsoft module complémentaire](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="a705b-132">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

#### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="a705b-133">Étape 2 : créer un nouveau compte d’utilisateur pour le téléphone et attribuer les licences</span><span class="sxs-lookup"><span data-stu-id="a705b-133">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="a705b-134">Dans le centre d’administration Office 365, accédez aux **utilisateurs** > **Utilisateurs actifs** > **Ajouter un utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="a705b-134">In the Office 365 admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="a705b-135">Placez dans un **nom d’utilisateur** comme « Main » pour le prénom et le « Réception » pour le nom du deuxième.</span><span class="sxs-lookup"><span data-stu-id="a705b-135">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="a705b-136">Placez dans un **nom d’affichage** si elle n’est pas générer automatiquement comme « Réception principal ».</span><span class="sxs-lookup"><span data-stu-id="a705b-136">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="a705b-137">Placez dans un **nom d’utilisateur** , tel que « MainReception » ou « Mainlobby ».</span><span class="sxs-lookup"><span data-stu-id="a705b-137">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="a705b-138">Pour les téléphones de partie commune, vous souhaitez définir un mot de passe manuellement ou ont le même mot de passe pour tous les téléphones de partie commune.</span><span class="sxs-lookup"><span data-stu-id="a705b-138">For common area phones, you might want to set a password manually or have the same password for all of you common area phones.</span></span> <span data-ttu-id="a705b-139">En outre, pensez à désélection **faire de cet utilisateur de modifier leur mot de passe lorsqu’ils se connectent tout d’abord**.</span><span class="sxs-lookup"><span data-stu-id="a705b-139">Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>

    > [!Tip]
    > <span data-ttu-id="a705b-140">ATTENDEZ !</span><span class="sxs-lookup"><span data-stu-id="a705b-140">WAIT!!</span></span> <span data-ttu-id="a705b-141">Ne cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="a705b-141">Don't click **Add**!!</span></span> <span data-ttu-id="a705b-142">Euh, si vous n’avez cliqué sur **Ajouter** ne ceci : centre d’administration Office 365 > **utilisateurs** > **utilisateurs** et Active puis rechercher l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a705b-142">Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user.</span></span> <span data-ttu-id="a705b-143">Cliquez sur page de propriétés de l’utilisateur, **les licences de produit** , puis sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="a705b-143">Then on the user's properties page, click **Product licenses** and then click **Edit**.</span></span> <span data-ttu-id="a705b-144">Dans la page **licences de produits** , activez le **Téléphone en zone commune** et choisir soit un **Intérieur appelant planifier** ou une national et **International appelant planifier**.</span><span class="sxs-lookup"><span data-stu-id="a705b-144">On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

6. <span data-ttu-id="a705b-145">Si vous êtes toujours là, attribuer les licences à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a705b-145">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="a705b-146">Sur la même page, cliquez pour développer des **licences de produits**.</span><span class="sxs-lookup"><span data-stu-id="a705b-146">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="a705b-147">Activer les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a705b-147">Turn on the following:</span></span>
    - <span data-ttu-id="a705b-148">Téléphone de partie commune</span><span class="sxs-lookup"><span data-stu-id="a705b-148">Common Area Phone</span></span>
    - <span data-ttu-id="a705b-149">Vous devez choisir soit un **Intérieur appelant planifier** ou une national et **International appelant planifier**.</span><span class="sxs-lookup"><span data-stu-id="a705b-149">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>
     
    <span data-ttu-id="a705b-150">Attribution de licences ressemblera à :</span><span class="sxs-lookup"><span data-stu-id="a705b-150">Assigning the licenses will look like:</span></span>

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > <span data-ttu-id="a705b-152">Ça, Skype pour Business Plan 2 est inclus dans la licence de **Téléphone en zone commune** .</span><span class="sxs-lookup"><span data-stu-id="a705b-152">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="a705b-153">Pour plus d’informations, voir [Ajouter un utilisateur](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="a705b-153">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

#### <a name="step-3---assign-a-phone-number-to-the-user"></a><span data-ttu-id="a705b-154">Étape 3 : attribuer un numéro de téléphone à l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="a705b-154">Step 3 - Assign a phone number to the user</span></span>
<span data-ttu-id="a705b-155">![SFB-logo-30x30.png](../../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="a705b-155">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
1. <span data-ttu-id="a705b-156">Dans le centre d’administration Office 365 > **centres d’administration** > **Skype pour les entreprises**.</span><span class="sxs-lookup"><span data-stu-id="a705b-156">In the Office 365 admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="a705b-157">Dans la **Skype pour le centre d’administration Business** >  **vocale** > **numéros de téléphone**.</span><span class="sxs-lookup"><span data-stu-id="a705b-157">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="a705b-158">Sélectionnez un numéro dans la liste des numéros de téléphone, cliquez sur **affecter**.</span><span class="sxs-lookup"><span data-stu-id="a705b-158">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="a705b-159">Dans la page **affecter** , dans la zone **utilisateur vocale** , entrez le nom de l’utilisateur qui est utilisé pour le téléphone puis sélectionnez l’utilisateur dans **Sélectionner un utilisateur vocal** de liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="a705b-159">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span> 
5. <span data-ttu-id="a705b-160">Lorsque vous y êtes, vous devez ajouter une adresse d’urgence.</span><span class="sxs-lookup"><span data-stu-id="a705b-160">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="a705b-161">Une fois que vous recherchez, examinez le **Sélectionnez adresse en cas d’urgence** à choisir celle de droite pour vous.</span><span class="sxs-lookup"><span data-stu-id="a705b-161">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="a705b-162">Cliquez sur **Enregistrer** et l’utilisateur doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="a705b-162">Click **Save** and your user should look like this:</span></span>

    ![Cap-utilisateur-number.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="a705b-164">Les utilisateurs seront affichent uniquement s’ils disposent d’une licence de **Système téléphonique** appliquée.</span><span class="sxs-lookup"><span data-stu-id="a705b-164">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="a705b-165">Si vous avez effectué uniquement cette, puis parfois nécessaire un peu de l’utilisateur s’affiche dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a705b-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="a705b-166">Pour d’autres objets, voir [mise en route des numéros de téléphone pour vos utilisateurs](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="a705b-166">For more stuff, see [Getting phone numbers for your users](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="a705b-167">Si vous vous demandez, vous pouvez également tirer votre numéro de téléphone que vous avez avec un autre transporteur et «*port*» ou leur transfert sur vers Office 365.</span><span class="sxs-lookup"><span data-stu-id="a705b-167">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="a705b-168">Consultez [transfert des numéros de téléphone vers Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="a705b-168">See, [Transfer phone numbers to Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span></span>

## <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="a705b-169">Étape 4 : configuration de votre téléphone</span><span class="sxs-lookup"><span data-stu-id="a705b-169">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="a705b-170">**Définir le mode sur un téléphone**</span><span class="sxs-lookup"><span data-stu-id="a705b-170">**Setting the mode on a phone**</span></span>

<span data-ttu-id="a705b-171">Le téléphone ou des téléphones que vous avez doivent avoir le mode de téléphone en zone commune activé.</span><span class="sxs-lookup"><span data-stu-id="a705b-171">The phone or phones you have must have the Common Area Phone mode turned on.</span></span> <span data-ttu-id="a705b-172">Vous voudrez peut-être vérifier que pour vous assurer de que leur.</span><span class="sxs-lookup"><span data-stu-id="a705b-172">You might want to check on that to make sure they do.</span></span> 

<span data-ttu-id="a705b-173">**Voici un exemple expliquant comment configurer un téléphone Polycom VVX**</span><span class="sxs-lookup"><span data-stu-id="a705b-173">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="a705b-174">Activer le mode de téléphone en zone commune pour le VVX Polycom en suivant ces étapes :</span><span class="sxs-lookup"><span data-stu-id="a705b-174">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="a705b-175">Dans votre navigateur, connectez-vous à l’interface web afin que vous pouvez activer le mode de point d’accès client.</span><span class="sxs-lookup"><span data-stu-id="a705b-175">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="a705b-176">Accédez au **paramètre** et dans l’option **Skype pour la configuration d’entreprise** , sélectionnez **Téléphone en zone commune**.</span><span class="sxs-lookup"><span data-stu-id="a705b-176">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="a705b-177">Cliquez sur **Oui** pour enregistrer vos paramètres.</span><span class="sxs-lookup"><span data-stu-id="a705b-177">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="a705b-178">Maintenant que le mode de cache est activé, vous pouvez configurer le téléphone à l’aide de l’affichage du téléphone.</span><span class="sxs-lookup"><span data-stu-id="a705b-178">Now that the CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="a705b-179">L’affichage doit contenir **CaAP est activé**.</span><span class="sxs-lookup"><span data-stu-id="a705b-179">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="a705b-180">Procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a705b-180">Then do the following:</span></span>

    1. <span data-ttu-id="a705b-181">Cliquez sur **paramètres**.</span><span class="sxs-lookup"><span data-stu-id="a705b-181">Click **Settings**.</span></span>
    2. <span data-ttu-id="a705b-182">Sélectionnez **Avancé**.</span><span class="sxs-lookup"><span data-stu-id="a705b-182">Select **Advanced**.</span></span>
    3. <span data-ttu-id="a705b-183">Entrez le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="a705b-183">Enter the password.</span></span>
    4. <span data-ttu-id="a705b-184">Dans les **paramètres d’Administration**, sélectionnez **Les paramètres de téléphonie zone commune**.</span><span class="sxs-lookup"><span data-stu-id="a705b-184">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="a705b-185">Activer **CAP** et **en Mode Admin CAP**.</span><span class="sxs-lookup"><span data-stu-id="a705b-185">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="a705b-186">Cliquez sur **Enregistrer la configuration**.</span><span class="sxs-lookup"><span data-stu-id="a705b-186">Click **Save Config**.</span></span>

- <span data-ttu-id="a705b-187">OK, maintenant votre téléphone étant prêt pouvoir vous connecter sur l’écran d’accueil.</span><span class="sxs-lookup"><span data-stu-id="a705b-187">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="a705b-188">Se connecter en sélectionnant **paramètres** > **fonctionnalités** > **Skype pour les entreprises.**</span><span class="sxs-lookup"><span data-stu-id="a705b-188">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="a705b-189">Sélectionnez les **Informations d’identification de l’utilisateur**et sélectionnez **web reconnectez-vous (CAP)** pour générer un code.</span><span class="sxs-lookup"><span data-stu-id="a705b-189">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="a705b-190">Accédez au [portail de mise en service](http://aka.ms/skypecap)et connectez-vous en tant **qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="a705b-190">Go to the [provisioning portal](http://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="a705b-191">Entrez le nom complet (par exemple, principal réception).</span><span class="sxs-lookup"><span data-stu-id="a705b-191">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="a705b-192">Si vous **Recherchez des téléphones en zone commune uniquement** est activée, désactivez la case à cocher et rechercher à nouveau. »</span><span class="sxs-lookup"><span data-stu-id="a705b-192">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.\`</span></span>

    5. <span data-ttu-id="a705b-193">Dans la fenêtre code jumelage, entrez le code affiché sur le téléphone, cliquez sur **mettre en service**.</span><span class="sxs-lookup"><span data-stu-id="a705b-193">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="a705b-194">La suite de cette dernière étape, le téléphone doit se connecter automatiquement.</span><span class="sxs-lookup"><span data-stu-id="a705b-194">Following this last step, the phone should sign in automatically.</span></span>

### <a name="related-topics"></a><span data-ttu-id="a705b-195">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="a705b-195">Related topics</span></span>

- <span data-ttu-id="a705b-196">En savoir plus sur les téléphones disponibles au [Déploiement de Skype pour les téléphones en ligne Business](deploying-skype-for-business-online-phones.md).</span><span class="sxs-lookup"><span data-stu-id="a705b-196">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="a705b-197">Obtention de numéros de téléphone pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="a705b-197">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)



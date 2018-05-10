---
title: Déploiement de téléphones Skype Entreprise Online
description: Découvrez les étapes de déploiement pour obtenir le microprogramme approprié, mettre à jour si nécessaire, attribuer des licences et configurer les paramètres pour les téléphones en zone commune.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
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
- Strat_SB_PSTN
ms.openlocfilehash: 453f9db6a022e924406594c567ea564b10f58694
ms.sourcegitcommit: 7ec95ea34422e635661f3659bbc43a7a3484ff99
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/09/2018
---
## <a name="common-area-phones"></a><span data-ttu-id="733af-103">Téléphones de partie commune</span><span class="sxs-lookup"><span data-stu-id="733af-103">Common Area Phones</span></span>
<span data-ttu-id="733af-104">Un téléphone en zone commune ou délimiter, est généralement placée dans une zone partagée et non associé à un utilisateur individuel.</span><span class="sxs-lookup"><span data-stu-id="733af-104">A common area phone, or CAP, is typically placed in a shared area and not associated with an individual user.</span></span> <span data-ttu-id="733af-105">Par exemple, un téléphone en zone réception, salle de réunion ou de téléphone porte le téléphone majuscules sont configurés en tant que périphériques plutôt que les utilisateurs et établir automatiquement une connexion au réseau.</span><span class="sxs-lookup"><span data-stu-id="733af-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically  sign in to the network.</span></span> <span data-ttu-id="733af-106">Dans les étapes suivantes, nous allons vous aider à configurer un compte pour le système téléphonique de Microsoft avec des Plans de l’appel, puis déployer une extrémité.</span><span class="sxs-lookup"><span data-stu-id="733af-106">In the steps below, we’ll help you set up an account for Microsoft Phone System with Calling Plans and then deploy a CAP.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="733af-107">Conditions requises pour les téléphones de partie commune</span><span class="sxs-lookup"><span data-stu-id="733af-107">Prerequisites for Common Area Phones</span></span>

<span data-ttu-id="733af-108">Vérifiez que vous disposez des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="733af-108">Confirm that you have the following:</span></span>

    - <span data-ttu-id="733af-109">Acheté téléphone en zone commune SKU</span><span class="sxs-lookup"><span data-stu-id="733af-109">Purchased Common Area Phone SKU</span></span> 
    - <span data-ttu-id="733af-110">Mise à jour de microprogramme (voir prise en charge du microprogramme dans la rubriquehttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="733af-110">Updated firmware (See Supported Firmware in topichttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span></span>
    - <span data-ttu-id="733af-111">Téléphones approuvés (consulter la liste àhttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)</span><span class="sxs-lookup"><span data-stu-id="733af-111">Approved  phones (view the list at https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)</span></span> 


## <a name="check-the-firmware-for-your-phone"></a><span data-ttu-id="733af-112">Vérification du microprogramme de votre téléphone</span><span class="sxs-lookup"><span data-stu-id="733af-112">Check the firmware for your phone</span></span>
- <span data-ttu-id="733af-113">**les téléphones Polycom VVX,**, accédez à **Settings (Paramètres)** > **Status (Statut)** > **Platform (Plate-forme)** > **Application** > **Main (Principal)**.</span><span class="sxs-lookup"><span data-stu-id="733af-113">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
- <span data-ttu-id="733af-114">**les téléphones Yealink**, accédez à **Status (Statut)** sur l'écran principal.</span><span class="sxs-lookup"><span data-stu-id="733af-114">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
- <span data-ttu-id="733af-115">**les téléphones AudioCodes**, accédez à **Menu** > **Device Status (Statut de l'appareil)** > **Firmware version (Version du microprogramme)** dans l'écran d'accueil.</span><span class="sxs-lookup"><span data-stu-id="733af-115">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span> 
- <span data-ttu-id="733af-116">**les téléphones Lync Phone Edition (LPE)**, accédez à **Menu** > **System Information (Informations système)** dans l'écran d'accueil.</span><span class="sxs-lookup"><span data-stu-id="733af-116">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>

<span data-ttu-id="733af-117">Les mises à jour de microprogramme sont gérées par le service Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="733af-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="733af-118">Chaque microprogramme de téléphone certifié Skype Entreprise est chargé vers le serveur de mise à jour Skype Entreprise et la mise à jour de l'appareil est activée par défaut sur tous les téléphones.</span><span class="sxs-lookup"><span data-stu-id="733af-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> 

<span data-ttu-id="733af-119">En fonction de la durée d'inactivité et des intervalles d'interrogation, les téléphones téléchargeront automatiquement les dernières versions certifiées.</span><span class="sxs-lookup"><span data-stu-id="733af-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="733af-120">Vous pouvez désactiver les paramètres de mise à jour des périphériques à l’aide de l’applet de commande [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) et au paramètre _EnableDeviceUpdate_ `false`.</span><span class="sxs-lookup"><span data-stu-id="733af-120">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>

## <a name="create-cap"></a><span data-ttu-id="733af-121">Créer le point d’accès client</span><span class="sxs-lookup"><span data-stu-id="733af-121">Create CAP</span></span>
<span data-ttu-id="733af-122">Vous créez le point d’accès client en configurant les paramètres avant de configurer le téléphone physique.</span><span class="sxs-lookup"><span data-stu-id="733af-122">You create the CAP by configuring the settings before you set up the physical phone.</span></span>

#### <a name="purchase-the-common-area-phone-sku"></a><span data-ttu-id="733af-123">Acheter un téléphone en zone commune SKU.</span><span class="sxs-lookup"><span data-stu-id="733af-123">Purchase the Common Area Phone SKU.</span></span> 
    In the Office 365 admin center, go to **Billing > Purchase Services**, and add **Common Area Phone**.

#### <a name="set-up-the-common-area-phone-----this-section-could-use-a-screen-shot--"></a><span data-ttu-id="733af-124">Configurer le téléphone en zone commune<!-- this section could use a screen shot--></span><span class="sxs-lookup"><span data-stu-id="733af-124">Set up the common area phone  <!-- this section could use a screen shot--></span></span>

<span data-ttu-id="733af-125">**Création d’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="733af-125">**Create user**</span></span> 
1. <span data-ttu-id="733af-126">Affecter le téléphone en zone commune SKU</span><span class="sxs-lookup"><span data-stu-id="733af-126">Assign Common Area Phone SKU</span></span>
2. <span data-ttu-id="733af-127">Affecter l’appel planifier (si vous utilisez le système téléphonique de Microsoft avec des Plans de l’appel).</span><span class="sxs-lookup"><span data-stu-id="733af-127">Assign Calling Plan (if using Microsoft Phone System with Calling Plans).</span></span> 
3. <span data-ttu-id="733af-128">Affecter un numéro de téléphone disponibles dans le Skype entreprise centre d’administration, ou demander un nouveau numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="733af-128">Assign an available telephone number in the Skype for Business Admin Center, or request a new telephone number.</span></span>

<span data-ttu-id="733af-129">**Créer un nouvel utilisateur**</span><span class="sxs-lookup"><span data-stu-id="733af-129">**Create New User**</span></span>

1. <span data-ttu-id="733af-130">Dans le volet Mise en service, vous pouvez entrer un prénom et le nom (par exemple, réception principal).</span><span class="sxs-lookup"><span data-stu-id="733af-130">In the provisioning pane, you have an option to enter a first and last name (for example, Reception Main).</span></span>
2. <span data-ttu-id="733af-131">Entrez un nom d’affichage (obligatoire), par exemple, « réception principal ».</span><span class="sxs-lookup"><span data-stu-id="733af-131">Enter a display name (required), for example, "Main Reception."</span></span>
3. <span data-ttu-id="733af-132">Entrez un nom d’utilisateur (obligatoire), par exemple « MainReception » @ » domaine » (nom de société ou entreprise)</span><span class="sxs-lookup"><span data-stu-id="733af-132">Enter a username (required), for example “MainReception” @” domain” (company or enterprise name)</span></span>
4. <span data-ttu-id="733af-133">Entrez l’emplacement (pays).</span><span class="sxs-lookup"><span data-stu-id="733af-133">Enter Location (country).</span></span>

<span data-ttu-id="733af-134">**Affecter le téléphone en zone commune SKU** Dans le centre d’administration Office 365, accédez à **facturation > Services d’achat** et ajoutez le **Téléphone en zone commune**</span><span class="sxs-lookup"><span data-stu-id="733af-134">**Assign Common Area Phone SKU** In the Office 365 admin center, go to **Billing > Purchase Services** and add **Common Area Phone**</span></span>

<span data-ttu-id="733af-135">**Affecter le Plan d’appel dans CAP SKU**</span><span class="sxs-lookup"><span data-stu-id="733af-135">**Assign Calling Plan in CAP SKU**</span></span>

1. <span data-ttu-id="733af-136">Sélectionnez un Plan de l’appel pour activer le téléphone.</span><span class="sxs-lookup"><span data-stu-id="733af-136">Select a Calling Plan to enable the phone.</span></span> 
2. <span data-ttu-id="733af-137">Ajouter le point d’accès client pour activer le système téléphonique et Skype pour Business Online Plan 2 dans le point d’extrémité.</span><span class="sxs-lookup"><span data-stu-id="733af-137">Add the CAP to enable the Phone System and Skype for Business Online Plan 2 in the CAP SKU.</span></span> <!-- odd order for step -->

<span data-ttu-id="733af-138">**Affecter un numéro de téléphone**</span><span class="sxs-lookup"><span data-stu-id="733af-138">**Assign a telephone number**</span></span>
1. <span data-ttu-id="733af-139">Vérifier les numéros de téléphone disponibles sous **vocale > numéros de téléphone**.</span><span class="sxs-lookup"><span data-stu-id="733af-139">Check for available phone numbers under **Voice > Phone Numbers**.</span></span>
2. <span data-ttu-id="733af-140">Sélectionnez un numéro dans la liste numéro de téléphone numéros disponibles.</span><span class="sxs-lookup"><span data-stu-id="733af-140">Select a number from the available list of phone numbers number.</span></span>
3. <span data-ttu-id="733af-141">Confirmer votre sélection en sélectionnant la **voix** et les **Numéros de téléphone**.</span><span class="sxs-lookup"><span data-stu-id="733af-141">Confirm your selection by selecting **Voice** and **Phone Numbers**.</span></span>

    ><span data-ttu-id="733af-142">[Note] Les utilisateurs de voix affichent uniquement s’ils disposent de la licence de système téléphonique appliquée, bien que même après avoir appliqué, peut prendre du temps pour actualiser.</span><span class="sxs-lookup"><span data-stu-id="733af-142">[Note] Voice users only show if they have the Phone System licence applied, although even after applying, it can take time to refresh.</span></span> <span data-ttu-id="733af-143">Permet de centre de soi à un moment rouvrir Skype pour administrateur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="733af-143">Sometime reopening Skype for Business Admin center helps.</span></span>
    
## <a name="configure-phone"></a><span data-ttu-id="733af-144">Configurer le téléphone</span><span class="sxs-lookup"><span data-stu-id="733af-144">Configure Phone</span></span>

<span data-ttu-id="733af-145">**Préparer les téléphones physiques**</span><span class="sxs-lookup"><span data-stu-id="733af-145">**Prepare the physical phones**</span></span> 

<span data-ttu-id="733af-146">Votre téléphone sélectionné doit avoir le mode de téléphone en zone commune.</span><span class="sxs-lookup"><span data-stu-id="733af-146">Your selected phone needs to have the Common Area Phone mode.</span></span> 

<span data-ttu-id="733af-147">***Téléphone de Polycom VVX exemple***</span><span class="sxs-lookup"><span data-stu-id="733af-147">***Example Polycom VVX phone***</span></span>

<span data-ttu-id="733af-148">Activer le Mode téléphone zone commune sur Polycom VVX en suivant ces étapes :</span><span class="sxs-lookup"><span data-stu-id="733af-148">Enable Common Area Phone Mode on Polycom VVX by following these steps:</span></span>
1. <span data-ttu-id="733af-149">Dans votre navigateur, utilisez l’interface web pour activer le mode de point d’accès client sur le VVX</span><span class="sxs-lookup"><span data-stu-id="733af-149">In your browser, use the web interface to enable CAP mode on the VVX</span></span>
2. <span data-ttu-id="733af-150">Accédez au **paramètre** et le Skype pour l’option de configuration d’entreprise, sélectionnez **Téléphone en zone commune**.</span><span class="sxs-lookup"><span data-stu-id="733af-150">Go to **Setting**  and in the Skype for Business Setting option, select **Common Area Phone**.</span></span>
3. <span data-ttu-id="733af-151">Cliquez sur **Enregistrer** pour enregistrer vos paramètres de configuration.</span><span class="sxs-lookup"><span data-stu-id="733af-151">Click **Save** to save your configuration settings.</span></span>

<span data-ttu-id="733af-152">Maintenant que le mode de téléphone CAP est activé, vous pouvez configurer le téléphone à l’aide de l’affichage du téléphone.</span><span class="sxs-lookup"><span data-stu-id="733af-152">Now that the CAP phone mode is enabled, set up the phone using the phone's display.</span></span>

1. <span data-ttu-id="733af-153">Dans les paramètres, cliquez sur **Avancé**.</span><span class="sxs-lookup"><span data-stu-id="733af-153">In the Settings, select **Advanced**.</span></span>
2. <span data-ttu-id="733af-154">Entrez le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="733af-154">Enter password.</span></span>
3. <span data-ttu-id="733af-155">Dans les paramètres d’Administration, sélectionnez **Les paramètres de téléphonie zone commune**.</span><span class="sxs-lookup"><span data-stu-id="733af-155">In Administration settings, select **Common Area Phone Settings**.</span></span>
4. <span data-ttu-id="733af-156">Activer le téléphone de partie commune et délimiter Admin</span><span class="sxs-lookup"><span data-stu-id="733af-156">Enable Common Area Phone and CAP Admin</span></span>
5. <span data-ttu-id="733af-157">Sélectionnez **Enregistrer la configuration**.</span><span class="sxs-lookup"><span data-stu-id="733af-157">Select **Save Config**.</span></span>

<span data-ttu-id="733af-158">Votre téléphone est prêt à être mis en service, ce qui vous serez amené à vous connecter sur l’écran d’accueil.</span><span class="sxs-lookup"><span data-stu-id="733af-158">Your phone is ready to be provisioned, which you'll do when you sign in on the home screen.</span></span>

1. <span data-ttu-id="733af-159">Se connecter en sélectionnant **Paramètres > fonctionnalités > Skype pour les entreprises.**</span><span class="sxs-lookup"><span data-stu-id="733af-159">Sign in by selecting **settings > features > Skype for Business.**</span></span>
2. <span data-ttu-id="733af-160">Sélectionnez les informations d’identification de l’utilisateur, puis sélectionnez Sélectionner **web reconnectez-vous (CAP)** pour générer un code...</span><span class="sxs-lookup"><span data-stu-id="733af-160">Select User Credentials, and select select **web sign-in (CAP)** to generate a code..</span></span>
3. <span data-ttu-id="733af-161">Accédez à la mise en service portal http://aka.ms/skypecapet se connecter en tant **qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="733af-161">Go to the provisioning portal http://aka.ms/skypecap, and sign in as **admin**.</span></span>
4. <span data-ttu-id="733af-162">Entrez le nom complet (par exemple, principal réception) pour afficher votre point d’accès client.</span><span class="sxs-lookup"><span data-stu-id="733af-162">Enter display name (for example, Main Reception) to view your CAP.</span></span>

><span data-ttu-id="733af-163">[Note] Si « Recherche pour seulement les téléphones de partie commune » est activée, désactivez la case à cocher et effectuez une nouvelle recherche.</span><span class="sxs-lookup"><span data-stu-id="733af-163">[Note] If “Search for Common Area Phones only” is checked, clear the checkbox and search again.</span></span>

5. <span data-ttu-id="733af-164">Dans la fenêtre code jumelage, entrez le code affiché sur le téléphone, cliquez sur **mettre en service**.</span><span class="sxs-lookup"><span data-stu-id="733af-164">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

<span data-ttu-id="733af-165">RS cette dernière étape, le téléphone doit se connecter automatiquement.</span><span class="sxs-lookup"><span data-stu-id="733af-165">Wht this last step, the phone should sign in automatically.</span></span>

<span data-ttu-id="733af-166">Pour plus d’informations sur les téléphones disponibles à [ ](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).</span><span class="sxs-lookup"><span data-stu-id="733af-166">Learn more about available phones at [](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).</span></span>



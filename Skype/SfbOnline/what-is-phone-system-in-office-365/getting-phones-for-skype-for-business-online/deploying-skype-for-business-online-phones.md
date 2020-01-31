---
title: Déploiement de téléphones Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
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
description: Découvrez les étapes de déploiement pour obtenir le microprogramme approprié, le mettre à jour si nécessaire, affecter des licences et configurer des paramètres pour des téléphones Skype entreprise online.
ms.openlocfilehash: 10562165547a27bb8a2903e7f11f3c547cca1b1e
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628380"
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="a1a7e-103">Déploiement de téléphones Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="a1a7e-103">Deploying Skype for Business Online phones</span></span>

<span data-ttu-id="a1a7e-104">Ce guide de déploiement vous aidera à déployer des téléphones IP Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="a1a7e-105">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-105">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business.</span></span> <span data-ttu-id="a1a7e-106">Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-106">Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices.</span></span> <span data-ttu-id="a1a7e-107">You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="a1a7e-107">You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="a1a7e-108">Étapes de déploiement pour les téléphones IP</span><span class="sxs-lookup"><span data-stu-id="a1a7e-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="a1a7e-109">Étape 1 : télécharger les guides de l'administrateur et les manuels de téléphone du fabricant</span><span class="sxs-lookup"><span data-stu-id="a1a7e-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="a1a7e-110">Avant de commencer, il est pertinent de télécharger les guides d'administration et les manuels de téléphone du fabricant.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="a1a7e-111">Dans le cas de téléphones Polycom, consultez le guide [Polycom Deployment Guide](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span><span class="sxs-lookup"><span data-stu-id="a1a7e-111">For Polycom phones, see the [Polycom Deployment Guide](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span></span>
    
- <span data-ttu-id="a1a7e-112">Pour les téléphones Yealink, reportez-vous à la rubrique [solution de téléphone SIP HD Yealink Skype entreprise](http://www.yealink.com/products_top_2.html).</span><span class="sxs-lookup"><span data-stu-id="a1a7e-112">For Yealink phones, see [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="a1a7e-113">Dans le cas de téléphones AudioCodes, consultez le guide [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span><span class="sxs-lookup"><span data-stu-id="a1a7e-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="a1a7e-114">Étape 2 : vérifier que votre achat ou migration concerne un téléphone IP et un microprogramme pris en charge par Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="a1a7e-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="a1a7e-115">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-115">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true.</span></span> <span data-ttu-id="a1a7e-116">To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="a1a7e-116">To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="a1a7e-117">Étape 3 : vérifier que le microprogramme adéquat est installé et le mettre à jour si nécessaire</span><span class="sxs-lookup"><span data-stu-id="a1a7e-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="a1a7e-118">Check the firmware version on your phones.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-118">Check the firmware version on your phones.</span></span> <span data-ttu-id="a1a7e-119">For:</span><span class="sxs-lookup"><span data-stu-id="a1a7e-119">For:</span></span>
  
- <span data-ttu-id="a1a7e-120">**les téléphones Polycom VVX,**, accédez à **Settings (Paramètres)** > **Status (Statut)** > **Platform (Plate-forme)** > **Application** > **Main (Principal)**.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="a1a7e-121">**les téléphones Yealink**, accédez à **Status (Statut)** sur l'écran principal.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="a1a7e-122">**les téléphones AudioCodes**, accédez à **Menu** > **Device Status (Statut de l'appareil)** > **Firmware version (Version du microprogramme)** dans l'écran d'accueil.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a1a7e-123">For remote access to phone details, refer to manufacturer administration guides.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-123">For remote access to phone details, refer to manufacturer administration guides.</span></span> <span data-ttu-id="a1a7e-124">See the links above for the user guides and phone manuals.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-124">See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="a1a7e-125">**les téléphones Lync Phone Edition (LPE)**, accédez à **Menu** > **System Information (Informations système)** dans l'écran d'accueil.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="a1a7e-126">Étape 4 : remarques sur la mise à jour de l'appareil</span><span class="sxs-lookup"><span data-stu-id="a1a7e-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="a1a7e-127">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock."</span><span class="sxs-lookup"><span data-stu-id="a1a7e-127">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock."</span></span> <span data-ttu-id="a1a7e-128">Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-128">Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured.</span></span> <span data-ttu-id="a1a7e-129">Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span><span class="sxs-lookup"><span data-stu-id="a1a7e-129">Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="a1a7e-130">Firmware updates are managed by the Skype for Business Service.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-130">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="a1a7e-131">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-131">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> <span data-ttu-id="a1a7e-132">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-132">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="a1a7e-133">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-133">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![Capture d’écran montrant le déploiement de téléphones](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="a1a7e-135">When a new firmware is available and ready for download and install, the phone will notify the user.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-135">When a new firmware is available and ready for download and install, the phone will notify the user.</span></span> <span data-ttu-id="a1a7e-136">Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-136">Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span></span>
  
![Capture d’écran montrant les options de mise à jour et de report.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="a1a7e-138">Dans le cas d'un téléphone Polycom, vous pouvez mettre à jour le microprogramme en sélectionnant **SwUpdate (Mise à jour logicielle)**.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![Capture d’écran montrant l’option SWupdate (](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="a1a7e-p108">Vous pouvez également gérer les mises à jour du microprogramme à l'aide d'un système de provisionnement partenaire. Pour plus d'informations sur la gestion de système de provisionnement partenaire, notamment la personnalisation de téléphone avancée, consultez les guide d'administration du fabricant.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-p108">You can also choose to manage firmware updates using a partner provisioning system. For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="a1a7e-142">Veillez à disposer d'une seule autorité de mise à jour pour l'appareil (mise à jour intrabande ou serveur de provisionnement tiers) pour éviter toute boucle de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="a1a7e-143">Étape 5 : paramètres du téléphone de configuration et d’infrastructure</span><span class="sxs-lookup"><span data-stu-id="a1a7e-143">Step 5 - Configuration and infrastructure phone settings</span></span>

<span data-ttu-id="a1a7e-p109">Vous pouvez configurer les options et stratégies téléphoniques les plus utilisées à l'aide d'applets de commande Windows PowerShell de gestion intrabande pour Skype Entreprise. Consultez le lien [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) pour plus de détails sur ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-p109">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="a1a7e-146">Pour la planification de l’infrastructure réseau, voir [infrastructure d’opérations Skype](https://www.skypeoperationsframework.com/).</span><span class="sxs-lookup"><span data-stu-id="a1a7e-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="a1a7e-147">Étape 6 : préparation de la connexion des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="a1a7e-147">Step 6 - Preparing for users to sign in</span></span>

<span data-ttu-id="a1a7e-148">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-148">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses.</span></span> <span data-ttu-id="a1a7e-149">At a minimum, you will need to assign a Phone System license and a Calling Plan.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-149">At a minimum, you will need to assign a Phone System license and a Calling Plan.</span></span> <span data-ttu-id="a1a7e-150">For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="a1a7e-150">For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
  
<span data-ttu-id="a1a7e-151">Pour en savoir plus sur les offres d’appel, consultez la documentation relative au [système téléphonique et aux offres d’appels](/microsoftteams/calling-plan-landing-page) .</span><span class="sxs-lookup"><span data-stu-id="a1a7e-151">You can find out more about Calling Plans by reading [Phone System and Calling Plans](/microsoftteams/calling-plan-landing-page)</span></span>
  
- <span data-ttu-id="a1a7e-152">Les **options de connexion** disponibles pour les utilisateurs Online sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a1a7e-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="a1a7e-153">Les utilisateurs de téléphones **Polycom VVX 5xx/6xx** verront :</span><span class="sxs-lookup"><span data-stu-id="a1a7e-153">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Capture d’écran montrant la connexion de téléphones Polycom](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="a1a7e-155">Les utilisateurs de téléphones **YEALINK VVX t48g/t46g verront** verront :</span><span class="sxs-lookup"><span data-stu-id="a1a7e-155">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Capture d’écran montrant la connexion de téléphones Yealink.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="a1a7e-157">Pour plus d’informations sur les options de connexion prises en charge par le fabricant, consultez la rubrique [réception de téléphones pour Skype entreprise Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="a1a7e-157">For details on sign-in options supported by the manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="a1a7e-p111">**ID d'utilisateur** À l'aide de leur clavier téléphonique ou de leur clavier visuel (le cas échéant), les utilisateurs peuvent se servir du nom d'utilisateur et du mot de passe de leur organisation pour se connecter à leur téléphone. Par exemple, ils doivent utiliser le format UPN (par ex. : <em>amosm@contoso.com</em>  pour leur nom d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-p111">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like <em>amosm@contoso.com</em>  for their user name.</span></span>
    
     ![Capture d’écran montrant l’écran de connexion](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="a1a7e-161">L'authentification par code confidentiel n'est pas prise en charge par Skype Entreprise Online avec les téléphones LPE et PIP (Partner IP Phone).</span><span class="sxs-lookup"><span data-stu-id="a1a7e-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="a1a7e-162">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-162">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App.</span></span> <span data-ttu-id="a1a7e-163">See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-163">See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="a1a7e-p113">Les utilisateurs doivent se servir du nom d'utilisateur et du mot de passe de leur organisation pour se connecter à leur téléphone. Par exemple, ils doivent utiliser le format UPN (par ex. :  <em>amosm@contoso.com</em>  pour leur nom d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-p113">Users are required to use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like  <em>amosm@contoso.com</em>  for their user name.</span></span>
  
     ![Capture d’écran montrant l’écran de connexion](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="a1a7e-167">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-167">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser.</span></span> <span data-ttu-id="a1a7e-168">Users will be provided with a set of instructions to follow when they use a browser to sign in.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-168">Users will be provided with a set of instructions to follow when they use a browser to sign in.</span></span>
    
  - <span data-ttu-id="a1a7e-169">Les utilisateurs de téléphones **Polycom VVX 5xx/6xx** verront :</span><span class="sxs-lookup"><span data-stu-id="a1a7e-169">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Capture d’écran montrant les instructions Polycom](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="a1a7e-171">Les utilisateurs de téléphones **YEALINK VVX t48g/t46g verront** verront :</span><span class="sxs-lookup"><span data-stu-id="a1a7e-171">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Capture d’écran montrant les instructions de Yealink](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="a1a7e-173">The code that is generated will expire in 15 minutes.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-173">The code that is generated will expire in 15 minutes.</span></span> <span data-ttu-id="a1a7e-174">When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-174">When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span></span>
    
  - <span data-ttu-id="a1a7e-175">Les utilisateurs de téléphones **Polycom VVX 5xx/6xx** verront :</span><span class="sxs-lookup"><span data-stu-id="a1a7e-175">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Capture d’écran montrant le code Polycom expiré](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="a1a7e-177">Les utilisateurs de téléphones **YEALINK VVX t48g/t46g verront** verront :</span><span class="sxs-lookup"><span data-stu-id="a1a7e-177">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Capture d’écran montrant le code Yealink expiré](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="a1a7e-179">À l'aide d'un navigateur, accédez à l'adresse affichée dans le téléphone et saisissez votre nom d'utilisateur Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![Capture d’écran montrant la vérification de l’e-mail](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="a1a7e-181">Entrez le code qui s'affiche sur le téléphone.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-181">Enter the code shown on the phone.</span></span>
    
     ![Capture d’écran montrant le code de saisie sur l’écran de connexion](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="a1a7e-183">Vérifiez que le site indique « [nom du fabricant du téléphone] **téléphone certifié Skype entreprise**» et cliquez sur **Continuer**.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**," and click **Continue**.</span></span>
    
     ![Capture d’écran montrant la vérification du nom](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="a1a7e-185">Cliquez sur les informations de connexion de l'utilisateur ou sur **Use another account (Utiliser un autre compte)**:</span><span class="sxs-lookup"><span data-stu-id="a1a7e-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![Capture d’écran montrant les options d’information d’identification](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="a1a7e-187">Lorsque la page suivante s’affiche, vous pouvez fermer le navigateur en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-187">When the following page is displayed, it is safe to close the browser.</span></span>
    
     ![Capture d’écran montrant un message de confirmation](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="a1a7e-189">Les téléphones LPE pour Skype Entreprise Online prennent en charge la connexion via un périphérique USB uniquement.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="a1a7e-190">**Déploiements pris en charge** Le tableau ci-après indique les types d'authentification pris en charge pour les modèles de déploiement actuellement pris en charge, y compris l'intégration d'Exchange, l'authentification moderne avec Multi-factor Authentication (MFA), et Skype Entreprise Online sur site.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a1a7e-191">**Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="a1a7e-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="a1a7e-192">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="a1a7e-192">**Exchange**</span></span> <br/> |<span data-ttu-id="a1a7e-193">**Méthode de connexion au téléphone**</span><span class="sxs-lookup"><span data-stu-id="a1a7e-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="a1a7e-194">**Accès à Skype entreprise**</span><span class="sxs-lookup"><span data-stu-id="a1a7e-194">**Skype for Business access**</span></span> <br/> |<span data-ttu-id="a1a7e-195">**Accès à Exchange avec Auth. moderne et MFA activées**</span><span class="sxs-lookup"><span data-stu-id="a1a7e-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="a1a7e-196">**Accès à Exchange avec Auth. moderne et MFA désactivées**</span><span class="sxs-lookup"><span data-stu-id="a1a7e-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="a1a7e-197">En ligne</span><span class="sxs-lookup"><span data-stu-id="a1a7e-197">Online</span></span>  <br/> |<span data-ttu-id="a1a7e-198">En ligne</span><span class="sxs-lookup"><span data-stu-id="a1a7e-198">Online</span></span>  <br/> |<span data-ttu-id="a1a7e-199">Connexion Web</span><span class="sxs-lookup"><span data-stu-id="a1a7e-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="a1a7e-200">Oui</span><span class="sxs-lookup"><span data-stu-id="a1a7e-200">Yes</span></span>  <br/> |<span data-ttu-id="a1a7e-201">Oui</span><span class="sxs-lookup"><span data-stu-id="a1a7e-201">Yes</span></span>  <br/> |<span data-ttu-id="a1a7e-202">Oui</span><span class="sxs-lookup"><span data-stu-id="a1a7e-202">Yes</span></span>  <br/> |
|<span data-ttu-id="a1a7e-203">En ligne</span><span class="sxs-lookup"><span data-stu-id="a1a7e-203">Online</span></span>  <br/> |<span data-ttu-id="a1a7e-204">En ligne</span><span class="sxs-lookup"><span data-stu-id="a1a7e-204">Online</span></span>  <br/> |<span data-ttu-id="a1a7e-205">Nom d'utilisateur/Mot de passe</span><span class="sxs-lookup"><span data-stu-id="a1a7e-205">Username/Password</span></span>  <br/> |<span data-ttu-id="a1a7e-206">Oui</span><span class="sxs-lookup"><span data-stu-id="a1a7e-206">Yes</span></span>  <br/> |<span data-ttu-id="a1a7e-207">Oui</span><span class="sxs-lookup"><span data-stu-id="a1a7e-207">Yes</span></span>  <br/> |<span data-ttu-id="a1a7e-208">Non</span><span class="sxs-lookup"><span data-stu-id="a1a7e-208">No</span></span>  <br/> |
|<span data-ttu-id="a1a7e-209">En ligne</span><span class="sxs-lookup"><span data-stu-id="a1a7e-209">Online</span></span>  <br/> |<span data-ttu-id="a1a7e-210">Sur site</span><span class="sxs-lookup"><span data-stu-id="a1a7e-210">On-premises</span></span>  <br/> |<span data-ttu-id="a1a7e-211">Connexion Web</span><span class="sxs-lookup"><span data-stu-id="a1a7e-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="a1a7e-212">Oui</span><span class="sxs-lookup"><span data-stu-id="a1a7e-212">Yes</span></span>  <br/> |<span data-ttu-id="a1a7e-213">Non</span><span class="sxs-lookup"><span data-stu-id="a1a7e-213">No</span></span>  <br/> |<span data-ttu-id="a1a7e-214">Non</span><span class="sxs-lookup"><span data-stu-id="a1a7e-214">No</span></span>  <br/> |
|<span data-ttu-id="a1a7e-215">En ligne</span><span class="sxs-lookup"><span data-stu-id="a1a7e-215">Online</span></span>  <br/> |<span data-ttu-id="a1a7e-216">Sur site</span><span class="sxs-lookup"><span data-stu-id="a1a7e-216">On-Premises</span></span>  <br/> |<span data-ttu-id="a1a7e-217">Nom d'utilisateur/Mot de passe</span><span class="sxs-lookup"><span data-stu-id="a1a7e-217">Username/Password</span></span>  <br/> |<span data-ttu-id="a1a7e-218">Oui</span><span class="sxs-lookup"><span data-stu-id="a1a7e-218">Yes</span></span>  <br/> |<span data-ttu-id="a1a7e-219">Oui</span><span class="sxs-lookup"><span data-stu-id="a1a7e-219">Yes</span></span>  <br/> |<span data-ttu-id="a1a7e-220">Non</span><span class="sxs-lookup"><span data-stu-id="a1a7e-220">No</span></span>  <br/> |
|<span data-ttu-id="a1a7e-221">Sur site</span><span class="sxs-lookup"><span data-stu-id="a1a7e-221">On-premises</span></span>  <br/> |<span data-ttu-id="a1a7e-222">En ligne/sur site</span><span class="sxs-lookup"><span data-stu-id="a1a7e-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="a1a7e-223">Authentification par code confidentiel</span><span class="sxs-lookup"><span data-stu-id="a1a7e-223">PIN Authentication</span></span>  <br/> |<span data-ttu-id="a1a7e-224">Oui</span><span class="sxs-lookup"><span data-stu-id="a1a7e-224">Yes</span></span>  <br/> |<span data-ttu-id="a1a7e-225">Non</span><span class="sxs-lookup"><span data-stu-id="a1a7e-225">No</span></span>  <br/> |<span data-ttu-id="a1a7e-226">Non</span><span class="sxs-lookup"><span data-stu-id="a1a7e-226">No</span></span>  <br/> |
|<span data-ttu-id="a1a7e-227">Sur site</span><span class="sxs-lookup"><span data-stu-id="a1a7e-227">On-premises</span></span>  <br/> |<span data-ttu-id="a1a7e-228">En ligne/sur site</span><span class="sxs-lookup"><span data-stu-id="a1a7e-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="a1a7e-229">Nom d'utilisateur/Mot de passe</span><span class="sxs-lookup"><span data-stu-id="a1a7e-229">Username/Password</span></span>  <br/> |<span data-ttu-id="a1a7e-230">Oui</span><span class="sxs-lookup"><span data-stu-id="a1a7e-230">Yes</span></span>  <br/> |<span data-ttu-id="a1a7e-231">Oui</span><span class="sxs-lookup"><span data-stu-id="a1a7e-231">Yes</span></span>  <br/> |<span data-ttu-id="a1a7e-232">N/D</span><span class="sxs-lookup"><span data-stu-id="a1a7e-232">N/A</span></span>  <br/> |
|<span data-ttu-id="a1a7e-233">Sur site</span><span class="sxs-lookup"><span data-stu-id="a1a7e-233">On-premises</span></span>  <br/> |<span data-ttu-id="a1a7e-234">En ligne/sur site</span><span class="sxs-lookup"><span data-stu-id="a1a7e-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="a1a7e-235">Connexion via PC (BTOE)</span><span class="sxs-lookup"><span data-stu-id="a1a7e-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="a1a7e-236">Oui</span><span class="sxs-lookup"><span data-stu-id="a1a7e-236">Yes</span></span>  <br/> |<span data-ttu-id="a1a7e-237">Oui</span><span class="sxs-lookup"><span data-stu-id="a1a7e-237">Yes</span></span>  <br/> |<span data-ttu-id="a1a7e-238">N/D</span><span class="sxs-lookup"><span data-stu-id="a1a7e-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="a1a7e-239">**Phone features** The feature set may vary slightly based on the IP phone partner.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-239">**Phone features** The feature set may vary slightly based on the IP phone partner.</span></span> <span data-ttu-id="a1a7e-240">For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="a1a7e-240">For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="a1a7e-241">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-241">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone.</span></span> <span data-ttu-id="a1a7e-242">If enabled, users will be asked to create a PIN upon successful authentication.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-242">If enabled, users will be asked to create a PIN upon successful authentication.</span></span> <span data-ttu-id="a1a7e-243">Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-243">Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing.</span></span> <span data-ttu-id="a1a7e-244">If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-244">If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner.</span></span> <span data-ttu-id="a1a7e-245">The user's PIN should be between 6 and 15 digits.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-245">The user's PIN should be between 6 and 15 digits.</span></span>
    
    <span data-ttu-id="a1a7e-246">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-246">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings.</span></span> <span data-ttu-id="a1a7e-247">Pour plus d’informations sur ces paramètres [, voir Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="a1a7e-247">See [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="a1a7e-248">Étape 7 : si vous disposez du couplage d'appareil et de Better Together over Ethernet (BToE) (facultatif)</span><span class="sxs-lookup"><span data-stu-id="a1a7e-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="a1a7e-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="a1a7e-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="a1a7e-250">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-250">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app.</span></span> <span data-ttu-id="a1a7e-251">BToE enables users to:</span><span class="sxs-lookup"><span data-stu-id="a1a7e-251">BToE enables users to:</span></span>
  
- <span data-ttu-id="a1a7e-252">Se connecter à leur téléphone IP à l’aide de leur application de bureau Skype entreprise (à l’aide d’un PC)</span><span class="sxs-lookup"><span data-stu-id="a1a7e-252">Sign in to their IP phone using their Skype for Business desktop app (using a PC)</span></span>
    
- <span data-ttu-id="a1a7e-253">Synchroniser le verrouillage du téléphone avec le verrouillage de l’ordinateur</span><span class="sxs-lookup"><span data-stu-id="a1a7e-253">Synchronize Phone-Lock with PC lock</span></span>
    
- <span data-ttu-id="a1a7e-254">Cliquer et appeler</span><span class="sxs-lookup"><span data-stu-id="a1a7e-254">Click to call</span></span>
    
<span data-ttu-id="a1a7e-255">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  .</span><span class="sxs-lookup"><span data-stu-id="a1a7e-255">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  .</span></span> <span data-ttu-id="a1a7e-256">It can also be enabled (default)/disabled for users using Skype for Business in-band settings.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-256">It can also be enabled (default)/disabled for users using Skype for Business in-band settings.</span></span> <span data-ttu-id="a1a7e-257">When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-257">When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="a1a7e-258">**Pour déployer BToE pour les utilisateurs**</span><span class="sxs-lookup"><span data-stu-id="a1a7e-258">**To deploy BToE to users**</span></span>
  
1. <span data-ttu-id="a1a7e-259">Connectez leur PC à leur téléphone à l'aide du port du PC.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![Capture d’écran montrant la connexion à un PC](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="a1a7e-p121">Téléchargez et installez la dernière version du logiciel BToE à partir du site Web du fabricant à partir des liens ci-dessous. Pour une meilleure expérience utilisateur, vous pouvez distribuer et installer le logiciel BToE à l’aide d’une solution de distribution d’administration telle que Microsoft Endpoint Configuration Manager. Pour obtenir de l’aide sur la Configuration Manager, voir [packages et programmes dans Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="a1a7e-p121">Download and install the latest BToE software from the manufacturer website from the links below. For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as Microsoft Endpoint Configuration Manager. For help using Configuration Manager, See [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>
    
   - [<span data-ttu-id="a1a7e-264">Site de téléchargement du logiciel BToE Polycom</span><span class="sxs-lookup"><span data-stu-id="a1a7e-264">Polycom BToE Software Download site</span></span>](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [<span data-ttu-id="a1a7e-265">Téléchargement du logiciel BToE pour Yealink</span><span class="sxs-lookup"><span data-stu-id="a1a7e-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
   - [<span data-ttu-id="a1a7e-266">Téléchargement du logiciel BToE pour AudioCodes</span><span class="sxs-lookup"><span data-stu-id="a1a7e-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="a1a7e-p122">The server setting for BToE is set to **Enabled** and **Auto mode** by default. To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx).</span><span class="sxs-lookup"><span data-stu-id="a1a7e-p122">The server setting for BToE is set to **Enabled** and **Auto mode** by default. To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx).</span></span>
    
> [!NOTE]
> <span data-ttu-id="a1a7e-269">BToE n'est actuellement pas disponible sur les plates-formes Mac et VDI.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="a1a7e-270">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="a1a7e-270">Related topics</span></span>
[<span data-ttu-id="a1a7e-271">Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a1a7e-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="a1a7e-272">Voici les avantages du système téléphonique dans Office 365</span><span class="sxs-lookup"><span data-stu-id="a1a7e-272">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="a1a7e-273">Disponibilité des offres d'appels et d'audioconférence selon les régions et les pays</span><span class="sxs-lookup"><span data-stu-id="a1a7e-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 

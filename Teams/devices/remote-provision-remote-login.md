---
title: Mise en service à distance et se connectez pour les appareils Android Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: prgholve
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser la mise en service à distance et la connectez-vous pour les appareils Android Teams
ms.openlocfilehash: 43a025c0cc68fb7f10015d69298f8dd75f9003e8
ms.sourcegitcommit: 95386369e2256ba382b4d6e34adb7473de050b26
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/29/2021
ms.locfileid: "51410336"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a><span data-ttu-id="cca88-103">Mise en service à distance et se connectez pour les appareils Android Teams</span><span class="sxs-lookup"><span data-stu-id="cca88-103">Remote provisioning and sign in for Teams Android devices</span></span>

<span data-ttu-id="cca88-104">Les administrateurs informatiques peuvent mettre en service et se connectent à distance sur un appareil Teams Android.</span><span class="sxs-lookup"><span data-stu-id="cca88-104">IT admins can remotely provision and sign in to a Teams Android device.</span></span> <span data-ttu-id="cca88-105">Pour mettre en service un appareil à distance, l’administrateur doit télécharger les ID MAC des appareils en cours de mise en service et créer un code de vérification.</span><span class="sxs-lookup"><span data-stu-id="cca88-105">To provision a device remotely, the admin needs to upload the MAC IDs of the devices being provisioned and create a verification code.</span></span> <span data-ttu-id="cca88-106">L’ensemble du processus peut être accompli à distance à partir du Centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="cca88-106">The entire process can be completed remotely from the Teams admin center.</span></span>

## <a name="review-the-supported-devices"></a><span data-ttu-id="cca88-107">Passer en revue les appareils pris en charge</span><span class="sxs-lookup"><span data-stu-id="cca88-107">Review the supported devices</span></span>

<span data-ttu-id="cca88-108">La liste suivante présente les conditions requises pour le microprogramme de l’appareil Android.</span><span class="sxs-lookup"><span data-stu-id="cca88-108">The following list shows the Android device firmware requirements.</span></span>

|<span data-ttu-id="cca88-109">Catégorie d’appareil</span><span class="sxs-lookup"><span data-stu-id="cca88-109">Device category</span></span>|<span data-ttu-id="cca88-110">Modèle d’appareil</span><span class="sxs-lookup"><span data-stu-id="cca88-110">Device model</span></span>|<span data-ttu-id="cca88-111">Version du microprogramme</span><span class="sxs-lookup"><span data-stu-id="cca88-111">Firmware version</span></span>|
|-|-|-|
|<span data-ttu-id="cca88-112">Téléphones Teams</span><span class="sxs-lookup"><span data-stu-id="cca88-112">Teams phones</span></span>|<span data-ttu-id="cca88-113">Yealink T55/T56/T58</span><span class="sxs-lookup"><span data-stu-id="cca88-113">Yealink T55/T56/T58</span></span>|<span data-ttu-id="cca88-114">58.15.0.124</span><span class="sxs-lookup"><span data-stu-id="cca88-114">58.15.0.124</span></span>|
|<span data-ttu-id="cca88-115">Téléphones Teams</span><span class="sxs-lookup"><span data-stu-id="cca88-115">Teams phones</span></span>|<span data-ttu-id="cca88-116">Yealink VP59</span><span class="sxs-lookup"><span data-stu-id="cca88-116">Yealink VP59</span></span>|<span data-ttu-id="cca88-117">91.15.0.58</span><span class="sxs-lookup"><span data-stu-id="cca88-117">91.15.0.58</span></span>|
|<span data-ttu-id="cca88-118">Téléphones Teams</span><span class="sxs-lookup"><span data-stu-id="cca88-118">Teams phones</span></span>|<span data-ttu-id="cca88-119">Yealink CP960</span><span class="sxs-lookup"><span data-stu-id="cca88-119">Yealink CP960</span></span>|<span data-ttu-id="cca88-120">73.15.0.117</span><span class="sxs-lookup"><span data-stu-id="cca88-120">73.15.0.117</span></span>|
|<span data-ttu-id="cca88-121">Téléphones Teams</span><span class="sxs-lookup"><span data-stu-id="cca88-121">Teams phones</span></span>|<span data-ttu-id="cca88-122">Yealink MP56/MP54/MP58</span><span class="sxs-lookup"><span data-stu-id="cca88-122">Yealink MP56/MP54/MP58</span></span>|<span data-ttu-id="cca88-123">122.15.0.36</span><span class="sxs-lookup"><span data-stu-id="cca88-123">122.15.0.36</span></span>|
|<span data-ttu-id="cca88-124">Téléphones Teams</span><span class="sxs-lookup"><span data-stu-id="cca88-124">Teams phones</span></span>|<span data-ttu-id="cca88-125">Crestron UC-2</span><span class="sxs-lookup"><span data-stu-id="cca88-125">Crestron UC-2</span></span>|<span data-ttu-id="cca88-126">1.0.3.52</span><span class="sxs-lookup"><span data-stu-id="cca88-126">1.0.3.52</span></span>|

## <a name="add-a-device-mac-address"></a><span data-ttu-id="cca88-127">Ajouter une adresse MAC d’appareil</span><span class="sxs-lookup"><span data-stu-id="cca88-127">Add a device MAC address</span></span>

<span data-ttu-id="cca88-128">Pour mettre en service un nouvel appareil, vous suivrez les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="cca88-128">Complete the following steps to provision a new device.</span></span>

1. <span data-ttu-id="cca88-129">Se connecter au Centre d’administration de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cca88-129">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="cca88-130">Développez **Périphériques.**</span><span class="sxs-lookup"><span data-stu-id="cca88-130">Expand **Devices**.</span></span>
3. <span data-ttu-id="cca88-131">Sélectionnez **Provision new device from** the **Actions** tab.</span><span class="sxs-lookup"><span data-stu-id="cca88-131">Select **Provision new device** from the **Actions** tab.</span></span>

<span data-ttu-id="cca88-132">Dans la **fenêtre Provision de nouveaux appareils,** vous pouvez ajouter l’adresse mac manuellement ou charger un fichier.</span><span class="sxs-lookup"><span data-stu-id="cca88-132">In the **Provision new devices** window, you can either add the MAC address manually or upload a file.</span></span>

### <a name="manually-add-a-device-mac-address"></a><span data-ttu-id="cca88-133">Ajouter manuellement une adresse MAC de périphérique</span><span class="sxs-lookup"><span data-stu-id="cca88-133">Manually add a device MAC address</span></span>

1. <span data-ttu-id="cca88-134">Dans **l’onglet Activation en** attente, **sélectionnez Ajouter un ID MAC.**</span><span class="sxs-lookup"><span data-stu-id="cca88-134">From the **Awaiting Activation** tab, select **Add MAC ID**.</span></span>

   ![ajouter manuellement une adresse Mac de périphérique](../media/remote-provision-6.png)

1. <span data-ttu-id="cca88-136">Entrez l’ID MAC.</span><span class="sxs-lookup"><span data-stu-id="cca88-136">Enter the MAC ID.</span></span>
1. <span data-ttu-id="cca88-137">Entrez un emplacement pour aider les techniciens à identifier l’emplacement d’installation des appareils.</span><span class="sxs-lookup"><span data-stu-id="cca88-137">Enter a location, which helps technicians identify where to install the devices.</span></span>
1. <span data-ttu-id="cca88-138">Sélectionnez **Appliquer** lorsque vous avez terminé.</span><span class="sxs-lookup"><span data-stu-id="cca88-138">Select **Apply** when finished.</span></span>

### <a name="upload-a-file-to-add-a-device-mac-address"></a><span data-ttu-id="cca88-139">Télécharger un fichier pour ajouter une adresse MAC d’appareil</span><span class="sxs-lookup"><span data-stu-id="cca88-139">Upload a file to add a device MAC address</span></span>

1. <span data-ttu-id="cca88-140">Dans **l’onglet Activation en** attente, **sélectionnez Télécharger les ID MAC.**</span><span class="sxs-lookup"><span data-stu-id="cca88-140">From the **Awaiting Activation** tab, select **Upload MAC IDs**.</span></span>
2. <span data-ttu-id="cca88-141">Téléchargez le modèle de fichier.</span><span class="sxs-lookup"><span data-stu-id="cca88-141">Download the file template.</span></span>
3. <span data-ttu-id="cca88-142">Entrez l’ID MAC et l’emplacement, puis enregistrez le fichier.</span><span class="sxs-lookup"><span data-stu-id="cca88-142">Enter the MAC ID and location, and then save the file.</span></span>
4. <span data-ttu-id="cca88-143">**Sélectionnez le** fichier, puis **Charger.**</span><span class="sxs-lookup"><span data-stu-id="cca88-143">**Select file**, and then select **Upload**.</span></span>

## <a name="generate-a-verification-code"></a><span data-ttu-id="cca88-144">Générer un code de vérification</span><span class="sxs-lookup"><span data-stu-id="cca88-144">Generate a verification code</span></span>

<span data-ttu-id="cca88-145">Vous avez besoin d’un code de vérification pour les appareils.</span><span class="sxs-lookup"><span data-stu-id="cca88-145">You need a verification code for the devices.</span></span> <span data-ttu-id="cca88-146">Le code de vérification est généré en bloc ou au niveau de l’appareil et est valable pendant 24 heures.</span><span class="sxs-lookup"><span data-stu-id="cca88-146">The verification code is generated in bulk or at the device level and is valid for 24 hours.</span></span>

1. <span data-ttu-id="cca88-147">Dans **l’onglet Activation** en attente, sélectionnez un ID MAC existant.</span><span class="sxs-lookup"><span data-stu-id="cca88-147">From the **Awaiting Activation** tab, select an existing MAC ID.</span></span>
   <span data-ttu-id="cca88-148">Un mot de passe est créé pour l’adresse MAC et s’affiche dans la colonne **Code de** vérification.</span><span class="sxs-lookup"><span data-stu-id="cca88-148">A password is created for the MAC address and is shown in the **Verification Code** column.</span></span>

2. <span data-ttu-id="cca88-149">Fournissez la liste des ID MAC et des codes de vérification aux techniciens de champ.</span><span class="sxs-lookup"><span data-stu-id="cca88-149">Provide the list of MAC IDs and verification codes to the field technicians.</span></span> <span data-ttu-id="cca88-150">Vous pouvez exporter les détails directement dans un fichier et le partager avec le technicien qui travaille sur l’installation réelle.</span><span class="sxs-lookup"><span data-stu-id="cca88-150">You can export the detail directly in a file and share the file with the technician who is doing the actual installation work.</span></span>

## <a name="provision-the-device"></a><span data-ttu-id="cca88-151">Approvisionnement de l’appareil</span><span class="sxs-lookup"><span data-stu-id="cca88-151">Provision the device</span></span>

<span data-ttu-id="cca88-152">Lorsque l’appareil est sous tension et connecté au réseau, le technicien le connecte.</span><span class="sxs-lookup"><span data-stu-id="cca88-152">When the device is powered on and connected to the network, the technician provisions the device.</span></span> <span data-ttu-id="cca88-153">Ces étapes sont effectuées sur l’appareil Teams.</span><span class="sxs-lookup"><span data-stu-id="cca88-153">These steps are completed on the Teams device.</span></span>

1. <span data-ttu-id="cca88-154">Le technicien sélectionne Périphérique **d’approvisionnement** dans **les paramètres.**</span><span class="sxs-lookup"><span data-stu-id="cca88-154">The technician selects **Provision device** from the **Settings**.</span></span>  

   ![Option Nouvel appareil disponible à partir de l’onglet Actions](../media/provision-device1.png)
  
2. <span data-ttu-id="cca88-156">Le technicien entre le code de vérification spécifique de l’appareil dans le champ de saisie fourni.</span><span class="sxs-lookup"><span data-stu-id="cca88-156">The technician enters the device-specific verification code in the provided input field.</span></span>

   ![Vérification de l’approvisionnement d’un nouvel appareil](../media/provision-device-verification1.png)

   <span data-ttu-id="cca88-158">Une fois l’appareil correctement mis en service, le nom du client s’affiche sur la page de inscription.</span><span class="sxs-lookup"><span data-stu-id="cca88-158">Once the device is provisioned successfully, the tenant name appears on the sign-in page.</span></span>

   ![Nom du client sur la page de inscription](../media/provision-code.png)

## <a name="sign-in-remotely"></a><span data-ttu-id="cca88-160">Se connectez à distance</span><span class="sxs-lookup"><span data-stu-id="cca88-160">Sign in remotely</span></span>

<span data-ttu-id="cca88-161">Le périphérique en attente apparaît dans **l’onglet De confirmation de** la mise en service. Démarrez le processus de inscription à distance en sélectionnant le périphérique individuel.</span><span class="sxs-lookup"><span data-stu-id="cca88-161">The provisioned device appears in the **Awaiting sign in** tab. Start the remote sign-in process by selecting the individual device.</span></span>

1. <span data-ttu-id="cca88-162">Sélectionnez un appareil dans **l’onglet Se connectez en** attente.</span><span class="sxs-lookup"><span data-stu-id="cca88-162">Select a device from the **Awaiting sign in** tab.</span></span>

   ![Fenêtre avec une liste d’appareils prêts à être connectés.](../media/remote-device1.png)

2. <span data-ttu-id="cca88-164">Suivez les instructions dans **Se connectez à un utilisateur,** puis sélectionnez **Fermer.**</span><span class="sxs-lookup"><span data-stu-id="cca88-164">Follow the instructions in **Sign in a user**, and then select **Close**.</span></span>

   ![Fenêtre Se connectez à un utilisateur pour un appareil individuel](../media/sign-in-user.png)

## <a name="related-article"></a><span data-ttu-id="cca88-166">Article connexe</span><span class="sxs-lookup"><span data-stu-id="cca88-166">Related article</span></span>

- [<span data-ttu-id="cca88-167">Gérer vos périphériques dans Teams</span><span class="sxs-lookup"><span data-stu-id="cca88-167">Manage your devices in Teams</span></span>](device-management.md)
- [<span data-ttu-id="cca88-168">Mettre à jour les appareils Teams à distance</span><span class="sxs-lookup"><span data-stu-id="cca88-168">Update Teams devices remotely</span></span>](remote-update.md)

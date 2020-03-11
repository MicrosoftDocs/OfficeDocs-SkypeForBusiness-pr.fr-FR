---
title: Gérer vos périphériques dans Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: Découvrez comment gérer les appareils utilisés avec les équipes de votre organisation.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef6412ff40d71a21f619b08ee5e334819d5470ca
ms.sourcegitcommit: a597b1572f1eca095144288446a2c038e5daa5f7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/10/2020
ms.locfileid: "42587276"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="a2d59-103">Gérer vos périphériques dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a2d59-103">Manage your devices in Microsoft Teams</span></span>

<span data-ttu-id="a2d59-104">En tant qu’administrateur, vous pouvez gérer les appareils utilisés avec les équipes de votre organisation à partir du centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a2d59-104">As an admin, you can manage devices used with Teams in your organization from the Microsoft Teams admin center.</span></span> <span data-ttu-id="a2d59-105">Vous pouvez afficher et gérer l’inventaire des appareils pour votre organisation, et effectuer des tâches telles que la mise à jour, le redémarrage et l’analyse des diagnostics pour les appareils.</span><span class="sxs-lookup"><span data-stu-id="a2d59-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="a2d59-106">Vous pouvez également créer des profils de configuration et les affecter à un appareil ou à un groupe d’appareils.</span><span class="sxs-lookup"><span data-stu-id="a2d59-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="a2d59-107">Quels appareils pouvez-vous gérer ?</span><span class="sxs-lookup"><span data-stu-id="a2d59-107">What devices can you manage?</span></span>
<span data-ttu-id="a2d59-108">Vous pouvez gérer tous les appareils qui sont certifiés pour et inscrits dans Teams.</span><span class="sxs-lookup"><span data-stu-id="a2d59-108">You can manage any device that's certified for, and enrolled in, Teams.</span></span> <span data-ttu-id="a2d59-109">Un appareil est automatiquement inscrit la première fois qu’un utilisateur se connecte à teams sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="a2d59-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="a2d59-110">Pour obtenir la liste des appareils certifiés qui peuvent être gérés, voir :</span><span class="sxs-lookup"><span data-stu-id="a2d59-110">For a list of certified devices that can be managed, see:</span></span>

- [<span data-ttu-id="a2d59-111">Conférences téléphoniques</span><span class="sxs-lookup"><span data-stu-id="a2d59-111">Conference phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16)
- [<span data-ttu-id="a2d59-112">Téléphones de bureau</span><span class="sxs-lookup"><span data-stu-id="a2d59-112">Desk phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- <span data-ttu-id="a2d59-113">Barres de collaboration</span><span class="sxs-lookup"><span data-stu-id="a2d59-113">Collaboration bars</span></span>

<span data-ttu-id="a2d59-114">Les appareils sont gérés dans le [Centre d’administration Microsoft teams](https://admin.teams.microsoft.com) sous **appareils** dans le volet de navigation de gauche.</span><span class="sxs-lookup"><span data-stu-id="a2d59-114">Devices are managed in the [Microsoft Teams admin center](https://admin.teams.microsoft.com) under **Devices** in the left navigation.</span></span>

> [!NOTE]
> <span data-ttu-id="a2d59-115">Si vous avez Microsoft Intune, les appareils sont automatiquement inscrits dans Intune.</span><span class="sxs-lookup"><span data-stu-id="a2d59-115">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="a2d59-116">Après l’inscription d’un appareil, la conformité de l’appareil est confirmée et les stratégies d’accès conditionnel sont appliquées à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="a2d59-116">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span>

## <a name="manage-phones-and-collaboration-bars-in-teams"></a><span data-ttu-id="a2d59-117">Gérer les téléphones et les barres de collaboration dans teams</span><span class="sxs-lookup"><span data-stu-id="a2d59-117">Manage phones and collaboration bars in Teams</span></span>

<span data-ttu-id="a2d59-118">Même si le centre d’administration Microsoft teams est géré en tant que téléphones et barres de collaboration, ils disposent de leurs propres sections dans le volet de navigation de gauche, sous **périphériques**.</span><span class="sxs-lookup"><span data-stu-id="a2d59-118">Even though phones and collaboration bars are managed the same in the Microsoft Teams admin center, they have their own respective sections in the left navigation under **Devices**.</span></span> <span data-ttu-id="a2d59-119">Cela vous permet de gérer chaque type d’appareil séparément.</span><span class="sxs-lookup"><span data-stu-id="a2d59-119">This lets you manage each type of device separately.</span></span>

<span data-ttu-id="a2d59-120">À partir de cet emplacement, vous pouvez afficher et gérer les téléphones et les barres de collaboration inscrits dans teams au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a2d59-120">From here, you can view and manage phones and collaboration bars enrolled in Teams in your organization.</span></span> <span data-ttu-id="a2d59-121">Les informations qui s’affichent pour chaque appareil incluent le nom de l’appareil, le fabricant, le modèle, l’utilisateur, le statut, l’action, le dernier affichage et l’historique.</span><span class="sxs-lookup"><span data-stu-id="a2d59-121">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="a2d59-122">Vous pouvez personnaliser l’affichage pour afficher les informations qui correspondent à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="a2d59-122">You can customize the view to show the information that fits your needs.</span></span>

<span data-ttu-id="a2d59-123">Voici quelques exemples de la manière dont vous pouvez gérer les appareils teams au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a2d59-123">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="a2d59-124">Pour cela, procédez comme suit...</span><span class="sxs-lookup"><span data-stu-id="a2d59-124">To do this...</span></span>  |<span data-ttu-id="a2d59-125">Procédez comme suit</span><span class="sxs-lookup"><span data-stu-id="a2d59-125">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="a2d59-126">Modification des informations de périphérique</span><span class="sxs-lookup"><span data-stu-id="a2d59-126">Change device information</span></span>   | <span data-ttu-id="a2d59-127">Sélectionnez un appareil > **modifier**.</span><span class="sxs-lookup"><span data-stu-id="a2d59-127">Select a device > **Edit**.</span></span> <span data-ttu-id="a2d59-128">Vous pouvez modifier les détails tels que le nom de l’appareil, l’étiquette de la ressource et ajouter des notes.</span><span class="sxs-lookup"><span data-stu-id="a2d59-128">You can edit details such as device name, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="a2d59-129">Gérer les mises à jour logicielles</span><span class="sxs-lookup"><span data-stu-id="a2d59-129">Manage software updates</span></span>   |<span data-ttu-id="a2d59-130">Sélectionnez un appareil > **mettre à jour**.</span><span class="sxs-lookup"><span data-stu-id="a2d59-130">Select a device > **Update**.</span></span> <span data-ttu-id="a2d59-131">Vous pouvez afficher la liste des mises à jour de logiciels et de microprogrammes disponibles pour l’appareil, puis sélectionner les mises à jour pour procéder à l’installation.</span><span class="sxs-lookup"><span data-stu-id="a2d59-131">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="a2d59-132">Redémarrer un appareil</span><span class="sxs-lookup"><span data-stu-id="a2d59-132">Restart a device</span></span>   |<span data-ttu-id="a2d59-133">Sélectionnez un appareil > **redémarrer**.</span><span class="sxs-lookup"><span data-stu-id="a2d59-133">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="a2d59-134">Afficher l’historique de l’appareil</span><span class="sxs-lookup"><span data-stu-id="a2d59-134">View device history</span></span>  | <span data-ttu-id="a2d59-135">Sélectionnez un appareil > **historique**.</span><span class="sxs-lookup"><span data-stu-id="a2d59-135">Select a device > **History**.</span></span> <span data-ttu-id="a2d59-136">Vous pouvez afficher l’historique des mises à jour de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="a2d59-136">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="a2d59-137">Afficher les Diagnostics</span><span class="sxs-lookup"><span data-stu-id="a2d59-137">View diagnostics</span></span>  | <span data-ttu-id="a2d59-138">Sélectionnez un appareil > **Diagnostics**.</span><span class="sxs-lookup"><span data-stu-id="a2d59-138">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="a2d59-139">Utiliser des profils de configuration dans teams</span><span class="sxs-lookup"><span data-stu-id="a2d59-139">Use configuration profiles in Teams</span></span>

<span data-ttu-id="a2d59-140">Utilisez les profils de configuration pour gérer les paramètres et les fonctionnalités des appareils teams de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a2d59-140">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="a2d59-141">Vous pouvez créer ou charger des profils de configuration pour inclure des paramètres et des fonctionnalités que vous souhaitez activer ou désactiver, puis attribuer un profil à un appareil ou à un groupe d’appareils.</span><span class="sxs-lookup"><span data-stu-id="a2d59-141">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="a2d59-142">Créer un profil de configuration</span><span class="sxs-lookup"><span data-stu-id="a2d59-142">Create a configuration profile</span></span>

1. <span data-ttu-id="a2d59-143">Dans le volet de navigation de gauche, accédez à**profils de configuration**de **périphériques** > .</span><span class="sxs-lookup"><span data-stu-id="a2d59-143">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="a2d59-144">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="a2d59-144">Click **Add**.</span></span>
3. <span data-ttu-id="a2d59-145">Entrez un nom pour le profil et, si vous le souhaitez, ajoutez une description conviviale.</span><span class="sxs-lookup"><span data-stu-id="a2d59-145">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="a2d59-146">Spécifiez les paramètres que vous voulez utiliser pour le profil, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a2d59-146">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="a2d59-147">Attribuer un profil de configuration</span><span class="sxs-lookup"><span data-stu-id="a2d59-147">Assign a configuration profile</span></span>

1. <span data-ttu-id="a2d59-148">Dans le volet de navigation de gauche, accédez à**profils de configuration**de **périphériques** > .</span><span class="sxs-lookup"><span data-stu-id="a2d59-148">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="a2d59-149">Sélectionnez le **profil de configuration** que vous voulez attribuer, puis cliquez sur **affecter au périphérique**.</span><span class="sxs-lookup"><span data-stu-id="a2d59-149">Select the **Configuration profile** you want to assign, and then click **Assign to device**.</span></span>  
3. <span data-ttu-id="a2d59-150">Dans le volet **affecter des appareils à un profil de configuration** , recherchez et sélectionnez les périphériques que vous voulez affecter.</span><span class="sxs-lookup"><span data-stu-id="a2d59-150">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="a2d59-151">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a2d59-151">Click **Save**.</span></span>

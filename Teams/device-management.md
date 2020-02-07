---
title: Gérer vos périphériques dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/12/2018
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
ms.openlocfilehash: 2557410adf0eda18fab0e5450f739baf2ec7d581
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824866"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="53d05-103">Gérer vos périphériques dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="53d05-103">Manage your devices in Microsoft Teams</span></span>

::: zone target="docs"
<span data-ttu-id="53d05-104">En tant qu’administrateur, vous gérez tous les appareils utilisés avec les équipes de votre organisation à partir du centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="53d05-104">As an admin, you manage all devices used with Teams in your organization from the Microsoft Teams admin center.</span></span> <span data-ttu-id="53d05-105">Vous pouvez afficher et gérer l’inventaire des appareils pour votre organisation, et effectuer des tâches telles que la mise à jour, le redémarrage et l’analyse des diagnostics pour les appareils.</span><span class="sxs-lookup"><span data-stu-id="53d05-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="53d05-106">Vous pouvez également créer des profils de configuration et les affecter à un appareil ou à un groupe d’appareils.</span><span class="sxs-lookup"><span data-stu-id="53d05-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="53d05-107">Quels appareils pouvez-vous gérer ?</span><span class="sxs-lookup"><span data-stu-id="53d05-107">What devices can you manage?</span></span>
<span data-ttu-id="53d05-108">Les appareils doivent être certifiés pour les équipes et inscrits dans Teams.</span><span class="sxs-lookup"><span data-stu-id="53d05-108">Devices must be certified for Teams and enrolled in Teams.</span></span> <span data-ttu-id="53d05-109">Un appareil est automatiquement inscrit la première fois qu’un utilisateur se connecte à teams sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="53d05-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="53d05-110">Pour obtenir la liste des appareils certifiés gérables, reportez-vous à la section [conférences](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16) téléphoniques et [téléphones de bureau](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34).</span><span class="sxs-lookup"><span data-stu-id="53d05-110">For a list of certified devices that can be managed, see [Conference phones](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16) and [Desk phones](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34).</span></span>

> [!NOTE]
> <span data-ttu-id="53d05-111">Si vous avez Microsoft Intune, les appareils sont automatiquement inscrits dans Intune.</span><span class="sxs-lookup"><span data-stu-id="53d05-111">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="53d05-112">Après l’inscription d’un appareil, la conformité de l’appareil est confirmée et les stratégies d’accès conditionnel sont appliquées à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="53d05-112">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span> 

## <a name="manage-devices-in-teams"></a><span data-ttu-id="53d05-113">Gérer les appareils dans teams</span><span class="sxs-lookup"><span data-stu-id="53d05-113">Manage devices in Teams</span></span>

<span data-ttu-id="53d05-114">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="53d05-114">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="53d05-115">Dans le volet de navigation de gauche, accédez à **périphériques** > **gérer les appareils**.</span><span class="sxs-lookup"><span data-stu-id="53d05-115">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="53d05-116">Sélectionnez **tous les appareils**.</span><span class="sxs-lookup"><span data-stu-id="53d05-116">Select **All devices**.</span></span>  

::: zone-end

 <span data-ttu-id="53d05-117">À partir de cet emplacement, vous pouvez afficher et gérer tous les périphériques inscrits dans teams au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="53d05-117">From here, you can view and manage all devices enrolled in Teams in your organization.</span></span> <span data-ttu-id="53d05-118">Les informations qui s’affichent pour chaque appareil incluent le nom de l’appareil, le fabricant, le modèle, l’utilisateur, le statut, l’action, le dernier affichage et l’historique.</span><span class="sxs-lookup"><span data-stu-id="53d05-118">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="53d05-119">Vous pouvez personnaliser l’affichage pour afficher les informations qui correspondent à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="53d05-119">You can customize the view to show the information that fits your needs.</span></span>

 <span data-ttu-id="53d05-120">Voici quelques exemples de la manière dont vous pouvez gérer les appareils teams au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="53d05-120">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="53d05-121">Pour cela, procédez comme suit...</span><span class="sxs-lookup"><span data-stu-id="53d05-121">To do this...</span></span>  |<span data-ttu-id="53d05-122">Procédez comme suit</span><span class="sxs-lookup"><span data-stu-id="53d05-122">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="53d05-123">Modification des informations de périphérique</span><span class="sxs-lookup"><span data-stu-id="53d05-123">Change device information</span></span>   | <span data-ttu-id="53d05-124">Sélectionnez un appareil > **modifier**.</span><span class="sxs-lookup"><span data-stu-id="53d05-124">Select a device > **Edit**.</span></span> <span data-ttu-id="53d05-125">Vous pouvez modifier des détails tels que le nom de l’appareil, les informations utilisateur, la balise de ressources et ajouter des notes.</span><span class="sxs-lookup"><span data-stu-id="53d05-125">You can edit details such as device name, user information, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="53d05-126">Gérer les mises à jour logicielles</span><span class="sxs-lookup"><span data-stu-id="53d05-126">Manage software updates</span></span>   |<span data-ttu-id="53d05-127">Sélectionnez un appareil > **mettre à jour**.</span><span class="sxs-lookup"><span data-stu-id="53d05-127">Select a device > **Update**.</span></span> <span data-ttu-id="53d05-128">Vous pouvez afficher la liste des mises à jour de logiciels et de microprogrammes disponibles pour l’appareil, puis sélectionner les mises à jour pour procéder à l’installation.</span><span class="sxs-lookup"><span data-stu-id="53d05-128">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="53d05-129">Redémarrer un appareil</span><span class="sxs-lookup"><span data-stu-id="53d05-129">Restart a device</span></span>   |<span data-ttu-id="53d05-130">Sélectionnez un appareil > **redémarrer**.</span><span class="sxs-lookup"><span data-stu-id="53d05-130">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="53d05-131">Afficher l’historique de l’appareil</span><span class="sxs-lookup"><span data-stu-id="53d05-131">View device history</span></span>  | <span data-ttu-id="53d05-132">Sélectionnez un appareil > **historique**.</span><span class="sxs-lookup"><span data-stu-id="53d05-132">Select a device > **History**.</span></span> <span data-ttu-id="53d05-133">Vous pouvez afficher l’historique des mises à jour de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="53d05-133">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="53d05-134">Afficher les Diagnostics</span><span class="sxs-lookup"><span data-stu-id="53d05-134">View diagnostics</span></span>  | <span data-ttu-id="53d05-135">Sélectionnez un appareil > **Diagnostics**.</span><span class="sxs-lookup"><span data-stu-id="53d05-135">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="53d05-136">Utiliser des profils de configuration dans teams</span><span class="sxs-lookup"><span data-stu-id="53d05-136">Use configuration profiles in Teams</span></span>

<span data-ttu-id="53d05-137">Utilisez les profils de configuration pour gérer les paramètres et les fonctionnalités des appareils teams de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="53d05-137">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="53d05-138">Vous pouvez créer ou charger des profils de configuration pour inclure des paramètres et des fonctionnalités que vous souhaitez activer ou désactiver, puis attribuer un profil à un appareil ou à un groupe d’appareils.</span><span class="sxs-lookup"><span data-stu-id="53d05-138">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="53d05-139">Créer un profil de configuration</span><span class="sxs-lookup"><span data-stu-id="53d05-139">Create a configuration profile</span></span>

::: zone target="docs"

![Icône affichant le logo Microsoft teams](media/teams-logo-30x30.png) <span data-ttu-id="53d05-141">Utilisation de Microsoft teams & le centre d’administration Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="53d05-141">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="53d05-142">Dans le volet de navigation de gauche, accédez à **périphériques** > **gérer les appareils**.</span><span class="sxs-lookup"><span data-stu-id="53d05-142">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>

::: zone-end

2. <span data-ttu-id="53d05-143">Sélectionnez **profils de configuration**, puis sélectionnez **nouveau profil de configuration**.</span><span class="sxs-lookup"><span data-stu-id="53d05-143">Select **Configuration profiles**, and then select **New configuration profile**.</span></span>
3. <span data-ttu-id="53d05-144">Entrez un nom pour le profil et, si vous le souhaitez, ajoutez une description conviviale.</span><span class="sxs-lookup"><span data-stu-id="53d05-144">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="53d05-145">Spécifiez les paramètres que vous voulez utiliser pour le profil, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="53d05-145">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="53d05-146">Attribuer un profil de configuration</span><span class="sxs-lookup"><span data-stu-id="53d05-146">Assign a configuration profile</span></span>

::: zone target="docs"

![Icône affichant le logo Microsoft teams](media/teams-logo-30x30.png) <span data-ttu-id="53d05-148">Utilisation de Microsoft teams & le centre d’administration Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="53d05-148">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="53d05-149">Dans le volet de navigation de gauche, accédez à **périphériques** > **gérer les appareils**.</span><span class="sxs-lookup"><span data-stu-id="53d05-149">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>

::: zone-end

2. <span data-ttu-id="53d05-150">Sélectionnez **profil de configuration**, puis sous **attribué à** dans le profil que vous voulez attribuer, cliquez sur le lien.</span><span class="sxs-lookup"><span data-stu-id="53d05-150">Select **Configuration profile**, and then under **Assigned to** in the profile you want to assign, click the link.</span></span>  
3. <span data-ttu-id="53d05-151">Dans le volet **affecter des appareils à un profil de configuration** , recherchez et sélectionnez les périphériques que vous voulez affecter.</span><span class="sxs-lookup"><span data-stu-id="53d05-151">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="53d05-152">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="53d05-152">Click **Save**.</span></span>

---
title: Gérer vos périphériques dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: kelsawi
f1keywords: ms.teamsadmincenter.devicemanagement.overview
description: Découvrez comment gérer les périphériques utilisés dans les équipes de votre organisation.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1cf2dcc1d300490d1b3049c9513d0c4e16c3f83
ms.sourcegitcommit: d400c8f83a2325c4a8bbb963ddad685a346bc4d8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/07/2019
ms.locfileid: "29760590"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="14c8c-103">Gérer vos périphériques dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="14c8c-103">Manage your devices in Microsoft Teams</span></span>

::: zone target="docs"
<span data-ttu-id="14c8c-104">En tant qu’administrateur, vous gérez tous les périphériques utilisés dans les équipes de votre organisation à partir de la & Microsoft Teams Skype pour entreprise centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="14c8c-104">As an admin, you manage all devices used with Teams in your organization from the Microsoft Teams & Skype for Business admin center.</span></span> <span data-ttu-id="14c8c-105">Vous pouvez afficher et gérer l’inventaire des appareils pour votre organisation et effectuer des tâches telles que la mise à jour, de redémarrage et surveiller les diagnostics pour les appareils.</span><span class="sxs-lookup"><span data-stu-id="14c8c-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="14c8c-106">Vous pouvez également créer et affecter des profils de configuration pour un périphérique ou des groupes de périphériques.</span><span class="sxs-lookup"><span data-stu-id="14c8c-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="14c8c-107">Quels appareils pouvez-vous gérer ?</span><span class="sxs-lookup"><span data-stu-id="14c8c-107">What devices can you manage?</span></span>
<span data-ttu-id="14c8c-108">Appareils doivent être certifiées pour les équipes et inscrit dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="14c8c-108">Devices must be certified for Teams and enrolled in Teams.</span></span> <span data-ttu-id="14c8c-109">Un périphérique est inscrit automatiquement la première fois qu’un utilisateur se connecte aux équipes sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="14c8c-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="14c8c-110">Pour obtenir la liste des périphériques certifiés qui peuvent être gérés, voir [téléphones de conférence](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16) et les [téléphones de bureau](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34).</span><span class="sxs-lookup"><span data-stu-id="14c8c-110">For a list of certified devices that can be managed, see [Conference phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16) and [Desk phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34).</span></span>

> [!NOTE]
> <span data-ttu-id="14c8c-111">Si vous avez Microsoft Intune, périphériques sont automatiquement inscrits dans Intune.</span><span class="sxs-lookup"><span data-stu-id="14c8c-111">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="14c8c-112">Une fois un périphérique est inscrit, conformité périphérique est confirmée et stratégies d’accès conditionnel sont appliquées à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="14c8c-112">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span> 

## <a name="manage-devices-in-teams"></a><span data-ttu-id="14c8c-113">Gérer les périphériques dans les équipes</span><span class="sxs-lookup"><span data-stu-id="14c8c-113">Manage devices in Teams</span></span>

<span data-ttu-id="14c8c-114">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**</span><span class="sxs-lookup"><span data-stu-id="14c8c-114">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="14c8c-115">Dans la navigation de gauche, accédez à des **périphériques** > **Gestion de périphériques**.</span><span class="sxs-lookup"><span data-stu-id="14c8c-115">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="14c8c-116">Sélectionnez **tous les périphériques**.</span><span class="sxs-lookup"><span data-stu-id="14c8c-116">Select **All devices**.</span></span>  

::: zone-end

 <span data-ttu-id="14c8c-117">À partir de là, vous pouvez afficher et gérer tous les périphériques inscrits dans les équipes de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="14c8c-117">From here, you can view and manage all devices enrolled in Teams in your organization.</span></span> <span data-ttu-id="14c8c-118">Les informations qui s’affichent pour chaque périphérique incluent l’historique, fabricant, modèle, utilisateur, état, action, dernière apparaît et nom du périphérique.</span><span class="sxs-lookup"><span data-stu-id="14c8c-118">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="14c8c-119">Vous pouvez personnaliser l’affichage pour afficher les informations qui correspond le mieux à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="14c8c-119">You can customize the view to show the information that fits your needs.</span></span>

 <span data-ttu-id="14c8c-120">Voici quelques exemples de la façon de gérer les périphériques équipes au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="14c8c-120">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="14c8c-121">Pour ce faire...</span><span class="sxs-lookup"><span data-stu-id="14c8c-121">To do this...</span></span>  |<span data-ttu-id="14c8c-122">Cela</span><span class="sxs-lookup"><span data-stu-id="14c8c-122">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="14c8c-123">Modifier les informations de périphérique</span><span class="sxs-lookup"><span data-stu-id="14c8c-123">Change device information</span></span>   | <span data-ttu-id="14c8c-124">Sélectionnez un > périphérique **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="14c8c-124">Select a device > **Edit**.</span></span> <span data-ttu-id="14c8c-125">Vous pouvez modifier les détails tels que le nom du périphérique, les informations utilisateur, numéro d’identification et ajouter des notes.</span><span class="sxs-lookup"><span data-stu-id="14c8c-125">You can edit details such as device name, user information, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="14c8c-126">Gérer les mises à jour logicielles</span><span class="sxs-lookup"><span data-stu-id="14c8c-126">Manage software updates</span></span>   |<span data-ttu-id="14c8c-127">Sélectionnez un périphérique de > **mise à jour**.</span><span class="sxs-lookup"><span data-stu-id="14c8c-127">Select a device > **Update**.</span></span> <span data-ttu-id="14c8c-128">Vous pouvez afficher la liste des mises à jour de logiciels et de microprogrammes, disponibles pour le périphérique et cliquez sur Installer les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="14c8c-128">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="14c8c-129">Redémarrer un appareil</span><span class="sxs-lookup"><span data-stu-id="14c8c-129">Restart a device</span></span>   |<span data-ttu-id="14c8c-130">Sélectionnez un > périphérique **redémarrer**.</span><span class="sxs-lookup"><span data-stu-id="14c8c-130">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="14c8c-131">Afficher l’historique du périphérique</span><span class="sxs-lookup"><span data-stu-id="14c8c-131">View device history</span></span>  | <span data-ttu-id="14c8c-132">Sélectionnez un > périphérique **historique**.</span><span class="sxs-lookup"><span data-stu-id="14c8c-132">Select a device > **History**.</span></span> <span data-ttu-id="14c8c-133">Vous pouvez afficher l’historique de mise à jour du périphérique.</span><span class="sxs-lookup"><span data-stu-id="14c8c-133">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="14c8c-134">Afficher des diagnostics</span><span class="sxs-lookup"><span data-stu-id="14c8c-134">View diagnostics</span></span>  | <span data-ttu-id="14c8c-135">Sélectionnez un périphérique de > **Diagnostics**.</span><span class="sxs-lookup"><span data-stu-id="14c8c-135">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="14c8c-136">Utilisation des profils de configuration dans les équipes</span><span class="sxs-lookup"><span data-stu-id="14c8c-136">Use configuration profiles in Teams</span></span>

<span data-ttu-id="14c8c-137">Utilisez les profils de configuration pour gérer les paramètres et les fonctionnalités pour les périphériques des équipes au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="14c8c-137">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="14c8c-138">Vous pouvez créer ou télécharger des profils de configuration pour inclure les paramètres et les fonctionnalités que vous souhaitez activer ou désactiver et affecter un profil à un appareil ou des groupes de périphériques.</span><span class="sxs-lookup"><span data-stu-id="14c8c-138">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="14c8c-139">Créer un profil de configuration</span><span class="sxs-lookup"><span data-stu-id="14c8c-139">Create a configuration profile</span></span>

::: zone target="docs"

![les équipes-logo-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="14c8c-141">À l’aide de la & Microsoft Teams Skype entreprise centre d’administration</span><span class="sxs-lookup"><span data-stu-id="14c8c-141">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="14c8c-142">Dans la navigation de gauche, accédez à des **périphériques** > **Gestion de périphériques**.</span><span class="sxs-lookup"><span data-stu-id="14c8c-142">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>

::: zone-end

2. <span data-ttu-id="14c8c-143">Sélectionnez **les profils de Configuration**, puis sélectionnez le **profil de configuration**.</span><span class="sxs-lookup"><span data-stu-id="14c8c-143">Select **Configuration profiles**, and then select **New configuration profile**.</span></span>
3. <span data-ttu-id="14c8c-144">Entrez un nom pour le profil et si vous le souhaitez, ajoutez une description conviviale.</span><span class="sxs-lookup"><span data-stu-id="14c8c-144">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="14c8c-145">Spécifier les paramètres souhaités pour le profil, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="14c8c-145">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="14c8c-146">Affecter un profil de configuration</span><span class="sxs-lookup"><span data-stu-id="14c8c-146">Assign a configuration profile</span></span>

::: zone target="docs"

![les équipes-logo-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="14c8c-148">À l’aide de la & Microsoft Teams Skype entreprise centre d’administration</span><span class="sxs-lookup"><span data-stu-id="14c8c-148">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="14c8c-149">Dans la navigation de gauche, accédez à des **périphériques** > **Gestion de périphériques**.</span><span class="sxs-lookup"><span data-stu-id="14c8c-149">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>

::: zone-end

2. <span data-ttu-id="14c8c-150">Sélectionnez le **profil de Configuration**, puis cliquez sur le lien sous **affecté à** dans le profil que vous voulez affecter.</span><span class="sxs-lookup"><span data-stu-id="14c8c-150">Select **Configuration profile**, and then under **Assigned to** in the profile you want to assign, click the link.</span></span>  
3. <span data-ttu-id="14c8c-151">Dans le volet **affecter des périphériques à un profil de configuration** , recherchez et sélectionnez les périphériques que vous voulez attribuer.</span><span class="sxs-lookup"><span data-stu-id="14c8c-151">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="14c8c-152">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="14c8c-152">Click **Save**.</span></span>

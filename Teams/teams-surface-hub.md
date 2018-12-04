---
title: Déployer les équipes Microsoft Surface concentrateur
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Configurer les paramètres d’administration pour Microsoft Teams concentrateur de la surface d’exposition.
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 485e4063c523608421955b86e0be680d5dc10b9a
ms.sourcegitcommit: 5742301cdd28e5e26107920f18e70f41b0f67cfb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/03/2018
ms.locfileid: "27132002"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="b57c9-103">Déployer les équipes Microsoft Surface concentrateur</span><span class="sxs-lookup"><span data-stu-id="b57c9-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="b57c9-104">Avant de déployer Microsoft Teams Microsoft Surface concentrateur, assurez-vous que le matériel, système d’exploitation et autres conditions sont réunies.</span><span class="sxs-lookup"><span data-stu-id="b57c9-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="b57c9-105">Pour plus d’informations, consultez le [guide d’administration de Microsoft Surface Hub](https://docs.microsoft.com/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="b57c9-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/surface-hub/).</span></span>

> [!NOTE]
> <span data-ttu-id="b57c9-106">Si vous faites passer de Skype pour Business Online, vous devez vérifier qu’une licence de Microsoft Teams est attribuée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b57c9-106">If you are transitioning from Skype for Business Online, you need to confirm that a Microsoft Teams license is assigned to the user.</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="b57c9-107">Installer des équipes pour exposer Hub à partir du magasin de Microsoft</span><span class="sxs-lookup"><span data-stu-id="b57c9-107">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="b57c9-108">Ces instructions sont pour l’installation des équipes concentrateur de Surface à partir de Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="b57c9-108">These instructions are for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="b57c9-109">Démarrer la banque Microsoft :</span><span class="sxs-lookup"><span data-stu-id="b57c9-109">Start the Microsoft Store:</span></span><br>
   <span data-ttu-id="b57c9-110">a.</span><span class="sxs-lookup"><span data-stu-id="b57c9-110">a.</span></span> <span data-ttu-id="b57c9-111">Cliquez sur **Démarrer** > **toutes les applications** > **paramètres**.</span><span class="sxs-lookup"><span data-stu-id="b57c9-111">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="b57c9-112">b.</span><span class="sxs-lookup"><span data-stu-id="b57c9-112">b.</span></span> <span data-ttu-id="b57c9-113">Cliquez sur **compte de Surface Hub DISPOSITIF, la gestion**.</span><span class="sxs-lookup"><span data-stu-id="b57c9-113">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="b57c9-114">c.</span><span class="sxs-lookup"><span data-stu-id="b57c9-114">c.</span></span> <span data-ttu-id="b57c9-115">Sur la gauche, cliquez sur l’onglet **applications et fonctionnalités** .</span><span class="sxs-lookup"><span data-stu-id="b57c9-115">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="b57c9-116">d.</span><span class="sxs-lookup"><span data-stu-id="b57c9-116">d.</span></span> <span data-ttu-id="b57c9-117">Sur la droite, appuyez sur le bouton **Ouvrir un magasin** .</span><span class="sxs-lookup"><span data-stu-id="b57c9-117">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="b57c9-118">Dans le Store Microsoft, recherchez les *Équipes Microsoft*.</span><span class="sxs-lookup"><span data-stu-id="b57c9-118">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="b57c9-119">Les **Équipes Microsoft Surface concentrateur** s’affichera.</span><span class="sxs-lookup"><span data-stu-id="b57c9-119">The **Microsoft Teams for Surface Hub** will be displayed.</span></span> <span data-ttu-id="b57c9-120">Appuyez sur le bouton **obtenir l’application** à installer.</span><span class="sxs-lookup"><span data-stu-id="b57c9-120">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="b57c9-121">Une fois l’installation terminée, redémarrez le Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="b57c9-121">When the installation is complete, restart the Surface Hub.</span></span> 

> [!NOTE]
> <span data-ttu-id="b57c9-122">Ne cliquez pas la **barre de lancement** de la page de liste des magasins.</span><span class="sxs-lookup"><span data-stu-id="b57c9-122">Do not tap **Launch** from the Store listing page.</span></span>

## <a name="make-teams-the-default-calling-and-meetings-application"></a><span data-ttu-id="b57c9-123">Rendre les équipes l’appel par défaut et l’application de réunions</span><span class="sxs-lookup"><span data-stu-id="b57c9-123">Make Teams the default calling and meetings application</span></span>
 
<span data-ttu-id="b57c9-124">Il existe deux options pour la configuration de la stratégie d’application appelant et réunions par défaut :</span><span class="sxs-lookup"><span data-stu-id="b57c9-124">There are two options for configuring the default calling and meetings application policy:</span></span> 

- <span data-ttu-id="b57c9-125">**Option 1**: configurer via une clé USB.</span><span class="sxs-lookup"><span data-stu-id="b57c9-125">**Option 1**: Configure via USB key.</span></span> 
- <span data-ttu-id="b57c9-126">**Option 2**: configurer via Mobile Device Manager tels que Intune.</span><span class="sxs-lookup"><span data-stu-id="b57c9-126">**Option 2**: Configure via MDM such as Intune.</span></span>
 
### <a name="option-1-configure-via-usb-key"></a><span data-ttu-id="b57c9-127">Option 1 : Configurer via une clé USB</span><span class="sxs-lookup"><span data-stu-id="b57c9-127">Option 1: Configure via USB key</span></span> 
 
<span data-ttu-id="b57c9-128">Les packages se trouvent sur cette [page de téléchargement](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span><span class="sxs-lookup"><span data-stu-id="b57c9-128">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="b57c9-129">Choisissez celui qui convient pour le programme que vous prévoyez d’installer et de le copier sur une clé USB.</span><span class="sxs-lookup"><span data-stu-id="b57c9-129">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="b57c9-130">Le fichier .ppkg correct à utiliser dépend de la stratégie d’application par défaut que voulez-vous appliquer comme suit :</span><span class="sxs-lookup"><span data-stu-id="b57c9-130">The correct .ppkg file to use depends on the default application policy you'd like to apply as follows:</span></span> 

|<span data-ttu-id="b57c9-131">Numéro</span><span class="sxs-lookup"><span data-stu-id="b57c9-131">Number</span></span>  |<span data-ttu-id="b57c9-132">Description</span><span class="sxs-lookup"><span data-stu-id="b57c9-132">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="b57c9-133">0</span><span class="sxs-lookup"><span data-stu-id="b57c9-133">0</span></span>     | <span data-ttu-id="b57c9-134">Application préférée Skype sur l’écran de démarrage, équipes de réunions disponibles</span><span class="sxs-lookup"><span data-stu-id="b57c9-134">Skype preferred app on the Start Screen, Teams Meetings available</span></span>        |
|<span data-ttu-id="b57c9-135">1</span><span class="sxs-lookup"><span data-stu-id="b57c9-135">1</span></span>     | <span data-ttu-id="b57c9-136">Application préférée équipes sur l’écran de démarrage, Skype réunions disponibles</span><span class="sxs-lookup"><span data-stu-id="b57c9-136">Teams preferred app on the Start Screen, Skype Meetings available</span></span>        |
|<span data-ttu-id="b57c9-137">2</span><span class="sxs-lookup"><span data-stu-id="b57c9-137">2</span></span>     | <span data-ttu-id="b57c9-138">Application exclusive équipes sur l’écran d’accueil (Skype app n’est pas disponible)</span><span class="sxs-lookup"><span data-stu-id="b57c9-138">Teams exclusive app on the Start screen (Skype app not available)</span></span>        |
 
1. <span data-ttu-id="b57c9-139">Attacher la clé USB à l’appareil Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="b57c9-139">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="b57c9-140">Ouvrez l’application de **paramètres** sur un appareil Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="b57c9-140">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="b57c9-141">Ouvrez **gestion de compte Hub Surface périphérique**.</span><span class="sxs-lookup"><span data-stu-id="b57c9-141">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="b57c9-142">Ouvrez **Gestion des périphériques**.</span><span class="sxs-lookup"><span data-stu-id="b57c9-142">Open **Device Management**.</span></span> 
5. <span data-ttu-id="b57c9-143">Cliquez sur **Ajouter ou supprimer un package de mise en service**.</span><span class="sxs-lookup"><span data-stu-id="b57c9-143">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="b57c9-144">Cliquez sur **Ajouter un Package**.</span><span class="sxs-lookup"><span data-stu-id="b57c9-144">Click **Add Package**.</span></span>
7. <span data-ttu-id="b57c9-145">Sélectionnez l’option **Support amovible** dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="b57c9-145">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="b57c9-146">Ajoutez le package <strong>TeamsRTMMode\*.ppkg</strong> approprié qui a été précédemment copié à la clé USB.</span><span class="sxs-lookup"><span data-stu-id="b57c9-146">Add the appropriate <strong>TeamsRTMMode\*.ppkg</strong> package that was previously copied to the USB key.</span></span> 
9. <span data-ttu-id="b57c9-147">Redémarrez le dispositif Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="b57c9-147">Restart the Surface Hub device.</span></span> 
10. <span data-ttu-id="b57c9-148">Après le redémarrage de l’appareil, vous devez être en mesure de démarrer l’application des équipes à partir de l’écran d’accueil et participer à une réunion à partir du calendrier.</span><span class="sxs-lookup"><span data-stu-id="b57c9-148">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span> 

### <a name="option-2-configure-via-mdm-such-as-intune"></a><span data-ttu-id="b57c9-149">Option 2 : Configurer via Mobile Device Manager tels que Intune</span><span class="sxs-lookup"><span data-stu-id="b57c9-149">Option 2: Configure via MDM such as Intune</span></span> 

<span data-ttu-id="b57c9-150">Utilisez ce qui suit pour configurer la stratégie par défaut les réunions et les appels d’application via Intune.</span><span class="sxs-lookup"><span data-stu-id="b57c9-150">Use the following to configure the default calling and meetings application policy via Intune.</span></span> <span data-ttu-id="b57c9-151">Consultez également le blog, [déployer les équipes Microsoft pour Hub de la Surface d’application à l’aide de Intune](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/).</span><span class="sxs-lookup"><span data-stu-id="b57c9-151">Also see the blog, [Deploy the Microsoft Teams for Surface Hub app using Intune](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/).</span></span>

|<span data-ttu-id="b57c9-152">Paramètre</span><span class="sxs-lookup"><span data-stu-id="b57c9-152">Setting</span></span>   |<span data-ttu-id="b57c9-153">Valeur</span><span class="sxs-lookup"><span data-stu-id="b57c9-153">Value</span></span>    |<span data-ttu-id="b57c9-154">Description</span><span class="sxs-lookup"><span data-stu-id="b57c9-154">Description</span></span>    |
|----------|---------|---------|
|<span data-ttu-id="b57c9-155"> Path</span><span class="sxs-lookup"><span data-stu-id="b57c9-155">Path</span></span>      | <span data-ttu-id="b57c9-156">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span><span class="sxs-lookup"><span data-stu-id="b57c9-156">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span></span>        |
|<span data-ttu-id="b57c9-157">Type de données</span><span class="sxs-lookup"><span data-stu-id="b57c9-157">Data Type</span></span> | <span data-ttu-id="b57c9-158">nombre entier (0-2)</span><span class="sxs-lookup"><span data-stu-id="b57c9-158">integer (0-2)</span></span>   |<span data-ttu-id="b57c9-159">0 - application préféré Skype sur l’écran de démarrage, équipes de réunions disponibles</span><span class="sxs-lookup"><span data-stu-id="b57c9-159">0 - Skype preferred app on the Start Screen, Teams Meetings available</span></span><br><span data-ttu-id="b57c9-160">1 - teams préféré application sur l’écran de démarrage, Skype réunions disponibles</span><span class="sxs-lookup"><span data-stu-id="b57c9-160">1 - Teams preferred app on the Start Screen, Skype Meetings available</span></span><br><span data-ttu-id="b57c9-161">2 - application exclusive d’équipes sur l’écran d’accueil (Skype app n’est pas disponible)</span><span class="sxs-lookup"><span data-stu-id="b57c9-161">2 - Teams exclusive app on the Start screen (Skype app not available)</span></span> |
|<span data-ttu-id="b57c9-162">Opérations</span><span class="sxs-lookup"><span data-stu-id="b57c9-162">Operations</span></span>| <span data-ttu-id="b57c9-163">Obtenir, définir</span><span class="sxs-lookup"><span data-stu-id="b57c9-163">Get, Set</span></span>        |

|<span data-ttu-id="b57c9-164">Paramètre</span><span class="sxs-lookup"><span data-stu-id="b57c9-164">Setting</span></span>   |<span data-ttu-id="b57c9-165">Valeur</span><span class="sxs-lookup"><span data-stu-id="b57c9-165">Value</span></span>    |
|----------|---------|
|<span data-ttu-id="b57c9-166"> Path</span><span class="sxs-lookup"><span data-stu-id="b57c9-166">Path</span></span>      | <span data-ttu-id="b57c9-167">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span><span class="sxs-lookup"><span data-stu-id="b57c9-167">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span></span>        |
|<span data-ttu-id="b57c9-168">Type de données</span><span class="sxs-lookup"><span data-stu-id="b57c9-168">Data Type</span></span> | <span data-ttu-id="b57c9-169">chaîne - ensemble chaîne aux équipes des ID de package d’application en tant que **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe ! Les équipes**</span><span class="sxs-lookup"><span data-stu-id="b57c9-169">string - set string to Teams application package ID as **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams**</span></span> |
|<span data-ttu-id="b57c9-170">Opérations</span><span class="sxs-lookup"><span data-stu-id="b57c9-170">Operations</span></span>| <span data-ttu-id="b57c9-171">Obtenir, définir</span><span class="sxs-lookup"><span data-stu-id="b57c9-171">Get, Set</span></span>        |

<span data-ttu-id="b57c9-172">Redémarrez le dispositif Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="b57c9-172">Restart the Surface Hub device.</span></span> <span data-ttu-id="b57c9-173">Après le redémarrage de l’appareil, vous devez être en mesure de démarrer l’application des équipes à partir de l’écran d’accueil et participer à une réunion à partir du calendrier.</span><span class="sxs-lookup"><span data-stu-id="b57c9-173">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span>


---
title: Déployer les équipes Microsoft Surface concentrateur
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 09/26/2018
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
ms.openlocfilehash: aca03693a7abea6e26f175cc49f0142894749160
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372180"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="0cafb-103">Déployer les équipes Microsoft Surface concentrateur</span><span class="sxs-lookup"><span data-stu-id="0cafb-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="0cafb-104">Avant de déployer Microsoft Teams Microsoft Surface concentrateur, assurez-vous que le matériel, système d’exploitation et autres conditions sont réunies.</span><span class="sxs-lookup"><span data-stu-id="0cafb-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="0cafb-105">Pour plus d’informations, consultez le [guide d’administration de Microsoft Surface Hub](https://docs.microsoft.com/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="0cafb-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/surface-hub/).</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="0cafb-106">Installer des équipes pour exposer Hub à partir du magasin de Microsoft</span><span class="sxs-lookup"><span data-stu-id="0cafb-106">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="0cafb-107">Ces instructions sont pour l’installation des équipes concentrateur de Surface à partir de Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="0cafb-107">These instructions are for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="0cafb-108">Démarrer la banque Microsoft :</span><span class="sxs-lookup"><span data-stu-id="0cafb-108">Start the Microsoft Store:</span></span><br>
   <span data-ttu-id="0cafb-109">a.</span><span class="sxs-lookup"><span data-stu-id="0cafb-109">a.</span></span> <span data-ttu-id="0cafb-110">Cliquez sur **Démarrer** > **toutes les applications** > **paramètres**.</span><span class="sxs-lookup"><span data-stu-id="0cafb-110">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="0cafb-111">b.</span><span class="sxs-lookup"><span data-stu-id="0cafb-111">b.</span></span> <span data-ttu-id="0cafb-112">Cliquez sur **compte de Surface Hub DISPOSITIF, la gestion**.</span><span class="sxs-lookup"><span data-stu-id="0cafb-112">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="0cafb-113">c.</span><span class="sxs-lookup"><span data-stu-id="0cafb-113">c.</span></span> <span data-ttu-id="0cafb-114">Sur la gauche, cliquez sur l’onglet **applications et fonctionnalités** .</span><span class="sxs-lookup"><span data-stu-id="0cafb-114">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="0cafb-115">d.</span><span class="sxs-lookup"><span data-stu-id="0cafb-115">d.</span></span> <span data-ttu-id="0cafb-116">Sur la droite, appuyez sur le bouton **Ouvrir un magasin** .</span><span class="sxs-lookup"><span data-stu-id="0cafb-116">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="0cafb-117">Dans le Store Microsoft, recherchez les *Équipes Microsoft*.</span><span class="sxs-lookup"><span data-stu-id="0cafb-117">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="0cafb-118">Les **Équipes Microsoft Surface concentrateur** s’affichera.</span><span class="sxs-lookup"><span data-stu-id="0cafb-118">The **Microsoft Teams for Surface Hub** will be displayed.</span></span> <span data-ttu-id="0cafb-119">Appuyez sur le bouton **obtenir l’application** à installer.</span><span class="sxs-lookup"><span data-stu-id="0cafb-119">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="0cafb-120">Une fois l’installation terminée, redémarrez le Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="0cafb-120">When the installation is complete, restart the Surface Hub.</span></span> 

> [!NOTE]
> <span data-ttu-id="0cafb-121">Ne cliquez pas sur la **barre de lancement** de la page de liste des magasins.</span><span class="sxs-lookup"><span data-stu-id="0cafb-121">Do not tap on **Launch** from the Store listing page.</span></span>

## <a name="make-teams-the-default-calling-and-meetings-application"></a><span data-ttu-id="0cafb-122">Rendre les équipes l’appel par défaut et l’application de réunions</span><span class="sxs-lookup"><span data-stu-id="0cafb-122">Make Teams the default calling and meetings application</span></span>
 
<span data-ttu-id="0cafb-123">Il existe deux options pour la configuration de la stratégie d’application appelant et réunions par défaut :</span><span class="sxs-lookup"><span data-stu-id="0cafb-123">There are two options for configuring the default calling and meetings application policy:</span></span> 

- <span data-ttu-id="0cafb-124">**Option 1**: configurer via une clé USB.</span><span class="sxs-lookup"><span data-stu-id="0cafb-124">**Option 1**: Configure via USB key.</span></span> 
- <span data-ttu-id="0cafb-125">**Option 2**: configurer via Mobile Device Manager tels que Intune.</span><span class="sxs-lookup"><span data-stu-id="0cafb-125">**Option 2**: Configure via MDM such as Intune.</span></span>
 
### <a name="option-1-configure-via-usb-key"></a><span data-ttu-id="0cafb-126">Option 1 : Configurer via une clé USB</span><span class="sxs-lookup"><span data-stu-id="0cafb-126">Option 1: Configure via USB key</span></span> 
 
<span data-ttu-id="0cafb-127">Les packages se trouvent sur cette [page de téléchargement](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span><span class="sxs-lookup"><span data-stu-id="0cafb-127">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="0cafb-128">Choisissez celui qui convient pour le programme que vous prévoyez d’installer et de le copier sur une clé USB.</span><span class="sxs-lookup"><span data-stu-id="0cafb-128">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="0cafb-129">Le fichier .ppkg correct à utiliser dépend de la stratégie d’application par défaut que voulez-vous appliquer comme suit :</span><span class="sxs-lookup"><span data-stu-id="0cafb-129">The correct .ppkg file to use depends on the default application policy you'd like to apply as follows:</span></span> 

|<span data-ttu-id="0cafb-130">Numéro</span><span class="sxs-lookup"><span data-stu-id="0cafb-130">Number</span></span>  |<span data-ttu-id="0cafb-131">Description</span><span class="sxs-lookup"><span data-stu-id="0cafb-131">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="0cafb-132">0</span><span class="sxs-lookup"><span data-stu-id="0cafb-132">0</span></span>     | <span data-ttu-id="0cafb-133">Application préférée Skype sur l’écran de démarrage, équipes de réunions disponibles</span><span class="sxs-lookup"><span data-stu-id="0cafb-133">Skype preferred app on the Start Screen, Teams Meetings available</span></span>        |
|<span data-ttu-id="0cafb-134">1</span><span class="sxs-lookup"><span data-stu-id="0cafb-134">1</span></span>     | <span data-ttu-id="0cafb-135">Application préférée équipes sur l’écran de démarrage, Skype réunions disponibles</span><span class="sxs-lookup"><span data-stu-id="0cafb-135">Teams preferred app on the Start Screen, Skype Meetings available</span></span>        |
|<span data-ttu-id="0cafb-136">2</span><span class="sxs-lookup"><span data-stu-id="0cafb-136">2</span></span>     | <span data-ttu-id="0cafb-137">Application exclusive équipes sur l’écran d’accueil (Skype app n’est pas disponible)</span><span class="sxs-lookup"><span data-stu-id="0cafb-137">Teams exclusive app on the Start screen (Skype app not available)</span></span>        |
 
1. <span data-ttu-id="0cafb-138">Attacher la clé USB à l’appareil Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="0cafb-138">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="0cafb-139">Ouvrez l’application de **paramètres** sur un appareil Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="0cafb-139">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="0cafb-140">Ouvrez **gestion de compte Hub Surface périphérique**.</span><span class="sxs-lookup"><span data-stu-id="0cafb-140">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="0cafb-141">Ouvrez **Gestion des périphériques**.</span><span class="sxs-lookup"><span data-stu-id="0cafb-141">Open **Device Management**.</span></span> 
5. <span data-ttu-id="0cafb-142">Cliquez sur **Ajouter ou supprimer un package de mise en service**.</span><span class="sxs-lookup"><span data-stu-id="0cafb-142">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="0cafb-143">Cliquez sur **Ajouter un Package**.</span><span class="sxs-lookup"><span data-stu-id="0cafb-143">Click **Add Package**.</span></span>
7. <span data-ttu-id="0cafb-144">Sélectionnez l’option **Support amovible** dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="0cafb-144">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="0cafb-145">Ajoutez le package <strong>TeamsRTMMode\*.ppkg</strong> approprié qui a été précédemment copié à la clé USB.</span><span class="sxs-lookup"><span data-stu-id="0cafb-145">Add the appropriate <strong>TeamsRTMMode\*.ppkg</strong> package that was previously copied to the USB key.</span></span> 
9. <span data-ttu-id="0cafb-146">Redémarrez le dispositif Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="0cafb-146">Restart the Surface Hub device.</span></span> 
10. <span data-ttu-id="0cafb-147">Après le redémarrage de l’appareil, vous devez être en mesure de démarrer l’application des équipes à partir de l’écran d’accueil et participer à une réunion à partir du calendrier.</span><span class="sxs-lookup"><span data-stu-id="0cafb-147">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span> 

### <a name="option-2-configure-via-mdm-such-as-intune"></a><span data-ttu-id="0cafb-148">Option 2 : Configurer via Mobile Device Manager tels que Intune</span><span class="sxs-lookup"><span data-stu-id="0cafb-148">Option 2: Configure via MDM such as Intune</span></span> 

<span data-ttu-id="0cafb-149">Utilisez ce qui suit pour configurer la stratégie par défaut les réunions et les appels d’application via Intune.</span><span class="sxs-lookup"><span data-stu-id="0cafb-149">Use the following to configure the default calling and meetings application policy via Intune.</span></span> <span data-ttu-id="0cafb-150">Consultez également le blog, [déployer les équipes Microsoft pour Hub de la Surface d’application à l’aide de Intune](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/).</span><span class="sxs-lookup"><span data-stu-id="0cafb-150">Also see the blog, [Deploy the Microsoft Teams for Surface Hub app using Intune](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/).</span></span>

|<span data-ttu-id="0cafb-151">Paramètre</span><span class="sxs-lookup"><span data-stu-id="0cafb-151">Setting</span></span>   |<span data-ttu-id="0cafb-152">Valeur</span><span class="sxs-lookup"><span data-stu-id="0cafb-152">Value</span></span>    |<span data-ttu-id="0cafb-153">Description</span><span class="sxs-lookup"><span data-stu-id="0cafb-153">Description</span></span>    |
|----------|---------|---------|
|<span data-ttu-id="0cafb-154"> Path</span><span class="sxs-lookup"><span data-stu-id="0cafb-154">Path</span></span>      | <span data-ttu-id="0cafb-155">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span><span class="sxs-lookup"><span data-stu-id="0cafb-155">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span></span>        |
|<span data-ttu-id="0cafb-156">Type de données</span><span class="sxs-lookup"><span data-stu-id="0cafb-156">Data Type</span></span> | <span data-ttu-id="0cafb-157">nombre entier (0-2)</span><span class="sxs-lookup"><span data-stu-id="0cafb-157">integer (0-2)</span></span>   |<span data-ttu-id="0cafb-158">0 - application préféré Skype sur l’écran de démarrage, équipes de réunions disponibles</span><span class="sxs-lookup"><span data-stu-id="0cafb-158">0 - Skype preferred app on the Start Screen, Teams Meetings available</span></span><br><span data-ttu-id="0cafb-159">1 - teams préféré application sur l’écran de démarrage, Skype réunions disponibles</span><span class="sxs-lookup"><span data-stu-id="0cafb-159">1 - Teams preferred app on the Start Screen, Skype Meetings available</span></span><br><span data-ttu-id="0cafb-160">2 - application exclusive d’équipes sur l’écran d’accueil (Skype app n’est pas disponible)</span><span class="sxs-lookup"><span data-stu-id="0cafb-160">2 - Teams exclusive app on the Start screen (Skype app not available)</span></span> |
|<span data-ttu-id="0cafb-161">Opérations</span><span class="sxs-lookup"><span data-stu-id="0cafb-161">Operations</span></span>| <span data-ttu-id="0cafb-162">Obtenir, définir</span><span class="sxs-lookup"><span data-stu-id="0cafb-162">Get, Set</span></span>        |

|<span data-ttu-id="0cafb-163">Paramètre</span><span class="sxs-lookup"><span data-stu-id="0cafb-163">Setting</span></span>   |<span data-ttu-id="0cafb-164">Valeur</span><span class="sxs-lookup"><span data-stu-id="0cafb-164">Value</span></span>    |
|----------|---------|
|<span data-ttu-id="0cafb-165"> Path</span><span class="sxs-lookup"><span data-stu-id="0cafb-165">Path</span></span>      | <span data-ttu-id="0cafb-166">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span><span class="sxs-lookup"><span data-stu-id="0cafb-166">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span></span>        |
|<span data-ttu-id="0cafb-167">Type de données</span><span class="sxs-lookup"><span data-stu-id="0cafb-167">Data Type</span></span> | <span data-ttu-id="0cafb-168">chaîne - ensemble chaîne aux équipes des ID de package d’application en tant que **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe ! Les équipes**</span><span class="sxs-lookup"><span data-stu-id="0cafb-168">string - set string to Teams application package ID as **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams**</span></span> |
|<span data-ttu-id="0cafb-169">Opérations</span><span class="sxs-lookup"><span data-stu-id="0cafb-169">Operations</span></span>| <span data-ttu-id="0cafb-170">Obtenir, définir</span><span class="sxs-lookup"><span data-stu-id="0cafb-170">Get, Set</span></span>        |

<span data-ttu-id="0cafb-171">Redémarrez le dispositif Hub de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="0cafb-171">Restart the Surface Hub device.</span></span> <span data-ttu-id="0cafb-172">Après le redémarrage de l’appareil, vous devez être en mesure de démarrer l’application des équipes à partir de l’écran d’accueil et participer à une réunion à partir du calendrier.</span><span class="sxs-lookup"><span data-stu-id="0cafb-172">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span>


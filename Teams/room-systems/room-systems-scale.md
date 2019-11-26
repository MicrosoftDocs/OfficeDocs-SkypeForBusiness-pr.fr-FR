---
title: Déploiement de salles de Microsoft teams à l’aide de System Center Configuration Manager
author: lanachin
ms.author: v-lanac
ms.reviewer: Turgayo
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: Consultez cette rubrique pour en savoir plus sur le déploiement de salles de Microsoft teams à des déploiements à grande échelle.
no-loc:
- Microsoft
- Microsoft Corporation
- Microsoft Teams Rooms
- Microsoft Teams Room
- System Center
- Configuration Manager
- Windows
- Surface
- Surface Pro
- Windows PE
- Windows 10
- Windows 10 Enterprise
- Azure
- Azure Monitor
- Log Analytics
- Operations Management Suite
ms.openlocfilehash: d116ea000bc18bf0e9c017b67bfa104dcfa29795
ms.sourcegitcommit: 000957709b841ce55a6813ccc2fbe745b1a9295b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2019
ms.locfileid: "39218031"
---
# <a name="deploy-microsoft-teams-rooms-by-using-system-center-configuration-manager"></a><span data-ttu-id="a2d8e-103">Déploiement de salles de Microsoft teams à l’aide de System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a2d8e-103">Deploy Microsoft Teams Rooms by using System Center Configuration Manager</span></span>

<span data-ttu-id="a2d8e-104">Cet article vous fournit toutes les informations nécessaires pour créer les déploiements de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using System Center Configuration Manager.</span></span>

<span data-ttu-id="a2d8e-105">À l’aide des méthodes simples d’utilisation fournies par System Center Configuration Manager, vous pouvez déployer le système d’exploitation et d’autres applications sur plusieurs appareils cibles.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-105">With the easy-to-use methods provided by System Center Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="a2d8e-106">Utilisez l’approche illustrée ci-dessous pour vous guider dans votre configuration du gestionnaire de configuration et personnaliser les packages et les scripts fournis dans ces conseils selon les besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Processus de déploiement de Microsoft teams à l’aide de Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="a2d8e-108">Cette solution n’a été testée qu’avec des déploiements en surface Pro.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="a2d8e-109">Suivez les instructions du fabricant pour les configurations qui ne sont pas basées sur surface Pro.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-109">Follow the manufacturer’s guidelines for configurations that aren’t based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="a2d8e-110">Valider les conditions préalables</span><span class="sxs-lookup"><span data-stu-id="a2d8e-110">Validate prerequisites</span></span>

<span data-ttu-id="a2d8e-111">Pour déployer des salles Microsoft teams avec Configuration Manager, vérifiez que vous remplissez les conditions préalables et requises suivantes.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="system-center-configuration-manager-requirements"></a><span data-ttu-id="a2d8e-112">Configuration requise pour System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a2d8e-112">System Center Configuration Manager requirements</span></span>

-   <span data-ttu-id="a2d8e-113">La version de System Center Configuration Manager doit être au minimum 1706 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-113">System Center Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="a2d8e-114">Nous vous recommandons d’utiliser 1710 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="a2d8e-115">Pour en savoir plus sur les versions de Windows 10 prises en charge par Configuration Manager, voir [prise en charge de Windows 10 dans System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) .</span><span class="sxs-lookup"><span data-stu-id="a2d8e-115">Check out [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="a2d8e-116">Une version prise en charge de kit de déploiement et d’évaluation Windows (ADK) pour Windows 10 doit être installée.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="a2d8e-117">Découvrez les versions de [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) que vous pouvez utiliser avec différentes versions de Configuration Manager et assurez-vous que votre déploiement inclut la version correcte.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-117">See the versions of the [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="a2d8e-118">Les serveurs de systèmes de site doivent avoir reçu le rôle de point de distribution et les images de démarrage doivent être activées pour la [prise en charge de l’environnement d’exécution prédémarrage (PXE)](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) pour permettre les déploiements initiés par le réseau.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="a2d8e-119">Si la prise en charge de PXE n’est pas activée, vous pouvez utiliser un [média amorçable](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) pour vos déploiements.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-119">If PXE support isn’t enabled, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="a2d8e-120">Un compte d’accès réseau doit être configuré pour prendre en charge les scénarios de déploiement de nouveaux ordinateurs (de matériel vierge).</span><span class="sxs-lookup"><span data-stu-id="a2d8e-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="a2d8e-121">Pour en savoir plus sur la configuration d’un compte d’accès réseau, voir [gérer les comptes pour accéder au contenu dans System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="a2d8e-121">To learn more about the configuration of a network access account, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="a2d8e-122">Nous vous recommandons d’activer la [prise en charge de la multidiffusion](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), si vous déployez en même temps la même image dans plusieurs salles de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-122">We recommend that you enable [multicast support](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you’re likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="a2d8e-123">Configuration réseau requise</span><span class="sxs-lookup"><span data-stu-id="a2d8e-123">Networking requirements</span></span>

-   <span data-ttu-id="a2d8e-124">Votre réseau doit être doté d’un serveur de protocole de configuration de l’hôte dynamique, configuré pour la distribution automatique de l’adresse IP sur les sous-réseaux dans lesquels les unités de salles de Microsoft teams sont déployées.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a2d8e-125">La durée du bail DHCP doit être définie sur une valeur supérieure à la durée du déploiement d’image.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="a2d8e-126">Dans le cas contraire, le déploiement risque d’échouer.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="a2d8e-127">Votre réseau, notamment les commutateurs et les réseaux locaux virtuels (VLAN), doit être configuré pour prendre en charge PXE.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="a2d8e-128">Pour plus d’informations sur l’assistance IP et la configuration PXE, reportez-vous à la rubrique fournisseur de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="a2d8e-129">Par ailleurs, vous pouvez utiliser un [média amorçable](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) pour vos déploiements si la prise en charge de PXE n’est pas activée.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-129">Alternatively, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn’t enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a2d8e-130">Pour les appareils surface Pro, le démarrage à partir du réseau (démarrage PXE) est uniquement pris en charge lorsque vous utilisez une carte Ethernet ou une station d’accueil de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="a2d8e-131">Les cartes Ethernet tierces ne prennent pas en charge le démarrage PXE avec surface Pro.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-131">Third-party Ethernet adapters don’t support PXE boot with Surface Pro.</span></span> <span data-ttu-id="a2d8e-132">Pour plus d’informations, reportez-vous à la rubrique [cartes Ethernet et déploiement de surface](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) .</span><span class="sxs-lookup"><span data-stu-id="a2d8e-132">See [Ethernet adapters and Surface deployment](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="a2d8e-133">Configurer System Center Configuration Manager pour le déploiement du système d’exploitation</span><span class="sxs-lookup"><span data-stu-id="a2d8e-133">Configure System Center Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="a2d8e-134">Cet article part du principe que vous disposez déjà d’un déploiement de System Center Configuration Manager correct et que vous n’avez pas d’informations détaillées sur les étapes nécessaires au déploiement et à la configuration de Configuration Manager à partir de zéro.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-134">This article assumes you already have a healthy System Center Configuration Manager deployment, and doesn’t detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="a2d8e-135">La [documentation et les instructions de configuration](https://docs.microsoft.com/sccm/) de System Center Configuration Manager constituent une formidable ressource. Nous vous recommandons de commencer avec ces ressources si vous n’avez pas encore déployé Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-135">The [documentation and the configuration guidance](https://docs.microsoft.com/sccm/) on the System Center Configuration Manager is a great resource; we recommend you start with these resources if you haven’t yet deployed Configuration Manager.</span></span>

<span data-ttu-id="a2d8e-136">Utilisez les instructions suivantes pour vérifier que les fonctionnalités de déploiement du système d’exploitation sont correctement configurées.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="a2d8e-137">Valider et mettre à niveau le gestionnaire de configuration</span><span class="sxs-lookup"><span data-stu-id="a2d8e-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="a2d8e-138">Dans la console Configuration Manager, accédez à \*\*\*\* \> **mises à jour d’administration et service de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="a2d8e-139">Recherchez les mises à jour installées et applicables qui n’ont pas encore été installées.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-139">Check the installed build and applicable updates that haven’t been installed yet.</span></span>

3.  <span data-ttu-id="a2d8e-140">Consultez la [prise en charge de Windows 10 dans System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client). Si vous devez mettre à niveau votre déploiement, sélectionnez la mise à jour que vous voulez installer, puis sélectionnez **Télécharger**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-140">Review [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="a2d8e-141">Une fois le téléchargement terminé, sélectionnez la mise à jour, puis cliquez sur **installer le Pack de mise à jour**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="a2d8e-142">Configurer les points de distribution pour la prise en charge de PXE et de la multidiffusion</span><span class="sxs-lookup"><span data-stu-id="a2d8e-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="a2d8e-143">Dans la console Configuration Manager, accédez à \*\*\*\* \> **points de distribution**d’administration.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="a2d8e-144">Sélectionnez le serveur de point de distribution qui servira le déploiement de Microsoft Teams, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="a2d8e-145">Sélectionnez l’onglet **PXE** et assurez-vous que les paramètres suivants sont activés :</span><span class="sxs-lookup"><span data-stu-id="a2d8e-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="a2d8e-146">Activer la prise en charge PXE pour les clients</span><span class="sxs-lookup"><span data-stu-id="a2d8e-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="a2d8e-147">Autoriser ce point de distribution à répondre aux demandes PXE entrantes</span><span class="sxs-lookup"><span data-stu-id="a2d8e-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="a2d8e-148">Activer la prise en charge d’ordinateurs non connus</span><span class="sxs-lookup"><span data-stu-id="a2d8e-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="a2d8e-149">*Facultatif :* Pour activer la prise en charge de la multidiffusion, sélectionnez l’onglet **multidiffusion** et assurez-vous que les paramètres suivants sont activés :</span><span class="sxs-lookup"><span data-stu-id="a2d8e-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="a2d8e-150">Autoriser la multidiffusion à envoyer des données simultanément à plusieurs clients</span><span class="sxs-lookup"><span data-stu-id="a2d8e-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="a2d8e-151">Configurer la plage de ports UDP conformément aux recommandations de votre équipe réseau</span><span class="sxs-lookup"><span data-stu-id="a2d8e-151">Configure the UDP port range as per your network team’s recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="a2d8e-152">Configurer le compte d’accès au réseau</span><span class="sxs-lookup"><span data-stu-id="a2d8e-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="a2d8e-153">Dans la console Configuration Manager, accédez à **sites**d' **administration** \> de **configuration** \> de site, puis sélectionnez le site.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="a2d8e-154">Dans le groupe **paramètres** , sélectionnez **configurer les composants** \> de site **distribution de logiciels**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="a2d8e-155">Sélectionnez l’onglet **compte d’accès au réseau** . Configurez un ou plusieurs comptes, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="a2d8e-156">Les comptes n’ont pas besoin de droits spéciaux, à l’exception de l' **accès à cet ordinateur à partir du réseau** , directement sur le serveur du point de distribution.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-156">The accounts don’t need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="a2d8e-157">Un compte d’utilisateur de domaine générique est approprié.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="a2d8e-158">Pour plus d’informations, voir [gérer les comptes pour accéder au contenu dans System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="a2d8e-158">For more information, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="a2d8e-159">Configurer une image de démarrage</span><span class="sxs-lookup"><span data-stu-id="a2d8e-159">Configure a boot image</span></span>

1.  <span data-ttu-id="a2d8e-160">Dans la console Configuration Manager, accédez à l' **image de démarrage**du **système** \> d’exploitation de la **bibliothèque** \> logiciel.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="a2d8e-161">Sélectionnez **image de démarrage (x64)**, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="a2d8e-162">Sélectionnez l’onglet **source de données** , puis activez l’option **déploiement de cette image de démarrage à partir du point de distribution PXE**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="a2d8e-163">Sélectionnez l’onglet **composants facultatifs** pour installer les composants nécessaires :</span><span class="sxs-lookup"><span data-stu-id="a2d8e-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="a2d8e-164">Sélectionner l’icône d’étoile et rechercher du **code html (WinPE-HTA)**</span><span class="sxs-lookup"><span data-stu-id="a2d8e-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="a2d8e-165">Sélectionnez **OK** pour ajouter la prise en charge de l’application HTML dans l’image de démarrage.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="a2d8e-166">*Facultatif :* Pour personnaliser l’interface de déploiement, sélectionnez l’onglet de **personnalisation** .</span><span class="sxs-lookup"><span data-stu-id="a2d8e-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="a2d8e-167">Activez le **support des commandes (tests uniquement)** si vous souhaitez accéder à une invite de commandes pendant le déploiement.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="a2d8e-168">Lorsque cette option est activée, vous pouvez démarrer une invite de commandes en sélectionnant **F8** à tout moment pendant le déploiement.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="a2d8e-169">Vous pouvez également spécifier une image d’arrière-plan personnalisée à afficher lors du déploiement.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="a2d8e-170">Pour définir une image, activez **l’option spécifier le fichier d’image d’arrière-plan personnalisé (chemin d’accès UNC** ), puis sélectionnez l’arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="a2d8e-171">Lorsque vous y êtes invité, sélectionnez **Oui** et distribuez l’image de démarrage mise à jour aux points de distribution.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="a2d8e-172">Pour plus d’informations, voir [gérer les images de démarrage à l’aide de System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span><span class="sxs-lookup"><span data-stu-id="a2d8e-172">For more information, see [Manage boot images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="a2d8e-173">Vous pouvez créer un média USB amorçable pour lancer des déploiements de séquence de tâches de Configuration Manager pour les environnements n’ayant pas de prise en charge PXE.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="a2d8e-174">Le média amorçable contient uniquement l’image de démarrage, les commandes de prédémarrage facultatives et les fichiers requis, ainsi que les fichiers binaires de configuration pour la prise en charge du démarrage dans Windows PE et la connexion à Configuration Manager pour le reste du processus de déploiement.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="a2d8e-175">Pour plus d’informations, reportez-vous [à la rubrique Création d’un média amorçable](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span><span class="sxs-lookup"><span data-stu-id="a2d8e-175">For more information, see [How to Create Bootable Media](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="a2d8e-176">Créer des packages de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a2d8e-176">Create Configuration Manager packages</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a2d8e-177">La version de système d’exploitation requise pour chaque version du programme d’installation de SRS change avec chaque version MSI.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-177">The required operating system version for each SRS installer version changes with every MSI release.</span></span> <span data-ttu-id="a2d8e-178">Pour déterminer la meilleure version du système d’exploitation pour un fichier MSI donné, exécutez le script de configuration de la console une seule fois.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-178">To determine the best operating system version for a given MSI, run the console setup script once.</span></span> <span data-ttu-id="a2d8e-179">Pour plus d’informations, reportez-vous à la rubrique [déploiement de salles Microsoft teams à l’aide de System Center Configuration Manager](room-systems-scale.md).</span><span class="sxs-lookup"><span data-stu-id="a2d8e-179">To learn more, see [Deploy Microsoft Teams Rooms by using System Center Configuration Manager](room-systems-scale.md).</span></span>

<span data-ttu-id="a2d8e-180">Configuration Manager nécessite un certain nombre de packages pour déployer et configurer les unités de salles de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-180">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="a2d8e-181">Vous avez besoin de créer et de configurer les packages suivants, puis de les distribuer sur les systèmes de site de Configuration Manager ayant reçu le rôle serveur de point de distribution.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-181">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="a2d8e-182">**Nom du package**</span><span class="sxs-lookup"><span data-stu-id="a2d8e-182">**Package name**</span></span>                     | <span data-ttu-id="a2d8e-183">**Type**</span><span class="sxs-lookup"><span data-stu-id="a2d8e-183">**Type**</span></span>               | <span data-ttu-id="a2d8e-184">**Description**</span><span class="sxs-lookup"><span data-stu-id="a2d8e-184">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="a2d8e-185">SRS v2-package d’application SRS</span><span class="sxs-lookup"><span data-stu-id="a2d8e-185">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="a2d8e-186">Package logiciel</span><span class="sxs-lookup"><span data-stu-id="a2d8e-186">Software package</span></span>       | <span data-ttu-id="a2d8e-187">Package pour le kit de déploiement de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="a2d8e-187">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="a2d8e-188">SRS v2-package Sysprep</span><span class="sxs-lookup"><span data-stu-id="a2d8e-188">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="a2d8e-189">Package logiciel</span><span class="sxs-lookup"><span data-stu-id="a2d8e-189">Software package</span></span>       | <span data-ttu-id="a2d8e-190">Package pour le fichier Unattended. XML de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="a2d8e-190">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="a2d8e-191">SRS v2-Set-package SRSComputerName</span><span class="sxs-lookup"><span data-stu-id="a2d8e-191">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="a2d8e-192">Package logiciel</span><span class="sxs-lookup"><span data-stu-id="a2d8e-192">Software package</span></span>       | <span data-ttu-id="a2d8e-193">Package pour l’application HTML (HTA) permettant d’affecter un nom d’ordinateur lors du déploiement</span><span class="sxs-lookup"><span data-stu-id="a2d8e-193">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="a2d8e-194">SRS v2-configurer le programme de configuration de SRS</span><span class="sxs-lookup"><span data-stu-id="a2d8e-194">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="a2d8e-195">Package logiciel</span><span class="sxs-lookup"><span data-stu-id="a2d8e-195">Software package</span></span>       | <span data-ttu-id="a2d8e-196">Package permettant de configurer le déploiement de l’application Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="a2d8e-196">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="a2d8e-197">Package de mise à jour de SRS v2-OS</span><span class="sxs-lookup"><span data-stu-id="a2d8e-197">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="a2d8e-198">Package logiciel</span><span class="sxs-lookup"><span data-stu-id="a2d8e-198">Software package</span></span>       | <span data-ttu-id="a2d8e-199">Package de déploiement des mises à jour de systèmes d’exploitation obligatoires</span><span class="sxs-lookup"><span data-stu-id="a2d8e-199">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="a2d8e-200">SRS v2-package de certificats racines</span><span class="sxs-lookup"><span data-stu-id="a2d8e-200">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="a2d8e-201">Package logiciel</span><span class="sxs-lookup"><span data-stu-id="a2d8e-201">Software package</span></span>       | <span data-ttu-id="a2d8e-202">Package facultatif pour le déploiement du certificat racine (non requis pour les unités jointes au domaine)</span><span class="sxs-lookup"><span data-stu-id="a2d8e-202">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="a2d8e-203">SRS v2-package de l’agent de surveillance Microsoft</span><span class="sxs-lookup"><span data-stu-id="a2d8e-203">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="a2d8e-204">Package logiciel</span><span class="sxs-lookup"><span data-stu-id="a2d8e-204">Software package</span></span>       | <span data-ttu-id="a2d8e-205">Package facultatif pour le déploiement et la configuration de l’agent Microsoft Operations Management Suite</span><span class="sxs-lookup"><span data-stu-id="a2d8e-205">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="a2d8e-206">SRS v2-package d’arrière-plan WinPE</span><span class="sxs-lookup"><span data-stu-id="a2d8e-206">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="a2d8e-207">Package logiciel</span><span class="sxs-lookup"><span data-stu-id="a2d8e-207">Software package</span></span>       | <span data-ttu-id="a2d8e-208">Package de l’image d’arrière-plan personnalisée à utiliser avec les images de démarrage</span><span class="sxs-lookup"><span data-stu-id="a2d8e-208">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="a2d8e-209">Windows 10 entreprise</span><span class="sxs-lookup"><span data-stu-id="a2d8e-209">Windows 10 Enterprise</span></span>                | <span data-ttu-id="a2d8e-210">Image de système d’exploitation</span><span class="sxs-lookup"><span data-stu-id="a2d8e-210">Operating system image</span></span> | <span data-ttu-id="a2d8e-211">Package du fichier d’installation du système d’exploitation (Install. wim)</span><span class="sxs-lookup"><span data-stu-id="a2d8e-211">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="a2d8e-212">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="a2d8e-212">Surface Pro</span></span>                          | <span data-ttu-id="a2d8e-213">Package de pilotes</span><span class="sxs-lookup"><span data-stu-id="a2d8e-213">Driver package</span></span>         | <span data-ttu-id="a2d8e-214">Package pour les pilotes de périphériques et le microprogramme pour Microsoft surface Pro</span><span class="sxs-lookup"><span data-stu-id="a2d8e-214">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="a2d8e-215">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="a2d8e-215">Surface Pro 4</span></span>                        | <span data-ttu-id="a2d8e-216">Package de pilotes</span><span class="sxs-lookup"><span data-stu-id="a2d8e-216">Driver package</span></span>         | <span data-ttu-id="a2d8e-217">Package pour les pilotes de périphériques et le microprogramme pour Microsoft surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="a2d8e-217">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="a2d8e-218">Pour plus d’informations, voir [packages et programmes dans System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="a2d8e-218">For more information, see [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="a2d8e-219">Créer des dossiers pour les fichiers source du package</span><span class="sxs-lookup"><span data-stu-id="a2d8e-219">Create folders for the package source files</span></span>

<span data-ttu-id="a2d8e-220">Configuration Manager exige que les fichiers sources du package soient organisés dans une structure de dossiers spécifique lors de leur création initiale et de leur mise à jour.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-220">Configuration Manager requires package source files to be organized in a specific folder structure when they’re first created and when they’re updated.</span></span>

<span data-ttu-id="a2d8e-221">Créez la structure de dossiers suivante dans le site d’administration centrale de System Center Configuration Manager ou le site principal, ou sur un partage de serveur que vous utilisez pour héberger les fichiers sources du package :</span><span class="sxs-lookup"><span data-stu-id="a2d8e-221">Create the following folder structure on the System Center Configuration Manager central administration site or primary site, or on a server share you’re using to host package source files:</span></span>

-   <span data-ttu-id="a2d8e-222">SRS v2-package de l’agent de surveillance Microsoft</span><span class="sxs-lookup"><span data-stu-id="a2d8e-222">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="a2d8e-223">Package de mise à jour de SRS v2-OS</span><span class="sxs-lookup"><span data-stu-id="a2d8e-223">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="a2d8e-224">SRS v2-package de certificats racines</span><span class="sxs-lookup"><span data-stu-id="a2d8e-224">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="a2d8e-225">SRS v2-Set-package SRSComputerName</span><span class="sxs-lookup"><span data-stu-id="a2d8e-225">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="a2d8e-226">SRS v2-package d’application SRS</span><span class="sxs-lookup"><span data-stu-id="a2d8e-226">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="a2d8e-227">SRS v2-configurer le programme de configuration de SRS</span><span class="sxs-lookup"><span data-stu-id="a2d8e-227">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="a2d8e-228">SRS v2-package Sysprep</span><span class="sxs-lookup"><span data-stu-id="a2d8e-228">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="a2d8e-229">Pilote</span><span class="sxs-lookup"><span data-stu-id="a2d8e-229">Drivers</span></span>
    -   <span data-ttu-id="a2d8e-230">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="a2d8e-230">Surface Pro</span></span>
    -   <span data-ttu-id="a2d8e-231">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="a2d8e-231">Surface Pro 4</span></span>
-   <span data-ttu-id="a2d8e-232">Systèmes d’exploitation</span><span class="sxs-lookup"><span data-stu-id="a2d8e-232">Operating Systems</span></span>
    -   <span data-ttu-id="a2d8e-233">Windows 10 entreprise</span><span class="sxs-lookup"><span data-stu-id="a2d8e-233">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="a2d8e-234">Vous pouvez également [Télécharger](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) et utiliser le fichier zip qui inclut la structure de dossiers des packages, les scripts que vous devez utiliser et le modèle de séquence de tâches que vous devez importer.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-234">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="a2d8e-235">Créer un package d’agent de surveillance</span><span class="sxs-lookup"><span data-stu-id="a2d8e-235">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="a2d8e-236">Téléchargez l’agent de surveillance <https://go.microsoft.com/fwlink/?LinkId=828603>de.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-236">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="a2d8e-237">Extrayez le package dans le dossier **SRS v2-Microsoft Analysis agent** en ouvrant une fenêtre d’invite de commandes et en entrant **MMASetup-amd64. exe/c :** à l’invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-237">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="a2d8e-238">Dans la console Configuration Manager, accédez à **packages**de **gestion** \> des applications de la **bibliothèque** \> de logiciels, puis sélectionnez **créer un package**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-238">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="a2d8e-239">Entrez les informations suivantes pour créer le package :</span><span class="sxs-lookup"><span data-stu-id="a2d8e-239">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="a2d8e-240">Nom<strong>: SRS v2-package de l’agent de surveillance Microsoft</strong></span><span class="sxs-lookup"><span data-stu-id="a2d8e-240">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="a2d8e-241">Fabricant<strong>: Microsoft Corporation</strong></span><span class="sxs-lookup"><span data-stu-id="a2d8e-241">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="a2d8e-242">Version<strong>: 8.1.11081.0</strong> (entrez la version du fichier d’installation téléchargé)</span><span class="sxs-lookup"><span data-stu-id="a2d8e-242">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="a2d8e-243">Cochez la case **ce package contient les fichiers sources** , entrez le chemin d’accès au dossier **SRS v2-Microsoft Monitoring agent** , puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-243">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="a2d8e-244">Sélectionnez **ne pas créer de programme**, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-244">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="a2d8e-245">Examinez la page **confirmez les paramètres** , puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-245">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="a2d8e-246">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-246">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="a2d8e-247">Créer le package mises à jour du système d’exploitation</span><span class="sxs-lookup"><span data-stu-id="a2d8e-247">Create the operating system updates package</span></span>

1. <span data-ttu-id="a2d8e-248">Dans le dossier de **package de mise à jour de SRS v2-OS** , créez un nouveau script PowerShell appelé **install-SRSv2-OS-Updates. ps1**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-248">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="a2d8e-249">Copiez le script ci-dessous dans le script **install-SRSv2-OS-Updates. ps1** .</span><span class="sxs-lookup"><span data-stu-id="a2d8e-249">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="a2d8e-250">Vous pouvez également télécharger le script Install-SRSv2-OS-Updates. ps1 à partir de [cet emplacement](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="a2d8e-250">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```
   # Install-SRSv2-OS-Updates.ps1
   $strPath = split-path -parent $MyInvocation.MyCommand.Definition
   $total = gci $strPath *.msu | measure | Select-Object -expand Count
   $i = 0
   gci $strPath *.msu | ForEach-Object {
     $i++
     WUSA ""$_.FullName /quiet /norestart""
     Write-Progress -activity "Applying Mandatory Updates" -status "Installing
     $_ .. $i of $total" -percentComplete (($i / $total) * 100)
     Wait-Process -name wusa
   }
   ```
3. <span data-ttu-id="a2d8e-251">Téléchargez les packages de mise à jour Windows obligatoires dans le même dossier.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-251">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="a2d8e-252">Au moment de la publication de cet article, seul [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) est requis.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-252">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="a2d8e-253">Cochez [la case configurer une console Microsoft teams](console.md)pour voir si d’autres mises à jour sont requises.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-253">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="a2d8e-254">Dans la console Configuration Manager, accédez à **packages**de **gestion** \> des applications de la **bibliothèque** \> de logiciels, puis sélectionnez **créer un package**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-254">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="a2d8e-255">Entrez les informations suivantes pour créer le package :</span><span class="sxs-lookup"><span data-stu-id="a2d8e-255">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="a2d8e-256">Nom : **SRS v2 – package mises à jour du système d’exploitation**</span><span class="sxs-lookup"><span data-stu-id="a2d8e-256">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="a2d8e-257">Fabricant : **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="a2d8e-257">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="a2d8e-258">Version : **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="a2d8e-258">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="a2d8e-259">Cochez la case **ce package contient les fichiers sources** , entrez le chemin d’accès au dossier des **mises à jour de SRS v2-OS** , puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-259">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="a2d8e-260">Sélectionnez **ne pas créer de programme**, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-260">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="a2d8e-261">Examinez la page **confirmez les paramètres** , puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-261">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="a2d8e-262">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-262">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="a2d8e-263">Créer le package de certificat racine (facultatif)</span><span class="sxs-lookup"><span data-stu-id="a2d8e-263">Create the root certificate package (optional)</span></span>

<span data-ttu-id="a2d8e-264">Vous créez ce package pour distribuer le certificat racine pour les appareils qui ne seront pas joints à un domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-264">You create this package to distribute the root certificate for devices that won’t be joined to an Active Directory domain.</span></span> <span data-ttu-id="a2d8e-265">Créez ce package uniquement si les deux conditions suivantes s’appliquent :</span><span class="sxs-lookup"><span data-stu-id="a2d8e-265">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="a2d8e-266">Votre déploiement inclut Lync local ou Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-266">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="a2d8e-267">Les unités de salles de Microsoft teams sont configurées pour fonctionner au sein d’un groupe de travail au lieu d’un membre du domaine.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-267">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="a2d8e-268">Copiez le certificat racine dans le dossier **SRS v2 – certificat racine** .</span><span class="sxs-lookup"><span data-stu-id="a2d8e-268">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="a2d8e-269">Dans la console Configuration Manager, accédez à **packages**de **gestion** \> des applications de la **bibliothèque** \> de logiciels, puis sélectionnez **créer un package**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-269">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="a2d8e-270">Entrez les informations suivantes pour créer le package :</span><span class="sxs-lookup"><span data-stu-id="a2d8e-270">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="a2d8e-271">Nom : **SRS v2-package de certificat racine**</span><span class="sxs-lookup"><span data-stu-id="a2d8e-271">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="a2d8e-272">Fabricant : *nom de votre organisation*</span><span class="sxs-lookup"><span data-stu-id="a2d8e-272">Manufacturer: *Your organization’s name*</span></span>
    -   <span data-ttu-id="a2d8e-273">Version : **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="a2d8e-273">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="a2d8e-274">Activez la case à cocher **ce package contient les fichiers sources** , entrez le chemin d’accès du dossier **SRS v2 – certificat racine du package** , puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-274">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="a2d8e-275">Sélectionnez **ne pas créer de programme**, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-275">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="a2d8e-276">Examinez la page **confirmez les paramètres** , puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-276">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="a2d8e-277">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-277">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="a2d8e-278">Créer le package du kit de déploiement de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="a2d8e-278">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="a2d8e-279">Téléchargez la version la plus récente du **Kit de déploiement de Microsoft teams** <https://go.microsoft.com/fwlink/?linkid=851168>, puis installez-la sur une station de travail.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-279">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="a2d8e-280">Copiez le contenu de **C\\: Program Files (x86\\) Skype Room System Deployment Kit** vers le dossier **SRS v2-package d’application SRS** .</span><span class="sxs-lookup"><span data-stu-id="a2d8e-280">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="a2d8e-281">Dans la console Configuration Manager, accédez à **packages**de **gestion** \> des applications de la **bibliothèque** \> de logiciels, puis sélectionnez **créer un package**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-281">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="a2d8e-282">Entrez les informations suivantes pour créer le package :</span><span class="sxs-lookup"><span data-stu-id="a2d8e-282">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="a2d8e-283">Nom : **SRS v2-package d’application SRS**</span><span class="sxs-lookup"><span data-stu-id="a2d8e-283">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="a2d8e-284">Fabricant : **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="a2d8e-284">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="a2d8e-285">Version : **3.1.104.0** (entrez la version du fichier d’installation téléchargé)</span><span class="sxs-lookup"><span data-stu-id="a2d8e-285">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="a2d8e-286">Cochez la case **ce package contient les fichiers sources** , entrez le chemin d’accès au dossier **SRS v2 – package d’application SRS** , puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-286">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="a2d8e-287">Sélectionnez **ne pas créer de programme**, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-287">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="a2d8e-288">Examinez la page **confirmez les paramètres** , puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-288">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="a2d8e-289">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-289">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="a2d8e-290">Créer le package d’attribution de nom d’ordinateur</span><span class="sxs-lookup"><span data-stu-id="a2d8e-290">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="a2d8e-291">Dans le dossier **SRS v2-Set-SRSComputerName package** , créez une nouvelle application HTML nommée **Set-SRSComputerName. hta** .</span><span class="sxs-lookup"><span data-stu-id="a2d8e-291">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="a2d8e-292">Copiez le script suivant dans le fichier **Set-SRSComputerName. hta** .</span><span class="sxs-lookup"><span data-stu-id="a2d8e-292">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="a2d8e-293">Vous pouvez également télécharger le fichier Set-SRSComputerName. hta à partir de [cet emplacement](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="a2d8e-293">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
    ```
    <!DOCTYPE HTML>
    <html>
    <head>
    <title>Set SRS Computer Name</title>
    <HTA:APPLICATION
      APPLICATIONNAME="Set SRS Computer Name"
      ID="SetSRSComputerName"
      VERSION="1.0"
      SCROLL="no"
      SINGLEINSTANCE="yes"
      WINDOWSTATE="maximize"
      MaximizeButton="no"
      MinimizeButton="no"
      SysMenu="no"
      ShowInTaskbar="no"
      Caption="no"
      />
    <style type="text/css">
    body {
        background-color: #fdfeff;
        color: darkblue;
        font-family: Calibri;
        font-size: 12pt;
        margin: 4em 3em;
    }
    </style>
    </head>
    <script language="VBScript">
    Public strNewComputerName
    Sub GenerateComputerName()
        strComputer = "."
        Set objWMIService = GetObject("winmgmts:\\" & strComputer & "\root\cimv2")
        Set colItems = objWMIService.ExecQuery("Select * from Win32_BIOS",,48)
        For Each objItem in colItems
            strSerialNumber = objItem.SerialNumber
        Next
        strNewComputerName = "SRS-"  & right(replace(strSerialNumber, "-","") ,10)
        TextArea1.innerHTML = "The serial number of the device: " & strSerialNumber
        strHTMLText = strHTMLText & "<br> Computer name to be assigned: <font color = red>" & strNewComputerName & "</font>"
        strHTMLText = strHTMLText & "<br><br> Click Accept to use this as the computer name and continue deployment, or Change to set a new name."
        strHTMLText = strHTMLText & "<p><input type=""button"" value=""Accept"" name = ""Accept_Button"" onclick=""SetComputerName"" />"
        strHTMLText = strHTMLText & " <input type=""button"" value=""Change"" name = ""Change_Button"" onclick=""ChangeComputerName"" />"
        TextArea2.innerHTML = strHTMLText
    End Sub

    Sub SetComputerName()
        dim result
        result = MsgBox("Computer Name to be assigned: " & strNewComputerName &vbcrlf & "Are you sure you want to continue?", 36)
        If (result = vbYes) then
            SET env = CreateObject("Microsoft.SMS.TSEnvironment")
            env("OSDComputerName") = strNewComputerName
            self.close
        elseif (result = vbNo) then
            Window_OnLoad
        End If
    End Sub

    Sub UpdateComputerName()
        strNewComputerName = newcomputername.value
        if len(trim(strNewComputerName)) = 0 then
            MsgBox "Computer name cannot be empty." &vbcrlf & "Update and try again.",16
            exit sub
        end if
        SetComputerName
    End Sub

    Sub ChangeComputerName()
        TextArea2.innerHTML = "<p>Type the new computer name and click Accept:  <input type=""text"" name=""newcomputername"" value =" & strNewComputerName & " />"
        TextArea2.innerHTML = TextArea2.innerHTML & "<br><input type=""button"" value=""Update"" name = ""Update_Button"" onclick=""UpdateComputerName"" />"
    End Sub

    Sub Window_OnLoad
        Set oTSProgressUI = CreateObject("Microsoft.SMS.TsProgressUI")
        oTSProgressUI.CloseProgressDialog
        GenerateComputerName
    End Sub
    </script>

    <body>
    <span id = "TextArea1"></span>
    <span id = "TextArea2">
    </span>
    </body>
    </html>

    ```
3.  <span data-ttu-id="a2d8e-294">Dans la console Configuration Manager, accédez à **packages**de **gestion** \> des applications de la **bibliothèque** \> de logiciels, puis sélectionnez **créer un package**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-294">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="a2d8e-295">Entrez les informations suivantes pour créer le package :</span><span class="sxs-lookup"><span data-stu-id="a2d8e-295">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="a2d8e-296">Nom : **SRS v2-Set-package SRSComputerName**</span><span class="sxs-lookup"><span data-stu-id="a2d8e-296">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="a2d8e-297">Fabricant : **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="a2d8e-297">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="a2d8e-298">Version : **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="a2d8e-298">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="a2d8e-299">Cochez la case **ce package contient les fichiers sources** , entrez le chemin d’accès au dossier **SRS v2-Set-SRSComputerName package** , puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-299">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="a2d8e-300">Sélectionnez **ne pas créer de programme**, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-300">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="a2d8e-301">Examinez la page **confirmez les paramètres** , puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-301">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="a2d8e-302">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-302">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="a2d8e-303">Créer le package Sysprep</span><span class="sxs-lookup"><span data-stu-id="a2d8e-303">Create the Sysprep package</span></span>

1. <span data-ttu-id="a2d8e-304">Dans le dossier **SRS v2 – package Sysprep** , créez un nouveau fichier XML intitulé **Unattend. xml** .</span><span class="sxs-lookup"><span data-stu-id="a2d8e-304">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="a2d8e-305">Copiez le texte suivant dans le fichier **Unattend. xml** .</span><span class="sxs-lookup"><span data-stu-id="a2d8e-305">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="a2d8e-306">Vous pouvez également télécharger le fichier Unattend. XML à partir de [cet emplacement](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="a2d8e-306">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```
   <?xml version="1.0" encoding="utf-8"?>
   <unattend xmlns="urn:schemas-microsoft-com:unattend">
   <settings pass="specialize">
       <component name="Microsoft-Windows-Embedded-BootExp" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <DisableBootMenu>1</DisableBootMenu>
           <DisplayDisabled>1</DisplayDisabled>
       </component>
       <component name="Microsoft-Windows-powercpl" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <PreferredPlan>8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c</PreferredPlan>
       </component>
   </settings>
   <settings pass="oobeSystem">
       <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <OOBE>
               <HideEULAPage>true</HideEULAPage>
               <HideLocalAccountScreen>true</HideLocalAccountScreen>
               <HideOEMRegistrationScreen>true</HideOEMRegistrationScreen>
               <HideOnlineAccountScreens>true</HideOnlineAccountScreens>
               <HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>
               <SkipMachineOOBE>true</SkipMachineOOBE>
               <SkipUserOOBE>true</SkipUserOOBE>
               <ProtectYourPC>1</ProtectYourPC>
           </OOBE>
           <AutoLogon>
               <Enabled>true</Enabled>
               <Username>Skype</Username>
               <Password>
                   <Value>UABhAHMAcwB3AG8AcgBkAA==</Value>
                   <PlainText>false</PlainText>
               </Password>
           </AutoLogon>
           <UserAccounts>
               <LocalAccounts>
                   <LocalAccount wcm:action="add">
                       <Password>
                           <Value>cwBmAGIAUABhAHMAcwB3AG8AcgBkAA==</Value>
                           <PlainText>false</PlainText>
                       </Password>
                       <Name>Admin</Name>
                       <Group>Administrators</Group>
                       <DisplayName>Administrator</DisplayName>
                       <Description>Administrator</Description>
                   </LocalAccount>
               </LocalAccounts>
           </UserAccounts>
       </component>
   </settings>
   <cpi:offlineImage cpi:source="wim:h:/install.wim#Windows 10 Enterprise" xmlns:cpi="urn:schemas-microsoft-com:cpi" />
   </unattend>
   ```
3. <span data-ttu-id="a2d8e-307">Dans la console Configuration Manager, accédez à **packages**de **gestion** \> des applications de la **bibliothèque** \> de logiciels, puis sélectionnez **créer un package**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-307">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="a2d8e-308">Entrez les informations suivantes pour créer le package :</span><span class="sxs-lookup"><span data-stu-id="a2d8e-308">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="a2d8e-309">Nom : **SRS v2-package Sysprep**</span><span class="sxs-lookup"><span data-stu-id="a2d8e-309">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="a2d8e-310">Fabricant : **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="a2d8e-310">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="a2d8e-311">Version : **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="a2d8e-311">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="a2d8e-312">Cochez la case **ce package contient les fichiers sources** , entrez le chemin d’accès au dossier **SRS v2 – package Sysprep** , puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-312">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="a2d8e-313">Sélectionnez **ne pas créer de programme**, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-313">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="a2d8e-314">Examinez la page **confirmez les paramètres** , puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-314">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="a2d8e-315">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-315">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="a2d8e-316">Créer le package Windows 10 entreprise</span><span class="sxs-lookup"><span data-stu-id="a2d8e-316">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="a2d8e-317">Obtenez un média Windows 10 entreprise x64 et copiez le fichier **install. wim** dans le dossier **systèmes\\d’exploitation Windows 10 entreprise** .</span><span class="sxs-lookup"><span data-stu-id="a2d8e-317">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="a2d8e-318">Dans la console Configuration Manager, accédez à l’image **systèmes** \> **d’exploitation des**systèmes d’exploitation de la **bibliothèque** \> de logiciels, puis sélectionnez **Ajouter une image de système d’exploitation**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-318">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="a2d8e-319">Spécifiez le chemin d’accès du fichier d' **installation. wim** que vous venez de copier, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-319">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="a2d8e-320">Mettez à jour le champ **version** pour correspondre au numéro de build de l’image Windows 10 entreprise, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-320">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="a2d8e-321">Examinez la page des **Détails** , puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-321">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="a2d8e-322">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-322">Select **Close**.</span></span>

<span data-ttu-id="a2d8e-323">Pour plus d’informations, voir [gérer les images du système d’exploitation à l’aide de System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span><span class="sxs-lookup"><span data-stu-id="a2d8e-323">For more information, see [Manage operating system images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="a2d8e-324">Créer des packages de pilotes de périphériques de surface Pro</span><span class="sxs-lookup"><span data-stu-id="a2d8e-324">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="a2d8e-325">Les salles de Microsoft teams sont prises en charge pour surface Pro et surface Pro 4.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-325">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="a2d8e-326">Vous devez créer un package de pilotes pour chaque modèle surface Pro dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-326">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a2d8e-327">Les pilotes doivent être compatibles avec la version de Windows 10 entreprise et celle du kit de déploiement de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-327">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="a2d8e-328">Pour plus d’informations, reportez-vous à [la rubrique Télécharger le microprogramme et pilotes les plus récents pour les appareils surface](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) et [configurer une console](console.md).</span><span class="sxs-lookup"><span data-stu-id="a2d8e-328">For more information, see [Download the latest firmware and drivers for Surface devices](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="a2d8e-329">Téléchargez les derniers pilotes et microprogrammes.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-329">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="a2d8e-330">Pour surface Pro :<https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="a2d8e-330">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="a2d8e-331">Pour surface Pro 4 :<https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="a2d8e-331">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="a2d8e-332">Extrayez le pilote et le microprogramme téléchargés.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-332">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="a2d8e-333">Ouvrez une fenêtre d’invite de commandes, puis à l’invite de commandes, entrez l’une des commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="a2d8e-333">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="a2d8e-334">Dans la console Configuration Manager, sélectionnez \> **pilotes**de **systèmes d’exploitation** de la **bibliothèque** \> de logiciels, puis **importer le pilote**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-334">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="a2d8e-335">Sélectionnez **Importer tous les pilotes dans le chemin réseau suivant (UNC)**, sélectionnez le dossier source (par exemple, C\\:\\_Sources\\pilotes surface Pro), puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-335">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="a2d8e-336">Dans la page **spécifier les détails pour les pilotes importés** , sélectionnez tous les pilotes répertoriés, puis sélectionnez **activer ces pilotes et autoriser les ordinateurs à les installer**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-336">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="a2d8e-337">Sélectionnez **catégories**, créez une nouvelle catégorie qui correspond au modèle de surface, sélectionnez **OK**, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-337">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="a2d8e-338">Sélectionnez **nouveau package**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-338">Select **New Package**.</span></span>

8.  <span data-ttu-id="a2d8e-339">Spécifiez le nom du package qui correspond au modèle surface Pro, entrez le chemin d’accès du dossier dans lequel vous souhaitez stocker les fichiers du package de pilotes, sélectionnez **OK**, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-339">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="a2d8e-340">Dans la page **images de démarrage** , assurez-vous qu’aucune image de démarrage n’est sélectionnée, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-340">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="a2d8e-341">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-341">Select **Close**.</span></span>

11. <span data-ttu-id="a2d8e-342">Accédez à \*\*\*\* \> **pilotes**de \> **systèmes d’exploitation** des bibliothèques de logiciels, sélectionnez \*\* \> créer un dossier\*\*, puis entrez le nom du dossier qui correspond au modèle surface Pro pour lequel vous venez d’importer les pilotes.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-342">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="a2d8e-343">Déplacez tous les pilotes importés dans le dossier nouvellement créé pour faciliter la navigation et l’utilisation.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-343">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="a2d8e-344">Répétez ces étapes pour les autres modèles surface Pro que vous avez peut-être.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-344">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="a2d8e-345">Pour plus d’informations, voir [gérer les pilotes dans System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span><span class="sxs-lookup"><span data-stu-id="a2d8e-345">For more information, see [Manage drivers in System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="a2d8e-346">Créer un package de configuration de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="a2d8e-346">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="a2d8e-347">Dans la console Configuration Manager, accédez à **packages**de **gestion** \> des applications de la **bibliothèque** \> de logiciels, puis sélectionnez **créer un package**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-347">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="a2d8e-348">Entrez les informations suivantes pour créer le package :</span><span class="sxs-lookup"><span data-stu-id="a2d8e-348">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="a2d8e-349">Nom : **SRS v2-configurer le package d’installation de SRS**</span><span class="sxs-lookup"><span data-stu-id="a2d8e-349">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="a2d8e-350">Fabricant : **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="a2d8e-350">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="a2d8e-351">Version : **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="a2d8e-351">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="a2d8e-352">Cochez la case **ce package contient les fichiers sources** , entrez le chemin d’accès au **service SRS v2-configurer le dossier d’installation de SRS** , puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-352">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="a2d8e-353">Sélectionnez **ne pas créer de programme**, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-353">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="a2d8e-354">Examinez la page **confirmez les paramètres** , puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-354">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="a2d8e-355">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-355">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="a2d8e-356">Distribuer des packages de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a2d8e-356">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="a2d8e-357">Tous les packages doivent être distribués aux serveurs auxquels le rôle de point de distribution a été attribué dans la hiérarchie du gestionnaire de configuration.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-357">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="a2d8e-358">Suivez les instructions ci-dessous pour lancer la distribution de package.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-358">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="a2d8e-359">Distribution des packages de logiciels.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-359">Distribute software packages.</span></span>

    1.  <span data-ttu-id="a2d8e-360">Dans la console Configuration Manager, accédez à **packages**de **gestion** \> des applications de la **bibliothèque** \> de logiciels.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-360">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="a2d8e-361">Sélectionnez tous les packages de logiciels que vous souhaitez distribuer, puis sélectionnez **distribuer le contenu**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-361">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="a2d8e-362">Examinez la liste des packages, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-362">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="a2d8e-363">Ajoutez tous les serveurs de points de distribution (ou groupes de points de distribution, en fonction de votre hiérarchie du gestionnaire de configuration) à la liste, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-363">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="a2d8e-364">Sélectionnez **suivant**, puis sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-364">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="a2d8e-365">Distribuer des packages de pilotes ;</span><span class="sxs-lookup"><span data-stu-id="a2d8e-365">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="a2d8e-366">Dans la console Configuration Manager, accédez à **packages de pilotes**de **systèmes** \> d’exploitation des **bibliothèques** \> de logiciels.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-366">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="a2d8e-367">Sélectionnez tous les packages de pilotes que vous souhaitez distribuer, puis sélectionnez **distribuer le contenu**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-367">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="a2d8e-368">Examinez la liste des packages, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-368">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="a2d8e-369">Ajoutez tous les serveurs de points de distribution (ou groupes de points de distribution, en fonction de votre hiérarchie du gestionnaire de configuration) à la liste, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-369">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="a2d8e-370">Sélectionnez **suivant**, puis sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-370">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="a2d8e-371">Distribuer des packages de système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-371">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="a2d8e-372">Dans la console Configuration Manager, accédez à l' **image**des systèmes d’exploitation des \> **systèmes** \> d’exploitation de la **bibliothèque logicielle** .</span><span class="sxs-lookup"><span data-stu-id="a2d8e-372">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="a2d8e-373">Sélectionnez toutes les images de système d’exploitation que vous souhaitez distribuer, puis sélectionnez **distribuer le contenu**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-373">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="a2d8e-374">Examinez la liste des packages, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-374">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="a2d8e-375">Ajoutez tous les serveurs de points de distribution (ou groupes de points de distribution, en fonction de votre hiérarchie du gestionnaire de configuration) à la liste, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-375">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="a2d8e-376">Sélectionnez **suivant**, puis sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-376">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="a2d8e-377">La distribution de package peut prendre un certain temps en fonction de la taille du package, de la hiérarchie de Configuration Manager, du nombre de serveurs de points de distribution et de la bande passante disponible dans votre réseau.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-377">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="a2d8e-378">Pour pouvoir commencer le déploiement d’une unité de Microsoft Teams, tous les packages doivent être distribués.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-378">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="a2d8e-379">Vous pouvez consulter l’état de la distribution de votre package dans la console Configuration Manager en accédant à **surveiller** \> l' **État du contenu**de l’état \> de **distribution** .</span><span class="sxs-lookup"><span data-stu-id="a2d8e-379">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="a2d8e-380">Séquences de tâches de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a2d8e-380">Configuration Manager task sequences</span></span>

<span data-ttu-id="a2d8e-381">Vous utilisez les séquences de tâches avec System Center Configuration Manager pour automatiser les étapes de déploiement d’une image de système d’exploitation sur un ordinateur de destination.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-381">You use task sequences with System Center Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="a2d8e-382">Pour déployer une unité de salle Microsoft teams de manière automatisée, vous devez créer une séquence de tâches qui fait référence à l’image de démarrage utilisée pour démarrer l’ordinateur de destination Microsoft Teams, l’image du système d’exploitation Windows 10 entreprise que vous voulez installer, et les autres autres contenus supplémentaires, tels que d’autres applications ou mises à jour logicielles.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-382">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="a2d8e-383">Importer la séquence de tâches d’exemple</span><span class="sxs-lookup"><span data-stu-id="a2d8e-383">Import the sample task sequence</span></span>

<span data-ttu-id="a2d8e-384">Vous pouvez télécharger et importer facilement un exemple de séquence de tâches et le personnaliser en fonction de vos besoins.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-384">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="a2d8e-385">[**Téléchargez**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) l’exemple de séquence de tâches et copiez le fichier zip téléchargé dans un emplacement partagé.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-385">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="a2d8e-386">Dans la console Configuration Manager, sélectionnez \> **séquences de tâches**des **systèmes d’exploitation** de la **bibliothèque** \> de logiciels, puis importer la séquence de **tâches**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-386">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="a2d8e-387">Sélectionnez **Parcourir**, accédez à l’emplacement du dossier partagé que vous avez utilisé à l’étape 1, sélectionnez le fichier de **déploiement de Microsoft Teams (en-US). zip** , puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-387">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="a2d8e-388">Définissez **action** sur **créer**, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-388">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="a2d8e-389">Confirmez les paramètres, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-389">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="a2d8e-390">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-390">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="a2d8e-391">Vérifiez que les packages de référence sont correctement liés à chaque étape de séquence de tâches.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-391">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="a2d8e-392">Sélectionnez la séquence de tâches importée, puis sélectionnez **modifier**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-392">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="a2d8e-393">L’éditeur de séquence de tâches s’ouvre et affiche les étapes séquentielles requises pour le déploiement et la configuration d’une unité de salle Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-393">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="a2d8e-394">Parcourez chacune des étapes et effectuez les mises à jour recommandées :</span><span class="sxs-lookup"><span data-stu-id="a2d8e-394">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="a2d8e-395">**Redémarrer dans Windows PE**: cette étape redémarre puis initialise l’ordinateur dans Windows PXE.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-395">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="a2d8e-396">Aucune modification n’est requise pour cette étape.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-396">No changes are required for this step.</span></span>

   2. <span data-ttu-id="a2d8e-397">**Partition Disk 0 – UEFI**: cette étape efface la configuration du disque et crée des partitions en fonction des paramètres configurés.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-397">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="a2d8e-398">Nous vous recommandons de ne pas apporter de modifications à cette étape.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-398">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="a2d8e-399">**Définir le nom de l’ordinateur SRS**: cette étape inclut une application HTML pour fournir une interface utilisateur permettant de définir le nom d’un ordinateur pour l’unité de salle Microsoft teams lors du déploiement.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-399">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="a2d8e-400">Il s’agit d’une étape facultative, mais elle peut uniquement être désactivée si vous souhaitez gérer le nom de l’ordinateur via un autre processus.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-400">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="a2d8e-401">Vérifiez que le package **SRS v2-Set-SRSComputerName** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-401">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="a2d8e-402">Si ce n’est pas le cas, recherchez le package et sélectionnez-le.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-402">If it isn’t, browse to the package and select it.</span></span>

   4. <span data-ttu-id="a2d8e-403">**Appliquer le système d’exploitation**: cette étape spécifie l’image du système d’exploitation à déployer et le fichier de réponses Sysprep sans assistance à utiliser.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-403">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="a2d8e-404">Vérifiez que le fichier d’image du système d’exploitation Windows 10 entreprise approprié est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-404">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="a2d8e-405">Vérifiez que l’option **utiliser un fichier de réponses sans assistance ou Sysprep pour une installation personnalisée** est activée et que le **package SRS v2-Sysprep** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-405">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="a2d8e-406">Assurez-vous également que le **nom de fichier** est défini sur **Unattend. xml**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-406">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="a2d8e-407">**Appliquer les paramètres Windows**: cette étape collecte des informations sur l’installation de Windows.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-407">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="a2d8e-408">Fournir des informations sur les licences et l’inscription, notamment la clé de produit, le mot de passe du compte d’administrateur local et le fuseau horaire (selon vos besoins).</span><span class="sxs-lookup"><span data-stu-id="a2d8e-408">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="a2d8e-409">**Appliquer les paramètres réseau**: cette étape vous permet de spécifier un groupe de travail ou un nom de domaine Active Directory et une unité d’organisation.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-409">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="a2d8e-410">Pour plus d’informations sur les actions recommandées, consultez la rubrique accès au [domaine du système de salle Skype](domain-joining-considerations.md) pour le déploiement d’unités de réunion Microsoft teams en tant que membres d’un domaine Actve</span><span class="sxs-lookup"><span data-stu-id="a2d8e-410">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="a2d8e-411">**Appliquer des axes stratégiques :** Cette étape et ses sous-étapes permettent le déploiement de pilotes de périphériques et de microprogrammes applicables en fonction du modèle de surface Pro que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-411">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="a2d8e-412">Mettez à jour chaque étape pour spécifier le package de pilotes approprié associé au déploiement.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-412">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="a2d8e-413">Chaque package de pilotes est configuré de manière à tirer parti des filtres WMI (Windows Management Instrumentation) pour déployer les pilotes et le microprogramme appropriés en fonction de la marque et du modèle de surface Pro.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-413">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="a2d8e-414">Nous vous recommandons vivement de ne pas modifier la configuration de ces pilotes, sinon le déploiement risque d’échouer.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-414">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="a2d8e-415">**Configurer Windows et Configuration Manager**: cette étape déploie et configure le client Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-415">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="a2d8e-416">Mettez à jour cette étape pour spécifier le package client intégré de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-416">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="a2d8e-417">**Installer le certificat racine**: cette étape distribue le certificat racine pour les appareils non joints au domaine et est par conséquent facultatif et désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-417">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="a2d8e-418">Activez cette étape si vous avez besoin de déployer un certificat racine vers les unités de salles de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-418">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="a2d8e-419">Si vous n’avez pas besoin d’effectuer cette étape, vérifiez que le **package SRS (SRS)** 64 et la **redirection** de votre système de fichiers sont sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-419">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="a2d8e-420">**Installer et configurer l’agent de surveillance**: cette étape installe la version 64 bits de l’agent de suivi Microsoft Azure et configure l’agent pour la connexion à votre espace de travail d’analyse du journal.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-420">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="a2d8e-421">Cette étape est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-421">This step is disabled by default.</span></span> <span data-ttu-id="a2d8e-422">Activez cette étape uniquement si vous envisagez d’utiliser l’agent de surveillance pour contrôler l’état de vos unités de salle Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-422">Enable this step only if you’re going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="a2d8e-423">Modifiez cette étape et mettez à jour les paramètres de ligne de commande pour spécifier votre **ID d’espace de travail** et votre **espace de travail**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-423">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="a2d8e-424">Pour plus d’informations sur l’obtention de l’ID d’espace de travail de la suite de gestion des opérations et de la clé primaire, voir [configurer des périphériques de test pour la surveillance Azure](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) .</span><span class="sxs-lookup"><span data-stu-id="a2d8e-424">See [Configure test devices for Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="a2d8e-425">Assurez-vous que le **service SRS v2 – Microsoft Analysis agent** et **désactivez la redirection de système de fichiers 64 bits** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-425">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="a2d8e-426">Pour plus d’informations sur la surveillance de l’état du déploiement de Microsoft Teams, reportez-vous à la rubrique planification de la [gestion des salles de Microsoft teams avec](azure-monitor-plan.md)Azure Monitor, déploiement de la [gestion des salles de Microsoft teams avec Azure Monitor](azure-monitor-deploy.md) et [gestion des appareils Microsoft teams avec Azure Monitor](azure-monitor-manage.md).</span><span class="sxs-lookup"><span data-stu-id="a2d8e-426">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span>

   11. <span data-ttu-id="a2d8e-427">**Copier les fichiers de configuration de SRS v2**: cette étape copie les fichiers d’installation et de configuration requis du kit de déploiement de Microsoft teams sur le disque dur local.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-427">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="a2d8e-428">Aucune personnalisation n’est requise pour cette étape.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-428">No customization is required for this step.</span></span>
       -   <span data-ttu-id="a2d8e-429">Vérifiez que le **package d’application SRS pour le service SRS** et la **désactivation de la redirection de système de fichiers 64 bits** sont sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-429">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="a2d8e-430">**Installation-SRSv2-OS-mises à jour**: cette étape déploie toutes les mises à jour de système d’exploitation obligatoires requises avec le déploiement de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-430">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="a2d8e-431">Procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a2d8e-431">Do the following:</span></span>
       -   <span data-ttu-id="a2d8e-432">Cochez [la case configurer une console de salle Microsoft teams](console.md) pour afficher les mises à jour nécessaires.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-432">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="a2d8e-433">Vérifiez que le **package de mise à jour de SRS v2 –** y compris toutes les mises à jour requises.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-433">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="a2d8e-434">Vérifiez que le **package SRS v2 – mises à jour du système d’exploitation** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-434">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="a2d8e-435">Vérifiez que la stratégie d’exécution PowerShell est définie sur **Bypass**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-435">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="a2d8e-436">**Redémarrer l’ordinateur**: cette étape redémarre l’ordinateur après l’installation des mises à jour de système d’exploitation obligatoires.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-436">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="a2d8e-437">Aucune personnalisation n’est requise pour cette étape.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-437">No customization is required for this step.</span></span>

   14. <span data-ttu-id="a2d8e-438">**Configurer les composants Windows**: cette étape configure les fonctionnalités Windows requises.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-438">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="a2d8e-439">Aucune personnalisation n’est requise pour cette étape.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-439">No customization is required for this step.</span></span>

   15. <span data-ttu-id="a2d8e-440">**Redémarrer l’ordinateur**: cette étape redémarre l’ordinateur une fois les fonctionnalités Windows configurées.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-440">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="a2d8e-441">Aucune personnalisation n’est requise pour cette étape.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-441">No customization is required for this step.</span></span>

   16. <span data-ttu-id="a2d8e-442">**Ajouter un utilisateur Skype local**: cette étape crée le compte Skype local utilisé pour vous connecter automatiquement à Windows et lancer l’application Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-442">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="a2d8e-443">Il n’y a pas de package logiciel associé et aucune personnalisation n’est requise pour cette étape.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-443">This step doesn’t have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="a2d8e-444">**Installer et configurer l’application SRS**: cette étape configure l’installation de l’application Microsoft teams salles pour le prochain démarrage du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-444">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="a2d8e-445">Vérifiez que le **service SRS v2 – configurer le package d’installation SRS** et **désactiver la redirection de système de fichiers 64 bits** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-445">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a2d8e-446">Il est très important que les étapes de la séquence de tâches doivent être dans l’ordre fourni.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-446">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="a2d8e-447">La modification de l’ordre des étapes ou la configuration d’étapes supplémentaires peuvent interrompre le déploiement.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-447">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="a2d8e-448">Configuration **et configuration de l’application SRS** vous devez disposer de la dernière étape de la séquence de tâches, sinon le déploiement risque d’échouer.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-448">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="a2d8e-449">Créer un déploiement pour la séquence de tâches</span><span class="sxs-lookup"><span data-stu-id="a2d8e-449">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="a2d8e-450">Sélectionnez la séquence de tâches, puis **déployer**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-450">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="a2d8e-451">Sélectionnez **Parcourir** pour sélectionner collection cible pour le déploiement.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-451">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="a2d8e-452">Sélectionnez **tous les ordinateurs inconnus** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-452">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="a2d8e-453">Sélectionnez **Next (suivant**).</span><span class="sxs-lookup"><span data-stu-id="a2d8e-453">Select **Next**.</span></span>

5. <span data-ttu-id="a2d8e-454">Sélectionnez **disponible** dans la liste déroulante **objectif** .</span><span class="sxs-lookup"><span data-stu-id="a2d8e-454">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="a2d8e-455">Sélectionnez **uniquement les éléments multimédias et PXE** dans la liste **mettre à disposition de** , puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-455">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="a2d8e-456">Il est très important que l' **objectif** soit défini sur **disponible**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-456">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="a2d8e-457">Assurez-vous que l' **objectif** n’est **pas** défini sur **obligatoire**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-457">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="a2d8e-458">Veillez également à sélectionner **uniquement média et PXE** dans le **rendez-vous disponible pour ce qui suit**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-458">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="a2d8e-459">La définition de ces valeurs sur un autre fichier peut entraîner l’affichage de l’image de déploiement de Microsoft teams sur tous les ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-459">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="a2d8e-460">Ne spécifiez aucun planning et sélectionnez **Next (suivant**).</span><span class="sxs-lookup"><span data-stu-id="a2d8e-460">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="a2d8e-461">Ne modifiez aucune valeur dans la section utilisation de l' **utilisateur** , puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-461">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="a2d8e-462">Ne modifiez aucune valeur dans la section **alertes** et sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-462">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="a2d8e-463">Ne modifiez aucune valeur dans la section **points de distribution** et sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-463">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="a2d8e-464">Confirmez les paramètres, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-464">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="a2d8e-465">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-465">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="a2d8e-466">Valider et dépanner la solution</span><span class="sxs-lookup"><span data-stu-id="a2d8e-466">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="a2d8e-467">Une fois que vous avez terminé les séquences de tâches System Center Configuration Manager, vous devez effectuer une opération de test pour vérifier que la séquence de tâches peut déployer et configurer des unités de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-467">After you’ve completed the System Center Configuration Manager task sequences, you’ll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="a2d8e-468">Connectez l’appareil de test au réseau filaire en utilisant l’une des cartes Ethernet prises en charge ou à l’aide du Dock surface.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-468">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="a2d8e-469">Si la fonctionnalité de démarrage PXE n’a pas été configurée pour votre environnement, vous pouvez utiliser l’image de démarrage sur le lecteur flash USB [que vous avez créé précédemment](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) pour démarrer à partir de la clé USB et vous connecter à Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-469">If PXE boot functionality hasn’t been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="a2d8e-470">Accédez au microprogramme et démarrez un démarrage PXE :</span><span class="sxs-lookup"><span data-stu-id="a2d8e-470">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="a2d8e-471">Assurez-vous que le périphérique surface est éteint.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-471">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="a2d8e-472">Appuyez de façon prolongée sur le bouton **monter le volume** .</span><span class="sxs-lookup"><span data-stu-id="a2d8e-472">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="a2d8e-473">Appuyez et relâchez le bouton **d’alimentation** .</span><span class="sxs-lookup"><span data-stu-id="a2d8e-473">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="a2d8e-474">Après le démarrage de l’appareil, relâchez le bouton **monter le volume** .</span><span class="sxs-lookup"><span data-stu-id="a2d8e-474">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="a2d8e-475">Sélectionnez **configuration de démarrage**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-475">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="a2d8e-476">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="a2d8e-476">Do one of the following:</span></span>

        -   <span data-ttu-id="a2d8e-477">Sélectionnez **démarrage PXE**et faites-le glisser vers le haut de la liste.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-477">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="a2d8e-478">Vous pouvez également effectuer un balayage vers la gauche sur la carte réseau pour démarrer l’appareil immédiatement.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-478">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="a2d8e-479">Cela n’affecte pas l’ordre de démarrage.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-479">This won’t affect the boot order.</span></span>
        -   <span data-ttu-id="a2d8e-480">Sélectionnez le lecteur flash USB qui contient le média de démarrage.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-480">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="a2d8e-481">Sélectionnez **quitter**, puis cliquez sur **redémarrer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-481">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="a2d8e-482">Lorsque vous y êtes invité, sélectionnez **entrée** pour le service de démarrage réseau.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-482">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="a2d8e-483">Windows PE est chargé en mémoire et l’Assistant séquence de tâches démarre.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-483">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="a2d8e-484">Sélectionnez **Next (suivant** ) pour continuer.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-484">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="a2d8e-485">Sélectionnez la séquence de tâches que vous avez importée précédemment, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-485">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="a2d8e-486">Une fois l’application configurée, vous êtes invité à spécifier le nom d’un ordinateur pour l’appareil.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-486">After the disk configuration is applied, you’ll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="a2d8e-487">L’interface utilisateur affiche un nom d’ordinateur recommandé en fonction du numéro de série de l’appareil surface Pro.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-487">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="a2d8e-488">Vous pouvez accepter le nom proposé ou en spécifier un nouveau.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-488">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="a2d8e-489">Suivez les instructions qui s’affichent sur l’écran d’attribution du nom de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-489">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="a2d8e-490">Lorsque vous sélectionnez **accepter**, le déploiement commence.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-490">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="a2d8e-491">Le reste du processus de déploiement est automatique et ne demande plus d’entrée utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-491">The rest of the deployment process is automatic and doesn’t ask for any more user input.</span></span>

9.  <span data-ttu-id="a2d8e-492">Une fois la séquence de tâches de déploiement terminée, vous verrez l’écran de configuration suivant qui vous demande de configurer les paramètres de l’application Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-492">After the deployment task sequence finishes configuring the device, you’ll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![Écran de configuration initiale de l’application Microsoft teams](../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="a2d8e-494">Branchez surface Pro dans la console Microsoft teams salles et configurez les paramètres de l’application.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-494">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="a2d8e-495">Vérifiez que les fonctionnalités répertoriées dans l' [aide de Microsoft teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) pour travailler sur l’appareil déployé.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-495">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="a2d8e-496">Pour résoudre un problème d’échec de l’installation, recherchez le fichier **smsts. log** qui enregistre toutes les étapes exécutées dans une séquence de tâches de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-496">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="a2d8e-497">Le fichier SMSTS. log est stocké sur l’un des chemins d’accès, en fonction de l’étape du processus de génération.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-497">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="a2d8e-498">Consultez le tableau suivant pour identifier le chemin d’accès au fichier SMSTS. log.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-498">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="a2d8e-499">**Phase de déploiement**</span><span class="sxs-lookup"><span data-stu-id="a2d8e-499">**Deployment phase**</span></span>                                                            | <span data-ttu-id="a2d8e-500">**Chemin du journal de séquence des tâches**</span><span class="sxs-lookup"><span data-stu-id="a2d8e-500">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="a2d8e-501">WinPE, avant le format HDD</span><span class="sxs-lookup"><span data-stu-id="a2d8e-501">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="a2d8e-502">X :\\Windows\\Temp\\smstslog\\smsts. log</span><span class="sxs-lookup"><span data-stu-id="a2d8e-502">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="a2d8e-503">WinPE, après le format HDD</span><span class="sxs-lookup"><span data-stu-id="a2d8e-503">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="a2d8e-504">C :\\_SMSTaskSequence\\journaux\\Smstslog\\smsts. log</span><span class="sxs-lookup"><span data-stu-id="a2d8e-504">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="a2d8e-505">Système d’exploitation déployé avant l’installation de l’agent Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a2d8e-505">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="a2d8e-506">c :\\_SMSTaskSequence\\journaux\\Smstslog\\smsts. log</span><span class="sxs-lookup"><span data-stu-id="a2d8e-506">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="a2d8e-507">Système d’exploitation et agent Configuration Manager déployé</span><span class="sxs-lookup"><span data-stu-id="a2d8e-507">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="a2d8e-508">journaux\\de CCM\\\\%\\windir% system32\\Smstslog smsts. log</span><span class="sxs-lookup"><span data-stu-id="a2d8e-508">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="a2d8e-509">Exécution d’une séquence de tâches terminée</span><span class="sxs-lookup"><span data-stu-id="a2d8e-509">Task sequence execution complete</span></span>                                                | <span data-ttu-id="a2d8e-510">% windir%\\system32\\,\\journaux\\de CCM smsts. log</span><span class="sxs-lookup"><span data-stu-id="a2d8e-510">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="a2d8e-511">Vous pouvez sélectionner **F8** à tout moment au cours de la séquence de tâches pour ouvrir une console de commandes, puis accéder au fichier smsts. log.</span><span class="sxs-lookup"><span data-stu-id="a2d8e-511">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="a2d8e-512">Pour résoudre les problèmes de démarrage PXE, recherchez dans les deux fichiers journaux du serveur Configuration Manager spécifiques aux actions PXE :</span><span class="sxs-lookup"><span data-stu-id="a2d8e-512">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="a2d8e-513">**Pxecontrol. log**, situé dans le répertoire des journaux d’installation de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a2d8e-513">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="a2d8e-514">**SMSPXE. log**, situé dans le répertoire des journaux du point de gestion de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a2d8e-514">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="a2d8e-515">Pour obtenir la liste complète des fichiers journaux que vous pouvez utiliser pour résoudre les problèmes de l’installation de votre gestionnaire de configuration, voir [fichiers journaux dans System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span><span class="sxs-lookup"><span data-stu-id="a2d8e-515">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>

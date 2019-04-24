---
title: Déployer Microsoft équipes salles à l’aide de System Center Configuration Manager
author: jambirk
ms.author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection: M365-voice
description: Lisez cette rubrique pour en savoir plus sur le déploiement de Microsoft équipes salles à des déploiements à grande échelle.
ms.openlocfilehash: fe6ffee0c6ab86496204ab4e17b86cc84a70a2a7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214910"
---
# <a name="deploy-microsoft-teams-rooms-by-using-system-center-configuration-manager"></a><span data-ttu-id="93e30-103">Déployer Microsoft équipes salles à l’aide de System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="93e30-103">Deploy Microsoft Teams Rooms by using System Center Configuration Manager</span></span>

<span data-ttu-id="93e30-104">Cet article vous offre toutes les informations nécessaires pour créer vos déploiements Microsoft équipes salles à l’aide de System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="93e30-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using System Center Configuration Manager.</span></span>

<span data-ttu-id="93e30-105">Avec les méthodes d’utilisation fournies par System Center Configuration Manager, vous pouvez déployer le système d’exploitation et autres applications à plusieurs périphériques cible.</span><span class="sxs-lookup"><span data-stu-id="93e30-105">With the easy-to-use methods provided by System Center Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="93e30-106">Utilisez l’approche illustrée ci-dessous pour vous guider tout au long de votre configuration du Gestionnaire de Configuration et personnaliser les exemples de packages et les scripts fournis dans ce guide, selon les besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="93e30-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Processus de déploiement de Microsoft équipes salles à l’aide du Gestionnaire de Configuration](../../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="93e30-108">Cette solution a été testée uniquement avec les déploiements basés sur la Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="93e30-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="93e30-109">Suivez les instructions du fabricant pour les configurations qui ne sont pas basées sur la Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="93e30-109">Follow the manufacturer’s guidelines for configurations that aren’t based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="93e30-110">Valider la configuration requise</span><span class="sxs-lookup"><span data-stu-id="93e30-110">Validate prerequisites</span></span>

<span data-ttu-id="93e30-111">Pour déployer Microsoft équipes salles avec le Gestionnaire de Configuration, vérifiez que vous disposez de la configuration requise et conditions préalables suivantes.</span><span class="sxs-lookup"><span data-stu-id="93e30-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="system-center-configuration-manager-requirements"></a><span data-ttu-id="93e30-112">Configuration requise de System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="93e30-112">System Center Configuration Manager requirements</span></span>

-   <span data-ttu-id="93e30-113">Version du système Center Configuration Manager doit être au moins 1706 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="93e30-113">System Center Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="93e30-114">Nous vous recommandons d’utiliser 1710 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="93e30-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="93e30-115">Consultez la rubrique [prise en charge pour Windows 10 dans System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) pour en savoir plus sur les versions de Windows 10 prend en charge le Gestionnaire de Configuration.</span><span class="sxs-lookup"><span data-stu-id="93e30-115">Check out [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="93e30-116">Une version prise en charge de l’évaluation de Windows et le Kit de déploiement (ADK) pour Windows 10 doit être installée.</span><span class="sxs-lookup"><span data-stu-id="93e30-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="93e30-117">Voir les versions de l' [ADK de 10 Windows](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) que vous pouvez utiliser avec différentes versions du Gestionnaire de Configuration et vous assurer que votre déploiement comprend la version correcte.</span><span class="sxs-lookup"><span data-stu-id="93e30-117">See the versions of the [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="93e30-118">Les serveurs de système de site doivent avoir reçu le rôle de point de distribution et les images de démarrage doivent être activées pour la [prise en charge de l’exécution environment (PXE) précédant le démarrage](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) activer des déploiements initiées par le réseau.</span><span class="sxs-lookup"><span data-stu-id="93e30-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="93e30-119">Si la prise en charge PXE n’est pas activée, vous pouvez utiliser [un support de démarrage](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) pour vos déploiements.</span><span class="sxs-lookup"><span data-stu-id="93e30-119">If PXE support isn’t enabled, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="93e30-120">Un compte d’accès au réseau doit être configuré pour prendre en charge de nouveaux scénarios de déploiement de l’ordinateur (vierge).</span><span class="sxs-lookup"><span data-stu-id="93e30-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="93e30-121">Pour en savoir plus sur la configuration d’un compte d’accès au réseau, voir [Gérer les comptes pour accéder au contenu dans System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="93e30-121">To learn more about the configuration of a network access account, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="93e30-122">Il est recommandé d’activer la [prise en charge multidiffusion](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), si vous êtes susceptible de déployer l’image de salles d’équipes Microsoft même plusieurs unités en même temps.</span><span class="sxs-lookup"><span data-stu-id="93e30-122">We recommend that you enable [multicast support](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you’re likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="93e30-123">Exigences de mise en réseau</span><span class="sxs-lookup"><span data-stu-id="93e30-123">Networking requirements</span></span>

-   <span data-ttu-id="93e30-124">Votre réseau doit posséder un serveur DHCP Dynamic Host Configuration Protocol (), configuré pour la distribution automatique des adresses IP pour les sous-réseaux où les unités de salles d’équipes Microsoft seront déployées.</span><span class="sxs-lookup"><span data-stu-id="93e30-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="93e30-125">Durée de bail DHCP doit être définie sur une valeur supérieure à la durée de déploiement d’image.</span><span class="sxs-lookup"><span data-stu-id="93e30-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="93e30-126">Dans le cas contraire, le déploiement peut échouer.</span><span class="sxs-lookup"><span data-stu-id="93e30-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="93e30-127">Votre réseau, y compris des commutateurs et des réseaux locaux virtuels (VLAN), doit être configuré pour prendre en charge PXE.</span><span class="sxs-lookup"><span data-stu-id="93e30-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="93e30-128">Consultez votre fournisseur de réseau pour plus d’informations sur la configuration d’assistance IP et PXE.</span><span class="sxs-lookup"><span data-stu-id="93e30-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="93e30-129">Autrement, vous pouvez utiliser [support](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) pour vos déploiements, si la prise en charge PXE n’est pas activé.</span><span class="sxs-lookup"><span data-stu-id="93e30-129">Alternatively, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn’t enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="93e30-130">Surface Pro appareils, démarrage à partir du réseau (démarrage PXE) sont uniquement pris en charge lorsque vous utilisez une carte réseau Ethernet ou une station d’accueil de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="93e30-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="93e30-131">Les cartes Ethernet tiers ne prend en charge démarrage PXE avec Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="93e30-131">Third-party Ethernet adapters don’t support PXE boot with Surface Pro.</span></span> <span data-ttu-id="93e30-132">Pour plus d’informations, voir [déploiement de Surface et de cartes Ethernet](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) .</span><span class="sxs-lookup"><span data-stu-id="93e30-132">See [Ethernet adapters and Surface deployment](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="93e30-133">Configuration de System Center Configuration Manager pour le déploiement de système d’exploitation</span><span class="sxs-lookup"><span data-stu-id="93e30-133">Configure System Center Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="93e30-134">Cet article suppose que vous disposez d’un déploiement de System Center Configuration Manager intègre et ne détail toutes les étapes nécessaires pour déployer et configurer le Gestionnaire de Configuration à partir de zéro.</span><span class="sxs-lookup"><span data-stu-id="93e30-134">This article assumes you already have a healthy System Center Configuration Manager deployment, and doesn’t detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="93e30-135">[documentation et les conseils de configuration](https://docs.microsoft.com/sccm/) de System Center Configuration Manager est une ressource importante ; Nous vous recommandons de que commencer avec ces ressources si vous n’avez pas encore déployé le Gestionnaire de Configuration.</span><span class="sxs-lookup"><span data-stu-id="93e30-135">The [documentation and the configuration guidance](https://docs.microsoft.com/sccm/) on the System Center Configuration Manager is a great resource; we recommend you start with these resources if you haven’t yet deployed Configuration Manager.</span></span>

<span data-ttu-id="93e30-136">Utilisez les instructions suivantes pour vérifier que les fonctionnalités de déploiement (système d’exploitation) du système d’exploitation sont correctement configurées.</span><span class="sxs-lookup"><span data-stu-id="93e30-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="93e30-137">Valider et le Gestionnaire de Configuration de la mise à niveau</span><span class="sxs-lookup"><span data-stu-id="93e30-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="93e30-138">Dans la console Configuration Manager, accédez à **Administration** \> **mises à jour et maintenance**.</span><span class="sxs-lookup"><span data-stu-id="93e30-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="93e30-139">Vérifiez la version installée et les mises à jour qui n’ont pas encore été installés.</span><span class="sxs-lookup"><span data-stu-id="93e30-139">Check the installed build and applicable updates that haven’t been installed yet.</span></span>

3.  <span data-ttu-id="93e30-140">Passez en revue la [prise en charge de Windows 10 dans System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); Si vous devez mettre à niveau votre déploiement, sélectionnez la mise à jour que vous voulez installer, puis sélectionnez **Télécharger**.</span><span class="sxs-lookup"><span data-stu-id="93e30-140">Review [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="93e30-141">Une fois que le téléchargement est terminé, sélectionnez la mise à jour, puis sélectionnez **Installer le Pack de mise à jour**.</span><span class="sxs-lookup"><span data-stu-id="93e30-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="93e30-142">Configurer des points de distribution pour prendre en charge PXE et la multidiffusion</span><span class="sxs-lookup"><span data-stu-id="93e30-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="93e30-143">Dans la console Configuration Manager, accédez à **Administration** \> **Points de Distribution**.</span><span class="sxs-lookup"><span data-stu-id="93e30-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="93e30-144">Sélectionnez le serveur du point de distribution qui va traiter le déploiement de salles d’équipes Microsoft, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="93e30-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="93e30-145">Sélectionnez l’onglet **PXE** et vérifiez que les paramètres suivants sont activés :</span><span class="sxs-lookup"><span data-stu-id="93e30-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="93e30-146">Activer la prise en charge PXE pour les clients</span><span class="sxs-lookup"><span data-stu-id="93e30-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="93e30-147">Autoriser ce point de distribution répondre aux demandes PXE entrantes</span><span class="sxs-lookup"><span data-stu-id="93e30-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="93e30-148">Activer la prise en charge de l’ordinateur inconnu</span><span class="sxs-lookup"><span data-stu-id="93e30-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="93e30-149">*Facultatif :* Pour activer la prise en charge multidiffusion, sélectionnez l’onglet **multidiffusion** et vérifiez que les paramètres suivants sont activés :</span><span class="sxs-lookup"><span data-stu-id="93e30-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="93e30-150">Activer la multidiffusion envoyer des données simultanément à plusieurs clients</span><span class="sxs-lookup"><span data-stu-id="93e30-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="93e30-151">Configurer la plage de ports UDP selon les recommandations de l’équipe de votre réseau</span><span class="sxs-lookup"><span data-stu-id="93e30-151">Configure the UDP port range as per your network team’s recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="93e30-152">Configurer le compte d’accès réseau</span><span class="sxs-lookup"><span data-stu-id="93e30-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="93e30-153">Dans la console Configuration Manager, accédez à **Administration** \> **Site Configuration** \> **Sites**et sélectionnez le site.</span><span class="sxs-lookup"><span data-stu-id="93e30-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="93e30-154">Dans le groupe **paramètres** , sélectionnez **Configurer les composants de Site** \> **La Distribution de logiciels**.</span><span class="sxs-lookup"><span data-stu-id="93e30-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="93e30-155">Sélectionnez l’onglet **Compte d’accès au réseau** d’un ou plusieurs comptes, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="93e30-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="93e30-156">Les comptes n’avez pas besoin des droits spéciaux, à l’exception de l' **accéder à cet ordinateur à partir du réseau** sur le serveur du point de distribution.</span><span class="sxs-lookup"><span data-stu-id="93e30-156">The accounts don’t need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="93e30-157">Un compte d’utilisateur de domaine générique sera approprié.</span><span class="sxs-lookup"><span data-stu-id="93e30-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="93e30-158">Pour plus d’informations, voir [Gérer les comptes pour accéder au contenu dans System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="93e30-158">For more information, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="93e30-159">Configurer une image de démarrage</span><span class="sxs-lookup"><span data-stu-id="93e30-159">Configure a boot image</span></span>

1.  <span data-ttu-id="93e30-160">Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **système d’exploitation** \> **Images de démarrage**.</span><span class="sxs-lookup"><span data-stu-id="93e30-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="93e30-161">Sélectionnez **l’image de démarrage (x64)**, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="93e30-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="93e30-162">Sélectionnez l’onglet **Source de données** et activez **déployer cette image de démarrage à partir du point de distribution à extension PXE**.</span><span class="sxs-lookup"><span data-stu-id="93e30-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="93e30-163">Sélectionnez l’onglet **Composants facultatifs** pour installer les composants requis :</span><span class="sxs-lookup"><span data-stu-id="93e30-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="93e30-164">Sélectionnez l’icône en étoile et de recherche pour le **code HTML (HTA-WinPE)**</span><span class="sxs-lookup"><span data-stu-id="93e30-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="93e30-165">Cliquez sur **OK** pour ajouter la prise en charge des applications de HTML dans à l’image de démarrage.</span><span class="sxs-lookup"><span data-stu-id="93e30-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="93e30-166">*Facultatif :* Pour personnaliser l’expérience de déploiement, sélectionnez l’onglet **personnalisation** .</span><span class="sxs-lookup"><span data-stu-id="93e30-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="93e30-167">Activer la **commande prend en charge (test uniquement)** si vous souhaitez avoir accès à une invite de commandes au cours du déploiement.</span><span class="sxs-lookup"><span data-stu-id="93e30-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="93e30-168">Lorsque cette option est activée, vous pouvez lancer une invite de commandes en sélectionnant **F8** à tout moment au cours du déploiement.</span><span class="sxs-lookup"><span data-stu-id="93e30-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="93e30-169">Vous pouvez également spécifier un arrière-plan personnalisé à afficher lors du déploiement.</span><span class="sxs-lookup"><span data-stu-id="93e30-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="93e30-170">Pour définir une image, activez **spécifier le fichier d’image arrière-plan personnalisé (chemin d’accès UNC** et sélectionnez votre arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="93e30-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="93e30-171">Lorsque vous êtes invité, sélectionnez **Oui** et distribuer l’image de démarrage mise à jour pour vos points de distribution.</span><span class="sxs-lookup"><span data-stu-id="93e30-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="93e30-172">Pour plus d’informations, voir [Gérer les images de démarrage avec System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span><span class="sxs-lookup"><span data-stu-id="93e30-172">For more information, see [Manage boot images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="93e30-173">Vous pouvez créer un support USB pour lancer le Gestionnaire de Configuration des déploiements basés sur la séquence tâche pour les environnements qui n’ont aucune prise en charge PXE.</span><span class="sxs-lookup"><span data-stu-id="93e30-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="93e30-174">Le support amorçable contient uniquement l’image de démarrage, commandes prestart facultatifs leurs requis et les fichiers binaires du Gestionnaire de Configuration pour prendre en charge le démarrage de Windows PE et la connexion au Gestionnaire de Configuration pour le reste du processus de déploiement.</span><span class="sxs-lookup"><span data-stu-id="93e30-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="93e30-175">Pour plus d’informations, voir [comment créer un support de démarrage](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span><span class="sxs-lookup"><span data-stu-id="93e30-175">For more information, see [How to Create Bootable Media](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="93e30-176">Créer des packages de gestionnaire de Configuration</span><span class="sxs-lookup"><span data-stu-id="93e30-176">Create Configuration Manager packages</span></span>

<span data-ttu-id="93e30-177">Gestionnaire de configuration requiert un nombre de packages pour déployer et configurer les unités de salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="93e30-177">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="93e30-178">Vous devez créer et configurer les packages suivants, puis les distribuer aux systèmes de site Configuration Manager qui ont été attribués le rôle de serveur de point de distribution.</span><span class="sxs-lookup"><span data-stu-id="93e30-178">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="93e30-179">**Nom du package**</span><span class="sxs-lookup"><span data-stu-id="93e30-179">**Package name**</span></span>                     | <span data-ttu-id="93e30-180">**Type**</span><span class="sxs-lookup"><span data-stu-id="93e30-180">**Type**</span></span>               | <span data-ttu-id="93e30-181">**Description**</span><span class="sxs-lookup"><span data-stu-id="93e30-181">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="93e30-182">SRS v2 - SRS Package d’Application</span><span class="sxs-lookup"><span data-stu-id="93e30-182">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="93e30-183">Package de logiciels</span><span class="sxs-lookup"><span data-stu-id="93e30-183">Software package</span></span>       | <span data-ttu-id="93e30-184">Package pour le kit de déploiement Microsoft équipes salles</span><span class="sxs-lookup"><span data-stu-id="93e30-184">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="93e30-185">SRS v2 - Package Sysprep</span><span class="sxs-lookup"><span data-stu-id="93e30-185">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="93e30-186">Package de logiciels</span><span class="sxs-lookup"><span data-stu-id="93e30-186">Software package</span></span>       | <span data-ttu-id="93e30-187">Package pour la Unattended.xml personnalisée configurer les unités de salles d’équipes Microsoft</span><span class="sxs-lookup"><span data-stu-id="93e30-187">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="93e30-188">SRS v2 - Package Set-SRSComputerName</span><span class="sxs-lookup"><span data-stu-id="93e30-188">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="93e30-189">Package de logiciels</span><span class="sxs-lookup"><span data-stu-id="93e30-189">Software package</span></span>       | <span data-ttu-id="93e30-190">Package de l’application HTML (HTA) attribuer un nom d’ordinateur au cours du déploiement</span><span class="sxs-lookup"><span data-stu-id="93e30-190">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="93e30-191">SRS v2 - configurer le programme d’installation SRS</span><span class="sxs-lookup"><span data-stu-id="93e30-191">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="93e30-192">Package de logiciels</span><span class="sxs-lookup"><span data-stu-id="93e30-192">Software package</span></span>       | <span data-ttu-id="93e30-193">Package pour configurer le déploiement de l’application Microsoft équipes salles</span><span class="sxs-lookup"><span data-stu-id="93e30-193">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="93e30-194">Système d’exploitation de SRS v2 - mises à jour de Package</span><span class="sxs-lookup"><span data-stu-id="93e30-194">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="93e30-195">Package de logiciels</span><span class="sxs-lookup"><span data-stu-id="93e30-195">Software package</span></span>       | <span data-ttu-id="93e30-196">Package de déploiement des mises à jour du système d’exploitation obligatoire</span><span class="sxs-lookup"><span data-stu-id="93e30-196">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="93e30-197">SRS v2 - Package du certificat racine</span><span class="sxs-lookup"><span data-stu-id="93e30-197">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="93e30-198">Package de logiciels</span><span class="sxs-lookup"><span data-stu-id="93e30-198">Software package</span></span>       | <span data-ttu-id="93e30-199">Facultatif : Package pour déployer le certificat racine (non requis pour les unités à un domaine)</span><span class="sxs-lookup"><span data-stu-id="93e30-199">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="93e30-200">SRS v2 - Microsoft Package de l’Agent de surveillance</span><span class="sxs-lookup"><span data-stu-id="93e30-200">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="93e30-201">Package de logiciels</span><span class="sxs-lookup"><span data-stu-id="93e30-201">Software package</span></span>       | <span data-ttu-id="93e30-202">Facultatif : Package pour déployer et configurer l’agent Microsoft Operations Management Suite</span><span class="sxs-lookup"><span data-stu-id="93e30-202">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="93e30-203">SRS v2 - Package WinPE arrière-plan</span><span class="sxs-lookup"><span data-stu-id="93e30-203">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="93e30-204">Package de logiciels</span><span class="sxs-lookup"><span data-stu-id="93e30-204">Software package</span></span>       | <span data-ttu-id="93e30-205">Nom du package de l’image d’arrière-plan personnalisé à utiliser avec les images de démarrage</span><span class="sxs-lookup"><span data-stu-id="93e30-205">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="93e30-206">Entreprise Windows 10</span><span class="sxs-lookup"><span data-stu-id="93e30-206">Windows 10 Enterprise</span></span>                | <span data-ttu-id="93e30-207">Image du système d’exploitation</span><span class="sxs-lookup"><span data-stu-id="93e30-207">Operating system image</span></span> | <span data-ttu-id="93e30-208">Package pour le fichier d’installation de système d’exploitation (install.wim)</span><span class="sxs-lookup"><span data-stu-id="93e30-208">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="93e30-209">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="93e30-209">Surface Pro</span></span>                          | <span data-ttu-id="93e30-210">Package de pilotes</span><span class="sxs-lookup"><span data-stu-id="93e30-210">Driver package</span></span>         | <span data-ttu-id="93e30-211">Package pour les pilotes de périphériques et le microprogramme Microsoft Surface Pro</span><span class="sxs-lookup"><span data-stu-id="93e30-211">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="93e30-212">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="93e30-212">Surface Pro 4</span></span>                        | <span data-ttu-id="93e30-213">Package de pilotes</span><span class="sxs-lookup"><span data-stu-id="93e30-213">Driver package</span></span>         | <span data-ttu-id="93e30-214">Package pour les pilotes de périphériques et de microprogrammes pour Microsoft Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="93e30-214">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="93e30-215">Pour plus d’informations, voir [Packages et des programmes dans System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="93e30-215">For more information, see [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="93e30-216">Créer des dossiers pour le package de fichiers sources</span><span class="sxs-lookup"><span data-stu-id="93e30-216">Create folders for the package source files</span></span>

<span data-ttu-id="93e30-217">Gestionnaire de configuration requiert des fichiers sources du package pour être organisés en une structure de dossiers spécifiques lorsqu’elles sont d’abord créées et lorsqu’ils sont mis à jour.</span><span class="sxs-lookup"><span data-stu-id="93e30-217">Configuration Manager requires package source files to be organized in a specific folder structure when they’re first created and when they’re updated.</span></span>

<span data-ttu-id="93e30-218">Créez la structure de dossier suivante sur le site administration centrale de System Center Configuration Manager ou principal ou sur un partage de serveur que vous utilisez pour les fichiers sources du package hôte :</span><span class="sxs-lookup"><span data-stu-id="93e30-218">Create the following folder structure on the System Center Configuration Manager central administration site or primary site, or on a server share you’re using to host package source files:</span></span>

-   <span data-ttu-id="93e30-219">SRS v2 - Microsoft Package de l’Agent de surveillance</span><span class="sxs-lookup"><span data-stu-id="93e30-219">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="93e30-220">Système d’exploitation de SRS v2 - mises à jour de Package</span><span class="sxs-lookup"><span data-stu-id="93e30-220">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="93e30-221">SRS v2 - Package du certificat racine</span><span class="sxs-lookup"><span data-stu-id="93e30-221">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="93e30-222">SRS v2 - Package Set-SRSComputerName</span><span class="sxs-lookup"><span data-stu-id="93e30-222">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="93e30-223">SRS v2 - SRS Package d’Application</span><span class="sxs-lookup"><span data-stu-id="93e30-223">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="93e30-224">SRS v2 - configurer le programme d’installation SRS</span><span class="sxs-lookup"><span data-stu-id="93e30-224">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="93e30-225">SRS v2 - Package Sysprep</span><span class="sxs-lookup"><span data-stu-id="93e30-225">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="93e30-226">Pilotes</span><span class="sxs-lookup"><span data-stu-id="93e30-226">Drivers</span></span>
    -   <span data-ttu-id="93e30-227">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="93e30-227">Surface Pro</span></span>
    -   <span data-ttu-id="93e30-228">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="93e30-228">Surface Pro 4</span></span>
-   <span data-ttu-id="93e30-229">Systèmes d’exploitation</span><span class="sxs-lookup"><span data-stu-id="93e30-229">Operating Systems</span></span>
    -   <span data-ttu-id="93e30-230">Entreprise Windows 10</span><span class="sxs-lookup"><span data-stu-id="93e30-230">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="93e30-231">Vous pouvez également [Télécharger](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) et utilisez le fichier zip qui inclut la structure de dossiers pour les packages, que vous devez utiliser les scripts et le modèle de séquence de tâches que vous devez l’importer.</span><span class="sxs-lookup"><span data-stu-id="93e30-231">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="93e30-232">Créer le package de l’agent de surveillance</span><span class="sxs-lookup"><span data-stu-id="93e30-232">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="93e30-233">Télécharger l’agent d’analyse à partir de <https://go.microsoft.com/fwlink/?LinkId=828603>.</span><span class="sxs-lookup"><span data-stu-id="93e30-233">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="93e30-234">Extraire le package dans le dossier **SRS v2 - Package de l’Agent de surveillance Microsoft** en ouvrant une fenêtre d’invite de commandes et en **saisissant/C: MMASetup-AMD64.exe** à l’invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="93e30-234">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="93e30-235">Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **Gestion des applications** \> **Packages**, puis sélectionnez **Créer un Package**.</span><span class="sxs-lookup"><span data-stu-id="93e30-235">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="93e30-236">Entrez les informations suivantes pour créer le package :</span><span class="sxs-lookup"><span data-stu-id="93e30-236">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="93e30-237">Nom<strong>: SRS v2 - Microsoft Package de l’Agent de surveillance</strong></span><span class="sxs-lookup"><span data-stu-id="93e30-237">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="93e30-238">Fabricant<strong>: Microsoft Corporation</strong></span><span class="sxs-lookup"><span data-stu-id="93e30-238">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="93e30-239">Version<strong>: 8.1.11081.0</strong> (entrez la version du fichier d’installation téléchargé)</span><span class="sxs-lookup"><span data-stu-id="93e30-239">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="93e30-240">Activez la case à cocher **ce package contient des fichiers source** , entrez le chemin d’accès du dossier **SRS v2 - Package de l’Agent de surveillance de Microsoft** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-240">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="93e30-241">Sélectionnez **ne pas créer un programme**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-241">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="93e30-242">Passez en revue la page **vérifier les paramètres** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-242">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="93e30-243">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="93e30-243">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="93e30-244">Créer le package de mises à jour de système d’exploitation</span><span class="sxs-lookup"><span data-stu-id="93e30-244">Create the operating system updates package</span></span>

1. <span data-ttu-id="93e30-245">Dans le dossier **SRS v2 - Package de mises à jour du système d’exploitation** , créez un nouveau script PowerShell nommé **Install-SRSv2-OS-Updates.ps1**.</span><span class="sxs-lookup"><span data-stu-id="93e30-245">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="93e30-246">Copiez le script ci-dessous dans le script **Install-SRSv2-OS-Updates.ps1** .</span><span class="sxs-lookup"><span data-stu-id="93e30-246">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="93e30-247">Vous pouvez également télécharger le script Install-SRSv2-OS-Updates.ps1 [ici](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="93e30-247">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="93e30-248">Téléchargez les packages de mise à jour Windows obligatoires dans le même dossier.</span><span class="sxs-lookup"><span data-stu-id="93e30-248">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="93e30-249">Au moment de que cet article a été publié, uniquement [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) était requis.</span><span class="sxs-lookup"><span data-stu-id="93e30-249">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="93e30-250">Vérifiez de [configurer une console salles des équipes Microsoft](console.md), pour voir si des mises à jour sont requises.</span><span class="sxs-lookup"><span data-stu-id="93e30-250">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="93e30-251">Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **Gestion des applications** \> **Packages**, puis sélectionnez **Créer un Package**.</span><span class="sxs-lookup"><span data-stu-id="93e30-251">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="93e30-252">Entrez les informations suivantes pour créer le package :</span><span class="sxs-lookup"><span data-stu-id="93e30-252">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="93e30-253">Nom : **SRS v2 – du système d’exploitation met à jour le Package**</span><span class="sxs-lookup"><span data-stu-id="93e30-253">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="93e30-254">Fabricant : **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="93e30-254">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="93e30-255">Version : **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="93e30-255">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="93e30-256">Activez la case à cocher **ce package contient des fichiers source** , entrez le chemin d’accès du dossier **SRS v2 - Package de mises à jour du système d’exploitation** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-256">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="93e30-257">Sélectionnez **ne pas créer un programme**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-257">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="93e30-258">Passez en revue la page **vérifier les paramètres** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-258">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="93e30-259">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="93e30-259">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="93e30-260">Créer le package de certificat racine (facultatif)</span><span class="sxs-lookup"><span data-stu-id="93e30-260">Create the root certificate package (optional)</span></span>

<span data-ttu-id="93e30-261">Vous créez ce package pour distribuer le certificat racine pour les périphériques qui ne sont pas être joint à un domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="93e30-261">You create this package to distribute the root certificate for devices that won’t be joined to an Active Directory domain.</span></span> <span data-ttu-id="93e30-262">Créer ce package uniquement si les deux conditions suivantes s’appliquent :</span><span class="sxs-lookup"><span data-stu-id="93e30-262">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="93e30-263">Votre déploiement comprend locale Lync ou Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="93e30-263">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="93e30-264">Unités de salles d’équipes Microsoft sont configurées pour fonctionner dans un groupe de travail au lieu d’un membre du domaine.</span><span class="sxs-lookup"><span data-stu-id="93e30-264">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="93e30-265">Copiez le certificat racine dans le dossier **SRS v2 – Package du certificat racine** .</span><span class="sxs-lookup"><span data-stu-id="93e30-265">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="93e30-266">Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **Gestion des applications** \> **Packages**, puis sélectionnez **Créer un Package**.</span><span class="sxs-lookup"><span data-stu-id="93e30-266">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="93e30-267">Entrez les informations suivantes pour créer le package :</span><span class="sxs-lookup"><span data-stu-id="93e30-267">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="93e30-268">Nom : **SRS v2 – Package du certificat racine**</span><span class="sxs-lookup"><span data-stu-id="93e30-268">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="93e30-269">Fabricant : *nom de votre organisation*</span><span class="sxs-lookup"><span data-stu-id="93e30-269">Manufacturer: *Your organization’s name*</span></span>
    -   <span data-ttu-id="93e30-270">Version : **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="93e30-270">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="93e30-271">Activez la case à cocher **ce package contient des fichiers source** , entrez le chemin d’accès du dossier **SRS v2 – Package du certificat racine** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-271">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="93e30-272">Sélectionnez **ne pas créer un programme**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-272">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="93e30-273">Passez en revue la page **vérifier les paramètres** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-273">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="93e30-274">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="93e30-274">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="93e30-275">Créer le package de kit de déploiement Microsoft équipes salles</span><span class="sxs-lookup"><span data-stu-id="93e30-275">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="93e30-276">Télécharger la dernière version du **kit de déploiement Microsoft équipes salles** à partir de <https://go.microsoft.com/fwlink/?linkid=851168>, puis installez-le dans une station de travail.</span><span class="sxs-lookup"><span data-stu-id="93e30-276">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="93e30-277">Copiez le contenu à partir de **c :\\Program Files (x86)\\Kit de déploiement de système de salle Skype** dans le dossier **SRS v2 - SRS Package d’Application** .</span><span class="sxs-lookup"><span data-stu-id="93e30-277">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="93e30-278">Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **Gestion des applications** \> **Packages**, puis sélectionnez **Créer un Package**.</span><span class="sxs-lookup"><span data-stu-id="93e30-278">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="93e30-279">Entrez les informations suivantes pour créer le package :</span><span class="sxs-lookup"><span data-stu-id="93e30-279">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="93e30-280">Nom : **SRS v2 – SRS Package d’Application**</span><span class="sxs-lookup"><span data-stu-id="93e30-280">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="93e30-281">Fabricant : **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="93e30-281">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="93e30-282">Version : **3.1.104.0** (entrez la version du fichier d’installation téléchargé)</span><span class="sxs-lookup"><span data-stu-id="93e30-282">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="93e30-283">Activez la case à cocher **ce package contient des fichiers source** , entrez le chemin d’accès du dossier **SRS v2 – SRS Package d’Application** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-283">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="93e30-284">Sélectionnez **ne pas créer un programme**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-284">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="93e30-285">Passez en revue la page **vérifier les paramètres** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-285">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="93e30-286">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="93e30-286">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="93e30-287">Créer le package d’affectation de nom ordinateur</span><span class="sxs-lookup"><span data-stu-id="93e30-287">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="93e30-288">Dans le dossier **SRS v2 - Package Set-SRSComputerName** , créez une nouvelle application HTML nommée **Set-SRSComputerName.hta** .</span><span class="sxs-lookup"><span data-stu-id="93e30-288">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="93e30-289">Copiez le script suivant dans le fichier **Set-SRSComputerName.hta** .</span><span class="sxs-lookup"><span data-stu-id="93e30-289">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="93e30-290">Sinon, vous pouvez télécharger le fichier Set-SRSComputerName.hta à partir [d’ici](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="93e30-290">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3.  <span data-ttu-id="93e30-291">Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **Gestion des applications** \> **Packages**, puis sélectionnez **Créer un Package**.</span><span class="sxs-lookup"><span data-stu-id="93e30-291">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="93e30-292">Entrez les informations suivantes pour créer le package :</span><span class="sxs-lookup"><span data-stu-id="93e30-292">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="93e30-293">Nom : **SRS v2 - Package Set-SRSComputerName**</span><span class="sxs-lookup"><span data-stu-id="93e30-293">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="93e30-294">Fabricant : **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="93e30-294">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="93e30-295">Version : **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="93e30-295">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="93e30-296">Activez la case à cocher **ce package contient des fichiers source** , entrez le chemin d’accès du dossier **SRS v2 - Set-SRSComputerName Package** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-296">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="93e30-297">Sélectionnez **ne pas créer un programme**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-297">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="93e30-298">Passez en revue la page **vérifier les paramètres** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-298">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="93e30-299">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="93e30-299">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="93e30-300">Créer le package Sysprep</span><span class="sxs-lookup"><span data-stu-id="93e30-300">Create the Sysprep package</span></span>

1. <span data-ttu-id="93e30-301">Dans le dossier **SRS v2 – Sysprep Package** , créez un nouveau fichier XML nommé **Unattend.xml** .</span><span class="sxs-lookup"><span data-stu-id="93e30-301">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="93e30-302">Copiez le texte suivant dans le fichier **Unattend.xml** .</span><span class="sxs-lookup"><span data-stu-id="93e30-302">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="93e30-303">Vous pouvez également télécharger le fichier Unattend.xml [ici](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="93e30-303">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="93e30-304">Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **Gestion des applications** \> **Packages**, puis sélectionnez **Créer un Package**.</span><span class="sxs-lookup"><span data-stu-id="93e30-304">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="93e30-305">Entrez les informations suivantes pour créer le package :</span><span class="sxs-lookup"><span data-stu-id="93e30-305">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="93e30-306">Nom : **SRS v2 - Package Sysprep**</span><span class="sxs-lookup"><span data-stu-id="93e30-306">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="93e30-307">Fabricant : **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="93e30-307">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="93e30-308">Version : **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="93e30-308">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="93e30-309">Activez la case à cocher **ce package contient des fichiers source** , entrez le chemin d’accès du dossier **SRS v2 – Sysprep Package** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-309">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="93e30-310">Sélectionnez **ne pas créer un programme**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-310">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="93e30-311">Passez en revue la page **vérifier les paramètres** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-311">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="93e30-312">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="93e30-312">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="93e30-313">Créer le package Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="93e30-313">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="93e30-314">Obtenir un support Windows 10 entreprise x64 et copiez le fichier **install.wim** à le **systèmes d’exploitation\\Windows 10 entreprise** dossier.</span><span class="sxs-lookup"><span data-stu-id="93e30-314">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="93e30-315">Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **systèmes d’exploitation** \> **Images du système d’exploitation**, puis choisissez **Ajouter une Image de système d’exploitation**.</span><span class="sxs-lookup"><span data-stu-id="93e30-315">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="93e30-316">Spécifiez le chemin d’accès au fichier **install.wim** que vous venez de copier, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-316">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="93e30-317">Mettre à jour le champ **Version** pour faire correspondre le numéro de version de l’image d’entreprise de 10 Windows, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-317">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="93e30-318">Passez en revue la page de **Détails** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-318">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="93e30-319">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="93e30-319">Select **Close**.</span></span>

<span data-ttu-id="93e30-320">Pour plus d’informations, voir [Gérer les images de système d’exploitation avec System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span><span class="sxs-lookup"><span data-stu-id="93e30-320">For more information, see [Manage operating system images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="93e30-321">Créer des packages de pilote de périphérique Surface Pro</span><span class="sxs-lookup"><span data-stu-id="93e30-321">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="93e30-322">Salles d’équipes Microsoft est pris en charge pour la Surface Pro et Surface Pro 4.</span><span class="sxs-lookup"><span data-stu-id="93e30-322">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="93e30-323">Vous devez créer un package pour chaque modèle de Surface Pro que vous disposez dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="93e30-323">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="93e30-324">Les pilotes doivent être compatibles avec la version entreprise de 10 Windows et la version de kit de déploiement Microsoft équipes salles.</span><span class="sxs-lookup"><span data-stu-id="93e30-324">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="93e30-325">Pour plus d’informations, voir [télécharger les derniers microprogrammes et pilotes de périphériques de Surface](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) et [configurer une console](console.md).</span><span class="sxs-lookup"><span data-stu-id="93e30-325">For more information, see [Download the latest firmware and drivers for Surface devices](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="93e30-326">Téléchargez les pilotes et le microprogramme le plus récent.</span><span class="sxs-lookup"><span data-stu-id="93e30-326">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="93e30-327">Pour une Surface Pro :<https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="93e30-327">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="93e30-328">Pour une Surface Pro 4 :<https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="93e30-328">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="93e30-329">Extrayez le pilote téléchargé et le micrologiciel.</span><span class="sxs-lookup"><span data-stu-id="93e30-329">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="93e30-330">Ouvrez une fenêtre d’invite de commandes et à l’invite de commandes, entrez l’une des commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="93e30-330">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="93e30-331">Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **systèmes d’exploitation** \> **pilotes**, puis sélectionnez **Importation pilote**.</span><span class="sxs-lookup"><span data-stu-id="93e30-331">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="93e30-332">Sélectionnez **Importer tous les pilotes dans le chemin d’accès réseau suivants (UNC)**, sélectionnez le dossier source (par exemple, c :\\_Sources\\pilotes\\Surface Pro), puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-332">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="93e30-333">Dans la page **spécifier les détails pour les pilotes importés** , sélectionnez tous les pilotes répertoriés, puis sélectionnez **activer ces pilotes et autoriser des ordinateurs à les installer**.</span><span class="sxs-lookup"><span data-stu-id="93e30-333">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="93e30-334">Sélectionner les **catégories**, créer une catégorie qui correspond au modèle de Surface, sélectionnez **OK**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-334">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="93e30-335">Sélectionnez **Nouveau Package**.</span><span class="sxs-lookup"><span data-stu-id="93e30-335">Select **New Package**.</span></span>

8.  <span data-ttu-id="93e30-336">Spécifiez le nom du package qui correspond au modèle Surface Pro, entrez un chemin d’accès du dossier pour stocker les fichiers de package de pilote dans, sélectionnez **OK**, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-336">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="93e30-337">Dans la page **d’images de démarrage** , ne vérifiez que l’option Aucun images de démarrage sont sélectionnés, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-337">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="93e30-338">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="93e30-338">Select **Close**.</span></span>

11. <span data-ttu-id="93e30-339">Accédez à la **Bibliothèque de logiciels** \> **systèmes d’exploitation** \> **pilotes**, sélectionnez **dossier \> créer un dossier**, puis entrez un nom de dossier qui correspond au modèle de Surface Pro que vous venez d’importer les pilotes.</span><span class="sxs-lookup"><span data-stu-id="93e30-339">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="93e30-340">Déplacez tous les pilotes importées dans le dossier nouvellement créé pour faciliter la navigation et opération.</span><span class="sxs-lookup"><span data-stu-id="93e30-340">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="93e30-341">Répétez les étapes pour les autres modèles de Surface Pro, que vous devrez peut-être.</span><span class="sxs-lookup"><span data-stu-id="93e30-341">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="93e30-342">Pour plus d’informations, voir [Gérer les pilotes dans System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span><span class="sxs-lookup"><span data-stu-id="93e30-342">For more information, see [Manage drivers in System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="93e30-343">Créer le Package de Configuration de salles équipes Microsoft</span><span class="sxs-lookup"><span data-stu-id="93e30-343">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="93e30-344">Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **Gestion des applications** \> **Packages**, puis sélectionnez **Créer un Package**.</span><span class="sxs-lookup"><span data-stu-id="93e30-344">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="93e30-345">Entrez les informations suivantes pour créer le package :</span><span class="sxs-lookup"><span data-stu-id="93e30-345">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="93e30-346">Nom : **SRS v2 - configurer le Package d’installation SRS**</span><span class="sxs-lookup"><span data-stu-id="93e30-346">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="93e30-347">Fabricant : **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="93e30-347">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="93e30-348">Version : **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="93e30-348">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="93e30-349">Activez la case à cocher **ce package contient des fichiers source** , entrez le chemin d’accès du dossier **SRS v2 - configurer le programme d’installation de SRS** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-349">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="93e30-350">Sélectionnez **ne pas créer un programme**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-350">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="93e30-351">Passez en revue la page **vérifier les paramètres** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-351">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="93e30-352">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="93e30-352">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="93e30-353">Distribuer des packages de gestionnaire de Configuration</span><span class="sxs-lookup"><span data-stu-id="93e30-353">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="93e30-354">Tous les packages doivent être distribués sur les serveurs qui ont été attribués au rôle de point de distribution dans la hiérarchie du Gestionnaire de Configuration.</span><span class="sxs-lookup"><span data-stu-id="93e30-354">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="93e30-355">Suivez les instructions ci-dessous pour lancer la distribution du package.</span><span class="sxs-lookup"><span data-stu-id="93e30-355">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="93e30-356">Distribuer des logiciels.</span><span class="sxs-lookup"><span data-stu-id="93e30-356">Distribute software packages.</span></span>

    1.  <span data-ttu-id="93e30-357">Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **Gestion des applications** \> **Packages**.</span><span class="sxs-lookup"><span data-stu-id="93e30-357">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="93e30-358">Sélectionnez tous les packages de logiciel que vous voulez distribuer, puis sélectionnez **Distribuer le contenu**.</span><span class="sxs-lookup"><span data-stu-id="93e30-358">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="93e30-359">Passez en revue la liste des packages, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-359">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="93e30-360">Ajoutez tous les serveurs de point de distribution (ou groupes de points de distribution, en fonction de votre hiérarchie de Configuration Manager) à la liste, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-360">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="93e30-361">Cliquez sur **suivant**, puis sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="93e30-361">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="93e30-362">Distribuer des packages de pilotes.</span><span class="sxs-lookup"><span data-stu-id="93e30-362">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="93e30-363">Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **systèmes d’exploitation** \> **Packages de pilotes**.</span><span class="sxs-lookup"><span data-stu-id="93e30-363">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="93e30-364">Sélectionnez tous les packages à distribuer, puis sélectionnez **Distribuer le contenu**.</span><span class="sxs-lookup"><span data-stu-id="93e30-364">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="93e30-365">Passez en revue la liste des packages, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-365">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="93e30-366">Ajoutez tous les serveurs de point de distribution (ou groupes de points de distribution, en fonction de votre hiérarchie de Configuration Manager) à la liste, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-366">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="93e30-367">Cliquez sur **suivant**, puis sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="93e30-367">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="93e30-368">Distribuer des packages de système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="93e30-368">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="93e30-369">Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **systèmes d’exploitation** \> **Images du système d’exploitation**.</span><span class="sxs-lookup"><span data-stu-id="93e30-369">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="93e30-370">Sélectionnez toutes les images de système d’exploitation que vous voulez distribuer, puis sélectionnez **Distribuer le contenu**.</span><span class="sxs-lookup"><span data-stu-id="93e30-370">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="93e30-371">Passez en revue la liste des packages, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-371">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="93e30-372">Ajoutez tous les serveurs de point de distribution (ou groupes de points de distribution, en fonction de votre hiérarchie de Configuration Manager) à la liste, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-372">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="93e30-373">Cliquez sur **suivant**, puis sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="93e30-373">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="93e30-374">Distribution de package peut prendre un certain temps, en fonction de la taille du package, le Gestionnaire de Configuration hiérarchie, nombre de serveurs de point de distribution et la bande passante disponible dans votre réseau.</span><span class="sxs-lookup"><span data-stu-id="93e30-374">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="93e30-375">Tous les packages doivent être distribuées avant de pouvoir commencer le déploiement d’une unité de salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="93e30-375">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="93e30-376">Vous pouvez consulter l’état de la distribution de package dans la console Configuration Manager en accédant à la **surveillance** \> **État de la Distribution** \> **État du contenu**.</span><span class="sxs-lookup"><span data-stu-id="93e30-376">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="93e30-377">Séquences de tâches Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="93e30-377">Configuration Manager task sequences</span></span>

<span data-ttu-id="93e30-378">Vous utilisez séquences de tâches avec System Center Configuration Manager pour automatiser les étapes de déploiement d’une image du système d’exploitation sur un ordinateur de destination.</span><span class="sxs-lookup"><span data-stu-id="93e30-378">You use task sequences with System Center Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="93e30-379">Pour déployer une unité de salles d’équipes Microsoft de manière automatique, vous créez une séquence de tâches qui fait référence à l’image de démarrage permet de démarrer l’ordinateur Microsoft équipes salles de destination, l’image du système d’exploitation Windows 10 entreprise que vous voulez installer et les autre contenu supplémentaire, tel que d’autres applications ou les mises à jour logicielles.</span><span class="sxs-lookup"><span data-stu-id="93e30-379">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="93e30-380">Importer la séquence de tâches exemple</span><span class="sxs-lookup"><span data-stu-id="93e30-380">Import the sample task sequence</span></span>

<span data-ttu-id="93e30-381">Vous pouvez télécharger facilement importer une séquence de tâches exemple et personnaliser pour répondre à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="93e30-381">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="93e30-382">[**Télécharger**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) l’exemple de séquence de tâches et copiez le fichier .ZIP téléchargé dans un emplacement partagé.</span><span class="sxs-lookup"><span data-stu-id="93e30-382">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="93e30-383">Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **systèmes d’exploitation** \> **Séquences de tâches**, puis sélectionnez **Séquence de tâches d’importation**.</span><span class="sxs-lookup"><span data-stu-id="93e30-383">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="93e30-384">Sélectionnez **Parcourir**, accédez à l’emplacement de dossier partagé que vous avez utilisé à l’étape 1, sélectionnez le fichier **.zip de Microsoft équipes salles de déploiement (EN-US)** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-384">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="93e30-385">Définir **l’Action** pour **Créer un nouveau**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-385">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="93e30-386">Vérifier les paramètres, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-386">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="93e30-387">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="93e30-387">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="93e30-388">Vérifiez que les packages de référence sont correctement liés à chaque étape de séquence de tâches.</span><span class="sxs-lookup"><span data-stu-id="93e30-388">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="93e30-389">Sélectionnez la séquence de tâches importés, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="93e30-389">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="93e30-390">L’éditeur de séquence de tâches s’ouvre et affiche chaque étape séquentiel dont vous avez besoin pour déployer et configurer une unité de salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="93e30-390">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="93e30-391">Passez en revue chaque étape et effectuer les mises à jour recommandées :</span><span class="sxs-lookup"><span data-stu-id="93e30-391">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="93e30-392">**Redémarrez dans Windows PE**: cette étape redémarre et PXE Windows puis démarre l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="93e30-392">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="93e30-393">Aucune modification n’est requise pour cette étape.</span><span class="sxs-lookup"><span data-stu-id="93e30-393">No changes are required for this step.</span></span>

   2. <span data-ttu-id="93e30-394">**Partition de disque 0 – UEFI**: cette étape efface la configuration du disque et crée des partitions en fonction des paramètres configurés.</span><span class="sxs-lookup"><span data-stu-id="93e30-394">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="93e30-395">Il est recommandé que vous apportez aucune modification à cette étape.</span><span class="sxs-lookup"><span data-stu-id="93e30-395">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="93e30-396">**Nom de l’ordinateur SRS défini**: cette étape inclut une application HTML pour fournir une interface utilisateur pour définir un nom d’ordinateur de l’unité de salles d’équipes Microsoft au cours du déploiement.</span><span class="sxs-lookup"><span data-stu-id="93e30-396">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="93e30-397">Il s’agit d’une étape facultative, mais elle peut être désactivée uniquement si vous souhaitez gérer l’ordinateur d’attribution de noms via un processus de substitution.</span><span class="sxs-lookup"><span data-stu-id="93e30-397">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="93e30-398">Vérifiez que le package **SRS v2 - Set-SRSComputerName** est activée.</span><span class="sxs-lookup"><span data-stu-id="93e30-398">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="93e30-399">Si elle n’est pas le cas, accédez au package et sélectionnez-le.</span><span class="sxs-lookup"><span data-stu-id="93e30-399">If it isn’t, browse to the package and select it.</span></span>

   4. <span data-ttu-id="93e30-400">**Appliquer un système d’exploitation**: cette étape spécifie l’image de système d’exploitation à déployer et le fichier de réponses Sysprep automatisé à utiliser.</span><span class="sxs-lookup"><span data-stu-id="93e30-400">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="93e30-401">Vérifiez que le fichier d’image de système d’exploitation Windows 10 entreprise approprié est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="93e30-401">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="93e30-402">Vérifiez que **utiliser une autonome ou le fichier de réponses Sysprep pour une installation personnalisée** est activée et le **SRS v2 - Sysprep Package** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="93e30-402">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="93e30-403">Vérifiez également que le **Nom de fichier** est définie sur **unattend.xml**.</span><span class="sxs-lookup"><span data-stu-id="93e30-403">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="93e30-404">**Appliquer les paramètres Windows**: cette étape rassemble des informations sur l’installation de Windows.</span><span class="sxs-lookup"><span data-stu-id="93e30-404">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="93e30-405">Fournissent des informations de gestion des licences et d’enregistrement, y compris la clé de produit, le mot de passe du compte administrateur local et le fuseau horaire (selon vos besoins).</span><span class="sxs-lookup"><span data-stu-id="93e30-405">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="93e30-406">**Appliquer les paramètres réseau**: cette étape vous permet de spécifier un groupe de travail ou le nom de domaine Active Directory et l’unité d’organisation.</span><span class="sxs-lookup"><span data-stu-id="93e30-406">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="93e30-407">Voir [domaine Skype salle système participer à des considérations](domain-joining-considerations.md) pour les mesures recommandées à suivre dans le déploiement des unités de salles d’équipes Microsoft en tant que membres d’un domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="93e30-407">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="93e30-408">**Appliquer les pilotes :** Cette étape et ses sous-étapes sont utilisés pour déployer des pilotes de périphériques et de microprogrammes basée sur le modèle de Surface Pro que vous avez.</span><span class="sxs-lookup"><span data-stu-id="93e30-408">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="93e30-409">Mettre à jour chaque étape pour spécifier le package de pilotes pertinents associé à ce déploiement.</span><span class="sxs-lookup"><span data-stu-id="93e30-409">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="93e30-410">Chaque package de pilote est configuré pour tirer parti des filtres Windows Management Instrumentation (WMI) pour déployer les pilotes pertinents et microprogramme en fonction de la Surface Pro marque et le modèle.</span><span class="sxs-lookup"><span data-stu-id="93e30-410">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="93e30-411">Nous vous recommandons vivement que vous ne modifiez pas la configuration de ces pilotes, sinon le déploiement peut échouer.</span><span class="sxs-lookup"><span data-stu-id="93e30-411">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="93e30-412">**Configurer Windows et le Gestionnaire de Configuration**: cette étape déploie et configure le client Gestionnaire de Configuration.</span><span class="sxs-lookup"><span data-stu-id="93e30-412">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="93e30-413">Mettre à jour cette étape pour spécifier le Package du Client Gestionnaire de Configuration intégrés.</span><span class="sxs-lookup"><span data-stu-id="93e30-413">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="93e30-414">**Installer le certificat racine**: cette étape distribue le certificat racine pour les périphériques non joints au domaine et par conséquent est facultative et désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="93e30-414">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="93e30-415">Activer cette étape si vous avez besoin déployer un certificat racine pour les unités de salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="93e30-415">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="93e30-416">Si vous n’avez pas besoin d’effectuer cette étape, vérifiez que le **SRS v2 – Package du certificat racine** et **redirection désactiver les 64 bits du système de fichiers** sont sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="93e30-416">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="93e30-417">**Installer et configurer l’Agent de surveillance**: cette étape installe la version 64 bits de l’agent Microsoft Azure Monitor et configure l’agent pour se connecter à votre espace de travail de journal Analytique.</span><span class="sxs-lookup"><span data-stu-id="93e30-417">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="93e30-418">Cette étape est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="93e30-418">This step is disabled by default.</span></span> <span data-ttu-id="93e30-419">Activez cette étape uniquement si vous prévoyez d’utiliser l’Agent de surveillance pour surveiller l’intégrité de vos unités de salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="93e30-419">Enable this step only if you’re going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="93e30-420">Modifier cette étape et mettre à jour les paramètres de ligne de commande pour spécifier votre **Clé de l’espace de travail**et **l’ID de l’espace de travail** .</span><span class="sxs-lookup"><span data-stu-id="93e30-420">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="93e30-421">Pour plus d’informations sur l’obtention de l’ID d’espace de travail Suite opérations de gestion et de la clé primaire, voir [configurer les dispositifs de surveillance Azure](azure-monitor.md#configure-test-devices-for-azure-monitoring) .</span><span class="sxs-lookup"><span data-stu-id="93e30-421">See [Configure test devices for Azure Monitoring](azure-monitor.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="93e30-422">Vérifiez que le **SRS v2 – Package de l’Agent de surveillance Microsoft** et **redirection désactiver les 64 bits du système de fichiers** sont sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="93e30-422">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="93e30-423">Pour plus d’informations sur la surveillance de l’intégrité de votre déploiement de salles d’équipes Microsoft, voir [gestion de planification Microsoft équipes salles avec Azure moniteur](../../plan-your-deployment/clients-and-devices/azure-monitor.md), [Gestion des salles d’équipes de déploiement Microsoft Azure moniteur](azure-monitor.md) et [gérer Microsoft Des équipes de périphériques de salles avec Azure moniteur](../../manage/skype-room-systems-v2/azure-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="93e30-423">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](../../plan-your-deployment/clients-and-devices/azure-monitor.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](../../manage/skype-room-systems-v2/azure-monitor.md).</span></span>

   11. <span data-ttu-id="93e30-424">**Fichiers de Configuration de copie SRS v2**: cette étape copie les fichiers requis du programme d’installation et de configuration à partir du kit de déploiement Microsoft équipes salles sur le disque dur local.</span><span class="sxs-lookup"><span data-stu-id="93e30-424">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="93e30-425">Aucune personnalisation n’est requise pour cette étape.</span><span class="sxs-lookup"><span data-stu-id="93e30-425">No customization is required for this step.</span></span>
       -   <span data-ttu-id="93e30-426">Vérifiez que le **SRS v2 – SRS Package d’Application** et **redirection désactiver les 64 bits du système de fichiers** sont sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="93e30-426">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="93e30-427">**Install-SRSv2-OS mises à jour**: cette étape déploie les mises à jour de système d’exploitation obligatoire requis avec le déploiement de salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="93e30-427">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="93e30-428">Procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="93e30-428">Do the following:</span></span>
       -   <span data-ttu-id="93e30-429">Vérifiez [Configure une console Microsoft équipes salles](console.md) pour voir les mises à jour sont nécessaires.</span><span class="sxs-lookup"><span data-stu-id="93e30-429">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="93e30-430">Vérifiez que votre **SRS v2 – Package de mises à jour du système d’exploitation** inclut toutes les mises à jour requises.</span><span class="sxs-lookup"><span data-stu-id="93e30-430">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="93e30-431">Vérifiez que le **SRS v2 – Package de mises à jour du système d’exploitation** est activée.</span><span class="sxs-lookup"><span data-stu-id="93e30-431">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="93e30-432">Vérifiez que la stratégie d’exécution PowerShell est définie sur **Ignorer**.</span><span class="sxs-lookup"><span data-stu-id="93e30-432">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="93e30-433">**Redémarrer l’ordinateur**: cette étape redémarre l’ordinateur une fois que les mises à jour de système d’exploitation obligatoires sont installés.</span><span class="sxs-lookup"><span data-stu-id="93e30-433">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="93e30-434">Aucune personnalisation n’est requise pour cette étape.</span><span class="sxs-lookup"><span data-stu-id="93e30-434">No customization is required for this step.</span></span>

   14. <span data-ttu-id="93e30-435">**Configurer les composants Windows**: cette étape configure les fonctionnalités Windows requises.</span><span class="sxs-lookup"><span data-stu-id="93e30-435">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="93e30-436">Aucune personnalisation n’est requise pour cette étape.</span><span class="sxs-lookup"><span data-stu-id="93e30-436">No customization is required for this step.</span></span>

   15. <span data-ttu-id="93e30-437">**Redémarrer l’ordinateur**: cette étape redémarre l’ordinateur après avoir configuré les fonctionnalités de Windows.</span><span class="sxs-lookup"><span data-stu-id="93e30-437">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="93e30-438">Aucune personnalisation n’est requise pour cette étape.</span><span class="sxs-lookup"><span data-stu-id="93e30-438">No customization is required for this step.</span></span>

   16. <span data-ttu-id="93e30-439">**Ajouter un utilisateur Local Skype**: cette étape crée le compte Skype local utilisé pour se connecter à Windows et démarrer l’application Microsoft équipes salles automatiquement.</span><span class="sxs-lookup"><span data-stu-id="93e30-439">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="93e30-440">Cette étape ne possède pas de tout logiciel associé, et aucune personnalisation n’est nécessaire pour qu’il.</span><span class="sxs-lookup"><span data-stu-id="93e30-440">This step doesn’t have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="93e30-441">**Définir vers le haut et configurer l’application SRS**: cette étape configure l’installation d’application salles d’équipes Microsoft pour le redémarrage du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="93e30-441">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="93e30-442">Vérifiez que le **SRS v2 – configurer un Package d’installation SRS** et **redirection désactiver les 64 bits du système de fichiers** sont sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="93e30-442">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="93e30-443">Il est très important que les étapes de séquence de tâches doivent être dans l’ordre indiqué.</span><span class="sxs-lookup"><span data-stu-id="93e30-443">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="93e30-444">Modification de l’ordre des étapes, ou la configuration des étapes supplémentaires peut empêcher le déploiement.</span><span class="sxs-lookup"><span data-stu-id="93e30-444">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="93e30-445">**Définir vers le haut et configurer l’application SRS** étape doit être la dernière étape de la séquence de tâches, sinon le déploiement peut échouer.</span><span class="sxs-lookup"><span data-stu-id="93e30-445">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="93e30-446">Créer le déploiement de la séquence de tâches</span><span class="sxs-lookup"><span data-stu-id="93e30-446">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="93e30-447">Sélectionnez la séquence de tâches, puis sélectionnez **déployer**.</span><span class="sxs-lookup"><span data-stu-id="93e30-447">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="93e30-448">Sélectionnez **Parcourir** pour sélectionner le regroupement cible pour le déploiement.</span><span class="sxs-lookup"><span data-stu-id="93e30-448">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="93e30-449">Sélectionnez **Tous les ordinateurs inconnus** , puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="93e30-449">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="93e30-450">Cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-450">Select **Next**.</span></span>

5. <span data-ttu-id="93e30-451">Dans la liste déroulante **objet** , sélectionnez **disponible** .</span><span class="sxs-lookup"><span data-stu-id="93e30-451">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="93e30-452">Sélectionnez **uniquement multimédia et PXE** dans la liste **mettre à disposition de ce qui suit** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-452">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="93e30-453">Il est très important que le **rôle** est défini sur **disponible**.</span><span class="sxs-lookup"><span data-stu-id="93e30-453">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="93e30-454">Assurez-vous que l' **objet** n’est **pas** la valeur **obligatoire**.</span><span class="sxs-lookup"><span data-stu-id="93e30-454">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="93e30-455">Assurez-vous également que vous sélectionnez **uniquement multimédia et PXE** dans le **rendre disponible pour les éléments suivants**.</span><span class="sxs-lookup"><span data-stu-id="93e30-455">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="93e30-456">Définition de ces valeurs à une chose risque de tous les ordinateurs obtenir l’image de déploiement Microsoft équipes salles lors du démarrage.</span><span class="sxs-lookup"><span data-stu-id="93e30-456">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="93e30-457">Ne pas spécifier un calendrier et cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-457">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="93e30-458">Ne pas modifier tous les éléments dans la section **Expérience utilisateur** et cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-458">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="93e30-459">Ne pas modifier tous les éléments dans la section **alertes** et cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-459">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="93e30-460">Ne pas modifier tous les éléments dans la section **Points de Distribution** et cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-460">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="93e30-461">Vérifier les paramètres, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-461">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="93e30-462">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="93e30-462">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="93e30-463">Valider et résoudre les problèmes de la solution</span><span class="sxs-lookup"><span data-stu-id="93e30-463">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="93e30-464">Après avoir réalisé les séquences de tâches System Center Configuration Manager, vous devez effectuer une série de tests pour valider que la séquence de tâches permettre déployer et configurer des unités de salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="93e30-464">After you’ve completed the System Center Configuration Manager task sequences, you’ll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="93e30-465">Connectez le périphérique de test au réseau câblé à l’aide d’une des cartes Ethernet pris en charge ou à l’aide de la surface d’exposition station d’accueil.</span><span class="sxs-lookup"><span data-stu-id="93e30-465">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="93e30-466">Si la fonctionnalité de démarrage PXE n’a pas été configurée pour votre environnement, vous pouvez utiliser l’image de démarrage sur la USB lecteur flash [que vous avez créé précédemment](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) pour démarrer à partir de USB et se connecter au Gestionnaire de Configuration.</span><span class="sxs-lookup"><span data-stu-id="93e30-466">If PXE boot functionality hasn’t been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="93e30-467">Accès du microprogramme et lancement de démarrage PXE :</span><span class="sxs-lookup"><span data-stu-id="93e30-467">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="93e30-468">Vérifiez que le périphérique Surface est éteint.</span><span class="sxs-lookup"><span data-stu-id="93e30-468">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="93e30-469">Maintenez le bouton **Volume** .</span><span class="sxs-lookup"><span data-stu-id="93e30-469">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="93e30-470">Appuyez puis relâchez le bouton **d’alimentation** .</span><span class="sxs-lookup"><span data-stu-id="93e30-470">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="93e30-471">Une fois le périphérique commence à démarrer, relâchez **le bouton** .</span><span class="sxs-lookup"><span data-stu-id="93e30-471">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="93e30-472">Sélectionnez **configuration de démarrage**.</span><span class="sxs-lookup"><span data-stu-id="93e30-472">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="93e30-473">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="93e30-473">Do one of the following:</span></span>

        -   <span data-ttu-id="93e30-474">Sélectionnez **démarrage PXE**et faites-le glisser vers le haut de la liste.</span><span class="sxs-lookup"><span data-stu-id="93e30-474">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="93e30-475">Vous pouvez également, faites glisser gauche sur la carte réseau pour qu’il démarre immédiatement à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="93e30-475">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="93e30-476">Cela n’affecte pas l’ordre de démarrage.</span><span class="sxs-lookup"><span data-stu-id="93e30-476">This won’t affect the boot order.</span></span>
        -   <span data-ttu-id="93e30-477">Sélectionnez le lecteur flash USB qui contient le support de démarrage.</span><span class="sxs-lookup"><span data-stu-id="93e30-477">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="93e30-478">Sélectionnez **Quitter**, puis sélectionnez **Redémarrer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-478">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="93e30-479">Lorsque vous y êtes invité, sélectionnez **l’entrée** pour le service de démarrage réseau.</span><span class="sxs-lookup"><span data-stu-id="93e30-479">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="93e30-480">Windows PE sont chargées en mémoire et démarre l’Assistant de séquence de tâches.</span><span class="sxs-lookup"><span data-stu-id="93e30-480">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="93e30-481">Sélectionnez **suivant** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="93e30-481">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="93e30-482">Sélectionnez la séquence de tâches que vous avez importé précédemment, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="93e30-482">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="93e30-483">Une fois la configuration du disque est appliquée, vous devrez spécifier un nom d’ordinateur pour le périphérique.</span><span class="sxs-lookup"><span data-stu-id="93e30-483">After the disk configuration is applied, you’ll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="93e30-484">L’interface utilisateur affiche un nom d’ordinateur recommandée en fonction du numéro de série du périphérique Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="93e30-484">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="93e30-485">Vous pouvez accepter le nom proposé ou spécifier un autre.</span><span class="sxs-lookup"><span data-stu-id="93e30-485">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="93e30-486">Suivez les instructions à l’écran d’affectation de nom.</span><span class="sxs-lookup"><span data-stu-id="93e30-486">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="93e30-487">Lorsque vous sélectionnez **Accepter**, le déploiement commence.</span><span class="sxs-lookup"><span data-stu-id="93e30-487">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="93e30-488">Le reste du processus de déploiement est automatique et ne demandez plus d’entrées utilisateur.</span><span class="sxs-lookup"><span data-stu-id="93e30-488">The rest of the deployment process is automatic and doesn’t ask for any more user input.</span></span>

9.  <span data-ttu-id="93e30-489">Une fois que la séquence de tâches de déploiement a terminé la configuration du périphérique, vous verrez l’écran configuration suivant qui vous demande de configurer les paramètres d’application salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="93e30-489">After the deployment task sequence finishes configuring the device, you’ll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![Écran initial d’installation pour application de salles d’équipes Microsoft](../../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="93e30-491">Branchez la Surface Pro dans la console de salles d’équipes Microsoft et configurez les paramètres d’application.</span><span class="sxs-lookup"><span data-stu-id="93e30-491">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="93e30-492">Valider que les fonctionnalités répertoriées dans les [salles d’équipes Microsoft aide](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) fonctionne sur les appareils mobiles déployés.</span><span class="sxs-lookup"><span data-stu-id="93e30-492">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="93e30-493">Pour résoudre un échec de l’installation, vérifiez le fichier **SMSTS.log** , qui enregistre toutes les étapes exécutées dans une séquence de tâches du Gestionnaire de Configuration.</span><span class="sxs-lookup"><span data-stu-id="93e30-493">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="93e30-494">Le fichier SMSTS.log est stocké sur un d’un nombre de chemins d’accès, en fonction de l’étape du processus de génération.</span><span class="sxs-lookup"><span data-stu-id="93e30-494">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="93e30-495">Consultez le tableau suivant pour identifier le chemin d’accès au fichier SMSTS.log.</span><span class="sxs-lookup"><span data-stu-id="93e30-495">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="93e30-496">**Phase de déploiement**</span><span class="sxs-lookup"><span data-stu-id="93e30-496">**Deployment phase**</span></span>                                                            | <span data-ttu-id="93e30-497">**Chemin d’accès de tâche séquence journal**</span><span class="sxs-lookup"><span data-stu-id="93e30-497">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="93e30-498">WinPE, avant le format du disque dur</span><span class="sxs-lookup"><span data-stu-id="93e30-498">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="93e30-499">X :\\Windows\\Temp\\smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="93e30-499">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="93e30-500">WinPE, après le format du disque dur</span><span class="sxs-lookup"><span data-stu-id="93e30-500">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="93e30-501">C :\\_SMSTaskSequence\\journaux\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="93e30-501">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="93e30-502">Système d’exploitation déployé, avant l’installation de l’agent de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="93e30-502">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="93e30-503">c :\\_SMSTaskSequence\\journaux\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="93e30-503">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="93e30-504">Système d’exploitation et l’agent de gestionnaire de Configuration déployé</span><span class="sxs-lookup"><span data-stu-id="93e30-504">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="93e30-505">%windir%\\System32\\ccm\\journaux\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="93e30-505">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="93e30-506">Complète de l’exécution de la séquence de tâches</span><span class="sxs-lookup"><span data-stu-id="93e30-506">Task sequence execution complete</span></span>                                                | <span data-ttu-id="93e30-507">%windir%\\System32\\ccm\\journaux\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="93e30-507">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="93e30-508">Vous pouvez sélectionner **F8** à tout moment au cours de la séquence de tâches pour ouvrir une console de commande et accéder au fichier SMSTS.log.</span><span class="sxs-lookup"><span data-stu-id="93e30-508">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="93e30-509">Pour résoudre les problèmes de démarrage PXE, vérifiez les deux fichiers journaux sur le serveur du Gestionnaire de Configuration qui sont spécifiques aux actions PXE :</span><span class="sxs-lookup"><span data-stu-id="93e30-509">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="93e30-510">**Pxecontrol.log**, situé dans le répertoire de journaux d’installation Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="93e30-510">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="93e30-511">**Smspxe.log**, situé dans le répertoire des journaux de Point de gestion Configuration Manager (MP)</span><span class="sxs-lookup"><span data-stu-id="93e30-511">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="93e30-512">Pour obtenir une liste complète des fichiers journaux que vous pouvez utiliser pour résoudre l’installation du Gestionnaire de Configuration, voir [fichiers journaux dans System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span><span class="sxs-lookup"><span data-stu-id="93e30-512">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>

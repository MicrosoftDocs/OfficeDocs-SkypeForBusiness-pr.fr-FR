---
title: Déployer des salles Microsoft Teams à l’aide de Microsoft Endpoint Configuration Manager
author: dstrome
ms.author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: Découvrez comment déployer des salles Microsoft Teams dans le cadre de déploiements à grande échelle à l’aide de Microsoft Endpoint Configuration Manager.
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
ms.openlocfilehash: 2348d0f3e9d94aed80494155fbaab8288ddd97a6
ms.sourcegitcommit: 95386369e2256ba382b4d6e34adb7473de050b26
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/29/2021
ms.locfileid: "51410110"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="8cce9-103">Déployer des salles Microsoft Teams à l’aide de Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8cce9-103">Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="8cce9-104">Cet article vous fournit toutes les informations nécessaires à la création de déploiements de salles Microsoft Teams à l’aide de Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="8cce9-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="8cce9-105">Grâce aux méthodes simples d’utilisation fournies par Configuration Manager, vous pouvez déployer le système d’exploitation et d’autres applications sur plusieurs appareils cibles.</span><span class="sxs-lookup"><span data-stu-id="8cce9-105">With the easy-to-use methods provided by Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="8cce9-106">Utilisez l’approche illustrée ci-dessous pour vous guider tout au long de votre configuration de Configuration Manager et personnaliser les exemples de packages et de scripts fournis dans le cadre de ces instructions, selon les besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8cce9-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Processus de déploiement de salles Microsoft Teams à l’aide de Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="8cce9-108">Cette solution n’a été testée qu’avec les déploiements de Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="8cce9-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="8cce9-109">Suivez les instructions du fabricant pour les configurations qui ne sont pas basées sur Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="8cce9-109">Follow the manufacturer's guidelines for configurations that aren't based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="8cce9-110">Valider les conditions préalables</span><span class="sxs-lookup"><span data-stu-id="8cce9-110">Validate prerequisites</span></span>

<span data-ttu-id="8cce9-111">Pour déployer des salles Microsoft Teams avec Configuration Manager, assurez-vous que vous respectez les conditions préalables et requises suivantes.</span><span class="sxs-lookup"><span data-stu-id="8cce9-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="microsoft-endpoint-configuration-manager-requirements"></a><span data-ttu-id="8cce9-112">Configuration requise pour Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8cce9-112">Microsoft Endpoint Configuration Manager requirements</span></span>

-   <span data-ttu-id="8cce9-113">La version de Microsoft Endpoint Configuration Manager doit être au moins 1706.</span><span class="sxs-lookup"><span data-stu-id="8cce9-113">Microsoft Endpoint Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="8cce9-114">Nous vous recommandons d’utiliser 1710 ou une date ultérieure.</span><span class="sxs-lookup"><span data-stu-id="8cce9-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="8cce9-115">Consultez [la prise en charge de Windows 10 dans Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) pour en savoir plus sur les versions de Windows 10 que Configuration Manager prend en charge.</span><span class="sxs-lookup"><span data-stu-id="8cce9-115">Check out [Support for Windows 10 in Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="8cce9-116">Une version prise en charge du Kit de déploiement et d’évaluation windows (ADK) pour Windows 10 doit être installée.</span><span class="sxs-lookup"><span data-stu-id="8cce9-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="8cce9-117">Consultez les versions de [Windows 10 ADK](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) que vous pouvez utiliser avec différentes versions de Configuration Manager et assurez-vous que votre déploiement inclut la version correcte.</span><span class="sxs-lookup"><span data-stu-id="8cce9-117">See the versions of the [Windows 10 ADK](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="8cce9-118">Le rôle de point de distribution doit avoir été attribué aux serveurs système de site et les images de démarrage doivent être activées pour la prise en charge de l’environnement d’exécution de [préboot (PXE)](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) pour permettre les déploiements initiés par le réseau.</span><span class="sxs-lookup"><span data-stu-id="8cce9-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="8cce9-119">Si la prise en charge de PXE n’est pas activée, vous pouvez utiliser un support [démarrageable](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) pour vos déploiements.</span><span class="sxs-lookup"><span data-stu-id="8cce9-119">If PXE support isn't enabled, you can use [bootable media](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="8cce9-120">Un compte d’accès réseau doit être configuré pour prendre en charge de nouveaux scénarios de déploiement d’ordinateurs (métal métallique).</span><span class="sxs-lookup"><span data-stu-id="8cce9-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="8cce9-121">Pour en savoir plus sur la configuration d’un compte d’accès réseau, voir [Comptes utilisés dans Configuration Manager.](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)</span><span class="sxs-lookup"><span data-stu-id="8cce9-121">To learn more about the configuration of a network access account, see [Accounts used in Configuration Manager](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="8cce9-122">Nous vous recommandons d’activer la prise en charge [multicast,](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)si vous êtes susceptible de déployer la même image salles Microsoft Teams sur plusieurs unités en même temps.</span><span class="sxs-lookup"><span data-stu-id="8cce9-122">We recommend that you enable [multicast support](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you're likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="8cce9-123">Conditions requises pour la mise en réseau</span><span class="sxs-lookup"><span data-stu-id="8cce9-123">Networking requirements</span></span>

-   <span data-ttu-id="8cce9-124">Votre réseau doit avoir un serveur DHCP (Dynamic Host Configuration Protocol), configuré pour la distribution automatique d’adresses IP sur les sous-réseaux où les unités de Salles Microsoft Teams seront déployées.</span><span class="sxs-lookup"><span data-stu-id="8cce9-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8cce9-125">La durée du contrat de location DHCP doit être définie sur une valeur plus longue que la durée du déploiement d’images.</span><span class="sxs-lookup"><span data-stu-id="8cce9-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="8cce9-126">Dans le cas contraire, le déploiement peut échouer.</span><span class="sxs-lookup"><span data-stu-id="8cce9-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="8cce9-127">Votre réseau, y compris les commutateurs et les réseaux lan virtuels (VLAN), doit être configuré pour prendre en charge PXE.</span><span class="sxs-lookup"><span data-stu-id="8cce9-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="8cce9-128">Pour plus d’informations sur les configurations IP Helper et PXE, reportez-vous à votre fournisseur réseau.</span><span class="sxs-lookup"><span data-stu-id="8cce9-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="8cce9-129">Vous pouvez également utiliser un support [qui](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) démarre pour vos déploiements, si la prise en charge de PXE n’est pas activée.</span><span class="sxs-lookup"><span data-stu-id="8cce9-129">Alternatively, you can use [bootable media](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn't enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8cce9-130">Pour les appareils Surface Pro, le démarrage à partir du réseau (démarrage PXE) n’est pris en charge que lorsque vous utilisez un adaptateur Ethernet ou une station d’accueil microsoft.</span><span class="sxs-lookup"><span data-stu-id="8cce9-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="8cce9-131">Les cartes Ethernet tierces ne supportent pas le démarrage PXE avec Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="8cce9-131">Third-party Ethernet adapters don't support PXE boot with Surface Pro.</span></span> <span data-ttu-id="8cce9-132">Pour [plus d’informations,](/surface/ethernet-adapters-and-surface-device-deployment) voir les cartes Ethernet et le déploiement de Surface.</span><span class="sxs-lookup"><span data-stu-id="8cce9-132">See [Ethernet adapters and Surface deployment](/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="8cce9-133">Configurer Microsoft Endpoint Configuration Manager pour le déploiement du système d’exploitation</span><span class="sxs-lookup"><span data-stu-id="8cce9-133">Configure Microsoft Endpoint Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="8cce9-134">Cet article part du principe que vous avez déjà un déploiement de Configuration Manager sain et ne détaille pas toutes les étapes requises pour déployer et configurer Configuration Manager de toutes pièces.</span><span class="sxs-lookup"><span data-stu-id="8cce9-134">This article assumes you already have a healthy Configuration Manager deployment, and doesn't detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="8cce9-135">La [documentation et les instructions de configuration de](/configmgr/) Microsoft Endpoint Configuration Manager sont très pertinentes. nous vous recommandons de commencer avec ces ressources si vous n’avez pas encore déployé Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="8cce9-135">The [documentation and the configuration guidance](/configmgr/) on the Microsoft Endpoint Configuration Manager is a great resource; we recommend you start with these resources if you haven't yet deployed Configuration Manager.</span></span>

<span data-ttu-id="8cce9-136">Utilisez les instructions suivantes pour vérifier que les fonctionnalités de déploiement du système d’exploitation sont correctement configurées.</span><span class="sxs-lookup"><span data-stu-id="8cce9-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="8cce9-137">Valider et mettre à niveau Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8cce9-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="8cce9-138">Dans la console Configuration Manager, sélectionnez Mises à jour **d’administration** \> **et Maintenance.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="8cce9-139">Vérifiez la build installée et les mises à jour applicables qui n’ont pas encore été installées.</span><span class="sxs-lookup"><span data-stu-id="8cce9-139">Check the installed build and applicable updates that haven't been installed yet.</span></span>

3.  <span data-ttu-id="8cce9-140">Examinez [la prise en charge de Windows 10 dans Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client). si vous avez besoin de mettre à niveau votre déploiement, sélectionnez la mise à jour que vous voulez installer, puis sélectionnez **Télécharger.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-140">Review [Support for Windows 10 in Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="8cce9-141">Une fois le téléchargement terminé, sélectionnez la mise à jour, puis sélectionnez **Installer le pack de mise à jour.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="8cce9-142">Configurer des points de distribution pour prendre en charge PXE et multicast</span><span class="sxs-lookup"><span data-stu-id="8cce9-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="8cce9-143">Dans la console Configuration Manager, sélectionnez **Points de** \> **distribution** Administration.</span><span class="sxs-lookup"><span data-stu-id="8cce9-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="8cce9-144">Sélectionnez le serveur de points de distribution qui servira au déploiement de salles Microsoft Teams, puis sélectionnez **Propriétés.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="8cce9-145">Sélectionnez **l’onglet PXE** et assurez-vous que les paramètres suivants sont activés :</span><span class="sxs-lookup"><span data-stu-id="8cce9-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="8cce9-146">Activer la prise en charge PXE pour les clients</span><span class="sxs-lookup"><span data-stu-id="8cce9-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="8cce9-147">Autoriser ce point de distribution à répondre aux demandes PXE entrantes</span><span class="sxs-lookup"><span data-stu-id="8cce9-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="8cce9-148">Activer le support informatique inconnu</span><span class="sxs-lookup"><span data-stu-id="8cce9-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="8cce9-149">*Facultatif :* Pour activer la prise en charge **multicast,** sélectionnez l’onglet Multicast et assurez-vous que les paramètres suivants sont activés :</span><span class="sxs-lookup"><span data-stu-id="8cce9-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="8cce9-150">Activer la multicast pour envoyer simultanément des données à plusieurs clients</span><span class="sxs-lookup"><span data-stu-id="8cce9-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="8cce9-151">Configurer la plage de ports UDP selon les recommandations de votre équipe réseau</span><span class="sxs-lookup"><span data-stu-id="8cce9-151">Configure the UDP port range as per your network team's recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="8cce9-152">Configurer le compte d’accès réseau</span><span class="sxs-lookup"><span data-stu-id="8cce9-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="8cce9-153">Dans la console Configuration  Manager, allez sur Sites de configuration du \> **site** \> Administration, puis sélectionnez le site.</span><span class="sxs-lookup"><span data-stu-id="8cce9-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="8cce9-154">Dans le **groupe Paramètres,** **sélectionnez Configurer la distribution de logiciels de composants de** \> **site.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="8cce9-155">Sélectionnez **l’onglet Compte d’accès** réseau. Configurer un ou plusieurs comptes, puis sélectionner **OK.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="8cce9-156">Les comptes n’ont pas besoin de droits spéciaux, à l’exception de **l’ordinateur Access** de ce réseau, directement sur le serveur du point de distribution.</span><span class="sxs-lookup"><span data-stu-id="8cce9-156">The accounts don't need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="8cce9-157">Un compte d’utilisateur de domaine générique sera approprié.</span><span class="sxs-lookup"><span data-stu-id="8cce9-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="8cce9-158">Pour plus d’informations, voir [Comptes utilisés dans Configuration Manager.](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)</span><span class="sxs-lookup"><span data-stu-id="8cce9-158">For more information, see [Accounts used in Configuration Manager](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="8cce9-159">Configurer une image de démarrage</span><span class="sxs-lookup"><span data-stu-id="8cce9-159">Configure a boot image</span></span>

1.  <span data-ttu-id="8cce9-160">Dans la console Configuration Manager, sélectionnez **Images de** démarrage du système d’exploitation \> **Bibliothèque** \> **de logiciels.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="8cce9-161">Sélectionnez **Image de démarrage (x64),** puis **Propriétés.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="8cce9-162">Sélectionnez **l’onglet Source** de données et **activez l’image** de démarrage à partir du point de distribution activé pour PXE.</span><span class="sxs-lookup"><span data-stu-id="8cce9-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="8cce9-163">Sélectionnez **l’onglet Composants facultatifs** pour installer les composants requis :</span><span class="sxs-lookup"><span data-stu-id="8cce9-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="8cce9-164">Sélectionnez l’icône d’étoile et **recherchez HTML (WinPE-HTA)**</span><span class="sxs-lookup"><span data-stu-id="8cce9-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="8cce9-165">Sélectionnez **OK** pour ajouter la prise en charge de l’application HTML à l’image de démarrage.</span><span class="sxs-lookup"><span data-stu-id="8cce9-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="8cce9-166">*Facultatif :* Pour personnaliser l’expérience de déploiement, sélectionnez **l’onglet Personnalisation.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="8cce9-167">Activez la prise en charge des commandes **(test uniquement)** si vous voulez avoir accès à une invite de commandes pendant le déploiement.</span><span class="sxs-lookup"><span data-stu-id="8cce9-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="8cce9-168">Lorsque cette commande est activée, vous pouvez démarrer une invite de commandes en sélectionnant **F8** à tout moment pendant le déploiement.</span><span class="sxs-lookup"><span data-stu-id="8cce9-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="8cce9-169">Vous pouvez également spécifier une image d’arrière-plan personnalisée à afficher pendant le déploiement.</span><span class="sxs-lookup"><span data-stu-id="8cce9-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="8cce9-170">Pour définir une image, activez Spécifier le fichier d’image d’arrière-plan **personnalisé (chemin UNC et** sélectionner votre arrière-plan).</span><span class="sxs-lookup"><span data-stu-id="8cce9-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="8cce9-171">Lorsque vous y avez été invité, **sélectionnez Oui** et distribuez l’image de démarrage mise à jour à vos points de distribution.</span><span class="sxs-lookup"><span data-stu-id="8cce9-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="8cce9-172">Pour plus d’informations, voir [Gérer les images de démarrage avec Configuration Manager.](/configmgr/osd/get-started/manage-boot-images)</span><span class="sxs-lookup"><span data-stu-id="8cce9-172">For more information, see [Manage boot images with Configuration Manager](/configmgr/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="8cce9-173">Vous pouvez créer un support USB en démarrage pour initier des déploiements de séquence de tâches dans Configuration Manager pour les environnements sans prise en charge PXE.</span><span class="sxs-lookup"><span data-stu-id="8cce9-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="8cce9-174">Le support de démarrage contient uniquement l’image de démarrage, les commandes de prédétrage facultatives et les fichiers requis, et les fichiers binaires de Configuration Manager pour prendre en charge le démarrage dans Windows PE et la connexion à Configuration Manager pour le reste du processus de déploiement.</span><span class="sxs-lookup"><span data-stu-id="8cce9-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="8cce9-175">Pour plus d’informations, voir [Créer un média qui peut être démarré.](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)</span><span class="sxs-lookup"><span data-stu-id="8cce9-175">For more information, see [Create bootable media](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="8cce9-176">Créer des packages Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8cce9-176">Create Configuration Manager packages</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8cce9-177">La version requise du système d’exploitation pour chaque version du programme d’installation SRS change à chaque publication MSI.</span><span class="sxs-lookup"><span data-stu-id="8cce9-177">The required operating system version for each SRS installer version changes with every MSI release.</span></span> <span data-ttu-id="8cce9-178">Pour déterminer la meilleure version du système d’exploitation pour un MSI donné, exécutez le script de configuration de la console une seule fois.</span><span class="sxs-lookup"><span data-stu-id="8cce9-178">To determine the best operating system version for a given MSI, run the console setup script once.</span></span> <span data-ttu-id="8cce9-179">Pour en savoir plus, [consultez Déployer des salles Microsoft Teams à l’aide de Microsoft Endpoint Configuration Manager.](rooms-scale.md)</span><span class="sxs-lookup"><span data-stu-id="8cce9-179">To learn more, see [Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager](rooms-scale.md).</span></span>

<span data-ttu-id="8cce9-180">Configuration Manager nécessite un certain nombre de packages pour déployer et configurer les unités de salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8cce9-180">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="8cce9-181">Vous devez créer et configurer les packages suivants, puis les distribuer aux systèmes de site Configuration Manager qui ont reçu le rôle de serveur de point de distribution.</span><span class="sxs-lookup"><span data-stu-id="8cce9-181">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="8cce9-182">**Nom du package**</span><span class="sxs-lookup"><span data-stu-id="8cce9-182">**Package name**</span></span>                     | <span data-ttu-id="8cce9-183">**Type**</span><span class="sxs-lookup"><span data-stu-id="8cce9-183">**Type**</span></span>               | <span data-ttu-id="8cce9-184">**Description**</span><span class="sxs-lookup"><span data-stu-id="8cce9-184">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="8cce9-185">SRS v2 - Package d’application SRS</span><span class="sxs-lookup"><span data-stu-id="8cce9-185">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="8cce9-186">Package logiciel</span><span class="sxs-lookup"><span data-stu-id="8cce9-186">Software package</span></span>       | <span data-ttu-id="8cce9-187">Package du kit de déploiement de Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8cce9-187">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="8cce9-188">SRS v2 - Sysprep Package</span><span class="sxs-lookup"><span data-stu-id="8cce9-188">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="8cce9-189">Package logiciel</span><span class="sxs-lookup"><span data-stu-id="8cce9-189">Software package</span></span>       | <span data-ttu-id="8cce9-190">Package pour l’équipe Unattended.xml pour configurer les unités des salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8cce9-190">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="8cce9-191">SRS v2 - Set-SRSComputerName Package</span><span class="sxs-lookup"><span data-stu-id="8cce9-191">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="8cce9-192">Package logiciel</span><span class="sxs-lookup"><span data-stu-id="8cce9-192">Software package</span></span>       | <span data-ttu-id="8cce9-193">Package pour l’application HTML (HTA) pour affecter un nom d’ordinateur pendant le déploiement</span><span class="sxs-lookup"><span data-stu-id="8cce9-193">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="8cce9-194">SRS v2 - Configurer la configuration SRS</span><span class="sxs-lookup"><span data-stu-id="8cce9-194">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="8cce9-195">Package logiciel</span><span class="sxs-lookup"><span data-stu-id="8cce9-195">Software package</span></span>       | <span data-ttu-id="8cce9-196">Package pour configurer le déploiement de l’application Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8cce9-196">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="8cce9-197">SRS v2 - Package de mises à jour du système d’exploitation</span><span class="sxs-lookup"><span data-stu-id="8cce9-197">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="8cce9-198">Package logiciel</span><span class="sxs-lookup"><span data-stu-id="8cce9-198">Software package</span></span>       | <span data-ttu-id="8cce9-199">Package pour déployer des mises à jour de système d’exploitation obligatoires</span><span class="sxs-lookup"><span data-stu-id="8cce9-199">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="8cce9-200">SRS v2 - Package de certificat racine</span><span class="sxs-lookup"><span data-stu-id="8cce9-200">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="8cce9-201">Package logiciel</span><span class="sxs-lookup"><span data-stu-id="8cce9-201">Software package</span></span>       | <span data-ttu-id="8cce9-202">Facultatif - Package pour déployer le certificat racine (non requis pour les unités jointes au domaine)</span><span class="sxs-lookup"><span data-stu-id="8cce9-202">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="8cce9-203">SRS v2 - Package de l’Agent de surveillance Microsoft</span><span class="sxs-lookup"><span data-stu-id="8cce9-203">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="8cce9-204">Package logiciel</span><span class="sxs-lookup"><span data-stu-id="8cce9-204">Software package</span></span>       | <span data-ttu-id="8cce9-205">Facultatif - Package pour déployer et configurer l’agent de la suite Microsoft Operations Management</span><span class="sxs-lookup"><span data-stu-id="8cce9-205">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="8cce9-206">SRS v2 - Package d’arrière-plan WinPE</span><span class="sxs-lookup"><span data-stu-id="8cce9-206">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="8cce9-207">Package logiciel</span><span class="sxs-lookup"><span data-stu-id="8cce9-207">Software package</span></span>       | <span data-ttu-id="8cce9-208">Package pour l’image d’arrière-plan personnalisée à utiliser avec les images de démarrage</span><span class="sxs-lookup"><span data-stu-id="8cce9-208">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="8cce9-209">Windows 10 Entreprise</span><span class="sxs-lookup"><span data-stu-id="8cce9-209">Windows 10 Enterprise</span></span>                | <span data-ttu-id="8cce9-210">Image du système d’exploitation</span><span class="sxs-lookup"><span data-stu-id="8cce9-210">Operating system image</span></span> | <span data-ttu-id="8cce9-211">Package pour le fichier d’installation du système d’exploitation (install.wim)</span><span class="sxs-lookup"><span data-stu-id="8cce9-211">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="8cce9-212">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="8cce9-212">Surface Pro</span></span>                          | <span data-ttu-id="8cce9-213">Package du pilote</span><span class="sxs-lookup"><span data-stu-id="8cce9-213">Driver package</span></span>         | <span data-ttu-id="8cce9-214">Package pour les pilotes de périphérique et microprogramme pour Microsoft Surface Pro</span><span class="sxs-lookup"><span data-stu-id="8cce9-214">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="8cce9-215">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="8cce9-215">Surface Pro 4</span></span>                        | <span data-ttu-id="8cce9-216">Package du pilote</span><span class="sxs-lookup"><span data-stu-id="8cce9-216">Driver package</span></span>         | <span data-ttu-id="8cce9-217">Package pour les pilotes de périphérique et microprogramme pour Microsoft Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="8cce9-217">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="8cce9-218">Pour plus d’informations, voir [Packages et programmes dans Configuration Manager.](/configmgr/apps/deploy-use/packages-and-programs)</span><span class="sxs-lookup"><span data-stu-id="8cce9-218">For more information, see [Packages and programs in Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="8cce9-219">Créer des dossiers pour les fichiers source du package</span><span class="sxs-lookup"><span data-stu-id="8cce9-219">Create folders for the package source files</span></span>

<span data-ttu-id="8cce9-220">Configuration Manager nécessite que les fichiers source de package soient organisés dans une structure de dossiers spécifique lors de leur création et de leur mise à jour.</span><span class="sxs-lookup"><span data-stu-id="8cce9-220">Configuration Manager requires package source files to be organized in a specific folder structure when they're first created and when they're updated.</span></span>

<span data-ttu-id="8cce9-221">Créez la structure de dossiers suivante sur le site d’administration centrale ou le site principal de Microsoft Endpoint Configuration Manager, ou sur un partage serveur que vous utilisez pour héberger des fichiers source de package :</span><span class="sxs-lookup"><span data-stu-id="8cce9-221">Create the following folder structure on the Microsoft Endpoint Configuration Manager central administration site or primary site, or on a server share you're using to host package source files:</span></span>

-   <span data-ttu-id="8cce9-222">SRS v2 - Package de l’Agent de surveillance Microsoft</span><span class="sxs-lookup"><span data-stu-id="8cce9-222">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="8cce9-223">SRS v2 - Package de mises à jour du système d’exploitation</span><span class="sxs-lookup"><span data-stu-id="8cce9-223">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="8cce9-224">SRS v2 - Package de certificat racine</span><span class="sxs-lookup"><span data-stu-id="8cce9-224">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="8cce9-225">SRS v2 - Set-SRSComputerName Package</span><span class="sxs-lookup"><span data-stu-id="8cce9-225">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="8cce9-226">SRS v2 - Package d’application SRS</span><span class="sxs-lookup"><span data-stu-id="8cce9-226">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="8cce9-227">SRS v2 - Configurer la configuration SRS</span><span class="sxs-lookup"><span data-stu-id="8cce9-227">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="8cce9-228">SRS v2 - Sysprep Package</span><span class="sxs-lookup"><span data-stu-id="8cce9-228">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="8cce9-229">Pilotes</span><span class="sxs-lookup"><span data-stu-id="8cce9-229">Drivers</span></span>
    -   <span data-ttu-id="8cce9-230">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="8cce9-230">Surface Pro</span></span>
    -   <span data-ttu-id="8cce9-231">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="8cce9-231">Surface Pro 4</span></span>
-   <span data-ttu-id="8cce9-232">Systèmes d’exploitation</span><span class="sxs-lookup"><span data-stu-id="8cce9-232">Operating Systems</span></span>
    -   <span data-ttu-id="8cce9-233">Windows 10 Entreprise</span><span class="sxs-lookup"><span data-stu-id="8cce9-233">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="8cce9-234">Vous pouvez [](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) également télécharger et utiliser le fichier zip qui inclut la structure des dossiers pour les packages, les scripts que vous devez utiliser et le modèle de séquence des tâches, que vous devez importer.</span><span class="sxs-lookup"><span data-stu-id="8cce9-234">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="8cce9-235">Créer le package de l’agent de surveillance</span><span class="sxs-lookup"><span data-stu-id="8cce9-235">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="8cce9-236">Téléchargez l’Agent de surveillance à partir <https://go.microsoft.com/fwlink/?LinkId=828603> de .</span><span class="sxs-lookup"><span data-stu-id="8cce9-236">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="8cce9-237">Extrayez le package dans le **dossier SRS v2 - Package** de l’Agent de surveillance Microsoft en ouvrant une fenêtre d’invite de commandes et enMMASetup-AMD64.exe **/C:**     à l’invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="8cce9-237">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="8cce9-238">Dans la console Configuration Manager, sélectionnez **Packages** de gestion d’application de bibliothèque de \>  \> **logiciels,** puis **sélectionnez Créer un package.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-238">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="8cce9-239">Entrez les informations suivantes pour créer le package :</span><span class="sxs-lookup"><span data-stu-id="8cce9-239">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="8cce9-240">Nom<strong>: SRS v2 - Package de l’Agent de surveillance Microsoft</strong></span><span class="sxs-lookup"><span data-stu-id="8cce9-240">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="8cce9-241">Fabricant<strong>: Microsoft Corporation</strong></span><span class="sxs-lookup"><span data-stu-id="8cce9-241">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="8cce9-242">Version<strong>: 8.1.11081.0</strong> (entrez la version du fichier d’installation téléchargé)</span><span class="sxs-lookup"><span data-stu-id="8cce9-242">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="8cce9-243">Cochez la case Ce package contient les fichiers **sources,** entrez le chemin d’accès au **dossier SRS v2 - Package** de l’Agent de surveillance Microsoft, puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-243">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="8cce9-244">Sélectionnez **Ne pas créer un programme,** puis **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-244">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="8cce9-245">Examinez la page **Confirmer les paramètres,** puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-245">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="8cce9-246">Sélectionnez **Fermer.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-246">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="8cce9-247">Créer le package de mises à jour du système d’exploitation</span><span class="sxs-lookup"><span data-stu-id="8cce9-247">Create the operating system updates package</span></span>

1. <span data-ttu-id="8cce9-248">Dans le **dossier SRS v2 - Mises** à jour du package du système d’exploitation, créez un script PowerShell nommé **Install-SRSv2-OS-Updates.ps1.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-248">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="8cce9-249">Copiez le script ci-dessous **dansInstall-SRSv2-OS-Updates.ps1** script.</span><span class="sxs-lookup"><span data-stu-id="8cce9-249">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="8cce9-250">Vous pouvez également télécharger le script d'Install-SRSv2-OS-Updates.ps1 [ici.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="8cce9-250">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="8cce9-251">Téléchargez les packages Windows Update obligatoires dans le même dossier.</span><span class="sxs-lookup"><span data-stu-id="8cce9-251">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="8cce9-252">Lors de la publication de cet article, seule la mise à niveau [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) était requise.</span><span class="sxs-lookup"><span data-stu-id="8cce9-252">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="8cce9-253">Vérifiez [la configuration d’une console salles Microsoft Teams](console.md)pour voir si d’autres mises à jour sont requises.</span><span class="sxs-lookup"><span data-stu-id="8cce9-253">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="8cce9-254">Dans la console Configuration Manager, sélectionnez **Packages** de gestion d’application de bibliothèque de \>  \> **logiciels,** puis **sélectionnez Créer un package.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-254">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="8cce9-255">Entrez les informations suivantes pour créer le package :</span><span class="sxs-lookup"><span data-stu-id="8cce9-255">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="8cce9-256">Nom : **SRS v2 – Package de mises à jour du système d’exploitation**</span><span class="sxs-lookup"><span data-stu-id="8cce9-256">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="8cce9-257">Fabricant : **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="8cce9-257">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="8cce9-258">Version : **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="8cce9-258">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="8cce9-259">Cochez la case Ce package contient les fichiers **sources,** entrez le chemin d’accès au dossier **SRS v2 - Mises** à jour du système d’exploitation, puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-259">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="8cce9-260">Sélectionnez **Ne pas créer un programme,** puis **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-260">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="8cce9-261">Examinez la page **Confirmer les paramètres,** puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-261">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="8cce9-262">Sélectionnez **Fermer.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-262">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="8cce9-263">Créer le package de certificat racine (facultatif)</span><span class="sxs-lookup"><span data-stu-id="8cce9-263">Create the root certificate package (optional)</span></span>

<span data-ttu-id="8cce9-264">Vous créez ce package pour distribuer le certificat racine pour les appareils qui ne seront pas joints à un domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8cce9-264">You create this package to distribute the root certificate for devices that won't be joined to an Active Directory domain.</span></span> <span data-ttu-id="8cce9-265">Créez ce package uniquement si les deux conditions suivantes s’appliquent :</span><span class="sxs-lookup"><span data-stu-id="8cce9-265">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="8cce9-266">Votre déploiement inclut Lync ou Skype Entreprise Server local.</span><span class="sxs-lookup"><span data-stu-id="8cce9-266">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="8cce9-267">Les unités Salles Microsoft Teams sont configurées pour fonctionner dans un groupe de travail plutôt que dans un membre de domaine.</span><span class="sxs-lookup"><span data-stu-id="8cce9-267">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="8cce9-268">Copiez le certificat racine dans le **dossier SRS v2 – Package de certificat** racine.</span><span class="sxs-lookup"><span data-stu-id="8cce9-268">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="8cce9-269">Dans la console Configuration Manager, sélectionnez **Packages** de gestion d’application de bibliothèque de \>  \> **logiciels,** puis **sélectionnez Créer un package.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-269">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="8cce9-270">Entrez les informations suivantes pour créer le package :</span><span class="sxs-lookup"><span data-stu-id="8cce9-270">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="8cce9-271">Nom : **SRS v2 – Package de certificat racine**</span><span class="sxs-lookup"><span data-stu-id="8cce9-271">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="8cce9-272">Fabricant : *nom de votre organisation*</span><span class="sxs-lookup"><span data-stu-id="8cce9-272">Manufacturer: *Your organization's name*</span></span>
    -   <span data-ttu-id="8cce9-273">Version : **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="8cce9-273">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="8cce9-274">Cochez la case Ce package contient les fichiers **sources,** entrez le chemin d’accès au dossier **SRS v2 – Package** de certificat racine, puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-274">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="8cce9-275">Sélectionnez **Ne pas créer un programme,** puis **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-275">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="8cce9-276">Examinez la page **Confirmer les paramètres,** puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-276">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="8cce9-277">Sélectionnez **Fermer.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-277">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="8cce9-278">Créer le package de kit de déploiement de Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8cce9-278">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="8cce9-279">Téléchargez la dernière version du kit de déploiement de **Salles Microsoft Teams** à partir <https://go.microsoft.com/fwlink/?linkid=851168> de et installez-la sur une station de travail.</span><span class="sxs-lookup"><span data-stu-id="8cce9-279">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="8cce9-280">Copiez le contenu de **C: \\ Program Files (x86) \\ Skype Room System Deployment Kit** dans le dossier **SRS v2 - Package d’application SRS.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-280">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="8cce9-281">Dans la console Configuration Manager, sélectionnez **Packages** de gestion d’application de bibliothèque de \>  \> **logiciels,** puis **sélectionnez Créer un package.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-281">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="8cce9-282">Entrez les informations suivantes pour créer le package :</span><span class="sxs-lookup"><span data-stu-id="8cce9-282">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="8cce9-283">Nom : **SRS v2 – Package d’application SRS**</span><span class="sxs-lookup"><span data-stu-id="8cce9-283">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="8cce9-284">Fabricant : **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="8cce9-284">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="8cce9-285">Version : **3.1.104.0** (entrez la version du fichier d’installation téléchargé)</span><span class="sxs-lookup"><span data-stu-id="8cce9-285">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="8cce9-286">Cochez la case Ce package contient les fichiers **sources,** entrez le chemin d’accès au dossier Package d’application **SRS v2 – SRS,** puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-286">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="8cce9-287">Sélectionnez **Ne pas créer un programme,** puis **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-287">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="8cce9-288">Examinez la page **Confirmer les paramètres,** puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-288">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="8cce9-289">Sélectionnez **Fermer.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-289">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="8cce9-290">Créer le package d’affectation du nom de l’ordinateur</span><span class="sxs-lookup"><span data-stu-id="8cce9-290">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="8cce9-291">Dans le **dossier SRS v2 - Set-SRSComputerName Package,** créez une application HTML nommée **Set-SRSComputerName.hta.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-291">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="8cce9-292">Copiez le script suivant dans le fichier **Set-SRSComputerName.hta.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-292">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="8cce9-293">Vous pouvez également télécharger le fichier Set-SRSComputerName.hta à partir [d’ici.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="8cce9-293">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
    ```HTML
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
3.  <span data-ttu-id="8cce9-294">Dans la console Configuration Manager, sélectionnez **Packages** de gestion d’application de bibliothèque de \>  \> **logiciels,** puis **sélectionnez Créer un package.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-294">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="8cce9-295">Entrez les informations suivantes pour créer le package :</span><span class="sxs-lookup"><span data-stu-id="8cce9-295">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="8cce9-296">Nom : **SRS v2 - Set-SRSComputerName package**</span><span class="sxs-lookup"><span data-stu-id="8cce9-296">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="8cce9-297">Fabricant : **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="8cce9-297">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="8cce9-298">Version : **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="8cce9-298">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="8cce9-299">Cochez la case Ce package contient les fichiers **sources,** entrez le chemin d’accès au dossier **SRS v2 - Set-SRSComputerName Package,** puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-299">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="8cce9-300">Sélectionnez **Ne pas créer un programme,** puis **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-300">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="8cce9-301">Examinez la page **Confirmer les paramètres,** puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-301">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="8cce9-302">Sélectionnez **Fermer.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-302">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="8cce9-303">Créer le package Sysprep</span><span class="sxs-lookup"><span data-stu-id="8cce9-303">Create the Sysprep package</span></span>

1. <span data-ttu-id="8cce9-304">Dans le **dossier SRS v2 – Package Sysprep,** créez un fichier XML nommé **Unattend.xml.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-304">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="8cce9-305">Copiez le texte suivant dans le **Unattend.xml** fichier.</span><span class="sxs-lookup"><span data-stu-id="8cce9-305">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="8cce9-306">Vous pouvez également télécharger le fichier Unattend.xml [ici.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="8cce9-306">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```XML
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
3. <span data-ttu-id="8cce9-307">Dans la console Configuration Manager, sélectionnez **Packages** de gestion d’application de bibliothèque de \>  \> **logiciels,** puis **sélectionnez Créer un package.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-307">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="8cce9-308">Entrez les informations suivantes pour créer le package :</span><span class="sxs-lookup"><span data-stu-id="8cce9-308">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="8cce9-309">Nom : **SRS v2 - Package Sysprep**</span><span class="sxs-lookup"><span data-stu-id="8cce9-309">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="8cce9-310">Fabricant : **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="8cce9-310">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="8cce9-311">Version : **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="8cce9-311">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="8cce9-312">Cochez la case Ce package contient les fichiers **sources,** entrez le chemin d’accès au dossier **Package SRS v2 – Sysprep,** puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-312">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="8cce9-313">Sélectionnez **Ne pas créer un programme,** puis **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-313">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="8cce9-314">Examinez la page **Confirmer les paramètres,** puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-314">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="8cce9-315">Sélectionnez **Fermer.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-315">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="8cce9-316">Créer le package Windows 10 Entreprise</span><span class="sxs-lookup"><span data-stu-id="8cce9-316">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="8cce9-317">Obtenez un support Windows 10 Entreprise x64 et copiez le fichier **install.wim** dans le dossier Systèmes d’exploitation **\\ Windows 10 Entreprise.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-317">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="8cce9-318">Dans la console Configuration Manager, sélectionnez **Images** du système d’exploitation de la bibliothèque de logiciels, puis \>  \>  **sélectionnez Ajouter une image du système d’exploitation.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-318">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="8cce9-319">Spécifiez le chemin **d’accès au fichier install.wim** que vous avez copié, puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-319">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="8cce9-320">Mettez à **jour le champ Version** pour qu’il corresponde au numéro de build de l’image Windows 10 Entreprise, puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-320">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="8cce9-321">Examinez la page **Détails,** puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-321">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="8cce9-322">Sélectionnez **Fermer.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-322">Select **Close**.</span></span>

<span data-ttu-id="8cce9-323">Pour plus d’informations, voir [Gérer les images du système d’exploitation avec Configuration Manager.](/configmgr/osd/get-started/manage-operating-system-images)</span><span class="sxs-lookup"><span data-stu-id="8cce9-323">For more information, see [Manage OS images with Configuration Manager](/configmgr/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="8cce9-324">Créer des packages de pilotes de périphérique Surface Pro</span><span class="sxs-lookup"><span data-stu-id="8cce9-324">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="8cce9-325">Salles Microsoft Teams est pris en charge pour Surface Pro et Surface Pro 4.</span><span class="sxs-lookup"><span data-stu-id="8cce9-325">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="8cce9-326">Vous devez créer un package de pilote pour chaque modèle Surface Pro de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="8cce9-326">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8cce9-327">Les pilotes doivent être compatibles avec la build Windows 10 Entreprise et la version du kit de déploiement de Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="8cce9-327">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="8cce9-328">Pour plus d’informations, [consultez Télécharger le dernier microprogramme](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) et pilotes pour les appareils Surface et [Configurer une console.](console.md)</span><span class="sxs-lookup"><span data-stu-id="8cce9-328">For more information, see [Download the latest firmware and drivers for Surface devices](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="8cce9-329">Téléchargez les pilotes et microprogrammes les plus récents.</span><span class="sxs-lookup"><span data-stu-id="8cce9-329">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="8cce9-330">Pour Surface Pro : <https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="8cce9-330">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="8cce9-331">Pour Surface Pro 4 : <https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="8cce9-331">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="8cce9-332">Extraire le pilote et le microprogramme téléchargés.</span><span class="sxs-lookup"><span data-stu-id="8cce9-332">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="8cce9-333">Ouvrez une fenêtre d’invite de commandes, puis à l’invite de commandes, entrez l’une des commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="8cce9-333">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="8cce9-334">Dans la console Configuration Manager, sélectionnez **Pilotes** des systèmes d’exploitation de la bibliothèque de \>  \> **logiciels,** puis **sélectionnez Importer un pilote.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-334">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="8cce9-335">Sélectionnez Importer tous les pilotes dans le chemin d’accès réseau **suivant (UNC),** sélectionnez le dossier source (par exemple, C : \\ _Sources \\ Drivers Surface Pro), puis \\ **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-335">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="8cce9-336">Dans la page Spécifier les détails pour les pilotes **importés,** sélectionnez tous les pilotes répertoriés, puis sélectionnez Activer ces pilotes et autoriser les ordinateurs à **les installer.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-336">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="8cce9-337">Sélectionnez **Catégories,** créez une catégorie qui correspond au modèle Surface, **sélectionnez OK,** puis **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-337">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="8cce9-338">Sélectionnez **Nouveau package.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-338">Select **New Package**.</span></span>

8.  <span data-ttu-id="8cce9-339">Spécifiez le nom du package qui correspond au modèle Surface Pro, entrez un chemin d’accès de dossier pour stocker les fichiers de package de pilote, sélectionnez **OK,** puis **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-339">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="8cce9-340">Sur la page **des images de** démarrage, assurez-vous qu’aucune image de démarrage n’est sélectionnée, puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-340">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="8cce9-341">Sélectionnez **Fermer.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-341">Select **Close**.</span></span>

11. <span data-ttu-id="8cce9-342">Sélectionnez **Pilotes** des systèmes d’exploitation de bibliothèque de \>  \> **logiciels,** **\>** créez un dossier, puis entrez un nom de dossier qui correspond au modèle Surface Pro pour qui vous viennent d’importer les pilotes.</span><span class="sxs-lookup"><span data-stu-id="8cce9-342">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="8cce9-343">Déplacez tous les pilotes importés vers le dossier nouvellement créé pour faciliter la navigation et le fonctionnement.</span><span class="sxs-lookup"><span data-stu-id="8cce9-343">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="8cce9-344">Répétez les mêmes étapes pour les autres modèles Surface Pro que vous pourriez avoir.</span><span class="sxs-lookup"><span data-stu-id="8cce9-344">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="8cce9-345">Pour plus d’informations, [voir Gérer les pilotes dans Configuration Manager.](/configmgr/osd/get-started/manage-drivers)</span><span class="sxs-lookup"><span data-stu-id="8cce9-345">For more information, see [Manage drivers in Configuration Manager](/configmgr/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="8cce9-346">Créer un package de configuration pour salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8cce9-346">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="8cce9-347">Dans la console Configuration Manager, sélectionnez **Packages** de gestion d’application de bibliothèque de \>  \> **logiciels,** puis **sélectionnez Créer un package.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-347">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="8cce9-348">Entrez les informations suivantes pour créer le package :</span><span class="sxs-lookup"><span data-stu-id="8cce9-348">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="8cce9-349">Nom : **SRS v2 - Configurer le package d’installation SRS**</span><span class="sxs-lookup"><span data-stu-id="8cce9-349">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="8cce9-350">Fabricant : **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="8cce9-350">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="8cce9-351">Version : **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="8cce9-351">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="8cce9-352">Cochez la case Ce package contient les fichiers **sources,** entrez le chemin d’accès au **fichier SRS v2 -** Configurer le dossier d’installation SRS, puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-352">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="8cce9-353">Sélectionnez **Ne pas créer un programme,** puis **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-353">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="8cce9-354">Examinez la page **Confirmer les paramètres,** puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-354">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="8cce9-355">Sélectionnez **Fermer.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-355">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="8cce9-356">Distribuer des packages Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8cce9-356">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="8cce9-357">Tous les packages doivent être distribués aux serveurs qui ont reçu le rôle de point de distribution dans la hiérarchie de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="8cce9-357">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="8cce9-358">Suivez les instructions ci-dessous pour initier la distribution du package.</span><span class="sxs-lookup"><span data-stu-id="8cce9-358">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="8cce9-359">Distribuer des packages logiciels.</span><span class="sxs-lookup"><span data-stu-id="8cce9-359">Distribute software packages.</span></span>

    1.  <span data-ttu-id="8cce9-360">Dans la console Configuration Manager, sélectionnez **Packages de** gestion d’application \>  \> **de bibliothèque de logiciels.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-360">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="8cce9-361">Sélectionnez tous les packages logiciels que vous voulez distribuer, puis **Distribuer le contenu.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-361">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="8cce9-362">Examinez la liste des packages, puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-362">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="8cce9-363">Ajoutez tous les serveurs de points de distribution (ou groupes de points de distribution, selon votre hiérarchie Configuration Manager) à la liste, puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-363">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="8cce9-364">Sélectionnez **Suivant,** puis **Fermer.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-364">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="8cce9-365">Distribuez des packages de pilotes.</span><span class="sxs-lookup"><span data-stu-id="8cce9-365">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="8cce9-366">Dans la console Configuration Manager, sélectionnez **Packages** de pilote de la bibliothèque \>  \> **de logiciels.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-366">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="8cce9-367">Sélectionnez tous les packages de pilotes que vous souhaitez distribuer, puis **distribuer le contenu.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-367">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="8cce9-368">Examinez la liste des packages, puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-368">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="8cce9-369">Ajoutez tous les serveurs de points de distribution (ou groupes de points de distribution, selon votre hiérarchie Configuration Manager) à la liste, puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-369">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="8cce9-370">Sélectionnez **Suivant,** puis **Fermer.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-370">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="8cce9-371">Distribuer des packages de système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="8cce9-371">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="8cce9-372">Dans la console Configuration Manager, sélectionnez **Images** du système d’exploitation de la bibliothèque \>  \> **de logiciels.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-372">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="8cce9-373">Sélectionnez toutes les images du système d’exploitation à distribuer, puis **distribuer le contenu.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-373">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="8cce9-374">Examinez la liste des packages, puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-374">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="8cce9-375">Ajoutez tous les serveurs de points de distribution (ou groupes de points de distribution, selon votre hiérarchie Configuration Manager) à la liste, puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-375">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="8cce9-376">**Sélectionnez** Suivant, puis **Fermer.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-376">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="8cce9-377">La distribution de package peut prendre un certain temps, selon la taille du package, la hiérarchie configuration manager, le nombre de serveurs de points de distribution et la bande passante disponible dans votre réseau.</span><span class="sxs-lookup"><span data-stu-id="8cce9-377">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="8cce9-378">Tous les packages doivent être distribués avant de pouvoir commencer à déployer une unité de salle Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8cce9-378">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="8cce9-379">Vous pouvez passer en revue l’état de votre distribution de package dans la console Configuration Manager en allant à **Surveillance** de l’état du contenu de \>  \> **l’état de distribution.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-379">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="8cce9-380">Séquences de tâches dans Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8cce9-380">Configuration Manager task sequences</span></span>

<span data-ttu-id="8cce9-381">Vous utilisez des séquences de tâches avec Configuration Manager pour automatiser les étapes de déploiement d’une image de système d’exploitation sur un ordinateur de destination.</span><span class="sxs-lookup"><span data-stu-id="8cce9-381">You use task sequences with Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="8cce9-382">Pour déployer automatiquement une unité Salles Microsoft Teams, vous créez une séquence des tâches qui fait référence à l’image de démarrage utilisée pour démarrer l’ordinateur salles Microsoft Teams de destination, l’image du système d’exploitation Windows 10 Entreprise que vous voulez installer, ainsi que tout autre contenu supplémentaire, tel que d’autres mises à jour d’applications ou de logiciels.</span><span class="sxs-lookup"><span data-stu-id="8cce9-382">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="8cce9-383">Importer l’exemple de séquence de tâches</span><span class="sxs-lookup"><span data-stu-id="8cce9-383">Import the sample task sequence</span></span>

<span data-ttu-id="8cce9-384">Vous pouvez télécharger et importer facilement un exemple de séquence de tâches et la personnaliser selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="8cce9-384">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="8cce9-385">[**Téléchargez**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) l’exemple de séquence de tâches et copiez le fichier zip téléchargé dans un emplacement partagé.</span><span class="sxs-lookup"><span data-stu-id="8cce9-385">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="8cce9-386">Dans la console Configuration Manager, **sélectionnez** Séquences de tâches de la bibliothèque de logiciels de systèmes d’exploitation, puis \>  \>  **sélectionnez Importer la séquence des tâches.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-386">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="8cce9-387">Sélectionnez Parcourir, accédez à l’emplacement du dossier partagé que vous avez utilisé à l’étape 1, sélectionnez le fichier **Microsoft Teams Rooms Deployment (EN-US).zip,** puis sélectionnez **Suivant.** </span><span class="sxs-lookup"><span data-stu-id="8cce9-387">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="8cce9-388">Définissez **l’action** **Créer nouveau,** puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-388">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="8cce9-389">Confirmez les paramètres, puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-389">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="8cce9-390">Sélectionnez **Fermer.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-390">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="8cce9-391">Vérifier que les packages de référence sont correctement liés à chaque étape de séquence de tâches.</span><span class="sxs-lookup"><span data-stu-id="8cce9-391">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="8cce9-392">Sélectionnez la séquence de tâches importée, puis sélectionnez **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-392">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="8cce9-393">L’Éditeur de séquence des tâches s’ouvre et affiche chaque étape séquentielle dont vous avez besoin pour déployer et configurer une unité de salle Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8cce9-393">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="8cce9-394">Parcourir chaque étape et mettre à jour les mises à jour recommandées :</span><span class="sxs-lookup"><span data-stu-id="8cce9-394">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="8cce9-395">**Redémarrez dans Windows PE**: cette étape redémarre, puis démarre l’ordinateur dans Windows PXE.</span><span class="sxs-lookup"><span data-stu-id="8cce9-395">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="8cce9-396">Aucune modification n’est requise pour cette étape.</span><span class="sxs-lookup"><span data-stu-id="8cce9-396">No changes are required for this step.</span></span>

   2. <span data-ttu-id="8cce9-397">**Partition Disk 0 – UEFI**: Cette étape efface la configuration du disque et crée des partitions sur la base des paramètres configurés.</span><span class="sxs-lookup"><span data-stu-id="8cce9-397">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="8cce9-398">Nous vous recommandons de ne pas apporter de modifications à cette étape.</span><span class="sxs-lookup"><span data-stu-id="8cce9-398">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="8cce9-399">**Définissez le nom de** l’ordinateur SRS : cette étape inclut une application HTML qui fournit une interface utilisateur pour définir un nom d’ordinateur pour l’unité salles Microsoft Teams pendant le déploiement.</span><span class="sxs-lookup"><span data-stu-id="8cce9-399">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="8cce9-400">Cette étape est facultative, mais elle ne peut être désactivée que si vous voulez gérer l’attribution de noms d’ordinateurs via un autre processus.</span><span class="sxs-lookup"><span data-stu-id="8cce9-400">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="8cce9-401">Vérifiez que le package **SRS v2 - Set-SRSComputerName** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="8cce9-401">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="8cce9-402">Si ce n’est pas le cas, recherchez le package et sélectionnez-le.</span><span class="sxs-lookup"><span data-stu-id="8cce9-402">If it isn't, browse to the package and select it.</span></span>

   4. <span data-ttu-id="8cce9-403">**Appliquer le système d’exploitation**: cette étape spécifie l’image du système d’exploitation à déployer et le fichier de réponse Sysprep sans surveillance à utiliser.</span><span class="sxs-lookup"><span data-stu-id="8cce9-403">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="8cce9-404">Vérifiez que le fichier image correct du système d’exploitation Windows 10 Entreprise est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="8cce9-404">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="8cce9-405">Vérifiez que l’utilisation d’un fichier de réponse sans surveillance ou **Sysprep** pour une installation personnalisée est activée et que le **package SRS v2 - Sysprep** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="8cce9-405">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="8cce9-406">Assurez-vous également **que le nom du** fichier estunattend.xml. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8cce9-406">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="8cce9-407">**Appliquer les paramètres Windows**: cette étape permet de recueillir des informations sur l’installation de Windows.</span><span class="sxs-lookup"><span data-stu-id="8cce9-407">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="8cce9-408">Fournissez des informations sur les licences et l’enregistrement, notamment la clé de produit, le mot de passe du compte d’administrateur local et le fuseau horaire (selon vos besoins).</span><span class="sxs-lookup"><span data-stu-id="8cce9-408">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="8cce9-409">**Appliquer les paramètres réseau**: cette étape vous permet de spécifier un nom de domaine de groupe de travail ou Active Directory et une unité organisationnelle.</span><span class="sxs-lookup"><span data-stu-id="8cce9-409">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="8cce9-410">Consultez le domaine Skype Room System pour prendre en considération les actions [recommandées](domain-joining-considerations.md) que vous devez prendre dans le déploiement d’unités de salles Microsoft Teams en tant que membres d’un domaine d’annuaire Actve.</span><span class="sxs-lookup"><span data-stu-id="8cce9-410">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="8cce9-411">**Appliquer des pilotes :** Cette étape et ses sous-étapes sont utilisées pour déployer les pilotes d’appareils applicables et le microprogramme en fonction du modèle Surface Pro que vous avez.</span><span class="sxs-lookup"><span data-stu-id="8cce9-411">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="8cce9-412">Mettez à jour chaque étape pour spécifier le package pilote approprié associé à ce déploiement.</span><span class="sxs-lookup"><span data-stu-id="8cce9-412">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="8cce9-413">Chaque package de pilote est configuré pour tirer parti des filtres WMI (Windows Management Sorte) pour déployer des pilotes et microprogrammes pertinents sur la base de la tablette Surface Pro et du modèle.</span><span class="sxs-lookup"><span data-stu-id="8cce9-413">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="8cce9-414">Il est vivement recommandé de ne pas modifier la configuration de ces pilotes, sans quoi le déploiement pourrait échouer.</span><span class="sxs-lookup"><span data-stu-id="8cce9-414">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="8cce9-415">**Configurer Windows et Configuration Manager :** cette étape permet de déployer et de configurer le client Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="8cce9-415">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="8cce9-416">Mettez à jour cette étape pour spécifier le package client intégré à Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="8cce9-416">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="8cce9-417">**Installer le certificat racine**: cette étape distribue le certificat racine pour les appareils non joints au domaine. Par conséquent, cette étape est facultative et désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="8cce9-417">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="8cce9-418">Activez cette étape si vous avez besoin de déployer un certificat racine sur les unités salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8cce9-418">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="8cce9-419">Si vous devez effectuer cette étape, vérifiez que le **package SRS v2 – Certificat** racine et la redirection du système de fichiers **64 bits** sont sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="8cce9-419">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="8cce9-420">**Installer et configurer l’Agent** de surveillance : cette étape installe la version 64 bits de l’agent de surveillance Microsoft Azure et configure l’agent pour qu’il se connecte à votre espace de travail Analyse journal.</span><span class="sxs-lookup"><span data-stu-id="8cce9-420">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="8cce9-421">Cette étape est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="8cce9-421">This step is disabled by default.</span></span> <span data-ttu-id="8cce9-422">Activez cette étape uniquement si vous comptez utiliser l’Agent de surveillance pour surveiller l’état de vos unités salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8cce9-422">Enable this step only if you're going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="8cce9-423">Modifiez cette étape et mettez à jour les paramètres de ligne de commande pour spécifier votre **ID** et votre touche **Espace de travail.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-423">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="8cce9-424">Pour [plus d’informations](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) sur l’obtention de l’ID d’espace de travail de la suite Operations Management Suite et de la clé primaire, voir Configurer des périphériques de test pour Azure Monitoring.</span><span class="sxs-lookup"><span data-stu-id="8cce9-424">See [Configure test devices for Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="8cce9-425">Vérifiez que le **package de l’Agent** de surveillance Microsoft v2 et la redirection du système de fichiers **64 bits** sont sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="8cce9-425">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="8cce9-426">Pour plus d’informations sur la surveillance de l’état de votre déploiement de salles Microsoft Teams, voir Planifier la gestion des salles Microsoft Teams avec [Azure Monitor,](azure-monitor-plan.md)Déployer la gestion des salles [Microsoft Teams](azure-monitor-deploy.md) avec Azure Monitor et Gérer les appareils [Salles Microsoft Teams](azure-monitor-manage.md)avec Azure Monitor.</span><span class="sxs-lookup"><span data-stu-id="8cce9-426">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span>

   11. <span data-ttu-id="8cce9-427">**Copier les fichiers de configuration SRS v2**: cette étape copie les fichiers de configuration et de configuration requis à partir du kit de déploiement de Salles Microsoft Teams sur le disque dur local.</span><span class="sxs-lookup"><span data-stu-id="8cce9-427">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="8cce9-428">Aucune personnalisation n’est requise pour cette étape.</span><span class="sxs-lookup"><span data-stu-id="8cce9-428">No customization is required for this step.</span></span>
       -   <span data-ttu-id="8cce9-429">Vérifiez que le **package d’application SRS v2 – SRS** et la désactivation de la redirection du système de fichiers **64 bits** sont sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="8cce9-429">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="8cce9-430">**Mises à jour install-SRSv2-OS-Updates**: cette étape déploie toutes les mises à jour obligatoires du système d’exploitation requises avec le déploiement de salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8cce9-430">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="8cce9-431">Procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="8cce9-431">Do the following:</span></span>
       -   <span data-ttu-id="8cce9-432">Vérifiez [configurer une console salles Microsoft Teams](console.md) pour voir quelles mises à jour sont requises.</span><span class="sxs-lookup"><span data-stu-id="8cce9-432">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="8cce9-433">Vérifiez que votre package **SRS v2 – Mises à** jour du système d’exploitation inclut toutes les mises à jour requises.</span><span class="sxs-lookup"><span data-stu-id="8cce9-433">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="8cce9-434">Vérifiez que le **package SRS v2 – Mises à** jour du système d’exploitation est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="8cce9-434">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="8cce9-435">Vérifiez que la stratégie d’exécution de PowerShell est définie sur **Contourner.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-435">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="8cce9-436">**Redémarrer l’ordinateur**: Cette étape redémarre l’ordinateur une fois que les mises à jour obligatoires du système d’exploitation sont installées.</span><span class="sxs-lookup"><span data-stu-id="8cce9-436">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="8cce9-437">Aucune personnalisation n’est requise pour cette étape.</span><span class="sxs-lookup"><span data-stu-id="8cce9-437">No customization is required for this step.</span></span>

   14. <span data-ttu-id="8cce9-438">**Configurer des composants Windows**: cette étape configure les fonctionnalités Windows requises.</span><span class="sxs-lookup"><span data-stu-id="8cce9-438">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="8cce9-439">Aucune personnalisation n’est requise pour cette étape.</span><span class="sxs-lookup"><span data-stu-id="8cce9-439">No customization is required for this step.</span></span>

   15. <span data-ttu-id="8cce9-440">**Redémarrer l’ordinateur**: cette étape redémarre l’ordinateur une fois que les fonctionnalités de Windows sont configurées.</span><span class="sxs-lookup"><span data-stu-id="8cce9-440">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="8cce9-441">Aucune personnalisation n’est requise pour cette étape.</span><span class="sxs-lookup"><span data-stu-id="8cce9-441">No customization is required for this step.</span></span>

   16. <span data-ttu-id="8cce9-442">**Ajouter un utilisateur Skype local**: cette étape crée le compte Skype local utilisé pour se connecter automatiquement à Windows et démarrer l’application Salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8cce9-442">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="8cce9-443">Aucun package logiciel n’est associé à cette étape et aucune personnalisation n’est requise pour cette étape.</span><span class="sxs-lookup"><span data-stu-id="8cce9-443">This step doesn't have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="8cce9-444">**Configurer et configurer l’application SRS**: cette étape configure l’installation de l’application Salles Microsoft Teams pour le prochain démarrage du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="8cce9-444">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="8cce9-445">Vérifiez que la configuration du package d’installation **SRS v2** et la désactivation de la redirection du système de fichiers **64 bits** sont sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="8cce9-445">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8cce9-446">Il est très important que les étapes de la séquence des tâches soient dans l’ordre fourni.</span><span class="sxs-lookup"><span data-stu-id="8cce9-446">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="8cce9-447">La modification de l’ordre des étapes ou la configuration d’étapes supplémentaires peuvent rompre le déploiement.</span><span class="sxs-lookup"><span data-stu-id="8cce9-447">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="8cce9-448">**La configuration et la configuration de l’étape de l’application SRS** doivent être la dernière étape de la séquence des tâches, faute de quoi le déploiement peut échouer.</span><span class="sxs-lookup"><span data-stu-id="8cce9-448">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="8cce9-449">Créer un déploiement pour la séquence de tâches</span><span class="sxs-lookup"><span data-stu-id="8cce9-449">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="8cce9-450">Sélectionnez la séquence des tâches, puis **Déployer.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-450">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="8cce9-451">Sélectionnez **Parcourir** pour sélectionner la collection cible pour le déploiement.</span><span class="sxs-lookup"><span data-stu-id="8cce9-451">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="8cce9-452">Sélectionnez **Tous les ordinateurs inconnus,** puis **OK.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-452">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="8cce9-453">Sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-453">Select **Next**.</span></span>

5. <span data-ttu-id="8cce9-454">**Sélectionnez** Disponible dans la **liste** de liste bas Objectif.</span><span class="sxs-lookup"><span data-stu-id="8cce9-454">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="8cce9-455">Sélectionnez **Média et PXE uniquement** dans la liste Rendre **disponible,** puis **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-455">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="8cce9-456">Il est très important que **l’objectif** soit réglé sur **Disponible.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-456">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="8cce9-457">Assurez-vous que **l’objectif** **n’est PAS** définie sur **Obligatoire.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-457">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="8cce9-458">Veillez également à sélectionner Uniquement le média **et PXE** dans **la liste Rendre disponible pour les informations suivantes.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-458">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="8cce9-459">La définition de ces valeurs sur une autre valeur peut entraîner l’image de déploiement de Microsoft Teams Rooms sur tous les ordinateurs au démarrage.</span><span class="sxs-lookup"><span data-stu-id="8cce9-459">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="8cce9-460">Ne spécifiez aucun échéancier et sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-460">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="8cce9-461">Ne modifiez rien dans la section Expérience utilisateur **et** sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-461">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="8cce9-462">Ne modifiez rien dans la section **Alertes** et sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-462">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="8cce9-463">Ne modifiez rien dans la section **Points de distribution et** sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-463">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="8cce9-464">Confirmez les paramètres, puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-464">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="8cce9-465">Sélectionnez **Fermer.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-465">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="8cce9-466">Valider et résoudre les problèmes de la solution</span><span class="sxs-lookup"><span data-stu-id="8cce9-466">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="8cce9-467">Une fois que vous avez terminé les séquences de tâches Microsoft Endpoint Configuration Manager, vous devez effectuer une exécuter un test pour vérifier que la séquence des tâches peut déployer et configurer les unités des salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8cce9-467">After you've completed the Microsoft Endpoint Configuration Manager task sequences, you'll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="8cce9-468">Connectez le périphérique de test au réseau câblé à l’aide de l’un des adaptateurs Ethernet pris en charge ou à l’aide de la station d’accueil Surface.</span><span class="sxs-lookup"><span data-stu-id="8cce9-468">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="8cce9-469">Si la fonctionnalité de démarrage PXE n’a pas été configurée pour votre [](/configmgr/osd/deploy-use/create-bootable-media) environnement, vous pouvez utiliser l’image de démarrage sur le lecteur flash USB que vous avez créé précédemment pour démarrer à partir de l’USB et vous connecter à Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="8cce9-469">If PXE boot functionality hasn't been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](/configmgr/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="8cce9-470">Accédez au microprogramme et démarrez le démarrage PXE :</span><span class="sxs-lookup"><span data-stu-id="8cce9-470">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="8cce9-471">Assurez-vous que l’appareil Surface est éteint.</span><span class="sxs-lookup"><span data-stu-id="8cce9-471">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="8cce9-472">Appuyez de long sur le **bouton Monter le** volume.</span><span class="sxs-lookup"><span data-stu-id="8cce9-472">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="8cce9-473">Appuyez sur le bouton **d’alimentation et relâchez-le.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-473">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="8cce9-474">Lorsque le démarrage de l’appareil commence, relâchez le **bouton Monter le** volume.</span><span class="sxs-lookup"><span data-stu-id="8cce9-474">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="8cce9-475">Sélectionnez **Configuration du démarrage.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-475">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="8cce9-476">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="8cce9-476">Do one of the following:</span></span>

        -   <span data-ttu-id="8cce9-477">Sélectionnez **le démarrage PXE,** puis faites-le glisser vers le haut de la liste.</span><span class="sxs-lookup"><span data-stu-id="8cce9-477">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="8cce9-478">Vous pouvez également balayer vers la gauche sur l’adaptateur réseau pour démarrer sur l’appareil immédiatement.</span><span class="sxs-lookup"><span data-stu-id="8cce9-478">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="8cce9-479">Cela n’affecte pas l’ordre de démarrage.</span><span class="sxs-lookup"><span data-stu-id="8cce9-479">This won't affect the boot order.</span></span>
        -   <span data-ttu-id="8cce9-480">Sélectionnez le lecteur flash USB qui contient le support de démarrage.</span><span class="sxs-lookup"><span data-stu-id="8cce9-480">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="8cce9-481">Sélectionnez **Quitter,** puis **Redémarrer maintenant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-481">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="8cce9-482">À l’invite, **sélectionnez Entrée pour** le service de démarrage réseau.</span><span class="sxs-lookup"><span data-stu-id="8cce9-482">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="8cce9-483">Windows PE se charge en mémoire et l’Assistant Séquence des tâches démarre.</span><span class="sxs-lookup"><span data-stu-id="8cce9-483">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="8cce9-484">Sélectionnez **Suivant** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="8cce9-484">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="8cce9-485">Sélectionnez la séquence des tâches que vous avez importée précédemment, puis **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="8cce9-485">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="8cce9-486">Une fois la configuration du disque appliquée, vous êtes invité à spécifier un nom d’ordinateur pour l’appareil.</span><span class="sxs-lookup"><span data-stu-id="8cce9-486">After the disk configuration is applied, you'll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="8cce9-487">L’interface utilisateur affiche un nom d’ordinateur recommandé en fonction du numéro de série de l’appareil Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="8cce9-487">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="8cce9-488">Vous pouvez accepter le nom proposé ou en spécifier un nouveau.</span><span class="sxs-lookup"><span data-stu-id="8cce9-488">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="8cce9-489">Suivez les instructions dans l’écran d’affectation du nom de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="8cce9-489">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="8cce9-490">Lorsque vous **sélectionnez Accepter,** le déploiement commence.</span><span class="sxs-lookup"><span data-stu-id="8cce9-490">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="8cce9-491">Le reste du processus de déploiement est automatique et ne demande pas d’autres commentaires de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8cce9-491">The rest of the deployment process is automatic and doesn't ask for any more user input.</span></span>

9.  <span data-ttu-id="8cce9-492">Une fois que la séquence des tâches de déploiement aura terminé de configurer l’appareil, l’écran de configuration suivant s’affiche pour vous demander de configurer les paramètres de l’application Salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8cce9-492">After the deployment task sequence finishes configuring the device, you'll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![Écran de configuration initiale de l’application Salles Microsoft Teams](../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="8cce9-494">Branchez le Surface Pro à la console Salles Microsoft Teams et configurez les paramètres de l’application.</span><span class="sxs-lookup"><span data-stu-id="8cce9-494">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="8cce9-495">Validez que les fonctionnalités répertoriées dans l’aide [de Salles Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) fonctionnent sur l’appareil déployé.</span><span class="sxs-lookup"><span data-stu-id="8cce9-495">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="8cce9-496">Pour résoudre un échec d’installation, consultez le fichier **SMSTS.log,** qui enregistre toutes les étapes exécutées dans une séquence de tâches du Gestionnaire de configuration.</span><span class="sxs-lookup"><span data-stu-id="8cce9-496">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="8cce9-497">Le fichier SMSTS.log est stocké sur l’un des chemins d’accès suivant l’étape du processus de création.</span><span class="sxs-lookup"><span data-stu-id="8cce9-497">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="8cce9-498">Consultez le tableau suivant pour identifier le chemin d’accès au fichier SMSTS.log.</span><span class="sxs-lookup"><span data-stu-id="8cce9-498">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="8cce9-499">**Phase de déploiement**</span><span class="sxs-lookup"><span data-stu-id="8cce9-499">**Deployment phase**</span></span>                                                            | <span data-ttu-id="8cce9-500">**Chemin d’accès du journal de séquence de tâches**</span><span class="sxs-lookup"><span data-stu-id="8cce9-500">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="8cce9-501">WinPE, avant format HDD</span><span class="sxs-lookup"><span data-stu-id="8cce9-501">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="8cce9-502">X : \\ \\ \\ Smstslog \\ Smstslog Windows Temp.log</span><span class="sxs-lookup"><span data-stu-id="8cce9-502">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="8cce9-503">WinPE, après le format HDD</span><span class="sxs-lookup"><span data-stu-id="8cce9-503">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="8cce9-504">C : \\ _SMSTaskSequence \\ \\ Smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="8cce9-504">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="8cce9-505">Système d’exploitation déployé avant l’installation de l’agent Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8cce9-505">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="8cce9-506">c : \\ _SMSTaskSequence \\ \\ Smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="8cce9-506">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="8cce9-507">Système d’exploitation et agent Configuration Manager déployés</span><span class="sxs-lookup"><span data-stu-id="8cce9-507">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="8cce9-508">%windir% \\ System32 \\ ccm \\ logs \\ SMStslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="8cce9-508">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="8cce9-509">Exécution de séquence de tâches terminée</span><span class="sxs-lookup"><span data-stu-id="8cce9-509">Task sequence execution complete</span></span>                                                | <span data-ttu-id="8cce9-510">%windir% \\ System32 \\ ccm \\ logs \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="8cce9-510">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="8cce9-511">Vous pouvez sélectionner **F8 à** tout moment pendant la séquence des tâches pour ouvrir une console de commande, puis accéder au fichier SMSTS.log.</span><span class="sxs-lookup"><span data-stu-id="8cce9-511">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="8cce9-512">Pour résoudre les problèmes de démarrage PXE, vérifiez les deux fichiers journaux sur le serveur Configuration Manager qui sont spécifiques aux actions PXE :</span><span class="sxs-lookup"><span data-stu-id="8cce9-512">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="8cce9-513">**Pxecontrol.log,** situé dans le répertoire des journaux d’installation de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8cce9-513">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="8cce9-514">**Smspxe.log,** situé dans le répertoire des journaux du point de gestion configuration manager (MP)</span><span class="sxs-lookup"><span data-stu-id="8cce9-514">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="8cce9-515">Pour obtenir la liste complète des fichiers journaux que vous pouvez utiliser pour résoudre les problèmes d’installation de Configuration Manager, consultez la référence du fichier journal de Microsoft Endpoint Configuration [Manager.](/configmgr/core/plan-design/hierarchy/log-files)</span><span class="sxs-lookup"><span data-stu-id="8cce9-515">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see the Microsoft Endpoint Configuration Manager [Log file reference](/configmgr/core/plan-design/hierarchy/log-files).</span></span>

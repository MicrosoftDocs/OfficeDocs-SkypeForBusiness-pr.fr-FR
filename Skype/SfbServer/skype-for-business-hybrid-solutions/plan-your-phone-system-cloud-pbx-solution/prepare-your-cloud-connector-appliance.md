---
title: Préparation de votre appliance Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Apprenez-en davantage sur la préparation de votre appareil Cloud Connector pour le déploiement et l’utilisation avec le système téléphonique dans Office 365 (Cloud PBX).
ms.openlocfilehash: 6e6cb71353dc2a2339fe92ce45d0cd3dee9f21a1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814432"
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="76416-103">Préparation de votre appliance Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="76416-103">Prepare your Cloud Connector appliance</span></span>

<span data-ttu-id="76416-104">Apprenez-en davantage sur la préparation de votre appareil Cloud Connector pour le déploiement et l’utilisation avec le système téléphonique dans Office 365 (Cloud PBX).</span><span class="sxs-lookup"><span data-stu-id="76416-104">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System in Office 365 (Cloud PBX).</span></span>

<span data-ttu-id="76416-105">Cette rubrique décrit comment obtenir les fichiers d’installation de la version Cloud Connector de Skype Entreprise, comment installer le logiciel Cloud Connector et préparer votre appliance Cloud Connector au déploiement.</span><span class="sxs-lookup"><span data-stu-id="76416-105">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="76416-106">Après avoir effectué toutes les étapes de cette rubrique, vous serez prêt à déployer Cloud Connector pour un ou plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="76416-106">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="76416-107">Si vous disposez d’un déploiement Cloud Connector existant et que vous n’avez pas encore effectué la mise à niveau vers la version 2,1 du Cloud Connector, voir [effectuer la mise à niveau vers une nouvelle version de Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="76416-107">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="76416-108">Microsoft prend en charge la version actuelle de l’édition Cloud Connector, version 2,1.</span><span class="sxs-lookup"><span data-stu-id="76416-108">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="76416-109">Si vous configurez une mise à jour automatique, Cloud Connector se mettra automatiquement à jour.</span><span class="sxs-lookup"><span data-stu-id="76416-109">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="76416-110">Si vous avez configuré la mise à jour manuelle, vous devez effectuer la mise à niveau vers la version 2,1 dans 60 jours de sa publication.</span><span class="sxs-lookup"><span data-stu-id="76416-110">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="76416-111">Microsoft prend en charge la version précédente de 60 jours après la publication d' 2,1 pour vous permettre d’effectuer la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="76416-111">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 

> [!NOTE]
> <span data-ttu-id="76416-112">Pour le Cloud Connector version 2,1 et les versions ultérieures, l’appareil hôte doit disposer de .NET Framework 4.6.1 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="76416-112">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="76416-113">Dans le cas d’un déploiement réussi, lorsque vous exécutez les applets de connexion pour configurer Skype entreprise version Cloud Connector, utilisez toujours la même session de console que celle que vous avez démarrée.</span><span class="sxs-lookup"><span data-stu-id="76416-113">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="76416-114">Évitez de basculer entre plusieurs sessions lors du déploiement et de la configuration.</span><span class="sxs-lookup"><span data-stu-id="76416-114">Avoid switching to different sessions during the deployment and configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="76416-115">Certaines étapes peuvent uniquement être exécutées pour la première appliance de votre déploiement : création d’un partage pour l’annuaire de sites, téléchargement de bits et préparation d’un fichier de disque dur virtuel (VHDX) à partir de l’image ISO du serveur Windows.</span><span class="sxs-lookup"><span data-stu-id="76416-115">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="76416-116">Téléchargement du programme d’installation de Skype Entreprise, version Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="76416-116">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="76416-117">Sur le serveur hôte sur lequel s’exécutent les VM de connexion Cloud, téléchargez les [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)fichiers d’installation :.</span><span class="sxs-lookup"><span data-stu-id="76416-117">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="76416-118">Le serveur hôte doit pouvoir accéder à Internet lors de l’installation de Cloud Connector, car des fichiers supplémentaires sont téléchargés pendant cette opération.</span><span class="sxs-lookup"><span data-stu-id="76416-118">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 

2. <span data-ttu-id="76416-119">Exécutez le programme d’installation et acceptez les valeurs par défaut lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="76416-119">Run the installer and accept the default values during the installation.</span></span>

3. <span data-ttu-id="76416-120">Vérifiez que l’installation a été correctement effectuée.</span><span class="sxs-lookup"><span data-stu-id="76416-120">Confirm that the installation completed successfully.</span></span>

## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="76416-121">Vérification de l’installation et configuration de l’environnement</span><span class="sxs-lookup"><span data-stu-id="76416-121">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="76416-122">Ouvrez une console PowerShell en tant qu’administrateur, puis vérifiez que les applets de commande Skype entreprise version Cloud Connector sont disponibles à l’aide de l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="76416-122">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>

   ```powershell
   Get-Command *-Cc*
   ```

    <span data-ttu-id="76416-123">La commande doit retourner une liste d’applets de commande pour Skype entreprise version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="76416-123">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>

2. <span data-ttu-id="76416-124">Les fichiers de disques durs virtuels, SfBBits et VersionInfo seront stockés dans l’**Annuaire de sites**.</span><span class="sxs-lookup"><span data-stu-id="76416-124">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>

    <span data-ttu-id="76416-125">Vous trouverez l’emplacement de l’**Annuaire de sites** à l’aide de l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="76416-125">You can find the location of the **Site Directory** with the following cmdlet:</span></span>

   ```powershell
   Get-CcSiteDirectory
   ```

    <span data-ttu-id="76416-126">La commande doit renvoyer un emplacement dans votre système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="76416-126">The command should return a location in your file system.</span></span> <span data-ttu-id="76416-127">L’emplacement peut être un dossier local ou un partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="76416-127">The location can be a local folder or a file share.</span></span> <span data-ttu-id="76416-128">L’emplacement par défaut de l’**Annuaire de sites** est le suivant : %USERPROFILE%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="76416-128">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="76416-129">L’emplacement par défaut doit être remplacé par un partage de fichiers sur le premier équipement créé dans chaque site.</span><span class="sxs-lookup"><span data-stu-id="76416-129">The default location should be changed to a file share on the first appliance created in each site.</span></span>

    <span data-ttu-id="76416-130">L’emplacement que vous sélectionnez doit être :</span><span class="sxs-lookup"><span data-stu-id="76416-130">The location you select must be:</span></span>

   - <span data-ttu-id="76416-131">Créé sur le premier équipement créé dans chaque site ;</span><span class="sxs-lookup"><span data-stu-id="76416-131">Created on the first appliance created in each site.</span></span>

   - <span data-ttu-id="76416-132">Un dossier partagé accessible par les autres serveurs hôtes (équipements) dans le même site; </span><span class="sxs-lookup"><span data-stu-id="76416-132">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>

     <span data-ttu-id="76416-133">Pour définir l’**Annuaire de sites** sur un emplacement différent de celui par défaut, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="76416-133">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    <span data-ttu-id="76416-134">Si vous déployez la haute disponibilité pour le site, veillez à exécuter l’applet de comment pour définir l’**Annuaire de sites** vers le même emplacement sur chaque serveur hôte dans le site.</span><span class="sxs-lookup"><span data-stu-id="76416-134">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>

    <span data-ttu-id="76416-135">Lorsque vous ouvrez une session et que vous déployez chaque application sur le site, vérifiez que votre compte d’ouverture de session actuel dispose de l’accès approprié à l' **Annuaire de sites**.</span><span class="sxs-lookup"><span data-stu-id="76416-135">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>

3. <span data-ttu-id="76416-136">Le **répertoire** de l’application est le répertoire racine de travail local de Skype entreprise version Cloud Connector et l’emplacement où sont enregistrés les certificats externes, les instances et les journaux.</span><span class="sxs-lookup"><span data-stu-id="76416-136">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="76416-137">L’emplacement par défaut est : %USERPROFILE%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="76416-137">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>

    <span data-ttu-id="76416-138">Pour rechercher l’emplacement de l’**Annuaire de sites** exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="76416-138">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>

   ```powershell
   Get-CcApplianceDirectory
   ```

    <span data-ttu-id="76416-139">Pour définir le **répertoire d'équipements** vers un emplacement différent de celui par défaut, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="76416-139">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    <span data-ttu-id="76416-140">L’annuaire d’appliances doit être dirigé vers un dossier local de l’appliance.</span><span class="sxs-lookup"><span data-stu-id="76416-140">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="76416-141">Vous ne devez définir le **répertoire** de l’application que avant de lancer le déploiement de Skype entreprise version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="76416-141">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="76416-142">Si vous le modifiez après le déploiement, vous devrez redéployer le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="76416-142">If you change it after deployment, you'll need to redeploy the host server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="76416-143">Le chemin d’accès au **répertoire d'équipements** ne doit contenir aucun espace.</span><span class="sxs-lookup"><span data-stu-id="76416-143">The path to the **Appliance Directory** must not contain any spaces.</span></span>

## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="76416-144">Définition du chemin d’accès au certificat Edge externe</span><span class="sxs-lookup"><span data-stu-id="76416-144">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="76416-p107">Pour définir le chemin d’accès au certificat Edge externe, notamment le nom du fichier, exécutez l’applet de commande suivante. Par exemple : C:\certs\cce\ap.contoso.com.pfx. Le certificat doit contenir des clés privées.</span><span class="sxs-lookup"><span data-stu-id="76416-p107">Run the following cmdlet to set the path, including the file name, to the external Edge certificate. For example: C:\certs\cce\ap.contoso.com.pfx. The certificate must contain private keys.</span></span>

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="76416-148">Notez que le paramètre-Target est spécifique aux versions 1.4.2 et ultérieures.</span><span class="sxs-lookup"><span data-stu-id="76416-148">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

    <span data-ttu-id="76416-149">Spécifiez le chemin d’accès vers le certificat externe, notamment le nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="76416-149">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="76416-150">Le certificat peut être enregistré localement ou sur un partage de fichier.</span><span class="sxs-lookup"><span data-stu-id="76416-150">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="76416-151">S’il est enregistré dans un dossier partagé, le dossier partagé doit être créé sur la première appliance de chaque site et être accessible par d’autres appliances appartenant au même site.</span><span class="sxs-lookup"><span data-stu-id="76416-151">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="76416-152">Cette applet de commande copie le certificat externe vers l’**annuaire d’appliances**.</span><span class="sxs-lookup"><span data-stu-id="76416-152">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="76416-153">**Si vous avez effectué une mise à jour vers le Connector Cloud version 1.4.2 ou une version ultérieure**, assurez-vous que votre certificat externe préparé contient des clés privées et la chaîne de certificats complète, y compris le certificat de l’autorité de certification racine et les certificats d’autorité de certification intermédiaire</span><span class="sxs-lookup"><span data-stu-id="76416-153">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.</span></span> <span data-ttu-id="76416-154">**Si vous n’avez pas encore mis à jour la version 1.4.2 de Cloud Connector**, vérifiez que votre certificat externe préparé contient des clés privées.</span><span class="sxs-lookup"><span data-stu-id="76416-154">**If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="76416-155">Ce certificat externe doit être émis par une autorité de certification approuvée par défaut par Windows.</span><span class="sxs-lookup"><span data-stu-id="76416-155">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="76416-156">Définition du chemin d’accès pour le certificat externe de la passerelle RTC/SBC</span><span class="sxs-lookup"><span data-stu-id="76416-156">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="76416-157">Si vous utilisez TLS entre le serveur de médiation et la passerelle RTC/SBC, exécutez l’applet de commande suivante pour configurer le chemin d’accès, notamment le nom de fichier vers le certificat passerelle.</span><span class="sxs-lookup"><span data-stu-id="76416-157">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="76416-158">Par exemple : C:\certs\cce\sbc.contoso.com.cer.</span><span class="sxs-lookup"><span data-stu-id="76416-158">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="76416-159">Le certificat doit contenir l’AC racine et la chaîne intermédiaire pour le certificat assigné à la passerelle :</span><span class="sxs-lookup"><span data-stu-id="76416-159">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> <span data-ttu-id="76416-160">Notez que le paramètre-Target est spécifique aux versions 1.4.2 et ultérieures.</span><span class="sxs-lookup"><span data-stu-id="76416-160">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="76416-161">Création de commutateurs virtuels dans le Gestionnaire Hyper-V</span><span class="sxs-lookup"><span data-stu-id="76416-161">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="76416-162">Ouvrez le**Gestionnaire de switches virtuel** **Hyper-V** > et sélectionnez **nouveau gestionnaire de switch virtuel**.</span><span class="sxs-lookup"><span data-stu-id="76416-162">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>

2. <span data-ttu-id="76416-163">Créez un commutateur virtuel externe et associez-le à la carte réseau physique qui est connectée à votre domaine réseau interne :</span><span class="sxs-lookup"><span data-stu-id="76416-163">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>

    <span data-ttu-id="76416-164">Sélectionnez **Permettre au système d’exploitation de gestion de partager cette carte réseau** pour le commutateur virtuel.</span><span class="sxs-lookup"><span data-stu-id="76416-164">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

3. <span data-ttu-id="76416-165">Créer un commutateur virtuel externe et le lier à la carte réseau physique routée vers Internet :</span><span class="sxs-lookup"><span data-stu-id="76416-165">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>

    <span data-ttu-id="76416-166">Dé-sélectionnez **autoriser la gestion du système d’exploitation pour partager cette carte réseau** pour ce commutateur virtuel.</span><span class="sxs-lookup"><span data-stu-id="76416-166">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

4. <span data-ttu-id="76416-167">Définissez le nom du commutateur connecté à votre réseau de périmètre pour le **commutateur corpnet**du domaine de réseau marketing.</span><span class="sxs-lookup"><span data-stu-id="76416-167">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>

    <span data-ttu-id="76416-168">Définissez le nom du commutateur connecté à votre réseau de périmètre au **commutateur Internet Marketing CCE**.</span><span class="sxs-lookup"><span data-stu-id="76416-168">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>

## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="76416-169">Mise à jour du fichier de configuration CloudConnector.ini</span><span class="sxs-lookup"><span data-stu-id="76416-169">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="76416-170">Préparez le fichier CloudConnector. ini en utilisant les informations que vous avez collectées dans la section [déterminer les paramètres de déploiement](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) du [plan pour Skype entreprise version Cloud Connector](plan-skype-for-business-cloud-connector-edition.md) .</span><span class="sxs-lookup"><span data-stu-id="76416-170">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>

<span data-ttu-id="76416-171">Pour mettre à jour le fichier, exécutez d’abord l’applet de commande suivante pour obtenir l’exemple de modèle (CloudConnector.Sample.ini) :</span><span class="sxs-lookup"><span data-stu-id="76416-171">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>

```powershell
Export-CcConfigurationSampleFile
```

<span data-ttu-id="76416-172">L’exemple de modèle est stocké dans le **répertoire d'équipements**.</span><span class="sxs-lookup"><span data-stu-id="76416-172">The sample template is stored in the **Appliance Directory**.</span></span>

<span data-ttu-id="76416-173">Une fois mis à jour avec les valeurs relatives à votre environnement, enregistrez le fichier sous CloudConnector.ini dans le **répertoire d'équipements**.</span><span class="sxs-lookup"><span data-stu-id="76416-173">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="76416-174">Vous pouvez exécuter **Get-CcApplianceDirectory** pour définir le chemin d’accès sur le **répertoire d'équipements**.</span><span class="sxs-lookup"><span data-stu-id="76416-174">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>

<span data-ttu-id="76416-175">Lors de la mise à jour du fichier .ini, tenez compte des points suivants :</span><span class="sxs-lookup"><span data-stu-id="76416-175">When updating the .ini file, consider the following:</span></span>

> [!NOTE]
> <span data-ttu-id="76416-176">Cette section couvre uniquement les valeurs du fichier .ini qui comportent des caractéristiques spécifiques.</span><span class="sxs-lookup"><span data-stu-id="76416-176">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="76416-177">Pour obtenir une liste complète, consultez la section [déterminer les paramètres de déploiement](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) de la rubrique [plan pour Skype entreprise version Cloud Connector](plan-skype-for-business-cloud-connector-edition.md) .</span><span class="sxs-lookup"><span data-stu-id="76416-177">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span> <span data-ttu-id="76416-178">Pour plus d’informations sur la nature des valeurs devant être changées pour des appliances supplémentaires ou de nouveaux sites, reportez-vous à [Site unique à haute disponibilité comparé aux déploiements multi-sites](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) dans la rubrique [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="76416-178">For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 

- <span data-ttu-id="76416-p113">**SiteName :** la valeur par défaut est **Site1**. Vous devez la mettre à jour avant de déployer Cloud Connector, car lorsque vous exécutez **Register-CcAppliance** pour enregistrer un équipement dans un site existant ou nouveau, l’applet de commande utilisera le **SiteName** pour déterminer le site à enregistrer.</span><span class="sxs-lookup"><span data-stu-id="76416-p113">**SiteName:** The default value is **Site1**. You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>

     <span data-ttu-id="76416-181">Si vous souhaitez enregistrer l’équipement dans un nouveau site, la valeur **SiteName** doit être unique et différent des sites existants.</span><span class="sxs-lookup"><span data-stu-id="76416-181">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="76416-182">Si vous voulez enregistrer l’application sur un site existant, la valeur de **SiteName** dans le fichier. ini doit correspondre au nom défini dans la configuration de votre client Office 365.</span><span class="sxs-lookup"><span data-stu-id="76416-182">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Office 365 tenant configuration.</span></span> <span data-ttu-id="76416-183">Si vous copiez un fichier de configuration d’un site vers un autre, veillez à mettre à jour la valeur **SiteName** pour chaque site comme il convient.</span><span class="sxs-lookup"><span data-stu-id="76416-183">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>

- <span data-ttu-id="76416-184">**ServerName :** Le nom de serveur ne doit pas contenir le nom de domaine et se limiter à 15 caractères. </span><span class="sxs-lookup"><span data-stu-id="76416-184">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>

- <span data-ttu-id="76416-185">**HardwareType :** Si vous ne définissez pas ou ne laissez pas la valeur null, la valeur par défaut **normale** est utilisée.</span><span class="sxs-lookup"><span data-stu-id="76416-185">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="76416-186">Utilisez **normal** si vous envisagez de déployer la version plus grande de Cloud Connector pour prendre en charge les appels simultanés 500 par ordinateur hôte comme décrit dans la section [plan de Skype entreprise version Cloud Connector](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="76416-186">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="76416-187">Utilisez **Minimum** pour un déploiement moins développé qui prend en charge 50 appels simultanés.</span><span class="sxs-lookup"><span data-stu-id="76416-187">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>

- <span data-ttu-id="76416-188">**Commutateurs virtuels Internet/corpnet/gestion :**: ajoutez le nom des commutateurs virtuels que vous avez créés.</span><span class="sxs-lookup"><span data-stu-id="76416-188">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="76416-189">Pour le commutateur virtuel de gestion, conservez la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="76416-189">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="76416-190">Le script de déploiement va créer le commutateur virtuel de gestion au début du déploiement et le supprimer à la fin du déploiement.</span><span class="sxs-lookup"><span data-stu-id="76416-190">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>

- <span data-ttu-id="76416-p117">**ManagementIPPrefix :** le paramètre ManagementIPPrefix dans la section Réseau doit être un sous-réseau différent des autres IP internes. Par exemple, comme la valeur par défaut l’indique, ManagementIPPrefix est 192.168.213.0, tandis que AD IPAddress est 192.168.0.238.</span><span class="sxs-lookup"><span data-stu-id="76416-p117">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs. For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>

    <span data-ttu-id="76416-p118">Les scripts de déploiement créent une carte réseau de gestion sur chacune des machines virtuelles, affectent une adresse IP de gestion et les connectent à un commutateur virtuel de gestion. Le serveur hôte peut ainsi se connecter aux machines virtuelles et les gérer via ce réseau de gestion. Le commutateur virtuel de gestion est supprimé à l’issue du déploiement.</span><span class="sxs-lookup"><span data-stu-id="76416-p118">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch. This enables the host server to connect to and manage each virtual machine via this management network. The management virtual switch is deleted when the deployment is finished.</span></span>

- <span data-ttu-id="76416-196">**Configurations spécifiques aux machines virtuelles de base :** les paramètres de cette section doivent être configurés pour l’applet de commande **Convert-CcIsoToVhdx**.</span><span class="sxs-lookup"><span data-stu-id="76416-196">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>

    <span data-ttu-id="76416-p119">Lors de la préparation de l’image de machine virtuelle de base, la machine virtuelle de base sera connectée au commutateur réseau interne. Les paramètres suivants sont critiques et permettent à la machine virtuelle d’accéder à Internet :</span><span class="sxs-lookup"><span data-stu-id="76416-p119">During base VM image preparation, the base VM will be connected to the internal network switch. The following settings are critical for the VM to be able to access the Internet:</span></span>

  - <span data-ttu-id="76416-199">[Common]BaseVMIP : adresse IP du réseau d’entreprise à affecter à la machine virtuelle de base</span><span class="sxs-lookup"><span data-stu-id="76416-199">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="76416-200">[Network]CorpnetDefaultGateway : passerelle par défaut à affecter à la machine virtuelle de base</span><span class="sxs-lookup"><span data-stu-id="76416-200">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>

  - <span data-ttu-id="76416-201">[Network]CorpnetDNSIPAddress : adresse IP du DNS à affecter à la machine virtuelle de base</span><span class="sxs-lookup"><span data-stu-id="76416-201">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="76416-202">[Network]WSUSServer : adresse IP du service WSUS (Windows Server Update Service)</span><span class="sxs-lookup"><span data-stu-id="76416-202">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>

  - <span data-ttu-id="76416-203">[Network]WSUSStatusServer : adresse IP du serveur de statut WSUS (Windows Server Update Service)</span><span class="sxs-lookup"><span data-stu-id="76416-203">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>

  - <span data-ttu-id="76416-204">[Network]EnableReferSupport : ce paramètre définira si la prise en charge SIP REFER est activée ou désactivée dans la configuration de jonctions pour votre IP/PBX.</span><span class="sxs-lookup"><span data-stu-id="76416-204">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>

- <span data-ttu-id="76416-205">**Adresses IP internes :**</span><span class="sxs-lookup"><span data-stu-id="76416-205">**Internal IPs:**</span></span>

  - <span data-ttu-id="76416-206">Vérifiez que le masque de sous-réseau CorpnetIPPrefixLength est correct.</span><span class="sxs-lookup"><span data-stu-id="76416-206">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="76416-207">Assurez-vous qu’il n’y a pas de conflits IP pour ces adresses IP internes.</span><span class="sxs-lookup"><span data-stu-id="76416-207">Make sure there are no IP conflicts for these internal IPs.</span></span>

- <span data-ttu-id="76416-208">**Adresses IP externes :**</span><span class="sxs-lookup"><span data-stu-id="76416-208">**External IPs:**</span></span>

  - <span data-ttu-id="76416-209">Pour une adresse IP publique de MR : spécifiez ExternalMRIPs pour les non-NAT ou ExternalMRPublicIPs pour tar.</span><span class="sxs-lookup"><span data-stu-id="76416-209">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>

  - <span data-ttu-id="76416-210">ExternalSIPIPs et ExternalMRIPs peuvent être identiques.</span><span class="sxs-lookup"><span data-stu-id="76416-210">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>

  - <span data-ttu-id="76416-211">Vérifiez que le masque de sous-réseau InternetIPPrefixLength est correct.</span><span class="sxs-lookup"><span data-stu-id="76416-211">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="76416-212">Assurez-vous qu’il n’y a pas de conflits IP pour ces adresses IP externes.</span><span class="sxs-lookup"><span data-stu-id="76416-212">Make sure there are no IP conflicts for these external IPs.</span></span>

- <span data-ttu-id="76416-213">**Passerelles :**</span><span class="sxs-lookup"><span data-stu-id="76416-213">**Gateways:**</span></span>

  - <span data-ttu-id="76416-p120">Si vous disposez d’une seule passerelle, supprimez la section concernant la deuxième passerelle. Si vous disposez de plus de deux passerelles, créez des sections supplémentaires en copiant et en collant, puis en la mettant à jour.</span><span class="sxs-lookup"><span data-stu-id="76416-p120">If you have only one gateway, remove the section for the secondary gateway. If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>

  - <span data-ttu-id="76416-216">Assurez-vous que l’adresse IP et le port des passerelles sont corrects.</span><span class="sxs-lookup"><span data-stu-id="76416-216">Make sure that the IP address and port of the gateway(s) are correct.</span></span>

  - <span data-ttu-id="76416-217">Pour prendre en charge la haute disponibilité de niveau passerelle PSTN, laissez la passerelle secondaire et ajoutez d’autres passerelles que vous utiliserez.</span><span class="sxs-lookup"><span data-stu-id="76416-217">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="76416-218">Vous pouvez copier et coller une entrée existante, puis la mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="76416-218">You can copy and paste an existing entry and then update it.</span></span>

- <span data-ttu-id="76416-219">Le cas échéant, vous pouvez mettre à jour la valeur LocalRoute pour limiter les numéros d’appel sortants.</span><span class="sxs-lookup"><span data-stu-id="76416-219">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>

## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="76416-220">Téléchargement des fichiers BITS dans l’Annuaire de sites</span><span class="sxs-lookup"><span data-stu-id="76416-220">Download the bits to the Site Directory</span></span>

<span data-ttu-id="76416-221">Exécutez l’applet de commande suivante pour télécharger les fichiers BITS et d’informations de version vers l’**Annuaire de sites **:</span><span class="sxs-lookup"><span data-stu-id="76416-221">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>

```powershell
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="76416-222">Vous devez effectuer cette étape uniquement pour la première appliance.</span><span class="sxs-lookup"><span data-stu-id="76416-222">You need to perform this step for the first appliance only.</span></span> 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="76416-223">Préparation du disque virtuel de base (VHDX) à partir du fichier ISO téléchargé</span><span class="sxs-lookup"><span data-stu-id="76416-223">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="76416-224">Cette étape permet de préparer un fichier de disque dur virtuel (VHDX) à partir de l’image ISO Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="76416-224">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="76416-225">Ce VDHX sera utilisé pour créer des machines virtuelles lors du déploiement.</span><span class="sxs-lookup"><span data-stu-id="76416-225">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="76416-226">Une machine virtuelle temporaire (VM de base) sera créée et Windows Server 2012 sera installé à partir du fichier ISO.</span><span class="sxs-lookup"><span data-stu-id="76416-226">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="76416-227">Après la création de la machine virtuelle, certains composants requis seront installés et la dernière mise à jour Windows sera appliquée.</span><span class="sxs-lookup"><span data-stu-id="76416-227">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="76416-228">Après cela, la machine virtuelle de base sera généralisée (sysprep) et nettoyée, seul le fichier de disque virtuel généré sera conservé.</span><span class="sxs-lookup"><span data-stu-id="76416-228">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>

> [!NOTE]
> <span data-ttu-id="76416-229">Vous devez effectuer cette étape uniquement pour la première appliance.</span><span class="sxs-lookup"><span data-stu-id="76416-229">You need to perform this step for the first appliance only.</span></span> 

<span data-ttu-id="76416-p123">Avant de réaliser cette étape, assurez-vous que le commutateur réseau d’entreprise est créé. D’autre part, veillez à ce que les paramètres suivants soient correctement configurés dans le fichier CloudConnector.ini :</span><span class="sxs-lookup"><span data-stu-id="76416-p123">Before proceeding with this step, make sure that the corpnet switch is created. Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>

- <span data-ttu-id="76416-232">[Network]CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="76416-232">[Network]CorpnetSwitchName</span></span>

- <span data-ttu-id="76416-233">[Common]BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="76416-233">[Common]BaseVMIP</span></span>

- <span data-ttu-id="76416-234">[Network]CorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="76416-234">[Network]CorpnetIPPrefixLength</span></span>

- <span data-ttu-id="76416-235">[Network]CorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="76416-235">[Network]CorpnetDefaultGateway</span></span>

- <span data-ttu-id="76416-236">[Network]CorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="76416-236">[Network]CorpnetDNSIPAddress</span></span>

<span data-ttu-id="76416-237">Démarrez une console PowerShell en tant qu’administrateur et exécutez l’applet de commande suivante pour convertir l’image ISO en disque dur virtuel (VHD) :</span><span class="sxs-lookup"><span data-stu-id="76416-237">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="76416-p124">Spécifiez le chemin d’accès complet, y compris le nom du fichier, à l’image ISO. Par exemple : C:\ISO\WindowsServer2012R2.iso.</span><span class="sxs-lookup"><span data-stu-id="76416-p124">Specify the full path, including file name, to the ISO image. For example: C:\ISO\WindowsServer2012R2.iso.</span></span>

<span data-ttu-id="76416-240">Le fichier de disque dur virtuel créé est stocké dans le dossier \Bits\VHD de l' **Annuaire de sites** .</span><span class="sxs-lookup"><span data-stu-id="76416-240">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="76416-241">Vous pouvez obtenir le chemin d’accès à l’**Annuaire de sites** en exécutant **Get-CcSiteDirectory**.</span><span class="sxs-lookup"><span data-stu-id="76416-241">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="76416-242">Par défaut, les paramètres proxy ne sont pas configurés dans la machine virtuelle de base.</span><span class="sxs-lookup"><span data-stu-id="76416-242">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="76416-243">Si un proxy est requis dans votre environnement réseau pour mettre à jour l’ordinateur virtuel par le biais de Windows Update, vous devez ajouter le commutateur-PauseBeforeUpdate lorsque vous exécutez « convert-CcIsoToVhdx ».</span><span class="sxs-lookup"><span data-stu-id="76416-243">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="76416-244">Le script est suspendu avant Windows Update et vous aurez la possibilité de configurer manuellement un proxy sur la machine virtuelle.</span><span class="sxs-lookup"><span data-stu-id="76416-244">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="76416-245">Une fois le proxy installé et que la machine virtuelle peut accéder à Internet, vous pouvez reprendre le script pour effectuer les étapes restantes.</span><span class="sxs-lookup"><span data-stu-id="76416-245">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 

### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="76416-246">Création de VHD pour un déploiement multisite</span><span class="sxs-lookup"><span data-stu-id="76416-246">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="76416-247">Cette étape facultative s’applique uniquement aux déploiements multisites.</span><span class="sxs-lookup"><span data-stu-id="76416-247">This is an optional step that applies only to multi-site deployments.</span></span>

<span data-ttu-id="76416-p127">Si vous effectuez un déploiement multisite, il n’est pas nécessaire de convertir l’image ISO en VHD pour chaque site. Vous pouvez copier le VHDX créé pour le premier site sur le serveur hôte pour un second site.</span><span class="sxs-lookup"><span data-stu-id="76416-p127">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site. You can copy the VHDX created for the first site to the host server for a second site.</span></span>

 <span data-ttu-id="76416-250">Copiez le fichier dans le même emplacement de fichier (dossier \Bits\VHD **Directory site** ) et avec le même nom de fichier, sur le serveur hôte d’un site supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="76416-250">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="76416-251">Définition de la stratégie d’exécution PowerShell sur RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="76416-251">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="76416-p128">Les scripts PowerShell fournis requièrent que la stratégie d’exécution soit définie sur RemoteSigned. Pour consulter le paramètre actuel, ouvrez une console PowerShell en tant qu’administrateur, puis exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="76416-p128">The PowerShell scripts provided require that the execution policy be set to RemoteSigned. To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="76416-254">Si elle n’est pas définie sur « RemoteSigned », exécutez l’applet de commande suivante pour la modifier :</span><span class="sxs-lookup"><span data-stu-id="76416-254">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="76416-255">Changement de la stratégie locale de groupe sur la machine hôte (versions 1.4.1 et précédentes)</span><span class="sxs-lookup"><span data-stu-id="76416-255">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="76416-256">Cette tâche n’est pas requise pour les versions de Cloud Connector 1.4.2 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="76416-256">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 

<span data-ttu-id="76416-257">Le compte CceService est créé lors du déplacement de Skype Entreprise, version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="76416-257">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="76416-258">Il exécute le service de gestion de connecteur Cloud et nécessite une autorisation de désinstallation de cloudconnector. msi.</span><span class="sxs-lookup"><span data-stu-id="76416-258">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="76416-259">Vous devez modifier le paramètre de stratégie de groupe locale sur l’ordinateur hôte de Cloud Connector pour spécifier que le registre de l’utilisateur ne doit pas être déchargé lors de sa déconnexion.</span><span class="sxs-lookup"><span data-stu-id="76416-259">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="76416-260">Suivez la procédure suivante :</span><span class="sxs-lookup"><span data-stu-id="76416-260">Follow the steps below:</span></span>

### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="76416-261">Pour modifier le paramètre de stratégie de groupe locale</span><span class="sxs-lookup"><span data-stu-id="76416-261">To change the Group Policy setting</span></span>

1. <span data-ttu-id="76416-262">Ouvrez l' **éditeur de stratégies de groupe** en exécutant gpedit. msc.</span><span class="sxs-lookup"><span data-stu-id="76416-262">Open the **Group Policy Editor** by running gpedit.msc.</span></span>

2. <span data-ttu-id="76416-263">Dans l’**Éditeur de stratégie de groupe**, sélectionnez Modèles d’administration > Système > UserProfile > Ne pas forcer le déchargement du registre de l’utilisateur lors de sa déconnexion. </span><span class="sxs-lookup"><span data-stu-id="76416-263">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 

3. <span data-ttu-id="76416-264">Définissez sa valeur sur **activé**.</span><span class="sxs-lookup"><span data-stu-id="76416-264">Set its value to **Enabled**.</span></span>

## <a name="set-up-your-office-365-tenant"></a><span data-ttu-id="76416-265">Configurez votre client Office 365.</span><span class="sxs-lookup"><span data-stu-id="76416-265">Set up your Office 365 tenant</span></span>

<span data-ttu-id="76416-266">Un client Office 365 avec Skype entreprise Online et un système téléphonique dans Office 365 est requis.</span><span class="sxs-lookup"><span data-stu-id="76416-266">An Office 365 tenant with Skype for Business Online and Phone System in Office 365 is required.</span></span> <span data-ttu-id="76416-267">Assurez-vous que votre client est configuré et configuré avant d’utiliser Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="76416-267">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>

<span data-ttu-id="76416-268">Certaines étapes d’installation d’Office 365 requièrent l’utilisation de Remote Remote PowerShell (TRPS) pour configurer votre client Office 365.</span><span class="sxs-lookup"><span data-stu-id="76416-268">Some Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Office 365 tenant.</span></span> <span data-ttu-id="76416-269">**Il doit être installé sur le serveur hôte**.</span><span class="sxs-lookup"><span data-stu-id="76416-269">**This should be installed on the host server.**</span></span> <span data-ttu-id="76416-270">Vous pouvez télécharger le module Skype entreprise Online pour PowerShell depuis : [Skype entreprise Online, module Windows PowerShell](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="76416-270">You can download the Skype for Business Online module for PowerShell from: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="76416-271">Créer un compte d’administrateur Skype entreprise dédié pour la gestion en ligne du Cloud Connector, par exemple CceOnlineManagmentAdministrator.</span><span class="sxs-lookup"><span data-stu-id="76416-271">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="76416-272">Ce compte sera utilisé pour ajouter ou supprimer un équipement, activer ou désactiver une mise à jour de SE automatique, activer ou désactiver la mise à jour automatique de fichiers binaires.</span><span class="sxs-lookup"><span data-stu-id="76416-272">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="76416-273">Définissez le mot de passe de ce compte pour qu’il n’expire jamais ; ainsi vous n’aurez jamais à le modifier pour le service.</span><span class="sxs-lookup"><span data-stu-id="76416-273">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>



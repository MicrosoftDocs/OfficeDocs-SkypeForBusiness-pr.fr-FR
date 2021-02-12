---
title: Préparation de votre appareil Cloud Connector
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
description: Découvrez comment préparer votre appliance Cloud Connector pour le déploiement et l’utilisation avec le système téléphonique (PBX cloud).
ms.openlocfilehash: 74c4885a25b4176f4d5eb3ac27926bd9528387c6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358940"
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="fa939-103">Préparation de votre appareil Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="fa939-103">Prepare your Cloud Connector appliance</span></span>

> [!Important]
> <span data-ttu-id="fa939-104">Cloud Connector Edition sera retirer le 31 juillet 2021 avec Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="fa939-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="fa939-105">Une fois votre organisation mise à niveau vers Teams, découvrez comment connecter votre réseau téléphonique local à Teams à l’aide du [routage direct.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="fa939-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="fa939-106">Découvrez comment préparer votre appliance Cloud Connector pour le déploiement et l’utilisation avec le système téléphonique (PBX cloud).</span><span class="sxs-lookup"><span data-stu-id="fa939-106">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System (Cloud PBX).</span></span>

<span data-ttu-id="fa939-107">Cette section décrit comment obtenir les fichiers d’installation de la version Cloud Connector de Skype Entreprise, installer le logiciel Cloud Connector et préparer votre appliance Cloud Connector pour le déploiement.</span><span class="sxs-lookup"><span data-stu-id="fa939-107">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="fa939-108">Une fois toutes les étapes de cette section terminées, vous êtes prêt à déployer Cloud Connector pour un ou plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="fa939-108">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="fa939-109">Si vous avez un déploiement Cloud Connector existant et que vous n’avez pas encore mis à niveau vers Cloud Connector version 2.1, voir Mise à niveau vers une nouvelle [version de Cloud Connector.](upgrade-to-a-new-version-of-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="fa939-109">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fa939-110">Microsoft prend en charge la version actuelle de Cloud Connector, version 2.1.</span><span class="sxs-lookup"><span data-stu-id="fa939-110">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="fa939-111">Si vous avez configuré la mise à jour automatique, Cloud Connector se met à jour automatiquement.</span><span class="sxs-lookup"><span data-stu-id="fa939-111">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="fa939-112">Si vous avez configuré la mise à jour manuelle, vous devrez mettre à niveau vers la version 2.1 dans les 60 jours suivant sa publication.</span><span class="sxs-lookup"><span data-stu-id="fa939-112">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="fa939-113">Microsoft prendra en charge la version précédente pendant 60 jours après la publication de la version 2.1 pour vous laisser le temps de mettre à niveau.</span><span class="sxs-lookup"><span data-stu-id="fa939-113">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 

> [!NOTE]
> <span data-ttu-id="fa939-114">Pour cloud connector version 2.1 et ultérieure, .NET Framework 4.6.1 ou version ultérieure doit être installé sur l’appliance hôte.</span><span class="sxs-lookup"><span data-stu-id="fa939-114">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="fa939-115">Pour un déploiement réussi, lorsque vous exécutez les cmdlets pour configurer La version Cloud Connector de Skype Entreprise, utilisez toujours la même session console que celle que vous avez démarrée.</span><span class="sxs-lookup"><span data-stu-id="fa939-115">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="fa939-116">Évitez de basculer vers différentes sessions pendant le déploiement et la configuration.</span><span class="sxs-lookup"><span data-stu-id="fa939-116">Avoid switching to different sessions during the deployment and configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="fa939-117">Certaines étapes sont effectuées uniquement pour la première appliance de votre déploiement : création d’un partage pour l’annuaire de sites, téléchargement des bits et préparation d’un fichier de disque dur virtuel (VHDX) à partir de l’image ISO de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="fa939-117">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="fa939-118">Télécharger le programme d’installation de la version Cloud Connector de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="fa939-118">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="fa939-119">Sur le serveur hôte sur lequel s’exécuteront les VM Cloud Connector, téléchargez les fichiers d’installation [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) :</span><span class="sxs-lookup"><span data-stu-id="fa939-119">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="fa939-120">Le serveur hôte doit pouvoir accéder à Internet pendant l’installation de Cloud Connector, car des fichiers supplémentaires sont téléchargés pendant l’installation.</span><span class="sxs-lookup"><span data-stu-id="fa939-120">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 

2. <span data-ttu-id="fa939-121">Exécutez le programme d’installation et acceptez les valeurs par défaut pendant l’installation.</span><span class="sxs-lookup"><span data-stu-id="fa939-121">Run the installer and accept the default values during the installation.</span></span>

3. <span data-ttu-id="fa939-122">Confirmez que l’installation s’est correctement terminée.</span><span class="sxs-lookup"><span data-stu-id="fa939-122">Confirm that the installation completed successfully.</span></span>

## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="fa939-123">Vérifier l’installation et configurer l’environnement</span><span class="sxs-lookup"><span data-stu-id="fa939-123">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="fa939-124">Ouvrez une console PowerShell en tant qu’administrateur et confirmez que les cmdlets de la version Cloud Connector de Skype Entreprise sont disponibles à l’aide de l’cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="fa939-124">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>

   ```powershell
   Get-Command *-Cc*
   ```

    <span data-ttu-id="fa939-125">La commande doit renvoyer la liste des cmdlets pour Skype Entreprise, version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="fa939-125">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>

2. <span data-ttu-id="fa939-126">Les fichiers VHD, SfBBits et VersionInfo seront stockés dans **l’annuaire de sites.**</span><span class="sxs-lookup"><span data-stu-id="fa939-126">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>

    <span data-ttu-id="fa939-127">Vous pouvez trouver l’emplacement de **l’annuaire de** sites avec l’cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="fa939-127">You can find the location of the **Site Directory** with the following cmdlet:</span></span>

   ```powershell
   Get-CcSiteDirectory
   ```

    <span data-ttu-id="fa939-128">La commande doit renvoyer un emplacement dans votre système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="fa939-128">The command should return a location in your file system.</span></span> <span data-ttu-id="fa939-129">L’emplacement peut être un dossier local ou un partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="fa939-129">The location can be a local folder or a file share.</span></span> <span data-ttu-id="fa939-130">L’emplacement par défaut de **l’annuaire de** sites est : %USERPROFILE%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="fa939-130">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="fa939-131">L’emplacement par défaut doit être changé en partage de fichiers sur la première appliance créée dans chaque site.</span><span class="sxs-lookup"><span data-stu-id="fa939-131">The default location should be changed to a file share on the first appliance created in each site.</span></span>

    <span data-ttu-id="fa939-132">L’emplacement que vous sélectionnez doit être :</span><span class="sxs-lookup"><span data-stu-id="fa939-132">The location you select must be:</span></span>

   - <span data-ttu-id="fa939-133">Créé sur la première appliance créée dans chaque site.</span><span class="sxs-lookup"><span data-stu-id="fa939-133">Created on the first appliance created in each site.</span></span>

   - <span data-ttu-id="fa939-134">Dossier partagé accessible par les autres serveurs hôtes (appliances) dans le même site.</span><span class="sxs-lookup"><span data-stu-id="fa939-134">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>

     <span data-ttu-id="fa939-135">Pour définir **l’annuaire de sites** sur un emplacement autre que celui par défaut, exécutez l’cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="fa939-135">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    <span data-ttu-id="fa939-136">Si vous déployez la haute disponibilité (HA) pour le site, veillez à exécuter l’cmdlet pour définir l’annuaire de sites sur le même emplacement sur chaque serveur hôte du site. </span><span class="sxs-lookup"><span data-stu-id="fa939-136">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>

    <span data-ttu-id="fa939-137">Lorsque vous vous connectez et déployez chaque appliance dans le site, assurez-vous que votre compte de connexion actuel dispose du droit d’accès à **l’annuaire de sites.**</span><span class="sxs-lookup"><span data-stu-id="fa939-137">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>

3. <span data-ttu-id="fa939-138">**L’annuaire** d’équipements est le répertoire racine de travail local pour Skype Entreprise, version Cloud Connector et l’emplacement où les certificats externes, les instances et les journaux sont enregistrés.</span><span class="sxs-lookup"><span data-stu-id="fa939-138">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="fa939-139">L’emplacement par défaut est : %USERPROFILE%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="fa939-139">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>

    <span data-ttu-id="fa939-140">Pour trouver l’emplacement du répertoire **d’équipements,** exécutez l’cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="fa939-140">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>

   ```powershell
   Get-CcApplianceDirectory
   ```

    <span data-ttu-id="fa939-141">Pour définir **l’annuaire d’équipements** sur un emplacement autre que le répertoire par défaut, exécutez l’cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="fa939-141">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    <span data-ttu-id="fa939-142">L’annuaire d’appliances doit être définie sur un dossier local sur l’appliance.</span><span class="sxs-lookup"><span data-stu-id="fa939-142">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="fa939-143">Vous devez uniquement définir **l’annuaire d’appliances** avant de commencer le déploiement de la version Cloud Connector de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="fa939-143">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="fa939-144">Si vous le modifiez après le déploiement, vous devez redéployer le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="fa939-144">If you change it after deployment, you'll need to redeploy the host server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fa939-145">Le chemin d’accès au **répertoire d’équipements** ne doit contenir aucun espace.</span><span class="sxs-lookup"><span data-stu-id="fa939-145">The path to the **Appliance Directory** must not contain any spaces.</span></span>

## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="fa939-146">Définir le chemin d’accès pour le certificat Edge externe</span><span class="sxs-lookup"><span data-stu-id="fa939-146">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="fa939-147">Exécutez l’cmdlet suivante pour définir le chemin d’accès, y compris le nom de fichier, au certificat Edge externe.</span><span class="sxs-lookup"><span data-stu-id="fa939-147">Run the following cmdlet to set the path, including the file name, to the external Edge certificate.</span></span> <span data-ttu-id="fa939-148">Par exemple : C:\certs\cce\ap.contoso.com.pfx.</span><span class="sxs-lookup"><span data-stu-id="fa939-148">For example: C:\certs\cce\ap.contoso.com.pfx.</span></span> <span data-ttu-id="fa939-149">Le certificat doit contenir des clés privées.</span><span class="sxs-lookup"><span data-stu-id="fa939-149">The certificate must contain private keys.</span></span>

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="fa939-150">Notez que le paramètre -Target est spécifique aux versions 1.4.2 et ultérieures.</span><span class="sxs-lookup"><span data-stu-id="fa939-150">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

    <span data-ttu-id="fa939-151">Spécifiez le chemin d’accès complet au certificat externe, y compris le nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="fa939-151">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="fa939-152">Le certificat peut être stocké localement ou sur un partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="fa939-152">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="fa939-153">Si le certificat est stocké dans un dossier partagé, le dossier partagé doit être créé sur la première appliance de chaque site et doit être accessible par d’autres appliances appartenant au même site.</span><span class="sxs-lookup"><span data-stu-id="fa939-153">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="fa939-154">Cette cmdlet copie le certificat externe dans **l’annuaire d’équipements.**</span><span class="sxs-lookup"><span data-stu-id="fa939-154">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fa939-155">Si vous avez mis à jour **la version 1.4.2** ou ultérieure de Cloud Connector, assurez-vous que votre certificat externe préparé contient des clés privées et la chaîne de certificats complète, y compris le certificat d’ac racine et les certificats d’ac intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="fa939-155">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.</span></span> <span data-ttu-id="fa939-156">Si vous n’avez PAS encore mis à jour **la version 1.4.2** de Cloud Connector, assurez-vous que votre certificat externe préparé contient des clés privées.</span><span class="sxs-lookup"><span data-stu-id="fa939-156">**If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="fa939-157">Ce certificat externe doit être émis par une autorité de certification qui est fiable par défaut par Windows.</span><span class="sxs-lookup"><span data-stu-id="fa939-157">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="fa939-158">Définir le chemin d’accès pour la passerelle PSTN externe/certificat SBC</span><span class="sxs-lookup"><span data-stu-id="fa939-158">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="fa939-159">Si vous utilisez TLS entre le serveur de médiation et la passerelle PSTN/SBC, exécutez l’cmdlet suivante pour définir le chemin d’accès, y compris le nom de fichier, au certificat de passerelle.</span><span class="sxs-lookup"><span data-stu-id="fa939-159">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="fa939-160">Par exemple : C:\certs\cce\sbc.contoso.com.cer.</span><span class="sxs-lookup"><span data-stu-id="fa939-160">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="fa939-161">Le certificat doit contenir l’ac racine et la chaîne intermédiaire pour le certificat affecté à la passerelle :</span><span class="sxs-lookup"><span data-stu-id="fa939-161">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> <span data-ttu-id="fa939-162">Notez que le paramètre -Target est spécifique aux versions 1.4.2 et ultérieures.</span><span class="sxs-lookup"><span data-stu-id="fa939-162">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="fa939-163">Créer des commutateurs virtuels dans le Gestionnaire Hyper-V</span><span class="sxs-lookup"><span data-stu-id="fa939-163">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="fa939-164">Ouvrez le Gestionnaire de commutateur virtuel   >  **Hyper-V,** puis sélectionnez **Nouveau gestionnaire de commutateur virtuel.**</span><span class="sxs-lookup"><span data-stu-id="fa939-164">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>

2. <span data-ttu-id="fa939-165">Créez un commutateur virtuel externe et l’attachez à la carte réseau physique connectée à votre domaine réseau interne :</span><span class="sxs-lookup"><span data-stu-id="fa939-165">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>

    <span data-ttu-id="fa939-166">Sélectionnez **Autoriser le système d’exploitation de gestion à partager cette carte réseau** pour ce commutateur virtuel.</span><span class="sxs-lookup"><span data-stu-id="fa939-166">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

3. <span data-ttu-id="fa939-167">Créez un commutateur virtuel externe et l’attachez à la carte réseau physique acheminée vers Internet :</span><span class="sxs-lookup"><span data-stu-id="fa939-167">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>

    <span data-ttu-id="fa939-168">Désélectez **Autoriser le système d’exploitation de gestion à partager cette carte réseau** pour ce commutateur virtuel.</span><span class="sxs-lookup"><span data-stu-id="fa939-168">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

4. <span data-ttu-id="fa939-169">Définissez le nom du commutateur qui connecte votre réseau de périmètre à votre domaine réseau **interne SfB CCE Corpnet Switch**.</span><span class="sxs-lookup"><span data-stu-id="fa939-169">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>

    <span data-ttu-id="fa939-170">Définissez le nom du commutateur qui connecte votre réseau de périmètre au commutateur **Internet SfB CCE Internet.**</span><span class="sxs-lookup"><span data-stu-id="fa939-170">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>

## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="fa939-171">Mettre à jour le CloudConnector.ini de configuration de l’ordinateur</span><span class="sxs-lookup"><span data-stu-id="fa939-171">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="fa939-172">Préparez le CloudConnector.ini à l’aide des informations que vous avez [recueillies](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) dans Déterminer les paramètres de déploiement dans la rubrique [Plan for Skype for Business Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="fa939-172">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>

<span data-ttu-id="fa939-173">Pour mettre à jour le fichier, exécutez d’abord l’cmdlet suivante pour obtenir l’exemple de modèle (CloudConnector.Sample.ini) :</span><span class="sxs-lookup"><span data-stu-id="fa939-173">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>

```powershell
Export-CcConfigurationSampleFile
```

<span data-ttu-id="fa939-174">L’exemple de modèle est stocké dans **l’annuaire d’équipements.**</span><span class="sxs-lookup"><span data-stu-id="fa939-174">The sample template is stored in the **Appliance Directory**.</span></span>

<span data-ttu-id="fa939-175">Une fois que vous l’avez mis à jour avec les valeurs de votre environnement, enregistrez le fichier CloudConnector.ini dans **l’annuaire d’équipements.**</span><span class="sxs-lookup"><span data-stu-id="fa939-175">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="fa939-176">Vous pouvez exécuter **Get-CcApplianceDirectory** pour déterminer le chemin d’accès au répertoire **d’équipements.**</span><span class="sxs-lookup"><span data-stu-id="fa939-176">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>

<span data-ttu-id="fa939-177">Lors de la mise à jour du fichier .ini, prenons en compte les considérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="fa939-177">When updating the .ini file, consider the following:</span></span>

> [!NOTE]
> <span data-ttu-id="fa939-178">Toutes les valeurs du fichier .ini ne sont pas abordées dans cette section, seules celles qui font l’objet d’une attention particulière sont abordées ici.</span><span class="sxs-lookup"><span data-stu-id="fa939-178">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="fa939-179">Pour obtenir la liste complète, consultez la section [Déterminer les paramètres](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) de déploiement de la rubrique [Plan for Skype for Business Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="fa939-179">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span> <span data-ttu-id="fa939-180">Pour plus d’informations sur les valeurs qui doivent être modifiées pour des appliances supplémentaires ou de nouveaux sites, voir Site unique avec haute disponibilité (HA) par rapport aux [déploiements multisesses](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) dans la rubrique Déployer plusieurs sites dans [Cloud Connector.](deploy-multiple-sites-in-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="fa939-180">For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 

- <span data-ttu-id="fa939-181">**SiteName :** La valeur par défaut **est Site1**.</span><span class="sxs-lookup"><span data-stu-id="fa939-181">**SiteName:** The default value is **Site1**.</span></span> <span data-ttu-id="fa939-182">Vous devez la mettre à jour avant de déployer Cloud Connector, car lorsque vous exécutez **Register-CcAppliance** pour inscrire une appliance sur un site existant ou nouveau, l’cmdlet utilise **SiteName** pour déterminer le site à inscrire.</span><span class="sxs-lookup"><span data-stu-id="fa939-182">You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>

     <span data-ttu-id="fa939-183">Si vous souhaitez inscrire l’appliance sur un nouveau site, la valeur de **SiteName** doit être unique et différente des sites existants.</span><span class="sxs-lookup"><span data-stu-id="fa939-183">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="fa939-184">Si vous souhaitez inscrire l’appliance sur un site existant, la valeur de **SiteName** dans le fichier .ini doit correspondre au nom défini dans la configuration de votre organisation Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="fa939-184">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="fa939-185">Si vous copiez un fichier de configuration d’un site à un autre, veillez à mettre à jour la valeur **de SiteName** pour chaque site en conséquence.</span><span class="sxs-lookup"><span data-stu-id="fa939-185">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>

- <span data-ttu-id="fa939-186">**ServerName :** Le nom du serveur ne doit pas contenir le nom de domaine et doit être limité à 15 caractères.</span><span class="sxs-lookup"><span data-stu-id="fa939-186">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>

- <span data-ttu-id="fa939-187">**HardwareType :** Si vous ne définissez pas ou ne laissez pas la valeur null, la valeur par défaut **normal** est utilisée.</span><span class="sxs-lookup"><span data-stu-id="fa939-187">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="fa939-188">Utilisez **Normal** si vous prévoyez de déployer la version plus grande de Cloud Connector pour prendre en charge 500 appels simultanés par ordinateur hôte, comme décrit dans La version Cloud Connector de [Plan pour Skype Entreprise.](plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="fa939-188">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="fa939-189">Utilisez **minimum** pour un déploiement plus petit qui prend en charge 50 appels simultanés.</span><span class="sxs-lookup"><span data-stu-id="fa939-189">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>

- <span data-ttu-id="fa939-190">**Commutateurs virtuels Internet/Réseau d’entreprise/Gestion**: ajoutez le nom des commutateurs virtuels que vous avez créés.</span><span class="sxs-lookup"><span data-stu-id="fa939-190">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="fa939-191">Pour le commutateur virtuel de gestion, laissez la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="fa939-191">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="fa939-192">Le script de déploiement crée le commutateur virtuel de gestion au début du déploiement et le supprime une fois le déploiement terminé.</span><span class="sxs-lookup"><span data-stu-id="fa939-192">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>

- <span data-ttu-id="fa939-193">**ManagementIPPrefix :** ManagementIPPrefix dans la section Réseau doit être un sous-réseau différent des autres IP internes.</span><span class="sxs-lookup"><span data-stu-id="fa939-193">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs.</span></span> <span data-ttu-id="fa939-194">Par exemple, comme le montre la valeur par défaut, ManagementIPPrefix est 192.168.213.0, tandis qu’AD IPAddress est 192.168.0.238.</span><span class="sxs-lookup"><span data-stu-id="fa939-194">For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>

    <span data-ttu-id="fa939-195">Les scripts de déploiement créent une carte réseau de gestion sur chaque ordinateur virtuel, attribuent une adresse IP de gestion et la connectent à un commutateur virtuel de gestion.</span><span class="sxs-lookup"><span data-stu-id="fa939-195">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch.</span></span> <span data-ttu-id="fa939-196">Cela permet au serveur hôte de se connecter à chaque machine virtuelle et de la gérer via ce réseau de gestion.</span><span class="sxs-lookup"><span data-stu-id="fa939-196">This enables the host server to connect to and manage each virtual machine via this management network.</span></span> <span data-ttu-id="fa939-197">Le commutateur virtuel de gestion est supprimé lorsque le déploiement est terminé.</span><span class="sxs-lookup"><span data-stu-id="fa939-197">The management virtual switch is deleted when the deployment is finished.</span></span>

- <span data-ttu-id="fa939-198">**Configurations spécifiques aux ordinateurs VM de base :** Les paramètres de cette section doivent être configurés pour l’cmdlet **Convert-CcIsoToVhdx.**</span><span class="sxs-lookup"><span data-stu-id="fa939-198">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>

    <span data-ttu-id="fa939-199">Lors de la préparation de l’image de la VM de base, la VM de base est connectée au commutateur réseau interne.</span><span class="sxs-lookup"><span data-stu-id="fa939-199">During base VM image preparation, the base VM will be connected to the internal network switch.</span></span> <span data-ttu-id="fa939-200">Les paramètres suivants sont essentiels pour que la VM puisse accéder à Internet :</span><span class="sxs-lookup"><span data-stu-id="fa939-200">The following settings are critical for the VM to be able to access the Internet:</span></span>

  - <span data-ttu-id="fa939-201">[Common] BaseVMIP : adresse IP du réseau d’entreprise à attribuer à la VM de base.</span><span class="sxs-lookup"><span data-stu-id="fa939-201">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="fa939-202">[Réseau] CorpnetDefaultGateway : passerelle par défaut à attribuer à la VM de base.</span><span class="sxs-lookup"><span data-stu-id="fa939-202">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>

  - <span data-ttu-id="fa939-203">[Réseau] CorpnetDNSIPAddress : adresse IP DNS à attribuer à la VM de base.</span><span class="sxs-lookup"><span data-stu-id="fa939-203">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="fa939-204">[Réseau] WSUSServer : adresse IP de Windows Server Update Service.</span><span class="sxs-lookup"><span data-stu-id="fa939-204">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>

  - <span data-ttu-id="fa939-205">[Réseau] WSUSStatusServer : adresse IP du serveur d’état du service Windows Server Update.</span><span class="sxs-lookup"><span data-stu-id="fa939-205">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>

  - <span data-ttu-id="fa939-206">[Réseau] EnableReferSupport : cette opération définit si la prise en charge SIP REFER est activée ou désactivée sur la configuration de la trunk sur votre IP/PBX.</span><span class="sxs-lookup"><span data-stu-id="fa939-206">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>

- <span data-ttu-id="fa939-207">**IPs internes :**</span><span class="sxs-lookup"><span data-stu-id="fa939-207">**Internal IPs:**</span></span>

  - <span data-ttu-id="fa939-208">Assurez-vous que le masque de sous-réseau CorpnetIPPrefixLength est correct.</span><span class="sxs-lookup"><span data-stu-id="fa939-208">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="fa939-209">Assurez-vous qu’il n’existe aucun conflit IP pour ces adresses IP internes.</span><span class="sxs-lookup"><span data-stu-id="fa939-209">Make sure there are no IP conflicts for these internal IPs.</span></span>

- <span data-ttu-id="fa939-210">**Fournisseurs d’IP externes :**</span><span class="sxs-lookup"><span data-stu-id="fa939-210">**External IPs:**</span></span>

  - <span data-ttu-id="fa939-211">Pour l’adresse IP publique mr : spécifiez externalMRIPs pour les adresses non NAT ou ExternalMRPublicIPs pour NAT.</span><span class="sxs-lookup"><span data-stu-id="fa939-211">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>

  - <span data-ttu-id="fa939-212">ExternalSIPIPs et ExternalMRIPs peuvent être identiques.</span><span class="sxs-lookup"><span data-stu-id="fa939-212">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>

  - <span data-ttu-id="fa939-213">Assurez-vous que le masque de sous-réseau InternetIPPrefixLength est correct.</span><span class="sxs-lookup"><span data-stu-id="fa939-213">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="fa939-214">Assurez-vous qu’il n’existe aucun conflit IP pour ces adresses IP externes.</span><span class="sxs-lookup"><span data-stu-id="fa939-214">Make sure there are no IP conflicts for these external IPs.</span></span>

- <span data-ttu-id="fa939-215">**Passerelles :**</span><span class="sxs-lookup"><span data-stu-id="fa939-215">**Gateways:**</span></span>

  - <span data-ttu-id="fa939-216">Si vous n’avez qu’une seule passerelle, supprimez la section de la passerelle secondaire.</span><span class="sxs-lookup"><span data-stu-id="fa939-216">If you have only one gateway, remove the section for the secondary gateway.</span></span> <span data-ttu-id="fa939-217">Si vous avez plus de deux passerelles, créez des sections supplémentaires en copiant et en coller une existante, puis en la mettant à jour.</span><span class="sxs-lookup"><span data-stu-id="fa939-217">If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>

  - <span data-ttu-id="fa939-218">Assurez-vous que l’adresse IP et le port des passerelles sont corrects.</span><span class="sxs-lookup"><span data-stu-id="fa939-218">Make sure that the IP address and port of the gateway(s) are correct.</span></span>

  - <span data-ttu-id="fa939-219">Pour prendre en charge la ha de niveau passerelle PSTN, quittez la passerelle secondaire et ajoutez les passerelles supplémentaires que vous utiliserez.</span><span class="sxs-lookup"><span data-stu-id="fa939-219">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="fa939-220">Vous pouvez copier et coller une entrée existante, puis la mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="fa939-220">You can copy and paste an existing entry and then update it.</span></span>

- <span data-ttu-id="fa939-221">Si vous le souhaitez, vous pouvez mettre à jour la valeur LocalRoute pour limiter les numéros d’appel sortants.</span><span class="sxs-lookup"><span data-stu-id="fa939-221">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>

## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="fa939-222">Télécharger les bits dans l’annuaire de sites</span><span class="sxs-lookup"><span data-stu-id="fa939-222">Download the bits to the Site Directory</span></span>

<span data-ttu-id="fa939-223">Exécutez l’cmdlet suivante pour télécharger les fichiers d’informations sur les bits et la version dans **l’annuaire de sites**:</span><span class="sxs-lookup"><span data-stu-id="fa939-223">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>

```powershell
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="fa939-224">Vous devez effectuer cette étape pour la première appliance uniquement.</span><span class="sxs-lookup"><span data-stu-id="fa939-224">You need to perform this step for the first appliance only.</span></span> 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="fa939-225">Préparer le disque virtuel de base (VHDX) à partir du fichier ISO téléchargé</span><span class="sxs-lookup"><span data-stu-id="fa939-225">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="fa939-226">Cette étape prépare un fichier de disque dur virtuel (VHDX) à partir de l’image ISO de Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="fa939-226">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="fa939-227">Le VHDX sera utilisé pour créer des machines virtuelles pendant le déploiement.</span><span class="sxs-lookup"><span data-stu-id="fa939-227">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="fa939-228">Une machine virtuelle temporaire (machine virtuelle de base) sera créée et Windows Server 2012 sera installé à partir du fichier ISO.</span><span class="sxs-lookup"><span data-stu-id="fa939-228">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="fa939-229">Une fois la VM créée, certains composants nécessaires sont installés et la dernière mise à jour Windows est appliquée.</span><span class="sxs-lookup"><span data-stu-id="fa939-229">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="fa939-230">À la fin, l’ordinateur virtuel de base sera généralisé (sysprep) et nettoyé, ne laissant que le fichier de disque virtuel généré.</span><span class="sxs-lookup"><span data-stu-id="fa939-230">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>

> [!NOTE]
> <span data-ttu-id="fa939-231">Vous devez effectuer cette étape pour la première appliance uniquement.</span><span class="sxs-lookup"><span data-stu-id="fa939-231">You need to perform this step for the first appliance only.</span></span> 

<span data-ttu-id="fa939-232">Avant de passer à cette étape, assurez-vous que le commutateur de réseau d’entreprise est créé.</span><span class="sxs-lookup"><span data-stu-id="fa939-232">Before proceeding with this step, make sure that the corpnet switch is created.</span></span> <span data-ttu-id="fa939-233">En outre, confirmez que les paramètres suivants sont correctement configurés dans CloudConnector.ini fichier :</span><span class="sxs-lookup"><span data-stu-id="fa939-233">Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>

- <span data-ttu-id="fa939-234">[Réseau] CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="fa939-234">[Network]CorpnetSwitchName</span></span>

- <span data-ttu-id="fa939-235">[Common] BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="fa939-235">[Common]BaseVMIP</span></span>

- <span data-ttu-id="fa939-236">[Réseau] CorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="fa939-236">[Network]CorpnetIPPrefixLength</span></span>

- <span data-ttu-id="fa939-237">[Réseau] CorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="fa939-237">[Network]CorpnetDefaultGateway</span></span>

- <span data-ttu-id="fa939-238">[Réseau] CorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="fa939-238">[Network]CorpnetDNSIPAddress</span></span>

<span data-ttu-id="fa939-239">Démarrez une console PowerShell en tant qu’administrateur et exécutez l’cmdlet suivante pour convertir l’image ISO en disque dur virtuel (VHD) :</span><span class="sxs-lookup"><span data-stu-id="fa939-239">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="fa939-240">Spécifiez le chemin d’accès complet, y compris le nom de fichier, à l’image ISO.</span><span class="sxs-lookup"><span data-stu-id="fa939-240">Specify the full path, including file name, to the ISO image.</span></span> <span data-ttu-id="fa939-241">Par exemple : C:\ISO\WindowsServer2012R2.iso.</span><span class="sxs-lookup"><span data-stu-id="fa939-241">For example: C:\ISO\WindowsServer2012R2.iso.</span></span>

<span data-ttu-id="fa939-242">Le fichier VHD créé est stocké dans le dossier **Répertoire** de sites \Bits\VHD.</span><span class="sxs-lookup"><span data-stu-id="fa939-242">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="fa939-243">Vous pouvez obtenir le chemin d’accès à **l’annuaire de** sites en exécutant **Get-CcSiteDirectory**.</span><span class="sxs-lookup"><span data-stu-id="fa939-243">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa939-244">Par défaut, les paramètres proxy ne sont pas configurés sur la VM de base.</span><span class="sxs-lookup"><span data-stu-id="fa939-244">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="fa939-245">Si un proxy est requis dans votre environnement réseau pour mettre à jour la VM via Windows Update, vous devez ajouter le commutateur -PauseBeforeUpdate lorsque vous exécutez « Convert-CcIsoToVhdx ».</span><span class="sxs-lookup"><span data-stu-id="fa939-245">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="fa939-246">Le script s’interrompt avant Windows Update et vous avez la possibilité de configurer manuellement le proxy sur l’ordinateur vm.</span><span class="sxs-lookup"><span data-stu-id="fa939-246">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="fa939-247">Une fois que le proxy est configuré et que la VM peut accéder à Internet, vous pouvez reprendre le script pour effectuer les étapes restantes.</span><span class="sxs-lookup"><span data-stu-id="fa939-247">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 

### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="fa939-248">Créer des disques durs durs pour un déploiement sur plusieurs sites</span><span class="sxs-lookup"><span data-stu-id="fa939-248">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="fa939-249">Il s’agit d’une étape facultative qui s’applique uniquement aux déploiements sur plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="fa939-249">This is an optional step that applies only to multi-site deployments.</span></span>

<span data-ttu-id="fa939-250">Si vous déployez un déploiement sur plusieurs sites, vous n’avez pas besoin de convertir l’iso en disque dur vhd pour chaque site.</span><span class="sxs-lookup"><span data-stu-id="fa939-250">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site.</span></span> <span data-ttu-id="fa939-251">Vous pouvez copier le vhDX créé pour le premier site sur le serveur hôte pour un second site.</span><span class="sxs-lookup"><span data-stu-id="fa939-251">You can copy the VHDX created for the first site to the host server for a second site.</span></span>

 <span data-ttu-id="fa939-252">Copiez le fichier au même emplacement (répertoire du **site** \Bits\dossier VHD) et avec le même nom de fichier, sur le serveur hôte pour un site supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="fa939-252">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="fa939-253">Définir la stratégie d’exécution PowerShell sur RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="fa939-253">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="fa939-254">Les scripts PowerShell fournis nécessitent que la stratégie d’exécution soit définie sur RemoteSigned.</span><span class="sxs-lookup"><span data-stu-id="fa939-254">The PowerShell scripts provided require that the execution policy be set to RemoteSigned.</span></span> <span data-ttu-id="fa939-255">Pour voir le paramètre actuel, ouvrez une console PowerShell en tant qu’administrateur, puis exécutez l’cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="fa939-255">To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="fa939-256">Si elle n’est pas définie sur « RemoteSigned », exécutez l’cmdlet suivante pour la modifier :</span><span class="sxs-lookup"><span data-stu-id="fa939-256">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="fa939-257">Modifier la stratégie de groupe locale sur l’ordinateur hôte (versions 1.4.1 et antérieures)</span><span class="sxs-lookup"><span data-stu-id="fa939-257">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="fa939-258">Cette tâche n’est pas requise pour les versions 1.4.2 et ultérieures de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="fa939-258">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 

<span data-ttu-id="fa939-259">Le compte CceService est créé lors du déploiement de la version Cloud Connector de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="fa939-259">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="fa939-260">Il exécute le service de gestion Cloud Connector et requiert l’autorisation de désinstaller le cloudconnector.msi.</span><span class="sxs-lookup"><span data-stu-id="fa939-260">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="fa939-261">Vous devez modifier le paramètre de stratégie de groupe sur l’ordinateur hôte Cloud Connector pour spécifier que le Registre de l’utilisateur ne doit pas être déchargé lorsque l’utilisateur se déconnecte.</span><span class="sxs-lookup"><span data-stu-id="fa939-261">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="fa939-262">Suivez les étapes ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="fa939-262">Follow the steps below:</span></span>

### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="fa939-263">Pour modifier le paramètre de stratégie de groupe</span><span class="sxs-lookup"><span data-stu-id="fa939-263">To change the Group Policy setting</span></span>

1. <span data-ttu-id="fa939-264">Ouvrez **l’Éditeur de stratégie de** groupe en exécutant gpedit.msc.</span><span class="sxs-lookup"><span data-stu-id="fa939-264">Open the **Group Policy Editor** by running gpedit.msc.</span></span>

2. <span data-ttu-id="fa939-265">Dans l’Éditeur de stratégie de **groupe,** accédez à Modèles d’administration > System > UserProfile > Ne déchargez pas de force le Registre utilisateur lors de la déconnexion de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fa939-265">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 

3. <span data-ttu-id="fa939-266">Définissez sa valeur sur **Activé.**</span><span class="sxs-lookup"><span data-stu-id="fa939-266">Set its value to **Enabled**.</span></span>

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="fa939-267">Configurer votre organisation Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="fa939-267">Set up your Microsoft 365 or Office 365 organization</span></span>

<span data-ttu-id="fa939-268">Une organisation Microsoft 365 ou Office 365 avec Skype Entreprise Online et le système téléphonique est requise.</span><span class="sxs-lookup"><span data-stu-id="fa939-268">A Microsoft 365 or Office 365 organization with Skype for Business Online and Phone System is required.</span></span> <span data-ttu-id="fa939-269">Assurez-vous que votre client est configuré avant d’essayer d’utiliser Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="fa939-269">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>

<span data-ttu-id="fa939-270">Certaines étapes de configuration de Microsoft 365 et d’Office 365 nécessitent l’utilisation de Tenant Remote PowerShell (TRPS) pour configurer votre organisation Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="fa939-270">Some Microsoft 365 and Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="fa939-271">**Il doit être installé sur le serveur hôte.**</span><span class="sxs-lookup"><span data-stu-id="fa939-271">**This should be installed on the host server.**</span></span> <span data-ttu-id="fa939-272">Vous pouvez télécharger le module Skype Entreprise Online pour PowerShell à partir de : Skype Entreprise [Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="fa939-272">You can download the Skype for Business Online module for PowerShell from: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="fa939-273">Créez un compte d’administrateur Skype Entreprise dédié pour la gestion en ligne de Cloud Connector, par exemple CceOnlineManagmentAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fa939-273">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="fa939-274">Ce compte sera utilisé par l’appliance pour ajouter ou supprimer une appliance, activer ou désactiver la mise à jour automatique du système d’exploitation, activer ou désactiver la mise à jour binaire automatique.</span><span class="sxs-lookup"><span data-stu-id="fa939-274">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="fa939-275">Définissez le mot de passe de ce compte pour qu’il n’expire jamais afin que vous n’avez pas besoin de le modifier pour le service chaque fois qu’il expire.</span><span class="sxs-lookup"><span data-stu-id="fa939-275">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>



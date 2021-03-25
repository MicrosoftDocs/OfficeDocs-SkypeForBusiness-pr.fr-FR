---
title: Obtenir des clients pour Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser les différents clients disponibles pour Microsoft Teams, notamment les clients Web, de bureau (Windows et Mac) et mobiles (Android, iOS).
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ff9e407edeab7d14e0d495c5f30a85abfb9ce02f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112440"
---
# <a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="4bb95-103">Obtenir des clients pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4bb95-103">Get clients for Microsoft Teams</span></span> 

<span data-ttu-id="4bb95-p101">Microsoft Teams dispose de clients Web, de bureau (Windows, Mac et Linux) et mobiles (Android et iOS). Ces clients requièrent une connexion Internet active et ne prennent pas en charge le mode hors connexion.</span><span class="sxs-lookup"><span data-stu-id="4bb95-p101">Microsoft Teams has clients available for desktop (Windows, Mac, and Linux), web, and mobile (Android and iOS). These clients all require an active internet connection and do not support an offline mode.</span></span> 

> [!Note]
> <span data-ttu-id="4bb95-106">Pour plus d’informations sur les fonctionnalités de chaque client sur différentes plateformes, consultez [les fonctionnalités de Teams par plateforme.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)</span><span class="sxs-lookup"><span data-stu-id="4bb95-106">For details about each clients' capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

> [!NOTE]
> <span data-ttu-id="4bb95-107">À compter du 29 novembre 2018, vous ne pourrez plus utiliser l’application Microsoft Teams pour Windows 10 S (Preview) disponible auprès du Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="4bb95-107">Effective November 29, 2018, you'll no longer be able to use the Microsoft Teams for Windows 10 S (Preview) app, available from the Microsoft Store.</span></span> <span data-ttu-id="4bb95-108">Au lieu de cela, vous pouvez désormais télécharger et installer le client de bureau Teams sur les appareils le Windows 10 en mode S.</span><span class="sxs-lookup"><span data-stu-id="4bb95-108">Instead, you can now download and install the Teams desktop client on devices running Windows 10 S mode.</span></span> <span data-ttu-id="4bb95-109">Pour télécharger le client de bureau, accédez à [ https://teams.microsoft.com/downloads ](https://go.microsoft.com/fwlink/?linkid=855754).</span><span class="sxs-lookup"><span data-stu-id="4bb95-109">To download the desktop client, go to [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span></span> <span data-ttu-id="4bb95-110">Les versions MSI du client de bureau Teams ne sont pas encore disponibles pour les appareils exécutant le Windows 10 en mode S.</span><span class="sxs-lookup"><span data-stu-id="4bb95-110">MSI builds of the Teams desktop client are not yet available for devices running Windows 10 S mode.</span></span>
>
> <span data-ttu-id="4bb95-111">Pour plus d’informations sur le mode Windows 10 S, consultez[Présentation de Windows 10 en mode S](https://www.microsoft.com/windows/s-mode).</span><span class="sxs-lookup"><span data-stu-id="4bb95-111">For more information about Windows 10 S mode, see [Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode).</span></span> 

## <a name="desktop-client"></a><span data-ttu-id="4bb95-112">Client de bureau </span><span class="sxs-lookup"><span data-stu-id="4bb95-112">Desktop client</span></span>

> [!TIP]
> <span data-ttu-id="4bb95-113">Regardez la session suivante pour en savoir plus sur les avantages du client bureau Windows, comment il le planifier et comment déployer : [Windows Teams Client de bureau](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="4bb95-113">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="4bb95-114">Le client de bureau Microsoft Teams est une application autonome et est également disponible dans les applications [Microsoft 365 pour les entreprises.](/deployoffice/teams-install)</span><span class="sxs-lookup"><span data-stu-id="4bb95-114">The Microsoft Teams desktop client is a standalone application and is also [available in Microsoft 365 Apps for enterprise](/deployoffice/teams-install).</span></span> <span data-ttu-id="4bb95-115">Teams est disponible pour les versions 32 bits et 64 bits de Windows (8.1 ou version ultérieure), ARM64 pour Windows 10 sur ARM et Windows Server (2012 R2 ou version ultérieure), ainsi que pour macOS et Linux (dans `.deb` et `.rpm` les formats).</span><span class="sxs-lookup"><span data-stu-id="4bb95-115">Teams is available for 32-bit and 64-bit versions of Windows (8.1 or later), ARM64 for Windows 10 on ARM, and Windows Server (2012 R2 or later), as well as for macOS and Linux (in `.deb` and `.rpm` formats).</span></span> <span data-ttu-id="4bb95-116">Sous Windows, Teams requiert .NET Framework 4.5 ou version ultérieure ; le programme d’installation Teams propose de l’installer pour vous si vous ne l’avez pas.</span><span class="sxs-lookup"><span data-stu-id="4bb95-116">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> <span data-ttu-id="4bb95-117">Sur Linux, les responsables de package tels que `apt` et `yum` tentent d’installer les conditions requises pour vous.</span><span class="sxs-lookup"><span data-stu-id="4bb95-117">On Linux, package managers such as `apt` and `yum` will try to install any requirements for you.</span></span> <span data-ttu-id="4bb95-118">Toutefois, si ce n’est pas le cas, vous devez installer les conditions requises avant d’installer Teams sur Linux.</span><span class="sxs-lookup"><span data-stu-id="4bb95-118">However, if they don't then you will need to install any reported requirements before installing Teams on Linux.</span></span>

<span data-ttu-id="4bb95-119">Les clients de bureau fournissent la prise en charge de communications en temps réel (audio, vidéo, et partage de contenu) pour les réunions d'équipe, les appels de groupes et les appels en tête-à-tête.</span><span class="sxs-lookup"><span data-stu-id="4bb95-119">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="4bb95-120">Les clients de bureau peuvent être téléchargés et installés par les utilisateurs finaux directement à partir de [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) s'ils disposent des autorisations locales appropriées (les droits d'administration ne sont pas requis pour installer le client Teams sur un PC, mais le sont pour un Mac).</span><span class="sxs-lookup"><span data-stu-id="4bb95-120">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

> [!NOTE]
> <span data-ttu-id="4bb95-121">Pour plus d’informations sur l’installation de Teams sur un Chromebook, voir Comment installer et exécuter des Microsoft Office [sur un Chromebook.](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad)</span><span class="sxs-lookup"><span data-stu-id="4bb95-121">For more details about installing Teams on a Chromebook, please see [How to install and run Microsoft Office on a Chromebook](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad).</span></span>

<span data-ttu-id="4bb95-122">Les administrateurs informatiques peuvent utiliser la méthode de leur choix pour distribuer les fichiers d'installation sur les ordinateurs de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="4bb95-122">IT admins can choose their preferred method to distribute the installation files to computers in their organization.</span></span> <span data-ttu-id="4bb95-123">Certains exemples incluent Microsoft Endpoint Configuration Manager (Windows) ou JAMF Pro (macOS).</span><span class="sxs-lookup"><span data-stu-id="4bb95-123">Some examples include Microsoft Endpoint Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="4bb95-124">Pour obtenir le package MSI de distribution Windows, voir [installer Microsoft Teams à l’aide de MSI](msi-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="4bb95-124">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="4bb95-125">La distribution du client via ces systèmes sert uniquement à l'installation initiale des clients Microsoft Teams, non pour les mises à jour futures.</span><span class="sxs-lookup"><span data-stu-id="4bb95-125">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="4bb95-126">Windows</span><span class="sxs-lookup"><span data-stu-id="4bb95-126">Windows</span></span>

<span data-ttu-id="4bb95-127">L’installation de Microsoft Teams pour Windows fournit des programmes d’installation téléchargeables dans architecture 32 bits et 64 bits.</span><span class="sxs-lookup"><span data-stu-id="4bb95-127">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="4bb95-128">L'architecture (32 bits ou 64 bits) de Microsoft Teams est indépendante de Windows et ignore celle d'Office installée.</span><span class="sxs-lookup"><span data-stu-id="4bb95-128">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="4bb95-129">Le client Windows est déployé vers le dossier AppData situé dans le profil de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4bb95-129">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="4bb95-130">Le déploiement au profil local de l’utilisateur permet au client d’être installé sans exiger des droits élevés.</span><span class="sxs-lookup"><span data-stu-id="4bb95-130">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="4bb95-131">Le client Windows exploite les emplacements suivants :</span><span class="sxs-lookup"><span data-stu-id="4bb95-131">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="4bb95-132">%LocalAppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="4bb95-132">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="4bb95-133">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span><span class="sxs-lookup"><span data-stu-id="4bb95-133">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span></span>

- <span data-ttu-id="4bb95-134">%AppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="4bb95-134">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="4bb95-135">% LocalAppData%\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="4bb95-135">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="4bb95-136">Lorsque les utilisateurs lancent un appel à l'aide du client Microsoft Teams la première fois, un message d'avertissement concernant les paramètres de pare-feu Windows peut s'afficher et requérir l'autorisation de la communication. </span><span class="sxs-lookup"><span data-stu-id="4bb95-136">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="4bb95-137">Les utilisateurs peuvent être invités à ignorer ce message, car l’appel fonctionnera, même lorsque l’avertissement est fermé.</span><span class="sxs-lookup"><span data-stu-id="4bb95-137">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![Capture d'écran d'une boîte de dialogue Alerte de sécurité Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="4bb95-139">La configuration du Pare-feu Windows sera modifiée même lorsque l’invite est fermée en sélectionnant « Annuler ».</span><span class="sxs-lookup"><span data-stu-id="4bb95-139">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”.</span></span> <span data-ttu-id="4bb95-140">Deux règles entrantes pour les teams.exe seront créées avec l’action Autoriser pour les protocoles TCP et UDP.</span><span class="sxs-lookup"><span data-stu-id="4bb95-140">Two inbound rules for teams.exe will be created with Allow action for both TCP and UDP protocols.</span></span>

<span data-ttu-id="4bb95-141">Si vous voulez empêcher Teams d’inviter les utilisateurs à créer des règles de pare-feu lorsque les utilisateurs font leur premier appel à partir de Teams, utilisez l’exemple de [script PowerShell (règle](#sample-powershell-script---inbound-firewall-rule) de pare-feu entrant ci-dessous).</span><span class="sxs-lookup"><span data-stu-id="4bb95-141">If you want to prevent Teams from prompting users to create firewall rules when the users make their first call from Teams, use the [Sample PowerShell script - inbound firewall rule](#sample-powershell-script---inbound-firewall-rule) below.</span></span> 

### <a name="mac"></a><span data-ttu-id="4bb95-142">Mac</span><span class="sxs-lookup"><span data-stu-id="4bb95-142">Mac</span></span>

<span data-ttu-id="4bb95-143">Les utilisateurs de Mac peuvent installer Teams à l’aide d’un fichier d’installation PKG pour ordinateurs macOS.</span><span class="sxs-lookup"><span data-stu-id="4bb95-143">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="4bb95-144">L’accès administrateur est requis pour installer le client Mac.</span><span class="sxs-lookup"><span data-stu-id="4bb95-144">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="4bb95-145">Le client macOS est installé dans le dossier /Applications.</span><span class="sxs-lookup"><span data-stu-id="4bb95-145">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="4bb95-146">Installer Teams en utilisant le fichier PKG</span><span class="sxs-lookup"><span data-stu-id="4bb95-146">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="4bb95-147">À partir de la [page de téléchargement Teams](https://teams.microsoft.com/downloads), sous **Mac**, cliquez sur **Télécharger**.</span><span class="sxs-lookup"><span data-stu-id="4bb95-147">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="4bb95-148">Double-cliquez sur le fichier PKG.</span><span class="sxs-lookup"><span data-stu-id="4bb95-148">Double click the PKG file.</span></span>
3. <span data-ttu-id="4bb95-149">Suivez les indications de l'Assistant Installation pour effectuer l'installation.</span><span class="sxs-lookup"><span data-stu-id="4bb95-149">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="4bb95-150">Teams sera installé dans le dossier /Applications.</span><span class="sxs-lookup"><span data-stu-id="4bb95-150">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="4bb95-151">Il s’agit d’une installation à l’échelle de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="4bb95-151">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="4bb95-152">Pendant l’installation, le PKG invite à entrer des informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="4bb95-152">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="4bb95-153">L’utilisateur doit entrer les informations d’identification d’administrateur, peu importe si l’utilisateur est un administrateur.</span><span class="sxs-lookup"><span data-stu-id="4bb95-153">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="4bb95-154">Si un utilisateur a une installation DMG de Teams et souhaite la remplacer par l’installation PKG, l’utilisateur doit :</span><span class="sxs-lookup"><span data-stu-id="4bb95-154">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="4bb95-155">Quitter l’application Teams.</span><span class="sxs-lookup"><span data-stu-id="4bb95-155">Exit the Teams app.</span></span>
2. <span data-ttu-id="4bb95-156">Désinstaller l’application Teams.</span><span class="sxs-lookup"><span data-stu-id="4bb95-156">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="4bb95-157">Installez le fichier PKG.</span><span class="sxs-lookup"><span data-stu-id="4bb95-157">Install the PKG file.</span></span>

<span data-ttu-id="4bb95-158">Les administrateurs informatiques peuvent utiliser le déploiement géré de Teams pour distribuer les fichiers d’installation pour tous les Macs dans leur organisation, tels que Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="4bb95-158">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="4bb95-159">Si vous rencontrez des problèmes en installant le PKG, faites-le nous savoir.</span><span class="sxs-lookup"><span data-stu-id="4bb95-159">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="4bb95-160">Dans la section **Commentaires** à la fin de cet article, cliquez sur **Adresser un commentaire**.</span><span class="sxs-lookup"><span data-stu-id="4bb95-160">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

### <a name="linux"></a><span data-ttu-id="4bb95-161">Linux</span><span class="sxs-lookup"><span data-stu-id="4bb95-161">Linux</span></span>

<span data-ttu-id="4bb95-162">Les utilisateurs peuvent installer des packages Linux natifs au format `.deb` et `.rpm`.</span><span class="sxs-lookup"><span data-stu-id="4bb95-162">Users will be able to install native Linux packages in `.deb` and `.rpm` formats.</span></span>
<span data-ttu-id="4bb95-163">L’installation du package DEB ou RPM installe automatiquement le référentiel de packages.</span><span class="sxs-lookup"><span data-stu-id="4bb95-163">Installing the DEB or RPM package will automatically install the package repository.</span></span>
- <span data-ttu-id="4bb95-164">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span><span class="sxs-lookup"><span data-stu-id="4bb95-164">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span></span>
- <span data-ttu-id="4bb95-165">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span><span class="sxs-lookup"><span data-stu-id="4bb95-165">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span></span> 

<span data-ttu-id="4bb95-166">La clé de signature permettant d’activer la mise à jour automatique à l’aide du gestionnaire de package du système est installée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="4bb95-166">The signing key to enable auto-updating using the system's package manager is installed automatically.</span></span> <span data-ttu-id="4bb95-167">Toutefois, elle peut également se trouver dans : (https://packages.microsoft.com/keys/microsoft.asc).</span><span class="sxs-lookup"><span data-stu-id="4bb95-167">However, it can also be found at: (https://packages.microsoft.com/keys/microsoft.asc).</span></span> <span data-ttu-id="4bb95-168">Microsoft Teams est inclus une fois par mois. Si le référentiel a été correctement installé, le gestionnaire de package système doit gérer la mise à jour automatique de la même façon que les autres packages sur le système.</span><span class="sxs-lookup"><span data-stu-id="4bb95-168">Microsoft Teams ships monthly and if the repository was installed correctly, then your system package manager should handle auto-updating in the same way as other packages on the system.</span></span>

> [!NOTE] 
> <span data-ttu-id="4bb95-169">Si vous trouvez un bogue, envoyez-le à l’aide d' `Report a Problem` à partir du client.</span><span class="sxs-lookup"><span data-stu-id="4bb95-169">If you find a bug, submit it using `Report a Problem` from within the client.</span></span> <span data-ttu-id="4bb95-170">Pour connaître les problèmes connus, consultez [équipes de support dans votre organisation.](/MicrosoftTeams/troubleshoot/teams-welcome)</span><span class="sxs-lookup"><span data-stu-id="4bb95-170">For known issues, see [Support Teams in your organization](/MicrosoftTeams/troubleshoot/teams-welcome).</span></span>
> <span data-ttu-id="4bb95-171">Pour la prise en charge de Teams pour Linux, vous pouvez utiliser le [canal de prise en charge du Forum Linux dans Microsoft Q & A](/answers/topics/teams.html).</span><span class="sxs-lookup"><span data-stu-id="4bb95-171">For Teams for Linux support you can use the [Linux forum support channel on Microsoft Q&A](/answers/topics/teams.html).</span></span> <span data-ttu-id="4bb95-172">Veillez à utiliser l’indicateur `teams-linux` quand vous publiez des questions.</span><span class="sxs-lookup"><span data-stu-id="4bb95-172">Be sure to use the `teams-linux` tag when posting questions.</span></span> 

#### <a name="install-teams-using-deb-package"></a><span data-ttu-id="4bb95-173">Installer Teams avec le package DEB</span><span class="sxs-lookup"><span data-stu-id="4bb95-173">Install Teams using DEB package</span></span>

1. <span data-ttu-id="4bb95-174">Téléchargez le package à partir de https://aka.ms/getteams.</span><span class="sxs-lookup"><span data-stu-id="4bb95-174">Download the package from https://aka.ms/getteams.</span></span>
2. <span data-ttu-id="4bb95-175">Installez à l’aide de l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4bb95-175">Install using one of the following:</span></span>  
    - <span data-ttu-id="4bb95-176">Ouvrez l’outil de gestion des packages approprié et suivez le processus d’installation de l’application Linux auto-guidée.</span><span class="sxs-lookup"><span data-stu-id="4bb95-176">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="4bb95-177">Ou, si vous aimez Terminal, tapez : `sudo dpkg -i **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="4bb95-177">Or if you love Terminal, type: `sudo dpkg -i **teams download file**`</span></span>

<span data-ttu-id="4bb95-178">Vous pouvez lancer Teams via les activités ou via un Terminal en tapant `teams`.</span><span class="sxs-lookup"><span data-stu-id="4bb95-178">You can launch Teams via Activities or via Terminal by typing `teams`.</span></span> 

#### <a name="install-teams-using-rpm-package"></a><span data-ttu-id="4bb95-179">Installer Teams avec le package RPM</span><span class="sxs-lookup"><span data-stu-id="4bb95-179">Install Teams using RPM package</span></span>

1. <span data-ttu-id="4bb95-180">Téléchargez le package à partir de https://aka.ms/getteams.</span><span class="sxs-lookup"><span data-stu-id="4bb95-180">Download the package from https://aka.ms/getteams.</span></span>
2. <span data-ttu-id="4bb95-181">Installez à l’aide de l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4bb95-181">Install using one of the following:</span></span>
    - <span data-ttu-id="4bb95-182">Ouvrez l’outil de gestion des packages approprié et suivez le processus d’installation de l’application Linux auto-guidée.</span><span class="sxs-lookup"><span data-stu-id="4bb95-182">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="4bb95-183">Ou, si vous aimez Terminal, tapez : `sudo yum install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="4bb95-183">Or if you love Terminal, type: `sudo yum install **teams download file**`</span></span>

<span data-ttu-id="4bb95-184">Vous pouvez lancer Teams via les activités ou via un Terminal en tapant `teams`.</span><span class="sxs-lookup"><span data-stu-id="4bb95-184">You can launch Teams via Activities or via Terminal by typing `teams`.</span></span>

#### <a name="install-manually-from-the-command-line"></a><span data-ttu-id="4bb95-185">Installez manuellement à partir de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="4bb95-185">Install manually from the command line</span></span>

<span data-ttu-id="4bb95-186">Installez manuellement sur des distributions Debian et Ubuntu :</span><span class="sxs-lookup"><span data-stu-id="4bb95-186">Install manually on Debian and Ubuntu distributions:</span></span>

```bash
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
 
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'
 
sudo apt update
sudo apt install teams
```

<span data-ttu-id="4bb95-187">Installez manuellement sur des distributions basées sur RHEL, Fedora et CentOS :</span><span class="sxs-lookup"><span data-stu-id="4bb95-187">Install manually on RHEL, Fedora and CentOS based distributions:</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'
 
sudo dnf check-update
sudo dnf install teams
```

<span data-ttu-id="4bb95-188">Vous pouvez également utiliser YUM au lieu de DNF :</span><span class="sxs-lookup"><span data-stu-id="4bb95-188">Alternatively, to use yum instead of dnf:</span></span>

```bash
yum check-update
sudo yum install teams
```

<span data-ttu-id="4bb95-189">Installez manuellement sur des distributions basées sur openSUSE :</span><span class="sxs-lookup"><span data-stu-id="4bb95-189">Install manually on openSUSE based distributions:</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'
 
sudo zypper refresh
sudo zypper install teams
```

## <a name="web-client"></a><span data-ttu-id="4bb95-190">Client Web</span><span class="sxs-lookup"><span data-stu-id="4bb95-190">Web client</span></span> 

<span data-ttu-id="4bb95-191">Le client Web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) est complet et fonctionnel, et peut être utilisé par divers navigateurs.</span><span class="sxs-lookup"><span data-stu-id="4bb95-191">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="4bb95-192">Le client web prend en charge les Réunions et Appels à l’aide de webRTC, aucun plug-in ou téléchargement n’est donc requis pour exécuter Teams dans un navigateur web.</span><span class="sxs-lookup"><span data-stu-id="4bb95-192">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="4bb95-193">Le navigateur doit également être configuré de manière à autoriser les cookies tiers.</span><span class="sxs-lookup"><span data-stu-id="4bb95-193">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="4bb95-194">Le client web effectue la détection de la version navigateur lors de la connexion à [ https://teams.microsoft.com ](https://go.microsoft.com/fwlink/?linkid=855753).</span><span class="sxs-lookup"><span data-stu-id="4bb95-194">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="4bb95-195">En cas de version non prise en charge, il bloquera l'accès à l'interface Web et recommandera de télécharger le client de bureau ou l'application mobile.</span><span class="sxs-lookup"><span data-stu-id="4bb95-195">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

## <a name="mobile-clients"></a><span data-ttu-id="4bb95-196">Clients mobiles</span><span class="sxs-lookup"><span data-stu-id="4bb95-196">Mobile clients</span></span>

<span data-ttu-id="4bb95-197">Les applications mobiles Microsoft Teams sont disponibles pour Android et iOS et sont destinées aux utilisateurs en déplacement pour participer aux chats basées sur la conversation et autorisent les appels audio privés.</span><span class="sxs-lookup"><span data-stu-id="4bb95-197">The Microsoft Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="4bb95-198">Pour les applications mobiles, accédez à Google Play et l’Apple App Store.</span><span class="sxs-lookup"><span data-stu-id="4bb95-198">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="4bb95-199">L’application Windows Phone a été retirée le 20 juillet 2018 et peut ne plus fonctionner.</span><span class="sxs-lookup"><span data-stu-id="4bb95-199">The Windows Phone App was retired July 20, 2018 and may no longer work.</span></span> 

<span data-ttu-id="4bb95-200">En Chine, voici comment [obtenir Teams pour Android](get-teams-android-in-china.md).</span><span class="sxs-lookup"><span data-stu-id="4bb95-200">In China, here's how to [get Teams for Android](get-teams-android-in-china.md).</span></span> 

<span data-ttu-id="4bb95-201">Les plateformes mobiles prises en charge pour les applications mobiles Microsoft Teams sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="4bb95-201">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="4bb95-202">**Android** : la prise en charge est limitée aux quatre dernières versions principales d’Android.</span><span class="sxs-lookup"><span data-stu-id="4bb95-202">**Android**: Support is limited to the last four major versions of Android.</span></span> <span data-ttu-id="4bb95-203">Lors de la publication d’une nouvelle version majeure d’Android, la nouvelle version et les trois versions précédentes sont officiellement prises en charge.</span><span class="sxs-lookup"><span data-stu-id="4bb95-203">When a new major version of Android is released, the new version and the previous three versions are officially supported.</span></span>

-   <span data-ttu-id="4bb95-204">**iOS** : la prise en charge est limitée aux deux versions principales d’iOS les plus récentes.</span><span class="sxs-lookup"><span data-stu-id="4bb95-204">**iOS**: Support is limited to the two most recent major versions of iOS.</span></span> <span data-ttu-id="4bb95-205">Lors de la publication d’une nouvelle version majeure d’iOS, la nouvelle version of iOS et les versions précédentes sont officiellement prises en charge.</span><span class="sxs-lookup"><span data-stu-id="4bb95-205">When a new major version of iOS is released, the new version of iOS and the previous version are officially supported.</span></span>

> [!NOTE]
> <span data-ttu-id="4bb95-206">La version mobile doit être disponible au public pour que Teams fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="4bb95-206">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="4bb95-207">Les applications mobiles sont distribuées et mises à jour via app store de la plateforme mobile respective uniquement.</span><span class="sxs-lookup"><span data-stu-id="4bb95-207">Mobile apps are distributed and updated through the respective mobile platform’s app store only.</span></span> <span data-ttu-id="4bb95-208">La distribution des applications mobiles via la gestion des périphériques mobiles ou le chargement de côte n’est pas prise en charge par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4bb95-208">Distribution of the mobile apps via MDM or side-loading is not supported by Microsoft.</span></span> <span data-ttu-id="4bb95-209">Une fois l’application mobile installée sur une plateforme mobile prise en charge, l’application mobile Teams elle-même est prise en charge, sous réserve que la version se trouve dans un délai de trois mois après la publication actuelle.</span><span class="sxs-lookup"><span data-stu-id="4bb95-209">Once the mobile app has been installed on a supported mobile platform, the Teams Mobile App itself will be supported provided the version is within three months of the current release.</span></span>


| | | |
|---------|---------|---------|
|![Icône montrant les points de décision](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="4bb95-211">Point de décision</span><span class="sxs-lookup"><span data-stu-id="4bb95-211">Decision Point</span></span>         |<span data-ttu-id="4bb95-212">Existe-il des restrictions empêchant les utilisateurs d'installer le client Microsoft Teams appropriés sur leur appareil ?</span><span class="sxs-lookup"><span data-stu-id="4bb95-212">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![Icône montrant les étapes suivantes](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="4bb95-214">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="4bb95-214">Next Steps</span></span>         |<span data-ttu-id="4bb95-p121">Si votre organisation limite l'installation de logiciels, veillez à ce que ce processus soit compatible avec Microsoft Teams. Note : Les droits d'administration ne sont pas requis pour l'installation d'un client sur PC, mais le sont pour un Mac.</span><span class="sxs-lookup"><span data-stu-id="4bb95-p121">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams. Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |

## <a name="client-update-management"></a><span data-ttu-id="4bb95-217">Gestion des mises à jour du client</span><span class="sxs-lookup"><span data-stu-id="4bb95-217">Client update management</span></span>

<span data-ttu-id="4bb95-218">Les clients sont actuellement mis à jour automatiquement par le service Microsoft Teams sans aucune intervention de l’administrateur informatique.</span><span class="sxs-lookup"><span data-stu-id="4bb95-218">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="4bb95-219">Si une mise à jour est disponible, le client télécharge automatiquement la mise à jour et lorsque celle-ci est inactive pendant un certain temps, le processus de mise à jour commence.</span><span class="sxs-lookup"><span data-stu-id="4bb95-219">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will begin.</span></span>

## <a name="client-side-configurations"></a><span data-ttu-id="4bb95-220">Configurations côté client</span><span class="sxs-lookup"><span data-stu-id="4bb95-220">Client-side configurations</span></span>

<span data-ttu-id="4bb95-221">Actuellement, aucune option prise en charge n'est disponible pour configurer le client via l'administration des clients, PowerShell, des objets de stratégie de groupe ou le registre.</span><span class="sxs-lookup"><span data-stu-id="4bb95-221">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

## <a name="notification-settings"></a><span data-ttu-id="4bb95-222">Paramètres des notifications</span><span class="sxs-lookup"><span data-stu-id="4bb95-222">Notification settings</span></span>

<span data-ttu-id="4bb95-p123">Aucune option n'est actuellement disponible pour les administrateurs informatiques pour configurer les paramètres des notifications côté client. Toutes les options de notification sont définies par l'utilisateur. La figure ci-après présente les paramètres client par défaut.</span><span class="sxs-lookup"><span data-stu-id="4bb95-p123">There are currently no options available for IT administrators to configure client-side notification settings. All notification options are set by the user. The figure below outlines the default client settings.</span></span>

![Capture d'écran des paramètres Notifications.](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script---inbound-firewall-rule"></a><span data-ttu-id="4bb95-227">Exemple de script PowerShell - règle de pare-feu entrant</span><span class="sxs-lookup"><span data-stu-id="4bb95-227">Sample PowerShell script - inbound firewall rule</span></span>

<span data-ttu-id="4bb95-228">Cet exemple de script qui doit s’exécuter sur des ordinateurs clients dans le contexte d’un compte d’administrateur élevé, crée une nouvelle règle de pare-feu entrant pour chaque dossier utilisateur trouvé dans c:\users.</span><span class="sxs-lookup"><span data-stu-id="4bb95-228">This sample script, which needs to run on client computers in the context of an elevated administrator account, will create a new inbound firewall rule for each user folder found in c:\users.</span></span> <span data-ttu-id="4bb95-229">Lorsque Teams détecte cette règle, il permet d’empêcher l’application Teams d’inviter les utilisateurs à créer des règles de pare-feu lorsque les utilisateurs passent leur premier appel à partir de Teams.</span><span class="sxs-lookup"><span data-stu-id="4bb95-229">When Teams finds this rule, it will prevent the Teams application from prompting users to create firewall rules when the users make their first call from Teams.</span></span> 

```powershell
<#
.SYNOPSIS
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($null -ne $users) {
    foreach ($user in $users) {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath) {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue)) {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}
```
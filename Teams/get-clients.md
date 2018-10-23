---
title: Obtenir des clients pour Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/05/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: vichau, majafry
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser les différents clients disponibles pour Microsoft Teams, notamment les clients Web, de bureau (Windows et Mac) et mobiles (Android, iOS, et Windows Phone).
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: a24f4ba3c9470827c8a73bf8ac234cf7ae8467e8
ms.sourcegitcommit: 044286f9dec2743a622bdaeac03469418cfdfa0d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/22/2018
ms.locfileid: "25372787"
---
<a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="5e668-103">Obtenir des clients pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5e668-103">Get clients for Microsoft Teams</span></span> 
===========================

<span data-ttu-id="5e668-104">Microsoft Teams dispose de clients mobiles et disponibles pour les web (Windows et Mac) du bureau (Android, iOS et Windows Phone).</span><span class="sxs-lookup"><span data-stu-id="5e668-104">Microsoft Teams has clients available for desktop (Windows and Mac), web, and mobile (Android,  iOS, and Windows Phone).</span></span> <span data-ttu-id="5e668-105">Ces clients requièrent une connexion Internet active et ne prennent pas en charge le mode hors connexion.</span><span class="sxs-lookup"><span data-stu-id="5e668-105">These clients all require an active internet connection and do not support an offline mode.</span></span>

<a name="desktop-client"></a><span data-ttu-id="5e668-106">Client de bureau</span><span class="sxs-lookup"><span data-stu-id="5e668-106">Desktop client</span></span>
--------------

> [!Tip]
> <span data-ttu-id="5e668-107">Regarder la session suivante pour en savoir plus sur les avantages du bureau Windows Client, comment planifier et comment le déployer : [Client de bureau Windows équipes](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="5e668-107">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="5e668-108">Le client de bureau Microsoft Teams est une application autonome et actuellement ne fait pas partie d’Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="5e668-108">The Microsoft Teams desktop client is a standalone application and currently not part of Office 365 ProPlus.</span></span> <span data-ttu-id="5e668-109">Les équipes est disponible pour Windows (7 +), les versions 32 bits et 64 bits et Mac OS (10.10 +).</span><span class="sxs-lookup"><span data-stu-id="5e668-109">Teams is available for both Windows (7+), both 32-bit and 64-bit versions, and macOS (10.10+).</span></span> <span data-ttu-id="5e668-110">Sous Windows, les équipes nécessite le .NET Framework 4.5 ou version ultérieure ; le programme d’installation équipes propose d’installer pour vous si vous ne l’avez pas.</span><span class="sxs-lookup"><span data-stu-id="5e668-110">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> 

<span data-ttu-id="5e668-111">Les clients de bureau prennent en charge de communications en temps réel (partage de contenu, vidéo et audio) pour les réunions de l’équipe, les appels en tête-à-tête group appelant et privés.</span><span class="sxs-lookup"><span data-stu-id="5e668-111">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="5e668-112">Clients de bureau peuvent être téléchargées et installées par les utilisateurs finaux directement à partir de [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) s’ils disposent des autorisations appropriées locales (des droits d’administration ne sont pas requis pour installer le client équipes sur un PC, mais sont requis sur un Mac).</span><span class="sxs-lookup"><span data-stu-id="5e668-112">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="5e668-113">Les administrateurs informatiques peuvent choisir leur méthode préférée pour distribuer les fichiers d’installation sur les ordinateurs de leur organisation, comme System Center Configuration Manager (Windows) ou Jamf Pro (Mac OS).</span><span class="sxs-lookup"><span data-stu-id="5e668-113">IT admins can choose their preferred method to distribute the installation files to computers in their organization, such as System Center Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="5e668-114">Pour obtenir le package MSI pour la distribution de Windows, voir [installer des équipes de Microsoft à l’aide de MSI](msi-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="5e668-114">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5e668-115">La distribution du client via ces systèmes sert uniquement à l'installation initiale des clients Microsoft Teams, non pour les mises à jour futures.</span><span class="sxs-lookup"><span data-stu-id="5e668-115">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="5e668-116">Windows</span><span class="sxs-lookup"><span data-stu-id="5e668-116">Windows</span></span>

<span data-ttu-id="5e668-117">L’installation de Microsoft Teams pour Windows fournit des programmes d’installation téléchargeables dans l’architecture 32 bits et 64 bits.</span><span class="sxs-lookup"><span data-stu-id="5e668-117">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="5e668-118">L’architecture (32 bits et 64 bits) de Microsoft Teams est indépendante de l’architecture de Windows et Office est installé.</span><span class="sxs-lookup"><span data-stu-id="5e668-118">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="5e668-119">Le client Windows est déployé dans le dossier AppData situé dans le profil de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5e668-119">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="5e668-120">Déploiement sur le profil d’utilisateur local permet au client d’être installé sans disposer de droits élevés.</span><span class="sxs-lookup"><span data-stu-id="5e668-120">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="5e668-121">Le client Windows tire parti des emplacements suivants :</span><span class="sxs-lookup"><span data-stu-id="5e668-121">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="5e668-122">%LocalAppData%\\Microsoft\\équipes</span><span class="sxs-lookup"><span data-stu-id="5e668-122">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="5e668-123">%LocalAppData%\\Microsoft\\TeamsMeetingsAddin</span><span class="sxs-lookup"><span data-stu-id="5e668-123">%LocalAppData%\\Microsoft\\TeamsMeetingsAddin</span></span>

- <span data-ttu-id="5e668-124">%AppData%\\Microsoft\\équipes</span><span class="sxs-lookup"><span data-stu-id="5e668-124">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="5e668-125">%LocalAppData%\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="5e668-125">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="5e668-126">Lorsque les utilisateurs lancer un appel à l’aide du client Microsoft Teams pour la première fois, ils peuvent noter un avertissement vous demandant aux utilisateurs permettre la communication avec les paramètres du pare-feu Windows.</span><span class="sxs-lookup"><span data-stu-id="5e668-126">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="5e668-127">Les utilisateurs peuvent demander à ignorer ce message, car l’appel fonctionne, même lorsque le message d’avertissement est rejeté.</span><span class="sxs-lookup"><span data-stu-id="5e668-127">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![Capture d'écran d'une boîte de dialogue Alerte de sécurité Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="5e668-p106">La configuration de pare-feu Windows sera modifiée même si l'invite est ignorée en sélectionnant Annuler. Deux règles de trafic entrant pour teams.exe seront créées avec une action de blocage pour les protocoles TCP et UDP.</span><span class="sxs-lookup"><span data-stu-id="5e668-p106">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”. Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

### <a name="mac"></a><span data-ttu-id="5e668-131">Mac</span><span class="sxs-lookup"><span data-stu-id="5e668-131">Mac</span></span>

<span data-ttu-id="5e668-132">Les utilisateurs de Mac peuvent installer des équipes à l’aide d’un fichier d’installation PKG pour les ordinateurs Mac OS.</span><span class="sxs-lookup"><span data-stu-id="5e668-132">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="5e668-133">L'accès administrateur est obligatoire pour installer le client Mac.</span><span class="sxs-lookup"><span data-stu-id="5e668-133">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="5e668-134">Le client Mac OS est installé dans le dossier/applications.</span><span class="sxs-lookup"><span data-stu-id="5e668-134">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="5e668-135">Installer des équipes en utilisant le fichier PKG</span><span class="sxs-lookup"><span data-stu-id="5e668-135">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="5e668-136">À partir de la [page de téléchargement des équipes](https://teams.microsoft.com/downloads), sous **Mac**, cliquez sur **Télécharger**.</span><span class="sxs-lookup"><span data-stu-id="5e668-136">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="5e668-137">Double-cliquez sur le fichier PKG.</span><span class="sxs-lookup"><span data-stu-id="5e668-137">Double click the PKG file.</span></span>
3. <span data-ttu-id="5e668-138">Suivez l’Assistant d’installation pour terminer l’installation.</span><span class="sxs-lookup"><span data-stu-id="5e668-138">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="5e668-139">Les équipes seront installés au dossier/applications.</span><span class="sxs-lookup"><span data-stu-id="5e668-139">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="5e668-140">Il s’agit d’une installation d’échelle de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="5e668-140">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="5e668-141">Pendant l’installation, la PKG vous invite à des informations d’identification d’administration.</span><span class="sxs-lookup"><span data-stu-id="5e668-141">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="5e668-142">L’utilisateur doit entrer les informations d’identification d’administration, quel que soit ou non l’utilisateur est un administrateur.</span><span class="sxs-lookup"><span data-stu-id="5e668-142">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="5e668-143">Si un utilisateur disposant d’une installation DMG des équipes actuellement et remplacez-la par l’installation PKG souhaite, l’utilisateur doit :</span><span class="sxs-lookup"><span data-stu-id="5e668-143">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="5e668-144">Quittez l’application d’équipes.</span><span class="sxs-lookup"><span data-stu-id="5e668-144">Exit the Teams app.</span></span>
2. <span data-ttu-id="5e668-145">Désinstaller l’application d’équipes.</span><span class="sxs-lookup"><span data-stu-id="5e668-145">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="5e668-146">Installez le fichier PKG.</span><span class="sxs-lookup"><span data-stu-id="5e668-146">Install the PKG file.</span></span>

<span data-ttu-id="5e668-147">Les administrateurs informatiques peuvent utiliser des équipes de déploiement pour distribuer les fichiers d’installation pour tous les Mac dans leur organisation, telles que Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="5e668-147">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="5e668-148">Si vous rencontrez des problèmes d’installation le PKG, faites-le nous savoir.</span><span class="sxs-lookup"><span data-stu-id="5e668-148">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="5e668-149">Dans la section **des commentaires** à la fin de cet article, cliquez sur **commentaires sur le produit**.</span><span class="sxs-lookup"><span data-stu-id="5e668-149">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

<a name="web-client"></a><span data-ttu-id="5e668-150">Client Web</span><span class="sxs-lookup"><span data-stu-id="5e668-150">Web client</span></span> 
----------

<span data-ttu-id="5e668-151">Le client web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) est un client complète et fonctionnel qui peut être utilisé à partir de nombreux navigateurs.</span><span class="sxs-lookup"><span data-stu-id="5e668-151">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="5e668-152">Le client web prend en charge les réunions et les appels à l’aide de webRTC, donc il n’existe aucun plug-in ou télécharger requises pour exécuter des équipes dans un navigateur web.</span><span class="sxs-lookup"><span data-stu-id="5e668-152">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="5e668-153">Le navigateur doit être configuré pour autoriser les cookies tiers.</span><span class="sxs-lookup"><span data-stu-id="5e668-153">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="5e668-154">Le client web exécute la détection de version du navigateur lorsqu’ils se connectent à [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span><span class="sxs-lookup"><span data-stu-id="5e668-154">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="5e668-155">Si une version de navigateur non pris en charge est détectée, il bloque l’accès à l’interface web et est recommandé que l’utilisateur télécharger le client de bureau ou d’une application mobile.</span><span class="sxs-lookup"><span data-stu-id="5e668-155">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

<a name="mobile-clients"></a><span data-ttu-id="5e668-156">Clients mobiles</span><span class="sxs-lookup"><span data-stu-id="5e668-156">Mobile clients</span></span>
--------------

<span data-ttu-id="5e668-157">Les applications mobiles Microsoft Teams sont disponibles pour Android et iOS et sont destinées aux utilisateurs atteindre la participation à des conversations en fonction de conversation et autorisent les appels audio d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="5e668-157">The Microsoft Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="5e668-158">Pour les applications mobiles, accédez aux magasins mobiles pertinents Google lire et l’App Store Apple.</span><span class="sxs-lookup"><span data-stu-id="5e668-158">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="5e668-159">L’application Windows Phone a été retirée 20 juillet 2018, voir [ici](https://support.microsoft.com/en-us/help/4230833/windows-phone-app-for-microsoft-teams-is-retiring) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="5e668-159">The Windows Phone App was retired July 20, 2018 see [here](https://support.microsoft.com/en-us/help/4230833/windows-phone-app-for-microsoft-teams-is-retiring) for more information.</span></span>

<span data-ttu-id="5e668-160">Les plateformes mobiles prises en charge pour les applications mobiles Microsoft Teams sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="5e668-160">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="5e668-161">**Android** : 4.4 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="5e668-161">**Android**: 4.4 or later</span></span>

-   <span data-ttu-id="5e668-162">**iOS**:  10.0 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="5e668-162">**iOS**: 10.0 or later</span></span>

> [!NOTE]
> <span data-ttu-id="5e668-163">La version mobile doit être disponible au public dans l’ordre des équipes fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="5e668-163">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="5e668-164">Les applications mobiles sont distribuées et mises à jour uniquement via la boutique d'applications de la plateforme mobile respective et ne peuvent pas être distribuées via des solutions MDM (gestion des périphériques mobiles) ni utilisées comme version de test.</span><span class="sxs-lookup"><span data-stu-id="5e668-164">Mobile apps are distributed and updated through the respective mobile platform’s app store only, and are not available to be distributed through MDM (mobile device management) solutions or side-loaded.</span></span>


| | | |
|---------|---------|---------|
|![Icône Point de décision.](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="5e668-166">Point de décision</span><span class="sxs-lookup"><span data-stu-id="5e668-166">Decision Point</span></span>         |<span data-ttu-id="5e668-167">Existe-il des restrictions empêchant les utilisateurs d'installer le client Microsoft Teams appropriés sur leur appareil ?</span><span class="sxs-lookup"><span data-stu-id="5e668-167">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![Icône Étapes suivantes.](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="5e668-169">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="5e668-169">Next Steps</span></span>         |<span data-ttu-id="5e668-p114">Si votre organisation limite l'installation de logiciels, veillez à ce que ce processus soit compatible avec Microsoft Teams. Note : Les droits d'administration ne sont pas requis pour l'installation d'un client sur PC, mais le sont pour un Mac.</span><span class="sxs-lookup"><span data-stu-id="5e668-p114">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams. Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |


  <span data-ttu-id="5e668-172"><span id="_Hlk477176062" class="anchor"></span>  Point de décision   Existe-il des restrictions empêchant les utilisateurs d'installer le client Microsoft Teams appropriés sur leur appareil ?</span><span class="sxs-lookup"><span data-stu-id="5e668-172"><span id="_Hlk477176062" class="anchor"></span>  Decision Point   Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>

<a name="client-update-management"></a><span data-ttu-id="5e668-173">Gestion des mises à jour du client</span><span class="sxs-lookup"><span data-stu-id="5e668-173">Client update management</span></span>
------------------------

<span data-ttu-id="5e668-p115">Actuellement, les clients sont automatiquement mis à jour par le service de Microsoft Teams ; aucune intervention de l'administrateur informatique n'est requise. Si une mise à jour est disponible, le client la téléchargera automatiquement et lorsque l'application est inactive pendant un certain temps, le processus de mise à jour se lancera.</span><span class="sxs-lookup"><span data-stu-id="5e668-p115">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required. If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will kick off.</span></span>

<a name="client-side-configurations"></a><span data-ttu-id="5e668-176">Configurations côté client</span><span class="sxs-lookup"><span data-stu-id="5e668-176">Client-side configurations</span></span>
---------------------------

<span data-ttu-id="5e668-177">Actuellement, aucune option prise en charge n'est disponible pour configurer le client via l'administration des clients, PowerShell, des objets de stratégie de groupe ou le registre.</span><span class="sxs-lookup"><span data-stu-id="5e668-177">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

<a name="notification-settings"></a><span data-ttu-id="5e668-178">Paramètres des notifications</span><span class="sxs-lookup"><span data-stu-id="5e668-178">Notification settings</span></span>
----------------------------

<span data-ttu-id="5e668-p116">Aucune option n'est actuellement disponible pour les administrateurs informatiques pour configurer les paramètres des notifications côté client. Toutes les options de notification sont définies par l'utilisateur. La figure ci-après présente les paramètres client par défaut.</span><span class="sxs-lookup"><span data-stu-id="5e668-p116">There are currently no options available for IT administrators to configure client-side notification settings. All notification options are set by the user. The figure below outlines the default client settings.</span></span>

![Capture d'écran des paramètres Notifications.](media/Get_clients_for_Microsoft_Teams_image6.png)

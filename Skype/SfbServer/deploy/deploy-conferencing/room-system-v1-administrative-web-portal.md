---
title: Déploiement du portail Web d’administration de SRS v1 dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Le portail Web d’administration Skype entreprise Server Skype Room Systems v1 (SRS v1, anciennement appelé Lync Room System) est un portail Web que les organisations peuvent utiliser pour gérer leurs salles de conférence de Skype Room Systems. Les administrateurs peuvent utiliser le portail Web d’administration de SRS v1 pour surveiller l’état de l’appareil, par exemple en surveillant les périphériques audio/vidéo. Grâce à ce portail, les administrateurs peuvent collecter à distance des informations de diagnostic pour surveiller l’état de la salle de conférence.
ms.openlocfilehash: d718adb60437fdd7e08724a5ba5fc48fa120425e
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2020
ms.locfileid: "42045897"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a><span data-ttu-id="f4866-105">Déploiement du portail Web d’administration de SRS v1 dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="f4866-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>

<span data-ttu-id="f4866-106">Le portail Web d’administration Skype entreprise Server Skype Room Systems v1 (SRS v1, anciennement appelé Lync Room System) est un portail Web que les organisations peuvent utiliser pour gérer leurs salles de conférence de Skype Room Systems.</span><span class="sxs-lookup"><span data-stu-id="f4866-106">The Skype for Business Server Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="f4866-107">Les administrateurs peuvent utiliser le portail Web d’administration de SRS v1 pour surveiller l’état de l’appareil, par exemple en surveillant les périphériques audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="f4866-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="f4866-108">Grâce à ce portail, les administrateurs peuvent collecter à distance des informations de diagnostic pour surveiller l’état de la salle de conférence.</span><span class="sxs-lookup"><span data-stu-id="f4866-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="f4866-109">Pour utiliser cette fonctionnalité, le portail Web d’administration de SRS v1 doit être déployé sur chaque serveur frontal Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f4866-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="f4866-110">Ce guide fournit aux administrateurs des instructions sur l’installation et la configuration du portail Web d’administration de SRS.</span><span class="sxs-lookup"><span data-stu-id="f4866-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="f4866-111">Elle est destinée aux administrateurs qui ont des connaissances sur l’administration de Skype entreprise Server et qui disposent des droits d’administrateur pour modifier la topologie Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f4866-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>

<span data-ttu-id="f4866-112">Une fois que le portail Web d’administration de SRS v1 est déployé sur le serveur, les administrateurs peuvent vérifier l’état des appareils SRS v1 en ouvrant une session sur le site à partir de leurs propres ordinateurs ou portables.</span><span class="sxs-lookup"><span data-stu-id="f4866-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4866-113">Téléchargez le [portail Web d’administration de Microsoft Skype Room Systems v1 pour Skype entreprise Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span><span class="sxs-lookup"><span data-stu-id="f4866-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="f4866-114">Dans cet article :</span><span class="sxs-lookup"><span data-stu-id="f4866-114">In this topic:</span></span>

- [<span data-ttu-id="f4866-115">Configuration de votre environnement pour le portail Web d’administration de SRS v1</span><span class="sxs-lookup"><span data-stu-id="f4866-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)

- [<span data-ttu-id="f4866-116">Installer le portail Web d’administration de SRS v1</span><span class="sxs-lookup"><span data-stu-id="f4866-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)

- [<span data-ttu-id="f4866-117">Utiliser le portail Web d’administration de SRS</span><span class="sxs-lookup"><span data-stu-id="f4866-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="f4866-118">Configuration de votre environnement pour le portail Web d’administration de SRS v1</span><span class="sxs-lookup"><span data-stu-id="f4866-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="f4866-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="f4866-119"><a name="Config_Env"> </a></span></span>

<span data-ttu-id="f4866-120">Pour utiliser le portail Web d’administration de SRS v1, vous devrez installer ou configurer les éléments prérequis suivants.</span><span class="sxs-lookup"><span data-stu-id="f4866-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4866-121">Si le serveur est configuré avec l’authentification Kerberos et NTLM et que SRS est en cours d’exécution sur un ordinateur qui n’est pas lié au domaine, l’authentification Kerberos échoue et l’utilisateur ne voit pas l’état de SRS dans le portail d’administration.</span><span class="sxs-lookup"><span data-stu-id="f4866-121">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal.</span></span> <span data-ttu-id="f4866-122">Pour résoudre ce problème, configurez le serveur avec l’authentification NTLM ou l’authentification NTLM et TLS-DSK (sans Kerberos) ou associez l’ordinateur SRS au domaine.</span><span class="sxs-lookup"><span data-stu-id="f4866-122">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span>

1. <span data-ttu-id="f4866-123">Installez les mises à jour cumulatives de Skype entreprise Server dans la topologie Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f4866-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span>

    <span data-ttu-id="f4866-124">Pour obtenir la mise à jour ou voir ce qu’elle contient, reportez-vous à la rubrique [mises à jour pour Skype entreprise Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="f4866-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

2. <span data-ttu-id="f4866-125">Créez un utilisateur Active Directory compatible SIP.</span><span class="sxs-lookup"><span data-stu-id="f4866-125">Create a SIP-enabled Active Directory user.</span></span>

    <span data-ttu-id="f4866-126">Le portail Web d’administration de SRS v1 utilise ces informations d’identification pour demander des informations à partir de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f4866-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="f4866-127">Le nom d’utilisateur dans les exemples donnés est LRSApp.</span><span class="sxs-lookup"><span data-stu-id="f4866-127">The username in the examples given is LRSApp.</span></span>

3. <span data-ttu-id="f4866-128">Créez un groupe de sécurité Active Directory avec le nom LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="f4866-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>

    <span data-ttu-id="f4866-129">Créez le groupe avec une étendue de groupe globale et de type de groupe comme sécurité.</span><span class="sxs-lookup"><span data-stu-id="f4866-129">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="f4866-130">Les utilisateurs à extension SIP qui sont ajoutés à ce groupe seront autorisés à afficher la liste des salles et à exécuter certaines commandes, telles que la collecte des journaux.</span><span class="sxs-lookup"><span data-stu-id="f4866-130">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4. <span data-ttu-id="f4866-131">Créez un groupe de sécurité Active Directory avec le nom LRSFullAccessAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="f4866-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>

    <span data-ttu-id="f4866-132">Créez le groupe avec une étendue de groupe comme global et un type de groupe pour les utilisateurs activés pour la sécurité. SIP qui sont ajoutés à ce groupe sont autorisés à utiliser toutes les fonctionnalités du portail d’administration sur une seule salle Skype.</span><span class="sxs-lookup"><span data-stu-id="f4866-132">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room.</span></span> <span data-ttu-id="f4866-133">Pour inclure la prise en charge de la gestion en bloc des salles Skype, reportez-vous à l’étape 5.</span><span class="sxs-lookup"><span data-stu-id="f4866-133">To include support for bulk management of Skype rooms, refer to step 5.</span></span>

     ![Liste des groupes d’administration avec le rôle de groupe de sécurité](../../media/LRS_LRSFullAccessAdminGroup.png)

5. <span data-ttu-id="f4866-135">Créez un groupe de sécurité Active Directory avec le nom LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="f4866-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span>

    <span data-ttu-id="f4866-136">Créez le groupe avec une étendue de groupe globale et de type de groupe comme sécurité.</span><span class="sxs-lookup"><span data-stu-id="f4866-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="f4866-137">Les utilisateurs activés pour SIP qui sont ajoutés à ce groupe sont autorisés à utiliser toutes les fonctionnalités du portail d’administration, y compris la gestion en bloc des salles Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="f4866-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span>

6. <span data-ttu-id="f4866-138">Ajoutez LRSFullAccessAdminGroup en tant que membre de LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="f4866-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>

     ![Page des membres de propriétés LRSSupportAdminGroup](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. <span data-ttu-id="f4866-140">Créez un utilisateur Active Directory activé pour SIP avec le nom LRSSupport.</span><span class="sxs-lookup"><span data-stu-id="f4866-140">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="f4866-141">Ajoutez cet utilisateur à LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="f4866-141">Add this user to LRSSupportAdminGroup.</span></span>

     ![Page des membres de propriétés LRSSupportAdminGroup](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. <span data-ttu-id="f4866-143">Installez [ASP.NET MVC 4 pour Visual Studio 2010 SP1 et Visual Web developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span><span class="sxs-lookup"><span data-stu-id="f4866-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>

## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="f4866-144">Installer le portail Web d’administration de SRS v1</span><span class="sxs-lookup"><span data-stu-id="f4866-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="f4866-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="f4866-145"><a name="Install_SRS"> </a></span></span>

<span data-ttu-id="f4866-146">Téléchargez le [portail Web d’administration de Microsoft Skype Room Systems v1 pour Skype entreprise Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span><span class="sxs-lookup"><span data-stu-id="f4866-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="f4866-147">Pour installer le portail Web d’administration de SRS v1, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="f4866-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>

1. <span data-ttu-id="f4866-148">Configurez le port d’applications approuvées en exécutant l’applet de commande suivante dans Skype entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="f4866-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="f4866-149">Pour installer le portail de salle de réunion, téléchargez **MeetingRoomPortalInstaller. msi** , puis exécutez-le en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="f4866-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>

3. <span data-ttu-id="f4866-150">Ouvrez le fichier Web. config à partir de l’emplacement suivant :</span><span class="sxs-lookup"><span data-stu-id="f4866-150">Open the Web.config file from the following location:</span></span>

    <span data-ttu-id="f4866-151">% Program Files%\Skype for Business Server 2015 \ Web Components\Meeting Room Portal\Int\Handler</span><span class="sxs-lookup"><span data-stu-id="f4866-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span></span>\

4. <span data-ttu-id="f4866-152">Dans le fichier Web. config, remplacez PortalUserName par le nom d’utilisateur créé à l’étape 2 sous la section «[configurer votre environnement pour le portail Web d’administration de SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)» (le nom recommandé à l’étape est LRSApp) :</span><span class="sxs-lookup"><span data-stu-id="f4866-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span>

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="f4866-153">Étant donné que le portail d’administration de SRS v1 est une application approuvée, vous n’avez pas besoin de fournir le mot de passe dans la configuration du portail.</span><span class="sxs-lookup"><span data-stu-id="f4866-153">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="f4866-154">Si cet utilisateur utilise un autre bureau d’enregistrement que le serveur d’inscriptions local, vous devez spécifier le serveur d’inscriptions en ajoutant la ligne suivante dans le fichier Web. config :</span><span class="sxs-lookup"><span data-stu-id="f4866-154">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="f4866-155">Si le port utilisé n’est pas 5061, ajoutez la ligne suivante dans le fichier Web. config :</span><span class="sxs-lookup"><span data-stu-id="f4866-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="f4866-156">Vérifier l’installation du portail Web d’administration de SRS</span><span class="sxs-lookup"><span data-stu-id="f4866-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="f4866-157">Pour vérifier l’installation du portail Web d’administration de SRS v1, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f4866-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>

1. <span data-ttu-id="f4866-158">Sur un serveur frontal, accédez à l’URL suivante :</span><span class="sxs-lookup"><span data-stu-id="f4866-158">On a Front End server, browse to the following URL:</span></span>

    <span data-ttu-id="f4866-159">https:// \<fe-server\> /LRS</span><span class="sxs-lookup"><span data-stu-id="f4866-159">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="f4866-160">Vous ne devez pas voir les erreurs, comme illustré dans l’image suivante :</span><span class="sxs-lookup"><span data-stu-id="f4866-160">You should not see any errors, as shown in the following image:</span></span>

     ![Écran de connexion du portail d’administration Lync Room System](../../media/LRS_AdminPortalSignIn.png)

2. <span data-ttu-id="f4866-162">Si aucune erreur ne s’affiche, essayez d’accéder à l’URL suivante à partir de n’importe quel autre ordinateur de la topologie :</span><span class="sxs-lookup"><span data-stu-id="f4866-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>

    <span data-ttu-id="f4866-163">https:// \<fe-server\> /LRS</span><span class="sxs-lookup"><span data-stu-id="f4866-163">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="f4866-164">Pour accéder à la page, vous devez ajouter les enregistrements DNS comme décrit dans la section «[enregistrements DNS requis pour la connexion automatique des clients](https://go.microsoft.com/fwlink/p/?LinkId=318056)».</span><span class="sxs-lookup"><span data-stu-id="f4866-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](https://go.microsoft.com/fwlink/p/?LinkId=318056)."</span></span>

## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="f4866-165">Utiliser le portail Web d’administration de SRS</span><span class="sxs-lookup"><span data-stu-id="f4866-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="f4866-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="f4866-166"><a name="Use_Portal"> </a></span></span>

<span data-ttu-id="f4866-167">Après avoir déployé SRS sur le serveur, vous pouvez vérifier l’état de toutes les salles SRS en vous connectant au portail Web d’administration de SRS v1 à partir d’un navigateur.</span><span class="sxs-lookup"><span data-stu-id="f4866-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>

### <a name="sign-in"></a><span data-ttu-id="f4866-168">Connexion</span><span class="sxs-lookup"><span data-stu-id="f4866-168">Sign in</span></span>

1. <span data-ttu-id="f4866-169">Accédez à l’URL suivante :</span><span class="sxs-lookup"><span data-stu-id="f4866-169">Browse to the following URL:</span></span>

    <span data-ttu-id="f4866-170">https:// \<fe-server\> /LRS</span><span class="sxs-lookup"><span data-stu-id="f4866-170">https://\<fe-server\>/lrs</span></span>

2. <span data-ttu-id="f4866-171">Entrez les informations d’identification du compte LRSSupport ou d’un compte qui a été ajouté au groupe de sécurité LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="f4866-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>

![Écran de connexion du portail d’administration Lync Room System](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="f4866-173">Page Résumé du portail Web d’administration de SRS</span><span class="sxs-lookup"><span data-stu-id="f4866-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="f4866-174">La page de résumé fournit les informations suivantes pour toutes les salles SRS déployées sur le serveur :</span><span class="sxs-lookup"><span data-stu-id="f4866-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>

- <span data-ttu-id="f4866-175">**Balise** Nom personnalisé que l’administrateur fournit à la salle.</span><span class="sxs-lookup"><span data-stu-id="f4866-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="f4866-176">La balise peut être définie dans le portail en cliquant sur le nom de la salle.</span><span class="sxs-lookup"><span data-stu-id="f4866-176">The Tag can be set in the portal by clicking on the room name.</span></span>

- <span data-ttu-id="f4866-177">**Intégrité** L’état d’intégrité de la salle, qui est dérivé de l’état d’intégrité agrégé de la salle, qui est affiché sous la section intégrité de la page Paramètres de la salle.</span><span class="sxs-lookup"><span data-stu-id="f4866-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

- <span data-ttu-id="f4866-178">**Réunion suivante** Date et heure de la prochaine réunion planifiée.</span><span class="sxs-lookup"><span data-stu-id="f4866-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>

- <span data-ttu-id="f4866-179">**Version SRS, fabricant, modèle** Ces valeurs sont prédéfinies dans SRS.</span><span class="sxs-lookup"><span data-stu-id="f4866-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="f4866-180">En fonction du fabricant, ces champs peuvent rester vides.</span><span class="sxs-lookup"><span data-stu-id="f4866-180">Depending on the manufacturer, these fields might be left blank.</span></span>

- <span data-ttu-id="f4866-181">**Dernière actualisation** Affiche la date de la dernière actualisation de la page Web.</span><span class="sxs-lookup"><span data-stu-id="f4866-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>

![Affichage de synthèse du portail d’administration de Lync Room System](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> <span data-ttu-id="f4866-183">Vous ne verrez le menu de gestion en bloc que si vous êtes membre du groupe de sécurité LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="f4866-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span>

### <a name="srs-room-information"></a><span data-ttu-id="f4866-184">Informations sur la salle SRS</span><span class="sxs-lookup"><span data-stu-id="f4866-184">SRS Room Information</span></span>

<span data-ttu-id="f4866-185">La section informations sur la salle du portail vous permet d’afficher et de configurer des salles SRS individuelles.</span><span class="sxs-lookup"><span data-stu-id="f4866-185">The Room Info section of the portal allows you to view and configure individual SRS rooms.</span></span> <span data-ttu-id="f4866-186">Il contient quatre sections : paramètres, détails, journalisation et intégrité.</span><span class="sxs-lookup"><span data-stu-id="f4866-186">It contains four sections: Settings, Details, Logging, and Health.</span></span>

#### <a name="settings"></a><span data-ttu-id="f4866-187">Paramètres</span><span class="sxs-lookup"><span data-stu-id="f4866-187">Settings</span></span>

<span data-ttu-id="f4866-188">Dans la section paramètres, vous pouvez définir le mot de passe, la balise Room et les niveaux de volume par défaut pour la salle.</span><span class="sxs-lookup"><span data-stu-id="f4866-188">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="f4866-189">Si vous configurez ces paramètres, les modifications ne sont répliquées qu’une fois que vous avez redémarré la console SRS.</span><span class="sxs-lookup"><span data-stu-id="f4866-189">If you configure these settings, the changes are replicated only after you restart the SRS console.</span></span> <span data-ttu-id="f4866-190">Vous verrez uniquement les paramètres de mise à jour du système pour les appareils SRS utilisant la version 15,12 et les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="f4866-190">You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>

![Paramètres de la salle du portail d’administration Lync Room System](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a><span data-ttu-id="f4866-192">Détails</span><span class="sxs-lookup"><span data-stu-id="f4866-192">Details</span></span>

<span data-ttu-id="f4866-193">La section Détails fournit une synthèse en lecture seule des paramètres de la salle des SRS, notamment : l’heure de la dernière actualisation ; réunion suivante ; dernières mises à jour, maintenance et étalonnage ; paramètres de haut-parleur, micro et sonnerie par défaut ; version9.0.2 URI SIP ; nombre d’écrans et détails sur chaque écran ; État et activité.</span><span class="sxs-lookup"><span data-stu-id="f4866-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

![Affichage détaillé du portail d’administration de Lync Room System](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a><span data-ttu-id="f4866-195">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="f4866-195">Troubleshooting</span></span>

<span data-ttu-id="f4866-196">La section Troubleshooting peut être utilisée pour collecter des journaux à distance et les enregistrer à un emplacement spécifié.</span><span class="sxs-lookup"><span data-stu-id="f4866-196">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="f4866-197">Vous pouvez également redémarrer la console SRS (interface utilisateur SRS) ou redémarrer l’ensemble du système.</span><span class="sxs-lookup"><span data-stu-id="f4866-197">You can also restart the SRS console (SRS user interface) or restart the entire system.</span></span> <span data-ttu-id="f4866-198">Pour collecter les journaux, fournissez un chemin d’accès au dossier au format spécifié et assurez-vous que le dossier dispose des autorisations d’écriture accordées au compte de l’ordinateur SRS.</span><span class="sxs-lookup"><span data-stu-id="f4866-198">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account.</span></span> <span data-ttu-id="f4866-199">Si la taille du journal est trop importante, la collecte des journaux peut prendre jusqu’à 5 minutes.</span><span class="sxs-lookup"><span data-stu-id="f4866-199">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="f4866-200">L’actualisation de la page vous donnera le dernier État.</span><span class="sxs-lookup"><span data-stu-id="f4866-200">Refreshing the page will give you the latest status.</span></span>

#### <a name="health"></a><span data-ttu-id="f4866-201">Intégrité</span><span class="sxs-lookup"><span data-stu-id="f4866-201">Health</span></span>

<span data-ttu-id="f4866-202">La section Health fournit une indication visuelle de l’intégrité de la connexion Skype entreprise Server, du périphérique audio, du périphérique vidéo, de l’état de résistance et de l’écran.</span><span class="sxs-lookup"><span data-stu-id="f4866-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>

![Intégrité de la salle du portail d’administration Lync Room System](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="f4866-204">Remarques supplémentaires sur le portail Web d’administration</span><span class="sxs-lookup"><span data-stu-id="f4866-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="f4866-205">Les modifications de paramètres ne sont appliquées qu’après le redémarrage du système SRS. > si le mot de passe du compte LRSApp expire, vous ne pourrez pas voir l’état des salles.</span><span class="sxs-lookup"><span data-stu-id="f4866-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="f4866-206">Configurez le mot de passe du compte LRSAppuser de sorte qu’il n’expire jamais ou veillez à mettre à jour le mot de passe lorsqu’il est proche de l’expiration. > le portail Web d’administration de SRS est pris en charge uniquement pour les déploiements locaux.</span><span class="sxs-lookup"><span data-stu-id="f4866-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>

### <a name="bulk-management"></a><span data-ttu-id="f4866-207">Gestion en bloc</span><span class="sxs-lookup"><span data-stu-id="f4866-207">Bulk management</span></span>

<span data-ttu-id="f4866-208">La gestion en bloc des salles SRS est une fonctionnalité conçue pour les administrateurs informatiques avancés, pour simplifier leur flux de travail et leur permettre d’utiliser un outil pratique permettant de gérer à distance plusieurs salles de manière globale.</span><span class="sxs-lookup"><span data-stu-id="f4866-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>

<span data-ttu-id="f4866-209">Pour afficher cette fonctionnalité, l’utilisateur doit être approvisionné en tant que membre du groupe de sécurité spécial **LRSPowerUserAdminsGroup**.</span><span class="sxs-lookup"><span data-stu-id="f4866-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span>

<span data-ttu-id="f4866-210">Il n’y a pas de limite au nombre de salles SRS que vous pouvez sélectionner pour la gestion en bloc.</span><span class="sxs-lookup"><span data-stu-id="f4866-210">There is no limit to the number of SRS rooms you can select for bulk management.</span></span> <span data-ttu-id="f4866-211">Toutefois, vous ne pouvez effectuer qu’une seule opération de gestion en bloc à la fois.</span><span class="sxs-lookup"><span data-stu-id="f4866-211">However, you can perform only one bulk management operation at a time.</span></span>

<span data-ttu-id="f4866-212">Pour effectuer une opération de gestion en bloc, sélectionnez les salles à surveiller, puis cliquez sur le menu gestion en bloc.</span><span class="sxs-lookup"><span data-stu-id="f4866-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span>

### <a name="frequently-asked-questions"></a><span data-ttu-id="f4866-213">Questions fréquemment posées</span><span class="sxs-lookup"><span data-stu-id="f4866-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="f4866-214">Pourquoi ne puis-je pas me connecter au portail Web d’administration ?</span><span class="sxs-lookup"><span data-stu-id="f4866-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="f4866-215">Lorsque vous ouvrez https://localhost/lrs , vous pouvez voir la page de connexion, mais lorsque vous tapez vos informations d’identification, vous ne pouvez pas vous connecter.</span><span class="sxs-lookup"><span data-stu-id="f4866-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="f4866-216">Dans ce cas, vous devez ouvrir https://FQDNofFEserver/SRS la session pour vous connecter au portail Web d’administration.</span><span class="sxs-lookup"><span data-stu-id="f4866-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="f4866-217">Pourquoi ne puis-je pas voir SRS v1 dans le portail Web d’administration ?</span><span class="sxs-lookup"><span data-stu-id="f4866-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="f4866-218">Assurez-vous que vous avez des comptes SRS dans votre déploiement et qu’ils sont créés conformément aux recommandations de déploiement du portail Web d’administration de SRS.</span><span class="sxs-lookup"><span data-stu-id="f4866-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="f4866-219">Assurez-vous que les comptes SRS sont configurés à l’aide de Enable-CsMeetingRoom, et non pas Enable-CsUser, sur le serveur Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="f4866-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>

- <span data-ttu-id="f4866-220">Si vous avez créé des comptes SRS et que vous ne voyez pas les comptes dans le portail Web d’administration, collectez les journaux du serveur à l’aide de l’outil de journalisation Skype entreprise Server avec le composant **MeetingPortal** sélectionné, puis envoyez-les à votre contact de support SRS.</span><span class="sxs-lookup"><span data-stu-id="f4866-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>

- <span data-ttu-id="f4866-221">Si vous avez créé des comptes SRS et que vous ne parvenez pas à voir les comptes dans le portail Web d’administration, collectez les journaux client à l’aide de Fiddler et copiez également le journal de console à partir des outils de développement de navigateur, puis envoyez-les à votre contact de support SRS.</span><span class="sxs-lookup"><span data-stu-id="f4866-221">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact.</span></span> <span data-ttu-id="f4866-222">Vous pouvez également modifier la valeur de niveau de suivi dans le fichier Web. config pour obtenir un journal plus détaillé.</span><span class="sxs-lookup"><span data-stu-id="f4866-222">You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>

  ```xml
  <system.diagnostics>
    <switches>
      <!--
      This switch controls logging message levels. 0 implies
      logging is turned off. 1 implies only errors are logged,
      2 implies errors &amp; warnings. 4 is the most detailed.
      -->
      <add name="TraceLevelSwitch" value="3" />
    </switches>
  </system.diagnostics>
  ```

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="f4866-223">Pourquoi ne puis-je pas voir l’état de SRS dans le portail Web d’administration ?</span><span class="sxs-lookup"><span data-stu-id="f4866-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="f4866-224">Assurez-vous que le compte d’utilisateur LRSApp est compatible SIP.</span><span class="sxs-lookup"><span data-stu-id="f4866-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>

- <span data-ttu-id="f4866-225">Si vous rencontrez encore des problèmes, récupérez le fichier **trace. log** dans le système SRS à partir de D:\Tracing\LRSAdminLogs, \, puis envoyez-le à votre contact de support SRS.</span><span class="sxs-lookup"><span data-stu-id="f4866-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="f4866-226">Pourquoi ne puis-je pas voir les menus de gestion en bloc pour SRS dans le portail Web d’administration ?</span><span class="sxs-lookup"><span data-stu-id="f4866-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="f4866-227">Assurez-vous que le compte d’utilisateur LRSApp est compatible SIP et qu’il fait partie du groupe de sécurité LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="f4866-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span>

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a><span data-ttu-id="f4866-228">Le portail Web d’administration de SRS v1 fonctionne-t-il avec les salles Microsoft teams ?</span><span class="sxs-lookup"><span data-stu-id="f4866-228">Does the SRS v1 administrative web portal work with Microsoft Teams Rooms?</span></span>

<span data-ttu-id="f4866-229">Non.</span><span class="sxs-lookup"><span data-stu-id="f4866-229">No.</span></span>



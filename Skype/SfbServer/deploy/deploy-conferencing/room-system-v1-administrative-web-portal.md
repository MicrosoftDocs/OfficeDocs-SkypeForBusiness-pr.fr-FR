---
title: Déployer le portail Web d’administration de SRS v1 dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Skype Entreprise Server Skype Room Systems v1 (SRS v1, anciennement appelé Lync Room System) Portail Web d’administration est un portail web que les organisations peuvent utiliser pour gérer leurs salles de conférence Skype Room Systems. Les administrateurs peuvent utiliser le portail Web d’administration de SRS v1 pour surveiller l’état de l’appareil, par exemple en surveillant les périphériques audio/vidéo. Grâce à ce portail, les administrateurs peuvent collecter à distance des informations de diagnostic pour surveiller l’état de la salle de conférence.
ms.openlocfilehash: 7d7bef99149d09ebf72c9b633370f262e535b23f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804534"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a><span data-ttu-id="40e8e-105">Déployer le portail Web d’administration de SRS v1 dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="40e8e-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>

<span data-ttu-id="40e8e-106">Skype Entreprise Server Skype Room Systems v1 (SRS v1, anciennement appelé Lync Room System) Portail Web d’administration est un portail web que les organisations peuvent utiliser pour gérer leurs salles de conférence Skype Room Systems.</span><span class="sxs-lookup"><span data-stu-id="40e8e-106">The Skype for Business Server Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="40e8e-107">Les administrateurs peuvent utiliser le portail Web d’administration de SRS v1 pour surveiller l’état de l’appareil, par exemple en surveillant les périphériques audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="40e8e-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="40e8e-108">Grâce à ce portail, les administrateurs peuvent collecter à distance des informations de diagnostic pour surveiller l’état de la salle de conférence.</span><span class="sxs-lookup"><span data-stu-id="40e8e-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="40e8e-109">Pour utiliser cette fonctionnalité, le portail Web d’administration de SRS v1 doit être déployé sur chaque serveur frontal Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="40e8e-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="40e8e-110">Ce guide fournit des instructions aux administrateurs sur l’installation et la configuration du portail Web d’administration SRS.</span><span class="sxs-lookup"><span data-stu-id="40e8e-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="40e8e-111">Il est destiné aux administrateurs qui connaissent l’administration de Skype Entreprise Server et qui ont des droits d’utilisateur d’administrateur pour modifier la topologie Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="40e8e-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>

<span data-ttu-id="40e8e-112">Une fois le portail Web d’administration SRS v1 déployé sur le serveur, les administrateurs peuvent vérifier l’état des appareils SRS v1 en se connectant au site à partir de leurs ordinateurs ou ordinateurs portables.</span><span class="sxs-lookup"><span data-stu-id="40e8e-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40e8e-113">Téléchargez le portail Web d’administration de [Microsoft Skype Room Systems v1 pour Skype Entreprise Server 2015.](https://www.microsoft.com/download/details.aspx?id=46906)</span><span class="sxs-lookup"><span data-stu-id="40e8e-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="40e8e-114">Dans cet article :</span><span class="sxs-lookup"><span data-stu-id="40e8e-114">In this topic:</span></span>

- [<span data-ttu-id="40e8e-115">Configurer votre environnement pour le portail Web d’administration de SRS v1</span><span class="sxs-lookup"><span data-stu-id="40e8e-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)

- [<span data-ttu-id="40e8e-116">Installer le portail Web d’administration de SRS v1</span><span class="sxs-lookup"><span data-stu-id="40e8e-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)

- [<span data-ttu-id="40e8e-117">Utiliser le portail Web d’administration SRS</span><span class="sxs-lookup"><span data-stu-id="40e8e-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="40e8e-118">Configurer votre environnement pour le portail Web d’administration de SRS v1</span><span class="sxs-lookup"><span data-stu-id="40e8e-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="40e8e-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="40e8e-119"><a name="Config_Env"> </a></span></span>

<span data-ttu-id="40e8e-120">Pour utiliser le portail Web d’administration de SRS v1, vous devez installer ou configurer les conditions préalables suivantes.</span><span class="sxs-lookup"><span data-stu-id="40e8e-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40e8e-121">Si le serveur est configuré avec l’authentification Kerberos et NTLM, et que SRS est en cours d’exécution sur un ordinateur qui n’est pas joint au domaine, l’authentification Kerberos échoue et l’utilisateur ne voit pas l’état de SRS dans le portail d’administration.</span><span class="sxs-lookup"><span data-stu-id="40e8e-121">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal.</span></span> <span data-ttu-id="40e8e-122">Pour résoudre ce problème, configurez le serveur avec l’authentification NTLM ou les authentifications NTLM et TLS-DSK (sans Kerberos), ou associez l’ordinateur SRS au domaine.</span><span class="sxs-lookup"><span data-stu-id="40e8e-122">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span>

1. <span data-ttu-id="40e8e-123">Installez les mises à jour cumulatives de Skype Entreprise Server dans la topologie Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="40e8e-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span>

    <span data-ttu-id="40e8e-124">To get the update or see what’s included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="40e8e-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

2. <span data-ttu-id="40e8e-125">Créez un utilisateur Active Directory activé pour SIP.</span><span class="sxs-lookup"><span data-stu-id="40e8e-125">Create a SIP-enabled Active Directory user.</span></span>

    <span data-ttu-id="40e8e-126">Le portail Web d’administration de SRS v1 utilise ces informations d’identification pour interroger des informations à partir de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="40e8e-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="40e8e-127">Le nom d’utilisateur dans les exemples donnés est LRSApp.</span><span class="sxs-lookup"><span data-stu-id="40e8e-127">The username in the examples given is LRSApp.</span></span>

3. <span data-ttu-id="40e8e-128">Créez un groupe de sécurité Active Directory nommé LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="40e8e-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>

    <span data-ttu-id="40e8e-129">Créez le groupe avec l’étendue de groupe comme global et type de groupe en tant que sécurité.</span><span class="sxs-lookup"><span data-stu-id="40e8e-129">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="40e8e-130">Les utilisateurs activés pour SIP qui sont ajoutés à ce groupe sont autorisés à voir la liste des salles et à exécuter certaines commandes, telles que la collecte de journaux.</span><span class="sxs-lookup"><span data-stu-id="40e8e-130">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4. <span data-ttu-id="40e8e-131">Créez un groupe de sécurité Active Directory nommé LRSFullAccessAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="40e8e-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>

    <span data-ttu-id="40e8e-132">Créez le groupe avec une étendue de groupe globale et un type de groupe en tant qu’utilisateurs activés security.SIP qui sont ajoutés à ce groupe sont autorisés à utiliser toutes les fonctionnalités du portail d’administration sur une seule salle Skype.</span><span class="sxs-lookup"><span data-stu-id="40e8e-132">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room.</span></span> <span data-ttu-id="40e8e-133">Pour inclure la prise en charge de la gestion en bloc des salles Skype, reportez-vous à l’étape 5.</span><span class="sxs-lookup"><span data-stu-id="40e8e-133">To include support for bulk management of Skype rooms, refer to step 5.</span></span>

     ![Liste des groupes d’administration avec rôle de groupe de sécurité](../../media/LRS_LRSFullAccessAdminGroup.png)

5. <span data-ttu-id="40e8e-135">Créez un groupe de sécurité Active Directory nommé LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="40e8e-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span>

    <span data-ttu-id="40e8e-136">Créez le groupe avec l’étendue de groupe comme global et type de groupe en tant que sécurité.</span><span class="sxs-lookup"><span data-stu-id="40e8e-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="40e8e-137">Les utilisateurs activés pour SIP qui sont ajoutés à ce groupe sont autorisés à utiliser toutes les fonctionnalités du portail d’administration, y compris la gestion en bloc des salles Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="40e8e-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span>

6. <span data-ttu-id="40e8e-138">Ajoutez LRSFullAccessAdminGroup en tant que membre de LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="40e8e-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>

     ![Page Membres des propriétés LRSSupportAdminGroup](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. <span data-ttu-id="40e8e-140">Créez un utilisateur Active Directory activé pour SIP avec le nom LRSSupport.</span><span class="sxs-lookup"><span data-stu-id="40e8e-140">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="40e8e-141">Ajoutez cet utilisateur à LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="40e8e-141">Add this user to LRSSupportAdminGroup.</span></span>

     ![Page Membres des propriétés LRSSupportAdminGroup](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. <span data-ttu-id="40e8e-143">Installez [ASP.NET MVC 4 pour Visual Studio 2010 SP1 et Visual Web Developer 2010 SP1.](https://go.microsoft.com/fwlink/p/?LinkId=323967)</span><span class="sxs-lookup"><span data-stu-id="40e8e-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>

## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="40e8e-144">Installer le portail Web d’administration de SRS v1</span><span class="sxs-lookup"><span data-stu-id="40e8e-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="40e8e-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="40e8e-145"><a name="Install_SRS"> </a></span></span>

<span data-ttu-id="40e8e-146">Téléchargez le portail Web d’administration de [Microsoft Skype Room Systems v1 pour Skype Entreprise Server 2015.](https://www.microsoft.com/download/details.aspx?id=46906)</span><span class="sxs-lookup"><span data-stu-id="40e8e-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="40e8e-147">Pour installer le portail Web d’administration de SRS v1, utilisez les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="40e8e-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>

1. <span data-ttu-id="40e8e-148">Configurez le port d’application approuvé en exécutant l’cmdlet suivante dans Skype Entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="40e8e-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="40e8e-149">Pour installer le portail de salle de réunion, **téléchargezMeetingRoomPortalInstaller.msi** puis exécutez-le en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="40e8e-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>

3. <span data-ttu-id="40e8e-150">Ouvrez le Web.config à partir de l’emplacement suivant :</span><span class="sxs-lookup"><span data-stu-id="40e8e-150">Open the Web.config file from the following location:</span></span>

    <span data-ttu-id="40e8e-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span><span class="sxs-lookup"><span data-stu-id="40e8e-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span></span>\

4. <span data-ttu-id="40e8e-152">Dans le fichier Web.Config, modifiez PortalUserName en nom d’utilisateur créé à l’étape 2 sous la section « Configurer votre environnement pour le portail web d’administration[de SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)» (le nom recommandé à l’étape est LRSApp) :</span><span class="sxs-lookup"><span data-stu-id="40e8e-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span>

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="40e8e-153">Étant donné que le portail d’administration SRS v1 est une application fiable, vous n’avez pas besoin de fournir le mot de passe dans la configuration du portail.</span><span class="sxs-lookup"><span data-stu-id="40e8e-153">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="40e8e-154">Si cet utilisateur utilise un bureau d’enregistrement différent du bureau d’enregistrement local, vous devez le spécifier en ajoutant la ligne suivante dans Web.Config fichier :</span><span class="sxs-lookup"><span data-stu-id="40e8e-154">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="40e8e-155">Si le port utilisé est autre que 5061, ajoutez la ligne suivante dans Web.Config fichier :</span><span class="sxs-lookup"><span data-stu-id="40e8e-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="40e8e-156">Vérifier l’installation du portail Web d’administration SRS</span><span class="sxs-lookup"><span data-stu-id="40e8e-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="40e8e-157">Pour vérifier l’installation du portail Web d’administration de SRS v1, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="40e8e-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>

1. <span data-ttu-id="40e8e-158">Sur un serveur frontal, accédez à l’URL suivante :</span><span class="sxs-lookup"><span data-stu-id="40e8e-158">On a Front End server, browse to the following URL:</span></span>

    <span data-ttu-id="40e8e-159">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="40e8e-159">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="40e8e-160">Vous ne devriez voir aucune erreur, comme illustré dans l’image suivante :</span><span class="sxs-lookup"><span data-stu-id="40e8e-160">You should not see any errors, as shown in the following image:</span></span>

     ![Écran de signature du portail d’administration Lync Room System](../../media/LRS_AdminPortalSignIn.png)

2. <span data-ttu-id="40e8e-162">Si vous ne voyez aucune erreur, essayez d’accéder à l’URL suivante à partir d’un autre ordinateur de la topologie :</span><span class="sxs-lookup"><span data-stu-id="40e8e-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>

    <span data-ttu-id="40e8e-163">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="40e8e-163">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="40e8e-164">Pour accéder à la page, vous devez ajouter les enregistrements DNS comme décrit dans «[Enregistrements DNS](https://go.microsoft.com/fwlink/p/?LinkId=318056)requis pour la signature automatique du client ».</span><span class="sxs-lookup"><span data-stu-id="40e8e-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](https://go.microsoft.com/fwlink/p/?LinkId=318056)."</span></span>

## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="40e8e-165">Utiliser le portail Web d’administration SRS</span><span class="sxs-lookup"><span data-stu-id="40e8e-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="40e8e-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="40e8e-166"><a name="Use_Portal"> </a></span></span>

<span data-ttu-id="40e8e-167">Après avoir déployé SRS sur le serveur, vous pouvez vérifier l’état de toutes les salles SRS en vous inscrivant dans le portail Web d’administration de SRS v1 à partir d’un navigateur.</span><span class="sxs-lookup"><span data-stu-id="40e8e-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>

### <a name="sign-in"></a><span data-ttu-id="40e8e-168">Se connecter</span><span class="sxs-lookup"><span data-stu-id="40e8e-168">Sign in</span></span>

1. <span data-ttu-id="40e8e-169">Accédez à l’URL suivante :</span><span class="sxs-lookup"><span data-stu-id="40e8e-169">Browse to the following URL:</span></span>

    <span data-ttu-id="40e8e-170">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="40e8e-170">https://\<fe-server\>/lrs</span></span>

2. <span data-ttu-id="40e8e-171">Entrez les informations d’identification du compte LRSSupport ou d’un compte qui a été ajouté au groupe de sécurité LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="40e8e-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>

![Écran de signature du portail d’administration Lync Room System](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="40e8e-173">Page récapitulatif du portail Web d’administration SRS</span><span class="sxs-lookup"><span data-stu-id="40e8e-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="40e8e-174">La page récapitulatif fournit les informations suivantes pour toutes les salles SRS déployées sur le serveur :</span><span class="sxs-lookup"><span data-stu-id="40e8e-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>

- <span data-ttu-id="40e8e-175">**Balise** Nom personnalisé que l’administrateur donne à la salle.</span><span class="sxs-lookup"><span data-stu-id="40e8e-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="40e8e-176">La balise peut être définie dans le portail en cliquant sur le nom de la salle.</span><span class="sxs-lookup"><span data-stu-id="40e8e-176">The Tag can be set in the portal by clicking on the room name.</span></span>

- <span data-ttu-id="40e8e-177">**Santé** L’état d’état de la salle, qui est dérivé de l’état d’agrégation de la salle, qui est affiché sous la section Santé de la page Paramètres de la salle.</span><span class="sxs-lookup"><span data-stu-id="40e8e-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

- <span data-ttu-id="40e8e-178">**Réunion suivante** Date et heure de la prochaine réunion.</span><span class="sxs-lookup"><span data-stu-id="40e8e-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>

- <span data-ttu-id="40e8e-179">**Version, fabricant, modèle SRS** Ces valeurs sont prédéfines dans SRS.</span><span class="sxs-lookup"><span data-stu-id="40e8e-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="40e8e-180">Selon le fabricant, ces champs peuvent être laissés vides.</span><span class="sxs-lookup"><span data-stu-id="40e8e-180">Depending on the manufacturer, these fields might be left blank.</span></span>

- <span data-ttu-id="40e8e-181">**Dernière actualisation** Affiche la dernière fois que la page web a été actualisée.</span><span class="sxs-lookup"><span data-stu-id="40e8e-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>

![Vue récapitulatif du portail d’administration Lync Room System](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> <span data-ttu-id="40e8e-183">Vous ne verrez le menu Gestion en bloc que si vous faites partie du groupe de sécurité LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="40e8e-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span>

### <a name="srs-room-information"></a><span data-ttu-id="40e8e-184">Informations sur la salle SRS</span><span class="sxs-lookup"><span data-stu-id="40e8e-184">SRS Room Information</span></span>

<span data-ttu-id="40e8e-185">La section Informations sur la salle du portail vous permet d’afficher et de configurer des salles SRS individuelles.</span><span class="sxs-lookup"><span data-stu-id="40e8e-185">The Room Info section of the portal allows you to view and configure individual SRS rooms.</span></span> <span data-ttu-id="40e8e-186">Il contient quatre sections : Paramètres, Détails, Journalisation et Santé.</span><span class="sxs-lookup"><span data-stu-id="40e8e-186">It contains four sections: Settings, Details, Logging, and Health.</span></span>

#### <a name="settings"></a><span data-ttu-id="40e8e-187">Paramètres</span><span class="sxs-lookup"><span data-stu-id="40e8e-187">Settings</span></span>

<span data-ttu-id="40e8e-188">Dans la section Paramètres, vous pouvez définir le mot de passe, la balise de salle et les niveaux de volume par défaut de la salle.</span><span class="sxs-lookup"><span data-stu-id="40e8e-188">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="40e8e-189">Si vous configurez ces paramètres, les modifications sont répliquées uniquement après le redémarrage de la console SRS.</span><span class="sxs-lookup"><span data-stu-id="40e8e-189">If you configure these settings, the changes are replicated only after you restart the SRS console.</span></span> <span data-ttu-id="40e8e-190">Vous ne verrez que les paramètres des mises à jour système pour les appareils SRS utilisant la version 15.12 et ultérieures.</span><span class="sxs-lookup"><span data-stu-id="40e8e-190">You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>

![Paramètres de salle du portail d’administration Lync Room System](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a><span data-ttu-id="40e8e-192">Détails</span><span class="sxs-lookup"><span data-stu-id="40e8e-192">Details</span></span>

<span data-ttu-id="40e8e-193">La section Détails fournit un résumé en lecture seule des paramètres de la salle SRS, y compris : l’heure de la dernière actualisation ; réunion suivante ; dernières mises à jour, maintenance et étalonnage ; paramètres de haut-parleur, de micro et de sonnerie par défaut ; version; URI SIP ; nombre d’écrans et de détails sur chaque écran ; statut et activité.</span><span class="sxs-lookup"><span data-stu-id="40e8e-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

![Affichage détaillé du portail d’administration Lync Room System](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a><span data-ttu-id="40e8e-195">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="40e8e-195">Troubleshooting</span></span>

<span data-ttu-id="40e8e-196">La section Dépannage peut être utilisée pour collecter à distance les journaux et les enregistrer à un emplacement spécifié.</span><span class="sxs-lookup"><span data-stu-id="40e8e-196">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="40e8e-197">Vous pouvez également redémarrer la console SRS (interface utilisateur SRS) ou redémarrer l’ensemble du système.</span><span class="sxs-lookup"><span data-stu-id="40e8e-197">You can also restart the SRS console (SRS user interface) or restart the entire system.</span></span> <span data-ttu-id="40e8e-198">Pour collecter des journaux, fournissez un chemin d’accès au dossier au format spécifié et assurez-vous que le dossier dispose des autorisations d’écriture accordées au compte d’ordinateur SRS.</span><span class="sxs-lookup"><span data-stu-id="40e8e-198">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account.</span></span> <span data-ttu-id="40e8e-199">Si la taille du journal est trop importante, la collecte des journaux peut prendre jusqu’à 5 minutes.</span><span class="sxs-lookup"><span data-stu-id="40e8e-199">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="40e8e-200">L’actualisation de la page vous donne l’état le plus récent.</span><span class="sxs-lookup"><span data-stu-id="40e8e-200">Refreshing the page will give you the latest status.</span></span>

#### <a name="health"></a><span data-ttu-id="40e8e-201">Intégrité</span><span class="sxs-lookup"><span data-stu-id="40e8e-201">Health</span></span>

<span data-ttu-id="40e8e-202">La section Santé fournit une indication visuelle de l’état de la connexion Skype Entreprise Server, de l’appareil audio, du périphérique vidéo, de l’état de résilience et de l’écran.</span><span class="sxs-lookup"><span data-stu-id="40e8e-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>

![Lync Room System Admin Portal Room Health](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="40e8e-204">Notes supplémentaires sur le portail Web d’administration</span><span class="sxs-lookup"><span data-stu-id="40e8e-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="40e8e-205">Les modifications de paramètre sont appliquées uniquement après le redémarrage du système SRS.> Si le mot de passe du compte LRSApp expire, vous ne pourrez pas voir l’état des salles.</span><span class="sxs-lookup"><span data-stu-id="40e8e-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="40e8e-206">Configurez le mot de passe du compte LRSAppuser de sorte qu’il n’expire jamais, ou assurez-vous de le mettre à jour lorsqu’il est sur le point d’expirer.> Le portail web d’administration SRS est uniquement pris en charge pour les déploiements locaux.</span><span class="sxs-lookup"><span data-stu-id="40e8e-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>

### <a name="bulk-management"></a><span data-ttu-id="40e8e-207">Gestion en bloc</span><span class="sxs-lookup"><span data-stu-id="40e8e-207">Bulk management</span></span>

<span data-ttu-id="40e8e-208">La gestion en bloc des salles SRS est une fonctionnalité conçue pour les administrateurs informatiques avancés, qui simplifie leur flux de travail et leur permet de gagner du temps et de gérer à distance plusieurs salles en bloc.</span><span class="sxs-lookup"><span data-stu-id="40e8e-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>

<span data-ttu-id="40e8e-209">Pour voir cette fonctionnalité, l’utilisateur doit être provisioné en tant que membre du groupe de sécurité **spécial, LRSPowerUserAdminsGroup**.</span><span class="sxs-lookup"><span data-stu-id="40e8e-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span>

<span data-ttu-id="40e8e-210">Il n’existe aucune limite au nombre de salles SRS que vous pouvez sélectionner pour la gestion en bloc.</span><span class="sxs-lookup"><span data-stu-id="40e8e-210">There is no limit to the number of SRS rooms you can select for bulk management.</span></span> <span data-ttu-id="40e8e-211">Toutefois, vous ne pouvez effectuer qu’une seule opération de gestion en bloc à la fois.</span><span class="sxs-lookup"><span data-stu-id="40e8e-211">However, you can perform only one bulk management operation at a time.</span></span>

<span data-ttu-id="40e8e-212">Pour effectuer une opération de gestion en bloc, sélectionnez les salles à surveiller, puis cliquez sur le menu Gestion en bloc.</span><span class="sxs-lookup"><span data-stu-id="40e8e-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span>

### <a name="frequently-asked-questions"></a><span data-ttu-id="40e8e-213">Questions fréquemment posées</span><span class="sxs-lookup"><span data-stu-id="40e8e-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="40e8e-214">Pourquoi ne puis-je pas me connecter au portail web d’administration ?</span><span class="sxs-lookup"><span data-stu-id="40e8e-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="40e8e-215">Lorsque vous ouvrez, vous pouvez voir la page de connexion, mais lorsque vous tapez vos informations d’identification, vous ne https://localhost/lrs pouvez pas vous y inscrire.</span><span class="sxs-lookup"><span data-stu-id="40e8e-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="40e8e-216">Dans ce cas, vous devez ouvrir pour https://FQDNofFEserver/SRS vous inscrire au portail web d’administration.</span><span class="sxs-lookup"><span data-stu-id="40e8e-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="40e8e-217">Pourquoi ne puis-je pas voir SRS v1 dans le portail web d’administration ?</span><span class="sxs-lookup"><span data-stu-id="40e8e-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="40e8e-218">Assurez-vous que vous avez des comptes SRS dans votre déploiement et qu’ils sont créés conformément aux recommandations de déploiement du portail Web d’administration SRS.</span><span class="sxs-lookup"><span data-stu-id="40e8e-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="40e8e-219">Assurez-vous que les comptes SRS sont provisionés à l’aide d’Enable-CsMeetingRoom, et non de Enable-CsUser, sur Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="40e8e-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>

- <span data-ttu-id="40e8e-220">Si vous avez créé des comptes SRS et que vous ne pouvez pas les voir dans le portail web d’administration, collectez les journaux du serveur à l’aide de l’outil de journalisation de Skype Entreprise Server avec le composant **MeetingPortal** sélectionné, puis envoyez-les à votre contact de support SRS.</span><span class="sxs-lookup"><span data-stu-id="40e8e-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>

- <span data-ttu-id="40e8e-221">Si vous avez créé des comptes SRS et que vous ne pouvez pas les voir dans le portail web d’administration, collectez les journaux clients à l’aide de Fiddler, copiez également le journal de la console à partir des outils de développement du navigateur, puis envoyez-les à votre contact de support SRS.</span><span class="sxs-lookup"><span data-stu-id="40e8e-221">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact.</span></span> <span data-ttu-id="40e8e-222">Vous pouvez également modifier la valeur du niveau de suivi dans le Web.config pour obtenir un journal plus détaillé.</span><span class="sxs-lookup"><span data-stu-id="40e8e-222">You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>

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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="40e8e-223">Pourquoi ne puis-je pas voir l’état de SRS dans le portail web d’administration ?</span><span class="sxs-lookup"><span data-stu-id="40e8e-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="40e8e-224">Assurez-vous que le compte d’utilisateur LRSApp est activé pour SIP.</span><span class="sxs-lookup"><span data-stu-id="40e8e-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>

- <span data-ttu-id="40e8e-225">Si vous avez encore des problèmes, collectez le fichier **Trace.log** dans le système SRS à partir de D:\Tracing\LRSAdminLogs, puis envoyez-le à votre contact de support \, SRS.</span><span class="sxs-lookup"><span data-stu-id="40e8e-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="40e8e-226">Pourquoi ne puis-je pas voir les menus de gestion en bloc pour SRS dans le portail web d’administration ?</span><span class="sxs-lookup"><span data-stu-id="40e8e-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="40e8e-227">Assurez-vous que le compte d’utilisateur LRSApp est activé pour SIP et qu’il fait partie du groupe de sécurité LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="40e8e-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span>

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a><span data-ttu-id="40e8e-228">Le portail web d’administration SRS v1 fonctionne-t-il avec les salles Microsoft Teams ?</span><span class="sxs-lookup"><span data-stu-id="40e8e-228">Does the SRS v1 administrative web portal work with Microsoft Teams Rooms?</span></span>

<span data-ttu-id="40e8e-229">Non.</span><span class="sxs-lookup"><span data-stu-id="40e8e-229">No.</span></span>



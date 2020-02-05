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
description: Le portail Web d’administration de Skype entreprise Server v1 (SRS v1, auparavant appelé système de salle Lync) est un portail Web que les organisations peuvent utiliser pour gérer leurs salles de conférence de systèmes de salle Skype. Les administrateurs peuvent utiliser le portail Web d’administration de SRS v1 pour contrôler l’état de l’appareil, par exemple en surveillant les périphériques audio/vidéo. Ils peuvent également collecter à distance des informations de diagnostic pour surveiller l’intégrité des salles de conférence.
ms.openlocfilehash: 558baac64bdb1e21ed710cb4dafb063ce75a62de
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768517"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a><span data-ttu-id="67078-105">Déploiement du portail Web d’administration de SRS v1 dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="67078-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>

<span data-ttu-id="67078-106">Le portail Web d’administration de Skype entreprise Server v1 (SRS v1, auparavant appelé système de salle Lync) est un portail Web que les organisations peuvent utiliser pour gérer leurs salles de conférence de systèmes de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="67078-106">The Skype for Business Server Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="67078-107">Les administrateurs peuvent utiliser le portail Web d’administration de SRS v1 pour contrôler l’état de l’appareil, par exemple en surveillant les périphériques audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="67078-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="67078-108">Ils peuvent également collecter à distance des informations de diagnostic pour surveiller l’intégrité des salles de conférence.</span><span class="sxs-lookup"><span data-stu-id="67078-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="67078-109">Pour utiliser cette fonctionnalité, le portail Web d’administration de SRS v1 doit être déployé sur chaque serveur frontal Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="67078-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="67078-110">Ce guide fournit des instructions aux administrateurs sur l’installation et la configuration du portail Web d’administration SRS.</span><span class="sxs-lookup"><span data-stu-id="67078-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="67078-111">Il est destiné aux administrateurs ayant connaissance de l’administration de Skype entreprise Server et disposant de droits d’administrateur pour la modification de la topologie de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="67078-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>

<span data-ttu-id="67078-112">Après le déploiement du portail Web d’administration SRS v1 sur le serveur, les administrateurs peuvent vérifier les appareils SRS v1 en se connectant au site à partir de leur ordinateur ou de leur ordinateur portable.</span><span class="sxs-lookup"><span data-stu-id="67078-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67078-113">Télécharger le [portail Web d’administration des systèmes de salle Skype Microsoft pour Skype entreprise Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span><span class="sxs-lookup"><span data-stu-id="67078-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="67078-114">Contenu de cette rubrique :</span><span class="sxs-lookup"><span data-stu-id="67078-114">In this topic:</span></span>

- [<span data-ttu-id="67078-115">Configuration de votre environnement pour le portail Web d’administration de SRS v1</span><span class="sxs-lookup"><span data-stu-id="67078-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)

- [<span data-ttu-id="67078-116">Installation du portail Web d’administration de SRS v1</span><span class="sxs-lookup"><span data-stu-id="67078-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)

- [<span data-ttu-id="67078-117">Utilisation du portail Web d’administration de SRS</span><span class="sxs-lookup"><span data-stu-id="67078-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="67078-118">Configuration de votre environnement pour le portail Web d’administration de SRS v1</span><span class="sxs-lookup"><span data-stu-id="67078-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="67078-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="67078-119"><a name="Config_Env"> </a></span></span>

<span data-ttu-id="67078-120">Pour utiliser le portail Web d’administration de SRS v1, vous devez remplir les conditions préalables suivantes.</span><span class="sxs-lookup"><span data-stu-id="67078-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67078-p104">Si le serveur est configuré avec les authentifications Kerberos et NTLM, et que SRS est en cours d’exécution sur un ordinateur non associé au domaine, l’authentification Kerberos échouera et l’utilisateur ne pourra pas visualiser le statut de SRS sur le portail d’administration. Pour résoudre ce problème, configurez le serveur avec l’authentification NTLM, ou avec les authentifications NTLM et TLS-DSK (sans Kerberos), ou associez l’ordinateur SRS au domaine.</span><span class="sxs-lookup"><span data-stu-id="67078-p104">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal. To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span>

1. <span data-ttu-id="67078-123">Installez les mises à jour cumulatives de Skype entreprise Server dans la topologie de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="67078-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span>

    <span data-ttu-id="67078-124">Pour obtenir la mise à jour ou découvrir ce qu’elle contient, voir [mises à jour de Skype entreprise Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="67078-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

2. <span data-ttu-id="67078-125">Créez un utilisateur Active Directory activé pour SIP.</span><span class="sxs-lookup"><span data-stu-id="67078-125">Create a SIP-enabled Active Directory user.</span></span>

    <span data-ttu-id="67078-126">Le portail Web d’administration de SRS v1 utilise ces informations d’identification pour interroger les informations de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="67078-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="67078-127">Le nom d’utilisateur dans les exemples présentés est LRSApp.</span><span class="sxs-lookup"><span data-stu-id="67078-127">The username in the examples given is LRSApp.</span></span>

3. <span data-ttu-id="67078-128">Créez un groupe de sécurité Active Directory nommé LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="67078-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>

    <span data-ttu-id="67078-p106">Créez le groupe avec une étendue globale et le type Sécurité. Les utilisateurs activés pour SIP ajoutés à ce groupe seront autorisés à afficher la liste des pièces et à exécuter certaines commandes, telles que la collecte de journaux.</span><span class="sxs-lookup"><span data-stu-id="67078-p106">Create the group with Group Scope as Global and Group Type as Security. SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4. <span data-ttu-id="67078-131">Créez un groupe de sécurité Active Directory nommé LRSFullAccessAdminGroup. </span><span class="sxs-lookup"><span data-stu-id="67078-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>

    <span data-ttu-id="67078-p107">Créez le groupe avec une étendue globale et le type Sécurité. Les utilisateurs activés pour SIP ajoutés à ce groupe sont autorisés à utiliser toutes les fonctionnalités du portail d’administration dans une seule salle Skype. Pour inclure la prise en charge de la gestion en bloc de salles Skype, reportez-vous à l’étape 5. </span><span class="sxs-lookup"><span data-stu-id="67078-p107">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room. To include support for bulk management of Skype rooms, refer to step 5.</span></span>

     ![Liste des groupes d’administrateurs avec rôle de groupe de sécurité](../../media/LRS_LRSFullAccessAdminGroup.png)

5. <span data-ttu-id="67078-135">Créez un groupe de sécurité Active Directory nommé LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="67078-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span>

    <span data-ttu-id="67078-136">Créez le groupe avec une étendue globale et le type Sécurité.</span><span class="sxs-lookup"><span data-stu-id="67078-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="67078-137">Les utilisateurs SIP activés qui sont ajoutés à ce groupe sont autorisés à utiliser toutes les fonctionnalités du portail d’administration, y compris la gestion en bloc des salles Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="67078-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span>

6. <span data-ttu-id="67078-138">Ajoutez LRSFullAccessAdminGroup en tant que membre de LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="67078-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>

     ![Page des membres des propriétés LRSSupportAdminGroup](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. <span data-ttu-id="67078-140">Créez un utilisateur Active Directory activé pour SIP avec le nom LRSSupport.</span><span class="sxs-lookup"><span data-stu-id="67078-140">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="67078-141">Ajoutez cet utilisateur au groupe LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="67078-141">Add this user to LRSSupportAdminGroup.</span></span>

     ![Page des membres des propriétés LRSSupportAdminGroup](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. <span data-ttu-id="67078-143">Installez [ASP.NET MVC 4 pour Visual Studio 2010 SP1 et Visual Web developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span><span class="sxs-lookup"><span data-stu-id="67078-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>

## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="67078-144">Installation du portail Web d’administration de SRS v1</span><span class="sxs-lookup"><span data-stu-id="67078-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="67078-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="67078-145"><a name="Install_SRS"> </a></span></span>

<span data-ttu-id="67078-146">Télécharger le [portail Web d’administration des systèmes de salle Skype Microsoft pour Skype entreprise Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span><span class="sxs-lookup"><span data-stu-id="67078-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="67078-147">Pour installer le portail Web d’administration de SRS v1, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="67078-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>

1. <span data-ttu-id="67078-148">Configurez le port d’application fiable en exécutant l’applet de commande suivante dans Skype entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="67078-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="67078-149">Pour installer le portail d’administration de salles de réunions, téléchargez **MeetingRoomPortalInstaller.msi**, puis exécutez-le en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="67078-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>

3. <span data-ttu-id="67078-150">Ouvrez le fichier Web.config à partir de l’emplacement suivant :</span><span class="sxs-lookup"><span data-stu-id="67078-150">Open the Web.config file from the following location:</span></span>

    <span data-ttu-id="67078-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span><span class="sxs-lookup"><span data-stu-id="67078-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span></span>\

4. <span data-ttu-id="67078-152">Dans le fichier Web. config, remplacez PortalUserName par le nom d’utilisateur créé à l’étape 2 de la section «[configurer votre environnement pour le portail Web d’administration SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)» (le nom recommandé dans l’étape est LRSApp) :</span><span class="sxs-lookup"><span data-stu-id="67078-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span>

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="67078-p110">Comme le portail d’administration de SRS v1 est une application approuvée, vous n’avez pas besoin d’indiquer le mot de passe dans la configuration du portail. Si cet utilisateur utilise un autre serveur d’inscriptions que le serveur d’inscriptions local, vous devez le spécifier en ajoutant la ligne suivante dans le fichier Web.Config : </span><span class="sxs-lookup"><span data-stu-id="67078-p110">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration. If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="67078-155">Si le port utilisé n’est pas le port 5061, ajoutez la ligne suivante dans le fichier Web.Config : </span><span class="sxs-lookup"><span data-stu-id="67078-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="67078-156">Vérification du portail Web d’administration de SRS</span><span class="sxs-lookup"><span data-stu-id="67078-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="67078-157">Pour vérifier l’installation du portail Web d’administration de SRS v1, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="67078-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>

1. <span data-ttu-id="67078-158">Sur un serveur frontal, accédez à l’URL suivante :</span><span class="sxs-lookup"><span data-stu-id="67078-158">On a Front End server, browse to the following URL:</span></span>

    <span data-ttu-id="67078-159">https://\<Fe-Server\>/LRS</span><span class="sxs-lookup"><span data-stu-id="67078-159">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="67078-160">Aucune erreur ne doit s’afficher, comme dans l’image suivante :</span><span class="sxs-lookup"><span data-stu-id="67078-160">You should not see any errors, as shown in the following image:</span></span>

     ![Écran Connexion au portail d’administration Lync Room System](../../media/LRS_AdminPortalSignIn.png)

2. <span data-ttu-id="67078-162">Si aucune erreur ne s’affiche, essayez d’accéder à l’URL suivante à partir d’un autre ordinateur dans la topologie :</span><span class="sxs-lookup"><span data-stu-id="67078-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>

    <span data-ttu-id="67078-163">https://\<Fe-Server\>/LRS</span><span class="sxs-lookup"><span data-stu-id="67078-163">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="67078-164">Pour accéder à la page, vous devez ajouter les enregistrements DNS comme décrit dans la section «[enregistrements DNS requis pour la connexion automatique au client](https://go.microsoft.com/fwlink/p/?LinkId=318056)».</span><span class="sxs-lookup"><span data-stu-id="67078-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](https://go.microsoft.com/fwlink/p/?LinkId=318056)."</span></span>

## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="67078-165">Utilisation du portail Web d’administration de SRS</span><span class="sxs-lookup"><span data-stu-id="67078-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="67078-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="67078-166"><a name="Use_Portal"> </a></span></span>

<span data-ttu-id="67078-167">Une fois que vous avez déployé SRS sur le serveur, vous pouvez vérifier le statut de toutes les salles LRS en vous connectant au portail Web d’administration de SRS v1 à partir d’un navigateur.</span><span class="sxs-lookup"><span data-stu-id="67078-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>

### <a name="sign-in"></a><span data-ttu-id="67078-168">Connexion</span><span class="sxs-lookup"><span data-stu-id="67078-168">Sign in</span></span>

1. <span data-ttu-id="67078-169">Accédez à l’URL suivante :</span><span class="sxs-lookup"><span data-stu-id="67078-169">Browse to the following URL:</span></span>

    <span data-ttu-id="67078-170">https://\<Fe-Server\>/LRS</span><span class="sxs-lookup"><span data-stu-id="67078-170">https://\<fe-server\>/lrs</span></span>

2. <span data-ttu-id="67078-171">Entrez les données d’identification du compte LRSSupport ou d’un compte ajouté au groupe de sécurité LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="67078-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>

![Écran Connexion au portail d’administration Lync Room System](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="67078-173">Page Récapitulatif du portail Web d’administration de SRS</span><span class="sxs-lookup"><span data-stu-id="67078-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="67078-174">La page Récapitulatif fournit les informations ci-dessous pour toutes les salles SRS déployées sur le serveur :</span><span class="sxs-lookup"><span data-stu-id="67078-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>

- <span data-ttu-id="67078-175">**Indicateur** Nom personnalisé que l’administrateur accorde à la salle.</span><span class="sxs-lookup"><span data-stu-id="67078-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="67078-176">Le libellé peut être défini sur le portail en cliquant sur le nom de la salle.</span><span class="sxs-lookup"><span data-stu-id="67078-176">The Tag can be set in the portal by clicking on the room name.</span></span>

- <span data-ttu-id="67078-177">**État d’intégrité** État d’intégrité de la salle, qui est dérivée de l’état d’intégrité agrégé de la salle, qui s’affiche dans la section intégrité de la page Paramètres de la salle.</span><span class="sxs-lookup"><span data-stu-id="67078-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

- <span data-ttu-id="67078-178">**Réunion suivante** Date et heure de la planification de la réunion suivante.</span><span class="sxs-lookup"><span data-stu-id="67078-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>

- <span data-ttu-id="67078-179">**Version SRS, fabricant et modèle** Ces valeurs sont prédéfinies dans SRS.</span><span class="sxs-lookup"><span data-stu-id="67078-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="67078-180">Selon la marque, ces champs peuvent rester vides.</span><span class="sxs-lookup"><span data-stu-id="67078-180">Depending on the manufacturer, these fields might be left blank.</span></span>

- <span data-ttu-id="67078-181">**Dernière actualisation** Affiche la date à laquelle la page Web a été actualisée pour la dernière fois.</span><span class="sxs-lookup"><span data-stu-id="67078-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>

![Affichage de synthèse du portail d’administration Lync Room System](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> <span data-ttu-id="67078-183">Le menu gestion en bloc ne s’affichera que si vous faites partie du groupe de sécurité LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="67078-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span>

### <a name="srs-room-information"></a><span data-ttu-id="67078-184">Informations sur la salle SRS</span><span class="sxs-lookup"><span data-stu-id="67078-184">SRS Room Information</span></span>

<span data-ttu-id="67078-p113">La section Informations sur la salle du portail permet d’afficher et de configurer des salles SRS individuelles. Elle contient quatre sections : Paramètres, Détails, Journalisation et Intégrité.</span><span class="sxs-lookup"><span data-stu-id="67078-p113">The Room Info section of the portal allows you to view and configure individual SRS rooms. It contains four sections: Settings, Details, Logging, and Health.</span></span>

#### <a name="settings"></a><span data-ttu-id="67078-187">Paramètres</span><span class="sxs-lookup"><span data-stu-id="67078-187">Settings</span></span>

<span data-ttu-id="67078-p114">Dans la section Paramètres, vous pouvez définir le mot de passe, le libellé de la salle et les niveaux de volume par défaut pour la salle. Si vous configurez ces paramètres, les modifications sont répliquées uniquement après le redémarrage de la console SRS. Les paramètres des mises à jour système seront visibles uniquement pour les périphériques SRS utilisant la version 15.12 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="67078-p114">In the Settings section, you can set the password, room tag, and default volume levels for the room. If you configure these settings, the changes are replicated only after you restart the SRS console. You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>

![Paramètre de la salle du portail d’administration Lync Room System](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a><span data-ttu-id="67078-192">Détails</span><span class="sxs-lookup"><span data-stu-id="67078-192">Details</span></span>

<span data-ttu-id="67078-193">La section Détails fournit une synthèse en lecture seule des paramètres de la salle de SRS, notamment : l’heure de la dernière actualisation ; réunion suivante ; dernières mises à jour, maintenance et calibrage ; paramètres de haut-parleur, micro et sonnerie par défaut ; version9.0.2 URI SIP ; nombre d’écrans et de détails relatifs à chaque écran ; État et activité.</span><span class="sxs-lookup"><span data-stu-id="67078-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

![Affichage détaillé du portail d’administration Lync Room System](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a><span data-ttu-id="67078-195">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="67078-195">Troubleshooting</span></span>

<span data-ttu-id="67078-p115">La section Dépannage peut être utilisée pour collecter à distance les journaux et les enregistrer à un emplacement spécifié. Vous pouvez également redémarrer la console SRS (interface utilisateur SRS) ou redémarrer tout le système. Pour collecter des journaux, fournissez un chemin d’accès à un dossier au format spécifié et assurez-vous que ce dossier accorde des autorisations en écriture au compte de l’ordinateur SRS. Si la taille du journal est trop volumineuse, la collecte peut prendre jusqu’à 5 minutes. Actualisez la page pour obtenir le dernier statut.</span><span class="sxs-lookup"><span data-stu-id="67078-p115">The Troubleshooting section can be used to remotely collect logs and save them to a specified location. You can also restart the SRS console (SRS user interface) or restart the entire system. To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account. If the log size is too big, it can take up to 5 minutes to finish collecting logs. Refreshing the page will give you the latest status.</span></span>

#### <a name="health"></a><span data-ttu-id="67078-201">Intégrité</span><span class="sxs-lookup"><span data-stu-id="67078-201">Health</span></span>

<span data-ttu-id="67078-202">La section santé fournit une indication visuelle de l’état de la connexion à Skype entreprise Server, du périphérique audio, de l’appareil vidéo, de l’état de résilience et du périphérique d’écran.</span><span class="sxs-lookup"><span data-stu-id="67078-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>

![Intégrité de la salle du portail d’administration Lync Room System](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="67078-204">Remarques supplémentaires concernant le portail Web d’administration</span><span class="sxs-lookup"><span data-stu-id="67078-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="67078-205">Les modifications apportées aux paramètres ne s’appliquent qu’après le redémarrage du système SRS. > si le mot de passe du compte LRSApp expire, vous ne serez pas en mesure de voir l’état des salles.</span><span class="sxs-lookup"><span data-stu-id="67078-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="67078-206">Configurez le mot de passe du compte LRSAppuser pour qu’il n’expire jamais, ou veillez à le mettre à jour en cas d’expiration proche. > le portail Web d’administration SRS est uniquement pris en charge pour les déploiements sur site.</span><span class="sxs-lookup"><span data-stu-id="67078-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>

### <a name="bulk-management"></a><span data-ttu-id="67078-207">Gestion en bloc </span><span class="sxs-lookup"><span data-stu-id="67078-207">Bulk management</span></span>

<span data-ttu-id="67078-208">La gestion en bloc des salles SRS est une fonctionnalité conçue pour les administrateurs informatiques avancés, afin de simplifier leur flux de travail, et de leur proposer un outil rapide de gestion à distance de différentes salles en bloc.</span><span class="sxs-lookup"><span data-stu-id="67078-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>

<span data-ttu-id="67078-209">Pour afficher cette fonctionnalité, l’utilisateur doit être approvisionné en tant que membre du groupe de sécurité spécial **LRSPowerUserAdminsGroup**.  </span><span class="sxs-lookup"><span data-stu-id="67078-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span>

<span data-ttu-id="67078-p117">Le nombre de salles SRS que vous pouvez sélectionner pour la gestion en bloc est illimité. Toutefois, vous pouvez réaliser une seule opération de gestion en bloc à la fois.</span><span class="sxs-lookup"><span data-stu-id="67078-p117">There is no limit to the number of SRS rooms you can select for bulk management. However, you can perform only one bulk management operation at a time.</span></span>

<span data-ttu-id="67078-212">Pour effectuer une opération de gestion en bloc, sélectionnez les salles à surveiller et cliquez sur le menu de gestion en bloc. </span><span class="sxs-lookup"><span data-stu-id="67078-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span>

### <a name="frequently-asked-questions"></a><span data-ttu-id="67078-213">Forum aux questions</span><span class="sxs-lookup"><span data-stu-id="67078-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="67078-214">Pourquoi ne puis-je pas me connecter au portail Web d’administration ?</span><span class="sxs-lookup"><span data-stu-id="67078-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="67078-215">Lorsque vous ouvrez https://localhost/lrsla page de connexion, vous pouvez voir la page de connexion, mais si vous entrez vos informations d’identification, vous ne pourrez pas vous connecter.</span><span class="sxs-lookup"><span data-stu-id="67078-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="67078-216">Dans ce cas, vous devez ouvrir https://FQDNofFEserver/SRS pour vous connecter au portail Web d’administration.</span><span class="sxs-lookup"><span data-stu-id="67078-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="67078-217">Pourquoi ne puis-je pas voir SRS v1 dans le portail Web d’administration ?</span><span class="sxs-lookup"><span data-stu-id="67078-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="67078-218">Assurez-vous que votre déploiement comporte des comptes SRS et qu’ils ont été créés selon les recommandations de déploiement du portail Web d’administration de SRS.</span><span class="sxs-lookup"><span data-stu-id="67078-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="67078-219">Assurez-vous que les comptes SRS sont approvisionnés à l’aide de Enable-CsMeetingRoom, et non d’Enable-CsUser, sur le serveur Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="67078-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>

- <span data-ttu-id="67078-220">Si vous avez créé des comptes SRS et ne pouvez pas les afficher dans le portail Web administratif, collectez les journaux du serveur à l’aide de l’outil de journalisation de Skype entreprise Server avec le composant **MeetingPortal** sélectionné, puis envoyez-le à votre contact du support SRS.</span><span class="sxs-lookup"><span data-stu-id="67078-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>

- <span data-ttu-id="67078-p120">Si vous avez créé des comptes SRS et que vous ne les voyez pas sur le portail Web d’administration, collectez les journaux clients à l’aide de Fiddler, copiez également le journal de la console à partir des outils de développement du navigateur et envoyez-les à votre contact d’assistance pour SRS. Vous pouvez également modifier la valeur de niveau du suivi dans le fichier Web.config pour obtenir un journal plus détaillé.</span><span class="sxs-lookup"><span data-stu-id="67078-p120">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact. You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>

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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="67078-223">Pourquoi ne puis-je pas voir l’état de SRS dans le portail Web d’administration ?</span><span class="sxs-lookup"><span data-stu-id="67078-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="67078-224">Assurez-vous que le compte d’utilisateur LRSApp est activé pour SIP.</span><span class="sxs-lookup"><span data-stu-id="67078-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>

- <span data-ttu-id="67078-225">Si vous rencontrez encore des problèmes, collectez le fichier **trace. log** dans le système SRS à\, partir de D:\Tracing\LRSAdminLogs, puis envoyez-le à votre contact du support SRS.</span><span class="sxs-lookup"><span data-stu-id="67078-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="67078-226">Pourquoi ne puis-je pas voir les menus de gestion en bloc pour le service SRS dans le portail Web d’administration ?</span><span class="sxs-lookup"><span data-stu-id="67078-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="67078-227">Assurez-vous que le compte d’utilisateur LRSApp est compatible SIP et fait partie du groupe de sécurité LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="67078-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span>

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a><span data-ttu-id="67078-228">Le portail Web d’administration de SRS v1 fonctionne-t-il avec les salles de Microsoft teams ?</span><span class="sxs-lookup"><span data-stu-id="67078-228">Does the SRS v1 administrative web portal work with Microsoft Teams Rooms?</span></span>

<span data-ttu-id="67078-229">Non</span><span class="sxs-lookup"><span data-stu-id="67078-229">No.</span></span>



---
title: 'Lync Server 2013: déploiement de l’application Lync du Windows Store'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b22880b230acda74c7485010550d5576ea200c61
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a><span data-ttu-id="496fe-102">Déploiement de l’application Lync du Windows Store dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="496fe-102">Deploying Lync Windows Store app in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="496fe-103">_**Dernière modification de la rubrique:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="496fe-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="496fe-104">Pour que l’application Lync du Windows Store soit disponible pour les utilisateurs, assurez-vous que votre déploiement répond à la [Configuration requise pour l’application Lync du Windows Store pour Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="496fe-104">Before making Lync Windows Store app available to users, make sure that your deployment meets the [Lync Windows Store app requirements for Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span></span> <span data-ttu-id="496fe-105">Pour plus d’informations sur la configuration de Lync Server 2013 pour prendre en charge l’application Lync du Windows Store, consultez l’article de blog NextHop, «découverte automatique de Lync Server [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966)et l’application Lync du Windows Store».</span><span class="sxs-lookup"><span data-stu-id="496fe-105">For details about configuring Lync Server 2013 to support Lync Windows Store app, see the NextHop Blog article, "Lync Server Autodiscover and the Lync Windows Store App," at [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966).</span></span> <span data-ttu-id="496fe-106">Une fois votre environnement serveur configuré correctement, vous pouvez indiquer aux utilisateurs de télécharger l’application Lync à partir du Windows Store en effectuant une recherche sur «Lync».</span><span class="sxs-lookup"><span data-stu-id="496fe-106">After your server environment is configured correctly, you can direct users to download the Lync app from the Windows Store by searching for "Lync."</span></span>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a><span data-ttu-id="496fe-107">Activation de l’authentification multifacteur pour l’application Lync du Windows Store</span><span class="sxs-lookup"><span data-stu-id="496fe-107">Enabling Multi-Factor Authentication for Lync Windows Store app</span></span>

<span data-ttu-id="496fe-108">Mises à jour cumulatives pour Lync Server 2013: le 2013 de juin ajoute une prise en charge de l’authentification multifacteur pour les clients de l’application Lync du Windows Store.</span><span class="sxs-lookup"><span data-stu-id="496fe-108">Cumulative Updates for Lync Server 2013: June 2013 adds support for multi-factor authentication for Lync Windows Store app clients.</span></span> <span data-ttu-id="496fe-109">Outre le nom d’utilisateur et le mot de passe, vous pouvez demander des méthodes d’authentification supplémentaires, telles que des cartes à puce ou des épingles, afin d’authentifier les utilisateurs externes lorsque ces personnes se connectent à des réunions Lync.</span><span class="sxs-lookup"><span data-stu-id="496fe-109">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate external users when they sign in to Lync meetings.</span></span> <span data-ttu-id="496fe-110">Pour activer l’authentification multifacteur, vous devez déployer le serveur de fédération AD FS (Active Directory Federation Services) et activer l’authentification passive dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="496fe-110">To enable multi-factor authentication, you deploy Active Directory Federation Service (AD FS) federation server and enable passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="496fe-111">Après la configuration d’AD FS, les utilisateurs externes qui essaient de participer à des réunions Lync sont dotés d’une page Web d’authentification multifacteur AD FS contenant le nom d’utilisateur et le mot de passe, ainsi que d’autres méthodes d’authentification que vous avez configurées. .</span><span class="sxs-lookup"><span data-stu-id="496fe-111">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="496fe-112">Voici quelques points importants à prendre en compte si vous envisagez de configurer AD FS pour l’authentification multifacteur pour l’application Lync du Windows Store:</span><span class="sxs-lookup"><span data-stu-id="496fe-112">The following are important considerations if you plan to configure AD FS for multi-factor authentication for Lync Windows Store app:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="496fe-113">Lync Server 2013 avec des mises à jour cumulatives pour Lync Server 2013:2013 juin est requis au minimum.</span><span class="sxs-lookup"><span data-stu-id="496fe-113">Lync Server 2013 with Cumulative Updates for Lync Server 2013: June 2013 is required at a minimum.</span></span> <span data-ttu-id="496fe-114">Les clients de bureau Lync 2013 ne nécessitent pas de mises à jour cumulatives pour Lync Server 2013:2013 de juin, il est donc possible que l’authentification passive fonctionne car les clients Lync 2013 peuvent s’authentifier.</span><span class="sxs-lookup"><span data-stu-id="496fe-114">Lync 2013 desktop clients do not require Cumulative Updates for Lync Server 2013: June 2013, so it might appear that passive authentication is working because Lync 2013 clients are able to authenticate.</span></span> <span data-ttu-id="496fe-115">Toutefois, le processus d’authentification pour les clients de l’application Lync du Windows Store ne sera pas exécuté et aucune notification ou message d’erreur ne s’affichera.</span><span class="sxs-lookup"><span data-stu-id="496fe-115">However, the authentication process for Lync Windows Store app clients will fail to complete and no notification or error message will display.</span></span></P>
> <LI>
> <P><span data-ttu-id="496fe-116">Le serveur doit être configuré de manière à ce que l’authentification passive soit le seul type d’authentification offert.</span><span class="sxs-lookup"><span data-stu-id="496fe-116">The server must be configured so that passive authentication is the only authentication type offered.</span></span></P>
> <LI>
> <P><span data-ttu-id="496fe-117">Si vous utilisez des équilibreurs de charge matérielle, activez la persistance des cookies sur les équilibreurs de charge de sorte que toutes les requêtes du client d’application Lync du Windows Store soient gérées par le même serveur principal.</span><span class="sxs-lookup"><span data-stu-id="496fe-117">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Windows Store app client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="496fe-118">Lorsque vous établissez une relation d’approbation de la partie de confiance entre les serveurs Lync Server et AD FS, attribuez une durée de vie du jeton suffisamment longue pour couvrir la longueur maximale de vos réunions Lync.</span><span class="sxs-lookup"><span data-stu-id="496fe-118">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="496fe-119">Une durée de vie de jeton de 240 minutes est généralement suffisante.</span><span class="sxs-lookup"><span data-stu-id="496fe-119">Typically, a token life of 240 minutes is sufficient.</span></span></P></LI></UL>



</div>

<span data-ttu-id="496fe-120">**Pour configurer l’authentification multifacteur**</span><span class="sxs-lookup"><span data-stu-id="496fe-120">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="496fe-121">Installez un rôle de serveur de fédération AD FS.</span><span class="sxs-lookup"><span data-stu-id="496fe-121">Install an AD FS federation server role.</span></span> <span data-ttu-id="496fe-122">Pour plus d’informations, consultez le Guide de déploiement de services ADFS <http://go.microsoft.com/fwlink/p/?linkid=267511>(Active Directory Federation Services) 2,0 à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="496fe-122">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <http://go.microsoft.com/fwlink/p/?linkid=267511>.</span></span>

2.  <span data-ttu-id="496fe-123">Créez des certificats pour AD FS.</span><span class="sxs-lookup"><span data-stu-id="496fe-123">Create certificates for AD FS.</span></span> <span data-ttu-id="496fe-124">Pour plus d’informations, reportez-vous à la section «certificats de serveur de Fédération» de la rubrique plan pour et déployer AD FS [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)pour une utilisation avec une connexion unique à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="496fe-124">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="496fe-125">À partir de l’interface de ligne de commande Windows PowerShell, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="496fe-125">From the Windows PowerShell command-line interface, run the following command:</span></span>
    
        add-pssnapin Microsoft.Adfs.powershell

4.  <span data-ttu-id="496fe-126">Établissez un partenariat en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="496fe-126">Establish a partnership by running the following command:</span></span>
    
        Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  <span data-ttu-id="496fe-127">Définissez les règles de partie de confiance suivantes :</span><span class="sxs-lookup"><span data-stu-id="496fe-127">Set the following relying party rules:</span></span>
    
       ```
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a><span data-ttu-id="496fe-128">Problèmes connus qui peuvent empêcher la connexion</span><span class="sxs-lookup"><span data-stu-id="496fe-128">Known Issues that Can Prevent Sign-in</span></span>

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a><span data-ttu-id="496fe-129">La date et l’heure ne sont pas définies correctement sur l’appareil exécutant l’application Lync du Windows Store</span><span class="sxs-lookup"><span data-stu-id="496fe-129">The time and date are not set accurately on the device running Lync Windows Store app</span></span>

<span data-ttu-id="496fe-130">Le paramètre d’heure sur l’appareil doit être synchronisé avec le paramètre d’heure sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="496fe-130">The time setting on the device must be synchronized with the time setting on the server.</span></span> <span data-ttu-id="496fe-131">Ceci est particulièrement important pour les appareils tels que Microsoft surface, et les autres appareils exécutant Windows RT qui ne sont pas joints à un domaine.</span><span class="sxs-lookup"><span data-stu-id="496fe-131">This is particularly important for devices such as Microsoft Surface, and other devices running Windows RT that are not joined to a domain.</span></span> <span data-ttu-id="496fe-132">Pour définir l’heure sur ces appareils automatiquement à partir d’un serveur de temps, exécutez la commande suivante à partir d’une invite de commandes avec élévation de privilèges sur l’appareil:</span><span class="sxs-lookup"><span data-stu-id="496fe-132">To set the time on these devices automatically from a time server, run the following command from an elevated command prompt on the device:</span></span>

    w32tm /resync

</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a><span data-ttu-id="496fe-133">L’application Lync du Windows Store ne peut pas accéder au serveur ou aux services Lync</span><span class="sxs-lookup"><span data-stu-id="496fe-133">Lync Windows Store app cannot access the Lync server or services</span></span>

<span data-ttu-id="496fe-134">L’application Lync du Windows Store peut ne pas être en mesure d’accéder au serveur ou aux services Lync par le biais de cartes réseau (par exemple, des modems USB 4G LTE) qui ne s’inscrivent pas sous Windows 8 en tant qu’appareils physiques.</span><span class="sxs-lookup"><span data-stu-id="496fe-134">Lync Windows Store app may not be able to access the Lync server or services through network adapters, such as 4G LTE USB modems, that do not register with Windows 8 as physical devices.</span></span> <span data-ttu-id="496fe-135">L’application Lync du Windows Store peut rencontrer ce problème même lorsque les applications de bureau et les navigateurs sont en mesure d’accéder à d’autres serveurs et sites Web.</span><span class="sxs-lookup"><span data-stu-id="496fe-135">Lync Windows Store app may have this issue even when the desktop apps and browsers are able to access other servers and web sites.</span></span>

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="496fe-136">L’application Lync du Windows Store ne peut pas se connecter à l’aide de Lync Server 2010 et d’Office Communications Server 2007 R2 Edge Server</span><span class="sxs-lookup"><span data-stu-id="496fe-136">Lync Windows Store app cannot sign in with Lync Server 2010 and Office Communications Server 2007 R2 Edge Server</span></span>

<span data-ttu-id="496fe-137">Si votre topologie est composée de Lync Server 2010 avec Office Communications Server 2007 R2 Edge Server, vous devez exécuter la version mise à jour du générateur de topologie disponible dans la mise à jour cumulative pour Lync Server 2010:2013.</span><span class="sxs-lookup"><span data-stu-id="496fe-137">If your topology consists of Lync Server 2010 with Office Communications Server 2007 R2 Edge Server, you will need to run the updated version of Topology Builder available in the cumulative update for Lync Server 2010: July 2013.</span></span> <span data-ttu-id="496fe-138">Les versions antérieures du générateur de topologie ne créent pas le mappage requis pour Office Communications Server 2007 Edge Server, de sorte que les clients de l’application Lync du Windows Store ne peuvent pas se connecter.</span><span class="sxs-lookup"><span data-stu-id="496fe-138">Earlier versions of Topology Builder do not create the required mapping to Office Communications Server 2007 Edge Server, so Lync Windows Store app clients are unable to sign in.</span></span> <span data-ttu-id="496fe-139">Les étapes suivantes sont nécessaires:</span><span class="sxs-lookup"><span data-stu-id="496fe-139">The following steps are required:</span></span>

1.  <span data-ttu-id="496fe-140">Installez la mise à jour cumulative pour Lync Server 2010: juillet 2013 sur les pools 2010 Server et les directeurs Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="496fe-140">Install the cumulative update for Lync Server 2010: July 2013 on Lync Server 2010 pools and Lync Server 2010 Directors.</span></span>

2.  <span data-ttu-id="496fe-141">Mettez à jour la configuration de découverte automatique Lync pour indiquer que le point d’entrée SIP externe est l’adresse du serveur Edge en procédant comme suit:</span><span class="sxs-lookup"><span data-stu-id="496fe-141">Update the Lync AutoDiscover configuration to indicate that the external SIP entry point is the Edge server address by doing the following:</span></span>
    
    1.  <span data-ttu-id="496fe-142">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="496fe-142">Open Lync Server Management Shell.</span></span>
    
    2.  <span data-ttu-id="496fe-143">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="496fe-143">Run the following command:</span></span>
        
            Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a><span data-ttu-id="496fe-144">L’application Lync du Windows Store ne peut pas se connecter en raison d’un échec de validation de nom de certificat</span><span class="sxs-lookup"><span data-stu-id="496fe-144">Lync Windows Store App cannot sign in due to a certificate name validation failure</span></span>

<span data-ttu-id="496fe-145">Un problème de connexion peut se produire pour les utilisateurs d’Office 365 qui n’exécutent pas la dernière version de l’application Lync du Windows Store.</span><span class="sxs-lookup"><span data-stu-id="496fe-145">A sign-in issue can occur for Office 365 users who are not running the latest version of Lync Windows Store app.</span></span> <span data-ttu-id="496fe-146">Ce problème se produit généralement lors de l’utilisation de plusieurs domaines (par exemple, lorsque l’URI SIP est **usera@domainZ.com** mais que le serveur de périphérie est **SIP.domainX.com**).</span><span class="sxs-lookup"><span data-stu-id="496fe-146">This issue generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span> <span data-ttu-id="496fe-147">Pour résoudre ce problème, les utilisateurs doivent installer la dernière version de l’application Lync du Windows Store, qui nécessite également Windows 8,1.</span><span class="sxs-lookup"><span data-stu-id="496fe-147">To fix the issue, users should install the latest version of Lync Windows Store app, which also requires Windows 8.1.</span></span>

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a><span data-ttu-id="496fe-148">Utiliser les journaux de l’application Lync du Windows Store pour résoudre les problèmes</span><span class="sxs-lookup"><span data-stu-id="496fe-148">Use Lync Windows Store app logs to troubleshoot issues</span></span>

<span data-ttu-id="496fe-149">Vous pouvez utiliser les journaux générés sur l’appareil pour résoudre les problèmes.</span><span class="sxs-lookup"><span data-stu-id="496fe-149">You can use the logs generated on the device to troubleshoot issues.</span></span> <span data-ttu-id="496fe-150">Les journaux sont stockés dans le dossier suivant:</span><span class="sxs-lookup"><span data-stu-id="496fe-150">The logs are stored in the following folder:</span></span>

<span data-ttu-id="496fe-151">% LocalAppData%\\packages\\Microsoft. LyncMX\_8wekyb3d8bbwe\\LocalState\\suivi</span><span class="sxs-lookup"><span data-stu-id="496fe-151">%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing</span></span>

<span data-ttu-id="496fe-152">Avant de parvenir aux journaux d’un utilisateur, assurez-vous que la journalisation est activée, puis demandez à l’utilisateur d’enregistrer les journaux de manière à ce que toutes les informations stockées en mémoire soient également enregistrées dans les fichiers sur le disque dur.</span><span class="sxs-lookup"><span data-stu-id="496fe-152">Before you get the logs from a user, make sure that logging is turned on, and then ask the user to save the logs so that all the information stored in memory is also saved to files on the hard drive.</span></span>

<span data-ttu-id="496fe-153">**Pour activer la journalisation**</span><span class="sxs-lookup"><span data-stu-id="496fe-153">**To turn on logging**</span></span>

1.  <span data-ttu-id="496fe-154">Ouvrez l’application Lync du Windows Store sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="496fe-154">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="496fe-155">Balayez à partir du bord droit de l’écran.</span><span class="sxs-lookup"><span data-stu-id="496fe-155">Swipe from the right side of the screen.</span></span> <span data-ttu-id="496fe-156">Si vous utilisez une souris, pointez sur le coin supérieur droit de l’écran, puis déplacez le pointeur de la souris vers le bas de l’écran.</span><span class="sxs-lookup"><span data-stu-id="496fe-156">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

3.  <span data-ttu-id="496fe-157">Sélectionnez **paramètres**, cliquez sur **options**, puis configurez les **journaux de diagnostic** sur **activé**.</span><span class="sxs-lookup"><span data-stu-id="496fe-157">Select **Settings**, select **Options**, and then set **Diagnostic Logs** to **On**.</span></span>

4.  <span data-ttu-id="496fe-158">Si les **journaux** de diagnostics étaient inactifs, vous devez redémarrer Lync.</span><span class="sxs-lookup"><span data-stu-id="496fe-158">If **Diagnostic Logs** was off previously, you must restart Lync.</span></span> <span data-ttu-id="496fe-159">Pour redémarrer Lync, effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="496fe-159">To restart Lync, do one of the following:</span></span>
    
      - <span data-ttu-id="496fe-160">Redémarrez l’appareil.</span><span class="sxs-lookup"><span data-stu-id="496fe-160">Restart the device.</span></span>
    
      - <span data-ttu-id="496fe-161">Terminez la tâche Lync, puis relancez l’application.</span><span class="sxs-lookup"><span data-stu-id="496fe-161">End the Lync task and launch the app again.</span></span> <span data-ttu-id="496fe-162">Pour mettre fin à la tâche, ouvrez le gestionnaire des tâches Windows, sélectionnez **Lync**, puis appuyez sur **fin de tâche**.</span><span class="sxs-lookup"><span data-stu-id="496fe-162">To end the task, open the Windows Task Manager, select **Lync**, and then tap **End task**.</span></span> <span data-ttu-id="496fe-163">Si Lync ne figure pas dans la liste, appuyez sur **plus de détails** et recherchez Lync sous **processus en arrière-plan**.</span><span class="sxs-lookup"><span data-stu-id="496fe-163">If Lync is not listed, tap **More details** and look for Lync under **Background processes**.</span></span>

<span data-ttu-id="496fe-164">**Pour enregistrer les journaux**</span><span class="sxs-lookup"><span data-stu-id="496fe-164">**To save the logs**</span></span>

1.  <span data-ttu-id="496fe-165">Ouvrez l’application Lync du Windows Store sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="496fe-165">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="496fe-166">Essayez de vous connecter.</span><span class="sxs-lookup"><span data-stu-id="496fe-166">Try signing in.</span></span>

3.  <span data-ttu-id="496fe-167">Balayez à partir du bord droit de l’écran.</span><span class="sxs-lookup"><span data-stu-id="496fe-167">Swipe from the right side of the screen.</span></span> <span data-ttu-id="496fe-168">Si vous utilisez une souris, pointez sur le coin supérieur droit de l’écran, puis déplacez le pointeur de la souris vers le bas de l’écran.</span><span class="sxs-lookup"><span data-stu-id="496fe-168">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

4.  <span data-ttu-id="496fe-169">Sélectionnez **paramètres**, sélectionnez **à propos**de, puis **enregistrer les journaux**.</span><span class="sxs-lookup"><span data-stu-id="496fe-169">Select **Settings**, select **About**, and then select **Save logs**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


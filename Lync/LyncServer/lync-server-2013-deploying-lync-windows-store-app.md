---
title: 'Lync Server 2013 : déploiement de l’application Lync Windows Store'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aaae8df4d21e3aa766bd452c5ffd697dce30660a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507481"
---
# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a><span data-ttu-id="f96f1-102">Déploiement de l’application Lync Windows Store dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f96f1-102">Deploying Lync Windows Store app in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f96f1-103">_**Dernière modification de la rubrique :** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="f96f1-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="f96f1-104">Avant de rendre l’application Lync Windows Store accessible aux utilisateurs, assurez-vous que votre déploiement est conforme à la [Configuration requise de l’application Lync pour Windows Store pour Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f96f1-104">Before making Lync Windows Store app available to users, make sure that your deployment meets the [Lync Windows Store app requirements for Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span></span> <span data-ttu-id="f96f1-105">Pour plus d’informations sur la configuration de Lync Server 2013 afin de prendre en charge l’application Lync Windows Store, voir l’article du blog NextHop, « Lync Server Autodiscover and the Lync Windows Store App », à l’adresse [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966) .</span><span class="sxs-lookup"><span data-stu-id="f96f1-105">For details about configuring Lync Server 2013 to support Lync Windows Store app, see the NextHop Blog article, "Lync Server Autodiscover and the Lync Windows Store App," at [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966).</span></span> <span data-ttu-id="f96f1-106">Une fois que votre environnement serveur est correctement configuré, vous pouvez demander aux utilisateurs de télécharger l’application Lync à partir du Windows Store en recherchant « Lync ».</span><span class="sxs-lookup"><span data-stu-id="f96f1-106">After your server environment is configured correctly, you can direct users to download the Lync app from the Windows Store by searching for "Lync."</span></span>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a><span data-ttu-id="f96f1-107">Activation de l’authentification multifacteur pour l’application Lync Windows Store</span><span class="sxs-lookup"><span data-stu-id="f96f1-107">Enabling Multi-Factor Authentication for Lync Windows Store app</span></span>

<span data-ttu-id="f96f1-108">Mises à jour cumulatives pour Lync Server 2013 : le 2013 juin ajoute la prise en charge de l’authentification multifacteur pour les clients de l’application Windows Store de Lync.</span><span class="sxs-lookup"><span data-stu-id="f96f1-108">Cumulative Updates for Lync Server 2013: June 2013 adds support for multi-factor authentication for Lync Windows Store app clients.</span></span> <span data-ttu-id="f96f1-109">Outre le nom d’utilisateur et le mot de passe, vous pouvez exiger des méthodes d’authentification supplémentaires, telles que des cartes à puce ou des codes confidentiels, pour authentifier les utilisateurs externes lorsqu’ils se connectent à des réunions Lync.</span><span class="sxs-lookup"><span data-stu-id="f96f1-109">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate external users when they sign in to Lync meetings.</span></span> <span data-ttu-id="f96f1-110">Pour activer l’authentification multifacteur, vous devez déployer le serveur de fédération AD FS (Active Directory Federation Service) et activer l’authentification passive dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f96f1-110">To enable multi-factor authentication, you deploy Active Directory Federation Service (AD FS) federation server and enable passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="f96f1-111">Une fois les services ADFS configurés, les utilisateurs externes qui tentent de participer à des réunions Lync sont présentés avec une page Web d’authentification multifacteur AD FS qui contient le nom d’utilisateur et le mot de passe, ainsi que les autres méthodes d’authentification que vous avez configurées.</span><span class="sxs-lookup"><span data-stu-id="f96f1-111">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="f96f1-112">Vous trouverez ci-dessous des considérations importantes si vous envisagez de configurer AD FS pour l’authentification multifacteur pour l’application Lync Windows Store :</span><span class="sxs-lookup"><span data-stu-id="f96f1-112">The following are important considerations if you plan to configure AD FS for multi-factor authentication for Lync Windows Store app:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="f96f1-113">Lync Server 2013 avec des mises à jour cumulatives pour Lync Server 2013 : le 2013 juin est requis au minimum.</span><span class="sxs-lookup"><span data-stu-id="f96f1-113">Lync Server 2013 with Cumulative Updates for Lync Server 2013: June 2013 is required at a minimum.</span></span> <span data-ttu-id="f96f1-114">Les clients de bureau Lync 2013 n’ont pas besoin de mises à jour cumulatives pour Lync Server 2013 : le 2013 juin, de sorte qu’il semble que l’authentification passive fonctionne car les clients Lync 2013 peuvent s’authentifier.</span><span class="sxs-lookup"><span data-stu-id="f96f1-114">Lync 2013 desktop clients do not require Cumulative Updates for Lync Server 2013: June 2013, so it might appear that passive authentication is working because Lync 2013 clients are able to authenticate.</span></span> <span data-ttu-id="f96f1-115">Toutefois, le processus d’authentification pour les clients d’application Lync Windows Store ne se termine pas et aucune notification ni message d’erreur ne s’affiche.</span><span class="sxs-lookup"><span data-stu-id="f96f1-115">However, the authentication process for Lync Windows Store app clients will fail to complete and no notification or error message will display.</span></span></P>
> <LI>
> <P><span data-ttu-id="f96f1-116">Le serveur doit être configuré de sorte que l’authentification passive soit le seul type d’authentification offert.</span><span class="sxs-lookup"><span data-stu-id="f96f1-116">The server must be configured so that passive authentication is the only authentication type offered.</span></span></P>
> <LI>
> <P><span data-ttu-id="f96f1-117">Si vous utilisez des programmes d’équilibrage de la charge matérielle, activez la persistance des cookies sur les programmes d’équilibrage de la charge afin que toutes les demandes du client d’application Lync du Windows Store soient gérées par le même serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="f96f1-117">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Windows Store app client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="f96f1-118">Lorsque vous établissez une approbation de partie de confiance entre les serveurs Lync Server et AD FS, affectez une durée de vie de jeton suffisamment longue pour couvrir la longueur maximale de vos réunions Lync.</span><span class="sxs-lookup"><span data-stu-id="f96f1-118">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="f96f1-119">Une durée de vie de jeton de 240 minutes est généralement suffisante.</span><span class="sxs-lookup"><span data-stu-id="f96f1-119">Typically, a token life of 240 minutes is sufficient.</span></span></P></LI></UL>



</div>

<span data-ttu-id="f96f1-120">**Pour configurer l’authentification multifacteur**</span><span class="sxs-lookup"><span data-stu-id="f96f1-120">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="f96f1-121">Installez un rôle de serveur de fédération AD FS.</span><span class="sxs-lookup"><span data-stu-id="f96f1-121">Install an AD FS federation server role.</span></span> <span data-ttu-id="f96f1-122">Pour plus d’informations, consultez le Guide de déploiement des services de fédération Active Directory (AD FS) 2,0 à l’adresse <https://go.microsoft.com/fwlink/p/?linkid=267511> .</span><span class="sxs-lookup"><span data-stu-id="f96f1-122">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <https://go.microsoft.com/fwlink/p/?linkid=267511>.</span></span>

2.  <span data-ttu-id="f96f1-123">Créer des certificats pour AD FS.</span><span class="sxs-lookup"><span data-stu-id="f96f1-123">Create certificates for AD FS.</span></span> <span data-ttu-id="f96f1-124">Pour plus d’informations, consultez la section « certificats de serveur de Fédération » de la rubrique plan for and Deploy AD FS for use with Single Sign-On [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376) .</span><span class="sxs-lookup"><span data-stu-id="f96f1-124">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="f96f1-125">À partir de l’interface de ligne de commande Windows PowerShell, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f96f1-125">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="f96f1-126">Établissez un partenariat en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f96f1-126">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```
5.  <span data-ttu-id="f96f1-127">Définissez les règles de partie de confiance suivantes :</span><span class="sxs-lookup"><span data-stu-id="f96f1-127">Set the following relying party rules:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a><span data-ttu-id="f96f1-128">Problèmes connus pouvant empêcher la connexion</span><span class="sxs-lookup"><span data-stu-id="f96f1-128">Known Issues that Can Prevent Sign-in</span></span>

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a><span data-ttu-id="f96f1-129">La date et l’heure ne sont pas définies correctement sur l’appareil exécutant l’application Lync du Windows Store</span><span class="sxs-lookup"><span data-stu-id="f96f1-129">The time and date are not set accurately on the device running Lync Windows Store app</span></span>

<span data-ttu-id="f96f1-130">Le paramètre de l’heure sur l’appareil doit être synchronisé avec le paramètre heure sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="f96f1-130">The time setting on the device must be synchronized with the time setting on the server.</span></span> <span data-ttu-id="f96f1-131">Ceci est particulièrement important pour les appareils tels que Microsoft surface, ainsi que d’autres appareils exécutant Windows RT qui ne sont pas liés à un domaine.</span><span class="sxs-lookup"><span data-stu-id="f96f1-131">This is particularly important for devices such as Microsoft Surface, and other devices running Windows RT that are not joined to a domain.</span></span> <span data-ttu-id="f96f1-132">Pour définir l’heure sur ces appareils automatiquement à partir d’un serveur de temps, exécutez la commande suivante à partir d’une invite de commandes avec élévation de privilèges sur l’appareil :</span><span class="sxs-lookup"><span data-stu-id="f96f1-132">To set the time on these devices automatically from a time server, run the following command from an elevated command prompt on the device:</span></span>
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a><span data-ttu-id="f96f1-133">L’application Lync du Windows Store ne peut pas accéder au serveur ou aux services Lync</span><span class="sxs-lookup"><span data-stu-id="f96f1-133">Lync Windows Store app cannot access the Lync server or services</span></span>

<span data-ttu-id="f96f1-134">L’application Lync du Windows Store n’est peut-être pas en mesure d’accéder au serveur ou aux services Lync par le biais de cartes réseau, telles que des modems USB 4G LTE, qui ne sont pas enregistrés avec Windows 8 en tant que périphériques physiques.</span><span class="sxs-lookup"><span data-stu-id="f96f1-134">Lync Windows Store app may not be able to access the Lync server or services through network adapters, such as 4G LTE USB modems, that do not register with Windows 8 as physical devices.</span></span> <span data-ttu-id="f96f1-135">L’application Lync du Windows Store peut présenter ce problème même si les applications de bureau et les navigateurs peuvent accéder à d’autres serveurs et sites Web.</span><span class="sxs-lookup"><span data-stu-id="f96f1-135">Lync Windows Store app may have this issue even when the desktop apps and browsers are able to access other servers and web sites.</span></span>

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="f96f1-136">L’application Lync du Windows Store ne peut pas se connecter avec Lync Server 2010 et le serveur Edge Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="f96f1-136">Lync Windows Store app cannot sign in with Lync Server 2010 and Office Communications Server 2007 R2 Edge Server</span></span>

<span data-ttu-id="f96f1-137">Si votre topologie se compose de Lync Server 2010 avec le serveur Edge Office Communications Server 2007 R2, vous devrez exécuter la version mise à jour du générateur de topologies disponible dans la mise à jour cumulative de Lync Server 2010 : juillet 2013.</span><span class="sxs-lookup"><span data-stu-id="f96f1-137">If your topology consists of Lync Server 2010 with Office Communications Server 2007 R2 Edge Server, you will need to run the updated version of Topology Builder available in the cumulative update for Lync Server 2010: July 2013.</span></span> <span data-ttu-id="f96f1-138">Les versions antérieures du générateur de topologie ne créent pas le mappage requis sur le serveur Edge Office Communications Server 2007, de sorte que les clients d’application Lync Windows Store ne peuvent pas se connecter.</span><span class="sxs-lookup"><span data-stu-id="f96f1-138">Earlier versions of Topology Builder do not create the required mapping to Office Communications Server 2007 Edge Server, so Lync Windows Store app clients are unable to sign in.</span></span> <span data-ttu-id="f96f1-139">Les étapes suivantes sont nécessaires :</span><span class="sxs-lookup"><span data-stu-id="f96f1-139">The following steps are required:</span></span>

1.  <span data-ttu-id="f96f1-140">Installez la mise à jour cumulative pour Lync Server 2010 : juillet 2013 sur les pools Lync Server 2010 et les directeurs Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f96f1-140">Install the cumulative update for Lync Server 2010: July 2013 on Lync Server 2010 pools and Lync Server 2010 Directors.</span></span>

2.  <span data-ttu-id="f96f1-141">Mettez à jour la configuration de découverte automatique Lync pour indiquer que le point d’entrée SIP externe est l’adresse du serveur Edge en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="f96f1-141">Update the Lync AutoDiscover configuration to indicate that the external SIP entry point is the Edge server address by doing the following:</span></span>
    
    1.  <span data-ttu-id="f96f1-142">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f96f1-142">Open Lync Server Management Shell.</span></span>
    
    2.  <span data-ttu-id="f96f1-143">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f96f1-143">Run the following command:</span></span>
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a><span data-ttu-id="f96f1-144">L’application Lync du Windows Store ne peut pas se connecter en raison d’un échec de validation de nom de certificat</span><span class="sxs-lookup"><span data-stu-id="f96f1-144">Lync Windows Store App cannot sign in due to a certificate name validation failure</span></span>

<span data-ttu-id="f96f1-145">Un problème de connexion peut se produire pour les utilisateurs de Microsoft 365 ou Office 365 qui n’exécutent pas la dernière version de l’application Lync du Windows Store.</span><span class="sxs-lookup"><span data-stu-id="f96f1-145">A sign-in issue can occur for Microsoft 365 or Office 365 users who are not running the latest version of Lync Windows Store app.</span></span> <span data-ttu-id="f96f1-146">Ce problème se produit généralement lorsque vous utilisez plusieurs domaines (par exemple, lorsque l’URI SIP est **usera@domainZ.com** mais que le serveur Edge est **SIP.domainX.com**).</span><span class="sxs-lookup"><span data-stu-id="f96f1-146">This issue generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span> <span data-ttu-id="f96f1-147">Pour résoudre le problème, les utilisateurs doivent installer la dernière version de l’application Lync du Windows Store, qui nécessite également Windows 8,1.</span><span class="sxs-lookup"><span data-stu-id="f96f1-147">To fix the issue, users should install the latest version of Lync Windows Store app, which also requires Windows 8.1.</span></span>

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a><span data-ttu-id="f96f1-148">Utiliser les journaux d’applications Lync Windows Store pour résoudre les problèmes</span><span class="sxs-lookup"><span data-stu-id="f96f1-148">Use Lync Windows Store app logs to troubleshoot issues</span></span>

<span data-ttu-id="f96f1-149">Vous pouvez utiliser les journaux générés sur l’appareil pour résoudre les problèmes.</span><span class="sxs-lookup"><span data-stu-id="f96f1-149">You can use the logs generated on the device to troubleshoot issues.</span></span> <span data-ttu-id="f96f1-150">Les journaux sont stockés dans le dossier suivant :</span><span class="sxs-lookup"><span data-stu-id="f96f1-150">The logs are stored in the following folder:</span></span>

<span data-ttu-id="f96f1-151">% Des packages% LocalAppData% \\ \\ Microsoft. LyncMX \_ 8wekyb3d8bbwe \\ suivi des LocalState \\</span><span class="sxs-lookup"><span data-stu-id="f96f1-151">%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing</span></span>

<span data-ttu-id="f96f1-152">Avant d’obtenir les journaux d’un utilisateur, vérifiez que la journalisation est activée, puis demandez à l’utilisateur d’enregistrer les journaux de sorte que toutes les informations stockées dans la mémoire soient également enregistrées dans des fichiers sur le disque dur.</span><span class="sxs-lookup"><span data-stu-id="f96f1-152">Before you get the logs from a user, make sure that logging is turned on, and then ask the user to save the logs so that all the information stored in memory is also saved to files on the hard drive.</span></span>

<span data-ttu-id="f96f1-153">**Pour activer la journalisation**</span><span class="sxs-lookup"><span data-stu-id="f96f1-153">**To turn on logging**</span></span>

1.  <span data-ttu-id="f96f1-154">Ouvrez l’application Lync Windows Store sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="f96f1-154">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="f96f1-155">Faire glisser à partir du côté droit de l’écran.</span><span class="sxs-lookup"><span data-stu-id="f96f1-155">Swipe from the right side of the screen.</span></span> <span data-ttu-id="f96f1-156">Si vous utilisez une souris, pointez sur le coin supérieur droit de l’écran, puis déplacez le pointeur de la souris vers le bas de l’écran.</span><span class="sxs-lookup"><span data-stu-id="f96f1-156">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

3.  <span data-ttu-id="f96f1-157">Sélectionnez **paramètres**, sélectionnez **options**, puis définissez les **journaux** de diagnostic **sur activé**.</span><span class="sxs-lookup"><span data-stu-id="f96f1-157">Select **Settings**, select **Options**, and then set **Diagnostic Logs** to **On**.</span></span>

4.  <span data-ttu-id="f96f1-158">Si les **journaux de diagnostic** étaient désactivés précédemment, vous devez redémarrer Lync.</span><span class="sxs-lookup"><span data-stu-id="f96f1-158">If **Diagnostic Logs** was off previously, you must restart Lync.</span></span> <span data-ttu-id="f96f1-159">Pour redémarrer Lync, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f96f1-159">To restart Lync, do one of the following:</span></span>
    
      - <span data-ttu-id="f96f1-160">Redémarrez l’appareil.</span><span class="sxs-lookup"><span data-stu-id="f96f1-160">Restart the device.</span></span>
    
      - <span data-ttu-id="f96f1-161">Terminez la tâche Lync et relancez l’application.</span><span class="sxs-lookup"><span data-stu-id="f96f1-161">End the Lync task and launch the app again.</span></span> <span data-ttu-id="f96f1-162">Pour mettre fin à la tâche, ouvrez le gestionnaire des tâches de Windows, sélectionnez **Lync**, puis cliquez sur **fin de tâche**.</span><span class="sxs-lookup"><span data-stu-id="f96f1-162">To end the task, open the Windows Task Manager, select **Lync**, and then tap **End task**.</span></span> <span data-ttu-id="f96f1-163">Si Lync n’est pas disponible, cliquez sur **plus de détails** et recherchez Lync sous **processus en arrière-plan**.</span><span class="sxs-lookup"><span data-stu-id="f96f1-163">If Lync is not listed, tap **More details** and look for Lync under **Background processes**.</span></span>

<span data-ttu-id="f96f1-164">**Pour enregistrer les journaux**</span><span class="sxs-lookup"><span data-stu-id="f96f1-164">**To save the logs**</span></span>

1.  <span data-ttu-id="f96f1-165">Ouvrez l’application Lync Windows Store sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="f96f1-165">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="f96f1-166">Essayez de vous connecter.</span><span class="sxs-lookup"><span data-stu-id="f96f1-166">Try signing in.</span></span>

3.  <span data-ttu-id="f96f1-167">Faire glisser à partir du côté droit de l’écran.</span><span class="sxs-lookup"><span data-stu-id="f96f1-167">Swipe from the right side of the screen.</span></span> <span data-ttu-id="f96f1-168">Si vous utilisez une souris, pointez sur le coin supérieur droit de l’écran, puis déplacez le pointeur de la souris vers le bas de l’écran.</span><span class="sxs-lookup"><span data-stu-id="f96f1-168">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

4.  <span data-ttu-id="f96f1-169">Sélectionnez **paramètres**, **à propos**de, puis sélectionnez **enregistrer les journaux**.</span><span class="sxs-lookup"><span data-stu-id="f96f1-169">Select **Settings**, select **About**, and then select **Save logs**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


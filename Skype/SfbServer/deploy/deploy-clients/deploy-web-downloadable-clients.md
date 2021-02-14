---
title: Déployer des clients web téléchargeables dans Skype Entreprise Server
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Résumé : Déployez l’application web Skype Entreprise et l’application Réunions Skype utilisées avec Skype Entreprise.'
ms.openlocfilehash: afab5d0977adb8749fb514f946b676598d42ea32
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805924"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="8beec-103">Déployer des clients web téléchargeables dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8beec-103">Deploy Web downloadable clients in Skype for Business Server</span></span>

<span data-ttu-id="8beec-104">**Résumé :** Déployez l’application web Skype Entreprise 2015 et l’application Réunions Skype utilisées avec Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8beec-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server.</span></span>

<span data-ttu-id="8beec-105">Skype Entreprise Web App est un client web IIS (Internet Information Services) qui est installé sur le serveur exécutant Skype Entreprise Server et, par défaut, il est déployé à la demande pour répondre aux utilisateurs qui n’ont pas encore le client Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="8beec-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="8beec-106">Ces utilisateurs de réunion se connectent le plus souvent depuis l’extérieur de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="8beec-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="8beec-107">Chaque fois qu’un utilisateur clique sur une URL de réunion, mais que le client Skype Entreprise n’est pas installé, l’utilisateur a la possibilité de participer à la réunion à l’aide de la dernière version de Skype Entreprise Web App, Skype Meetings App ou Skype Entreprise pour Mac.</span><span class="sxs-lookup"><span data-stu-id="8beec-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App, Skype Meetings App, or Skype for Business for Mac.</span></span>

<span data-ttu-id="8beec-108">Les fonctionnalités vocales, vidéo et de partage dans Skype Entreprise Web App nécessitent un contrôle Microsoft ActiveX utilisé comme plug-in par le navigateur de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8beec-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="8beec-109">Vous pouvez installer le contrôle ActiveX à l’avance ou autoriser les utilisateurs à l’installer à l’invite, ce qui se produit la première fois qu’ils utilisent Skype Entreprise Web App ou la première fois qu’ils accèdent à une fonctionnalité nécessitant le contrôle ActiveX.</span><span class="sxs-lookup"><span data-stu-id="8beec-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>

> [!NOTE]
> <span data-ttu-id="8beec-110">Dans les déploiements de serveur Edge Skype Entreprise Server, un proxy inverse HTTPS dans le réseau de périmètre est requis pour l’accès au client Skype Entreprise Web App.</span><span class="sxs-lookup"><span data-stu-id="8beec-110">In Skype for Business Server Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="8beec-111">Vous devez également publier des URL simples.</span><span class="sxs-lookup"><span data-stu-id="8beec-111">You must also publish simple URLs.</span></span> <span data-ttu-id="8beec-112">Pour plus d’informations, voir [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span><span class="sxs-lookup"><span data-stu-id="8beec-112">For details, see [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="8beec-113">Activer l’authentification multifacteur pour Skype Entreprise Web App</span><span class="sxs-lookup"><span data-stu-id="8beec-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="8beec-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="8beec-114"><a name="MFA"> </a></span></span>

<span data-ttu-id="8beec-115">Skype Entreprise Web App, l’application réunions Skype et Skype Entreprise pour Mac prise en charge l’authentification multifacteur.</span><span class="sxs-lookup"><span data-stu-id="8beec-115">Skype for Business Web App,  Skype Meetings App, and Skype for Business for Mac support multi-factor authentication.</span></span> <span data-ttu-id="8beec-116">Outre le nom d’utilisateur et le mot de passe, vous pouvez exiger des méthodes d’authentification supplémentaires, telles que des cartes à puce ou des code pin pin, pour authentifier les utilisateurs qui rejoignent des réseaux externes lorsqu’ils se connectent à des réunions Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="8beec-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="8beec-117">Vous pouvez activer l’authentification multifacteur en déployant le serveur de fédération AD FS (Active Directory Federation Service) et en activant l’authentification passive dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8beec-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="8beec-118">Une fois les services AD FS configurés, les utilisateurs externes qui tentent de rejoindre des réunions Skype Entreprise se présentent avec une page web d’authentification multifacteur AD FS qui contient le nom d’utilisateur et la demande de mot de passe, ainsi que toutes les méthodes d’authentification supplémentaires que vous avez configurées.</span><span class="sxs-lookup"><span data-stu-id="8beec-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8beec-119">Vous trouverez ci-dessous des considérations importantes si vous envisagez de configurer les services AD FS pour l’authentification multifacteur :</span><span class="sxs-lookup"><span data-stu-id="8beec-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span>

- <span data-ttu-id="8beec-120">L’authentification ADFS multifacteur fonctionne si le participant à la réunion et l’organisateur font tous deux partie de la même organisation ou d’une organisation fédérée AD FS.</span><span class="sxs-lookup"><span data-stu-id="8beec-120">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="8beec-121">L’authentification ADFS multifacteur ne fonctionne pas pour les utilisateurs fédérés Lync, car l’infrastructure web Lync Server ne la prend actuellement pas en charge.</span><span class="sxs-lookup"><span data-stu-id="8beec-121">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>

- <span data-ttu-id="8beec-122">Si vous utilisez des équilibreurs de charge matérielle, activez la persistance des cookies sur les équilibreurs de charge afin que toutes les demandes provenant des clients Skype Entreprise Web App ou Meetings App soient gérées par le même serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="8beec-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>

- <span data-ttu-id="8beec-123">Lorsque vous établissez une relation d’confiance entre Skype Entreprise Server et les serveurs AD FS, attribuez une durée de vie de jeton suffisamment longue pour englober la durée maximale de vos réunions Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="8beec-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="8beec-124">Une durée de vie de jeton de 240 minutes est généralement suffisante.</span><span class="sxs-lookup"><span data-stu-id="8beec-124">Typically, a token life of 240 minutes is sufficient.</span></span>

- <span data-ttu-id="8beec-125">Cette configuration ne s’applique pas aux clients mobiles Lync.</span><span class="sxs-lookup"><span data-stu-id="8beec-125">This configuration does not apply to Lync mobile clients.</span></span>

### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="8beec-126">Configurer l’authentification multifacteur</span><span class="sxs-lookup"><span data-stu-id="8beec-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="8beec-127">Installez un rôle de serveur de fédération AD FS.</span><span class="sxs-lookup"><span data-stu-id="8beec-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="8beec-128">Pour plus d’informations, voir le guide de déploiement des services de fédération [Active Directory 2.0](https://go.microsoft.com/fwlink/p/?linkid=267511)</span><span class="sxs-lookup"><span data-stu-id="8beec-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](https://go.microsoft.com/fwlink/p/?linkid=267511)</span></span>

2. <span data-ttu-id="8beec-129">Créez des certificats pour AD FS.</span><span class="sxs-lookup"><span data-stu-id="8beec-129">Create certificates for AD FS.</span></span> <span data-ttu-id="8beec-130">Pour plus d’informations, voir la section « [Certificats](https://go.microsoft.com/fwlink/p/?LinkId=285376) de serveur de fédération » de la rubrique Plan for and deploy AD FS for use with single sign-on topic.</span><span class="sxs-lookup"><span data-stu-id="8beec-130">For more information, see ["Federation server certificates"](https://go.microsoft.com/fwlink/p/?LinkId=285376) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>

3. <span data-ttu-id="8beec-131">À partir Windows PowerShell’interface de ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="8beec-131">From the Windows PowerShell command-line interface, run the following command:</span></span>

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="8beec-132">Établissez un partenariat en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="8beec-132">Establish a partnership by running the following command:</span></span>

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="8beec-133">Définissez les règles de partie de confiance suivantes :</span><span class="sxs-lookup"><span data-stu-id="8beec-133">Set the following relying party rules:</span></span>

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="8beec-134">Désactiver BranchCache</span><span class="sxs-lookup"><span data-stu-id="8beec-134">Disable BranchCache</span></span>
<span data-ttu-id="8beec-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="8beec-135"><a name="MFA"> </a></span></span>

<span data-ttu-id="8beec-136">La fonctionnalité BranchCache dans Windows 7 et Windows Server 2008 R2 peut interférer avec les composants web Skype Entreprise Web App.</span><span class="sxs-lookup"><span data-stu-id="8beec-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="8beec-137">Pour éviter les problèmes pour les utilisateurs de Skype Entreprise Web App, assurez-vous que BranchCache n’est pas activé.</span><span class="sxs-lookup"><span data-stu-id="8beec-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="8beec-138">Pour plus d’informations sur la désactivation de BranchCache, voir le [Guide de déploiement de BranchCache.](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)</span><span class="sxs-lookup"><span data-stu-id="8beec-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>

## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="8beec-139">Vérification du déploiement de Skype Entreprise Web App</span><span class="sxs-lookup"><span data-stu-id="8beec-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="8beec-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="8beec-140"><a name="MFA"> </a></span></span>

<span data-ttu-id="8beec-141">Vous pouvez utiliser l’applet de commande Test-CsUcwaConference pour vérifier que deux utilisateurs de test peuvent participer à une conférence à l’aide de l’API UCWA (Unified Communications Web API).</span><span class="sxs-lookup"><span data-stu-id="8beec-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="8beec-142">Pour plus d’informations sur cette cmdlet, voir [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) dans la documentation de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8beec-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="8beec-143">Résolution des problèmes d’installation du plug-in sur Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="8beec-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="8beec-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="8beec-144"><a name="MFA"> </a></span></span>

<span data-ttu-id="8beec-145">Si l’installation du plug-in échoue sur un ordinateur exécutant Windows Server 2008 R2, vous devrez peut-être modifier le paramètre de sécurité Internet Explorer ou le paramètre de clé de Registre DisableMSI.</span><span class="sxs-lookup"><span data-stu-id="8beec-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="8beec-146">Modifier le paramètre de sécurité dans Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="8beec-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="8beec-147">Ouvrez Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="8beec-147">Open Internet Explorer.</span></span>

2. <span data-ttu-id="8beec-148">Cliquez sur **Outils**, sur **Options Internet**, puis sur **Avancé**.</span><span class="sxs-lookup"><span data-stu-id="8beec-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3. <span data-ttu-id="8beec-149">Faites défiler la page vers le bas jusqu’à la section **Sécurité**.</span><span class="sxs-lookup"><span data-stu-id="8beec-149">Scroll down to the **Security** section.</span></span>

4. <span data-ttu-id="8beec-150">Désactivez la case à cocher **Ne pas enregistrer les pages chiffrées sur le disque**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8beec-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8beec-151">S’il est sélectionné, ce paramètre provoque également une erreur lors de la tentative de téléchargement d’une pièce jointe à partir de Skype Entreprise Web App.</span><span class="sxs-lookup"><span data-stu-id="8beec-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span>

5. <span data-ttu-id="8beec-152">Rejoignez la réunion.</span><span class="sxs-lookup"><span data-stu-id="8beec-152">Rejoin the meeting.</span></span> <span data-ttu-id="8beec-153">Le plug-in doit se télécharger sans erreurs.</span><span class="sxs-lookup"><span data-stu-id="8beec-153">The plug-in should download without errors.</span></span>

### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="8beec-154">Modifier le paramètre de Registre DisableMSI</span><span class="sxs-lookup"><span data-stu-id="8beec-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="8beec-155">Cliquez sur **Démarrer**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="8beec-155">Click **Start**, and then click **Run**.</span></span>

2. <span data-ttu-id="8beec-156">Pour accéder à l’Éditeur du Registre, tapez **regedit**.</span><span class="sxs-lookup"><span data-stu-id="8beec-156">To access the Registry Editor, type **regedit**.</span></span>

3. <span data-ttu-id="8beec-157">Accédez à HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span><span class="sxs-lookup"><span data-stu-id="8beec-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>

4. <span data-ttu-id="8beec-158">Modifiez ou ajoutez la clé de Registre DisableMSI de type REG_DWORD, et affectez-lui la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="8beec-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>

5. <span data-ttu-id="8beec-159">Rejoignez la réunion.</span><span class="sxs-lookup"><span data-stu-id="8beec-159">Rejoin the meeting.</span></span>

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="8beec-160">Activer l’application réunions Skype pour remplacer Skype Entreprise Web App (facultatif, Skype Entreprise Server 2015 uniquement)</span><span class="sxs-lookup"><span data-stu-id="8beec-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="8beec-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="8beec-161"><a name="SMA_Enable"> </a></span></span>

<span data-ttu-id="8beec-162">Cette procédure est facultative et s’applique à Skype Entreprise Server 2015 CU5 et ultérieur.</span><span class="sxs-lookup"><span data-stu-id="8beec-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="8beec-163">Si vous ne l’utilisez pas, les utilisateurs externes continueront à participer à des réunions à l’aide de Skype Entreprise Web App.</span><span class="sxs-lookup"><span data-stu-id="8beec-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span>

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="8beec-164">Activer la réunion simplifiée et l’application Réunions Skype</span><span class="sxs-lookup"><span data-stu-id="8beec-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="8beec-165">Lorsque vous activez l’accès au réseau de distribution de contenu (CDN), les utilisateurs ont la possibilité de se connecter au CDN en ligne et d’obtenir l’application Réunions Skype (sur Windows) et Skype Entreprise pour Mac (sur Mac), et utilisent l’expérience simplifiée de réunion.</span><span class="sxs-lookup"><span data-stu-id="8beec-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App (on Windows) and Skype for Business for Mac (on Mac), and will use the simplified meeting join experience.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="8beec-166">Autoriser l’envoi de la télémétrie de journalisation côté client à partir de la page web de connexion à une réunion ou de l’application Réunions Skype aux serveurs Microsoft (la commande est false par défaut).</span><span class="sxs-lookup"><span data-stu-id="8beec-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="8beec-167">Les informations envoyées à Microsoft sont strictement conformes aux pratiques de collecte de données [Skype Entreprise.](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices)</span><span class="sxs-lookup"><span data-stu-id="8beec-167">Information sent to Microsoft is in strict compliance with [Skype for Business data collection practices](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span></span>

3. <span data-ttu-id="8beec-168">Définissez le délai avant de revenir à l’expérience Skype Entreprise Web App hébergée localement si CDN n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="8beec-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="8beec-169">La valeur par défaut est 6 secondes.</span><span class="sxs-lookup"><span data-stu-id="8beec-169">The default value is 6 seconds.</span></span> <span data-ttu-id="8beec-170">Si cette valeur est définie sur 0, il n’y aura aucun délai d’accès.</span><span class="sxs-lookup"><span data-stu-id="8beec-170">If this value is set to 0, there will be no timeout.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> <span data-ttu-id="8beec-171">Avec la mise à jour cumulative 5 de MeetingUxUseCdn dans Skype Entreprise Server 2015, la valeur par défaut est définie sur False.</span><span class="sxs-lookup"><span data-stu-id="8beec-171">With MeetingUxUseCdn in Skype for Business Server 2015 Cumulative Update 5, the default value is set to False.</span></span> <span data-ttu-id="8beec-172">Cela provoque un problème dans lequel le client Skype Entreprise pour Mac ne peut pas rejoindre les réunions des partenaires non fédérés en tant qu’invité, même si l’administrateur skype entreprise a réglé MeetingUxUseCdn sur True.</span><span class="sxs-lookup"><span data-stu-id="8beec-172">This causes an issue where Skype for Business for Mac client is unable to join non-federated partners' meetings as a guest, even if Skype for Business Admin has set MeetingUxUseCdn to True.</span></span> <span data-ttu-id="8beec-173">Pour que cela fonctionne, Skype Entreprise Server 2015 doit avoir la mise à jour cumulative 7, 6.0.9319.534 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="8beec-173">For this to work, Skype for Business Server 2015 must have the Cumulative Update 7, 6.0.9319.534, or later.</span></span> <span data-ttu-id="8beec-174">Voir [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).</span><span class="sxs-lookup"><span data-stu-id="8beec-174">See [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).</span></span>


## <a name="see-also"></a><span data-ttu-id="8beec-175">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8beec-175">See also</span></span>
<span data-ttu-id="8beec-176"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="8beec-176"><a name="SMA_Enable"> </a></span></span>

[<span data-ttu-id="8beec-177">Planifier les clients Meetings (application Web et application réunions)</span><span class="sxs-lookup"><span data-stu-id="8beec-177">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="8beec-178">Configurer la page de réunion dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8beec-178">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)

[<span data-ttu-id="8beec-179">Déclaration de confidentialité de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8beec-179">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[<span data-ttu-id="8beec-180">Conditions de licence et documentation</span><span class="sxs-lookup"><span data-stu-id="8beec-180">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)

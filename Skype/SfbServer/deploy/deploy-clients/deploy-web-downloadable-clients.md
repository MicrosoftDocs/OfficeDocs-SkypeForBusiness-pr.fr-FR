---
title: Déploiement de clients Web à télécharger dans Skype entreprise Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Résumé: déploiement de l’application Skype entreprise Web App et de réunions Skype utilisée avec Skype entreprise.'
ms.openlocfilehash: 8f2449fde2f270834bda50602fe163829f3b725f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234392"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="862ca-103">Déploiement de clients Web à télécharger dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="862ca-103">Deploy Web downloadable clients in Skype for Business Server</span></span>

<span data-ttu-id="862ca-104">**Résumé:** Déploiement de l’application Web Skype entreprise 2015 et de réunions Skype utilisée avec Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="862ca-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server.</span></span>

<span data-ttu-id="862ca-105">Skype entreprise Web App est un client Web Internet Information Services (IIS) installé sur le serveur exécutant Skype entreprise Server et par défaut, il est déployé à la demande pour les utilisateurs qui n’ont pas encore le client Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="862ca-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="862ca-106">Il est plus souvent possible de se connecter à l’extérieur de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="862ca-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="862ca-107">Dès qu’un utilisateur clique sur l’URL d’une réunion, mais que le client Skype entreprise n’est pas installé, l’utilisateur est invité à rejoindre la réunion à l’aide de la version la plus récente de Skype entreprise Web App, de l’application réunions Skype ou de Skype entreprise pour Mac.</span><span class="sxs-lookup"><span data-stu-id="862ca-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App, Skype Meetings App, or Skype for Business for Mac.</span></span>

<span data-ttu-id="862ca-108">Les fonctionnalités de voix, de vidéo et de partage dans Skype entreprise Web App requièrent un contrôle Microsoft ActiveX utilisé comme plugin par le navigateur de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="862ca-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="862ca-109">Lorsque vous y êtes invité, vous pouvez installer le contrôle ActiveX à l’avance ou permettre aux utilisateurs de l’installer lorsque vous y êtes invité pour la première fois sur Skype entreprise Web App ou lorsque la première fois qu’ils ont accès à une fonctionnalité nécessitant le contrôle ActiveX.</span><span class="sxs-lookup"><span data-stu-id="862ca-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>

> [!NOTE]
> <span data-ttu-id="862ca-110">Dans les déploiements de serveur Edge Skype entreprise Server, un proxy HTTPs inverse dans le réseau de périmètre est requis pour l’accès au client Skype entreprise Web App.</span><span class="sxs-lookup"><span data-stu-id="862ca-110">In Skype for Business Server Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="862ca-111">Vous devez également publier des URL simples.</span><span class="sxs-lookup"><span data-stu-id="862ca-111">You must also publish simple URLs.</span></span> <span data-ttu-id="862ca-112">Pour plus d’informations, reportez-vous à la rubrique [configuration de serveurs proxy inverse](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) et [de configurations DNS requises pour des URL simples dans Skype entreprise Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span><span class="sxs-lookup"><span data-stu-id="862ca-112">For details, see [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="862ca-113">Activer l’authentification multifacteur dans Skype entreprise Web App</span><span class="sxs-lookup"><span data-stu-id="862ca-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="862ca-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="862ca-114"></span></span>

<span data-ttu-id="862ca-115">Skype entreprise Web App, l’application réunions Skype et Skype entreprise pour Mac prennent en charge l’authentification multifacteur.</span><span class="sxs-lookup"><span data-stu-id="862ca-115">Skype for Business Web App,  Skype Meetings App, and Skype for Business for Mac support multi-factor authentication.</span></span> <span data-ttu-id="862ca-116">Outre le nom d’utilisateur et le mot de passe, vous pouvez demander des méthodes d’authentification supplémentaires, telles que des cartes à puce ou des épingles, afin d’authentifier les utilisateurs qui se connectent à partir de réseaux extérieurs lors de leur connexion aux réunions Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="862ca-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="862ca-117">Vous pouvez activer l’authentification multifacteur via le déploiement du serveur de fédération AD FS (Active Directory Federation Services) et l’activation de l’authentification passive dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="862ca-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="862ca-118">Une fois AD FS configuré, les utilisateurs externes qui essaient de participer à des réunions Skype entreprise sont dotés d’une page Web d’authentification multifacteur AD FS contenant le nom d’utilisateur et le mot de passe, ainsi que toutes les méthodes d’authentification supplémentaires que vous configuré.</span><span class="sxs-lookup"><span data-stu-id="862ca-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="862ca-119">Vous trouverez ci-dessous des considérations importantes si vous envisagez de configurer les services AD FS pour l’authentification multifacteur :</span><span class="sxs-lookup"><span data-stu-id="862ca-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span>

- <span data-ttu-id="862ca-p105">L'authentification ADFS multifacteur fonctionne si le participant à la réunion et l'organisateur appartiennent à la même organisation ou à une organisation fédérée AD FS. Elle ne fonctionne pas pour les utilisateurs fédérés Lync, car l’infrastructure web du serveur Lync ne la prend pas en charge pour le moment.</span><span class="sxs-lookup"><span data-stu-id="862ca-p105">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization. Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>

- <span data-ttu-id="862ca-122">Si vous utilisez des équilibreurs de charge matérielle, activez la persistance des cookies sur les équilibreurs de charge de sorte que toutes les demandes des clients de l’application Skype entreprise Web App ou réunions soient gérées par le même serveur principal.</span><span class="sxs-lookup"><span data-stu-id="862ca-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>

- <span data-ttu-id="862ca-123">Lorsque vous établissez une relation d’approbation de la partie de confiance entre les serveurs Skype entreprise Server et AD FS, vous devez affecter une durée de vie de jeton suffisamment longue pour pouvoir prolonger la durée maximale de votre réunion Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="862ca-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="862ca-124">Une durée de vie de jeton de 240 minutes est généralement suffisante.</span><span class="sxs-lookup"><span data-stu-id="862ca-124">Typically, a token life of 240 minutes is sufficient.</span></span>

- <span data-ttu-id="862ca-125">Cette configuration ne s’applique pas aux clients mobiles Lync.</span><span class="sxs-lookup"><span data-stu-id="862ca-125">This configuration does not apply to Lync mobile clients.</span></span>

### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="862ca-126">Configuration de l'authentification multifacteur</span><span class="sxs-lookup"><span data-stu-id="862ca-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="862ca-127">Installez un rôle de serveur de fédération AD FS.</span><span class="sxs-lookup"><span data-stu-id="862ca-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="862ca-128">Pour plus d’informations, voir le [Guide de déploiement de services ADFS (Active Directory Federation Services) 2,0](https://go.microsoft.com/fwlink/p/?linkid=267511) .</span><span class="sxs-lookup"><span data-stu-id="862ca-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](https://go.microsoft.com/fwlink/p/?linkid=267511)</span></span>

2. <span data-ttu-id="862ca-129">Créez des certificats pour AD FS.</span><span class="sxs-lookup"><span data-stu-id="862ca-129">Create certificates for AD FS.</span></span> <span data-ttu-id="862ca-130">Pour plus d’informations, reportez-vous à la section [«certificat de serveur de Fédération»](https://go.microsoft.com/fwlink/p/?LinkId=285376) de la rubrique plan pour et déployer AD FS pour une utilisation avec la rubrique authentification unique.</span><span class="sxs-lookup"><span data-stu-id="862ca-130">For more information, see ["Federation server certificates"](https://go.microsoft.com/fwlink/p/?LinkId=285376) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>

3. <span data-ttu-id="862ca-131">À partir de l’interface de ligne de commande Windows PowerShell, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="862ca-131">From the Windows PowerShell command-line interface, run the following command:</span></span>

    ```
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="862ca-132">Établissez un partenariat en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="862ca-132">Establish a partnership by running the following command:</span></span>

    ```
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="862ca-133">Définissez les règles de partie de confiance suivantes :</span><span class="sxs-lookup"><span data-stu-id="862ca-133">Set the following relying party rules:</span></span>

    ```
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="862ca-134">Désactivation de BranchCache </span><span class="sxs-lookup"><span data-stu-id="862ca-134">Disable BranchCache</span></span>
<span data-ttu-id="862ca-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="862ca-135"></span></span>

<span data-ttu-id="862ca-136">La fonctionnalité BranchCache dans Windows 7 et Windows Server 2008 R2 peut interférer avec les composants WebPart de Skype entreprise Web App.</span><span class="sxs-lookup"><span data-stu-id="862ca-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="862ca-137">Pour éviter des problèmes pour les utilisateurs de Skype entreprise Web App, assurez-vous que BranchCache n’est pas activé.</span><span class="sxs-lookup"><span data-stu-id="862ca-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="862ca-138">Pour plus d’informations sur la désactivation de BranchCache, voir le [Guide de déploiement de BranchCache](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span><span class="sxs-lookup"><span data-stu-id="862ca-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>

## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="862ca-139">Vérification du déploiement de Skype entreprise Web App</span><span class="sxs-lookup"><span data-stu-id="862ca-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="862ca-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="862ca-140"></span></span>

<span data-ttu-id="862ca-141">Vous pouvez utiliser l'applet de commande Test-CsUcwaConference pour vérifier que deux utilisateurs de test peuvent participer à une conférence à l'aide de l'API UCWA (Unified Communications Web API).</span><span class="sxs-lookup"><span data-stu-id="862ca-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="862ca-142">Pour plus d’informations sur cette applet de connexion, voir [test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) dans la documentation de Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="862ca-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="862ca-143">Résoudre les problèmes d’installation du plug-in sur Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="862ca-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="862ca-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="862ca-144"></span></span>

<span data-ttu-id="862ca-145">Si l’installation du plug-in échoue sur un ordinateur exécutant Windows Server 2008 R2, vous devrez peut-être modifier le paramètre de sécurité Internet Explorer ou le paramètre de clé de Registre DisableMSI.</span><span class="sxs-lookup"><span data-stu-id="862ca-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="862ca-146">Modification du paramètre de sécurité dans Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="862ca-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="862ca-147">Ouvrez Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="862ca-147">Open Internet Explorer.</span></span>

2. <span data-ttu-id="862ca-148">Cliquez sur \*\*Outils \*\*, sur \*\*Options Internet \*\*, puis sur \*\*Avancé \*\*.</span><span class="sxs-lookup"><span data-stu-id="862ca-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3. <span data-ttu-id="862ca-149">Faites défiler la page vers le bas jusqu'à la section **Sécurité**.</span><span class="sxs-lookup"><span data-stu-id="862ca-149">Scroll down to the **Security** section.</span></span>

4. <span data-ttu-id="862ca-150">Désactivez la case à cocher **Ne pas enregistrer les pages chiffrées sur le disque**, puis cliquez sur \*\*OK \*\*.</span><span class="sxs-lookup"><span data-stu-id="862ca-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="862ca-151">Ce paramètre entraîne également une erreur lorsque vous tentez de télécharger une pièce jointe à partir de Skype entreprise Web App.</span><span class="sxs-lookup"><span data-stu-id="862ca-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span>

5. <span data-ttu-id="862ca-p111">Rejoignez la réunion. Le plug-in doit se télécharger sans erreurs.</span><span class="sxs-lookup"><span data-stu-id="862ca-p111">Rejoin the meeting. The plug-in should download without errors.</span></span>

### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="862ca-154">Modification du paramètre de Registre DisableMSI</span><span class="sxs-lookup"><span data-stu-id="862ca-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="862ca-155">Cliquez sur \*\*Démarrer \*\*, puis sur \*\*Exécuter \*\*.</span><span class="sxs-lookup"><span data-stu-id="862ca-155">Click **Start**, and then click **Run**.</span></span>

2. <span data-ttu-id="862ca-156">Pour accéder à l'Éditeur du registre, tapez \*\*regedit \*\*.</span><span class="sxs-lookup"><span data-stu-id="862ca-156">To access the Registry Editor, type **regedit**.</span></span>

3. <span data-ttu-id="862ca-157">Accédez à HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span><span class="sxs-lookup"><span data-stu-id="862ca-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>

4. <span data-ttu-id="862ca-158">Modifiez ou ajoutez la clé de Registre DisableMSI de type REG_DWORD, et affectez-lui la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="862ca-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>

5. <span data-ttu-id="862ca-159">Rejoignez la réunion.</span><span class="sxs-lookup"><span data-stu-id="862ca-159">Rejoin the meeting.</span></span>

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="862ca-160">Activation de l’application réunions Skype pour remplacer Skype entreprise Web App (facultatif, Skype entreprise Server 2015 uniquement)</span><span class="sxs-lookup"><span data-stu-id="862ca-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="862ca-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="862ca-161"></span></span>

<span data-ttu-id="862ca-162">Cette procédure est facultative et s’applique à Skype entreprise Server 2015 CU5 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="862ca-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="862ca-163">Si ce n’est pas le cas, les utilisateurs externes continuent à rejoindre des réunions à l’aide de Skype entreprise Web App.</span><span class="sxs-lookup"><span data-stu-id="862ca-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span>

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="862ca-164">Activation de la participation simplifiée aux réunions et l'application Réunions Skype</span><span class="sxs-lookup"><span data-stu-id="862ca-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="862ca-165">Lorsque vous activez l’accès au réseau de distribution de contenu (CDN), les utilisateurs peuvent se connecter au CDN en ligne et obtenir l’application réunions Skype (sur Windows) et Skype entreprise pour Mac (sur Mac) et utiliser l’interface de réunion simplifiée.</span><span class="sxs-lookup"><span data-stu-id="862ca-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App (on Windows) and Skype for Business for Mac (on Mac), and will use the simplified meeting join experience.</span></span>

   ```
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="862ca-166">Autoriser la télémétrie de la journalisation côté client à partir de la page Web de participation à la réunion ou de l’application réunions Skype pour être envoyée aux serveurs Microsoft (la commande est définie sur false par défaut).</span><span class="sxs-lookup"><span data-stu-id="862ca-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span>

   ```
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="862ca-167">Les informations envoyées à Microsoft sont strictement conformes aux [pratiques en matière de collecte de données Skype entreprise](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span><span class="sxs-lookup"><span data-stu-id="862ca-167">Information sent to Microsoft is in strict compliance with [Skype for Business data collection practices](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span></span>

3. <span data-ttu-id="862ca-168">Définissez le délai d’expiration avant de revenir à l’interface Web de Skype entreprise hébergée en local si le CDN n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="862ca-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="862ca-169">La valeur par défaut est de 6 secondes.</span><span class="sxs-lookup"><span data-stu-id="862ca-169">The default value is 6 seconds.</span></span> <span data-ttu-id="862ca-170">Si celle-ci est définie sur 0, il n'y a pas de délai.</span><span class="sxs-lookup"><span data-stu-id="862ca-170">If this value is set to 0, there will be no timeout.</span></span>

   ```
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

## <a name="see-also"></a><span data-ttu-id="862ca-171">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="862ca-171">See also</span></span>
<span data-ttu-id="862ca-172"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="862ca-172"></span></span>

[<span data-ttu-id="862ca-173">Planifier pour les clients de conférences (application Web et application réunions)</span><span class="sxs-lookup"><span data-stu-id="862ca-173">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="862ca-174">Configuration de la page de participation à une réunion dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="862ca-174">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)

[<span data-ttu-id="862ca-175">Déclaration de confidentialité de Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="862ca-175">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)

[<span data-ttu-id="862ca-176">Termes du contrat de licence et documentation</span><span class="sxs-lookup"><span data-stu-id="862ca-176">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)

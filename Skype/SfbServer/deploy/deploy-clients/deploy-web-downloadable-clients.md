---
title: Déploiement des clients web téléchargeables pour Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Résumé : Déployer le Skype pour Business Web App et application de réunions Skype utilisé avec Skype pour les entreprises.'
ms.openlocfilehash: e1cee2741e1538da1e4c5ed8e25509415cb16ac3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server-2015"></a><span data-ttu-id="8c8c6-103">Déploiement des clients web téléchargeables pour Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="8c8c6-103">Deploy Web downloadable clients in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8c8c6-104">**Résumé :** Déployer le Skype pour Business Web App et application de réunions Skype utilisé avec Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-104">**Summary:** Deploy the Skype for Business Web App and Skype Meetings App used with Skype for Business.</span></span>
  
<span data-ttu-id="8c8c6-105">Skype pour Business Web App est un client web Internet Information Services (IIS) est installé sur le serveur exécutant Skype pour Business Server 2015 et par défaut qu'il est déployé sur demande aux utilisateurs de réunion qui n’ont pas déjà la Skype pour client d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server 2015 and default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="8c8c6-106">Ces utilisateurs de réunion sont le plus souvent que ne pas connexion à partir de l’extérieur de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="8c8c6-107">Chaque fois qu’un utilisateur clique sur une URL de la réunion, mais n’a pas le Skype pour client d’entreprise installé, l’utilisateur est présenté avec l’option pour joindre la réunion à l’aide de la dernière version de Skype pour Business Web App.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App.</span></span>
  
<span data-ttu-id="8c8c6-108">La voix, vidéo et partage les fonctionnalités dans Skype pour Business Web App nécessitent un contrôle Microsoft ActiveX qui est utilisé comme un plug-in par le navigateur de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="8c8c6-109">Vous pouvez installer le contrôle ActiveX à l’avance ou permettre aux utilisateurs d’installer lorsque vous y êtes invité, ce qui se passe la première fois qu’ils utilisent Skype pour Business Web App ou la première fois qu’ils accèdent à une fonction qui requiert le contrôle ActiveX.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8c8c6-110">Dans Skype pour les déploiements de serveur de transport Edge 2015 Business Server, un serveur proxy inverse HTTPS dans le réseau de périmètre est requis pour Skype pour l’accès client Business Web App.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-110">In Skype for Business Server 2015 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="8c8c6-111">Vous devez également publier des URL simples.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-111">You must also publish simple URLs.</span></span> <span data-ttu-id="8c8c6-112">Pour plus d’informations, consultez [Configuration des serveurs Proxy inverse](http://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) et [planification d’URL Simple](http://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx).</span><span class="sxs-lookup"><span data-stu-id="8c8c6-112">For details, see [Setting Up Reverse Proxy Servers](http://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [Planning for Simple URLs](http://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx).</span></span> 
  
## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="8c8c6-113">Activer l’authentification à plusieurs facteurs pour Skype pour Business Web App</span><span class="sxs-lookup"><span data-stu-id="8c8c6-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="8c8c6-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="8c8c6-114"></span></span>

<span data-ttu-id="8c8c6-115">Le Skype pour la version Business Server 2015 de Skype pour Business Web App prend en charge l’authentification à plusieurs facteurs.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-115">The Skype for Business Server 2015 version of Skype for Business Web App supports multi-factor authentication.</span></span> <span data-ttu-id="8c8c6-116">Outre le nom d’utilisateur et le mot de passe, vous pouvez exiger des méthodes d’authentification supplémentaires, tels que des cartes à puce ou de broches, à authentifier les utilisateurs qui appartiennent à partir de réseaux externes lors de leur inscription à Skype pour les réunions d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="8c8c6-117">Vous pouvez activer l’authentification à facteurs multiples par un déploiement de serveur de fédération de Service de fédération Active Directory (Active Directory Federation Services) et l’activation de l’authentification de passive dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server 2015.</span></span> <span data-ttu-id="8c8c6-118">Après avoir configuré ADFS, les utilisateurs externes qui tentent de joindre Skype pour les réunions d’entreprise sont présentées avec une page Web une authentification multifacteur AD FS qui contient le nom d’utilisateur et défi de mot de passe en même temps que les autres méthodes d’authentification que vous avez avez configuré.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8c8c6-119">Vous trouverez ci-dessous des considérations importantes si vous envisagez de configurer les services AD FS pour l’authentification multifacteur :</span><span class="sxs-lookup"><span data-stu-id="8c8c6-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span> 
  
- <span data-ttu-id="8c8c6-p105">L'authentification ADFS multifacteur fonctionne si le participant à la réunion et l'organisateur appartiennent à la même organisation ou à une organisation fédérée AD FS. Elle ne fonctionne pas pour les utilisateurs fédérés Lync, car l’infrastructure web du serveur Lync ne la prend pas en charge pour le moment.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-p105">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization. Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>
    
- <span data-ttu-id="8c8c6-122">Si vous utilisez des équilibreurs de charge matériels, activer la persistance de cookie sur les équilibreurs de charge afin que toutes les demandes provenant du Skype pour client d’entreprise Web App sont traitées par le même serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App client are handled by the same Front End Server.</span></span>
    
- <span data-ttu-id="8c8c6-123">Lorsque vous établissez une approbation de tiers de confiance entre Skype pour serveurs Business Server et d’AD FS, affecter une durée de vie de jeton est suffisamment longue pour couvrir la longueur maximale de votre Skype pour les réunions d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="8c8c6-124">Une durée de vie de jeton de 240 minutes est généralement suffisante.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-124">Typically, a token life of 240 minutes is sufficient.</span></span>
    
- <span data-ttu-id="8c8c6-125">Cette configuration ne s’applique pas aux clients mobiles Lync.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-125">This configuration does not apply to Lync mobile clients.</span></span>
    
### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="8c8c6-126">Configuration de l'authentification multifacteur</span><span class="sxs-lookup"><span data-stu-id="8c8c6-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="8c8c6-127">Installez un rôle de serveur de fédération AD FS.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="8c8c6-128">Pour plus d’informations, consultez le [Guide de déploiement de Active Directory Federation Services 2.0](https://go.microsoft.com/fwlink/p/?linkid=267511)</span><span class="sxs-lookup"><span data-stu-id="8c8c6-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](https://go.microsoft.com/fwlink/p/?linkid=267511)</span></span>
    
2. <span data-ttu-id="8c8c6-129">Créez des certificats pour AD FS.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-129">Create certificates for AD FS.</span></span> <span data-ttu-id="8c8c6-130">Pour plus d’informations, consultez la section [« Certificats de serveur de fédération »](https://go.microsoft.com/fwlink/p/?LinkId=285376) du Plan et déployer ADFS pour une utilisation avec une seule ouverture de session de la rubrique.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-130">For more information, see ["Federation server certificates"](https://go.microsoft.com/fwlink/p/?LinkId=285376) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>
    
3. <span data-ttu-id="8c8c6-131">À partir de l’interface de ligne de commande de Windows PowerShell, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="8c8c6-131">From the Windows PowerShell command-line interface, run the following command:</span></span>
    
    ```
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="8c8c6-132">Établissez un partenariat en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="8c8c6-132">Establish a partnership by running the following command:</span></span>
    
    ```
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="8c8c6-133">Définissez les règles de partie de confiance suivantes :</span><span class="sxs-lookup"><span data-stu-id="8c8c6-133">Set the following relying party rules:</span></span>
    
    ```
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   ```
 
   ```
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   ```

   ```
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="8c8c6-134">Désactivation de BranchCache </span><span class="sxs-lookup"><span data-stu-id="8c8c6-134">Disable BranchCache</span></span>
<span data-ttu-id="8c8c6-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="8c8c6-135"></span></span>

<span data-ttu-id="8c8c6-136">La fonctionnalité BranchCache dans Windows 7 et Windows Server 2008 R2 peut interférer avec Skype pour les composants web Business Web App.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="8c8c6-137">Pour éviter les problèmes de Skype pour les utilisateurs d’entreprise Web App, assurez-vous que BranchCache n’est pas activé.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span> 
  
<span data-ttu-id="8c8c6-138">Pour plus d’informations sur la désactivation de BranchCache, consultez le Guide de déploiement de BranchCache, qui est disponible dans le format Word à Microsoft Download Center au [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?LinkId=268788) et au format HTML dans la bibliothèque Windows Server 2008 R2 technique à [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?LinkId=268789).</span><span class="sxs-lookup"><span data-stu-id="8c8c6-138">For details about disabling BranchCache, see the BranchCache Deployment Guide, which is available in Word format at the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?LinkId=268788) and in HTML format in the Windows Server 2008 R2 Technical Library at [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?LinkId=268789).</span></span>
  
## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="8c8c6-139">Vérification de Skype pour le déploiement d’applications métier Web</span><span class="sxs-lookup"><span data-stu-id="8c8c6-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="8c8c6-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="8c8c6-140"></span></span>

<span data-ttu-id="8c8c6-141">Vous pouvez utiliser l'applet de commande Test-CsUcwaConference pour vérifier que deux utilisateurs de test peuvent participer à une conférence à l'aide de l'API UCWA (Unified Communications Web API).</span><span class="sxs-lookup"><span data-stu-id="8c8c6-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="8c8c6-142">Pour plus d’informations sur cette applet de commande, reportez-vous à la section [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) dans le Skype pour obtenir une documentation Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>
  
## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="8c8c6-143">Dépannage de l’Installation du plug-in sur Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="8c8c6-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="8c8c6-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="8c8c6-144"></span></span>

<span data-ttu-id="8c8c6-145">En cas d’échec de l’installation du plug-in sur un ordinateur exécutant Windows Server 2008 R2, vous devrez peut-être modifier le paramètre de sécurité d’Internet Explorer ou le paramètre de clé de Registre DisableMSI.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>
  
### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="8c8c6-146">Modification du paramètre de sécurité dans Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="8c8c6-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="8c8c6-147">Ouvrez Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-147">Open Internet Explorer.</span></span>
    
2. <span data-ttu-id="8c8c6-148">Cliquez sur **Outils **, sur **Options Internet **, puis sur **Avancé **.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>
    
3. <span data-ttu-id="8c8c6-149">Faites défiler la page vers le bas jusqu'à la section **Sécurité**.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-149">Scroll down to the **Security** section.</span></span>
    
4. <span data-ttu-id="8c8c6-150">Désactivez la case à cocher **Ne pas enregistrer les pages chiffrées sur le disque**, puis cliquez sur **OK **.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8c8c6-151">Si sélectionné, ce paramètre provoque également une erreur lorsque vous tentez de télécharger une pièce jointe à partir de Skype pour Business Web App.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span> 
  
5. <span data-ttu-id="8c8c6-p111">Rejoignez la réunion. Le plug-in doit se télécharger sans erreurs.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-p111">Rejoin the meeting. The plug-in should download without errors.</span></span>
    
### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="8c8c6-154">Modification du paramètre de Registre DisableMSI</span><span class="sxs-lookup"><span data-stu-id="8c8c6-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="8c8c6-155">Cliquez sur **Démarrer **, puis sur **Exécuter **.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-155">Click **Start**, and then click **Run**.</span></span>
    
2. <span data-ttu-id="8c8c6-156">Pour accéder à l'Éditeur du registre, tapez **regedit **.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-156">To access the Registry Editor, type **regedit**.</span></span>
    
3. <span data-ttu-id="8c8c6-157">Accédez à HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>
    
4. <span data-ttu-id="8c8c6-158">Modifiez ou ajoutez la clé de Registre DisableMSI de type REG_DWORD, et affectez-lui la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>
    
5. <span data-ttu-id="8c8c6-159">Rejoignez la réunion.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-159">Rejoin the meeting.</span></span>
    
## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional"></a><span data-ttu-id="8c8c6-160">Activation de l'application Réunions Skype pour remplacer Skype Entreprise Web App (facultatif)</span><span class="sxs-lookup"><span data-stu-id="8c8c6-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional)</span></span>
<span data-ttu-id="8c8c6-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="8c8c6-161"></span></span>

<span data-ttu-id="8c8c6-162">Cette procédure est facultative.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-162">This procedure is optional.</span></span> <span data-ttu-id="8c8c6-163">Si vous ne l’utilisez pas, les utilisateurs externes continuera à participer à des conférences à l’aide de Skype pour Business Web App.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span> 
  
### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="8c8c6-164">Activation de la participation simplifiée aux réunions et l'application Réunions Skype</span><span class="sxs-lookup"><span data-stu-id="8c8c6-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="8c8c6-165">Lorsque vous activez l’accès pour le réseau CDN (Content Delivery), les utilisateurs auront la possibilité de se connecter en ligne CDN et application de réunions Skype et utilisez simplifié expérience de jointure de la réunion.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App, and will use the simplified meeting join experience.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="8c8c6-166">Autoriser le client télémétrie de journalisation côté de la réunion de joindre une page web ou l’application de réunions Skype à envoyer aux serveurs de Microsoft (la commande false par défaut).</span><span class="sxs-lookup"><span data-stu-id="8c8c6-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="8c8c6-167">Informations envoyées à Microsoft sont en stricte conformité avec [Skype pour entreprise de collecte de données](https://support.office.com/en-us/article/Skype-for-Business-data-collection-practices-c17e8ea6-b83b-4345-9401-47a6c8b13aad?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8c8c6-167">Information sent to Microsoft is in strict compliance with [Skype for Business data collection practices](https://support.office.com/en-us/article/Skype-for-Business-data-collection-practices-c17e8ea6-b83b-4345-9401-47a6c8b13aad?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
    
3. <span data-ttu-id="8c8c6-168">Définir le délai d’attente avant le passage à la Skype hébergé localement pour une expérience d’entreprise Web App CDN n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="8c8c6-169">La valeur par défaut est de 6 secondes.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-169">The default value is 6 seconds.</span></span> <span data-ttu-id="8c8c6-170">Si celle-ci est définie sur 0, il n'y a pas de délai.</span><span class="sxs-lookup"><span data-stu-id="8c8c6-170">If this value is set to 0, there will be no timeout.</span></span>
    
   ```
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

## <a name="see-also"></a><span data-ttu-id="8c8c6-171">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8c8c6-171">See also</span></span>
<span data-ttu-id="8c8c6-172"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="8c8c6-172"></span></span>

#### 

[<span data-ttu-id="8c8c6-173">Planifier des clients de réunions (Web App et réunions App)</span><span class="sxs-lookup"><span data-stu-id="8c8c6-173">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)
  
[<span data-ttu-id="8c8c6-174">Planifier des clients de réunions (Web App et réunions App)</span><span class="sxs-lookup"><span data-stu-id="8c8c6-174">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)
#### 

[<span data-ttu-id="8c8c6-175">Configuration de la Page d’inscription de réunion</span><span class="sxs-lookup"><span data-stu-id="8c8c6-175">Configuring the Meeting Join Page</span></span>](http://technet.microsoft.com/library/45880423-47f4-49af-b825-cbd8e3fc1046.aspx)
  
[<span data-ttu-id="8c8c6-176">Déclaration de confidentialité de Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="8c8c6-176">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)
  
[<span data-ttu-id="8c8c6-177">Termes du contrat de licence et la Documentation</span><span class="sxs-lookup"><span data-stu-id="8c8c6-177">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)


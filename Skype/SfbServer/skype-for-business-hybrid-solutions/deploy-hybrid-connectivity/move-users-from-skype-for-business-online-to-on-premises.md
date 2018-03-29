---
title: Déplacer les utilisateurs Skype pour Business Online sur site
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/19/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 55733bb5-6742-4daf-8db5-1c5df86f4cea
description: 'Résumé : Découvrez comment déplacer des comptes d’utilisateurs en ligne dans les locaux de Skype pour Business Server.'
ms.openlocfilehash: e429aebc6847146ad5bef2b34d6ccfa7d2997ec6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="move-users-from-skype-for-business-online-to-on-premises"></a><span data-ttu-id="1a04b-103">Déplacer les utilisateurs Skype pour Business Online sur site</span><span class="sxs-lookup"><span data-stu-id="1a04b-103">Move users from Skype for Business Online to on premises</span></span>
 
<span data-ttu-id="1a04b-104">**Résumé :** Découvrez comment déplacer des comptes d’utilisateurs en ligne dans les locaux de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="1a04b-104">**Summary:** Learn how to move user accounts from online to on premises in Skype for Business Server.</span></span>
  
<span data-ttu-id="1a04b-105">Vous devrez peut-être déplacer des comptes d’utilisateurs à partir d’online à sur site pour garantir que les utilisateurs hébergement en ligne et sur site sont identifiables à une de l’autre.</span><span class="sxs-lookup"><span data-stu-id="1a04b-105">You might need to move user accounts from online to on premises to ensure that users homed online and on premises are discoverable to one another.</span></span> <span data-ttu-id="1a04b-106">Pour être détectable par une de l’autre, tous les utilisateurs doivent avoir une présence dans le local d’Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1a04b-106">To be discoverable to one another, all users must have a presence in the on-premises Active Directory.</span></span> <span data-ttu-id="1a04b-107">Pour plus d’informations, consultez [planification de la connectivité d’hybride entre Skype pour Business Server et Skype pour l’activité en ligne](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="1a04b-107">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span></span> <span data-ttu-id="1a04b-108">Vous souhaiterez déplacer des utilisateurs en ligne sur le site, par exemple, si :</span><span class="sxs-lookup"><span data-stu-id="1a04b-108">You might want to move online users to on premises, for example, if:</span></span> 
  
- <span data-ttu-id="1a04b-109">Vous avez des utilisateurs qui doivent être créés sur un site et ensuite vers le nuage.</span><span class="sxs-lookup"><span data-stu-id="1a04b-109">You have new users who need to be created on premises and then moved to the cloud.</span></span>
    
- <span data-ttu-id="1a04b-110">Votre organisation a déployé Skype pour Business Online avant de déployer Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="1a04b-110">Your organization deployed Skype for Business Online before it deployed Skype for Business Server.</span></span> <span data-ttu-id="1a04b-111">Par conséquent, vous avez des utilisateurs qui ont été créés initialement dans le nuage et maintenant devez être déplacées à dans les locaux d’avant de les déplacer à Skype pour entreprise en ligne.</span><span class="sxs-lookup"><span data-stu-id="1a04b-111">Therefore, you have users who were created in the cloud first, and now need to be moved to on premises before they are move to Skype for Business Online.</span></span> 
    
<span data-ttu-id="1a04b-112">Cette rubrique décrit deux scénarios :</span><span class="sxs-lookup"><span data-stu-id="1a04b-112">This topic describes two scenarios:</span></span>
  
- [<span data-ttu-id="1a04b-113">Déplacer des utilisateurs en ligne — qui étaient à l’origine en ligne — à sur site</span><span class="sxs-lookup"><span data-stu-id="1a04b-113">Move online users—who were originally online—to on premises</span></span>](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonline)
    
- [<span data-ttu-id="1a04b-114">Déplacer en ligne utilisateurs (ce qui étaient initialement sur un site) sur le site</span><span class="sxs-lookup"><span data-stu-id="1a04b-114">Move online users (who were originally on premises) to on premises</span></span>](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonprem)
    
## <a name="move-online-userswho-were-originally-onlineto-on-premises"></a><span data-ttu-id="1a04b-115">Déplacer des utilisateurs en ligne — qui étaient à l’origine en ligne — à sur site</span><span class="sxs-lookup"><span data-stu-id="1a04b-115">Move online users—who were originally online—to on premises</span></span>
<span data-ttu-id="1a04b-116"><a name="BKMK_originallyonline"> </a></span><span class="sxs-lookup"><span data-stu-id="1a04b-116"></span></span>

<span data-ttu-id="1a04b-117">Cette section s’applique uniquement aux utilisateurs qui ont créé et activé en ligne, mais qui n’ont pas d’un compte dans les locaux sur Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1a04b-117">This section applies only to users who were created and enabled online, but who do not have an account in the on premises Active Directory.</span></span> 
  
<span data-ttu-id="1a04b-118">Avant de commencer à déplacer les utilisateurs en ligne vers votre environnement local, vérifiez que toutes les conditions suivantes sont vraies :</span><span class="sxs-lookup"><span data-stu-id="1a04b-118">Before you start moving online users to your on-premises environment, check that all of the following are true:</span></span>
  
- <span data-ttu-id="1a04b-119">Votre environnement local doit être déployé et validé complètement.</span><span class="sxs-lookup"><span data-stu-id="1a04b-119">Your on-premises environment must be fully deployed and validated.</span></span> <span data-ttu-id="1a04b-120">Pour plus d’informations, consultez [déploiement de Lync Server 2013](http://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) ou [Déployer un Skype pour Business Server 2015](../../deploy/deploy.md), selon quelle version vous utilisez dans les locaux.</span><span class="sxs-lookup"><span data-stu-id="1a04b-120">For more information, see [Deploying Lync Server 2013](http://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) or [Deploy Skype for Business Server 2015](../../deploy/deploy.md), depending on which version you are using on premises.</span></span> 
    
- <span data-ttu-id="1a04b-121">Vos clients en ligne doit être configuré pour l’accès distant de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a04b-121">Your online tenant must be configured for remote PowerShell access.</span></span>
    
    <span data-ttu-id="1a04b-122">Pour ce faire, installez d’abord le Skype pour module de connecteur Business Online pour Windows PowerShell, ce que vous pouvez obtenir ici : [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="1a04b-122">To do this, first install the Skype for Business Online connector module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
    
    <span data-ttu-id="1a04b-123">Après avoir installé le module, vous pouvez établir une session à distance en tapant les applets de commande suivantes dans le Skype pour Business Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="1a04b-123">After you install the module, you can establish a remote session by typing the following cmdlets in the Skype for Business Server Management Shell:</span></span>
    
  ```
  Import-Module SkypeOnlineConnector
  ```

  ```
  $cred = Get-Credential
  ```

  ```
  $CSSession = New-CsOnlineSession -Credential $cred
  ```

  ```
  Import-PSSession $CSSession -AllowClobber
  ```

    <span data-ttu-id="1a04b-124">Pour plus d’informations sur la façon d’établir une session PowerShell à distance avec Skype pour professionnels en ligne, consultez [connexion à Lync Online en utilisant Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx).</span><span class="sxs-lookup"><span data-stu-id="1a04b-124">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Lync Online By Using Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx).</span></span>
    
    <span data-ttu-id="1a04b-125">Pour plus d’informations sur l’utilisation de la Skype pour module de PowerShell en ligne Business connector, reportez-vous [à l’aide de Windows PowerShell pour gérer Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).</span><span class="sxs-lookup"><span data-stu-id="1a04b-125">For more information about using the Skype for Business Online connector PowerShell module, see [Using Windows PowerShell to Manage Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).</span></span>
    
- <span data-ttu-id="1a04b-126">Vos clients en ligne doivent être configurés pour un espace d’adressage partagé SIP.</span><span class="sxs-lookup"><span data-stu-id="1a04b-126">Your online tenant must be configured for a shared SIP address space.</span></span> <span data-ttu-id="1a04b-127">Pour ce faire, commencez une session Powershell distante avec Skype pour l’activité en ligne.</span><span class="sxs-lookup"><span data-stu-id="1a04b-127">To do this, first start a remote Powershell session with Skype for Business Online.</span></span> <span data-ttu-id="1a04b-128">Ensuite, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1a04b-128">Then run the following cmdlet:</span></span>
    
  ```
  Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
  ```

    > [!NOTE]
    > <span data-ttu-id="1a04b-129">L’attribut SharedSipAddressSpace doit rester « True », jusqu'à ce que pour le déplacement en ligne est final et aucun utilisateur reste dans les locaux.</span><span class="sxs-lookup"><span data-stu-id="1a04b-129">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on premises.</span></span> 
  
<span data-ttu-id="1a04b-130">Une fois que vous avez terminé ces étapes, vous pouvez migrer les comptes d’utilisateur comme décrit dans la procédure suivante :</span><span class="sxs-lookup"><span data-stu-id="1a04b-130">After you've finished these steps, you can migrate user accounts as described in the following procedure:</span></span>
  
### <a name="move-user-accounts-originally-enabled-online-to-an-on-premises-deployment"></a><span data-ttu-id="1a04b-131">Déplacer des comptes d’utilisateur à l’origine en ligne à un déploiement sur site</span><span class="sxs-lookup"><span data-stu-id="1a04b-131">Move user accounts originally enabled online to an on-premises deployment</span></span>

1. <span data-ttu-id="1a04b-132">Vérifiez tout d’abord que votre organisation est configurée pour l’environnement hybride, dont les outils Azure Active Directory Connect et de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="1a04b-132">First, make sure that your organization is configured for hybrid, including Azure Active Directory Connect and sync tools.</span></span> <span data-ttu-id="1a04b-133">Pour plus d’informations, consultez [planification de la connectivité d’hybride entre Skype pour Business Server et Skype pour l’activité en ligne](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="1a04b-133">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span></span>
    
  - <span data-ttu-id="1a04b-134">Dans votre déploiement sur site, le Skype pour Business Server Management Shell, tapez les applets de commande suivantes pour créer le fournisseur d’hébergement pour Skype pour l’activité en ligne.</span><span class="sxs-lookup"><span data-stu-id="1a04b-134">On your on-premises deployment, in the Skype for Business Server Management Shell, type the following cmdlets to create the hosting provider for Skype for Business Online.</span></span> <span data-ttu-id="1a04b-135">Vous pouvez utiliser les valeurs de votre choix pour les paramètres Identité et Nom.</span><span class="sxs-lookup"><span data-stu-id="1a04b-135">You can use whatever value you want for the Identity and Name parameters.</span></span>
    
  ```
  Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
  ```

  ```
  New-CsHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
  ```

2. <span data-ttu-id="1a04b-136">Vérifiez que sur vos serveurs de bord sur place, la chaîne de certificats qui permet la connexion à Skype pour Business Online, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="1a04b-136">Confirm that on your on-premises Edge Servers, you have the certificate chain that enables connection to Skype for Business Online, as shown in the following table.</span></span> <span data-ttu-id="1a04b-137">Vous pouvez télécharger cette chaîne ici : [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).</span><span class="sxs-lookup"><span data-stu-id="1a04b-137">You can download this chain here: [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).</span></span>
    
|<span data-ttu-id="1a04b-138">**Certificat**</span><span class="sxs-lookup"><span data-stu-id="1a04b-138">**Certificate**</span></span>|<span data-ttu-id="1a04b-139">**Magasin de certificats**</span><span class="sxs-lookup"><span data-stu-id="1a04b-139">**Certificate Store**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1a04b-140">Certificat racine de CyberTrust Baltimore</span><span class="sxs-lookup"><span data-stu-id="1a04b-140">Baltimore CyberTrust Root</span></span>  <br/> |<span data-ttu-id="1a04b-141">Autorité de certification racine de confiance</span><span class="sxs-lookup"><span data-stu-id="1a04b-141">Trusted Root CA</span></span>  <br/> |
|<span data-ttu-id="1a04b-142">Microsoft Internet Authority (Nouveau certificat de l’autorité de certification racine)</span><span class="sxs-lookup"><span data-stu-id="1a04b-142">Microsoft Internet Authority (New CA certificate)</span></span>  <br/> |<span data-ttu-id="1a04b-143">Autorité de certification intermédiaire</span><span class="sxs-lookup"><span data-stu-id="1a04b-143">Intermediate CA</span></span>  <br/> |
|<span data-ttu-id="1a04b-144">MSIT Machine Auth CA2 (Nouvelle autorité de certification émettrice CA2)</span><span class="sxs-lookup"><span data-stu-id="1a04b-144">MSIT Machine Auth CA2 (New Issuing CA2)</span></span>  <br/> |<span data-ttu-id="1a04b-145">Autorité de certification intermédiaire</span><span class="sxs-lookup"><span data-stu-id="1a04b-145">Intermediate CA</span></span>  <br/> |
   
3. <span data-ttu-id="1a04b-146">Dans Active Directory sur site, activer les comptes d’utilisateur concernés pour Skype pour 2015 de serveur d’entreprise dans les locaux.</span><span class="sxs-lookup"><span data-stu-id="1a04b-146">In your on-premises Active Directory, enable the affected user accounts for Skype for Business Server 2015 on premises.</span></span> <span data-ttu-id="1a04b-147">Pour un utilisateur individuel, tapez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1a04b-147">You can do this for an individual user by typing the following cmdlet:</span></span> 
    
  ```
  Enable-CsUser
-Identity "username " 
-SipAddress "sip: username @contoso.com"
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

    <span data-ttu-id="1a04b-148">Vous pouvez également créer un script qui lit les noms d’utilisateur dans un fichier et les transmet comme informations à l’applet de commande Enable-CsUser :</span><span class="sxs-lookup"><span data-stu-id="1a04b-148">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>
    
  ```
  Enable-CsUser
-Identity $Identity 
-SipAddress $SipAddress 
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

4. <span data-ttu-id="1a04b-149">Synchroniser les utilisateurs en ligne avec les utilisateurs de la mise à jour sur site.</span><span class="sxs-lookup"><span data-stu-id="1a04b-149">Synchronize the online users with the updated on-premises users.</span></span> <span data-ttu-id="1a04b-150">Pour plus d’informations, consultez [Outils d’intégration de répertoire](https://go.microsoft.com/fwlink/p/?LinkId=530320).</span><span class="sxs-lookup"><span data-stu-id="1a04b-150">For more information, see [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?LinkId=530320).</span></span>
    
5. <span data-ttu-id="1a04b-151">Mettre à jour les enregistrements DNS suivants pour diriger le trafic SIP à votre déploiement sur site :</span><span class="sxs-lookup"><span data-stu-id="1a04b-151">Update the following DNS records to direct all SIP traffic to your on-premises deployment:</span></span>
    
  - <span data-ttu-id="1a04b-152">Mettez à jour **lyncdiscover.contoso.com**  Un enregistrement pour pointer vers le nom de domaine complet (FQDN) du serveur proxy inverse local.</span><span class="sxs-lookup"><span data-stu-id="1a04b-152">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>
    
  - <span data-ttu-id="1a04b-153">Mise à jour de la ** *_sip* . _tls.contoso.com** SRV enregistrement pour résoudre l’adresse IP ou VIP publique du service des locaux de Lync Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="1a04b-153">Update the ** *_sip*  ._tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
  - <span data-ttu-id="1a04b-154">Mise à jour de la ** *_sipfederationtls* . _tcp.contoso.com** SRV enregistrement pour résoudre l’adresse IP ou VIP publique du service Edge d’accès de Skype pour Business Server 2015 sur site.</span><span class="sxs-lookup"><span data-stu-id="1a04b-154">Update the ** *_sipfederationtls*  ._tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Skype for Business Server 2015 on-premises.</span></span>
    
  - <span data-ttu-id="1a04b-155">Si votre entreprise utilise fractionnée DNS (parfois appelé « Déconnexion évitée DNS »), assurez-vous que les utilisateurs de la résolution de noms par le biais de la zone DNS interne sont dirigés vers le Pool fin avant.</span><span class="sxs-lookup"><span data-stu-id="1a04b-155">If your organization uses split DNS (sometimes called "split-brain DNS"), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>
    
6. <span data-ttu-id="1a04b-156">Type de la `Get-CsUser` applet de commande pour vérifier certaines propriétés sur les utilisateurs que vous allez déplacer.</span><span class="sxs-lookup"><span data-stu-id="1a04b-156">Type the  `Get-CsUser` cmdlet to check some properties about the users you'll be moving.</span></span> <span data-ttu-id="1a04b-157">Vérifiez que HostingProviderProxyFQDN possède la valeur `"sipfed.online.lync.com"` et que les adresses SIP (Session Initiation Protocol) sont définies correctement.</span><span class="sxs-lookup"><span data-stu-id="1a04b-157">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>
    
7. <span data-ttu-id="1a04b-158">Déplacer des utilisateurs en ligne sur le site.</span><span class="sxs-lookup"><span data-stu-id="1a04b-158">Move online users to on premises.</span></span>
    
    <span data-ttu-id="1a04b-159">Pour déplacer un seul utilisateur, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="1a04b-159">To move a single user, type this:</span></span>
    
  ```
  $cred = Get-Credential
  ```

  ```
  Move-CsUser -Identity <username>@contoso.com  -Target "<fe-pool>.contoso.com " -Credential $cred -HostedMigrationOverrideURL <URL>
  ```

    <span data-ttu-id="1a04b-160">Vous pouvez déplacer plusieurs utilisateurs à l’aide de l’applet de commande **Get-CsUSer** -paramètre de filtre pour sélectionner les utilisateurs à une propriété spécifique.</span><span class="sxs-lookup"><span data-stu-id="1a04b-160">You can move multiple users by using the **Get-CsUSer** cmdlet with the -Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="1a04b-161">Par exemple, vous pouvez sélectionner tous les utilisateurs en ligne par filtrage des {fournisseur d’hébergement - eq « sipfed.online.lync.om »}.</span><span class="sxs-lookup"><span data-stu-id="1a04b-161">For example, you could select all Online users by filtering for {Hosting Provider -eq "sipfed.online.lync.om"}.</span></span> <span data-ttu-id="1a04b-162">Vous pouvez ensuite canaliser les utilisateurs retournées à l’applet de commande **Move-CsUSer** , comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="1a04b-162">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>
    
  ```
  Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com " -Credential $creds -HostedMigrationOverrideURL <URL>
  ```

    <span data-ttu-id="1a04b-163">Le format de l’URL spécifiée pour le paramètre **HostedMigrationOverrideUrl** doit être une URL vers le pool dans lequel le service hébergé de Migration est en cours d’exécution, dans le format suivant : _Https://\<nom de domaine complet Pool\>/HostedMigration/ hostedmigrationService.svc_.</span><span class="sxs-lookup"><span data-stu-id="1a04b-163">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: _Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span>
    
    <span data-ttu-id="1a04b-164">Vous pouvez déterminer l’URL du service de migration hébergée en affichant l’URL du Panneau de configuration Lync Online correspondant à votre compte client Office 365.</span><span class="sxs-lookup"><span data-stu-id="1a04b-164">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>
    
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="1a04b-165">Pour déterminer l’URL du service de migration hébergée de votre client Office 365</span><span class="sxs-lookup"><span data-stu-id="1a04b-165">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="1a04b-166">Connectez-vous à votre client Office 365 en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="1a04b-166">Login to your Office 365 tenant as an administrator.</span></span>
    
2. <span data-ttu-id="1a04b-167">Ouvrez le **Centre d’administration Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="1a04b-167">Open the **Skype for Business admin center**.</span></span>
    
3. <span data-ttu-id="1a04b-168">Une fois le **Centre d’administration Skype Entreprise** affiché, sélectionnez l’URL et copiez-la dans la barre d’adresse jusqu’à **lync.com**. L’URL doit se présenter comme dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="1a04b-168">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. <span data-ttu-id="1a04b-169">Dans l’URL, remplacez **webdir** par **admin** pour obtenir le résultat suivant :</span><span class="sxs-lookup"><span data-stu-id="1a04b-169">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span> 
    
     `https://admin0a.online.lync.com`
    
5. <span data-ttu-id="1a04b-170">Ajoutez la chaîne ci-dessous à l’URL : **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="1a04b-170">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="1a04b-171">L’URL résultante, qui est la valeur de la **HostedMigrationOverrideUrl**, doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="1a04b-171">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    > [!NOTE]
    > <span data-ttu-id="1a04b-172">La taille maximale par défaut pour les fichiers journaux de transaction de la base de données rtcxds est de 16 Go.</span><span class="sxs-lookup"><span data-stu-id="1a04b-172">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="1a04b-173">Cela est assez grand pour si vous déplacez un grand nombre d’utilisateurs à la fois, surtout si vous avez activé de la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="1a04b-173">This might not be big enough if you're moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="1a04b-174">Pour résoudre ce problème, vous pouvez augmenter la taille du fichier ou sauvegarder régulièrement les fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="1a04b-174">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="1a04b-175">Pour plus d’informations, voir [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725).</span><span class="sxs-lookup"><span data-stu-id="1a04b-175">For more information, see [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725).</span></span> 
  
8. <span data-ttu-id="1a04b-176">Il s’agit d’une étape facultative.</span><span class="sxs-lookup"><span data-stu-id="1a04b-176">This is an optional step.</span></span> <span data-ttu-id="1a04b-177">Pour une intégration à Exchange 2013 Online, vous devez utiliser un autre fournisseur d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="1a04b-177">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="1a04b-178">Pour plus d’informations, consultez [configurer une intégration entre Skype sur site pour Business Server 2015 et Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="1a04b-178">For details, see [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).</span></span>
    
9. <span data-ttu-id="1a04b-p114">Les utilisateurs sont maintenant déplacés. Pour vérifier qu’un utilisateur possède des valeurs correctes pour les attributs affichés dans le tableau ci-dessous, tapez cette applet de commande :</span><span class="sxs-lookup"><span data-stu-id="1a04b-p114">The users are now moved. To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span> 
    
  ```
  Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
  ```

|<span data-ttu-id="1a04b-181">**Attribut de répertoire actif**</span><span class="sxs-lookup"><span data-stu-id="1a04b-181">**Active Directory attribute**</span></span>|<span data-ttu-id="1a04b-182">**Nom de l’attribut**</span><span class="sxs-lookup"><span data-stu-id="1a04b-182">**Attribute name**</span></span>|<span data-ttu-id="1a04b-183">**Valeur correcte pour l’utilisateur en ligne**</span><span class="sxs-lookup"><span data-stu-id="1a04b-183">**Correct value for Online user**</span></span>|<span data-ttu-id="1a04b-184">**Valeur correcte pour les utilisateurs locaux**</span><span class="sxs-lookup"><span data-stu-id="1a04b-184">**Correct value for on-premises users**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1a04b-185">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="1a04b-185">msRTCSIP-DeploymentLocator</span></span>  <br/> |<span data-ttu-id="1a04b-186">HostingProvider</span><span class="sxs-lookup"><span data-stu-id="1a04b-186">HostingProvider</span></span>  <br/> |<span data-ttu-id="1a04b-187">sipfed.Online.Lync.com</span><span class="sxs-lookup"><span data-stu-id="1a04b-187">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="1a04b-188">SRV :</span><span class="sxs-lookup"><span data-stu-id="1a04b-188">SRV:</span></span>  <br/> |
|<span data-ttu-id="1a04b-189">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="1a04b-189">msRTCSIP-PrimaryUserAddress</span></span>  <br/> |<span data-ttu-id="1a04b-190">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="1a04b-190">SIPAddress</span></span>  <br/> |<span data-ttu-id="1a04b-191">SIP:username@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a04b-191">sip:userName@contoso.com</span></span>  <br/> |<span data-ttu-id="1a04b-192">SIP:username@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a04b-192">sip:userName@contoso.com</span></span>  <br/> |
|<span data-ttu-id="1a04b-193">sRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="1a04b-193">sRTCSIP-UserEnabled</span></span>  <br/> |<span data-ttu-id="1a04b-194">Activé</span><span class="sxs-lookup"><span data-stu-id="1a04b-194">Enabled</span></span>  <br/> |<span data-ttu-id="1a04b-195">True</span><span class="sxs-lookup"><span data-stu-id="1a04b-195">True</span></span>  <br/> |<span data-ttu-id="1a04b-196">True</span><span class="sxs-lookup"><span data-stu-id="1a04b-196">True</span></span>  <br/> |
   
10. <span data-ttu-id="1a04b-p115">Chaque utilisateur déplacé devra se déconnecter, puis se reconnecter. Lorsque l’utilisateur se reconnecte, il doit vérifier ses listes de contacts et ajouter des contacts, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="1a04b-p115">Each user who has been moved will need to log out, then log back in. When they log in they should verify their contact lists, and add contacts if needed.</span></span>
    
    <span data-ttu-id="1a04b-p116">Notez que les réunions planifiées ne sont pas migrées de la version en ligne vers la version locale. Les utilisateurs doivent replanifier ces réunions après les avoir déplacées.</span><span class="sxs-lookup"><span data-stu-id="1a04b-p116">Note that scheduled meetings are not migrated from online to on-premises. Users will need to reschedule these meetings after being moved.</span></span>
    
    <span data-ttu-id="1a04b-201">Une fois que les enregistrements DNS sont mis à jour et tous les utilisateurs sont dirigés vers les locaux, l’attribut HostingProvider dirige l’utilisateur vers les utilisent des enregistrements SRV ou de les diriger vers le fournisseur en ligne « sipfed.online.lync.com ».</span><span class="sxs-lookup"><span data-stu-id="1a04b-201">After the DNS records are updated and all users are directed to On-premises, the HostingProvider attribute directs the user to either use SRV records or direct them to the Online provider "sipfed.online.lync.com."</span></span>
    
## <a name="move-online-users-who-were-originally-on-premises-to-on-premises"></a><span data-ttu-id="1a04b-202">Déplacer en ligne utilisateurs (ce qui étaient initialement sur un site) sur le site</span><span class="sxs-lookup"><span data-stu-id="1a04b-202">Move online users (who were originally on premises) to on premises</span></span>
<span data-ttu-id="1a04b-203"><a name="BKMK_originallyonprem"> </a></span><span class="sxs-lookup"><span data-stu-id="1a04b-203"></span></span>

<span data-ttu-id="1a04b-204">Cette section s’applique uniquement aux utilisateurs qui ont été créés et activés pour un déploiement sur site et ensuite vers un déploiement sur site en ligne.</span><span class="sxs-lookup"><span data-stu-id="1a04b-204">This section applies only to users who were created and enabled for an on-premises deployment and then moved from an on-premises deployment to online.</span></span> 
  
- <span data-ttu-id="1a04b-205">Exécuter les applets de commande suivantes pour atteindre un utilisateur à partir de Skype pour Business Online sur site, remplacez la valeur pour les paramètres **d’identité** et de la **cible** de valeurs correctes pour votre environnement :</span><span class="sxs-lookup"><span data-stu-id="1a04b-205">Run the following cmdlets to move a user from Skype for Business Online back to on-premises, replacing the value for the **Identity** and **Target** parameters to correct values for your environment:</span></span>
    
  ```
  $cred=Get-Credential
  ```

  ```
  Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
  ```

<span data-ttu-id="1a04b-206">Le format de l’URL spécifiée pour le paramètre **HostedMigrationOverrideUrl** doit être une URL vers le pool dans lequel le service hébergé de Migration est en cours d’exécution, dans le format suivant :</span><span class="sxs-lookup"><span data-stu-id="1a04b-206">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>
  
 <span data-ttu-id="1a04b-207">_Https://\<nom de domaine complet du Pool\>/HostedMigration/hostedmigrationService.svc_.</span><span class="sxs-lookup"><span data-stu-id="1a04b-207">_Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span> <span data-ttu-id="1a04b-208">Vous pouvez déterminer l’URL du service de migration hébergée en affichant l’URL du Panneau de configuration Lync Online correspondant à votre compte client Office 365.</span><span class="sxs-lookup"><span data-stu-id="1a04b-208">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>
  
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="1a04b-209">Pour déterminer l’URL du service de migration hébergée de votre client Office 365</span><span class="sxs-lookup"><span data-stu-id="1a04b-209">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="1a04b-210">Connectez-vous à votre client Office 365 en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="1a04b-210">Login to your Office 365 tenant as an administrator.</span></span>
    
2. <span data-ttu-id="1a04b-211">Ouvrez le **Centre d’administration Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="1a04b-211">Open the **Skype for Business admin center**.</span></span>
    
3. <span data-ttu-id="1a04b-212">Une fois le **Centre d’administration Skype Entreprise** affiché, sélectionnez l’URL et copiez-la dans la barre d’adresse jusqu’à **lync.com**. L’URL doit se présenter comme dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="1a04b-212">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. <span data-ttu-id="1a04b-213">Dans l’URL, remplacez **webdir** par **admin** pour obtenir le résultat suivant :</span><span class="sxs-lookup"><span data-stu-id="1a04b-213">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span> 
    
     `https://admin0a.online.lync.com`
    
5. <span data-ttu-id="1a04b-214">Ajoutez la chaîne ci-dessous à l’URL : **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="1a04b-214">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="1a04b-215">L’URL résultante, qui est la valeur de la **HostedMigrationOverrideUrl**, doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="1a04b-215">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    


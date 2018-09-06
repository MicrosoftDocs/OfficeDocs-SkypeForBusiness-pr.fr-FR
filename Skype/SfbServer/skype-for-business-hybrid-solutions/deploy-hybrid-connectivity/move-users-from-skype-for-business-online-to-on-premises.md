---
title: Déplacer les utilisateurs de Skype pour Business en ligne et en local
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/19/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 55733bb5-6742-4daf-8db5-1c5df86f4cea
description: 'Résumé : Découvrez comment déplacer les comptes d’utilisateurs en ligne et localement dans Skype pour Business Server.'
ms.openlocfilehash: 655c037fc2299044aa3799d06e0d231784248d7e
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23260145"
---
# <a name="move-users-from-skype-for-business-online-to-on-premises"></a><span data-ttu-id="3f706-103">Déplacer les utilisateurs de Skype pour Business en ligne et en local</span><span class="sxs-lookup"><span data-stu-id="3f706-103">Move users from Skype for Business Online to on premises</span></span>

<span data-ttu-id="3f706-104">**Résumé :** Découvrez comment déplacer les comptes d’utilisateurs en ligne et localement dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="3f706-104">**Summary:** Learn how to move user accounts from online to on premises in Skype for Business Server.</span></span>

<span data-ttu-id="3f706-105">Vous devrez peut-être déplacer des comptes d’utilisateurs d’en ligne et sur site pour vous assurer que les utilisateurs hébergement en ligne et dans les locaux sont accessibles à l’autre.</span><span class="sxs-lookup"><span data-stu-id="3f706-105">You might need to move user accounts from online to on premises to ensure that users homed online and on premises are discoverable to one another.</span></span> <span data-ttu-id="3f706-106">Pour être accessibles à l’autre, tous les utilisateurs doivent avoir une présence dans Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="3f706-106">To be discoverable to one another, all users must have a presence in the on-premises Active Directory.</span></span> <span data-ttu-id="3f706-107">Pour plus d’informations, voir [planification de la connectivité hybride entre Skype pour Business Server et Skype pour Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="3f706-107">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span></span> <span data-ttu-id="3f706-108">Vous pouvez souhaiter déplacer des utilisateurs en ligne sur site, par exemple, si :</span><span class="sxs-lookup"><span data-stu-id="3f706-108">You might want to move online users to on premises, for example, if:</span></span>

- <span data-ttu-id="3f706-109">Vous devez les nouveaux utilisateurs qui doivent être créés dans les locaux et ensuite vers le nuage.</span><span class="sxs-lookup"><span data-stu-id="3f706-109">You have new users who need to be created on premises and then moved to the cloud.</span></span>

- <span data-ttu-id="3f706-110">Votre organisation a déployé Skype pour Business Online avant de déployer Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="3f706-110">Your organization deployed Skype for Business Online before it deployed Skype for Business Server.</span></span> <span data-ttu-id="3f706-111">Par conséquent, vous avez des utilisateurs qui ont été créés dans le nuage tout d’abord et maintenant devez être déplacés vers localement avant de les déplacer vers Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="3f706-111">Therefore, you have users who were created in the cloud first, and now need to be moved to on premises before they are move to Skype for Business Online.</span></span>

<span data-ttu-id="3f706-112">Cette rubrique décrit les deux scénarios :</span><span class="sxs-lookup"><span data-stu-id="3f706-112">This topic describes two scenarios:</span></span>

- [<span data-ttu-id="3f706-113">Déplacer des utilisateurs en ligne, qui ont été initialement en ligne — à local</span><span class="sxs-lookup"><span data-stu-id="3f706-113">Move online users—who were originally online—to on premises</span></span>](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonline)

- [<span data-ttu-id="3f706-114">Déplacer des utilisateurs en ligne (ceux qui ont été initialement sur site) pour sur site</span><span class="sxs-lookup"><span data-stu-id="3f706-114">Move online users (who were originally on premises) to on premises</span></span>](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonprem)

## <a name="move-online-userswho-were-originally-onlineto-on-premises"></a><span data-ttu-id="3f706-115">Déplacer des utilisateurs en ligne, qui ont été initialement en ligne — à local</span><span class="sxs-lookup"><span data-stu-id="3f706-115">Move online users—who were originally online—to on premises</span></span>
<span data-ttu-id="3f706-116"><a name="BKMK_originallyonline"> </a></span><span class="sxs-lookup"><span data-stu-id="3f706-116"></span></span>

<span data-ttu-id="3f706-117">Cette section s’applique uniquement aux utilisateurs qui ont été créés et activés en ligne, mais qui n’ont pas d’un compte dans l’environnement local sur Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3f706-117">This section applies only to users who were created and enabled online, but who do not have an account in the on premises Active Directory.</span></span>

<span data-ttu-id="3f706-118">Avant de commencer à déplacer les utilisateurs en ligne vers votre environnement local, vérifiez que toutes les conditions suivantes sont vraies :</span><span class="sxs-lookup"><span data-stu-id="3f706-118">Before you start moving online users to your on-premises environment, check that all of the following are true:</span></span>

- <span data-ttu-id="3f706-119">Votre environnement local doit être déployé et validé complètement.</span><span class="sxs-lookup"><span data-stu-id="3f706-119">Your on-premises environment must be fully deployed and validated.</span></span> <span data-ttu-id="3f706-120">Pour plus d’informations, voir [déploiement de Lync Server 2013](https://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) ou [Déployer de Skype pour Business Server 2015](../../deploy/deploy.md), selon la version que vous utilisez le localement.</span><span class="sxs-lookup"><span data-stu-id="3f706-120">For more information, see [Deploying Lync Server 2013](https://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) or [Deploy Skype for Business Server 2015](../../deploy/deploy.md), depending on which version you are using on premises.</span></span>

- <span data-ttu-id="3f706-121">Votre client en ligne doit être configuré pour l’accès à distance PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f706-121">Your online tenant must be configured for remote PowerShell access.</span></span>

    <span data-ttu-id="3f706-122">Pour ce faire, installez d’abord la Skype pour module connecteur Business en ligne pour Windows PowerShell, vous pouvez obtenir ici : [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="3f706-122">To do this, first install the Skype for Business Online connector module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>

    <span data-ttu-id="3f706-123">Après avoir installé le module, vous pouvez établir une session à distance en tapant les cmdlets suivantes dans le Skype pour Business Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="3f706-123">After you install the module, you can establish a remote session by typing the following cmdlets in the Skype for Business Server Management Shell:</span></span>

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

    <span data-ttu-id="3f706-124">Pour plus d’informations sur l’utilisation de PowerShell avec Skype pour Business Online, voir [configurer votre ordinateur pour Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="3f706-124">For more information about using PowerShell with Skype for Business Online, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span></span>

- <span data-ttu-id="3f706-125">Votre client en ligne doit être configuré pour un espace d’adressage SIP partagé.</span><span class="sxs-lookup"><span data-stu-id="3f706-125">Your online tenant must be configured for a shared SIP address space.</span></span> <span data-ttu-id="3f706-126">Pour ce faire, commencez par démarrer une session Powershell distante avec Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="3f706-126">To do this, first start a remote Powershell session with Skype for Business Online.</span></span> <span data-ttu-id="3f706-127">Ensuite, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="3f706-127">Then run the following cmdlet:</span></span>

  ```
  Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
  ```

    > [!NOTE]
    > <span data-ttu-id="3f706-128">L’attribut SharedSipAddressSpace doit rester « True », jusqu'à ce que le déplacement vers online est final et aucun utilisateur reste dans les locaux.</span><span class="sxs-lookup"><span data-stu-id="3f706-128">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on premises.</span></span>

<span data-ttu-id="3f706-129">Une fois que vous avez terminé ces étapes, vous pouvez migrer les comptes d’utilisateurs comme décrit dans la procédure suivante :</span><span class="sxs-lookup"><span data-stu-id="3f706-129">After you've finished these steps, you can migrate user accounts as described in the following procedure:</span></span>

### <a name="move-user-accounts-originally-enabled-online-to-an-on-premises-deployment"></a><span data-ttu-id="3f706-130">Déplacer les comptes d’utilisateur à l’origine activés en ligne à un déploiement sur site</span><span class="sxs-lookup"><span data-stu-id="3f706-130">Move user accounts originally enabled online to an on-premises deployment</span></span>

1. <span data-ttu-id="3f706-131">Vérifiez tout d’abord que votre organisation est configurée pour l’environnement hybride, dont les outils Azure Active Directory Connect et de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="3f706-131">First, make sure that your organization is configured for hybrid, including Azure Active Directory Connect and sync tools.</span></span> <span data-ttu-id="3f706-132">Pour plus d’informations, voir [planification de la connectivité hybride entre Skype pour Business Server et Skype pour Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="3f706-132">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span></span>

  - <span data-ttu-id="3f706-133">Dans votre déploiement sur site, dans la Skype pour Business Server Management Shell, tapez les applets de commande suivantes pour créer le fournisseur d’hébergement pour Skype pour Business en ligne.</span><span class="sxs-lookup"><span data-stu-id="3f706-133">On your on-premises deployment, in the Skype for Business Server Management Shell, type the following cmdlets to create the hosting provider for Skype for Business Online.</span></span> <span data-ttu-id="3f706-134">Vous pouvez utiliser les valeurs de votre choix pour les paramètres Identité et Nom.</span><span class="sxs-lookup"><span data-stu-id="3f706-134">You can use whatever value you want for the Identity and Name parameters.</span></span>

  ```
  Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
  ```

  ```
  New-CsHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
  ```

2. <span data-ttu-id="3f706-135">Vérifiez que sur les serveurs de périphérie locale, vous avez la chaîne de certificats qui permet la connexion à Skype pour Business Online, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="3f706-135">Confirm that on your on-premises Edge Servers, you have the certificate chain that enables connection to Skype for Business Online, as shown in the following table.</span></span> <span data-ttu-id="3f706-136">Vous pouvez télécharger cette chaîne ici : [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).</span><span class="sxs-lookup"><span data-stu-id="3f706-136">You can download this chain here: [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).</span></span>

|<span data-ttu-id="3f706-137">**Certificat**</span><span class="sxs-lookup"><span data-stu-id="3f706-137">**Certificate**</span></span>|<span data-ttu-id="3f706-138">**Magasin de certificats**</span><span class="sxs-lookup"><span data-stu-id="3f706-138">**Certificate Store**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3f706-139">Certificat racine de CyberTrust Baltimore</span><span class="sxs-lookup"><span data-stu-id="3f706-139">Baltimore CyberTrust Root</span></span>  <br/> |<span data-ttu-id="3f706-140">Autorité de certification racine de confiance</span><span class="sxs-lookup"><span data-stu-id="3f706-140">Trusted Root CA</span></span>  <br/> |
|<span data-ttu-id="3f706-141">Microsoft Internet Authority (Nouveau certificat de l’autorité de certification racine)</span><span class="sxs-lookup"><span data-stu-id="3f706-141">Microsoft Internet Authority (New CA certificate)</span></span>  <br/> |<span data-ttu-id="3f706-142">Autorité de certification intermédiaire</span><span class="sxs-lookup"><span data-stu-id="3f706-142">Intermediate CA</span></span>  <br/> |
|<span data-ttu-id="3f706-143">MSIT Machine Auth CA2 (Nouvelle autorité de certification émettrice CA2)</span><span class="sxs-lookup"><span data-stu-id="3f706-143">MSIT Machine Auth CA2 (New Issuing CA2)</span></span>  <br/> |<span data-ttu-id="3f706-144">Autorité de certification intermédiaire</span><span class="sxs-lookup"><span data-stu-id="3f706-144">Intermediate CA</span></span>  <br/> |

3. <span data-ttu-id="3f706-145">Dans Active Directory sur site, activez les comptes d’utilisateur affecté pour Skype pour Business Server 2015 localement.</span><span class="sxs-lookup"><span data-stu-id="3f706-145">In your on-premises Active Directory, enable the affected user accounts for Skype for Business Server 2015 on premises.</span></span> <span data-ttu-id="3f706-146">Pour un utilisateur individuel, tapez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="3f706-146">You can do this for an individual user by typing the following cmdlet:</span></span>

  ```
  Enable-CsUser
-Identity "username "
-SipAddress "sip: username @contoso.com"
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

    <span data-ttu-id="3f706-147">Vous pouvez également créer un script qui lit les noms d’utilisateur dans un fichier et les transmet comme informations à l’applet de commande Enable-CsUser :</span><span class="sxs-lookup"><span data-stu-id="3f706-147">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>

  ```
  Enable-CsUser
-Identity $Identity
-SipAddress $SipAddress
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

4. <span data-ttu-id="3f706-148">Synchroniser les utilisateurs en ligne avec les mise à jour les utilisateurs locaux.</span><span class="sxs-lookup"><span data-stu-id="3f706-148">Synchronize the online users with the updated on-premises users.</span></span> <span data-ttu-id="3f706-149">Pour plus d’informations, voir [Outils de l’intégration d’annuaire](https://go.microsoft.com/fwlink/p/?LinkId=530320).</span><span class="sxs-lookup"><span data-stu-id="3f706-149">For more information, see [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?LinkId=530320).</span></span>

5. <span data-ttu-id="3f706-150">Mettre à jour les enregistrements DNS suivants pour diriger tout le trafic SIP à votre déploiement sur site :</span><span class="sxs-lookup"><span data-stu-id="3f706-150">Update the following DNS records to direct all SIP traffic to your on-premises deployment:</span></span>

  - <span data-ttu-id="3f706-151">Mettez à jour **lyncdiscover.contoso.com**  Un enregistrement pour pointer vers le nom de domaine complet (FQDN) du serveur proxy inverse local.</span><span class="sxs-lookup"><span data-stu-id="3f706-151">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>

  - <span data-ttu-id="3f706-152">Mise à jour la \*\* *_sip* . _tls.contoso.com\*\* enregistrement SRV pour résoudre l’adresse IP ou l’adresse IP publique du service Edge d’accès de Lync sur site.</span><span class="sxs-lookup"><span data-stu-id="3f706-152">Update the ***_sip*  ._tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>

  - <span data-ttu-id="3f706-153">Mise à jour la \*\* *_sipfederationtls* . _tcp.contoso.com\*\* enregistrement SRV pour résoudre l’adresse IP ou l’adresse IP publique du service Edge d’accès de Skype pour Business Server 2015 locale.</span><span class="sxs-lookup"><span data-stu-id="3f706-153">Update the ***_sipfederationtls*  ._tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Skype for Business Server 2015 on-premises.</span></span>

  - <span data-ttu-id="3f706-154">Si votre organisation utilise fractionnées DNS (parfois appelée « DNS split-brain »), assurez-vous que les utilisateurs de la résolution de noms par le biais de la zone DNS interne sont dirigés vers le Pool frontal.</span><span class="sxs-lookup"><span data-stu-id="3f706-154">If your organization uses split DNS (sometimes called "split-brain DNS"), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6. <span data-ttu-id="3f706-155">Type de la `Get-CsUser` applet de commande pour vérifier certaines propriétés sur les utilisateurs que vous prévoyez de déplacer.</span><span class="sxs-lookup"><span data-stu-id="3f706-155">Type the  `Get-CsUser` cmdlet to check some properties about the users you'll be moving.</span></span> <span data-ttu-id="3f706-156">Vérifiez que HostingProviderProxyFQDN possède la valeur `"sipfed.online.lync.com"` et que les adresses SIP (Session Initiation Protocol) sont définies correctement.</span><span class="sxs-lookup"><span data-stu-id="3f706-156">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7. <span data-ttu-id="3f706-157">Déplacer des utilisateurs en ligne en local.</span><span class="sxs-lookup"><span data-stu-id="3f706-157">Move online users to on premises.</span></span>

    <span data-ttu-id="3f706-158">Pour déplacer un seul utilisateur, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="3f706-158">To move a single user, type this:</span></span>

  ```
  $cred = Get-Credential
  Move-CsUser -Identity <username>@contoso.com  -Target "<fe-pool>.contoso.com " -Credential $cred -HostedMigrationOverrideURL <URL>
  ```

    <span data-ttu-id="3f706-159">Vous pouvez déplacer plusieurs utilisateurs à l’aide de l’applet de commande **Get-CsUSer** avec le paramètre - Filter pour sélectionner les utilisateurs avec une propriété spécifique.</span><span class="sxs-lookup"><span data-stu-id="3f706-159">You can move multiple users by using the **Get-CsUSer** cmdlet with the -Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="3f706-160">Par exemple, vous pouvez sélectionner tous les utilisateurs en ligne en filtrant les {fournisseur d’hébergement - eq « sipfed.online.lync.om »}.</span><span class="sxs-lookup"><span data-stu-id="3f706-160">For example, you could select all Online users by filtering for {Hosting Provider -eq "sipfed.online.lync.om"}.</span></span> <span data-ttu-id="3f706-161">Vous pouvez ensuite canaliser renvoyées aux utilisateurs de l’applet de commande **Move-CsUSer** , comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="3f706-161">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>

  ```
  Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com " -Credential $creds -HostedMigrationOverrideURL <URL>
  ```

    <span data-ttu-id="3f706-162">Le format de l’URL spécifiée pour le paramètre **HostedMigrationOverrideUrl** doit être une URL vers le pool dans lequel s’exécute le service de Migration hébergé, dans le format suivant : _Https://\<nom complet du Pool\>/HostedMigration/ hostedmigrationService.svc_.</span><span class="sxs-lookup"><span data-stu-id="3f706-162">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: _Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span>

    <span data-ttu-id="3f706-163">Vous pouvez déterminer l’URL du service de migration hébergée en affichant l’URL du Panneau de configuration Lync Online correspondant à votre compte client Office 365.</span><span class="sxs-lookup"><span data-stu-id="3f706-163">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="3f706-164">Pour déterminer l’URL du service de migration hébergée de votre client Office 365</span><span class="sxs-lookup"><span data-stu-id="3f706-164">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="3f706-165">Connectez-vous à votre client Office 365 en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="3f706-165">Login to your Office 365 tenant as an administrator.</span></span>

2. <span data-ttu-id="3f706-166">Ouvrez le **Centre d’administration Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="3f706-166">Open the **Skype for Business admin center**.</span></span>

3. <span data-ttu-id="3f706-p112">Une fois le **Centre d’administration Skype Entreprise** affiché, sélectionnez l’URL et copiez-la dans la barre d’adresse jusqu’à **lync.com**. L’URL doit se présenter comme dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="3f706-p112">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>

     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`

4. <span data-ttu-id="3f706-169">Dans l’URL, remplacez **webdir** par **admin** pour obtenir le résultat suivant :</span><span class="sxs-lookup"><span data-stu-id="3f706-169">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>

     `https://admin0a.online.lync.com`

5. <span data-ttu-id="3f706-170">Ajoutez la chaîne ci-dessous à l’URL : **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="3f706-170">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>

    <span data-ttu-id="3f706-171">L’URL qui en résulte, qui est la valeur de la **HostedMigrationOverrideUrl**, doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="3f706-171">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>

     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

    > [!NOTE]
    > <span data-ttu-id="3f706-172">La taille maximale par défaut pour les fichiers journaux de transaction de la base de données rtcxds est de 16 Go.</span><span class="sxs-lookup"><span data-stu-id="3f706-172">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="3f706-173">Cela ne peut pas être suffisamment importante si vous déplacez un grand nombre d’utilisateurs à la fois, en particulier si vous avez activé de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="3f706-173">This might not be big enough if you're moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="3f706-174">Pour résoudre ce problème, vous pouvez augmenter la taille du fichier ou sauvegarder régulièrement les fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="3f706-174">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="3f706-175">Pour plus d’informations, voir [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725).</span><span class="sxs-lookup"><span data-stu-id="3f706-175">For more information, see [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725).</span></span>

8. <span data-ttu-id="3f706-176">Il s’agit d’une étape facultative.</span><span class="sxs-lookup"><span data-stu-id="3f706-176">This is an optional step.</span></span> <span data-ttu-id="3f706-177">Pour une intégration à Exchange 2013 Online, vous devez utiliser un autre fournisseur d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="3f706-177">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="3f706-178">Pour plus d’informations, voir [configurer l’intégration entre locale Skype pour Business Server 2015 et Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="3f706-178">For details, see [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).</span></span>

9. <span data-ttu-id="3f706-p115">Les utilisateurs sont maintenant déplacés. Pour vérifier qu’un utilisateur possède des valeurs correctes pour les attributs affichés dans le tableau ci-dessous, tapez cette applet de commande :</span><span class="sxs-lookup"><span data-stu-id="3f706-p115">The users are now moved. To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>

  ```
  Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
  ```

|<span data-ttu-id="3f706-181">**Attribut Active Directory**</span><span class="sxs-lookup"><span data-stu-id="3f706-181">**Active Directory attribute**</span></span>|<span data-ttu-id="3f706-182">**Nom Attribut**</span><span class="sxs-lookup"><span data-stu-id="3f706-182">**Attribute name**</span></span>|<span data-ttu-id="3f706-183">**Valeur correcte pour l’utilisateur Online**</span><span class="sxs-lookup"><span data-stu-id="3f706-183">**Correct value for Online user**</span></span>|<span data-ttu-id="3f706-184">**Valeur correcte pour les utilisateurs locaux**</span><span class="sxs-lookup"><span data-stu-id="3f706-184">**Correct value for on-premises users**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3f706-185">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="3f706-185">msRTCSIP-DeploymentLocator</span></span>  <br/> |<span data-ttu-id="3f706-186">HostingProvider</span><span class="sxs-lookup"><span data-stu-id="3f706-186">HostingProvider</span></span>  <br/> |<span data-ttu-id="3f706-187">sipfed.Online.Lync.com</span><span class="sxs-lookup"><span data-stu-id="3f706-187">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="3f706-188">SRV :</span><span class="sxs-lookup"><span data-stu-id="3f706-188">SRV:</span></span>  <br/> |
|<span data-ttu-id="3f706-189">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="3f706-189">msRTCSIP-PrimaryUserAddress</span></span>  <br/> |<span data-ttu-id="3f706-190">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="3f706-190">SIPAddress</span></span>  <br/> |<span data-ttu-id="3f706-191">SIP:username@contoso.com</span><span class="sxs-lookup"><span data-stu-id="3f706-191">sip:userName@contoso.com</span></span>  <br/> |<span data-ttu-id="3f706-192">SIP:username@contoso.com</span><span class="sxs-lookup"><span data-stu-id="3f706-192">sip:userName@contoso.com</span></span>  <br/> |
|<span data-ttu-id="3f706-193">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="3f706-193">msRTCSIP-UserEnabled</span></span>  <br/> |<span data-ttu-id="3f706-194">Activé</span><span class="sxs-lookup"><span data-stu-id="3f706-194">Enabled</span></span>  <br/> |<span data-ttu-id="3f706-195">True</span><span class="sxs-lookup"><span data-stu-id="3f706-195">True</span></span>  <br/> |<span data-ttu-id="3f706-196">True</span><span class="sxs-lookup"><span data-stu-id="3f706-196">True</span></span>  <br/> |

10. <span data-ttu-id="3f706-p116">Chaque utilisateur déplacé devra se déconnecter, puis se reconnecter. Lorsque l’utilisateur se reconnecte, il doit vérifier ses listes de contacts et ajouter des contacts, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="3f706-p116">Each user who has been moved will need to log out, then log back in. When they log in they should verify their contact lists, and add contacts if needed.</span></span>

    <span data-ttu-id="3f706-p117">Notez que les réunions planifiées ne sont pas migrées de la version en ligne vers la version locale. Les utilisateurs doivent replanifier ces réunions après les avoir déplacées.</span><span class="sxs-lookup"><span data-stu-id="3f706-p117">Note that scheduled meetings are not migrated from online to on-premises. Users will need to reschedule these meetings after being moved.</span></span>

    <span data-ttu-id="3f706-201">Une fois que les enregistrements DNS sont mises à jour et tous les utilisateurs sont dirigés vers le site, l’attribut HostingProvider dirige l’utilisateur à utiliser les enregistrements SRV ou les diriger vers le fournisseur en ligne « sipfed.online.lync.com ».</span><span class="sxs-lookup"><span data-stu-id="3f706-201">After the DNS records are updated and all users are directed to On-premises, the HostingProvider attribute directs the user to either use SRV records or direct them to the Online provider "sipfed.online.lync.com."</span></span>

## <a name="move-online-users-who-were-originally-on-premises-to-on-premises"></a><span data-ttu-id="3f706-202">Déplacer des utilisateurs en ligne (ceux qui ont été initialement sur site) pour sur site</span><span class="sxs-lookup"><span data-stu-id="3f706-202">Move online users (who were originally on premises) to on premises</span></span>
<span data-ttu-id="3f706-203"><a name="BKMK_originallyonprem"> </a></span><span class="sxs-lookup"><span data-stu-id="3f706-203"></span></span>

<span data-ttu-id="3f706-204">Cette section s’applique uniquement aux utilisateurs qui ont été créés et activés pour un déploiement sur site et ensuite vers à partir d’un déploiement sur site en ligne.</span><span class="sxs-lookup"><span data-stu-id="3f706-204">This section applies only to users who were created and enabled for an on-premises deployment and then moved from an on-premises deployment to online.</span></span>

- <span data-ttu-id="3f706-205">Exécutez les applets de commande suivante pour déplacer un utilisateur de Skype pour Business Online retour vers le site, en remplaçant la valeur pour les paramètres **Identity** et **cible** pour corriger les valeurs pour votre environnement :</span><span class="sxs-lookup"><span data-stu-id="3f706-205">Run the following cmdlets to move a user from Skype for Business Online back to on-premises, replacing the value for the **Identity** and **Target** parameters to correct values for your environment:</span></span>

  ```
  $cred=Get-Credential
  ```

  ```
  Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
  ```

<span data-ttu-id="3f706-206">Le format de l’URL spécifiée pour le paramètre **HostedMigrationOverrideUrl** doit être une URL vers le pool dans lequel s’exécute le service de Migration hébergé, dans le format suivant :</span><span class="sxs-lookup"><span data-stu-id="3f706-206">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

 <span data-ttu-id="3f706-207">_Https://\<nom de domaine complet du Pool\>/HostedMigration/hostedmigrationService.svc_.</span><span class="sxs-lookup"><span data-stu-id="3f706-207">_Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span> <span data-ttu-id="3f706-208">Vous pouvez déterminer l’URL du service de migration hébergée en affichant l’URL du Panneau de configuration Lync Online correspondant à votre compte client Office 365.</span><span class="sxs-lookup"><span data-stu-id="3f706-208">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="3f706-209">Pour déterminer l’URL du service de migration hébergée de votre client Office 365</span><span class="sxs-lookup"><span data-stu-id="3f706-209">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="3f706-210">Connectez-vous à votre client Office 365 en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="3f706-210">Login to your Office 365 tenant as an administrator.</span></span>

2. <span data-ttu-id="3f706-211">Ouvrez le **Centre d’administration Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="3f706-211">Open the **Skype for Business admin center**.</span></span>

3. <span data-ttu-id="3f706-p119">Une fois le **Centre d’administration Skype Entreprise** affiché, sélectionnez l’URL et copiez-la dans la barre d’adresse jusqu’à **lync.com**. L’URL doit se présenter comme dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="3f706-p119">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>

     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`

4. <span data-ttu-id="3f706-214">Dans l’URL, remplacez **webdir** par **admin** pour obtenir le résultat suivant :</span><span class="sxs-lookup"><span data-stu-id="3f706-214">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>

     `https://admin0a.online.lync.com`

5. <span data-ttu-id="3f706-215">Ajoutez la chaîne ci-dessous à l’URL : **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="3f706-215">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>

    <span data-ttu-id="3f706-216">L’URL qui en résulte, qui est la valeur de la **HostedMigrationOverrideUrl**, doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="3f706-216">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>

     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`



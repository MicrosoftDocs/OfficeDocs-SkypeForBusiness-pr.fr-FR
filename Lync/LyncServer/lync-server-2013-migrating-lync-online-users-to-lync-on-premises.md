---
title: 'Lync Server 2013 : migration des utilisateurs Lync Online vers Lync local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e76f8c0c40e13d0d9c6b19dee118e1513390d7e7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="36c72-102">Migration des utilisateurs Lync Online vers Lync local dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36c72-102">Migrating Lync Online users to Lync on-premises in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36c72-103">_**Dernière modification de la rubrique :** 2015-11-13_</span><span class="sxs-lookup"><span data-stu-id="36c72-103">_**Topic Last Modified:** 2015-11-13_</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="36c72-104">Ces étapes sont nécessaires uniquement pour la migration des comptes d’utilisateurs qui ont été activés pour Lync dans Lync Online avant de déployer Lync en local.</span><span class="sxs-lookup"><span data-stu-id="36c72-104">These steps are necessary only for migrating user accounts that were originally enabled for Lync in Lync Online, before you deployed Lync on-premises.</span></span> <span data-ttu-id="36c72-105">Pour déplacer des utilisateurs qui ont été activés pour Lync local, puis transférés plus tard vers Lync Online, voir <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">administration des utilisateurs dans un déploiement 2013 Lync Server</A>.</span><span class="sxs-lookup"><span data-stu-id="36c72-105">To move users who were originally enabled for Lync on-premises, then later moved to Lync Online, see <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</A>.</span></span><BR><span data-ttu-id="36c72-106">De plus, tous les utilisateurs en cours de déplacement doivent disposer de comptes dans l’instance locale d’Active Directory.</span><span class="sxs-lookup"><span data-stu-id="36c72-106">Additionally, all users being moved must have accounts in the on-premises Active Directory.</span></span>



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a><span data-ttu-id="36c72-107">Migration des comptes d’utilisateurs activés dans Lync Online vers Lync local</span><span class="sxs-lookup"><span data-stu-id="36c72-107">Migrating User Accounts Originally Enabled in Lync Online to Lync On-Premises</span></span>

1.  <span data-ttu-id="36c72-108">Tout d’abord, assurez-vous que votre organisation est configurée pour l’environnement hybride.</span><span class="sxs-lookup"><span data-stu-id="36c72-108">First, make sure that your organization is configured for hybrid.</span></span>
    
      - <span data-ttu-id="36c72-109">Installez l’outil de synchronisation Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="36c72-109">Install the Azure Active Directory Sync Tool.</span></span> <span data-ttu-id="36c72-110">Pour plus d’informations, <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>reportez-vous à.</span><span class="sxs-lookup"><span data-stu-id="36c72-110">For more information, see <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span></span>
    
      - <span data-ttu-id="36c72-111">Pour permettre à vos utilisateurs d’utiliser l’authentification unique pour Lync Online, installez les services ADFS ( <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>Active Directory Federation Services).</span><span class="sxs-lookup"><span data-stu-id="36c72-111">To enable your users to use single sign-on for Lync Online, install Active Directory Federation Services <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.</span></span>
    
      - <span data-ttu-id="36c72-112">Sur votre déploiement local, dans Lync Server Management Shell, entrez les applets de commande suivantes pour créer le fournisseur d’hébergement pour Lync Online :</span><span class="sxs-lookup"><span data-stu-id="36c72-112">On your on-premises deployment, in Lync Server Management Shell, type the following cmdlets to create the hosting provider for Lync Online:</span></span>
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  <span data-ttu-id="36c72-113">Vérifiez que, sur votre serveur Edge local, vous disposez de la chaîne de certificats qui permet de se connecter à Lync Online, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="36c72-113">Confirm that, on your on-premises Edge Servers, you have the certificate chain that enables connection to Lync Online, as shown in the following table.</span></span> <span data-ttu-id="36c72-114">Vous pouvez télécharger cette chaîne à l’adresse suivante :https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span><span class="sxs-lookup"><span data-stu-id="36c72-114">You can download this chain here: https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span></span>


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="36c72-115">Certificat</span><span class="sxs-lookup"><span data-stu-id="36c72-115">Certificate</span></span></th>
    <th><span data-ttu-id="36c72-116">Magasin de certificats</span><span class="sxs-lookup"><span data-stu-id="36c72-116">Certificate Store</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="36c72-117">Certificat racine de CyberTrust Baltimore</span><span class="sxs-lookup"><span data-stu-id="36c72-117">Baltimore CyberTrust Root</span></span></p></td>
    <td><p><span data-ttu-id="36c72-118">Autorité de certification racine de confiance</span><span class="sxs-lookup"><span data-stu-id="36c72-118">Trusted Root CA</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="36c72-119">Microsoft Internet Authority (Nouveau certificat de l’autorité de certification racine)</span><span class="sxs-lookup"><span data-stu-id="36c72-119">Microsoft Internet Authority (New CA certificate)</span></span></p></td>
    <td><p><span data-ttu-id="36c72-120">Autorité de certification intermédiaire</span><span class="sxs-lookup"><span data-stu-id="36c72-120">Intermediate CA</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="36c72-121">MSIT Machine Auth CA2 (Nouvelle autorité de certification émettrice CA2)</span><span class="sxs-lookup"><span data-stu-id="36c72-121">MSIT Machine Auth CA2 (New Issuing CA2)</span></span></p></td>
    <td><p><span data-ttu-id="36c72-122">Autorité de certification intermédiaire</span><span class="sxs-lookup"><span data-stu-id="36c72-122">Intermediate CA</span></span></p></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="36c72-123">Dans votre Active Directory local, activez les comptes d’utilisateurs concernés pour Lync local.</span><span class="sxs-lookup"><span data-stu-id="36c72-123">In your on-premises Active Directory, enable the affected user accounts for Lync on-premises.</span></span> <span data-ttu-id="36c72-124">Pour un utilisateur individuel, tapez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="36c72-124">You can do this for an individual user by typing the following cmdlet:</span></span>
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    <span data-ttu-id="36c72-125">Vous pouvez également créer un script qui lit les noms d’utilisateur dans un fichier et les transmet comme informations à l’applet de commande Enable-CsUser :</span><span class="sxs-lookup"><span data-stu-id="36c72-125">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  <span data-ttu-id="36c72-126">Exécutez DirSync pour synchroniser les utilisateurs Lync Online avec les utilisateurs Lync locaux mis à jour.</span><span class="sxs-lookup"><span data-stu-id="36c72-126">Run DirSync to sync the Lync Online users with the updated Lync on-premises users.</span></span>

5.  <span data-ttu-id="36c72-127">Mettez à jour les enregistrements DNS pour acheminer l’ensemble du trafic SIP vers Lync local :</span><span class="sxs-lookup"><span data-stu-id="36c72-127">Update some DNS records to direct all SIP traffic to Lync on-premises:</span></span>
    
      - <span data-ttu-id="36c72-128">Mettez à jour **lyncdiscover.contoso.com**  Un enregistrement pour pointer vers le nom de domaine complet (FQDN) du serveur proxy inverse local.</span><span class="sxs-lookup"><span data-stu-id="36c72-128">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>
    
      - <span data-ttu-id="36c72-129">Mettez à jour le \*\**\_SIP\_ *. tls.contoso.com** SRV enregistrement pour la résolution vers l’adresse IP ou VIP publique du service Edge d’accès de Lync local.</span><span class="sxs-lookup"><span data-stu-id="36c72-129">Update the \***\_sip\*.\_tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="36c72-130">Mettez à jour \*\**\_sipfederationtls *\_ . tcp.contoso.com** SRV enregistrement pour la résolution vers l’adresse IP ou VIP publique du service Edge d’accès de Lync local.</span><span class="sxs-lookup"><span data-stu-id="36c72-130">Update the \***\_sipfederationtls\*.\_tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="36c72-131">Si votre organisation utilise un « DNS split » (également appelé « DNS split-brain »), vérifiez que les utilisateurs qui résolvent des noms par le biais de la zone DNS interne sont dirigés vers le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="36c72-131">If your organization uses split DNS (sometimes called “split-brain DNS”), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6.  <span data-ttu-id="36c72-132">Tapez l' `Get-CsUser` applet de recherche pour vérifier certaines propriétés des utilisateurs que vous allez déplacer.</span><span class="sxs-lookup"><span data-stu-id="36c72-132">Type the `Get-CsUser` cmdlet to check some properties about the users you’ll be moving.</span></span> <span data-ttu-id="36c72-133">Vous voulez vous assurer que HostingProviderProxyFQDN est défini sur `"sipfed.online.lync.com"` et que les adresses SIP sont correctement définies.</span><span class="sxs-lookup"><span data-stu-id="36c72-133">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7.  <span data-ttu-id="36c72-134">Déplacez les utilisateurs Lync Online vers Lync local.</span><span class="sxs-lookup"><span data-stu-id="36c72-134">Move Lync Online users to Lync on-premises.</span></span>
    
    <span data-ttu-id="36c72-135">Pour déplacer un seul utilisateur, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="36c72-135">To move a single user, type this:</span></span>
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    <span data-ttu-id="36c72-136">Vous pouvez déplacer plusieurs utilisateurs à l’aide de l’applet de commande **Get-CsUSer**  avec le paramètre –Filter pour sélectionner les utilisateurs comportant une propriété spécifique.</span><span class="sxs-lookup"><span data-stu-id="36c72-136">You can move multiple users by using the **Get-CsUSer** cmdlet with the –Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="36c72-137">Par exemple, vous pouvez sélectionner tous les utilisateurs de Lync Online en filtrant pour {Hosting Provider-EQ "sipfed.online.lync.om"}.</span><span class="sxs-lookup"><span data-stu-id="36c72-137">For example, you could select all Lync Online users by filtering for {Hosting Provider –eq “sipfed.online.lync.om”}.</span></span> <span data-ttu-id="36c72-138">Vous pouvez ensuite rediriger les utilisateurs renvoyés vers l’applet de commande **Move-CsUSer**, comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="36c72-138">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    <span data-ttu-id="36c72-139">Le format de l’URL spécifiée pour le paramètre **hostedmigrationoverrideurl doit correspondre** doit être l’URL du pool sur lequel le service de migration hébergé est en cours d’exécution, au format suivant : *nom de domaine complet\<\>https:///HostedMigration/hostedmigrationService.svc*.</span><span class="sxs-lookup"><span data-stu-id="36c72-139">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.</span></span>
    
    <span data-ttu-id="36c72-140">Vous pouvez déterminer l’URL du service de migration hébergée en affichant l’URL du Panneau de configuration Lync Online correspondant à votre compte client Office 365.</span><span class="sxs-lookup"><span data-stu-id="36c72-140">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="36c72-141">Pour déterminer l’URL du service de migration hébergée de votre client Office 365</span><span class="sxs-lookup"><span data-stu-id="36c72-141">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>
    
    1.  <span data-ttu-id="36c72-142">Connectez-vous à votre client Office 365 en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="36c72-142">Login to your Office 365 tenant as an administrator.</span></span>
    
    2.  <span data-ttu-id="36c72-143">Ouvrez le **Centre d’administration Lync**.</span><span class="sxs-lookup"><span data-stu-id="36c72-143">Open the **Lync admin center**.</span></span>
    
    3.  <span data-ttu-id="36c72-144">Avec le **Centre d’administration Lync** affiché, sélectionnez et copiez l’URL dans la barre d’adresses jusqu’à **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="36c72-144">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="36c72-145">L’URL doit se présenter comme dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="36c72-145">An example URL looks similar to the following:</span></span>
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  <span data-ttu-id="36c72-146">Dans l’URL, remplacez **webdir** par **admin** pour obtenir le résultat suivant :</span><span class="sxs-lookup"><span data-stu-id="36c72-146">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
        
        `https://admin0a.online.lync.com`
    
    5.  <span data-ttu-id="36c72-147">Ajoutez la chaîne ci-dessous à l’URL : **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="36c72-147">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
        
        <span data-ttu-id="36c72-148">L’URL obtenue, qui est la valeur de **HostedMigrationOverrideUrl**, doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="36c72-148">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="36c72-149">La taille maximale par défaut pour les fichiers journaux de transaction de la base de données rtcxds est de 16 Go.</span><span class="sxs-lookup"><span data-stu-id="36c72-149">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="36c72-150">Cette taille peut être insuffisante si vous déplacez simultanément un grand nombre d’utilisateurs, notamment si la mise en miroir est activée.</span><span class="sxs-lookup"><span data-stu-id="36c72-150">This might not be big enough if you’re moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="36c72-151">Pour résoudre ce problème, vous pouvez augmenter la taille du fichier ou sauvegarder régulièrement les fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="36c72-151">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="36c72-152">Pour plus d’informations, <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>reportez-vous à.</span><span class="sxs-lookup"><span data-stu-id="36c72-152">For more information, see <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="36c72-153">Il s’agit d’une étape facultative.</span><span class="sxs-lookup"><span data-stu-id="36c72-153">This is an optional step.</span></span> <span data-ttu-id="36c72-154">Pour une intégration à Exchange 2013 Online, vous devez utiliser un autre fournisseur d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="36c72-154">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="36c72-155">Pour plus d’informations, reportez-vous à la rubrique [configuration d’une intégration de Lync Server 2013 en local avec Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span><span class="sxs-lookup"><span data-stu-id="36c72-155">For details, see [Configuring on-premises Lync Server 2013 integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span></span>

9.  <span data-ttu-id="36c72-p110">Les utilisateurs sont maintenant déplacés. Pour vérifier qu’un utilisateur possède des valeurs correctes pour les attributs affichés dans le tableau ci-dessous, tapez cette applet de commande :</span><span class="sxs-lookup"><span data-stu-id="36c72-p110">The users are now moved. To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>
    
        Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="36c72-158">Attribut Active Directory</span><span class="sxs-lookup"><span data-stu-id="36c72-158">Active Directory attribute</span></span></th>
    <th><span data-ttu-id="36c72-159">Nom Attribut</span><span class="sxs-lookup"><span data-stu-id="36c72-159">Attribute name</span></span></th>
    <th><span data-ttu-id="36c72-160">Valeur correcte pour l’utilisateur de Lync Online</span><span class="sxs-lookup"><span data-stu-id="36c72-160">Correct value for Lync Online user</span></span></th>
    <th><span data-ttu-id="36c72-161">Valeur correcte pour les utilisateurs Lync local</span><span class="sxs-lookup"><span data-stu-id="36c72-161">Correct value for Lync on–premises users</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="36c72-162">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="36c72-162">msRTCSIP-DeploymentLocator</span></span></p></td>
    <td><p><span data-ttu-id="36c72-163">HostingProvider</span><span class="sxs-lookup"><span data-stu-id="36c72-163">HostingProvider</span></span></p></td>
    <td><p><span data-ttu-id="36c72-164">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="36c72-164">sipfed.online.lync.com</span></span></p></td>
    <td><p><span data-ttu-id="36c72-165">SRV :</span><span class="sxs-lookup"><span data-stu-id="36c72-165">SRV:</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="36c72-166">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="36c72-166">msRTCSIP-PrimaryUserAddress</span></span></p></td>
    <td><p><span data-ttu-id="36c72-167">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="36c72-167">SIPAddress</span></span></p></td>
    <td><p><span data-ttu-id="36c72-168">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="36c72-168">sip:userName@contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="36c72-169">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="36c72-169">sip:userName@contoso.com</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="36c72-170">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="36c72-170">msRTCSIP-UserEnabled</span></span></p></td>
    <td><p><span data-ttu-id="36c72-171">Activé</span><span class="sxs-lookup"><span data-stu-id="36c72-171">Enabled</span></span></p></td>
    <td><p><span data-ttu-id="36c72-172">Vrai</span><span class="sxs-lookup"><span data-stu-id="36c72-172">True</span></span></p></td>
    <td><p><span data-ttu-id="36c72-173">Vrai</span><span class="sxs-lookup"><span data-stu-id="36c72-173">True</span></span></p></td>
    </tr>
    </tbody>
    </table>


10. <span data-ttu-id="36c72-174">Chaque utilisateur déplacé aura besoin de se déconnecter de Lync, puis de vous reconnecter.</span><span class="sxs-lookup"><span data-stu-id="36c72-174">Each user who has been moved will need to log out of Lync, then log back in.</span></span> <span data-ttu-id="36c72-175">Lorsque l’utilisateur se reconnecte, il doit vérifier ses listes de contacts et ajouter des contacts, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="36c72-175">When they log in they should verify their contact lists, and add contacts if needed.</span></span>
    
    <span data-ttu-id="36c72-176">Notez que les réunions planifiées ne sont pas déplacées de Lync Online vers Lync local.</span><span class="sxs-lookup"><span data-stu-id="36c72-176">Note that scheduled meetings are not migrated from Lync Online to Lync on-premises.</span></span> <span data-ttu-id="36c72-177">Les utilisateurs doivent replanifier ces réunions après les avoir déplacées.</span><span class="sxs-lookup"><span data-stu-id="36c72-177">Users will need to reschedule these meetings after being moved.</span></span>
    
    <span data-ttu-id="36c72-178">Une fois que les enregistrements DNS sont mis à jour et que tous les utilisateurs sont dirigés vers le site, l’attribut HostingProvider indique à l’utilisateur de Lync d’utiliser des enregistrements SRV ou de le diriger vers le fournisseur en ligne « sipfed.online.lync.com ».</span><span class="sxs-lookup"><span data-stu-id="36c72-178">After the DNS records are updated and all users are directed to On premise, the HostingProvider attribute directs the Lync user to either use SRV records or direct them to the Online provider “sipfed.online.lync.com.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


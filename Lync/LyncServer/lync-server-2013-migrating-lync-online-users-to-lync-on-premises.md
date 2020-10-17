---
title: 'Lync Server 2013 : migration des utilisateurs Lync Online vers Lync local'
description: 'Lync Server 2013 : migration des utilisateurs Lync Online vers Lync local.'
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
ms.openlocfilehash: 620bc07def8e3c1f6b761c6398b452b4dbcd3b04
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561000"
---
# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="2151f-103">Migration des utilisateurs Lync Online vers Lync sur site dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2151f-103">Migrating Lync Online users to Lync on-premises in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2151f-104">_**Dernière modification de la rubrique :** 2015-11-13_</span><span class="sxs-lookup"><span data-stu-id="2151f-104">_**Topic Last Modified:** 2015-11-13_</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="2151f-105">Ces étapes sont nécessaires uniquement pour la migration des comptes d’utilisateurs qui ont été activés à l’origine pour Lync dans Lync Online, avant le déploiement de Lync sur site.</span><span class="sxs-lookup"><span data-stu-id="2151f-105">These steps are necessary only for migrating user accounts that were originally enabled for Lync in Lync Online, before you deployed Lync on-premises.</span></span> <span data-ttu-id="2151f-106">Pour déplacer les utilisateurs activés à l’origine pour Lync sur site, puis déplacés vers Lync Online, reportez-vous à <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">la rubrique Administering users in a Hybrid Lync Server 2013 Deployment</A>.</span><span class="sxs-lookup"><span data-stu-id="2151f-106">To move users who were originally enabled for Lync on-premises, then later moved to Lync Online, see <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</A>.</span></span><BR><span data-ttu-id="2151f-107">De plus, tous les utilisateurs déplacés doivent disposer de comptes dans l’annuaire Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="2151f-107">Additionally, all users being moved must have accounts in the on-premises Active Directory.</span></span>



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a><span data-ttu-id="2151f-108">Migration des comptes d’utilisateur activés à l’origine dans Lync Online vers Lync local</span><span class="sxs-lookup"><span data-stu-id="2151f-108">Migrating User Accounts Originally Enabled in Lync Online to Lync On-Premises</span></span>

1.  <span data-ttu-id="2151f-109">Tout d’abord, assurez-vous que votre organisation est configurée pour l’environnement hybride.</span><span class="sxs-lookup"><span data-stu-id="2151f-109">First, make sure that your organization is configured for hybrid.</span></span>
    
      - <span data-ttu-id="2151f-110">Installez l’outil de synchronisation Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2151f-110">Install the Azure Active Directory Sync Tool.</span></span> <span data-ttu-id="2151f-111">Pour plus d'informations, reportez-vous à l'article <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span><span class="sxs-lookup"><span data-stu-id="2151f-111">For more information, see <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span></span>
    
      - <span data-ttu-id="2151f-112">Pour permettre à vos utilisateurs d’utiliser l’authentification unique pour Lync Online, installez les services ADFS (Active Directory Federation Services) <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx> .</span><span class="sxs-lookup"><span data-stu-id="2151f-112">To enable your users to use single sign-on for Lync Online, install Active Directory Federation Services <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.</span></span>
    
      - <span data-ttu-id="2151f-113">Sur votre déploiement local, dans Lync Server Management Shell, tapez les applets de commande suivantes pour créer le fournisseur d’hébergement pour Lync Online :</span><span class="sxs-lookup"><span data-stu-id="2151f-113">On your on-premises deployment, in Lync Server Management Shell, type the following cmdlets to create the hosting provider for Lync Online:</span></span>
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  <span data-ttu-id="2151f-114">Vérifiez que, sur vos serveurs Edge locaux, vous disposez de la chaîne de certificats qui permet la connexion à Lync Online, comme illustré dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="2151f-114">Confirm that, on your on-premises Edge Servers, you have the certificate chain that enables connection to Lync Online, as shown in the following table.</span></span> <span data-ttu-id="2151f-115">Vous pouvez télécharger cette chaîne ici : https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span><span class="sxs-lookup"><span data-stu-id="2151f-115">You can download this chain here: https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span></span>


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="2151f-116">Certificat</span><span class="sxs-lookup"><span data-stu-id="2151f-116">Certificate</span></span></th>
    <th><span data-ttu-id="2151f-117">Magasin de certificats</span><span class="sxs-lookup"><span data-stu-id="2151f-117">Certificate Store</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="2151f-118">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="2151f-118">Baltimore CyberTrust Root</span></span></p></td>
    <td><p><span data-ttu-id="2151f-119">Autorité de certification racine de confiance</span><span class="sxs-lookup"><span data-stu-id="2151f-119">Trusted Root CA</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="2151f-120">Microsoft Internet Authority (nouveau certificat d’autorité de certification)</span><span class="sxs-lookup"><span data-stu-id="2151f-120">Microsoft Internet Authority (New CA certificate)</span></span></p></td>
    <td><p><span data-ttu-id="2151f-121">Autorité de certification intermédiaire</span><span class="sxs-lookup"><span data-stu-id="2151f-121">Intermediate CA</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="2151f-122">CA2 d’authentification de l’ordinateur MSIT (nouvelle émission de CA2)</span><span class="sxs-lookup"><span data-stu-id="2151f-122">MSIT Machine Auth CA2 (New Issuing CA2)</span></span></p></td>
    <td><p><span data-ttu-id="2151f-123">Autorité de certification intermédiaire</span><span class="sxs-lookup"><span data-stu-id="2151f-123">Intermediate CA</span></span></p></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="2151f-124">Dans votre annuaire Active Directory local, activez les comptes d’utilisateur affectés pour Lync sur site.</span><span class="sxs-lookup"><span data-stu-id="2151f-124">In your on-premises Active Directory, enable the affected user accounts for Lync on-premises.</span></span> <span data-ttu-id="2151f-125">Vous pouvez effectuer cette opération pour un utilisateur individuel en tapant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="2151f-125">You can do this for an individual user by typing the following cmdlet:</span></span>
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    <span data-ttu-id="2151f-126">Vous pouvez aussi créer un script qui lit les noms d’utilisateur à partir d’un fichier et les fournit en tant qu’entrée à l’applet de commande Enable-CsUser :</span><span class="sxs-lookup"><span data-stu-id="2151f-126">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  <span data-ttu-id="2151f-127">Exécutez DirSync pour synchroniser les utilisateurs Lync Online avec les utilisateurs de Lync sur site mis à jour.</span><span class="sxs-lookup"><span data-stu-id="2151f-127">Run DirSync to sync the Lync Online users with the updated Lync on-premises users.</span></span>

5.  <span data-ttu-id="2151f-128">Mettre à jour certains enregistrements DNS pour diriger tout le trafic SIP vers Lync en local :</span><span class="sxs-lookup"><span data-stu-id="2151f-128">Update some DNS records to direct all SIP traffic to Lync on-premises:</span></span>
    
      - <span data-ttu-id="2151f-129">Mettez à jour l’enregistrement **Lyncdiscover.contoso.com** A de sorte qu’il pointe vers le nom de domaine complet du serveur proxy inverse local.</span><span class="sxs-lookup"><span data-stu-id="2151f-129">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>
    
      - <span data-ttu-id="2151f-130">Mettez à jour le \*\*\* \_ SIP \*. \_ \*\*enregistrement SRV TLS.contoso.com à convertir en adresse IP publique ou adresse IP virtuelle du service Edge d’accès de Lync sur site.</span><span class="sxs-lookup"><span data-stu-id="2151f-130">Update the \***\_sip\*.\_tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="2151f-131">Mettre à jour les \*\*\* \_ sipfederationtls \*. \_ \*\*enregistrement SRV TCP.contoso.com à convertir en adresse IP publique ou adresse IP virtuelle du service Edge d’accès de Lync sur site.</span><span class="sxs-lookup"><span data-stu-id="2151f-131">Update the \***\_sipfederationtls\*.\_tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="2151f-132">Si votre organisation utilise le DNS fractionné (parfois appelé « DNS split-brain »), assurez-vous que les utilisateurs résolvent les noms par le biais de la zone DNS interne sont dirigés vers le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="2151f-132">If your organization uses split DNS (sometimes called “split-brain DNS”), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6.  <span data-ttu-id="2151f-133">Tapez l' `Get-CsUser` applet de commande pour vérifier certaines propriétés des utilisateurs que vous allez déplacer.</span><span class="sxs-lookup"><span data-stu-id="2151f-133">Type the `Get-CsUser` cmdlet to check some properties about the users you’ll be moving.</span></span> <span data-ttu-id="2151f-134">Vous voulez vous assurer que le HostingProviderProxyFQDN est défini sur `"sipfed.online.lync.com"` et que les adresses SIP sont définies correctement.</span><span class="sxs-lookup"><span data-stu-id="2151f-134">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7.  <span data-ttu-id="2151f-135">Déplacez les utilisateurs Lync Online vers Lync local.</span><span class="sxs-lookup"><span data-stu-id="2151f-135">Move Lync Online users to Lync on-premises.</span></span>
    
    <span data-ttu-id="2151f-136">Pour déplacer un seul utilisateur, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="2151f-136">To move a single user, type this:</span></span>
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    <span data-ttu-id="2151f-137">Vous pouvez déplacer plusieurs utilisateurs à l’aide de la cmdlet **Get-CsUSer** avec le paramètre – Filter pour sélectionner les utilisateurs avec une propriété spécifique.</span><span class="sxs-lookup"><span data-stu-id="2151f-137">You can move multiple users by using the **Get-CsUSer** cmdlet with the –Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="2151f-138">Par exemple, vous pouvez sélectionner tous les utilisateurs Lync Online en filtrant pour {Hosting Provider – EQ "sipfed.online.lync.om"}.</span><span class="sxs-lookup"><span data-stu-id="2151f-138">For example, you could select all Lync Online users by filtering for {Hosting Provider –eq “sipfed.online.lync.om”}.</span></span> <span data-ttu-id="2151f-139">Vous pouvez ensuite rediriger les utilisateurs renvoyés vers l’applet de commande **Move-CsUSer** , comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="2151f-139">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    <span data-ttu-id="2151f-140">Le format de l’URL spécifiée pour le paramètre **HostedMigrationOverrideUrl** doit être l’URL du pool où le service de migration hébergée est en cours d’exécution, au format suivant : *https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc*.</span><span class="sxs-lookup"><span data-stu-id="2151f-140">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.</span></span>
    
    <span data-ttu-id="2151f-141">Vous pouvez déterminer l’URL du service de migration hébergée en affichant l’URL du panneau de configuration Lync Online pour votre compte d’organisation Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="2151f-141">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Microsoft 365 or Office 365 organization account.</span></span>
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-organizaton"></a><span data-ttu-id="2151f-142">Pour déterminer l’URL du service de migration hébergée pour votre Organizaton</span><span class="sxs-lookup"><span data-stu-id="2151f-142">To determine the Hosted Migration Service URL for your organizaton</span></span>
    
    1.  <span data-ttu-id="2151f-143">Connectez-vous à votre organisation Microsoft 365 ou Office 365 en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="2151f-143">Log in to your Microsoft 365 or Office 365 organization as an administrator.</span></span>
    
    2.  <span data-ttu-id="2151f-144">Ouvrez le **Centre d’administration Lync**.</span><span class="sxs-lookup"><span data-stu-id="2151f-144">Open the **Lync admin center**.</span></span>
    
    3.  <span data-ttu-id="2151f-145">Avec le **Centre d’administration Lync** affiché, sélectionnez et copiez l’URL dans la barre d’adresse jusqu’à **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="2151f-145">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="2151f-146">Un exemple d’URL doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="2151f-146">An example URL looks similar to the following:</span></span>
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  <span data-ttu-id="2151f-147">Remplacez **webdir** dans l’URL par **administrateur**, de la façon suivante :</span><span class="sxs-lookup"><span data-stu-id="2151f-147">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
        
        `https://admin0a.online.lync.com`
    
    5.  <span data-ttu-id="2151f-148">Ajoutez la chaîne suivante à l’URL : **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="2151f-148">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
        
        <span data-ttu-id="2151f-149">L’URL résultante, qui est la valeur de **HostedMigrationOverrideUrl**, doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="2151f-149">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="2151f-150">La taille maximale par défaut pour les fichiers journaux des transactions de la base de données rtcxds est de 16 Go.</span><span class="sxs-lookup"><span data-stu-id="2151f-150">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="2151f-151">Cela n’est peut-être pas assez grand si vous déplacez un grand nombre d’utilisateurs à la fois, en particulier si vous avez activé la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="2151f-151">This might not be big enough if you’re moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="2151f-152">Pour contourner ce risque, vous pouvez augmenter la taille du fichier ou sauvegarder les fichiers journaux régulièrement.</span><span class="sxs-lookup"><span data-stu-id="2151f-152">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="2151f-153">Pour plus d’informations, reportez-vous à <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A> .</span><span class="sxs-lookup"><span data-stu-id="2151f-153">For more information, see <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="2151f-154">Il s’agit d’une étape facultative.</span><span class="sxs-lookup"><span data-stu-id="2151f-154">This is an optional step.</span></span> <span data-ttu-id="2151f-155">Si vous avez besoin d’une intégration à Exchange 2013 Online, vous devez utiliser un fournisseur d’hébergement supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="2151f-155">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="2151f-156">Pour plus d’informations, reportez-vous à la rubrique [Configuring on-premises Lync Server 2013 Integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span><span class="sxs-lookup"><span data-stu-id="2151f-156">For details, see [Configuring on-premises Lync Server 2013 integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span></span>

9.  <span data-ttu-id="2151f-157">Les utilisateurs sont déplacés.</span><span class="sxs-lookup"><span data-stu-id="2151f-157">The users are now moved.</span></span> <span data-ttu-id="2151f-158">Pour vérifier qu’un utilisateur a des valeurs correctes pour les attributs indiqués dans le tableau suivant, tapez cette applet de commande :</span><span class="sxs-lookup"><span data-stu-id="2151f-158">To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>
    
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
    <th><span data-ttu-id="2151f-159">Attribut Active Directory</span><span class="sxs-lookup"><span data-stu-id="2151f-159">Active Directory attribute</span></span></th>
    <th><span data-ttu-id="2151f-160">Nom de l’attribut</span><span class="sxs-lookup"><span data-stu-id="2151f-160">Attribute name</span></span></th>
    <th><span data-ttu-id="2151f-161">Valeur correcte pour l’utilisateur Lync Online</span><span class="sxs-lookup"><span data-stu-id="2151f-161">Correct value for Lync Online user</span></span></th>
    <th><span data-ttu-id="2151f-162">Valeur correcte pour les utilisateurs de Lync sur site</span><span class="sxs-lookup"><span data-stu-id="2151f-162">Correct value for Lync on–premises users</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="2151f-163">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="2151f-163">msRTCSIP-DeploymentLocator</span></span></p></td>
    <td><p><span data-ttu-id="2151f-164">HostingProvider</span><span class="sxs-lookup"><span data-stu-id="2151f-164">HostingProvider</span></span></p></td>
    <td><p><span data-ttu-id="2151f-165">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2151f-165">sipfed.online.lync.com</span></span></p></td>
    <td><p><span data-ttu-id="2151f-166">SRV</span><span class="sxs-lookup"><span data-stu-id="2151f-166">SRV:</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="2151f-167">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="2151f-167">msRTCSIP-PrimaryUserAddress</span></span></p></td>
    <td><p><span data-ttu-id="2151f-168">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="2151f-168">SIPAddress</span></span></p></td>
    <td><p><span data-ttu-id="2151f-169">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2151f-169">sip:userName@contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="2151f-170">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2151f-170">sip:userName@contoso.com</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="2151f-171">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="2151f-171">msRTCSIP-UserEnabled</span></span></p></td>
    <td><p><span data-ttu-id="2151f-172">Activé</span><span class="sxs-lookup"><span data-stu-id="2151f-172">Enabled</span></span></p></td>
    <td><p><span data-ttu-id="2151f-173">True</span><span class="sxs-lookup"><span data-stu-id="2151f-173">True</span></span></p></td>
    <td><p><span data-ttu-id="2151f-174">True</span><span class="sxs-lookup"><span data-stu-id="2151f-174">True</span></span></p></td>
    </tr>
    </tbody>
    </table>


10. <span data-ttu-id="2151f-175">Chaque utilisateur qui a été déplacé doit se déconnecter de Lync, puis se reconnecter.</span><span class="sxs-lookup"><span data-stu-id="2151f-175">Each user who has been moved will need to log out of Lync, then log back in.</span></span> <span data-ttu-id="2151f-176">Lorsqu’ils se connectent, ils doivent vérifier leurs listes de contacts et ajouter des contacts si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="2151f-176">When they log in they should verify their contact lists, and add contacts if needed.</span></span>
    
    <span data-ttu-id="2151f-177">Notez que les réunions planifiées ne sont pas migrées de Lync Online vers Lync en local.</span><span class="sxs-lookup"><span data-stu-id="2151f-177">Note that scheduled meetings are not migrated from Lync Online to Lync on-premises.</span></span> <span data-ttu-id="2151f-178">Les utilisateurs devront replanifier ces réunions après leur déplacement.</span><span class="sxs-lookup"><span data-stu-id="2151f-178">Users will need to reschedule these meetings after being moved.</span></span>
    
    <span data-ttu-id="2151f-179">Une fois que les enregistrements DNS sont mis à jour et que tous les utilisateurs sont dirigés vers le site, l’attribut HostingProvider indique à l’utilisateur Lync d’utiliser des enregistrements SRV ou de les diriger vers le fournisseur en ligne « sipfed.online.lync.com ».</span><span class="sxs-lookup"><span data-stu-id="2151f-179">After the DNS records are updated and all users are directed to On premise, the HostingProvider attribute directs the Lync user to either use SRV records or direct them to the Online provider “sipfed.online.lync.com.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013 : Get-CsService pour la gestion du carnet d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsService for Address Book management
ms:assetid: 373b717d-5efa-4c36-a899-a23a5bd922b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429698(v=OCS.15)
ms:contentKeyID: 48183853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 656c1aa545a1f10e49c5ff60b51c20386854d146
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="6f7fb-102">Get-CsService pour la gestion du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f7fb-102">Get-CsService for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f7fb-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6f7fb-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6f7fb-104">Qui peut exécuter cette applet de commande : par défaut, les membres des groupes suivants sont autorisés à exécuter l’applet de commande Get-CsService localement : RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="6f7fb-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsService cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span> <span data-ttu-id="6f7fb-105">Pour renvoyer la liste de tous les rôles de contrôle d’accès basés sur des rôles (RBAC) affectés à cette applet de commande (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="6f7fb-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

<span data-ttu-id="6f7fb-106">Get-CsService est utile pour récupérer et afficher la configuration actuelle des services Web définis de votre infrastructure.</span><span class="sxs-lookup"><span data-stu-id="6f7fb-106">Get-CsService is valuable to retrieve and display the current configuration of your infrastructure’s defined Web Services.</span></span> <span data-ttu-id="6f7fb-107">En définissant le nom de domaine complet (FQDN) du pool et le serveur de noms WebServer, l’applet de passe renvoie les services Web proposés par votre serveur, y compris le gestionnaire du carnet d’adresses et les URI d’extension de liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="6f7fb-107">By defining the pool’s fully qualified domain name (FQDN) and the parameter WebServer, the cmdlet returns the web-based services offered by your server, including the Address Book handler and distribution list expansion URIs.</span></span>

<span data-ttu-id="6f7fb-108">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="6f7fb-108">For example:</span></span>

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

<span data-ttu-id="6f7fb-109">Cette applet de commande renvoie ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="6f7fb-109">This cmdlet returns the following:</span></span>

<span data-ttu-id="6f7fb-110">Identité : serveur :pool01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="6f7fb-110">Identity : WebServer:pool01.contoso.net</span></span>

<span data-ttu-id="6f7fb-111">:DC01 :%. contoso. net</span><span class="sxs-lookup"><span data-stu-id="6f7fb-111">FileStore : FileStore:dc01.contoso.net</span></span>

<span data-ttu-id="6f7fb-112">UserServer : UserServer :pool01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="6f7fb-112">UserServer : UserServer:pool01.contoso.net</span></span>

<span data-ttu-id="6f7fb-113">PrimaryHttpPort : 80</span><span class="sxs-lookup"><span data-stu-id="6f7fb-113">PrimaryHttpPort : 80</span></span>

<span data-ttu-id="6f7fb-114">PrimaryHttpsPort : 443</span><span class="sxs-lookup"><span data-stu-id="6f7fb-114">PrimaryHttpsPort : 443</span></span>

<span data-ttu-id="6f7fb-115">ExternalHttpPort : 8080</span><span class="sxs-lookup"><span data-stu-id="6f7fb-115">ExternalHttpPort : 8080</span></span>

<span data-ttu-id="6f7fb-116">ExternalHttpsPort : 4443</span><span class="sxs-lookup"><span data-stu-id="6f7fb-116">ExternalHttpsPort : 4443</span></span>

<span data-ttu-id="6f7fb-117">PublishedPrimaryHttpPort : 80</span><span class="sxs-lookup"><span data-stu-id="6f7fb-117">PublishedPrimaryHttpPort : 80</span></span>

<span data-ttu-id="6f7fb-118">PublishedPrimaryHttpsPort : 443</span><span class="sxs-lookup"><span data-stu-id="6f7fb-118">PublishedPrimaryHttpsPort : 443</span></span>

<span data-ttu-id="6f7fb-119">PublishedExternalHttpPort : 80</span><span class="sxs-lookup"><span data-stu-id="6f7fb-119">PublishedExternalHttpPort : 80</span></span>

<span data-ttu-id="6f7fb-120">PublishedExternalHttpsPort : 443</span><span class="sxs-lookup"><span data-stu-id="6f7fb-120">PublishedExternalHttpsPort : 443</span></span>

<span data-ttu-id="6f7fb-121">ReachPrimaryPsomServerPort : 8060</span><span class="sxs-lookup"><span data-stu-id="6f7fb-121">ReachPrimaryPsomServerPort : 8060</span></span>

<span data-ttu-id="6f7fb-122">ReachExternalPsomServerPort : 8061</span><span class="sxs-lookup"><span data-stu-id="6f7fb-122">ReachExternalPsomServerPort : 8061</span></span>

<span data-ttu-id="6f7fb-123">AppSharingPortStart : 49152</span><span class="sxs-lookup"><span data-stu-id="6f7fb-123">AppSharingPortStart : 49152</span></span>

<span data-ttu-id="6f7fb-124">AppSharingPortCount : 16383</span><span class="sxs-lookup"><span data-stu-id="6f7fb-124">AppSharingPortCount : 16383</span></span>

<span data-ttu-id="6f7fb-125">LIServiceInternalUri :https://internalweb.contoso.net/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="6f7fb-125">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span></span>

<span data-ttu-id="6f7fb-126">ABHandlerInternalUri :https://internalweb.contoso.net/abs/handler</span><span class="sxs-lookup"><span data-stu-id="6f7fb-126">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span></span>

<span data-ttu-id="6f7fb-127">ABHandlerExternalUri :https://csweb.contoso.com/abs/handler</span><span class="sxs-lookup"><span data-stu-id="6f7fb-127">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span></span>

<span data-ttu-id="6f7fb-128">DLExpansionInternalUri :https://internalweb.contoso.net/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="6f7fb-128">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span></span>

<span data-ttu-id="6f7fb-129">DLExpansionExternalUri :https://csweb.contoso.com/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="6f7fb-129">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span></span>

<span data-ttu-id="6f7fb-130">CAHandlerInternalUri :https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="6f7fb-130">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="6f7fb-131">CAHandlerInternalAnonUri :http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="6f7fb-131">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="6f7fb-132">CollabContentInternalUri :https://internalweb.contoso.net/CollabContent</span><span class="sxs-lookup"><span data-stu-id="6f7fb-132">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span></span>

<span data-ttu-id="6f7fb-133">CollabContentExternalUri :https://csweb.contoso.com/CollabContent</span><span class="sxs-lookup"><span data-stu-id="6f7fb-133">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span></span>

<span data-ttu-id="6f7fb-134">CAHandlerExternalUri :https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="6f7fb-134">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="6f7fb-135">DeviceUpdateDownloadInternalUri :https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="6f7fb-135">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span></span>

<span data-ttu-id="6f7fb-136">DeviceUpdateDownloadExternalUri :https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="6f7fb-136">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span></span>

<span data-ttu-id="6f7fb-137">DeviceUpdateStoreInternalUri :http://internalweb.contoso.net/RequestHandler/Files</span><span class="sxs-lookup"><span data-stu-id="6f7fb-137">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span></span>

<span data-ttu-id="6f7fb-138">DeviceUpdateStoreExternalUri :https://csweb.contoso.com/RequestHandlerExt/Files</span><span class="sxs-lookup"><span data-stu-id="6f7fb-138">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span></span>

<span data-ttu-id="6f7fb-139">RgsAgentServiceInternalUri :https://internalweb.contoso.net/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="6f7fb-139">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="6f7fb-140">RgsAgentServiceExternalUri :https://csweb.contoso.com/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="6f7fb-140">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="6f7fb-141">MeetExternalUri :https://csweb.contoso.com/Meet</span><span class="sxs-lookup"><span data-stu-id="6f7fb-141">MeetExternalUri : https://csweb.contoso.com/Meet</span></span>

<span data-ttu-id="6f7fb-142">DialinExternalUri :https://csweb.contoso.com/Dialin</span><span class="sxs-lookup"><span data-stu-id="6f7fb-142">DialinExternalUri : https://csweb.contoso.com/Dialin</span></span>

<span data-ttu-id="6f7fb-143">CscpInternalUri :https://internalweb.contoso.net/Cscp</span><span class="sxs-lookup"><span data-stu-id="6f7fb-143">CscpInternalUri : https://internalweb.contoso.net/Cscp</span></span>

<span data-ttu-id="6f7fb-144">ReachExternalUri :https://csweb.contoso.com/Reach</span><span class="sxs-lookup"><span data-stu-id="6f7fb-144">ReachExternalUri : https://csweb.contoso.com/Reach</span></span>

<span data-ttu-id="6f7fb-145">ReachInternalUri :https://internalweb.contoso.net/Reach</span><span class="sxs-lookup"><span data-stu-id="6f7fb-145">ReachInternalUri : https://internalweb.contoso.net/Reach</span></span>

<span data-ttu-id="6f7fb-146">WebTicketExternalUri :https://csweb.contoso.com/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="6f7fb-146">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="6f7fb-147">WebTicketInternalUri :https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="6f7fb-147">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="6f7fb-148">ExternalFqdn : csweb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6f7fb-148">ExternalFqdn : csweb.contoso.com</span></span>

<span data-ttu-id="6f7fb-149">InternalFqdn : internalweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6f7fb-149">InternalFqdn : internalweb.contoso.net</span></span>

<span data-ttu-id="6f7fb-150">DependentServiceList : {Registrar :pool01. contoso. net ConferencingServer :pool01. contoso. net}</span><span class="sxs-lookup"><span data-stu-id="6f7fb-150">DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}</span></span>

<span data-ttu-id="6f7fb-151">ServiceId : 1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="6f7fb-151">ServiceId : 1-WebServices-1</span></span>

<span data-ttu-id="6f7fb-152">SiteId : site : Redmond</span><span class="sxs-lookup"><span data-stu-id="6f7fb-152">SiteId : Site:Redmond</span></span>

<span data-ttu-id="6f7fb-153">PoolFqdn : pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6f7fb-153">PoolFqdn : pool01.contoso.net</span></span>

<span data-ttu-id="6f7fb-154">Version : 5</span><span class="sxs-lookup"><span data-stu-id="6f7fb-154">Version : 5</span></span>

<span data-ttu-id="6f7fb-155">Rôle : webserver</span><span class="sxs-lookup"><span data-stu-id="6f7fb-155">Role : WebServer</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6f7fb-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6f7fb-156">See Also</span></span>


[<span data-ttu-id="6f7fb-157">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="6f7fb-157">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


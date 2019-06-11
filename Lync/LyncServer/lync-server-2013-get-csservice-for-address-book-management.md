---
title: 'Lync Server 2013: Get-CsService pour la gestion du carnet d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Get-CsService for Address Book management
ms:assetid: 373b717d-5efa-4c36-a899-a23a5bd922b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429698(v=OCS.15)
ms:contentKeyID: 48183853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cfa9bd42bb29ca32ab27dc64d2ee9a111abab8d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="b9663-102">Get-CsService pour la gestion du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9663-102">Get-CsService for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9663-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b9663-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b9663-104">Qui peut exécuter cette applet de commande: par défaut, les membres des groupes suivants sont autorisés à exécuter l’applet de commande Get-CsService localement: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b9663-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsService cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span> <span data-ttu-id="b9663-105">Pour renvoyer la liste de tous les rôles de contrôle d’accès basés sur des rôles (RBAC) affectés à cette applet de commande (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de l’invite Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b9663-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

<span data-ttu-id="b9663-106">Get-CsService est utile pour récupérer et afficher la configuration actuelle des services Web définis de votre infrastructure.</span><span class="sxs-lookup"><span data-stu-id="b9663-106">Get-CsService is valuable to retrieve and display the current configuration of your infrastructure’s defined Web Services.</span></span> <span data-ttu-id="b9663-107">En définissant le nom de domaine complet (FQDN) du pool et le serveur de noms WebServer, l’applet de passe renvoie les services Web proposés par votre serveur, y compris le gestionnaire du carnet d’adresses et les URI d’extension de liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="b9663-107">By defining the pool’s fully qualified domain name (FQDN) and the parameter WebServer, the cmdlet returns the web-based services offered by your server, including the Address Book handler and distribution list expansion URIs.</span></span>

<span data-ttu-id="b9663-108">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b9663-108">For example:</span></span>

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

<span data-ttu-id="b9663-109">Cette applet de commande renvoie ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="b9663-109">This cmdlet returns the following:</span></span>

<span data-ttu-id="b9663-110">Identité: serveur:pool01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="b9663-110">Identity : WebServer:pool01.contoso.net</span></span>

<span data-ttu-id="b9663-111">:DC01:%. contoso. net</span><span class="sxs-lookup"><span data-stu-id="b9663-111">FileStore : FileStore:dc01.contoso.net</span></span>

<span data-ttu-id="b9663-112">UserServer: UserServer:pool01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="b9663-112">UserServer : UserServer:pool01.contoso.net</span></span>

<span data-ttu-id="b9663-113">PrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="b9663-113">PrimaryHttpPort : 80</span></span>

<span data-ttu-id="b9663-114">PrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="b9663-114">PrimaryHttpsPort : 443</span></span>

<span data-ttu-id="b9663-115">ExternalHttpPort: 8080</span><span class="sxs-lookup"><span data-stu-id="b9663-115">ExternalHttpPort : 8080</span></span>

<span data-ttu-id="b9663-116">ExternalHttpsPort: 4443</span><span class="sxs-lookup"><span data-stu-id="b9663-116">ExternalHttpsPort : 4443</span></span>

<span data-ttu-id="b9663-117">PublishedPrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="b9663-117">PublishedPrimaryHttpPort : 80</span></span>

<span data-ttu-id="b9663-118">PublishedPrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="b9663-118">PublishedPrimaryHttpsPort : 443</span></span>

<span data-ttu-id="b9663-119">PublishedExternalHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="b9663-119">PublishedExternalHttpPort : 80</span></span>

<span data-ttu-id="b9663-120">PublishedExternalHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="b9663-120">PublishedExternalHttpsPort : 443</span></span>

<span data-ttu-id="b9663-121">ReachPrimaryPsomServerPort: 8060</span><span class="sxs-lookup"><span data-stu-id="b9663-121">ReachPrimaryPsomServerPort : 8060</span></span>

<span data-ttu-id="b9663-122">ReachExternalPsomServerPort: 8061</span><span class="sxs-lookup"><span data-stu-id="b9663-122">ReachExternalPsomServerPort : 8061</span></span>

<span data-ttu-id="b9663-123">AppSharingPortStart: 49152</span><span class="sxs-lookup"><span data-stu-id="b9663-123">AppSharingPortStart : 49152</span></span>

<span data-ttu-id="b9663-124">AppSharingPortCount: 16383</span><span class="sxs-lookup"><span data-stu-id="b9663-124">AppSharingPortCount : 16383</span></span>

<span data-ttu-id="b9663-125">LIServiceInternalUri :https://internalweb.contoso.net/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="b9663-125">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span></span>

<span data-ttu-id="b9663-126">ABHandlerInternalUri :https://internalweb.contoso.net/abs/handler</span><span class="sxs-lookup"><span data-stu-id="b9663-126">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span></span>

<span data-ttu-id="b9663-127">ABHandlerExternalUri :https://csweb.contoso.com/abs/handler</span><span class="sxs-lookup"><span data-stu-id="b9663-127">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span></span>

<span data-ttu-id="b9663-128">DLExpansionInternalUri :https://internalweb.contoso.net/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="b9663-128">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span></span>

<span data-ttu-id="b9663-129">DLExpansionExternalUri :https://csweb.contoso.com/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="b9663-129">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span></span>

<span data-ttu-id="b9663-130">CAHandlerInternalUri :https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="b9663-130">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="b9663-131">CAHandlerInternalAnonUri :http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="b9663-131">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="b9663-132">CollabContentInternalUri :https://internalweb.contoso.net/CollabContent</span><span class="sxs-lookup"><span data-stu-id="b9663-132">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span></span>

<span data-ttu-id="b9663-133">CollabContentExternalUri :https://csweb.contoso.com/CollabContent</span><span class="sxs-lookup"><span data-stu-id="b9663-133">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span></span>

<span data-ttu-id="b9663-134">CAHandlerExternalUri :https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="b9663-134">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="b9663-135">DeviceUpdateDownloadInternalUri :https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="b9663-135">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span></span>

<span data-ttu-id="b9663-136">DeviceUpdateDownloadExternalUri :https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="b9663-136">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span></span>

<span data-ttu-id="b9663-137">DeviceUpdateStoreInternalUri :http://internalweb.contoso.net/RequestHandler/Files</span><span class="sxs-lookup"><span data-stu-id="b9663-137">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span></span>

<span data-ttu-id="b9663-138">DeviceUpdateStoreExternalUri :https://csweb.contoso.com/RequestHandlerExt/Files</span><span class="sxs-lookup"><span data-stu-id="b9663-138">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span></span>

<span data-ttu-id="b9663-139">RgsAgentServiceInternalUri :https://internalweb.contoso.net/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="b9663-139">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="b9663-140">RgsAgentServiceExternalUri :https://csweb.contoso.com/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="b9663-140">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="b9663-141">MeetExternalUri :https://csweb.contoso.com/Meet</span><span class="sxs-lookup"><span data-stu-id="b9663-141">MeetExternalUri : https://csweb.contoso.com/Meet</span></span>

<span data-ttu-id="b9663-142">DialinExternalUri :https://csweb.contoso.com/Dialin</span><span class="sxs-lookup"><span data-stu-id="b9663-142">DialinExternalUri : https://csweb.contoso.com/Dialin</span></span>

<span data-ttu-id="b9663-143">CscpInternalUri :https://internalweb.contoso.net/Cscp</span><span class="sxs-lookup"><span data-stu-id="b9663-143">CscpInternalUri : https://internalweb.contoso.net/Cscp</span></span>

<span data-ttu-id="b9663-144">ReachExternalUri :https://csweb.contoso.com/Reach</span><span class="sxs-lookup"><span data-stu-id="b9663-144">ReachExternalUri : https://csweb.contoso.com/Reach</span></span>

<span data-ttu-id="b9663-145">ReachInternalUri :https://internalweb.contoso.net/Reach</span><span class="sxs-lookup"><span data-stu-id="b9663-145">ReachInternalUri : https://internalweb.contoso.net/Reach</span></span>

<span data-ttu-id="b9663-146">WebTicketExternalUri :https://csweb.contoso.com/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="b9663-146">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="b9663-147">WebTicketInternalUri :https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="b9663-147">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="b9663-148">ExternalFqdn: csweb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b9663-148">ExternalFqdn : csweb.contoso.com</span></span>

<span data-ttu-id="b9663-149">InternalFqdn: internalweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="b9663-149">InternalFqdn : internalweb.contoso.net</span></span>

<span data-ttu-id="b9663-150">DependentServiceList: {Registrar:pool01. contoso. net ConferencingServer:pool01. contoso. net}</span><span class="sxs-lookup"><span data-stu-id="b9663-150">DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}</span></span>

<span data-ttu-id="b9663-151">ServiceId: 1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="b9663-151">ServiceId : 1-WebServices-1</span></span>

<span data-ttu-id="b9663-152">SiteId: site: Redmond</span><span class="sxs-lookup"><span data-stu-id="b9663-152">SiteId : Site:Redmond</span></span>

<span data-ttu-id="b9663-153">PoolFqdn: pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="b9663-153">PoolFqdn : pool01.contoso.net</span></span>

<span data-ttu-id="b9663-154">Version: 5</span><span class="sxs-lookup"><span data-stu-id="b9663-154">Version : 5</span></span>

<span data-ttu-id="b9663-155">Rôle: webserver</span><span class="sxs-lookup"><span data-stu-id="b9663-155">Role : WebServer</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b9663-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b9663-156">See Also</span></span>


[<span data-ttu-id="b9663-157">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="b9663-157">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


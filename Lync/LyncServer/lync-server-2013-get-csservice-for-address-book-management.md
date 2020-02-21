---
title: 'Lync Server 2013 : Get-CsService pour la gestion des carnets d’adresses'
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
ms.openlocfilehash: 8a9e8be425a86eef0d548493e1466888d3d8728c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="017e6-102">Get-CsService pour la gestion des carnets d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="017e6-102">Get-CsService for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="017e6-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="017e6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="017e6-p101">Personnes autorisées à exécuter cette applet de commande : Par défaut, les membres des groupes suivants sont autorisés à exécuter localement l’applet de commande Get-CsService : RTCUniversalUserAdmins, RTCUniversalServerAdmins. Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="017e6-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsService cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

<span data-ttu-id="017e6-106">Get-CsService est utile pour extraire et afficher la configuration actuelle des services Web définis de votre infrastructure.</span><span class="sxs-lookup"><span data-stu-id="017e6-106">Get-CsService is valuable to retrieve and display the current configuration of your infrastructure’s defined Web Services.</span></span> <span data-ttu-id="017e6-107">Si vous définissez le nom de domaine complet (FQDN) du pool et le paramètre WebServer, l’applet de commande renvoie les services web que votre serveur met à disposition, y compris les URI de développement du gestionnaire de carnet d’adresses et de la liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="017e6-107">By defining the pool’s fully qualified domain name (FQDN) and the parameter WebServer, the cmdlet returns the web-based services offered by your server, including the Address Book handler and distribution list expansion URIs.</span></span>

<span data-ttu-id="017e6-108">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="017e6-108">For example:</span></span>

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

<span data-ttu-id="017e6-109">L’applet de commande renvoie ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="017e6-109">This cmdlet returns the following:</span></span>

<span data-ttu-id="017e6-110">Identity : serveur :pool01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="017e6-110">Identity : WebServer:pool01.contoso.net</span></span>

<span data-ttu-id="017e6-111">:DC01 : cache de sous-magasin. contoso. net</span><span class="sxs-lookup"><span data-stu-id="017e6-111">FileStore : FileStore:dc01.contoso.net</span></span>

<span data-ttu-id="017e6-112">UserServer : UserServer :pool01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="017e6-112">UserServer : UserServer:pool01.contoso.net</span></span>

<span data-ttu-id="017e6-113">PrimaryHttpPort : 80</span><span class="sxs-lookup"><span data-stu-id="017e6-113">PrimaryHttpPort : 80</span></span>

<span data-ttu-id="017e6-114">PrimaryHttpsPort : 443</span><span class="sxs-lookup"><span data-stu-id="017e6-114">PrimaryHttpsPort : 443</span></span>

<span data-ttu-id="017e6-115">ExternalHttpPort : 8080</span><span class="sxs-lookup"><span data-stu-id="017e6-115">ExternalHttpPort : 8080</span></span>

<span data-ttu-id="017e6-116">ExternalHttpsPort : 4443</span><span class="sxs-lookup"><span data-stu-id="017e6-116">ExternalHttpsPort : 4443</span></span>

<span data-ttu-id="017e6-117">PublishedPrimaryHttpPort : 80</span><span class="sxs-lookup"><span data-stu-id="017e6-117">PublishedPrimaryHttpPort : 80</span></span>

<span data-ttu-id="017e6-118">PublishedPrimaryHttpsPort : 443</span><span class="sxs-lookup"><span data-stu-id="017e6-118">PublishedPrimaryHttpsPort : 443</span></span>

<span data-ttu-id="017e6-119">PublishedExternalHttpPort : 80</span><span class="sxs-lookup"><span data-stu-id="017e6-119">PublishedExternalHttpPort : 80</span></span>

<span data-ttu-id="017e6-120">PublishedExternalHttpsPort : 443</span><span class="sxs-lookup"><span data-stu-id="017e6-120">PublishedExternalHttpsPort : 443</span></span>

<span data-ttu-id="017e6-121">ReachPrimaryPsomServerPort : 8060</span><span class="sxs-lookup"><span data-stu-id="017e6-121">ReachPrimaryPsomServerPort : 8060</span></span>

<span data-ttu-id="017e6-122">ReachExternalPsomServerPort : 8061</span><span class="sxs-lookup"><span data-stu-id="017e6-122">ReachExternalPsomServerPort : 8061</span></span>

<span data-ttu-id="017e6-123">AppSharingPortStart : 49152</span><span class="sxs-lookup"><span data-stu-id="017e6-123">AppSharingPortStart : 49152</span></span>

<span data-ttu-id="017e6-124">AppSharingPortCount : 16383</span><span class="sxs-lookup"><span data-stu-id="017e6-124">AppSharingPortCount : 16383</span></span>

<span data-ttu-id="017e6-125">LIServiceInternalUri :https://internalweb.contoso.net/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="017e6-125">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span></span>

<span data-ttu-id="017e6-126">ABHandlerInternalUri :https://internalweb.contoso.net/abs/handler</span><span class="sxs-lookup"><span data-stu-id="017e6-126">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span></span>

<span data-ttu-id="017e6-127">ABHandlerExternalUri :https://csweb.contoso.com/abs/handler</span><span class="sxs-lookup"><span data-stu-id="017e6-127">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span></span>

<span data-ttu-id="017e6-128">DLExpansionInternalUri :https://internalweb.contoso.net/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="017e6-128">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span></span>

<span data-ttu-id="017e6-129">DLExpansionExternalUri :https://csweb.contoso.com/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="017e6-129">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span></span>

<span data-ttu-id="017e6-130">CAHandlerInternalUri :https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="017e6-130">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="017e6-131">CAHandlerInternalAnonUri :http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="017e6-131">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="017e6-132">CollabContentInternalUri :https://internalweb.contoso.net/CollabContent</span><span class="sxs-lookup"><span data-stu-id="017e6-132">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span></span>

<span data-ttu-id="017e6-133">CollabContentExternalUri :https://csweb.contoso.com/CollabContent</span><span class="sxs-lookup"><span data-stu-id="017e6-133">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span></span>

<span data-ttu-id="017e6-134">CAHandlerExternalUri :https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="017e6-134">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="017e6-135">DeviceUpdateDownloadInternalUri :https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="017e6-135">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span></span>

<span data-ttu-id="017e6-136">DeviceUpdateDownloadExternalUri :https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="017e6-136">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span></span>

<span data-ttu-id="017e6-137">DeviceUpdateStoreInternalUri :http://internalweb.contoso.net/RequestHandler/Files</span><span class="sxs-lookup"><span data-stu-id="017e6-137">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span></span>

<span data-ttu-id="017e6-138">DeviceUpdateStoreExternalUri :https://csweb.contoso.com/RequestHandlerExt/Files</span><span class="sxs-lookup"><span data-stu-id="017e6-138">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span></span>

<span data-ttu-id="017e6-139">RgsAgentServiceInternalUri :https://internalweb.contoso.net/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="017e6-139">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="017e6-140">RgsAgentServiceExternalUri :https://csweb.contoso.com/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="017e6-140">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="017e6-141">MeetExternalUri :https://csweb.contoso.com/Meet</span><span class="sxs-lookup"><span data-stu-id="017e6-141">MeetExternalUri : https://csweb.contoso.com/Meet</span></span>

<span data-ttu-id="017e6-142">DialinExternalUri :https://csweb.contoso.com/Dialin</span><span class="sxs-lookup"><span data-stu-id="017e6-142">DialinExternalUri : https://csweb.contoso.com/Dialin</span></span>

<span data-ttu-id="017e6-143">CscpInternalUri :https://internalweb.contoso.net/Cscp</span><span class="sxs-lookup"><span data-stu-id="017e6-143">CscpInternalUri : https://internalweb.contoso.net/Cscp</span></span>

<span data-ttu-id="017e6-144">ReachExternalUri :https://csweb.contoso.com/Reach</span><span class="sxs-lookup"><span data-stu-id="017e6-144">ReachExternalUri : https://csweb.contoso.com/Reach</span></span>

<span data-ttu-id="017e6-145">ReachInternalUri :https://internalweb.contoso.net/Reach</span><span class="sxs-lookup"><span data-stu-id="017e6-145">ReachInternalUri : https://internalweb.contoso.net/Reach</span></span>

<span data-ttu-id="017e6-146">WebTicketExternalUri :https://csweb.contoso.com/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="017e6-146">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="017e6-147">WebTicketInternalUri :https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="017e6-147">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="017e6-148">ExternalFqdn : csweb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="017e6-148">ExternalFqdn : csweb.contoso.com</span></span>

<span data-ttu-id="017e6-149">InternalFqdn : internalweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="017e6-149">InternalFqdn : internalweb.contoso.net</span></span>

<span data-ttu-id="017e6-150">DependentServiceList : {serveur d’inscriptions :pool01. contoso. net, conferenceserver :pool01. contoso. net}</span><span class="sxs-lookup"><span data-stu-id="017e6-150">DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}</span></span>

<span data-ttu-id="017e6-151">ServiceId : 1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="017e6-151">ServiceId : 1-WebServices-1</span></span>

<span data-ttu-id="017e6-152">SiteId : site : Redmond</span><span class="sxs-lookup"><span data-stu-id="017e6-152">SiteId : Site:Redmond</span></span>

<span data-ttu-id="017e6-153">PoolFqdn : pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="017e6-153">PoolFqdn : pool01.contoso.net</span></span>

<span data-ttu-id="017e6-154">Version : 5</span><span class="sxs-lookup"><span data-stu-id="017e6-154">Version : 5</span></span>

<span data-ttu-id="017e6-155">Rôle : webserver</span><span class="sxs-lookup"><span data-stu-id="017e6-155">Role : WebServer</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="017e6-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="017e6-156">See Also</span></span>


[<span data-ttu-id="017e6-157">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="017e6-157">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


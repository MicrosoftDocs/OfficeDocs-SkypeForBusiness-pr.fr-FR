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

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a>Get-CsService pour la gestion du carnet d’adresses dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Qui peut exécuter cette applet de commande : par défaut, les membres des groupes suivants sont autorisés à exécuter l’applet de commande Get-CsService localement : RTCUniversalUserAdmins, RTCUniversalServerAdmins. Pour renvoyer la liste de tous les rôles de contrôle d’accès basés sur des rôles (RBAC) affectés à cette applet de commande (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de l’invite Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

Get-CsService est utile pour récupérer et afficher la configuration actuelle des services Web définis de votre infrastructure. En définissant le nom de domaine complet (FQDN) du pool et le serveur de noms WebServer, l’applet de passe renvoie les services Web proposés par votre serveur, y compris le gestionnaire du carnet d’adresses et les URI d’extension de liste de distribution.

Par exemple :

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

Cette applet de commande renvoie ce qui suit :

Identité : serveur :pool01. contoso. net

:DC01 :%. contoso. net

UserServer : UserServer :pool01. contoso. net

PrimaryHttpPort : 80

PrimaryHttpsPort : 443

ExternalHttpPort : 8080

ExternalHttpsPort : 4443

PublishedPrimaryHttpPort : 80

PublishedPrimaryHttpsPort : 443

PublishedExternalHttpPort : 80

PublishedExternalHttpsPort : 443

ReachPrimaryPsomServerPort : 8060

ReachExternalPsomServerPort : 8061

AppSharingPortStart : 49152

AppSharingPortCount : 16383

LIServiceInternalUri :https://internalweb.contoso.net/locationinformation/liservice.svc

ABHandlerInternalUri :https://internalweb.contoso.net/abs/handler

ABHandlerExternalUri :https://csweb.contoso.com/abs/handler

DLExpansionInternalUri :https://internalweb.contoso.net/groupexpansion/service.svc

DLExpansionExternalUri :https://csweb.contoso.com/groupexpansion/service.svc

CAHandlerInternalUri :https://internalweb.contoso.net/CertProv/CertProvisioningService.svc

CAHandlerInternalAnonUri :http://internalweb.contoso.net/CertProv/CertProvisioningService.svc

CollabContentInternalUri :https://internalweb.contoso.net/CollabContent

CollabContentExternalUri :https://csweb.contoso.com/CollabContent

CAHandlerExternalUri :https://csweb.contoso.com/CertProv/CertProvisioningService.svc

DeviceUpdateDownloadInternalUri :https://internalweb.contoso.net/RequestHandler/ucdevice.upx

DeviceUpdateDownloadExternalUri :https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx

DeviceUpdateStoreInternalUri :http://internalweb.contoso.net/RequestHandler/Files

DeviceUpdateStoreExternalUri :https://csweb.contoso.com/RequestHandlerExt/Files

RgsAgentServiceInternalUri :https://internalweb.contoso.net/RgsClients/AgentService.svc

RgsAgentServiceExternalUri :https://csweb.contoso.com/RgsClients/AgentService.svc

MeetExternalUri :https://csweb.contoso.com/Meet

DialinExternalUri :https://csweb.contoso.com/Dialin

CscpInternalUri :https://internalweb.contoso.net/Cscp

ReachExternalUri :https://csweb.contoso.com/Reach

ReachInternalUri :https://internalweb.contoso.net/Reach

WebTicketExternalUri :https://csweb.contoso.com/WebTicket/WebTicketService.svc

WebTicketInternalUri :https://internalweb.contoso.net/WebTicket/WebTicketService.svc

ExternalFqdn : csweb.contoso.com

InternalFqdn : internalweb.contoso.net

DependentServiceList : {Registrar :pool01. contoso. net ConferencingServer :pool01. contoso. net}

ServiceId : 1-WebServices-1

SiteId : site : Redmond

PoolFqdn : pool01.contoso.net

Version : 5

Rôle : webserver

<div>

## <a name="see-also"></a>Voir aussi


[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


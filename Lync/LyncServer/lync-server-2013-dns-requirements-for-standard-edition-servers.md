---
title: 'Lync Server 2013 : configuration DNS requise pour les serveurs Standard Edition Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Standard Edition servers
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425900(v=OCS.15)
ms:contentKeyID: 48183920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2064181a7c4d60015905d5974ac01378b7d025e2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="ab11e-102">Configuration DNS requise pour les serveurs Standard Edition Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab11e-102">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab11e-103">_**Dernière modification de la rubrique :** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="ab11e-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="ab11e-104">Cette section décrit les enregistrements DNS (Domain Name System) requis pour le déploiement de serveurs Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ab11e-104">This section describes the Domain Name System (DNS) records that are required for deployment of Standard Edition servers.</span></span>

<div>

## <a name="dns-records-for-standard-edition-servers"></a><span data-ttu-id="ab11e-105">Enregistrements DNS requis pour les serveurs Standard Edition</span><span class="sxs-lookup"><span data-stu-id="ab11e-105">DNS Records for Standard Edition Servers</span></span>

<span data-ttu-id="ab11e-106">Le tableau suivant spécifie les exigences DNS pour le déploiement de Lync Server 2013 Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="ab11e-106">The following table specifies DNS requirements for Lync Server 2013 Standard Edition server deployment.</span></span>

### <a name="dns-requirements-for-a-standard-edition-server"></a><span data-ttu-id="ab11e-107">Enregistrements DNS requis pour les serveurs Standard Edition</span><span class="sxs-lookup"><span data-stu-id="ab11e-107">DNS Requirements for a Standard Edition Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab11e-108">Scénario de déploiement</span><span class="sxs-lookup"><span data-stu-id="ab11e-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="ab11e-109">Enregistrement DNS requis</span><span class="sxs-lookup"><span data-stu-id="ab11e-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab11e-110">Serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="ab11e-110">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="ab11e-111">Enregistrement A interne associant le nom de domaine complet (FQDN) du serveur à son adresse IP.</span><span class="sxs-lookup"><span data-stu-id="ab11e-111">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab11e-112">Ouverture de session client automatique</span><span class="sxs-lookup"><span data-stu-id="ab11e-112">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="ab11e-113">Pour chaque domaine SIP pris en charge, un enregistrement SRV pour _sipinternaltls. _tcp. &lt;domaine&gt; sur le port 5061 qui correspond au nom de domaine complet (FQDN) du serveur Standard Edition qui authentifie et redirige les demandes client de connexion.</span><span class="sxs-lookup"><span data-stu-id="ab11e-113">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Standard Edition server that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="ab11e-114">Pour plus d’informations, consultez la rubrique <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS Requirements for Automatic client Sign-in dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ab11e-114">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab11e-115">Détection du service web de mise à jour des périphériques par les périphériques de communications unifiées</span><span class="sxs-lookup"><span data-stu-id="ab11e-115">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="ab11e-116">Un enregistrement A interne portant le nom ucupdates-r2. &lt;Domaine&gt; SIP qui est résolu en adresse IP du service Web de mise à jour des périphériques hébergeant le serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ab11e-116">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Standard Edition server hosting Device Update Web service.</span></span> <span data-ttu-id="ab11e-117">Dans le cas où un périphérique de communications unifiées est activé, alors qu’un utilisateur ne s’y est jamais connecté, l’enregistrement A permet au périphérique de détecter le serveur hébergeant le service web de mise à jour des périphériques et d’obtenir des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="ab11e-117">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the server hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="ab11e-118">Les périphériques peuvent autrement se procurer ces informations via une mise en service de la bande entrante la première fois qu’un utilisateur se connecte.</span><span class="sxs-lookup"><span data-stu-id="ab11e-118">Otherwise, devices obtain the server information though in-band provisioning the first time a user logs in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab11e-119">Proxy inverse de prise en charge du trafic HTTP</span><span class="sxs-lookup"><span data-stu-id="ab11e-119">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="ab11e-120">Enregistrement A externe qui résout le nom de domaine complet de la batterie de serveurs web externes en adresse IP externe du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="ab11e-120">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="ab11e-121">Les clients et les périphériques de communications unifiées utilisent cet enregistrement pour se connecter au proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="ab11e-121">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="ab11e-122">Pour plus d’informations, reportez-vous à la rubrique <a href="lync-server-2013-determine-dns-requirements.md">determine DNS Requirements for Lync Server 2013</a> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="ab11e-122">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


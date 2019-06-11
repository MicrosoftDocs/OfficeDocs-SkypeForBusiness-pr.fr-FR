---
title: 'Lync Server 2013: configuration requise pour DNS pour les serveurs de chat permanent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Persistent Chat Servers
ms:assetid: f7531374-d7ed-4b63-ae81-02294cb4496a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205391(v=OCS.15)
ms:contentKeyID: 48185857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1f52fde1ee1034f453fe62f2aa3aa44d04b389c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-persistent-chat-servers-in-lync-server-2013"></a><span data-ttu-id="7e5e6-102">Configuration DNS requise pour les serveurs de chat permanent dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e5e6-102">DNS requirements for Persistent Chat Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e5e6-103">_**Dernière modification de la rubrique:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="7e5e6-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="7e5e6-104">Cette section décrit les enregistrements DNS (Domain Name System) requis pour le déploiement de serveurs de chat permanents.</span><span class="sxs-lookup"><span data-stu-id="7e5e6-104">This section describes the Domain Name System (DNS) records that are required for deployment of Persistent Chat Servers.</span></span>

<div>

## <a name="dns-records-for-persistent-chat-servers"></a><span data-ttu-id="7e5e6-105">Enregistrements DNS pour les serveurs de chat permanent</span><span class="sxs-lookup"><span data-stu-id="7e5e6-105">DNS Records for Persistent Chat Servers</span></span>

<span data-ttu-id="7e5e6-106">Le tableau suivant indique les exigences DNS pour le déploiement d’un serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="7e5e6-106">The following table specifies DNS requirements for Persistent Chat Server deployment.</span></span>

### <a name="dns-requirements-for-a-persistent-chat-server"></a><span data-ttu-id="7e5e6-107">Configuration DNS requise pour un serveur de chat permanent</span><span class="sxs-lookup"><span data-stu-id="7e5e6-107">DNS Requirements for a Persistent Chat Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e5e6-108">Scénario de déploiement</span><span class="sxs-lookup"><span data-stu-id="7e5e6-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="7e5e6-109">Enregistrement DNS requis</span><span class="sxs-lookup"><span data-stu-id="7e5e6-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e5e6-110">Un serveur de chat permanent</span><span class="sxs-lookup"><span data-stu-id="7e5e6-110">One Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="7e5e6-111">Un enregistrement interne A qui associe le nom de domaine complet (FQDN) du serveur à son adresse IP.</span><span class="sxs-lookup"><span data-stu-id="7e5e6-111">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e5e6-112">Pool de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="7e5e6-112">Persistent Chat pool</span></span></p></td>
<td><p><span data-ttu-id="7e5e6-113">Un enregistrement A interne qui résout le nom de domaine complet (FQDN) des serveurs à son adresse IP.</span><span class="sxs-lookup"><span data-stu-id="7e5e6-113">An internal A record that resolves the fully qualified domain name (FQDN) of the servers to its IP address.</span></span></p>
<p><span data-ttu-id="7e5e6-114"><strong>Exemple</strong></span><span class="sxs-lookup"><span data-stu-id="7e5e6-114"><strong>Example</strong></span></span></p>
<p><span data-ttu-id="7e5e6-115">PersistentChatServer01.contoso.com 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="7e5e6-115">PersistentChatServer01.contoso.com     10.10.10.1</span></span></p>
<p><span data-ttu-id="7e5e6-116">PersistentChatServer02.contoso.com 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="7e5e6-116">PersistentChatServer02.contoso.com     10.10.10.2</span></span></p>
<p><span data-ttu-id="7e5e6-117">Un enregistrement A interne qui résout le nom de domaine complet (FQDN) des serveurs à son adresse IP.</span><span class="sxs-lookup"><span data-stu-id="7e5e6-117">An internal A record that resolves the fully qualified domain name (FQDN) of the servers to its IP address.</span></span></p>
<p><span data-ttu-id="7e5e6-118"><strong>Exemple</strong></span><span class="sxs-lookup"><span data-stu-id="7e5e6-118"><strong>Example</strong></span></span></p>
<p><span data-ttu-id="7e5e6-119">PersistentChatPool.contoso.com 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="7e5e6-119">PersistentChatPool.contoso.com    10.10.10.1</span></span></p>
<p><span data-ttu-id="7e5e6-120">PersistentChatPool.contoso.com 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="7e5e6-120">PersistentChatPool.contoso.com    10.10.10.2</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


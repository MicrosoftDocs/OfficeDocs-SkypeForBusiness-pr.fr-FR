---
title: 'Lync Server 2013: valider les paramètres système de nom de domaine pour l’équilibrage de charge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d56219dc36859eb37a766a94f827fb0c28a9909
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="cc417-102">Valider les paramètres système de nom de domaine pour l’équilibrage de charge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc417-102">Validate Domain Name System settings for load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc417-103">_**Dernière modification de la rubrique:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="cc417-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="cc417-104">Pour prendre en charge le FQDN utilisé par l’équilibrage de charge DNS, vous devez configurer le système DNS pour résoudre le nom de domaine complet (par exemple, pool01.contoso.com) pour les adresses IP de tous les serveurs du pool (par exemple, 192.168.1.1, 192.168.1.2, etc.).</span><span class="sxs-lookup"><span data-stu-id="cc417-104">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span> <span data-ttu-id="cc417-105">Vous ne devez inclure que les adresses IP des serveurs actuellement déployés.</span><span class="sxs-lookup"><span data-stu-id="cc417-105">You should include only the IP addresses of servers that are currently deployed.</span></span>

<span data-ttu-id="cc417-106">Par ailleurs, si vous utilisez l’équilibrage de charge DNS pour les pools Edge, les entrées DNS suivantes sont nécessaires:</span><span class="sxs-lookup"><span data-stu-id="cc417-106">Additionally if you are using DNS load balancing for the Edge pools the following DNS entries are required:</span></span>

  - <span data-ttu-id="cc417-107">Pour le service Edge d’accès de Lync Server, vous devez disposer d’une entrée pour chaque serveur dans le pool.</span><span class="sxs-lookup"><span data-stu-id="cc417-107">For the Lync Server Access Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="cc417-108">Chaque entrée doit résoudre le nom de domaine complet du service Edge d’accès de Lync Server (par exemple, sip.contoso.com) en adresse IP du service Edge d’accès de Lync Server sur l’un des serveurs Edge du pool.</span><span class="sxs-lookup"><span data-stu-id="cc417-108">Each entry must resolve the FQDN of the Lync Server Access Edge service (for example, sip.contoso.com) to the IP address of the Lync Server Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="cc417-109">Pour le service Edge de conférence Web Lync Server, vous devez disposer d’une entrée pour chaque serveur du pool.</span><span class="sxs-lookup"><span data-stu-id="cc417-109">For the Lync Server Web Conferencing Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="cc417-110">Chaque entrée doit résoudre le nom de domaine complet (par exemple, webconf.contoso.com) du service Edge de conférence Web de Lync Server (par exemple,) à l’adresse IP du service Edge de conférence Web de Lync Server sur l’un des serveurs Edge du pool.</span><span class="sxs-lookup"><span data-stu-id="cc417-110">Each entry must resolve the FQDN of the Lync Server Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Lync Server Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="cc417-111">Pour le service Edge audio/vidéo de Lync Server, vous devez disposer d’une entrée pour chaque serveur dans le pool.</span><span class="sxs-lookup"><span data-stu-id="cc417-111">For the Lync Server Audio/Video Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="cc417-112">Chaque entrée doit résoudre le nom de domaine complet (par exemple, av.contoso.com) de l’adresse IP du serveur Lync Server audio/vidéo de Lync Server sur l’un des serveurs Edge du pool.</span><span class="sxs-lookup"><span data-stu-id="cc417-112">Each entry must resolve the FQDN of the Lync Server Audio/Video Edge service (for example, av.contoso.com) to the IP address of the Lync Server Audio/Video Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="cc417-113">Si vous souhaitez utiliser l’équilibrage de charge DNS sur l’interface interne du pool de bords, vous devez ajouter un enregistrement DNS, qui résout le nom de domaine complet (FQDN) du pool Edge vers l’adresse IP de chaque serveur du pool.</span><span class="sxs-lookup"><span data-stu-id="cc417-113">If you want to use DNS load balancing on the internal interface of the Edge pool, you must add one DNS record, which resolves the internal FQDN of the Edge pool to the IP address of each server in the pool.</span></span>

<span data-ttu-id="cc417-114">Pour vérifier que le DNS renvoie les valeurs correctes pour l’équilibrage de charge DNS, vous devez utiliser l’outil Nslookup.</span><span class="sxs-lookup"><span data-stu-id="cc417-114">To verify that DNS is returning the correct values for DNS load balancing you should use the nslookup tool.</span></span> <span data-ttu-id="cc417-115">Pour renvoyer toutes les valeurs d’un enregistrement DNS avec nslookup, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="cc417-115">To return all values for a DNS record with nslookup you should run the command:</span></span>

`nslookup <FQDN >`

<span data-ttu-id="cc417-116">Exécutez cette commande pour chaque nom de domaine complet utilisé dans la configuration de l’équilibrage de charge DNS pour vérifier que chaque jeu d’enregistrements pour l’équilibrage de charge DNS a renvoyé toutes les entrées correctes.</span><span class="sxs-lookup"><span data-stu-id="cc417-116">You would run this command for every FQDN used in DNS load balancing configuration to verify that every record set for DNS load balancing returned all of the correct entries.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


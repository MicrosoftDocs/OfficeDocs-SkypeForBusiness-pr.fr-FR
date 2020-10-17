---
title: 'Lync Server 2013 : validation des paramètres système de nom de domaine pour l’équilibrage de charge'
description: 'Lync Server 2013 : validation des paramètres système de nom de domaine pour l’équilibrage de charge.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a218a79a541e9c9705a8403146fe7e134e8ed827
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547230"
---
# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="ec46d-103">Valider les paramètres système de nom de domaine pour l’équilibrage de charge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec46d-103">Validate Domain Name System settings for load balancing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec46d-104">_**Dernière modification de la rubrique :** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="ec46d-104">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="ec46d-p101">Pour prendre en charge le nom de domaine complet utilisé par l’équilibrage de la charge DNS, vous devez mettre en service DNS pour résoudre le nom de domaine complet du pool (par exemple, pool01.contoso.com) en adresse IP pour chaque serveur dans le pool (par exemple, 192.168.1.1, 192.168.1.2, etc.). Veillez à inclure uniquement les adresses IP des serveurs en cours de déploiement.</span><span class="sxs-lookup"><span data-stu-id="ec46d-p101">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>

<span data-ttu-id="ec46d-107">En outre, si vous utilisez l’équilibrage de charge DNS pour les pools de serveurs Edge, les entrées DNS suivantes sont requises :</span><span class="sxs-lookup"><span data-stu-id="ec46d-107">Additionally if you are using DNS load balancing for the Edge pools the following DNS entries are required:</span></span>

  - <span data-ttu-id="ec46d-108">Pour le service Edge d’accès Lync Server, vous devez disposer d’une entrée pour chaque serveur dans le pool.</span><span class="sxs-lookup"><span data-stu-id="ec46d-108">For the Lync Server Access Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="ec46d-109">Chaque entrée doit résoudre le nom de domaine complet (FQDN) du service Edge d’accès Lync Server (par exemple, sip.contoso.com) en adresse IP du service Edge d’accès Lync Server sur l’un des serveurs Edge du pool.</span><span class="sxs-lookup"><span data-stu-id="ec46d-109">Each entry must resolve the FQDN of the Lync Server Access Edge service (for example, sip.contoso.com) to the IP address of the Lync Server Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="ec46d-110">Pour le service Edge de conférence Web Lync Server, vous devez disposer d’une entrée pour chaque serveur dans le pool.</span><span class="sxs-lookup"><span data-stu-id="ec46d-110">For the Lync Server Web Conferencing Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="ec46d-111">Chaque entrée doit résoudre le nom de domaine complet (FQDN) du service Edge de conférence Web Lync Server (par exemple, webconf.contoso.com) en adresse IP du service Edge de conférence Web Lync Server sur l’un des serveurs Edge du pool.</span><span class="sxs-lookup"><span data-stu-id="ec46d-111">Each entry must resolve the FQDN of the Lync Server Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Lync Server Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="ec46d-112">Pour le service Edge audio/vidéo Lync Server, vous devez disposer d’une entrée pour chaque serveur dans le pool.</span><span class="sxs-lookup"><span data-stu-id="ec46d-112">For the Lync Server Audio/Video Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="ec46d-113">Chaque entrée doit résoudre le nom de domaine complet (FQDN) du service Edge audio/vidéo Lync Server (par exemple, av.contoso.com) en adresse IP du service Edge audio/vidéo Lync Server sur l’un des serveurs Edge du pool.</span><span class="sxs-lookup"><span data-stu-id="ec46d-113">Each entry must resolve the FQDN of the Lync Server Audio/Video Edge service (for example, av.contoso.com) to the IP address of the Lync Server Audio/Video Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="ec46d-114">Si vous souhaitez utiliser l’équilibrage de charge DNS sur l’interface interne du pool de serveurs Edge, vous devez ajouter un enregistrement DNS, ce qui permet de résoudre le nom de domaine complet interne du pool de serveurs Edge en adresse IP de chaque serveur du pool.</span><span class="sxs-lookup"><span data-stu-id="ec46d-114">If you want to use DNS load balancing on the internal interface of the Edge pool, you must add one DNS record, which resolves the internal FQDN of the Edge pool to the IP address of each server in the pool.</span></span>

<span data-ttu-id="ec46d-115">Pour vérifier que DNS renvoie les valeurs correctes pour l’équilibrage de la charge DNS, vous devez utiliser l’outil Nslookup.</span><span class="sxs-lookup"><span data-stu-id="ec46d-115">To verify that DNS is returning the correct values for DNS load balancing you should use the nslookup tool.</span></span> <span data-ttu-id="ec46d-116">Pour renvoyer toutes les valeurs d’un enregistrement DNS avec nslookup, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ec46d-116">To return all values for a DNS record with nslookup you should run the command:</span></span>

`nslookup <FQDN >`

<span data-ttu-id="ec46d-117">Vous devez exécuter cette commande pour chaque nom de domaine complet utilisé dans la configuration de l’équilibrage de charge DNS pour vérifier que chaque jeu d’enregistrements pour l’équilibrage de charge DNS a renvoyé toutes les entrées correctes.</span><span class="sxs-lookup"><span data-stu-id="ec46d-117">You would run this command for every FQDN used in DNS load balancing configuration to verify that every record set for DNS load balancing returned all of the correct entries.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


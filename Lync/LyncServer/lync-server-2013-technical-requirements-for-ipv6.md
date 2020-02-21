---
title: Configuration technique requise pour Lync Server 2013 pour IPv6
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48185465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a5565080f2b5fab0f47cc944f9569f55e8721c4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="8f72e-102">Configuration technique requise pour IPv6 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f72e-102">Technical requirements for IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f72e-103">_**Dernière modification de la rubrique :** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="8f72e-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="8f72e-104">Si vous envisagez de configurer Lync Server 2013 pour IPv6, gardez les exigences suivantes à l’esprit :</span><span class="sxs-lookup"><span data-stu-id="8f72e-104">If you plan to configure Lync Server 2013 for IPv6, keep the following requirements in mind:</span></span>

  - <span data-ttu-id="8f72e-105">Pour utiliser des adresses IPv6 avec Lync Server, vous devez créer des enregistrements DNS (Domain Name System) pour les enregistrements qui doivent être découverts et résolus en adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="8f72e-105">To use IPv6 addresses with Lync Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="8f72e-106">Le DNS IPv6 utilise des enregistrements AAAA (quadruple A).</span><span class="sxs-lookup"><span data-stu-id="8f72e-106">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="8f72e-107">Si vous utilisez IPv4 et IPv6 dans votre déploiement, il est préférable de configurer et maintenir des enregistrements d’hôte A pour IPv4 et des enregistrements d’hôte AAAA pour IPv6.</span><span class="sxs-lookup"><span data-stu-id="8f72e-107">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="8f72e-108">Même lors de la transition complète de votre déploiement vers IPv6, vous pouvez également nécessiter des enregistrements d’hôte DNS IPv4 pour les utilisateurs externes utilisant encore IPv4.</span><span class="sxs-lookup"><span data-stu-id="8f72e-108">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="8f72e-109">Vous pouvez déployer les enregistrements d’hôte DNS IPv6 avant de commencer à utiliser IPv6.</span><span class="sxs-lookup"><span data-stu-id="8f72e-109">You can deploy IPv6 DNS host records before you start using IPv6.</span></span> <span data-ttu-id="8f72e-110">Si le client ou le serveur n’utilise pas IPv6, l’enregistrement ne sera pas référencé.</span><span class="sxs-lookup"><span data-stu-id="8f72e-110">If the client or server doesn't use IPv6, the record will not be referenced.</span></span> <span data-ttu-id="8f72e-111">Des technologies de transition décideront de l’enregistrement à utiliser, en fonction de la configuration des technologies de transition et des stratégies.</span><span class="sxs-lookup"><span data-stu-id="8f72e-111">Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>

  - <span data-ttu-id="8f72e-112">Chaque adresse IPv6 a une étendue.</span><span class="sxs-lookup"><span data-stu-id="8f72e-112">Each IPv6 address has a scope.</span></span> <span data-ttu-id="8f72e-113">Les trois étendues que vous pouvez utiliser pour l’adressage IPv6 sont des adresses globales IPv6 (similaires aux adresses IPv4 publiques), des adresses locales uniques IPv6 (similaires aux plages d’adresses IPv4 privées) et des adresses IPv6 lien-local (semblables aux adresses IP privées automatiques dans Windows Server pour IPv4).</span><span class="sxs-lookup"><span data-stu-id="8f72e-113">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="8f72e-114">Tous les serveurs au sein d’un pool doivent avoir des adresses IPv6 avec la même étendue.</span><span class="sxs-lookup"><span data-stu-id="8f72e-114">All the servers within a pool should have IPv6 addresses with the same scope.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8f72e-115">IPv6 est une rubrique complexe qui nécessite une planification soignée avec votre équipe réseau et votre fournisseur Internet afin de garantir que les adresses que vous affectez au niveau de Windows Server et de Lync Server 2013 fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="8f72e-115">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Lync Server 2013 level work as expected.</span></span> <span data-ttu-id="8f72e-116">Consultez les liens à la fin de cette rubrique pour accéder à des ressources supplémentaires sur l’adressage et la planification IPv6.</span><span class="sxs-lookup"><span data-stu-id="8f72e-116">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8f72e-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8f72e-117">See Also</span></span>


[<span data-ttu-id="8f72e-118">Architecture d’adressage IP version 6</span><span class="sxs-lookup"><span data-stu-id="8f72e-118">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="8f72e-119">Format d’adresse unicast global IPv6</span><span class="sxs-lookup"><span data-stu-id="8f72e-119">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="8f72e-120">Adresses unicast IPv6 locales uniques</span><span class="sxs-lookup"><span data-stu-id="8f72e-120">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


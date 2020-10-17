---
title: 'Lync Server 2013 : planification et configuration D’ipv6'
description: 'Lync Server 2013 : planification et configuration D’ipv6.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for and configuring IPv6
ms:assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204624(v=OCS.15)
ms:contentKeyID: 48183236
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c63268bd92fc9d3b683cfa05ab49f01ea56d6ba
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554360"
---
# <a name="planning-for-and-configuring-ipv6-in-lync-server-2013"></a><span data-ttu-id="854bc-103">Planification et configuration D’ipv6 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="854bc-103">Planning for and configuring IPv6 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="854bc-104">_**Dernière modification de la rubrique :** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="854bc-104">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="854bc-105">Lync Server 2013 inclut la prise en charge des adresses IP version 6 (IPv6), ainsi que la prise en charge continue des adresses IP version 4 (IPv4).</span><span class="sxs-lookup"><span data-stu-id="854bc-105">Lync Server 2013 includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> <span data-ttu-id="854bc-106">Les adresses IPv4 sont des adresses 32 bits qui permettent à un ordinateur de communiquer sur Internet.</span><span class="sxs-lookup"><span data-stu-id="854bc-106">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="854bc-107">En raison du nombre croissant d’appareils dans le monde entier, les adresses IPv4 disponibles ont expiré. De ce fait, de nombreux nouveaux appareils passent à l’aide d’adresses IPv6.</span><span class="sxs-lookup"><span data-stu-id="854bc-107">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="854bc-108">Les adresses IPv6 exécutent la même fonction que les adresses IPv4 (avec certaines fonctionnalités supplémentaires), mais au lieu d’utiliser uniquement 32 bits, les adresses IPv6 utilisent 128 bits.</span><span class="sxs-lookup"><span data-stu-id="854bc-108">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="854bc-109">Cela fournit non seulement un nouvel ensemble d’adresses, mais également un plus grand nombre d’adresses.</span><span class="sxs-lookup"><span data-stu-id="854bc-109">This provides not only a new set of addresses, but also a much larger number of them.</span></span> <span data-ttu-id="854bc-110">Une adresse IPv4 classique ressemble à ceci : 192.0.2.235, tandis qu’une adresse IPv6 se présente comme ceci : 2001:0DB8:85a3:0000:0000:8a2e : 0370:7334.</span><span class="sxs-lookup"><span data-stu-id="854bc-110">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="854bc-111">La modification de la mise en forme et des fonctionnalités pour les appareils qui utilisent des adresses IPv6 nécessite plusieurs considérations relatives au déploiement et à la configuration dans votre installation Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="854bc-111">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Lync Server 2013 installation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="854bc-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="854bc-112">In This Section</span></span>

  - [<span data-ttu-id="854bc-113">Vue d’ensemble des types d’adresses IP pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="854bc-113">Overview of IP address types for Lync Server 2013</span></span>](lync-server-2013-overview-of-ip-address-types.md)

  - [<span data-ttu-id="854bc-114">Configuration technique requise pour IPv6 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="854bc-114">Technical requirements for IPv6 in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-ipv6.md)

  - [<span data-ttu-id="854bc-115">Considérations relatives à la migration et à la coexistence pour IPv6 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="854bc-115">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>](lync-server-2013-migration-and-coexistence-considerations-for-ipv6.md)

  - [<span data-ttu-id="854bc-116">Configurer des types d’adresses IP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="854bc-116">Configure IP address types in Lync Server 2013</span></span>](lync-server-2013-configure-ip-address-types.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


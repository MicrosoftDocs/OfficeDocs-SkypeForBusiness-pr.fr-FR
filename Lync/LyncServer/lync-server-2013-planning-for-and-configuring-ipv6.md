---
title: 'Lync Server 2013 : planification et configuration du protocole IPv6'
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
ms.openlocfilehash: 05ca3b20d78d20f4c442edcb3a5722700c3e14a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-and-configuring-ipv6-in-lync-server-2013"></a><span data-ttu-id="bf2f1-102">Planification et configuration du protocole IPv6 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf2f1-102">Planning for and configuring IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf2f1-103">_**Dernière modification de la rubrique :** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="bf2f1-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="bf2f1-104">Lync Server 2013 inclut la prise en charge des adresses IP version 6 (IPv6), ainsi que la prise en charge de la prise en charge des adresses IP version 4 (IPv4).</span><span class="sxs-lookup"><span data-stu-id="bf2f1-104">Lync Server 2013 includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> <span data-ttu-id="bf2f1-105">Les adresses IPv4 sont des adresses 32 bits qui permettent aux ordinateurs de communiquer sur Internet.</span><span class="sxs-lookup"><span data-stu-id="bf2f1-105">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="bf2f1-106">En raison de l’augmentation du nombre d’appareils dans le monde entier, les adresses IPv4 disponibles sont épuisées. C’est la raison pour laquelle de nombreux nouveaux appareils sont déplacés vers l’adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="bf2f1-106">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="bf2f1-107">Les adresses IPv6 ont le même rôle que les adresses IPv4 (avec des fonctionnalités supplémentaires), mais au lieu d’utiliser uniquement 32 bits, les adresses IPv6 utilisent 128 bits.</span><span class="sxs-lookup"><span data-stu-id="bf2f1-107">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="bf2f1-108">Cela permet de nouvelles adresses, mais également un plus grand nombre d’adresses.</span><span class="sxs-lookup"><span data-stu-id="bf2f1-108">This provides not only a new set of addresses, but also a much larger number of them.</span></span> <span data-ttu-id="bf2f1-109">Une adresse IPv4 classique ressemble à ceci : 192.0.2.235, alors qu’une adresse IPv6 ressemble à ceci : 2001:0DB8:85a3:0000:0000:8a2e : 0370:7334.</span><span class="sxs-lookup"><span data-stu-id="bf2f1-109">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="bf2f1-110">La modification de la mise en forme et des fonctionnalités pour les appareils qui utilisent des adresses IPv6 nécessite plusieurs considérations de déploiement et de configuration dans votre installation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf2f1-110">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Lync Server 2013 installation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bf2f1-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="bf2f1-111">In This Section</span></span>

  - [<span data-ttu-id="bf2f1-112">Vue d’ensemble des types d’adresse IP pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf2f1-112">Overview of IP address types for Lync Server 2013</span></span>](lync-server-2013-overview-of-ip-address-types.md)

  - [<span data-ttu-id="bf2f1-113">Configuration technique requise pour IPv6 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf2f1-113">Technical requirements for IPv6 in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-ipv6.md)

  - [<span data-ttu-id="bf2f1-114">Remarques sur la migration et la coexistence pour IPv6 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf2f1-114">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>](lync-server-2013-migration-and-coexistence-considerations-for-ipv6.md)

  - [<span data-ttu-id="bf2f1-115">Configurer les types d’adresses IP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf2f1-115">Configure IP address types in Lync Server 2013</span></span>](lync-server-2013-configure-ip-address-types.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


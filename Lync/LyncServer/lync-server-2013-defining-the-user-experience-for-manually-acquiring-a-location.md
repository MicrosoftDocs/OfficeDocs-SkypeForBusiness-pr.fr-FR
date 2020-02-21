---
title: Définition de l’expérience utilisateur pour l’acquisition manuelle d’un emplacement
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the user experience for manually acquiring a location
ms:assetid: d37f67d3-e248-483b-b64c-3986559ef357
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398912(v=OCS.15)
ms:contentKeyID: 48185435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fb1d4a51179326f15999f05f2f80649d7b9dec8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="639ed-102">Définition de l’expérience utilisateur pour l’acquisition manuelle d’un emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="639ed-102">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="639ed-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="639ed-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="639ed-104">Si un client se trouve en dehors du réseau ou dans un sous-réseau non défini, l’utilisateur peut entrer manuellement un emplacement.</span><span class="sxs-lookup"><span data-stu-id="639ed-104">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location.</span></span> <span data-ttu-id="639ed-105">Toutefois, pendant un appel d’urgence, l’appel est d’abord acheminé vers un centre de réponse aux appels d’urgence (ECRC) national/régional E9-1-1, avant d’être acheminé vers un point de contrôle de la sécurité publique (PSAPI).</span><span class="sxs-lookup"><span data-stu-id="639ed-105">But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP).</span></span> <span data-ttu-id="639ed-106">L’ECRC interroge oralement l’appelant pour un emplacement, puis transfère l’appel vers le PSAPI approprié, en fonction des informations fournies.</span><span class="sxs-lookup"><span data-stu-id="639ed-106">The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span>

  - <span data-ttu-id="639ed-107">**Les utilisateurs doivent-ils être invités à entrer un emplacement lorsque l’utilisateur n’est pas fourni automatiquement par le service d’informations d’emplacement ?**</span><span class="sxs-lookup"><span data-stu-id="639ed-107">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>  
    <span data-ttu-id="639ed-108">Par exemple, si un client se trouve dans un sous-réseau non défini, à la maison, dans un hôtel ou ailleurs en dehors du réseau, l’utilisateur doit-il être invité à entrer un emplacement ?</span><span class="sxs-lookup"><span data-stu-id="639ed-108">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
    <span data-ttu-id="639ed-109">Vous pouvez configurer le paramètre **emplacement requis** dans la stratégie d’emplacement pour définir le comportement du client.</span><span class="sxs-lookup"><span data-stu-id="639ed-109">You can configure the **Location Required** setting in the location policy to define the client behavior.</span></span> <span data-ttu-id="639ed-110">La définition de cette valeur sur no signifie que l’utilisateur ne sera pas invité à entrer un emplacement.</span><span class="sxs-lookup"><span data-stu-id="639ed-110">Setting this value to No means that the user will not be prompted for a location.</span></span> <span data-ttu-id="639ed-111">La définition de cette valeur sur Yes signifie que l’utilisateur sera invité à entrer un emplacement, mais peut ignorer l’invite.</span><span class="sxs-lookup"><span data-stu-id="639ed-111">Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="639ed-112">La définition de cette valeur sur clause d’exclusion de responsabilité signifie que l’utilisateur est invité à entrer un emplacement et qu’il affiche une clause d’exclusion de responsabilité s’il tente de rejeter l’invite.</span><span class="sxs-lookup"><span data-stu-id="639ed-112">Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="639ed-113">Dans tous les cas, l’utilisateur peut continuer à utiliser le client comme d’habitude.</span><span class="sxs-lookup"><span data-stu-id="639ed-113">In all cases, the user can continue to use the client as usual.</span></span>

<span data-ttu-id="639ed-114">Lorsqu’un utilisateur entre un emplacement manuellement, l’emplacement est mappé à l’adresse MAC de la passerelle par défaut du réseau du client et est stocké dans une table par utilisateur située sur le client.</span><span class="sxs-lookup"><span data-stu-id="639ed-114">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client’s network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="639ed-115">Lorsque l’utilisateur revient à un emplacement précédemment stocké, le client Lync se définit automatiquement à cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="639ed-115">When the user returns to any previously stored location, the Lync client automatically sets itself to that location.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="639ed-116">Vous pouvez modifier uniquement l’emplacement actuel de votre client, mais vous pouvez également supprimer tous les emplacements stockés dans la table des utilisateurs locaux.</span><span class="sxs-lookup"><span data-stu-id="639ed-116">You can modify only the current location of your client, but you can also delete any location stored in the local user’s table.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


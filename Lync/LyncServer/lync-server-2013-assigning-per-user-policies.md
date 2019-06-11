---
title: 'Lync Server 2013: attribution de stratégies par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assigning per-user policies
ms:assetid: a4ed0120-d9e5-4eb2-acfd-8de2cb503652
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182561(v=OCS.15)
ms:contentKeyID: 48184971
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9088326d5d7a11bd186a594327eb083df590849
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-policies-in-lync-server-2013"></a><span data-ttu-id="fc340-102">Attribution de stratégies par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc340-102">Assigning per-user policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc340-103">_**Dernière modification de la rubrique:** 2012-10-14_</span><span class="sxs-lookup"><span data-stu-id="fc340-103">_**Topic Last Modified:** 2012-10-14_</span></span>

<span data-ttu-id="fc340-104">Vous pouvez affecter certaines stratégies à un utilisateur ou à un groupe d’utilisateurs afin de spécifier des paramètres spécifiques qui s’écartent des paramètres définis dans les stratégies affectées à d’autres utilisateurs, telles que les stratégies globales.</span><span class="sxs-lookup"><span data-stu-id="fc340-104">You can assign certain policies to a user or a group of users in order to specify particular settings that deviate from the settings defined in policies assigned to other users, such as global policies.</span></span> <span data-ttu-id="fc340-105">Ces stratégies s’appellent des politiques par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fc340-105">These policies are called per-user policies.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fc340-106">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="fc340-106">In This Section</span></span>

  - [<span data-ttu-id="fc340-107">Affecter une stratégie de conférence par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc340-107">Assign a per-user conferencing policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-conferencing-policy.md)

  - [<span data-ttu-id="fc340-108">Affecter une stratégie de version de client par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc340-108">Assign a per-user client version policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-client-version-policy.md)

  - [<span data-ttu-id="fc340-109">Affecter une stratégie de code confidentiel par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc340-109">Assign a per-user PIN policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-pin-policy.md)

  - [<span data-ttu-id="fc340-110">Attribution d’une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc340-110">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="fc340-111">Affecter une stratégie d’archivage par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc340-111">Assign a per-user archiving policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-archiving-policy.md)

  - [<span data-ttu-id="fc340-112">Affecter une stratégie d’emplacement par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc340-112">Assign a per-user location policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-location-policy.md)

  - [<span data-ttu-id="fc340-113">Affecter une stratégie de mobilité par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc340-113">Assign a per-user mobility policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-mobility-policy.md)

  - [<span data-ttu-id="fc340-114">Assigner une stratégie de discussion persistante par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc340-114">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-persistent-chat-policy.md)

  - [<span data-ttu-id="fc340-115">Affecter une stratégie de plan de numérotation par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc340-115">Assign a per-user dial plan policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-dial-plan-policy.md)

  - [<span data-ttu-id="fc340-116">Affecter une stratégie vocale par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc340-116">Assign a per-user voice policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-voice-policy.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fc340-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fc340-117">See Also</span></span>


[<span data-ttu-id="fc340-118">Gestion des utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc340-118">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


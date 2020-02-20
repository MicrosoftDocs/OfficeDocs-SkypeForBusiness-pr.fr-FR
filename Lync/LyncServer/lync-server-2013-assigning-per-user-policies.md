---
title: 'Lync Server 2013 : attribution de stratégies par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user policies
ms:assetid: a4ed0120-d9e5-4eb2-acfd-8de2cb503652
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182561(v=OCS.15)
ms:contentKeyID: 48184971
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acee046ebe05d87e17cd72ef1c5d8d19830d4ee8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-policies-in-lync-server-2013"></a><span data-ttu-id="9c181-102">Affectation de stratégies par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c181-102">Assigning per-user policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c181-103">_**Dernière modification de la rubrique :** 2012-10-14_</span><span class="sxs-lookup"><span data-stu-id="9c181-103">_**Topic Last Modified:** 2012-10-14_</span></span>

<span data-ttu-id="9c181-p101">Vous pouvez attribuer certaines stratégies à un utilisateur ou à un groupe d’utilisateurs pour spécifier des paramètres particuliers, qui divergent de ceux définis dans les stratégies attribuées aux autres utilisateurs, telles que les stratégies globales. Ces stratégies sont connues sous le terme de stratégies par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9c181-p101">You can assign certain policies to a user or a group of users in order to specify particular settings that deviate from the settings defined in policies assigned to other users, such as global policies. These policies are called per-user policies.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9c181-106">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="9c181-106">In This Section</span></span>

  - [<span data-ttu-id="9c181-107">Affecter une stratégie de conférence par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c181-107">Assign a per-user conferencing policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-conferencing-policy.md)

  - [<span data-ttu-id="9c181-108">Affecter une stratégie de version de client par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c181-108">Assign a per-user client version policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-client-version-policy.md)

  - [<span data-ttu-id="9c181-109">Affectation d’une stratégie de code confidentiel par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c181-109">Assign a per-user PIN policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-pin-policy.md)

  - [<span data-ttu-id="9c181-110">Affectation d’une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c181-110">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="9c181-111">Affectation d’une stratégie d’archivage par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c181-111">Assign a per-user archiving policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-archiving-policy.md)

  - [<span data-ttu-id="9c181-112">Affecter une stratégie d’emplacement par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c181-112">Assign a per-user location policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-location-policy.md)

  - [<span data-ttu-id="9c181-113">Attribuer une stratégie de mobilité par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c181-113">Assign a per-user mobility policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-mobility-policy.md)

  - [<span data-ttu-id="9c181-114">Affectation d’une stratégie de conversation permanente par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c181-114">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-persistent-chat-policy.md)

  - [<span data-ttu-id="9c181-115">Affectation d’une stratégie de plan de numérotation par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c181-115">Assign a per-user dial plan policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-dial-plan-policy.md)

  - [<span data-ttu-id="9c181-116">Affecter une stratégie de voix par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c181-116">Assign a per-user voice policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-voice-policy.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9c181-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9c181-117">See Also</span></span>


[<span data-ttu-id="9c181-118">Gestion des utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c181-118">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


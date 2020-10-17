---
title: Vérifier la fédération et l’accès à distance pour les utilisateurs externes
description: Vérifiez la Fédération et l’accès à distance pour les utilisateurs externes.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ac36f2e1b6c5ddfd889810ba2a3ab4d82b7ae33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555070"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="52f8d-103">Vérifier la fédération et l’accès à distance pour les utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="52f8d-103">Verify federation and remote access for external users</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52f8d-104">_**Dernière modification de la rubrique :** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="52f8d-104">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="52f8d-105">Après avoir effectué la transition de l’itinéraire de Fédération vers le serveur Edge Lync Server 2013, vous devez effectuer certains tests fonctionnels pour vérifier que la Fédération se comporte comme prévu.</span><span class="sxs-lookup"><span data-stu-id="52f8d-105">After transitioning the federation route to the Lync Server 2013 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="52f8d-106">Les tests relatifs à l’accès des utilisateurs externes doivent inclure chaque type d’utilisateur externe pris en charge par votre organisation, notamment une partie ou l’ensemble de ce qui suit.</span><span class="sxs-lookup"><span data-stu-id="52f8d-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="52f8d-107">Tester la connectivité des utilisateurs externes et de l’accès externe</span><span class="sxs-lookup"><span data-stu-id="52f8d-107">Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="52f8d-108">Utilisateurs d’au moins un domaine fédéré, un utilisateur interne sur Lync Server 2013 et un utilisateur sur Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="52f8d-108">Users from at least one federated domain, an internal user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="52f8d-109">Testez la messagerie instantanée, la présence, l’audio/vidéo (A/V) et le partage de Bureau.</span><span class="sxs-lookup"><span data-stu-id="52f8d-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="52f8d-110">Utilisateurs de chaque fournisseur de services de messagerie instantanée public pris en charge par votre organisation (et pour lequel le provisionnement a été effectué) communiquant avec un utilisateur sur Lync Server 2013 et un utilisateur sur Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="52f8d-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Lync Server 2010.</span></span>

  - <span data-ttu-id="52f8d-111">Vérifiez que les utilisateurs anonymes peuvent participer à des conférences.</span><span class="sxs-lookup"><span data-stu-id="52f8d-111">Verify that anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="52f8d-112">Un utilisateur hébergé sur Lync Server 2010 à l’aide de l’accès des utilisateurs distants (connexion à Lync Server 2010 depuis l’extérieur de l’intranet mais sans VPN) avec un utilisateur sur Lync Server 2013 et un utilisateur sur Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="52f8d-112">A user hosted on Lync Server 2010 using remote user access (logging into Lync Server 2010 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="52f8d-113">Testez la messagerie instantanée, la présence, l’audio/vidéo et le partage de Bureau.</span><span class="sxs-lookup"><span data-stu-id="52f8d-113">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="52f8d-114">Un utilisateur hébergé sur Lync Server 2013 à l’aide de l’accès des utilisateurs distants (connexion à Lync Server 2013 depuis l’extérieur de l’intranet mais sans VPN) avec un utilisateur sur Lync Server 2013 et un utilisateur sur Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="52f8d-114">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="52f8d-115">Testez la messagerie instantanée, la présence, l’audio/vidéo et le partage de Bureau.</span><span class="sxs-lookup"><span data-stu-id="52f8d-115">Test IM, presence, A/V, and desktop sharing.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


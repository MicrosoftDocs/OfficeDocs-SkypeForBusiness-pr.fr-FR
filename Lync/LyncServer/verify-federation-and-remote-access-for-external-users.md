---
title: Vérifier la fédération et l’accès à distance pour les utilisateurs externes
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 382c3e892f7e4d46b5c584e7efc0c03cc89531ac
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="aaa9c-102">Vérifier la fédération et l’accès à distance pour les utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="aaa9c-102">Verify federation and remote access for external users</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aaa9c-103">_**Dernière modification de la rubrique :** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="aaa9c-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="aaa9c-104">Après avoir effectué la transition de l’itinéraire de Fédération vers le serveur Edge Lync Server 2013, vous devez effectuer certains tests fonctionnels pour vérifier que la Fédération se comporte comme prévu.</span><span class="sxs-lookup"><span data-stu-id="aaa9c-104">After transitioning the federation route to the Lync Server 2013 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="aaa9c-105">Les tests relatifs à l’accès des utilisateurs externes doivent inclure chaque type d’utilisateur externe pris en charge par votre organisation, notamment une partie ou l’ensemble de ce qui suit.</span><span class="sxs-lookup"><span data-stu-id="aaa9c-105">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="aaa9c-106">Tester la connectivité des utilisateurs externes et de l’accès externe</span><span class="sxs-lookup"><span data-stu-id="aaa9c-106">Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="aaa9c-107">Utilisateurs d’au moins un domaine fédéré, un utilisateur interne sur Lync Server 2013 et un utilisateur sur Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aaa9c-107">Users from at least one federated domain, an internal user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="aaa9c-108">Testez la messagerie instantanée, la présence, l’audio/vidéo (A/V) et le partage de Bureau.</span><span class="sxs-lookup"><span data-stu-id="aaa9c-108">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="aaa9c-109">Utilisateurs de chaque fournisseur de services de messagerie instantanée public pris en charge par votre organisation (et pour lequel le provisionnement a été effectué) communiquant avec un utilisateur sur Lync Server 2013 et un utilisateur sur Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aaa9c-109">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Lync Server 2010.</span></span>

  - <span data-ttu-id="aaa9c-110">Vérifiez que les utilisateurs anonymes peuvent participer à des conférences.</span><span class="sxs-lookup"><span data-stu-id="aaa9c-110">Verify that anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="aaa9c-111">Un utilisateur hébergé sur Lync Server 2010 à l’aide de l’accès des utilisateurs distants (connexion à Lync Server 2010 depuis l’extérieur de l’intranet mais sans VPN) avec un utilisateur sur Lync Server 2013 et un utilisateur sur Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aaa9c-111">A user hosted on Lync Server 2010 using remote user access (logging into Lync Server 2010 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="aaa9c-112">Testez la messagerie instantanée, la présence, l’audio/vidéo et le partage de Bureau.</span><span class="sxs-lookup"><span data-stu-id="aaa9c-112">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="aaa9c-113">Un utilisateur hébergé sur Lync Server 2013 à l’aide de l’accès des utilisateurs distants (connexion à Lync Server 2013 depuis l’extérieur de l’intranet mais sans VPN) avec un utilisateur sur Lync Server 2013 et un utilisateur sur Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aaa9c-113">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="aaa9c-114">Testez la messagerie instantanée, la présence, l’audio/vidéo et le partage de Bureau.</span><span class="sxs-lookup"><span data-stu-id="aaa9c-114">Test IM, presence, A/V, and desktop sharing.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013 : gestion des appels vers des numéros non attribués'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing calls to unassigned numbers
ms:assetid: a45a7546-5ee6-4c1e-ab13-20a71a058f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688167(v=OCS.15)
ms:contentKeyID: 49733772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 571bddf8de62d7b22ac23a3b00de740030a2f7ca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-calls-to-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="3bc2e-102">Gestion des appels vers des numéros non attribués dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bc2e-102">Managing calls to unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bc2e-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3bc2e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3bc2e-104">Lync Server vous permet de configurer la gestion des appels téléphoniques entrants lorsque le numéro numéroté est valide pour votre organisation, mais qu’il n’est pas attribué à un utilisateur ou à un téléphone.</span><span class="sxs-lookup"><span data-stu-id="3bc2e-104">Lync Server lets you configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or phone.</span></span> <span data-ttu-id="3bc2e-105">Vous pouvez utiliser l’application annonce pour transférer ces appels vers une destination prédéfinie (numéro de téléphone, URI SIP ou messagerie vocale), ou pour lire une annonce audio ou les deux.</span><span class="sxs-lookup"><span data-stu-id="3bc2e-105">You can use the Announcement application to transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="3bc2e-106">Vous pouvez également transférer ces appels vers le numéro de téléphone du standard automatique de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="3bc2e-106">You can also transfer these calls to an Exchange UM Auto Attendant phone number.</span></span> <span data-ttu-id="3bc2e-107">Le fait de gérer les appels vers des numéros non attribués de l’une de ces manières vous permet d’éviter les situations dans lesquelles un appelant ne compose pas le numéro et entend une tonalité occupée, ou le client SIP reçoit un message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="3bc2e-107">Handling calls to unassigned numbers in one of these ways helps you avoid the situations in which a caller misdials and then hears a busy tone, or the SIP client receives an error message.</span></span>

<span data-ttu-id="3bc2e-108">Cette section explique comment gérer les plages de nombres non attribués pour gérer les appels vers des numéros de téléphone non attribués.</span><span class="sxs-lookup"><span data-stu-id="3bc2e-108">This section describes how to manage unassigned number ranges to handle calls to unassigned phone numbers.</span></span> <span data-ttu-id="3bc2e-109">Cette section décrit également comment gérer les annonces lors de la récupération après sinistre si vous souhaitez utiliser cette fonctionnalité en cas d’interruption.</span><span class="sxs-lookup"><span data-stu-id="3bc2e-109">The section also describes how to manage Announcements during disaster recovery if you want this functionality during an outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3bc2e-110">L’utilisation de la gestion des numéros non attribués lors d’une interruption est facultative.</span><span class="sxs-lookup"><span data-stu-id="3bc2e-110">Using unassigned number handling during an outage is optional.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3bc2e-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="3bc2e-111">In This Section</span></span>

  - [<span data-ttu-id="3bc2e-112">Créer une annonce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bc2e-112">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="3bc2e-113">Configurer les numéros de téléphone non affectés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bc2e-113">Configure unassigned phone numbers in Lync Server 2013</span></span>](lync-server-2013-configure-unassigned-phone-numbers.md)

  - [<span data-ttu-id="3bc2e-114">Gestion des annonces lors de la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bc2e-114">Manage announcements during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-announcements-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


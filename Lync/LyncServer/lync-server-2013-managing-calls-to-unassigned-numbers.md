---
title: 'Lync Server 2013 : gestion des appels à des numéros non attribués'
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
ms.openlocfilehash: 12809736c67a4ad606503a3a663532b51a1a191b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-calls-to-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="fd808-102">Gestion des appels à des numéros non attribués dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd808-102">Managing calls to unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd808-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="fd808-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="fd808-104">Lync Server vous permet de configurer la gestion des appels téléphoniques entrants lorsque le numéro composé est valide pour votre organisation, mais n’est pas affecté à un utilisateur ou à un téléphone.</span><span class="sxs-lookup"><span data-stu-id="fd808-104">Lync Server lets you configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or phone.</span></span> <span data-ttu-id="fd808-105">Vous pouvez utiliser l’application annonce pour transférer ces appels vers une destination prédéterminée (numéro de téléphone, URI SIP ou messagerie vocale), ou pour lire une annonce audio, ou les deux.</span><span class="sxs-lookup"><span data-stu-id="fd808-105">You can use the Announcement application to transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="fd808-106">Vous pouvez également transférer ces appels vers un numéro de téléphone de standard automatique de la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="fd808-106">You can also transfer these calls to an Exchange UM Auto Attendant phone number.</span></span> <span data-ttu-id="fd808-107">Gérer de cette manière les appels aux numéros non attribués permet d’éviter les situations dans lesquels un appelant ayant composé un numéro erroné entend une tonalité occupé ou dans lesquelles le client SIP reçoit un message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="fd808-107">Handling calls to unassigned numbers in one of these ways helps you avoid the situations in which a caller misdials and then hears a busy tone, or the SIP client receives an error message.</span></span>

<span data-ttu-id="fd808-p102">Cette section décrit comment gérer les plages de numéros non attribués pour gérer les appels aux numéros de téléphones non attribués. Elle décrit également comment gérer les annonces durant la récupération d’urgence si vous souhaitez bénéficier de cette fonctionnalité lors d’une panne.</span><span class="sxs-lookup"><span data-stu-id="fd808-p102">This section describes how to manage unassigned number ranges to handle calls to unassigned phone numbers. The section also describes how to manage Announcements during disaster recovery if you want this functionality during an outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fd808-110">La gestion des numéros de téléphones non attribués durant une panne est facultative.</span><span class="sxs-lookup"><span data-stu-id="fd808-110">Using unassigned number handling during an outage is optional.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fd808-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="fd808-111">In This Section</span></span>

  - [<span data-ttu-id="fd808-112">Créer une annonce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd808-112">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="fd808-113">Configurer les numéros de téléphone non attribués dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd808-113">Configure unassigned phone numbers in Lync Server 2013</span></span>](lync-server-2013-configure-unassigned-phone-numbers.md)

  - [<span data-ttu-id="fd808-114">Gérer les annonces lors de la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd808-114">Manage announcements during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-announcements-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


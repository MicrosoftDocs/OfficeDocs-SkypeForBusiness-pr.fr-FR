---
title: 'Lync Server 2013 : Forum aux questions sur la prise en charge des grandes réunions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c8d834bbd38cbfeeccc74e90bad6f11e47cc805
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a><span data-ttu-id="59703-102">Forum aux questions sur la prise en charge des grandes réunions pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59703-102">Large meeting support FAQ for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59703-103">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="59703-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="59703-104">Les sections suivantes apportent des réponses aux questions fréquemment posées sur la création et l’exécution de grandes réunions.</span><span class="sxs-lookup"><span data-stu-id="59703-104">The following sections provide answers to common questions for creating and running large meetings.</span></span>

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a><span data-ttu-id="59703-105">Q : Combien d’utilisateurs peuvent participer à une grande réunion ?</span><span class="sxs-lookup"><span data-stu-id="59703-105">Q: How many users can participate in a large meeting?</span></span>

<span data-ttu-id="59703-106">Le modèle utilisateur Lync Server spécifie des limites de 250 utilisateurs dans un pool partagé ou 1000 utilisateurs dans un pool dédié aux grandes réunions, mais ces chiffres représentent uniquement le nombre d’utilisateurs que nous avons testés et uniquement pour le jeu de matériel spécifique que nous avons utilisé lors de nos tests.</span><span class="sxs-lookup"><span data-stu-id="59703-106">The Lync Server user model specifies limits of 250 users in a shared pool or 1000 users in a pool dedicated to large meetings, but these numbers only represent the number of users we tested and only for the specific set of hardware that we used in our testing.</span></span> <span data-ttu-id="59703-107">En fonction de nos tests, nous recommandons ces limites pour les tailles maximales.</span><span class="sxs-lookup"><span data-stu-id="59703-107">Based on our testing, we recommend those limits for maximum sizes.</span></span> <span data-ttu-id="59703-108">Toutefois, vous contrôlez le nombre réel de participants autorisés dans les réunions au sein de votre organisation en configurant une ou plusieurs stratégies de conférence (que vous configurez à l’aide des applets de commande Windows PowerShell dans Lync Server Management Shell ou à l’aide de Lync Server Panneau de configuration).</span><span class="sxs-lookup"><span data-stu-id="59703-108">However, you control the actual number of participants allowed in meetings in your organization by configuring one or more conferencing policies (which you configure using Windows PowerShell cmdlets in the Lync Server Management Shell or using the Lync Server Control Panel).</span></span> <span data-ttu-id="59703-109">Le nombre que vous spécifiez dans une stratégie de conférence peut être n’importe quel nombre entier de 32 bits compris entre 1 et 4 294 967 295, mais la taille recommandée est comprise entre 2 et 250 participants (inclus). et la valeur par défaut est 250.</span><span class="sxs-lookup"><span data-stu-id="59703-109">The number that you specify in a conferencing policy can be any 32-bit whole number between 1 and 4,294,967,295, but the recommended size is between 2 and 250 participants, inclusive; and the default value is 250.</span></span>

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a><span data-ttu-id="59703-110">Q : Combien de réunions ou autres charges de travail puis-je avoir dans un pool dédié aux grandes réunions ?</span><span class="sxs-lookup"><span data-stu-id="59703-110">Q: How many meetings or other workloads can I have in a pool that is dedicated to large meetings?</span></span>

<span data-ttu-id="59703-p102">Pour garantir la meilleure expérience utilisateur dans les grandes réunions d’un maximum de 1 000 participants, nous vous conseillons d’héberger sur un pool dédié aux grandes réunions une seule grande réunion à la fois. Il est aussi préférable de ne pas autoriser l’exécution d’autres charges de travail sur ce pool pendant le déroulement d’une grande réunion.</span><span class="sxs-lookup"><span data-stu-id="59703-p102">To ensure the best user experience in large meetings of up to 1000 participants, we recommend hosting only a single large meeting at a time on a pool that is dedicated to large meetings. We also recommend not allowing any other workloads to run on that pool when the large meeting is in progress.</span></span>

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a><span data-ttu-id="59703-113">Q : Les organisateurs de grandes réunions doivent-ils être hébergés sur le pool dédié ?</span><span class="sxs-lookup"><span data-stu-id="59703-113">Q: Should the organizers of large meeting be homed on the dedicated pool?</span></span>

<span data-ttu-id="59703-p103">Non. Nous ne recommandons pas d’héberger sur le pool dédié des utilisateurs autres que le personnel dédié à la planification des grandes réunions. Cela permet d’éviter que les grandes réunions hébergées dans le pool ne soient affectées par le trafic d’autres communications en temps réel. Vous devez planifier les grandes réunions sur le pool dédié à l’aide d’un compte d’utilisateur appartenant à un membre du personnel chargé de la planification des grandes réunions. Vous devez ajouter le compte d’utilisateur de l’organisateur de la réunion (celui qui sollicite la grande réunion) en tant que présentateur de la grande réunion.</span><span class="sxs-lookup"><span data-stu-id="59703-p103">No. We recommend not homing any users other than the dedicated staff that manages scheduling of large meetings on the dedicated pool. This prevents other real-time communications traffic from causing problems with large meetings that are hosted in the pool. You should schedule large meetings on the dedicated pool using a user account of the large meeting scheduling staff. You should add the user account of the meeting organizer (the user who requests a large meeting) as a presenter for the large meeting.</span></span>

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a><span data-ttu-id="59703-119">Q : Quelles modalités multimédias puis-je utiliser dans une grande réunion ?</span><span class="sxs-lookup"><span data-stu-id="59703-119">Q: What media modalities can I use in a large meeting?</span></span>

<span data-ttu-id="59703-120">Les grandes réunions de plus de 1 000 utilisateurs peuvent inclure de l’audio, de la vidéo, un partage PowerPoint, des tableaux blancs et l’interrogation de présence.</span><span class="sxs-lookup"><span data-stu-id="59703-120">Large meetings with up to 1000 users can include audio, video, PowerPoint sharing, whiteboards, and presence polling.</span></span>

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a><span data-ttu-id="59703-121">Q : Puis-je utiliser la messagerie instantanée de groupe dans les grandes réunions ?</span><span class="sxs-lookup"><span data-stu-id="59703-121">Q: Can I use group instant messaging (IM) in large meetings?</span></span>

<span data-ttu-id="59703-122">Oui.</span><span class="sxs-lookup"><span data-stu-id="59703-122">Yes.</span></span> <span data-ttu-id="59703-123">Toutefois, un grand nombre de messages instantanés, en particulier quand ils sont envoyés par un grand nombre de participants à la réunion, peuvent affecter l’expérience utilisateur en raison des problèmes liés au défilement rapide du texte dans la fenêtre de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="59703-123">However, large numbers of instant messages, especially when sent by a large number of meeting participants, can affect the user experience due to problems with fast text scrolling in the IM window.</span></span> <span data-ttu-id="59703-124">La distribution d’un grand nombre de messages instantanés à un groupe de 1 000 utilisateurs peut également introduire des charges de serveur considérable, et ainsi nuire aux performances.</span><span class="sxs-lookup"><span data-stu-id="59703-124">Delivering a large amount of instant messages to up to 1000 users can also introduce significant server loads, which can affect performance.</span></span> <span data-ttu-id="59703-125">En règle générale, la messagerie instantanée est uniquement requise pour les\&questions et les réponses (Q As).</span><span class="sxs-lookup"><span data-stu-id="59703-125">Generally, IM is only required for questions and answers (Q\&As).</span></span>

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a><span data-ttu-id="59703-126">Q :Les utilisateurs peuvent-ils participer à de grandes réunions en composant le numéro à partir d’un téléphone ?</span><span class="sxs-lookup"><span data-stu-id="59703-126">Can users join large meetings by dialing in from a phone?</span></span>

<span data-ttu-id="59703-127">Oui.</span><span class="sxs-lookup"><span data-stu-id="59703-127">Yes.</span></span> <span data-ttu-id="59703-128">Si le pool Lync Server 2013 est correctement déployé et activé pour la Conférence rendez-vous, les utilisateurs pourront participer aux grandes réunions en appelant.</span><span class="sxs-lookup"><span data-stu-id="59703-128">If the Lync Server 2013 pool is properly deployed and enabled for dial-in conferencing, users will be able to join the large meetings by dialing in.</span></span> <span data-ttu-id="59703-129">Nos tests ont montré que jusqu’à 15 % de 1 000 participants peuvent participer à une grande réunion pendant 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="59703-129">Our testing has shown that up to 15% of the 1000 users can join the large meeting over a 10 minute period.</span></span>

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a><span data-ttu-id="59703-130">Q : Puis-je héberger des grandes réunions dans une topologie virtuelle ?</span><span class="sxs-lookup"><span data-stu-id="59703-130">Q: Can I host large meetings in a virtual topology?</span></span>

<span data-ttu-id="59703-131">Nous n’avons pas testé de grandes réunions dans une topologie virtuelle, nous ne sommes donc pas en mesure d’assurer un support en cas d’utilisation d’ordinateurs virtuels pour héberger un pool dédié aux grandes réunions.</span><span class="sxs-lookup"><span data-stu-id="59703-131">We have not tested large meetings in a virtual topology, so we do not support the use of virtual machines to host a dedicated pool for large meetings.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


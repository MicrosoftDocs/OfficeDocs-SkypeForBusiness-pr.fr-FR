---
title: 'Lync Server 2013 : FAQ sur la prise en charge des réunions de grande taille'
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
ms.openlocfilehash: 6f5a8d63fddf3b8633ebf31651d501458eaf4893
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a><span data-ttu-id="5c48c-102">FAQ sur la prise en charge des réunions de grande taille pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c48c-102">Large meeting support FAQ for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c48c-103">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="5c48c-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="5c48c-104">Les sections suivantes fournissent des réponses aux questions les plus fréquentes sur la création et l’exécution de réunions de grande envergure.</span><span class="sxs-lookup"><span data-stu-id="5c48c-104">The following sections provide answers to common questions for creating and running large meetings.</span></span>

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a><span data-ttu-id="5c48c-105">Q : combien d’utilisateurs peuvent participer à une réunion de grande envergure ?</span><span class="sxs-lookup"><span data-stu-id="5c48c-105">Q: How many users can participate in a large meeting?</span></span>

<span data-ttu-id="5c48c-106">Le modèle utilisateur de Lync Server spécifie des limites d’utilisateurs 250 dans un pool partagé ou 1000 utilisateurs dans un pool dédié à des réunions de grande taille, mais ces numéros représentent uniquement le nombre d’utilisateurs que nous avons testés et uniquement pour l’ensemble spécifique de matériel que nous avons utilisé dans le cadre de nos tests.</span><span class="sxs-lookup"><span data-stu-id="5c48c-106">The Lync Server user model specifies limits of 250 users in a shared pool or 1000 users in a pool dedicated to large meetings, but these numbers only represent the number of users we tested and only for the specific set of hardware that we used in our testing.</span></span> <span data-ttu-id="5c48c-107">D’après nos tests, nous vous conseillons de les limiter à des tailles maximales.</span><span class="sxs-lookup"><span data-stu-id="5c48c-107">Based on our testing, we recommend those limits for maximum sizes.</span></span> <span data-ttu-id="5c48c-108">Toutefois, vous contrôlez le nombre réel de participants autorisés à participer à des réunions au sein de votre organisation en configurant une ou plusieurs stratégies de conférence (que vous configurez à l’aide d’applets de commande Windows PowerShell dans Lync Server Management Shell ou à l’aide du serveur Lync. Panneau de configuration).</span><span class="sxs-lookup"><span data-stu-id="5c48c-108">However, you control the actual number of participants allowed in meetings in your organization by configuring one or more conferencing policies (which you configure using Windows PowerShell cmdlets in the Lync Server Management Shell or using the Lync Server Control Panel).</span></span> <span data-ttu-id="5c48c-109">Le numéro que vous spécifiez dans une stratégie de conférence peut être tout nombre entier de 32 bits compris entre 1 et 4 294 967 295, mais la taille recommandée est comprise entre 2 et 250 participants, y compris. et la valeur par défaut est 250.</span><span class="sxs-lookup"><span data-stu-id="5c48c-109">The number that you specify in a conferencing policy can be any 32-bit whole number between 1 and 4,294,967,295, but the recommended size is between 2 and 250 participants, inclusive; and the default value is 250.</span></span>

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a><span data-ttu-id="5c48c-110">Q : combien de réunions ou autres charges de travail puis-je avoir dans un pool dédié aux grandes réunions ?</span><span class="sxs-lookup"><span data-stu-id="5c48c-110">Q: How many meetings or other workloads can I have in a pool that is dedicated to large meetings?</span></span>

<span data-ttu-id="5c48c-111">Pour garantir 1000 une meilleure utilisation de l’utilisateur dans les réunions de grande taille, nous vous conseillons d’héberger uniquement une seule grande réunion à la fois sur un pool dédié aux réunions de grande envergure.</span><span class="sxs-lookup"><span data-stu-id="5c48c-111">To ensure the best user experience in large meetings of up to 1000 participants, we recommend hosting only a single large meeting at a time on a pool that is dedicated to large meetings.</span></span> <span data-ttu-id="5c48c-112">Nous vous recommandons également de ne pas autoriser l’exécution de toutes les autres charges de travail sur le pool lors de la grande réunion.</span><span class="sxs-lookup"><span data-stu-id="5c48c-112">We also recommend not allowing any other workloads to run on that pool when the large meeting is in progress.</span></span>

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a><span data-ttu-id="5c48c-113">Q : les organisateurs de grande réunion doivent-ils être hébergés sur le pool dédié ?</span><span class="sxs-lookup"><span data-stu-id="5c48c-113">Q: Should the organizers of large meeting be homed on the dedicated pool?</span></span>

<span data-ttu-id="5c48c-114">Non.</span><span class="sxs-lookup"><span data-stu-id="5c48c-114">No.</span></span> <span data-ttu-id="5c48c-115">Nous vous recommandons de ne pas organiser des utilisateurs autres que le personnel spécialisé qui gère la planification de réunions de grande envergure sur le pool dédié.</span><span class="sxs-lookup"><span data-stu-id="5c48c-115">We recommend not homing any users other than the dedicated staff that manages scheduling of large meetings on the dedicated pool.</span></span> <span data-ttu-id="5c48c-116">Cela empêche tout trafic de communication en temps réel de provoquer des problèmes liés aux réunions importantes qui sont hébergées dans le pool.</span><span class="sxs-lookup"><span data-stu-id="5c48c-116">This prevents other real-time communications traffic from causing problems with large meetings that are hosted in the pool.</span></span> <span data-ttu-id="5c48c-117">Il est recommandé de planifier des réunions de grande envergure sur le pool dédié en utilisant un compte d’utilisateur du personnel directeur de la réunion.</span><span class="sxs-lookup"><span data-stu-id="5c48c-117">You should schedule large meetings on the dedicated pool using a user account of the large meeting scheduling staff.</span></span> <span data-ttu-id="5c48c-118">Vous devez ajouter le compte d’utilisateur de l’organisateur de la réunion (l’utilisateur qui demande une importante réunion) en tant que présentateur de la grande réunion.</span><span class="sxs-lookup"><span data-stu-id="5c48c-118">You should add the user account of the meeting organizer (the user who requests a large meeting) as a presenter for the large meeting.</span></span>

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a><span data-ttu-id="5c48c-119">Q : Quelles sont les modalités de médias que j’utilise dans une grande réunion ?</span><span class="sxs-lookup"><span data-stu-id="5c48c-119">Q: What media modalities can I use in a large meeting?</span></span>

<span data-ttu-id="5c48c-120">Les réunions de grande envergure avec un maximum de 1000 peuvent inclure des éléments audio, vidéo, partage PowerPoint, tableaux blancs et interrogation de présence.</span><span class="sxs-lookup"><span data-stu-id="5c48c-120">Large meetings with up to 1000 users can include audio, video, PowerPoint sharing, whiteboards, and presence polling.</span></span>

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a><span data-ttu-id="5c48c-121">Q : est-il possible d’utiliser la messagerie instantanée de groupe dans de grandes réunions ?</span><span class="sxs-lookup"><span data-stu-id="5c48c-121">Q: Can I use group instant messaging (IM) in large meetings?</span></span>

<span data-ttu-id="5c48c-122">Oui.</span><span class="sxs-lookup"><span data-stu-id="5c48c-122">Yes.</span></span> <span data-ttu-id="5c48c-123">Toutefois, un grand nombre de messages instantanés, en particulier ceux envoyés par un grand nombre de participants à la réunion, peuvent influer sur l’interface utilisateur en raison de problèmes liés au défilement rapide du texte dans la fenêtre de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="5c48c-123">However, large numbers of instant messages, especially when sent by a large number of meeting participants, can affect the user experience due to problems with fast text scrolling in the IM window.</span></span> <span data-ttu-id="5c48c-124">La livraison d’un grand nombre de messages instantanés à un maximum de 1000 utilisateurs peut également provoquer de importants efforts de chargement du serveur, ce qui peut affecter les performances.</span><span class="sxs-lookup"><span data-stu-id="5c48c-124">Delivering a large amount of instant messages to up to 1000 users can also introduce significant server loads, which can affect performance.</span></span> <span data-ttu-id="5c48c-125">En règle générale, la messagerie instantanée est uniquement requise pour les\&questions et réponses (Q As).</span><span class="sxs-lookup"><span data-stu-id="5c48c-125">Generally, IM is only required for questions and answers (Q\&As).</span></span>

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a><span data-ttu-id="5c48c-126">Les utilisateurs peuvent-ils participer à des réunions importantes en se connectant depuis un téléphone ?</span><span class="sxs-lookup"><span data-stu-id="5c48c-126">Can users join large meetings by dialing in from a phone?</span></span>

<span data-ttu-id="5c48c-127">Oui.</span><span class="sxs-lookup"><span data-stu-id="5c48c-127">Yes.</span></span> <span data-ttu-id="5c48c-128">Si le pool Lync Server 2013 est correctement déployé et activé pour la Conférence rendez-vous, les utilisateurs peuvent rejoindre les réunions de grande taille en composant un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="5c48c-128">If the Lync Server 2013 pool is properly deployed and enabled for dial-in conferencing, users will be able to join the large meetings by dialing in.</span></span> <span data-ttu-id="5c48c-129">Nos tests ont démontré qu’un maximum de 15% des utilisateurs de 1000 peuvent rejoindre la réunion de grande taille sur une période de 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="5c48c-129">Our testing has shown that up to 15% of the 1000 users can join the large meeting over a 10 minute period.</span></span>

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a><span data-ttu-id="5c48c-130">Q : est-il possible d’héberger de grandes réunions dans une topologie virtuelle ?</span><span class="sxs-lookup"><span data-stu-id="5c48c-130">Q: Can I host large meetings in a virtual topology?</span></span>

<span data-ttu-id="5c48c-131">Comme nous n’avons pas testé de grande réunion dans une topologie virtuelle, nous ne prenons pas en charge l’utilisation d’ordinateurs virtuels pour l’hébergement d’une réserve dédiée pour les réunions de grande envergure.</span><span class="sxs-lookup"><span data-stu-id="5c48c-131">We have not tested large meetings in a virtual topology, so we do not support the use of virtual machines to host a dedicated pool for large meetings.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


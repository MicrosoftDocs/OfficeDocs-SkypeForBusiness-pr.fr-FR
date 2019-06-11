---
title: 'Lync Server 2013: vue d’ensemble du parc d’appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2d6f6b8f0f6a91e75071c7d103cf4bff3b4be1f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a><span data-ttu-id="63c27-102">Présentation du parc d’appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63c27-102">Overview of Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63c27-103">_**Dernière modification de la rubrique:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="63c27-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="63c27-104">L’application de parc d’appels de Lync Server 2013 permet aux utilisateurs voix entreprise de procéder de l’une des façons suivantes:</span><span class="sxs-lookup"><span data-stu-id="63c27-104">The Lync Server 2013 Call Park application lets Enterprise Voice users do any of the following:</span></span>

  - <span data-ttu-id="63c27-105">mettre un appel en attente, puis récupérer l’appel depuis le même téléphone ou un autre téléphone ;</span><span class="sxs-lookup"><span data-stu-id="63c27-105">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>

  - <span data-ttu-id="63c27-106">mettre un appel en attente pour le transférer vers un service ou une zone générale (par exemple, vers un service commercial ou un entrepôt où il y a un téléphone de partie commune) ;</span><span class="sxs-lookup"><span data-stu-id="63c27-106">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>

  - <span data-ttu-id="63c27-107">mettre un appel en attente et garder le téléphone d’origine libre pour répondre aux autres appels.</span><span class="sxs-lookup"><span data-stu-id="63c27-107">Put a call on hold and keep the original answering phone free for other calls.</span></span>

<span data-ttu-id="63c27-108">Lorsqu’un utilisateur travaille sur un appel, Lync Server transfère l’appel vers un numéro temporaire, appelé *orbite*, où l’appel est maintenu jusqu’à ce qu’il soit récupéré ou qu’il arrive à expiration. Lync Server envoie l’orbite à l’utilisateur qui a parqué l’appel.</span><span class="sxs-lookup"><span data-stu-id="63c27-108">When a user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until it is retrieved or it times out. Lync Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="63c27-109">Pour récupérer l’appel parqué, l’utilisateur peut composer le numéro de l’orbite ou cliquer sur le lien ou le bouton d’orbite dans la fenêtre de conversation.</span><span class="sxs-lookup"><span data-stu-id="63c27-109">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span>

<span data-ttu-id="63c27-p102">L’utilisateur qui a parqué un appel peut avertir quelqu’un pour récupérer l’appel en ayant recours à un mécanisme externe, tel qu’un système de messagerie instantanée ou de radiomessagerie, pour communiquer le numéro d’orbite à quelqu’un d’autre. L’utilisateur qui a parqué l’appel peut laisser la fenêtre de conversation ouverte pour recevoir une notification quand l’appel est récupéré.</span><span class="sxs-lookup"><span data-stu-id="63c27-p102">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else. The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>

<span data-ttu-id="63c27-112">Étant donné que les plages d’orbites sont globalement uniques, il est possible de récupérer les appels à partir d’un site ou d’un téléphone PBX du serveur Lync si le routage est configuré de manière appropriée.</span><span class="sxs-lookup"><span data-stu-id="63c27-112">Because orbit ranges are globally unique, it is possible to retrieve calls from any Lync Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="63c27-113">Si personne ne récupère l’appel dans un délai configurable, la personne qui l’a parqué est rappelée.</span><span class="sxs-lookup"><span data-stu-id="63c27-113">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="63c27-114">Si cette personne ne répond pas au rappel, l’appel est transféré vers une destination de remplacement, telle qu’un opérateur, si la configuration est définie de la sorte.</span><span class="sxs-lookup"><span data-stu-id="63c27-114">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="63c27-115">Vous pouvez configurer le nombre de sonneries de rappel avant le transfert, de une à dix.</span><span class="sxs-lookup"><span data-stu-id="63c27-115">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="63c27-116">Si personne ne répond à un appel transféré, l’appel est déconnecté.</span><span class="sxs-lookup"><span data-stu-id="63c27-116">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="63c27-117">L’orbite est libérée lorsque l’appel est récupéré ou déconnecté.</span><span class="sxs-lookup"><span data-stu-id="63c27-117">The orbit is freed when the call is retrieved or disconnected.</span></span>

<span data-ttu-id="63c27-118">Quand vous déployez le parcage d’appel, vous devez réserver des plages de numéros d’extension pour le parcage des appels.</span><span class="sxs-lookup"><span data-stu-id="63c27-118">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="63c27-119">Il doit s’agir d’extensions virtuelles, c’est-à-dire d’extensions auxquelles aucun utilisateur ou téléphone n’est attribué.</span><span class="sxs-lookup"><span data-stu-id="63c27-119">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="63c27-120">Vous configurez ensuite la table d’orbites de parcage d’appel avec les plages de numéros d’extension, puis spécifiez quel service d’application héberge l’application de parcage d’appel qui gère chaque plage.</span><span class="sxs-lookup"><span data-stu-id="63c27-120">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="63c27-121">Chaque pool frontal possède une table de parc d’appels sur le serveur principal correspondant qui est utilisé pour gérer les appels qui sont emparking sur le pool.</span><span class="sxs-lookup"><span data-stu-id="63c27-121">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="63c27-122">La liste des plages d’orbites qui est stockée dans le magasin central de gestion est utilisée pour diriger les orbites vers le pool de destination.</span><span class="sxs-lookup"><span data-stu-id="63c27-122">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="63c27-123">Chaque pool de serveurs Lync dans lequel l’application de parc d’appels est déployée et configurée peut avoir une ou plusieurs plages d’orbite.</span><span class="sxs-lookup"><span data-stu-id="63c27-123">Each Lync Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="63c27-124">Les plages orbites doivent être globalement uniques dans le déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="63c27-124">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<span data-ttu-id="63c27-p105">Vous configurez également d’autres paramètres de parcage d’appel, tels que l’endroit où sont redirigés les appels s’ils arrivent à expiration et si la personne en ligne entend de la musique lorsque son appel est parqué. Vous pouvez aussi spécifier le fichier de musique à lire lorsque l’appel est en attente.</span><span class="sxs-lookup"><span data-stu-id="63c27-p105">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked. You can also specify the music file to play while the call is on hold.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="63c27-127">Les fichiers de conservation de musique personnalisés pour le parc d’appels ne sont pas sauvegardés dans le cadre du processus de reprise après sinistre de Lync Server 2013 et seront perdus si les fichiers téléchargés sur le pool sont endommagés, endommagés ou supprimés.</span><span class="sxs-lookup"><span data-stu-id="63c27-127">Customized music-on-hold files for Call Park are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="63c27-128">Veillez à toujours conserver une copie de sauvegarde distincte des fichiers de mise en attente musicale personnalisés que vous avez téléchargés pour le parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="63c27-128">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="63c27-129">The Call Park application is a component of Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="63c27-129">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="63c27-130">Lorsque vous déployez Enterprise Voice, l’application de parc d’appels est installée et activée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="63c27-130">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="63c27-131">Pour que vous puissiez utiliser le parc d’appels, vous devez toutefois le configurer et l’activer pour les utilisateurs via la stratégie vocale.</span><span class="sxs-lookup"><span data-stu-id="63c27-131">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013 : vue d’ensemble du parcage d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22811a0c55f0e0c7a7bfb7f3aeeb3ab5fcbc2653
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530671"
---
# <a name="overview-of-call-park-in-lync-server-2013"></a><span data-ttu-id="564ae-102">Vue d’ensemble du parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="564ae-102">Overview of Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="564ae-103">_**Dernière modification de la rubrique :** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="564ae-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="564ae-104">L’application de parcage d’appel Lync Server 2013 permet aux utilisateurs de voix entreprise d’effectuer l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="564ae-104">The Lync Server 2013 Call Park application lets Enterprise Voice users do any of the following:</span></span>

  - <span data-ttu-id="564ae-105">Mettre un appel en attente, puis récupérer l’appel depuis le même téléphone ou un autre téléphone.</span><span class="sxs-lookup"><span data-stu-id="564ae-105">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>

  - <span data-ttu-id="564ae-106">Mettre un appel en attente pour le transférer vers un service ou une zone générale (par exemple, vers un service commercial ou un entrepôt où il y a un téléphone de partie commune).</span><span class="sxs-lookup"><span data-stu-id="564ae-106">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>

  - <span data-ttu-id="564ae-107">Mettre un appel en attente et conserver le téléphone d’origine gratuitement pour les autres appels.</span><span class="sxs-lookup"><span data-stu-id="564ae-107">Put a call on hold and keep the original answering phone free for other calls.</span></span>

<span data-ttu-id="564ae-108">Lorsqu’un utilisateur héberge un appel, Lync Server transfère l’appel vers un numéro temporaire, appelé *orbite*, où l’appel est conservé jusqu’à ce qu’il soit récupéré ou qu’il arrive à expiration. Lync Server envoie l’orbite à l’utilisateur qui a parqué l’appel.</span><span class="sxs-lookup"><span data-stu-id="564ae-108">When a user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until it is retrieved or it times out. Lync Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="564ae-109">Pour récupérer l’appel parqué, l’utilisateur peut composer le numéro d’orbite ou cliquer sur le lien ou le bouton d’orbite dans la fenêtre de conversation.</span><span class="sxs-lookup"><span data-stu-id="564ae-109">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span>

<span data-ttu-id="564ae-110">L’utilisateur qui a parqué un appel peut informer quelqu’un pour qu’il récupère l’appel à l’aide d’un mécanisme externe, tel que la messagerie instantanée ou un système de radiomessagerie, pour communiquer le numéro d’orbite à une autre personne.</span><span class="sxs-lookup"><span data-stu-id="564ae-110">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else.</span></span> <span data-ttu-id="564ae-111">L’utilisateur qui a parqué l’appel peut laisser la fenêtre de conversation ouverte pour recevoir une notification lorsque l’appel est récupéré.</span><span class="sxs-lookup"><span data-stu-id="564ae-111">The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>

<span data-ttu-id="564ae-112">Étant donné que les plages d’orbites sont globalement uniques, il est possible de récupérer des appels à partir de n’importe quel site ou téléphone PBX de Lync Server si le routage est correctement configuré.</span><span class="sxs-lookup"><span data-stu-id="564ae-112">Because orbit ranges are globally unique, it is possible to retrieve calls from any Lync Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="564ae-113">Si personne ne récupère l’appel dans un intervalle de temps configurable, l’appel sonne à la personne qui l’a parqué.</span><span class="sxs-lookup"><span data-stu-id="564ae-113">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="564ae-114">Si cette personne ne répond pas au rappel, l’appel est transféré vers une destination de secours, telle qu’un opérateur, si elle est configurée.</span><span class="sxs-lookup"><span data-stu-id="564ae-114">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="564ae-115">Vous pouvez configurer le nombre de sonneries de l’appel avant de le transférer d’une à dix fois.</span><span class="sxs-lookup"><span data-stu-id="564ae-115">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="564ae-116">Si personne ne répond à un appel transféré, l’appel est déconnecté.</span><span class="sxs-lookup"><span data-stu-id="564ae-116">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="564ae-117">L’orbite est libérée lors de l’extraction ou de la déconnexion de l’appel.</span><span class="sxs-lookup"><span data-stu-id="564ae-117">The orbit is freed when the call is retrieved or disconnected.</span></span>

<span data-ttu-id="564ae-118">Lorsque vous déployez le parcage d’appel, vous devez réserver des plages de numéros de poste pour les appels de parking.</span><span class="sxs-lookup"><span data-stu-id="564ae-118">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="564ae-119">Ces extensions doivent être des extensions virtuelles : les extensions auxquelles aucun utilisateur ou téléphone n’est affecté.</span><span class="sxs-lookup"><span data-stu-id="564ae-119">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="564ae-120">Vous configurez ensuite la table d’orbites de parcage d’appel avec les plages de numéros d’extension et spécifiez quel service d’application héberge l’application de parcage d’appel qui gère chaque plage.</span><span class="sxs-lookup"><span data-stu-id="564ae-120">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="564ae-121">Chaque pool frontal a une table de parcage d’appel sur le serveur principal correspondant qui est utilisé pour gérer les appels parqués sur le pool.</span><span class="sxs-lookup"><span data-stu-id="564ae-121">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="564ae-122">La liste des plages d’orbites est stockée dans le magasin central de gestion et est utilisée pour acheminer les orbites vers le pool de destination.</span><span class="sxs-lookup"><span data-stu-id="564ae-122">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="564ae-123">Chaque pool Lync Server où l’application de parcage d’appel est déployée et configurée peut avoir une ou plusieurs plages d’orbites.</span><span class="sxs-lookup"><span data-stu-id="564ae-123">Each Lync Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="564ae-124">Les plages d’orbites doivent être uniques au niveau global dans le déploiement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="564ae-124">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<span data-ttu-id="564ae-125">Vous configurez également d’autres paramètres de parcage d’appel, tels que l’endroit où les appels sont redirigés s’ils expirent et si la personne sur le téléphone entend la musique quand elle est parqué.</span><span class="sxs-lookup"><span data-stu-id="564ae-125">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked.</span></span> <span data-ttu-id="564ae-126">Vous pouvez également spécifier le fichier audio à lire pendant l’attente de l’appel.</span><span class="sxs-lookup"><span data-stu-id="564ae-126">You can also specify the music file to play while the call is on hold.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="564ae-127">Les fichiers de mise en attente musicale personnalisés pour le parcage d’appel ne sont pas sauvegardés dans le cadre du processus de récupération d’urgence Lync Server 2013 et seront perdus si les fichiers chargés dans le pool sont endommagés, endommagés ou effacés.</span><span class="sxs-lookup"><span data-stu-id="564ae-127">Customized music-on-hold files for Call Park are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="564ae-128">Conservez toujours une copie de sauvegarde distincte des fichiers de conservation musicaux personnalisés que vous avez téléchargés pour le parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="564ae-128">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="564ae-129">L’application de parcage d’appel est un composant de voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="564ae-129">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="564ae-130">Lorsque vous déployez voix entreprise, l’application de parcage d’appel est installée et activée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="564ae-130">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="564ae-131">Avant de pouvoir utiliser le parcage d’appel, l’administrateur de voix entreprise doit toutefois le configurer et l’activer pour les utilisateurs par le biais de la stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="564ae-131">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


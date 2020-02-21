---
title: 'Lync Server 2013 : planifier l’apparence des lignes partagées'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef6bb768ca892aa684613d1261d88266237ab111
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="32cc2-102">Planifier l’apparence des lignes partagées dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32cc2-102">Plan for Shared Line Appearance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32cc2-103">_**Dernière modification de la rubrique :** 2016-03-21_</span><span class="sxs-lookup"><span data-stu-id="32cc2-103">_**Topic Last Modified:** 2016-03-21_</span></span>

<span data-ttu-id="32cc2-104">Consultez cette rubrique pour découvrir comment planifier l’apparence de ligne partagée (SLA) dans Lync Server 2013, mise à jour cumulative avril 2016.</span><span class="sxs-lookup"><span data-stu-id="32cc2-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="32cc2-105">Shared Line Appearance est une fonctionnalité de Lync Server 2013, cumulative update avril 2016 pour le traitement de plusieurs appels sur un numéro spécifique appelé « numéro partagé ».</span><span class="sxs-lookup"><span data-stu-id="32cc2-105">Shared Line Appearance is a feature in Lync Server 2013, Cumulative Update April 2016 for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="32cc2-106">Le contrat SLA peut configurer un utilisateur Lync voix entreprise compatible avec plusieurs lignes pour répondre à plusieurs appels.</span><span class="sxs-lookup"><span data-stu-id="32cc2-106">SLA can configure any enterprise voice enabled Lync user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="32cc2-107">Les appels ne sont pas réellement reçus sur le numéro partagé, mais ils sont transférés aux utilisateurs qui agissent en tant que délégués pour le numéro partagé.</span><span class="sxs-lookup"><span data-stu-id="32cc2-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="32cc2-108">Tous les délégués peuvent sélectionner l’appel pendant que le reste des délégués obtient une notification sur leur téléphone indiquant qui a pris l’appel et quelle ligne a été utilisée comme résultat.</span><span class="sxs-lookup"><span data-stu-id="32cc2-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="32cc2-109">Le nombre de lignes et les délégués peuvent être configurés pour un numéro partagé dans le contrat SLA.</span><span class="sxs-lookup"><span data-stu-id="32cc2-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="32cc2-110">De plus, les options avancées, telles que BusyOption (ce qui se passe dans une situation où toutes les lignes sont occupées) et MissedCallOption (le cas dans lequel aucun des délégués ne récupère un appel), peuvent également être configurées pour un numéro partagé.</span><span class="sxs-lookup"><span data-stu-id="32cc2-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>

<span data-ttu-id="32cc2-111">Le contrat SLA est pris en charge uniquement sur les appareils téléphoniques suivants (il n’est pas pris en charge pour les clients Lync sur des ordinateurs, des téléphones mobiles ou d’autres appareils) :</span><span class="sxs-lookup"><span data-stu-id="32cc2-111">SLA is supported only on the following phone devices (it is not supported for Lync clients on computers, mobile phones, or other devices):</span></span>

  - <span data-ttu-id="32cc2-112">Polycom VVX300 avec mise à jour du microprogramme 5.4.1</span><span class="sxs-lookup"><span data-stu-id="32cc2-112">Polycom VVX300 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="32cc2-113">Polycom VVX400 avec mise à jour du microprogramme 5.4.1</span><span class="sxs-lookup"><span data-stu-id="32cc2-113">Polycom VVX400 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="32cc2-114">Polycom VVX500 avec mise à jour du microprogramme 5.4.1</span><span class="sxs-lookup"><span data-stu-id="32cc2-114">Polycom VVX500 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="32cc2-115">Polycom VVX600 avec mise à jour du microprogramme 5.4.1</span><span class="sxs-lookup"><span data-stu-id="32cc2-115">Polycom VVX600 with firmware update 5.4.1</span></span>

<span data-ttu-id="32cc2-116">Le contrat SLA est une nouvelle fonctionnalité de Lync Server 2013, mise à jour cumulative avril 2016.</span><span class="sxs-lookup"><span data-stu-id="32cc2-116">SLA is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="32cc2-117">Pour plus d’informations sur le déploiement du contrat SLA, voir [Deploy Shared Line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="32cc2-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span></span>

<div>

## <a name="feature-list"></a><span data-ttu-id="32cc2-118">Liste des fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="32cc2-118">Feature List</span></span>

<span data-ttu-id="32cc2-119">La configuration d’un groupe de SLA permet d’activer les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="32cc2-119">Setting up an SLA group enables the following:</span></span>

  - <span data-ttu-id="32cc2-120">Tous les délégués du groupe peuvent répondre à des appels entrants vers le même numéro partagé.</span><span class="sxs-lookup"><span data-stu-id="32cc2-120">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="32cc2-121">Les appels peuvent être basés sur PSTN ou sur SIP.</span><span class="sxs-lookup"><span data-stu-id="32cc2-121">The calls can be PSTN-based or SIP-based.</span></span>

  - <span data-ttu-id="32cc2-122">Les délégués peuvent suspendre et reprendre des appels.</span><span class="sxs-lookup"><span data-stu-id="32cc2-122">Delegates can hold and pick up calls.</span></span>

  - <span data-ttu-id="32cc2-123">Les délégués peuvent transférer des appels vers un numéro en dehors du groupe SLA.</span><span class="sxs-lookup"><span data-stu-id="32cc2-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>

  - <span data-ttu-id="32cc2-124">Les délégués peuvent voir le nombre d’appels actuellement sur le numéro partagé et afficher l’état de chacun de ces appels.</span><span class="sxs-lookup"><span data-stu-id="32cc2-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>

  - <span data-ttu-id="32cc2-125">Vous pouvez configurer un nombre maximal d’appels simultanés pour le numéro partagé.</span><span class="sxs-lookup"><span data-stu-id="32cc2-125">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="32cc2-126">Vous pouvez également définir la façon dont vous souhaitez que les appels supplémentaires soient gérés une fois ce maximum atteint.</span><span class="sxs-lookup"><span data-stu-id="32cc2-126">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="32cc2-127">Les appels excédentaires peuvent être rejetés avec un signal occupé, transférés vers un autre numéro ou transférés vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="32cc2-127">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>

  - <span data-ttu-id="32cc2-128">Vous pouvez configurer le mode de traitement des appels manqués (appels non récupérés après un certain temps).</span><span class="sxs-lookup"><span data-stu-id="32cc2-128">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="32cc2-129">Si vous activez la messagerie vocale pour l’identité du groupe, les appels manqués sont automatiquement dirigés vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="32cc2-129">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="32cc2-130">Si la messagerie vocale n’est pas activée pour l’identité du groupe (numéro partagé), vous pouvez choisir de refuser les appels manqués à l’aide d’un signal d’occupation, de le transférer à un autre numéro ou de le déconnecter.</span><span class="sxs-lookup"><span data-stu-id="32cc2-130">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013 : attribution de stratégies de présence par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ec15b826614afcca970989b6436d3ad94d7941f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="c0948-102">Attribution de stratégies de présence par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0948-102">Assigning per-user presence policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0948-103">_**Dernière modification de la rubrique :** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="c0948-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="c0948-104">Une politique de présence est un ensemble de limites et de restrictions qui influent sur la présence.</span><span class="sxs-lookup"><span data-stu-id="c0948-104">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="c0948-105">Le tableau suivant décrit les paramètres de stratégie de présence disponibles dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c0948-105">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="c0948-106">Paramètres de la stratégie de présence</span><span class="sxs-lookup"><span data-stu-id="c0948-106">Presence Policy Settings</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0948-107">Nom XML</span><span class="sxs-lookup"><span data-stu-id="c0948-107">XML name</span></span></th>
<th><span data-ttu-id="c0948-108">Nom d’affichage</span><span class="sxs-lookup"><span data-stu-id="c0948-108">Display name</span></span></th>
<th><span data-ttu-id="c0948-109">Description</span><span class="sxs-lookup"><span data-stu-id="c0948-109">Description</span></span></th>
<th><span data-ttu-id="c0948-110">Type</span><span class="sxs-lookup"><span data-stu-id="c0948-110">Type</span></span></th>
<th><span data-ttu-id="c0948-111">Valeur</span><span class="sxs-lookup"><span data-stu-id="c0948-111">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0948-112">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="c0948-112">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="c0948-113">Nombre maximal d’abonnements aux catégories d’abonnés</span><span class="sxs-lookup"><span data-stu-id="c0948-113">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="c0948-114">Limite le nombre d’abonnements à des catégories d’abonnés.</span><span class="sxs-lookup"><span data-stu-id="c0948-114">Limits the number of subscriber category subscriptions.</span></span> <span data-ttu-id="c0948-115">Par exemple, lorsque Communicator s’abonne à la présence d’un utilisateur, il obtient un abonnement de catégorie pour chaque carte de visite, données de calendrier, notes, services et catégories d’États.</span><span class="sxs-lookup"><span data-stu-id="c0948-115">For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="c0948-116">La valeur 0 indique que l’utilisateur ou le contact ne peut pas s’abonner à d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c0948-116">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c0948-117">Ce paramètre peut avoir une incidence considérable sur les performances s’il est défini sur un numéro élevé et l’utilisateur moyen a un grand nombre d’utilisateurs s’abonnant à sa présence.</span><span class="sxs-lookup"><span data-stu-id="c0948-117">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="c0948-118">Entier</span><span class="sxs-lookup"><span data-stu-id="c0948-118">Integer</span></span></p></td>
<td><p><span data-ttu-id="c0948-119">0-3000</span><span class="sxs-lookup"><span data-stu-id="c0948-119">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0948-120">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="c0948-120">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="c0948-121">Nombre maximal d’alertes d’abonnement de présence en file d’attente</span><span class="sxs-lookup"><span data-stu-id="c0948-121">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="c0948-122">Limite le nombre d’entrées dans la table abonnés invites.</span><span class="sxs-lookup"><span data-stu-id="c0948-122">Limits the number of entries in the prompted subscribers table.</span></span> <span data-ttu-id="c0948-123">Ce paramètre détermine le nombre maximal d’invites qui peuvent être mis en file d’attente pour un utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="c0948-123">This setting determines the maximum number of prompts that can be queued for a given user.</span></span> <span data-ttu-id="c0948-124">Par exemple, lorsque l’utilisateur A s’abonner à la présence de l’utilisateur B, il reçoit une invite indiquant que l’utilisateur A est désormais abonné à l’utilisateur B et une invite d’accusé de réception est créée dans la table des abonnés invités de l’utilisateur B.</span><span class="sxs-lookup"><span data-stu-id="c0948-124">For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table.</span></span> <span data-ttu-id="c0948-125">Après que l’utilisateur a accepté, ou accuse de réception, l’abonnement, l’invite d’accusé de réception est supprimée de la table des abonnés invites de l’utilisateur B.</span><span class="sxs-lookup"><span data-stu-id="c0948-125">After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="c0948-126">La valeur 0 indique que l’utilisateur n’est pas invité à s’abonner à sa présence.</span><span class="sxs-lookup"><span data-stu-id="c0948-126">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="c0948-127">Entier ou jeton</span><span class="sxs-lookup"><span data-stu-id="c0948-127">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="c0948-128">0-500</span><span class="sxs-lookup"><span data-stu-id="c0948-128">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c0948-129">Par défaut, la stratégie et le **service** **par défaut** : stratégies de présence moyenne sont installés lors du déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c0948-129">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="c0948-130">Le tableau suivant décrit les paramètres spécifiques des deux stratégies de présence.</span><span class="sxs-lookup"><span data-stu-id="c0948-130">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="c0948-131">Politiques de présence</span><span class="sxs-lookup"><span data-stu-id="c0948-131">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0948-132">Nom de la stratégie</span><span class="sxs-lookup"><span data-stu-id="c0948-132">Policy name</span></span></th>
<th><span data-ttu-id="c0948-133">Description</span><span class="sxs-lookup"><span data-stu-id="c0948-133">Description</span></span></th>
<th><span data-ttu-id="c0948-134">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="c0948-134">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="c0948-135">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="c0948-135">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0948-136">Stratégie par défaut</span><span class="sxs-lookup"><span data-stu-id="c0948-136">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="c0948-137">Politique pour les utilisateurs typiques.</span><span class="sxs-lookup"><span data-stu-id="c0948-137">Policy for typical users.</span></span> <span data-ttu-id="c0948-138">Il s’agit de la stratégie de présence par défaut.</span><span class="sxs-lookup"><span data-stu-id="c0948-138">This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="c0948-139">1000</span><span class="sxs-lookup"><span data-stu-id="c0948-139">1000</span></span></p></td>
<td><p><span data-ttu-id="c0948-140">200</span><span class="sxs-lookup"><span data-stu-id="c0948-140">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0948-141">Service : moyen</span><span class="sxs-lookup"><span data-stu-id="c0948-141">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="c0948-142">Stratégie pour les applications qui requièrent davantage d’utilisateurs pour s’abonner à la présence de l’objet.</span><span class="sxs-lookup"><span data-stu-id="c0948-142">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="c0948-143">1000</span><span class="sxs-lookup"><span data-stu-id="c0948-143">1000</span></span></p></td>
<td><p><span data-ttu-id="c0948-144">0,4</span><span class="sxs-lookup"><span data-stu-id="c0948-144">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


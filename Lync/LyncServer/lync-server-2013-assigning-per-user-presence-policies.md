---
title: 'Lync Server 2013 : attribution de stratégies de présence par utilisateur'
description: 'Lync Server 2013 : affectation de stratégies de présence par utilisateur.'
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
ms.openlocfilehash: 5c3d4b4bda0c4bb85065d546fdbb4b2578db0e3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563370"
---
# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="69248-103">Affectation de stratégies de présence par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69248-103">Assigning per-user presence policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69248-104">_**Dernière modification de la rubrique :** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="69248-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="69248-105">Une stratégie de présence est un ensemble de limites et de restrictions qui affectent la présence.</span><span class="sxs-lookup"><span data-stu-id="69248-105">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="69248-106">Le tableau suivant décrit les paramètres de stratégie de présence disponibles dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="69248-106">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="69248-107">Paramètres de stratégie de présence</span><span class="sxs-lookup"><span data-stu-id="69248-107">Presence Policy Settings</span></span>

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
<th><span data-ttu-id="69248-108">Nom XML</span><span class="sxs-lookup"><span data-stu-id="69248-108">XML name</span></span></th>
<th><span data-ttu-id="69248-109">Nom d'affichage</span><span class="sxs-lookup"><span data-stu-id="69248-109">Display name</span></span></th>
<th><span data-ttu-id="69248-110">Description</span><span class="sxs-lookup"><span data-stu-id="69248-110">Description</span></span></th>
<th><span data-ttu-id="69248-111">Type</span><span class="sxs-lookup"><span data-stu-id="69248-111">Type</span></span></th>
<th><span data-ttu-id="69248-112">Valeur</span><span class="sxs-lookup"><span data-stu-id="69248-112">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69248-113">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="69248-113">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="69248-114">Nombre maximum d’abonnements aux catégories d’abonnés</span><span class="sxs-lookup"><span data-stu-id="69248-114">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="69248-p102">Limite le nombre d’abonnements aux catégories d’abonnés Par exemple, lorsque Communicator s’abonne à la présence d’un utilisateur, il obtient un abonnement aux catégories pour chaque carte de visite, données de calendrier, notes, services et catégories d’état.</span><span class="sxs-lookup"><span data-stu-id="69248-p102">Limits the number of subscriber category subscriptions. For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="69248-117">Un paramètre de 0 signifie que l’objet contact ou utilisateur ne peut pas être souscrit par d’autres.</span><span class="sxs-lookup"><span data-stu-id="69248-117">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="69248-118">Ce paramètre peut avoir un impact significatif sur les performances s’il est défini sur une valeur élevée, et l’utilisateur moyen a un grand nombre d’utilisateurs qui s’abonnent à sa présence.</span><span class="sxs-lookup"><span data-stu-id="69248-118">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="69248-119">Entier</span><span class="sxs-lookup"><span data-stu-id="69248-119">Integer</span></span></p></td>
<td><p><span data-ttu-id="69248-120">0-3000</span><span class="sxs-lookup"><span data-stu-id="69248-120">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69248-121">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="69248-121">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="69248-122">Nombre maximal d’alertes d’abonnement de présence mises en file d’attente</span><span class="sxs-lookup"><span data-stu-id="69248-122">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="69248-p103">Limite le nombre d’entrées dans la table des abonnés alertés. Ce paramètre détermine le nombre maximum d’alertes pouvant être mises en file d’attente pour un utilisateur donné. Par exemple, lorsque l’utilisateur A s’abonne à la présence de l’utilisateur B, ce dernier reçoit une alerte l’informant que l’utilisateur A est abonné à l’utilisateur B, et un accusé de réception est créé dans la table des abonnés alertés de l’utilisateur B. Lorsque l’utilisateur B accepte ou accuse réception de l’abonnement, l’alerte d’accusé de réception est supprimée de la table des abonnées alertés de l’utilisateur B.</span><span class="sxs-lookup"><span data-stu-id="69248-p103">Limits the number of entries in the prompted subscribers table. This setting determines the maximum number of prompts that can be queued for a given user. For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table. After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="69248-127">Un paramètre de 0 signifie que l’utilisateur n’est pas alerté lorsque quelqu’un s’abonne à sa présence.</span><span class="sxs-lookup"><span data-stu-id="69248-127">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="69248-128">Entier ou jeton</span><span class="sxs-lookup"><span data-stu-id="69248-128">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="69248-129">0-500</span><span class="sxs-lookup"><span data-stu-id="69248-129">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="69248-130">Par défaut, la stratégie et le **service** **par défaut** : les stratégies de présence moyennes sont installées lorsque vous déployez Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69248-130">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="69248-131">Le tableau suivant décrit les paramètres spécifiques des deux stratégies de présence.</span><span class="sxs-lookup"><span data-stu-id="69248-131">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="69248-132">Stratégies de présence</span><span class="sxs-lookup"><span data-stu-id="69248-132">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69248-133">Nom de la stratégie</span><span class="sxs-lookup"><span data-stu-id="69248-133">Policy name</span></span></th>
<th><span data-ttu-id="69248-134">Description</span><span class="sxs-lookup"><span data-stu-id="69248-134">Description</span></span></th>
<th><span data-ttu-id="69248-135">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="69248-135">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="69248-136">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="69248-136">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69248-137">Stratégie par défaut</span><span class="sxs-lookup"><span data-stu-id="69248-137">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="69248-p105">Stratégies pour les utilisateurs types. Il s’agit de la stratégie de présence par défaut.</span><span class="sxs-lookup"><span data-stu-id="69248-p105">Policy for typical users. This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="69248-140">1000</span><span class="sxs-lookup"><span data-stu-id="69248-140">1000</span></span></p></td>
<td><p><span data-ttu-id="69248-141">200</span><span class="sxs-lookup"><span data-stu-id="69248-141">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69248-142">Service : moyen</span><span class="sxs-lookup"><span data-stu-id="69248-142">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="69248-143">Stratégie pour les applications qui ont besoin que plusieurs utilisateurs s’abonnent à la présence de l’objet.</span><span class="sxs-lookup"><span data-stu-id="69248-143">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="69248-144">1000</span><span class="sxs-lookup"><span data-stu-id="69248-144">1000</span></span></p></td>
<td><p><span data-ttu-id="69248-145">0</span><span class="sxs-lookup"><span data-stu-id="69248-145">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


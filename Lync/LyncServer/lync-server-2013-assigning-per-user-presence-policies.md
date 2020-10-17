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
ms.openlocfilehash: 7c4f561189b72cf19fad28879711e3a1da0da8fb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527121"
---
# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="39f47-102">Affectation de stratégies de présence par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39f47-102">Assigning per-user presence policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39f47-103">_**Dernière modification de la rubrique :** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="39f47-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="39f47-104">Une stratégie de présence est un ensemble de limites et de restrictions qui affectent la présence.</span><span class="sxs-lookup"><span data-stu-id="39f47-104">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="39f47-105">Le tableau suivant décrit les paramètres de stratégie de présence disponibles dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39f47-105">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="39f47-106">Paramètres de stratégie de présence</span><span class="sxs-lookup"><span data-stu-id="39f47-106">Presence Policy Settings</span></span>

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
<th><span data-ttu-id="39f47-107">Nom XML</span><span class="sxs-lookup"><span data-stu-id="39f47-107">XML name</span></span></th>
<th><span data-ttu-id="39f47-108">Nom d'affichage</span><span class="sxs-lookup"><span data-stu-id="39f47-108">Display name</span></span></th>
<th><span data-ttu-id="39f47-109">Description</span><span class="sxs-lookup"><span data-stu-id="39f47-109">Description</span></span></th>
<th><span data-ttu-id="39f47-110">Type</span><span class="sxs-lookup"><span data-stu-id="39f47-110">Type</span></span></th>
<th><span data-ttu-id="39f47-111">Valeur</span><span class="sxs-lookup"><span data-stu-id="39f47-111">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39f47-112">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="39f47-112">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="39f47-113">Nombre maximum d’abonnements aux catégories d’abonnés</span><span class="sxs-lookup"><span data-stu-id="39f47-113">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="39f47-p102">Limite le nombre d’abonnements aux catégories d’abonnés Par exemple, lorsque Communicator s’abonne à la présence d’un utilisateur, il obtient un abonnement aux catégories pour chaque carte de visite, données de calendrier, notes, services et catégories d’état.</span><span class="sxs-lookup"><span data-stu-id="39f47-p102">Limits the number of subscriber category subscriptions. For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="39f47-116">Un paramètre de 0 signifie que l’objet contact ou utilisateur ne peut pas être souscrit par d’autres.</span><span class="sxs-lookup"><span data-stu-id="39f47-116">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="39f47-117">Ce paramètre peut avoir un impact significatif sur les performances s’il est défini sur une valeur élevée, et l’utilisateur moyen a un grand nombre d’utilisateurs qui s’abonnent à sa présence.</span><span class="sxs-lookup"><span data-stu-id="39f47-117">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="39f47-118">Entier</span><span class="sxs-lookup"><span data-stu-id="39f47-118">Integer</span></span></p></td>
<td><p><span data-ttu-id="39f47-119">0-3000</span><span class="sxs-lookup"><span data-stu-id="39f47-119">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39f47-120">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="39f47-120">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="39f47-121">Nombre maximal d’alertes d’abonnement de présence mises en file d’attente</span><span class="sxs-lookup"><span data-stu-id="39f47-121">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="39f47-p103">Limite le nombre d’entrées dans la table des abonnés alertés. Ce paramètre détermine le nombre maximum d’alertes pouvant être mises en file d’attente pour un utilisateur donné. Par exemple, lorsque l’utilisateur A s’abonne à la présence de l’utilisateur B, ce dernier reçoit une alerte l’informant que l’utilisateur A est abonné à l’utilisateur B, et un accusé de réception est créé dans la table des abonnés alertés de l’utilisateur B. Lorsque l’utilisateur B accepte ou accuse réception de l’abonnement, l’alerte d’accusé de réception est supprimée de la table des abonnées alertés de l’utilisateur B.</span><span class="sxs-lookup"><span data-stu-id="39f47-p103">Limits the number of entries in the prompted subscribers table. This setting determines the maximum number of prompts that can be queued for a given user. For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table. After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="39f47-126">Un paramètre de 0 signifie que l’utilisateur n’est pas alerté lorsque quelqu’un s’abonne à sa présence.</span><span class="sxs-lookup"><span data-stu-id="39f47-126">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="39f47-127">Entier ou jeton</span><span class="sxs-lookup"><span data-stu-id="39f47-127">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="39f47-128">0-500</span><span class="sxs-lookup"><span data-stu-id="39f47-128">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="39f47-129">Par défaut, la stratégie et le **service** **par défaut** : les stratégies de présence moyennes sont installées lorsque vous déployez Lync Server.</span><span class="sxs-lookup"><span data-stu-id="39f47-129">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="39f47-130">Le tableau suivant décrit les paramètres spécifiques des deux stratégies de présence.</span><span class="sxs-lookup"><span data-stu-id="39f47-130">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="39f47-131">Stratégies de présence</span><span class="sxs-lookup"><span data-stu-id="39f47-131">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39f47-132">Nom de la stratégie</span><span class="sxs-lookup"><span data-stu-id="39f47-132">Policy name</span></span></th>
<th><span data-ttu-id="39f47-133">Description</span><span class="sxs-lookup"><span data-stu-id="39f47-133">Description</span></span></th>
<th><span data-ttu-id="39f47-134">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="39f47-134">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="39f47-135">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="39f47-135">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39f47-136">Stratégie par défaut</span><span class="sxs-lookup"><span data-stu-id="39f47-136">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="39f47-p105">Stratégies pour les utilisateurs types. Il s’agit de la stratégie de présence par défaut.</span><span class="sxs-lookup"><span data-stu-id="39f47-p105">Policy for typical users. This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="39f47-139">1000</span><span class="sxs-lookup"><span data-stu-id="39f47-139">1000</span></span></p></td>
<td><p><span data-ttu-id="39f47-140">200</span><span class="sxs-lookup"><span data-stu-id="39f47-140">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39f47-141">Service : moyen</span><span class="sxs-lookup"><span data-stu-id="39f47-141">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="39f47-142">Stratégie pour les applications qui ont besoin que plusieurs utilisateurs s’abonnent à la présence de l’objet.</span><span class="sxs-lookup"><span data-stu-id="39f47-142">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="39f47-143">1000</span><span class="sxs-lookup"><span data-stu-id="39f47-143">1000</span></span></p></td>
<td><p><span data-ttu-id="39f47-144">0</span><span class="sxs-lookup"><span data-stu-id="39f47-144">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013 : règles de traduction'
description: 'Lync Server 2013 : règles de traduction.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65ee21459123ea09f54eb52e65a4d9ecba61c386
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549040"
---
# <a name="translation-rules-in-lync-server-2013"></a><span data-ttu-id="62c0f-103">Règles de conversion dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62c0f-103">Translation rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62c0f-104">_**Dernière modification de la rubrique :** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="62c0f-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="62c0f-105">Lync Server 2013 Enterprise Voice nécessite que toutes les chaînes de numérotation soient normalisées au format E. 164 dans le but d’effectuer une recherche inversée des numéros (RNL).</span><span class="sxs-lookup"><span data-stu-id="62c0f-105">Lync Server 2013 Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="62c0f-106">Dans Microsoft Lync Server 2010, les règles de traduction sont prises en charge uniquement pour les numéros appelés.</span><span class="sxs-lookup"><span data-stu-id="62c0f-106">In Microsoft Lync Server 2010, translation rules are supported only for called numbers.</span></span> <span data-ttu-id="62c0f-107">Nouveauté de Microsoft Lync Server 2013, les règles de traduction sont également prises en charge pour les numéros d’appel.</span><span class="sxs-lookup"><span data-stu-id="62c0f-107">New in Microsoft Lync Server 2013, translation rules are also supported for calling numbers.</span></span> <span data-ttu-id="62c0f-108">L' *homologue de jonction* (c’est-à-dire, la passerelle associée, le PBX ou la jonction SIP) peut exiger que les numéros soient au format de numérotation local.</span><span class="sxs-lookup"><span data-stu-id="62c0f-108">The *trunk peer* (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="62c0f-109">Pour convertir des nombres au format E. 164 en un format de numérotation local, vous pouvez définir une ou plusieurs règles de traduction pour manipuler l’URI de la demande avant de l’acheminer vers l’homologue de jonction.</span><span class="sxs-lookup"><span data-stu-id="62c0f-109">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="62c0f-110">Par exemple, vous pouvez rédiger une règle de traduction pour remplacer « +44 » au début de la chaîne de numérotation par « 0144 ».</span><span class="sxs-lookup"><span data-stu-id="62c0f-110">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="62c0f-111">En effectuant une traduction de l’itinéraire sortant sur le serveur, vous pouvez réduire la configuration requise sur chaque homologue de jonction afin de convertir les numéros de téléphone dans un format de numérotation local.</span><span class="sxs-lookup"><span data-stu-id="62c0f-111">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="62c0f-112">Lorsque vous planifiez les passerelles, ainsi que le nombre de passerelles, à associer à un cluster de serveurs de médiation spécifique, il peut être utile de regrouper des homologues de jonction avec des exigences de numérotation locale similaires.</span><span class="sxs-lookup"><span data-stu-id="62c0f-112">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="62c0f-113">Cela peut réduire le nombre de règles de traduction requises et le temps nécessaire pour les écrire.</span><span class="sxs-lookup"><span data-stu-id="62c0f-113">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="62c0f-114">L’Association d’une ou de plusieurs règles de traduction à une configuration de jonction voix entreprise doit être utilisée à la place de la configuration des règles de traduction sur l’homologue de jonction.</span><span class="sxs-lookup"><span data-stu-id="62c0f-114">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="62c0f-115">N’associez pas de règles de conversion à une configuration de jonction voix entreprise si vous avez configuré des règles de traduction sur l’homologue de jonction, car les deux règles peuvent entrer en conflit.</span><span class="sxs-lookup"><span data-stu-id="62c0f-115">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>



</div>

<div>

## <a name="example-translation-rules"></a><span data-ttu-id="62c0f-116">Exemples de règles de traduction</span><span class="sxs-lookup"><span data-stu-id="62c0f-116">Example Translation Rules</span></span>

<span data-ttu-id="62c0f-117">Les exemples de règles de conversion suivants montrent comment vous pouvez développer des règles sur le serveur pour traduire des nombres d’un format E. 164 vers un format local pour l’homologue de jonction.</span><span class="sxs-lookup"><span data-stu-id="62c0f-117">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="62c0f-118">Pour plus d’informations sur la façon d’implémenter des règles de traduction, voir [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="62c0f-118">For details about how to implement translation rules, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62c0f-119">Description</span><span class="sxs-lookup"><span data-stu-id="62c0f-119">Description</span></span></th>
<th><span data-ttu-id="62c0f-120">Chiffres de début</span><span class="sxs-lookup"><span data-stu-id="62c0f-120">Starting Digits</span></span></th>
<th><span data-ttu-id="62c0f-121">Longueur</span><span class="sxs-lookup"><span data-stu-id="62c0f-121">Length</span></span></th>
<th><span data-ttu-id="62c0f-122">Chiffres à supprimer</span><span class="sxs-lookup"><span data-stu-id="62c0f-122">Digits to Remove</span></span></th>
<th><span data-ttu-id="62c0f-123">Chiffres à ajouter</span><span class="sxs-lookup"><span data-stu-id="62c0f-123">Digits to Add</span></span></th>
<th><span data-ttu-id="62c0f-124">Modèle de correspondance</span><span class="sxs-lookup"><span data-stu-id="62c0f-124">Matching Pattern</span></span></th>
<th><span data-ttu-id="62c0f-125">Conversion</span><span class="sxs-lookup"><span data-stu-id="62c0f-125">Translation</span></span></th>
<th><span data-ttu-id="62c0f-126">Exemple</span><span class="sxs-lookup"><span data-stu-id="62c0f-126">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62c0f-127">Numérotation longue distance conventionnelle aux États-Unis</span><span class="sxs-lookup"><span data-stu-id="62c0f-127">Conventional long-distance dialing in U.S.</span></span></p>
<p><span data-ttu-id="62c0f-128">(supprimer le signe « + »)</span><span class="sxs-lookup"><span data-stu-id="62c0f-128">(strip out the ‘+’)</span></span></p></td>
<td><p><span data-ttu-id="62c0f-129">+ 1</span><span class="sxs-lookup"><span data-stu-id="62c0f-129">+1</span></span></p></td>
<td><p><span data-ttu-id="62c0f-130">Exactement 12</span><span class="sxs-lookup"><span data-stu-id="62c0f-130">Exactly 12</span></span></p></td>
<td><p><span data-ttu-id="62c0f-131">0,1</span><span class="sxs-lookup"><span data-stu-id="62c0f-131">1</span></span></p></td>
<td><p><span data-ttu-id="62c0f-132">0</span><span class="sxs-lookup"><span data-stu-id="62c0f-132">0</span></span></p></td>
<td><p><span data-ttu-id="62c0f-133">^\+(1 \ d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="62c0f-133">^\+(1\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="62c0f-134">$1</span><span class="sxs-lookup"><span data-stu-id="62c0f-134">$1</span></span></p></td>
<td><p><span data-ttu-id="62c0f-135">+ 14255551010 devient 14255551010</span><span class="sxs-lookup"><span data-stu-id="62c0f-135">+14255551010 becomes 14255551010</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62c0f-136">Numérotation longue distance pour les États-Unis internationaux</span><span class="sxs-lookup"><span data-stu-id="62c0f-136">U.S. international long-distance dialing</span></span></p>
<p><span data-ttu-id="62c0f-137">(supprimer' + 'et ajouter 011)</span><span class="sxs-lookup"><span data-stu-id="62c0f-137">(strip out ‘+’ and add 011)</span></span></p></td>
<td><p>+</p></td>
<td><p><span data-ttu-id="62c0f-138">Au moins 11</span><span class="sxs-lookup"><span data-stu-id="62c0f-138">At least 11</span></span></p></td>
<td><p><span data-ttu-id="62c0f-139">0,1</span><span class="sxs-lookup"><span data-stu-id="62c0f-139">1</span></span></p></td>
<td><p><span data-ttu-id="62c0f-140">011</span><span class="sxs-lookup"><span data-stu-id="62c0f-140">011</span></span></p></td>
<td><p><span data-ttu-id="62c0f-141">^\+(\d {9} \d +) $</span><span class="sxs-lookup"><span data-stu-id="62c0f-141">^\+(\d{9}\d+)$</span></span></p></td>
<td><p><span data-ttu-id="62c0f-142">011 $1</span><span class="sxs-lookup"><span data-stu-id="62c0f-142">011$1</span></span></p></td>
<td><p><span data-ttu-id="62c0f-143">+ 441235551010 devient 011441235551010</span><span class="sxs-lookup"><span data-stu-id="62c0f-143">+441235551010 becomes 011441235551010</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


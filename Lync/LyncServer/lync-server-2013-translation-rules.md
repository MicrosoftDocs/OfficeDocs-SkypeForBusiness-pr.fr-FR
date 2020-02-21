---
title: 'Lync Server 2013 : règles de traduction'
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
ms.openlocfilehash: d1576b9c0c7286150c62f1491960bf9beef5d700
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a><span data-ttu-id="405f2-102">Règles de conversion dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="405f2-102">Translation rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="405f2-103">_**Dernière modification de la rubrique :** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="405f2-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="405f2-104">Lync Server 2013 Enterprise Voice nécessite que toutes les chaînes de numérotation soient normalisées au format E. 164 dans le but d’effectuer une recherche inversée des numéros (RNL).</span><span class="sxs-lookup"><span data-stu-id="405f2-104">Lync Server 2013 Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="405f2-105">Dans Microsoft Lync Server 2010, les règles de traduction sont prises en charge uniquement pour les numéros appelés.</span><span class="sxs-lookup"><span data-stu-id="405f2-105">In Microsoft Lync Server 2010, translation rules are supported only for called numbers.</span></span> <span data-ttu-id="405f2-106">Nouveauté de Microsoft Lync Server 2013, les règles de traduction sont également prises en charge pour les numéros d’appel.</span><span class="sxs-lookup"><span data-stu-id="405f2-106">New in Microsoft Lync Server 2013, translation rules are also supported for calling numbers.</span></span> <span data-ttu-id="405f2-107">L' *homologue de jonction* (c’est-à-dire, la passerelle associée, le PBX ou la jonction SIP) peut exiger que les numéros soient au format de numérotation local.</span><span class="sxs-lookup"><span data-stu-id="405f2-107">The *trunk peer* (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="405f2-108">Pour convertir des nombres au format E. 164 en un format de numérotation local, vous pouvez définir une ou plusieurs règles de traduction pour manipuler l’URI de la demande avant de l’acheminer vers l’homologue de jonction.</span><span class="sxs-lookup"><span data-stu-id="405f2-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="405f2-109">Par exemple, vous pouvez rédiger une règle de traduction pour remplacer « +44 » au début de la chaîne de numérotation par « 0144 ».</span><span class="sxs-lookup"><span data-stu-id="405f2-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="405f2-110">En effectuant une traduction de l’itinéraire sortant sur le serveur, vous pouvez réduire la configuration requise sur chaque homologue de jonction afin de convertir les numéros de téléphone dans un format de numérotation local.</span><span class="sxs-lookup"><span data-stu-id="405f2-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="405f2-111">Lorsque vous planifiez les passerelles, ainsi que le nombre de passerelles, à associer à un cluster de serveurs de médiation spécifique, il peut être utile de regrouper des homologues de jonction avec des exigences de numérotation locale similaires.</span><span class="sxs-lookup"><span data-stu-id="405f2-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="405f2-112">Cela peut réduire le nombre de règles de traduction requises et le temps nécessaire pour les écrire.</span><span class="sxs-lookup"><span data-stu-id="405f2-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="405f2-113">L’Association d’une ou de plusieurs règles de traduction à une configuration de jonction voix entreprise doit être utilisée à la place de la configuration des règles de traduction sur l’homologue de jonction.</span><span class="sxs-lookup"><span data-stu-id="405f2-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="405f2-114">N’associez pas de règles de conversion à une configuration de jonction voix entreprise si vous avez configuré des règles de traduction sur l’homologue de jonction, car les deux règles peuvent entrer en conflit.</span><span class="sxs-lookup"><span data-stu-id="405f2-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>



</div>

<div>

## <a name="example-translation-rules"></a><span data-ttu-id="405f2-115">Exemples de règles de traduction</span><span class="sxs-lookup"><span data-stu-id="405f2-115">Example Translation Rules</span></span>

<span data-ttu-id="405f2-116">Les exemples de règles de conversion suivants montrent comment vous pouvez développer des règles sur le serveur pour traduire des nombres d’un format E. 164 vers un format local pour l’homologue de jonction.</span><span class="sxs-lookup"><span data-stu-id="405f2-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="405f2-117">Pour plus d’informations sur la façon d’implémenter des règles de traduction, voir [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="405f2-117">For details about how to implement translation rules, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>


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
<th><span data-ttu-id="405f2-118">Description</span><span class="sxs-lookup"><span data-stu-id="405f2-118">Description</span></span></th>
<th><span data-ttu-id="405f2-119">Chiffres de début</span><span class="sxs-lookup"><span data-stu-id="405f2-119">Starting Digits</span></span></th>
<th><span data-ttu-id="405f2-120">Longueur</span><span class="sxs-lookup"><span data-stu-id="405f2-120">Length</span></span></th>
<th><span data-ttu-id="405f2-121">Chiffres à supprimer</span><span class="sxs-lookup"><span data-stu-id="405f2-121">Digits to Remove</span></span></th>
<th><span data-ttu-id="405f2-122">Chiffres à ajouter</span><span class="sxs-lookup"><span data-stu-id="405f2-122">Digits to Add</span></span></th>
<th><span data-ttu-id="405f2-123">Modèle de correspondance</span><span class="sxs-lookup"><span data-stu-id="405f2-123">Matching Pattern</span></span></th>
<th><span data-ttu-id="405f2-124">Conversion</span><span class="sxs-lookup"><span data-stu-id="405f2-124">Translation</span></span></th>
<th><span data-ttu-id="405f2-125">Exemple</span><span class="sxs-lookup"><span data-stu-id="405f2-125">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="405f2-126">Numérotation longue distance conventionnelle aux États-Unis</span><span class="sxs-lookup"><span data-stu-id="405f2-126">Conventional long-distance dialing in U.S.</span></span></p>
<p><span data-ttu-id="405f2-127">(supprimer le signe « + »)</span><span class="sxs-lookup"><span data-stu-id="405f2-127">(strip out the ‘+’)</span></span></p></td>
<td><p><span data-ttu-id="405f2-128">+ 1</span><span class="sxs-lookup"><span data-stu-id="405f2-128">+1</span></span></p></td>
<td><p><span data-ttu-id="405f2-129">Exactement 12</span><span class="sxs-lookup"><span data-stu-id="405f2-129">Exactly 12</span></span></p></td>
<td><p><span data-ttu-id="405f2-130">0,1</span><span class="sxs-lookup"><span data-stu-id="405f2-130">1</span></span></p></td>
<td><p><span data-ttu-id="405f2-131">0</span><span class="sxs-lookup"><span data-stu-id="405f2-131">0</span></span></p></td>
<td><p><span data-ttu-id="405f2-132">^\+(1 \ d{10}) $</span><span class="sxs-lookup"><span data-stu-id="405f2-132">^\+(1\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="405f2-133">$1</span><span class="sxs-lookup"><span data-stu-id="405f2-133">$1</span></span></p></td>
<td><p><span data-ttu-id="405f2-134">+ 14255551010 devient 14255551010</span><span class="sxs-lookup"><span data-stu-id="405f2-134">+14255551010 becomes 14255551010</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="405f2-135">Numérotation longue distance pour les États-Unis internationaux</span><span class="sxs-lookup"><span data-stu-id="405f2-135">U.S. international long-distance dialing</span></span></p>
<p><span data-ttu-id="405f2-136">(supprimer' + 'et ajouter 011)</span><span class="sxs-lookup"><span data-stu-id="405f2-136">(strip out ‘+’ and add 011)</span></span></p></td>
<td><p>+</p></td>
<td><p><span data-ttu-id="405f2-137">Au moins 11</span><span class="sxs-lookup"><span data-stu-id="405f2-137">At least 11</span></span></p></td>
<td><p><span data-ttu-id="405f2-138">0,1</span><span class="sxs-lookup"><span data-stu-id="405f2-138">1</span></span></p></td>
<td><p><span data-ttu-id="405f2-139">011</span><span class="sxs-lookup"><span data-stu-id="405f2-139">011</span></span></p></td>
<td><p><span data-ttu-id="405f2-140">^\+(\d{9}\d +) $</span><span class="sxs-lookup"><span data-stu-id="405f2-140">^\+(\d{9}\d+)$</span></span></p></td>
<td><p><span data-ttu-id="405f2-141">011 $1</span><span class="sxs-lookup"><span data-stu-id="405f2-141">011$1</span></span></p></td>
<td><p><span data-ttu-id="405f2-142">+ 441235551010 devient 011441235551010</span><span class="sxs-lookup"><span data-stu-id="405f2-142">+441235551010 becomes 011441235551010</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


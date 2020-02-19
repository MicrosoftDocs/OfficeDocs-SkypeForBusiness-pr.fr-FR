---
title: 'Lync Server 2013 : vue d’ensemble de l’application d’annonce'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Announcement application
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204757(v=OCS.15)
ms:contentKeyID: 48183689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 264fbf5faf3fbce830a8d55cd7626d1ff67c2d58
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="b83b8-102">Vue d’ensemble de l’application d’annonce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b83b8-102">Overview of the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b83b8-103">_**Dernière modification de la rubrique :** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="b83b8-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="b83b8-104">Lorsque vous déployez l’application d’annonce, vous devez configurer une table de numéros non attribués qui détermine l’action à effectuer lorsqu’un utilisateur compose un numéro non attribué.</span><span class="sxs-lookup"><span data-stu-id="b83b8-104">When you deploy the Announcement application, you need to configure an unassigned number table that determines the action to be taken when someone dials an unassigned number.</span></span> <span data-ttu-id="b83b8-105">La table des numéros non attribués contient des plages de numéros de téléphone valides pour l’organisation et spécifie l’application d’annonce qui gère chaque plage.</span><span class="sxs-lookup"><span data-stu-id="b83b8-105">The unassigned number table contains ranges of phone numbers that are valid for the organization and specifies which Announcement application handles each range.</span></span> <span data-ttu-id="b83b8-106">Lorsqu’un appelant compose un numéro de téléphone qui est valide pour votre organisation, mais qui n’est attribué à personne, Lync Server consulte le numéro de la table de routage des numéros non attribués, identifie la plage dans laquelle le numéro se trouve et achemine l’appel vers l’annonce. application spécifiée pour cette plage.</span><span class="sxs-lookup"><span data-stu-id="b83b8-106">When a caller dials a telephone number that is valid for your organization but is not assigned to anyone, Lync Server looks up the number in the unassigned number routing table, identifies which range the number falls in, and routes the call to the Announcement application specified for that range.</span></span> <span data-ttu-id="b83b8-107">L’application d’annonce répond à l’appel et lit un message audio (si vous l’avez configurée), puis déconnecte l’appel ou le transfère à une destination prédéterminée, par exemple pour un opérateur.</span><span class="sxs-lookup"><span data-stu-id="b83b8-107">The Announcement application answers the call and plays an audio message (if you configured it to do so) and then either disconnects the call or transfers it to a predetermined destination, such as to an operator.</span></span> <span data-ttu-id="b83b8-108">Vous pouvez utiliser les applets de commande Lync Server Management Shell pour configurer plusieurs messages audio ou transférer des destinations.</span><span class="sxs-lookup"><span data-stu-id="b83b8-108">You can use Lync Server Management Shell cmdlets to configure multiple audio messages or to transfer destinations.</span></span>

<span data-ttu-id="b83b8-p102">La manière dont vous configurez la table des numéros non attribués dépend de la façon dont vous comptez l’utiliser. Si vous avez des numéros spécifiques qui ne sont plus utilisés et que vous voulez lire des messages personnalisés pour chacun d’eux, vous pouvez entrer ces numéros spécifiques dans la table des numéros non attribués. Par exemple, si vous avez changé le numéro du bureau de service client, vous pouvez entrer l’ancien numéro du service client et l’associer à une annonce qui indique le nouveau. Si vous voulez lire un message général à quiconque appelle un numéro non attribué (comme celui d’un employé ayant quitté votre organisation), vous pouvez entrer des plages pour toutes les extensions valides de votre organisation. La table des numéros non attribués est appelée à chaque fois qu’un appelant compose un numéro qui n’est pas actuellement attribué.</span><span class="sxs-lookup"><span data-stu-id="b83b8-p102">How you configure the unassigned number table depends on how you want to use it. If you have specific numbers that are no longer in use and you want to play messages that are tailored for each number, you can enter those specific numbers in the unassigned number table. For example, if you changed the number for your customer service desk, you can enter the old customer service number and associate it with an announcement that gives the new number. If you want to play a general message to anyone who calls a number that is not assigned, such as for employees who have left your organization, you can enter ranges for all the valid extensions in your organization. The unassigned number table is invoked whenever the caller dials a number that is not currently assigned.</span></span>

<span data-ttu-id="b83b8-114">Dans Lync Server 2013, l’application d’annonce est automatiquement installée avec l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="b83b8-114">In Lync Server 2013, the Announcement application is automatically installed with the Response Group application.</span></span> <span data-ttu-id="b83b8-115">Les applications annonce et Response Group sont des composants standard d’un déploiement voix entreprise : lorsque vous déployez voix entreprise, ces deux applications sont déployées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="b83b8-115">The Announcement and Response Group applications are standard components of an Enterprise Voice deployment: When you deploy Enterprise Voice, both of these applications are automatically deployed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


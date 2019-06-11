---
title: 'Lync Server 2013: vue d’ensemble de l’application annonce'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Announcement application
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204757(v=OCS.15)
ms:contentKeyID: 48183689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0e9cedddf6dfdf714bb3d0eef0e0cd01063b89f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a>Présentation de l’application annonce dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-13_

Lorsque vous déployez l’application d’annonce, vous devez configurer une table numérotée non assignée qui détermine l’action à entreprendre lorsque quelqu’un compose un numéro non attribué. La table numéro non affecté contient des plages de numéros de téléphone valides pour l’organisation et spécifie l’application d’annonce qui gère chaque plage. Lorsqu’un utilisateur compose un numéro de téléphone valide pour votre organisation, mais qu’il n’est pas attribué à une personne, Lync Server recherche le numéro dans la table de routage des numéros non attribués, identifie la plage dans laquelle se trouve le numéro et achemine l’appel vers l’annonce. application spécifiée pour cette plage. L’application d’annonce répond à l’appel et lit un message audio (si vous l’avez configurée), puis déconnecte l’appel ou le transfère à une destination prédéfinie (par exemple, un opérateur). Vous pouvez utiliser les applets de cmdlet Lync Server Management Shell pour configurer plusieurs messages audio ou pour transférer des destinations.

La manière dont vous configurez la table des numéros non attribués dépend de la façon dont vous comptez l’utiliser. Si vous avez des numéros spécifiques qui ne sont plus utilisés et que vous voulez lire des messages personnalisés pour chacun d’eux, vous pouvez entrer ces numéros spécifiques dans la table des numéros non attribués. Par exemple, si vous avez changé le numéro du bureau de service client, vous pouvez entrer l’ancien numéro du service client et l’associer à une annonce qui indique le nouveau. Si vous voulez lire un message général à quiconque appelle un numéro non attribué (comme celui d’un employé ayant quitté votre organisation), vous pouvez entrer des plages pour toutes les extensions valides de votre organisation. La table des numéros non attribués est appelée à chaque fois qu’un appelant compose un numéro qui n’est pas actuellement attribué.

Dans Lync Server 2013, l’application d’annonce est automatiquement installée avec l’application Response Group. Les applications d’annonce et de groupe de réponse sont des composants standard d’un déploiement voix entreprise: lorsque vous déployez une voix entreprise, ces deux applications sont déployées automatiquement.

</div>

<span> </span>

</div>

</div>

</div>


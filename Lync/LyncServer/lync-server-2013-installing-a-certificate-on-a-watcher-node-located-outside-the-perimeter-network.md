---
title: 'Lync Server 2013 : installation d’un certificat sur un nœud observateur situé en dehors du réseau de périmètre'
description: 'Lync Server 2013 : installation d’un certificat sur un nœud observateur situé en dehors du réseau de périmètre.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing a certificate on a watcher node located outside the perimeter network
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49733711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66f40886e9784b5bd4182a60b955745b5daf2034
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574030"
---
# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a><span data-ttu-id="ea8df-103">Installation d’un certificat sur un nœud observateur situé en dehors du réseau de périmètre de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea8df-103">Installing a certificate on a watcher node located outside the perimeter network of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea8df-104">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="ea8df-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="ea8df-105">Les agents System Center Operations Manager exécutés dans un réseau de périmètre (tel qu’un serveur Edge Lync Server), en dehors de l’entreprise (comme un nœud observateur de transaction synthétique externe) ou dans une limite d’approbation des services de domaine Active Directory, peuvent nécessiter la configuration d’un serveur de passerelle System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="ea8df-105">System Center Operations Manager agents running in a perimeter network (such as a Lync Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory Domain Services trust boundary, might require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="ea8df-106">Ce rôle serveur permet à des agents qui n’ont pas de relation d’approbation avec le serveur d’administration racine de déclencher des alertes.</span><span class="sxs-lookup"><span data-stu-id="ea8df-106">This server role allows agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="ea8df-107">Pour plus d’informations, consultez la rubrique relative à la gestion des serveurs de passerelle dans Operations Manager 2007 dans la bibliothèque TechNet de System Center Operations Manager à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703) .</span><span class="sxs-lookup"><span data-stu-id="ea8df-107">For details, see "Managing Gateway Servers in Operations Manager 2007" in the System Center Operations Manager TechNet Library at [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703).</span></span>

<span data-ttu-id="ea8df-108">Si vous déployez un agent à l’un de ces emplacements, vous devrez également demander et configurer un certificat qui permet au nœud observateur d’envoyer des alertes à System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="ea8df-108">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="ea8df-109">Pour simplifier ce processus, l’équipe Operations Manager a créé un ensemble d’utilitaires qui vous permettent de demander et d’installer le type correct de certificat sur l’ordinateur du nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="ea8df-109">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="ea8df-110">Pour plus d’informations et pour télécharger ces utilitaires, voir l’article sur le blog « obtention de certificats pour les agents non joints à un domaine en plus de l’Assistant génération de certificat » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421) .</span><span class="sxs-lookup"><span data-stu-id="ea8df-110">For details, and to download these utilities, see the "Obtaining Certificates for Non-Domain Joined Agents Made Easy With Certificate Generation Wizard" blog article at [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: liste de vérification de déploiement de contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdda2e5231beb9f8303684ff29075c6322654945
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="c7d35-102">Liste de contrôle du déploiement de contrôle d’admission des appels pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7d35-102">Call admission control deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7d35-103">_**Dernière modification de la rubrique:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="c7d35-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="c7d35-104">Utilisez la liste de vérification suivante pour vérifier que vous avez effectué toutes les tâches de configuration nécessaires pour déployer le contrôle d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="c7d35-104">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy call admission control (CAC).</span></span>

  - <span data-ttu-id="c7d35-105">Si au moins un serveur Edge est déployé, chaque adresse IP de l’interface externe doit être ajoutée à la liste des sous-réseaux dans les paramètres de configuration du réseau, avec un masque de bits de 32.</span><span class="sxs-lookup"><span data-stu-id="c7d35-105">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="c7d35-106">Vous devez également associer ce sous-réseau (adresse IP) à l’ID de site réseau pour l’emplacement géographique auquel le service Edge A/V est déployé.</span><span class="sxs-lookup"><span data-stu-id="c7d35-106">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c7d35-107">Il n’est pas nécessaire de mettre en place des serveurs de périphérie pour le CAC.</span><span class="sxs-lookup"><span data-stu-id="c7d35-107">Edge servers are not required to implement CAC.</span></span>

    
    </div>

  - <span data-ttu-id="c7d35-108">Assurez-vous que l’option CAC est activée via le panneau de configuration de Lync Server ou en exécutant l’applet de commande, comme indiqué dans [activer le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="c7d35-108">Make sure that CAC is enabled, either through Lync Server Control Panel or by running the cmdlet as specified in [Enable call admission control in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span></span>

  - <span data-ttu-id="c7d35-109">Vérifiez que le contrôle d’admission des appels est activé sur tous les sites centraux.</span><span class="sxs-lookup"><span data-stu-id="c7d35-109">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="c7d35-110">Cette opération peut être réalisée par le biais du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="c7d35-110">This can be done through the Topology Builder.</span></span> <span data-ttu-id="c7d35-111">Si un avertissement s’affiche lors de la publication, ne l’ignorez *pas*.</span><span class="sxs-lookup"><span data-stu-id="c7d35-111">If a warning is generated when you publish, *do not* ignore it.</span></span>

  - <span data-ttu-id="c7d35-112">Vérifiez que tous les sous-réseaux gérés dans le réseau d’entreprise sont configurés dans les paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="c7d35-112">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="c7d35-113">Il est également essentiel que chaque sous-réseau soit associé à un site réseau, comme décrit dans la rubrique [associez un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="c7d35-113">It is also essential that every subnet be associated to a network site, as explained in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

  - <span data-ttu-id="c7d35-114">Vérifiez que les adresses IP ou de sous-réseau de tous les serveurs frontaux, SBA (Survivable Branch Appliances), serveurs de conférence audio/vidéo (s’ils figurent dans un pool distinct) et serveurs de médiation sont configurées dans les paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="c7d35-114">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013 : liste de vérification du déploiement du contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd1de11f9d169babc8a4367f429d9d99559d6aa6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="40c41-102">Liste de vérification du déploiement du contrôle d’admission des appels pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40c41-102">Call admission control deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40c41-103">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="40c41-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="40c41-104">Servez-vous de la liste de contrôle suivante pour vérifier que vous avez exécuté toutes les tâches de configuration nécessaires au déploiement du contrôle d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="40c41-104">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy call admission control (CAC).</span></span>

  - <span data-ttu-id="40c41-p101">Si un ou plusieurs serveurs Edge sont déployés, chaque adresse IP de l’interface externe doit être ajoutée à la liste de sous-réseaux dans les paramètres de configuration réseau, avec un masque de 32 bits. Vous devez également associer ce sous-réseau (adresse IP) à l’ID de site réseau pour l’emplacement géographique où est déployé le service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="40c41-p101">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32. You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="40c41-107">Il n’est pas obligatoire que les serveurs Edge implémentent le contrôle d’admission des appels.</span><span class="sxs-lookup"><span data-stu-id="40c41-107">Edge servers are not required to implement CAC.</span></span>

    
    </div>

  - <span data-ttu-id="40c41-108">Assurez-vous que le contrôle d’admission des appels est activé, soit via le panneau de configuration de Lync Server, soit en exécutant l’applet de commande, comme indiqué dans [Enable Call Admission Control in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="40c41-108">Make sure that CAC is enabled, either through Lync Server Control Panel or by running the cmdlet as specified in [Enable call admission control in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span></span>

  - <span data-ttu-id="40c41-109">Vérifiez que le contrôle d’admission des appels est activé sur tous les sites centraux.</span><span class="sxs-lookup"><span data-stu-id="40c41-109">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="40c41-110">Pour ce faire, vous pouvez utiliser le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="40c41-110">This can be done through the Topology Builder.</span></span> <span data-ttu-id="40c41-111">Si un avertissement s’affiche lors de la publication, ne l’ignorez *pas*.</span><span class="sxs-lookup"><span data-stu-id="40c41-111">If a warning is generated when you publish, *do not* ignore it.</span></span>

  - <span data-ttu-id="40c41-112">Vérifiez que tous les sous-réseaux qui sont gérés dans le réseau d’entreprise sont configurés dans les paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="40c41-112">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="40c41-113">Il est également essentiel que chaque sous-réseau soit associé à un site réseau, comme expliqué dans [Associate a Subnet with a Network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="40c41-113">It is also essential that every subnet be associated to a network site, as explained in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

  - <span data-ttu-id="40c41-114">Vérifiez que les adresses IP ou de sous-réseau de tous les serveurs frontaux, SBA (Survivable Branch Appliances), serveurs de conférence Audio/Vidéo (s’ils figurent dans un pool distinct) et serveurs de médiation sont configurées dans les paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="40c41-114">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013 : déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server'
description: 'Lync Server 2013 : déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8c8610ab85b61d33a5f181f1d5f51d0e5095f49
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558590"
---
# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a><span data-ttu-id="db079-103">Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db079-103">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db079-104">_**Dernière modification de la rubrique :** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="db079-104">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="db079-105">La voix entreprise fiable fait référence à la résistance des sites de succursale, c’est-à-dire à la possibilité de fournir un service voix entreprise continu aux utilisateurs de sites de succursales, si le lien vers le site central devient indisponible.</span><span class="sxs-lookup"><span data-stu-id="db079-105">Resilient Enterprise Voice refers to branch-site resiliency, that is, the ability to provide continuous Enterprise Voice service to branch site users in the event that the link to the central site becomes unavailable.</span></span>

<span data-ttu-id="db079-106">Pour les sites de succursale de petite et moyenne taille (sites de succursale avec 25 à 1 000 utilisateurs), nous vous recommandons de déployer un Survivable Branch appliance, qui mettra fin aux appels RTC (réseau téléphonique commuté) à l’aide de sa passerelle PSTN intégrée ou d’une jonction SIP vers un fournisseur de services téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="db079-106">For small and medium-sized branch sites (branch sites with 25 to 1,000 users), we recommend deploying a Survivable Branch Appliance, which will terminate public switched telephone network (PSTN) calls by using its built-in PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="db079-107">Un Survivable Branch Appliance est un périphérique tiers qui inclut un serveur de Blades exécutant le système d’exploitation Windows Server 2008 R2, le serveur d’inscriptions Lync Server 2013, le logiciel de serveur de médiation et une passerelle PSTN, tous dans un seul châssis d’appareil.</span><span class="sxs-lookup"><span data-stu-id="db079-107">A Survivable Branch Appliance is a third-party device that includes a blade server running the Windows Server 2008 R2 operating system, Lync Server 2013 Registrar, Mediation Server software, and a PSTN gateway, all in a single appliance chassis.</span></span>

<span data-ttu-id="db079-108">Pour les sites de succursale avec 1 000 à 5 000 utilisateurs et pas de réseau étendu (WAN) résilient, nous recommandons un serveur Survivable Branch Server connecté à une passerelle PSTN ou une jonction SIP avec un fournisseur de services téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="db079-108">For branch sites with 1,000 to 5,000 users and no resilient WAN, we recommend a Survivable Branch Server connected to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="db079-109">Un serveur Survivable Branch Server est un ordinateur Windows Server sur lequel est installé le logiciel de serveur d’inscriptions et de médiation.</span><span class="sxs-lookup"><span data-stu-id="db079-109">A Survivable Branch Server is a Windows Server-based computer that has Registrar and Mediation Server software installed on it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="db079-110">Pour les sites de succursale comportant plus de 5 000 utilisateurs et des administrateurs Lync Server dédiés, nous vous recommandons d’utiliser un déploiement complet de Lync Server 2013, distinct de celui du site central.</span><span class="sxs-lookup"><span data-stu-id="db079-110">For branch sites with more than 5,000 users and dedicated Lync Server administrators, we recommend a full Lync Server 2013 deployment, separate from that of the central site.</span></span><BR><span data-ttu-id="db079-111">Pour plus d’informations sur le choix de la meilleure solution de résilience pour les sites de succursale de votre organisation, notamment les conditions préalables et les considérations de planification, voir <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site Resiliency Requirements for Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="db079-111">For details about choosing the best resiliency solution for the branch sites in your organization, including prerequisites and planning considerations, see <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="db079-112">Les utilisateurs hébergés sur une appliance Survivable Branch Lync Server ne peuvent pas créer de nouvelles salles de conversation ni afficher la carte de salle pour les salles existantes.</span><span class="sxs-lookup"><span data-stu-id="db079-112">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="db079-113">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="db079-113">In This Section</span></span>

  - [<span data-ttu-id="db079-114">Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec Lync Server 2013-tâches de site central</span><span class="sxs-lookup"><span data-stu-id="db079-114">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [<span data-ttu-id="db079-115">Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec la tâche Lync Server 2013-Branch site</span><span class="sxs-lookup"><span data-stu-id="db079-115">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [<span data-ttu-id="db079-116">Configuration des utilisateurs pour la résistance des sites de succursale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db079-116">Configuring users for branch site resiliency in Lync Server 2013</span></span>](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [<span data-ttu-id="db079-117">Utilisateurs domestiques sur un Survivable Branch Appliance ou un serveur Survivable Branch Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db079-117">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [<span data-ttu-id="db079-118">Annexes : Survivable Branch Appliances and Servers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db079-118">Appendices: Survivable Branch Appliances and Servers in Lync Server 2013</span></span>](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="db079-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="db079-119">See Also</span></span>


[<span data-ttu-id="db079-120">Déploiement de Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db079-120">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


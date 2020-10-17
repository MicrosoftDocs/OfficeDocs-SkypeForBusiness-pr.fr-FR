---
title: Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server-tâches de site central
description: Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server-tâches de site central.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4460ea215d6fc80ee89f1ca9bc42f08ac5d14617
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558600"
---
# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a><span data-ttu-id="fe2c5-103">Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec Lync Server 2013-tâches de site central</span><span class="sxs-lookup"><span data-stu-id="fe2c5-103">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe2c5-104">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="fe2c5-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="fe2c5-105">Effectuez les tâches de cette section sur le site central.</span><span class="sxs-lookup"><span data-stu-id="fe2c5-105">Complete the tasks in this section at the central site.</span></span> <span data-ttu-id="fe2c5-106">Si vous déployez un serveur Survivable Branch Server, ignorez la première tâche.</span><span class="sxs-lookup"><span data-stu-id="fe2c5-106">If you’re deploying a Survivable Branch Server, skip the first task.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="fe2c5-107">Avant d’effectuer les tâches dans cette section, les conditions suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="fe2c5-107">Before you perform the tasks in this section, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="fe2c5-108">Lync Server doit être configuré sur le site central.</span><span class="sxs-lookup"><span data-stu-id="fe2c5-108">Lync Server must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="fe2c5-109">Un technicien d’installation du site de succursale doit être ajouté au groupe RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="fe2c5-109">An installation technician at the branch site must be added to the RTCUniversalSBATechnicians group.</span></span></P></LI></UL><span data-ttu-id="fe2c5-110">En outre, nous vous recommandons d’effectuer ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="fe2c5-110">In addition, we recommend that you do the following:</span></span>
> <UL>
> <LI>
> <P><span data-ttu-id="fe2c5-111">Déployez un serveur DHCP sur chaque site de succursale pour permettre aux clients d’obtenir les adresses IP.</span><span class="sxs-lookup"><span data-stu-id="fe2c5-111">Deploy a DHCP server at each branch site to enable clients to obtain IP addresses.</span></span></P>
> <LI>
> <P><span data-ttu-id="fe2c5-112">En guise d’alternative au déploiement d’un serveur DHCP sur chaque site de succursale, vous pouvez activer le protocole DHCP Lync Server sur le Survivable Branch Appliance ou le serveur Survivable Branch Server à l’aide de la cmdlet Lync Server Management Shell <STRONG>Set-CsRegistrarConfiguration – EnableDHCPServer $true</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="fe2c5-112">As an alternative to deploying a DHCP server at each branch site, enable Lync Server DHCP on the Survivable Branch Appliance or Survivable Branch Server by using the Lync Server Management Shell cmdlet <STRONG>Set-CsRegistrarConfiguration –EnableDHCPServer $true</STRONG>.</span></span> <span data-ttu-id="fe2c5-113">Pour plus d’informations, reportez-vous à la section Configuration matérielle et logicielle requise <A href="lync-server-2013-branch-site-resiliency-requirements.md">pour la résistance des sites de succursale pour Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="fe2c5-113">For details, see the “Hardware and Software Requirements” section of <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fe2c5-114">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="fe2c5-114">In This Section</span></span>

  - [<span data-ttu-id="fe2c5-115">Ajouter un Survivable Branch appliance à Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe2c5-115">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [<span data-ttu-id="fe2c5-116">Ajouter des sites de succursale à votre topologie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe2c5-116">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="fe2c5-117">Définition d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe2c5-117">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


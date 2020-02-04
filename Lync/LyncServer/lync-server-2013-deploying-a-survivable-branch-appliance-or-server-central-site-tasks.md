---
title: Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server - Tâches pour un site central
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
ms.openlocfilehash: a9aa6d38ec873652feae6ef6a374ee5b771520b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a><span data-ttu-id="58745-102">Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec Lync Server 2013 - Tâches pour un site central</span><span class="sxs-lookup"><span data-stu-id="58745-102">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58745-103">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="58745-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="58745-104">Suivez les étapes décrites dans cette section sur le site central.</span><span class="sxs-lookup"><span data-stu-id="58745-104">Complete the tasks in this section at the central site.</span></span> <span data-ttu-id="58745-105">Si vous déployez un serveur de succursales survivant, ignorez la première tâche.</span><span class="sxs-lookup"><span data-stu-id="58745-105">If you’re deploying a Survivable Branch Server, skip the first task.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="58745-106">Avant d’effectuer les tâches décrites dans cette section, les conditions suivantes doivent être en place :</span><span class="sxs-lookup"><span data-stu-id="58745-106">Before you perform the tasks in this section, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="58745-107">Le serveur Lync doit être configuré sur le site central.</span><span class="sxs-lookup"><span data-stu-id="58745-107">Lync Server must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="58745-108">Un technicien d’installation sur le site de succursale doit être ajouté au groupe RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="58745-108">An installation technician at the branch site must be added to the RTCUniversalSBATechnicians group.</span></span></P></LI></UL><span data-ttu-id="58745-109">Par ailleurs, il est recommandé d’effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="58745-109">In addition, we recommend that you do the following:</span></span>
> <UL>
> <LI>
> <P><span data-ttu-id="58745-110">Déploiement d’un serveur DHCP sur chaque site de succursale pour permettre aux clients d’obtenir des adresses IP.</span><span class="sxs-lookup"><span data-stu-id="58745-110">Deploy a DHCP server at each branch site to enable clients to obtain IP addresses.</span></span></P>
> <LI>
> <P><span data-ttu-id="58745-111">À la place du déploiement d’un serveur DHCP sur chaque site de succursale, activez le protocole DHCP de Lync Server sur l’appareil de succursales survivant ou sur le serveur de succursales survivant en utilisant l’applet de cmdlet Lync Server Management Shell <STRONG>Set-CsRegistrarConfiguration – EnableDHCPServer $true</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="58745-111">As an alternative to deploying a DHCP server at each branch site, enable Lync Server DHCP on the Survivable Branch Appliance or Survivable Branch Server by using the Lync Server Management Shell cmdlet <STRONG>Set-CsRegistrarConfiguration –EnableDHCPServer $true</STRONG>.</span></span> <span data-ttu-id="58745-112">Pour plus d’informations, reportez-vous à la section « Configuration matérielle et logicielle requise » dans la rubrique Configuration de la <A href="lync-server-2013-branch-site-resiliency-requirements.md">résilience de site pour Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="58745-112">For details, see the “Hardware and Software Requirements” section of <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="58745-113">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="58745-113">In This Section</span></span>

  - [<span data-ttu-id="58745-114">Ajout d’un Survivable Branch Appliance à Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58745-114">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [<span data-ttu-id="58745-115">Ajout des sites de succursale à votre topologie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58745-115">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="58745-116">Définition d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58745-116">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


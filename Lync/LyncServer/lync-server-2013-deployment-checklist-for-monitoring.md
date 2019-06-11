---
title: 'Lync Server 2013 : Liste de vérification du déploiement pour la surveillance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for monitoring
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204874(v=OCS.15)
ms:contentKeyID: 48184080
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cbf14920ef0103f2d6e8aa6088a2c0b35e17654
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="02430-102">Liste de vérification du déploiement pour la surveillance dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02430-102">Deployment checklist for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02430-103">_**Dernière modification de la rubrique:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="02430-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="02430-104">Même si la surveillance est déjà installée et activée sur chaque serveur frontal, il existe toujours plusieurs étapes que vous devez effectuer avant de pouvoir recueillir des données d’analyse pour Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="02430-104">Although monitoring is already installed and activated on each Front End server, there are still several steps that you must undertake before you can actually being to collect monitoring data for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="02430-105">Ces étapes sont décrites dans la liste de vérification suivante :</span><span class="sxs-lookup"><span data-stu-id="02430-105">These steps are outlined in the following checklist:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02430-106">Phase</span><span class="sxs-lookup"><span data-stu-id="02430-106">Phase</span></span></p></td>
<td><p><span data-ttu-id="02430-107">Étapes</span><span class="sxs-lookup"><span data-stu-id="02430-107">Steps</span></span></p></td>
<td><p><span data-ttu-id="02430-108">Rôles et appartenance aux groupes</span><span class="sxs-lookup"><span data-stu-id="02430-108">Role and group membership</span></span></p></td>
<td><p><span data-ttu-id="02430-109">Documentation</span><span class="sxs-lookup"><span data-stu-id="02430-109">Documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02430-110"><strong>Installer le matériel et les logiciels prérequis</strong></span><span class="sxs-lookup"><span data-stu-id="02430-110"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="02430-111">Installez une version prise en charge de Microsoft SQL Server sur l’ordinateur qui fera office de magasin de données principal pour la surveillance.</span><span class="sxs-lookup"><span data-stu-id="02430-111">Install a supported version of Microsoft SQL Server on the computer that will act as the backend data store for monitoring.</span></span></p></td>
<td><p><span data-ttu-id="02430-112">Utilisateur de domaine qui est également membre du groupe Administrateurs local.</span><span class="sxs-lookup"><span data-stu-id="02430-112">Domain user who is also a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="02430-113"><a href="lync-server-2013-supported-hardware.md">Matériel compatible pour Lync Server 2013</a> dans le Guide de prise en charge</span><span class="sxs-lookup"><span data-stu-id="02430-113"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability guide</span></span></p>
<p><span data-ttu-id="02430-114"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Prise en charge de Software and Infrastructure Server dans Lync Server 2013</a> dans le Guide de prise en charge</span><span class="sxs-lookup"><span data-stu-id="02430-114"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability Guide</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02430-115"><strong>Créer la topologie interne appropriée pour prendre en charge la surveillance</strong></span><span class="sxs-lookup"><span data-stu-id="02430-115"><strong>Create the appropriate internal topology to support monitoring</strong></span></span></p></td>
<td><p><span data-ttu-id="02430-116">Utilisez le générateur de topologie Lync Server 2013 pour ajouter des bases de données de surveillance à la topologie, puis publiez la topologie mise à jour.</span><span class="sxs-lookup"><span data-stu-id="02430-116">Use Lync Server 2013 Topology Builder to add monitoring databases to the topology, then published the updated topology.</span></span></p></td>
<td><p><span data-ttu-id="02430-117">Pour définir une topologie, utilisateur membre du groupe Utilisateurs local.</span><span class="sxs-lookup"><span data-stu-id="02430-117">To define a topology, a user who is a member of the local users group.</span></span></p>
<p><span data-ttu-id="02430-118">Pour publier la topologie, utilisateur membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="02430-118">To publish the topology, a user who is a member if the domain administrators group and the RTCUniversalServerAdmins group.</span></span></p></td>
<td><p><span data-ttu-id="02430-119"><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Association d’un magasin d’analyse à un pool frontal dans Lync Server 2013</a> dans le Guide de déploiement</span><span class="sxs-lookup"><span data-stu-id="02430-119"><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Associating a monitoring store with a Front End pool in Lync Server 2013</a> in the Deployment guide</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02430-120"><strong>Activer les paramètres de surveillance appropriés</strong></span><span class="sxs-lookup"><span data-stu-id="02430-120"><strong>Enable the appropriate monitoring settings</strong></span></span></p></td>
<td><p><span data-ttu-id="02430-121">Activez l’enregistrement des détails des appels (CDR) et/ou la qualité de l’expertise (QoE) au niveau du global et/ou des étendues de site.</span><span class="sxs-lookup"><span data-stu-id="02430-121">Enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global and/or the site scopes.</span></span></p></td>
<td><p><span data-ttu-id="02430-122">Utilisateur membre du groupe RTCUniversalServerAdmins ou disposant d’un rôle RBAC qui permet d’accéder aux applets de commande CsCdrConfiguration et CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="02430-122">A user who is a member of the RTCUniversalServerAdmins group or who has been assigned an RBAC role that provides access to the CsCdrConfiguration and CsQoEConfiguration cmdlets.</span></span></p></td>
<td><p><span data-ttu-id="02430-123"><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configuration des paramètres d’enregistrement des détails des appels et de la qualité de l’utilisation dans Lync Server 2013</a> dans le guide des opérations</span><span class="sxs-lookup"><span data-stu-id="02430-123"><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</a> in the Operations guide</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


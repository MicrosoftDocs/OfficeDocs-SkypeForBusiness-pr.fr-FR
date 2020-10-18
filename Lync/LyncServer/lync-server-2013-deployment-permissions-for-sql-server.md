---
title: 'Lync Server 2013 : autorisations de déploiement pour SQL Server'
description: 'Lync Server 2013 : autorisations de déploiement pour SQL Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be5985bc8f3173b03d8969d3dd58cfbf8daf85f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575720"
---
# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="af04b-103">Autorisations de déploiement pour SQL Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af04b-103">Deployment permissions for SQL Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af04b-104">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="af04b-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="af04b-105">Microsoft SQL Server 2012 a des exigences spécifiques lors de l’installation et du déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="af04b-105">Microsoft SQL Server 2012 has specific requirements when installing and deploying Lync Server 2013.</span></span> <span data-ttu-id="af04b-106">Étant donné que Windows et SQL Server définissent leur sécurité différemment, la connexion en tant qu’administrateur dans le domaine Active Directory n’accorde pas implicitement des autorisations pour SQL Server.</span><span class="sxs-lookup"><span data-stu-id="af04b-106">Because Windows and SQL Server define their security differently, logging in as an administrator in the Active Directory domain does not implicitly grant permissions for SQL Server.</span></span> <span data-ttu-id="af04b-107">Vous devez être membre de l’entité sysadmin sur le serveur SQL Server que vous configurez.</span><span class="sxs-lookup"><span data-stu-id="af04b-107">You must also be a member of the sysadmin entity on the SQL Server-based server you are configuring.</span></span>

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a><span data-ttu-id="af04b-108">Autorisations requises pour l’installation de la base de données et de Lync Server</span><span class="sxs-lookup"><span data-stu-id="af04b-108">Permissions Required for Database and Lync Server Installation</span></span>

<span data-ttu-id="af04b-109">Les options suivantes détaillent trois autorisations et des associations d’appartenance aux groupes pour l’installation des fichiers Lync Server 2013 et des bases de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="af04b-109">The following options detail three permissions and group membership associations for installation of Lync Server 2013 files and SQL Server databases.</span></span> <span data-ttu-id="af04b-110">Choisissez le scénario qui répond le mieux aux exigences de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="af04b-110">Choose the scenario that best meets the requirements of your organization.</span></span>

### <a name="permissions-and-group-membership-associations"></a><span data-ttu-id="af04b-111">Associations des autorisations et de l’appartenance à un groupe</span><span class="sxs-lookup"><span data-stu-id="af04b-111">Permissions and Group Membership Associations</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="af04b-112">Rôle SQL Server ou Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af04b-112">SQL Server or Lync Server 2013 role</span></span></th>
<th><span data-ttu-id="af04b-113">Autorisations SQL Server et appartenance à un groupe en fonction du rôle</span><span class="sxs-lookup"><span data-stu-id="af04b-113">Role-Typical SQL Server permissions and group membership</span></span></th>
<th><span data-ttu-id="af04b-114">Rôle : autorisations Lync Server 2013 classiques et appartenance aux groupes</span><span class="sxs-lookup"><span data-stu-id="af04b-114">Role-typical Lync Server 2013 permissions and group membership</span></span></th>
<th><span data-ttu-id="af04b-115">Possibilités associées aux autorisations</span><span class="sxs-lookup"><span data-stu-id="af04b-115">Permissions outcome</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af04b-116">Administrateur Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af04b-116">Lync Server 2013 administrator</span></span></p></td>
<td><p><span data-ttu-id="af04b-117">Doit être membre du groupe de sécurité sysadmins SQL Server et membre du groupe Administrateurs local SQL Server</span><span class="sxs-lookup"><span data-stu-id="af04b-117">Must be granted membership of sysadmins SQL Server security group and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="af04b-118">Doit être membre du groupe RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="af04b-118">Must be a member of the RTCUniversalServerAdmins group</span></span></p></td>
<td><p><span data-ttu-id="af04b-119">L’administrateur Lync Server 2013 dispose des autorisations appropriées pour installer les bases de données Lync Server 2013 et SQL Server.</span><span class="sxs-lookup"><span data-stu-id="af04b-119">Lync Server 2013 administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af04b-120">Administrateur SQL Server</span><span class="sxs-lookup"><span data-stu-id="af04b-120">SQL Server administrator</span></span></p></td>
<td><p><span data-ttu-id="af04b-121">Membre du groupe sysadmins SQL Server (ou équivalent) et membre du groupe Administrateurs local SQL Server</span><span class="sxs-lookup"><span data-stu-id="af04b-121">SQL Server sysadmin group member (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="af04b-122">Doit être membre du groupe RTCUniversalServerReadOnly</span><span class="sxs-lookup"><span data-stu-id="af04b-122">Must be a member of the RTCUniversalServerReadOnly group</span></span></p></td>
<td><p><span data-ttu-id="af04b-123">L’administrateur SQL Server dispose des autorisations appropriées pour installer les bases de données Lync Server 2013 et SQL Server.</span><span class="sxs-lookup"><span data-stu-id="af04b-123">SQL Server administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af04b-124">Les deux administrateurs partageant les tâches d’installation</span><span class="sxs-lookup"><span data-stu-id="af04b-124">Both administrators sharing installation duties</span></span></p></td>
<td><p><span data-ttu-id="af04b-125">L’administrateur SQL Server est membre du groupe sysadmins (ou équivalent) et membre du groupe Administrateurs local SQL Server</span><span class="sxs-lookup"><span data-stu-id="af04b-125">SQL Server administrator is member of sysadmins group (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="af04b-126">L’administrateur Lync Server 2013 est membre de RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="af04b-126">Lync Server 2013 administrator is member of RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="af04b-127">L’administrateur Lync Server 2013 peut installer Lync Server 2013, mais ne peut pas installer les bases de données.</span><span class="sxs-lookup"><span data-stu-id="af04b-127">The Lync Server 2013 administrator can install Lync Server 2013, but cannot install the databases.</span></span> <span data-ttu-id="af04b-128">L’administrateur SQL Server utilise les applets de commande Lync Server Management Shell et Windows PowerShell fournies par l’administrateur Lync Server 2013 pour installer les bases de données.</span><span class="sxs-lookup"><span data-stu-id="af04b-128">The SQL Server administrator uses the Lync Server Management Shell and Windows PowerShell cmdlets provided by the Lync Server 2013 administrator to install the databases.</span></span> <span data-ttu-id="af04b-129">Lync Server 2013 Management Shell utilisé par l’administrateur SQL Server est installé sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="af04b-129">The Lync Server 2013 Management Shell used by the SQL Server administrator is installed on the Front End Server.</span></span> <span data-ttu-id="af04b-130">Ainsi, il n’est pas nécessaire d’installer les outils d’administration Lync Server 2013 sur le serveur basé sur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="af04b-130">This eliminates the need to install the Lync Server 2013 administrative tools on the SQL Server-based server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


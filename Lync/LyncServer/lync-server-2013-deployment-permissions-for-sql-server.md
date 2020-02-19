---
title: 'Lync Server 2013 : autorisations de déploiement pour SQL Server'
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
ms.openlocfilehash: 2a6697fdb4910b16592ace53e08dcc754cdb2446
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="a08b3-102">Autorisations de déploiement pour SQL Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a08b3-102">Deployment permissions for SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a08b3-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a08b3-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a08b3-104">Microsoft SQL Server 2012 a des exigences spécifiques lors de l’installation et du déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a08b3-104">Microsoft SQL Server 2012 has specific requirements when installing and deploying Lync Server 2013.</span></span> <span data-ttu-id="a08b3-105">Étant donné que Windows et SQL Server définissent leur sécurité différemment, la connexion en tant qu’administrateur dans le domaine Active Directory n’accorde pas implicitement des autorisations pour SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a08b3-105">Because Windows and SQL Server define their security differently, logging in as an administrator in the Active Directory domain does not implicitly grant permissions for SQL Server.</span></span> <span data-ttu-id="a08b3-106">Vous devez être membre de l’entité sysadmin sur le serveur SQL Server que vous configurez.</span><span class="sxs-lookup"><span data-stu-id="a08b3-106">You must also be a member of the sysadmin entity on the SQL Server-based server you are configuring.</span></span>

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a><span data-ttu-id="a08b3-107">Autorisations requises pour l’installation de la base de données et de Lync Server</span><span class="sxs-lookup"><span data-stu-id="a08b3-107">Permissions Required for Database and Lync Server Installation</span></span>

<span data-ttu-id="a08b3-108">Les options suivantes détaillent trois autorisations et des associations d’appartenance aux groupes pour l’installation des fichiers Lync Server 2013 et des bases de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a08b3-108">The following options detail three permissions and group membership associations for installation of Lync Server 2013 files and SQL Server databases.</span></span> <span data-ttu-id="a08b3-109">Choisissez le scénario qui répond le mieux aux exigences de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a08b3-109">Choose the scenario that best meets the requirements of your organization.</span></span>

### <a name="permissions-and-group-membership-associations"></a><span data-ttu-id="a08b3-110">Associations des autorisations et de l’appartenance à un groupe</span><span class="sxs-lookup"><span data-stu-id="a08b3-110">Permissions and Group Membership Associations</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a08b3-111">Rôle SQL Server ou Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a08b3-111">SQL Server or Lync Server 2013 role</span></span></th>
<th><span data-ttu-id="a08b3-112">Autorisations SQL Server et appartenance à un groupe en fonction du rôle</span><span class="sxs-lookup"><span data-stu-id="a08b3-112">Role-Typical SQL Server permissions and group membership</span></span></th>
<th><span data-ttu-id="a08b3-113">Rôle : autorisations Lync Server 2013 classiques et appartenance aux groupes</span><span class="sxs-lookup"><span data-stu-id="a08b3-113">Role-typical Lync Server 2013 permissions and group membership</span></span></th>
<th><span data-ttu-id="a08b3-114">Possibilités associées aux autorisations</span><span class="sxs-lookup"><span data-stu-id="a08b3-114">Permissions outcome</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a08b3-115">Administrateur Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a08b3-115">Lync Server 2013 administrator</span></span></p></td>
<td><p><span data-ttu-id="a08b3-116">Doit être membre du groupe de sécurité sysadmins SQL Server et membre du groupe Administrateurs local SQL Server</span><span class="sxs-lookup"><span data-stu-id="a08b3-116">Must be granted membership of sysadmins SQL Server security group and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="a08b3-117">Doit être membre du groupe RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a08b3-117">Must be a member of the RTCUniversalServerAdmins group</span></span></p></td>
<td><p><span data-ttu-id="a08b3-118">L’administrateur Lync Server 2013 dispose des autorisations appropriées pour installer les bases de données Lync Server 2013 et SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a08b3-118">Lync Server 2013 administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a08b3-119">Administrateur SQL Server</span><span class="sxs-lookup"><span data-stu-id="a08b3-119">SQL Server administrator</span></span></p></td>
<td><p><span data-ttu-id="a08b3-120">Membre du groupe sysadmins SQL Server (ou équivalent) et membre du groupe Administrateurs local SQL Server</span><span class="sxs-lookup"><span data-stu-id="a08b3-120">SQL Server sysadmin group member (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="a08b3-121">Doit être membre du groupe RTCUniversalServerReadOnly</span><span class="sxs-lookup"><span data-stu-id="a08b3-121">Must be a member of the RTCUniversalServerReadOnly group</span></span></p></td>
<td><p><span data-ttu-id="a08b3-122">L’administrateur SQL Server dispose des autorisations appropriées pour installer les bases de données Lync Server 2013 et SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a08b3-122">SQL Server administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a08b3-123">Les deux administrateurs partageant les tâches d’installation</span><span class="sxs-lookup"><span data-stu-id="a08b3-123">Both administrators sharing installation duties</span></span></p></td>
<td><p><span data-ttu-id="a08b3-124">L’administrateur SQL Server est membre du groupe sysadmins (ou équivalent) et membre du groupe Administrateurs local SQL Server</span><span class="sxs-lookup"><span data-stu-id="a08b3-124">SQL Server administrator is member of sysadmins group (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="a08b3-125">L’administrateur Lync Server 2013 est membre de RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a08b3-125">Lync Server 2013 administrator is member of RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="a08b3-126">L’administrateur Lync Server 2013 peut installer Lync Server 2013, mais ne peut pas installer les bases de données.</span><span class="sxs-lookup"><span data-stu-id="a08b3-126">The Lync Server 2013 administrator can install Lync Server 2013, but cannot install the databases.</span></span> <span data-ttu-id="a08b3-127">L’administrateur SQL Server utilise les applets de commande Lync Server Management Shell et Windows PowerShell fournies par l’administrateur Lync Server 2013 pour installer les bases de données.</span><span class="sxs-lookup"><span data-stu-id="a08b3-127">The SQL Server administrator uses the Lync Server Management Shell and Windows PowerShell cmdlets provided by the Lync Server 2013 administrator to install the databases.</span></span> <span data-ttu-id="a08b3-128">Lync Server 2013 Management Shell utilisé par l’administrateur SQL Server est installé sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="a08b3-128">The Lync Server 2013 Management Shell used by the SQL Server administrator is installed on the Front End Server.</span></span> <span data-ttu-id="a08b3-129">Ainsi, il n’est pas nécessaire d’installer les outils d’administration Lync Server 2013 sur le serveur basé sur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a08b3-129">This eliminates the need to install the Lync Server 2013 administrative tools on the SQL Server-based server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


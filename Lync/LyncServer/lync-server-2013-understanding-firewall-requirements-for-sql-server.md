---
title: 'Lync Server 2013 : présentation des exigences en matière de pare-feu pour SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57f32d84e4cd08c40f95a47af7c988599678c972
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a><span data-ttu-id="9b0ee-102">Présentation des exigences en matière de pare-feu pour SQL Server avec Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b0ee-102">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b0ee-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="9b0ee-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="9b0ee-104">Pour un déploiement Standard Edition, les exceptions de pare-feu sont créées automatiquement lors de l’installation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b0ee-104">For a Standard Edition deployment, firewall exceptions are created automatically during Lync Server 2013 Setup.</span></span> <span data-ttu-id="9b0ee-105">Toutefois, pour les déploiements Enterprise Edition, vous devez configurer manuellement les exceptions de pare-feu sur le serveur principal SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9b0ee-105">However, for Enterprise Edition deployments, you must configure the firewall exceptions manually on the SQL Server Back End Server.</span></span> <span data-ttu-id="9b0ee-106">Le protocole TCP/IP autorise l’utilisation unique d’un port donné pour une adresse IP donnée.</span><span class="sxs-lookup"><span data-stu-id="9b0ee-106">The TCP/IP protocol allows for a given port to be used once for a given IP address.</span></span> <span data-ttu-id="9b0ee-107">Cela signifie que dans le cas d’un serveur SQL Server, vous pouvez affecter le port TCP 1433 à l’instance de base de données par défaut.</span><span class="sxs-lookup"><span data-stu-id="9b0ee-107">This means that for the SQL Server-based server you can assign the default database instance the default TCP port 1433.</span></span> <span data-ttu-id="9b0ee-108">Pour toutes les autres instances, vous devez utiliser le Gestionnaire de configuration SQL Server pour affecter les ports uniques et inutilisés.</span><span class="sxs-lookup"><span data-stu-id="9b0ee-108">For any other instances you will need to use the SQL Server Configuration Manager to assign unique and unused ports.</span></span> <span data-ttu-id="9b0ee-109">Cette rubrique traite des sujets suivants :</span><span class="sxs-lookup"><span data-stu-id="9b0ee-109">This topic covers:</span></span>

  - <span data-ttu-id="9b0ee-110">Configuration requise pour une exception de pare-feu dans le cadre de l’utilisation de l’instance par défaut</span><span class="sxs-lookup"><span data-stu-id="9b0ee-110">Requirements for a firewall exception when using the default instance</span></span>

  - <span data-ttu-id="9b0ee-111">Configuration requise pour une exception de pare-feu pour le service SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="9b0ee-111">Requirements for a firewall exception for the SQL Server Browser service</span></span>

  - <span data-ttu-id="9b0ee-112">Configuration requise pour les ports d’écoute statiques lors de l’utilisation d’instances nommées</span><span class="sxs-lookup"><span data-stu-id="9b0ee-112">Requirements for static listening ports when using named instances</span></span>

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a><span data-ttu-id="9b0ee-113">Configuration requise pour une exception de pare-feu dans le cadre de l’utilisation de l’instance par défaut</span><span class="sxs-lookup"><span data-stu-id="9b0ee-113">Requirements for a Firewall Exception When Using the Default Instance</span></span>

<span data-ttu-id="9b0ee-114">Si vous utilisez l’instance par défaut de SQL Server pour une base de données lors du déploiement de Lync Server 2013, les conditions requises suivantes pour la règle de pare-feu sont utilisées pour garantir la communication entre le pool frontal et l’instance par défaut de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9b0ee-114">If you are using the SQL Server default instance for any database when deploying Lync Server 2013, the following firewall rule requirements are used to help ensure communication from the Front End pool to the SQL Server default instance.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b0ee-115">Protocole</span><span class="sxs-lookup"><span data-stu-id="9b0ee-115">Protocol</span></span></th>
<th><span data-ttu-id="9b0ee-116">Port</span><span class="sxs-lookup"><span data-stu-id="9b0ee-116">Port</span></span></th>
<th><span data-ttu-id="9b0ee-117">Direction</span><span class="sxs-lookup"><span data-stu-id="9b0ee-117">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b0ee-118">TCP</span><span class="sxs-lookup"><span data-stu-id="9b0ee-118">TCP</span></span></p></td>
<td><p><span data-ttu-id="9b0ee-119">1433</span><span class="sxs-lookup"><span data-stu-id="9b0ee-119">1433</span></span></p></td>
<td><p><span data-ttu-id="9b0ee-120">Entrant vers SQL Server</span><span class="sxs-lookup"><span data-stu-id="9b0ee-120">Inbound to SQL Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a><span data-ttu-id="9b0ee-121">Configuration requise pour une exception de pare-feu pour le service SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="9b0ee-121">Requirements for a Firewall Exception for the SQL Server Browser Service</span></span>

<span data-ttu-id="9b0ee-122">Le service SQL Server Browser localise les instances de base de données et indique le port que l’instance (nommée ou par défaut) doit utiliser.</span><span class="sxs-lookup"><span data-stu-id="9b0ee-122">The SQL Server Browser service will locate database instances and communicate the port that the instance (named or default) is configured to use.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b0ee-123">Protocole</span><span class="sxs-lookup"><span data-stu-id="9b0ee-123">Protocol</span></span></th>
<th><span data-ttu-id="9b0ee-124">Port</span><span class="sxs-lookup"><span data-stu-id="9b0ee-124">Port</span></span></th>
<th><span data-ttu-id="9b0ee-125">Direction</span><span class="sxs-lookup"><span data-stu-id="9b0ee-125">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b0ee-126">DATAGRAMME</span><span class="sxs-lookup"><span data-stu-id="9b0ee-126">UDP</span></span></p></td>
<td><p><span data-ttu-id="9b0ee-127">1434</span><span class="sxs-lookup"><span data-stu-id="9b0ee-127">1434</span></span></p></td>
<td><p><span data-ttu-id="9b0ee-128">Entrant</span><span class="sxs-lookup"><span data-stu-id="9b0ee-128">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a><span data-ttu-id="9b0ee-129">Configuration requise pour les ports d’écoute statiques lors de l’utilisation d’instances nommées</span><span class="sxs-lookup"><span data-stu-id="9b0ee-129">Requirements for Static Listening Ports When Using Named Instances</span></span>

<span data-ttu-id="9b0ee-130">Lors de l’utilisation d’instances nommées dans la configuration SQL Server pour les bases de données prenant en charge Lync Server 2013, vous configurez des ports statiques à l’aide du gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9b0ee-130">When using named instances in the SQL Server configuration for databases supporting Lync Server 2013, you configure static ports by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="9b0ee-131">Une fois les ports statiques affectés à chaque instance nommée, vous devez créer des exceptions pour chaque port statique du pare-feu.</span><span class="sxs-lookup"><span data-stu-id="9b0ee-131">After the static ports have been assigned to each named instance, you create exceptions for each static port in the firewall.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b0ee-132">Protocole</span><span class="sxs-lookup"><span data-stu-id="9b0ee-132">Protocol</span></span></th>
<th><span data-ttu-id="9b0ee-133">Port</span><span class="sxs-lookup"><span data-stu-id="9b0ee-133">Port</span></span></th>
<th><span data-ttu-id="9b0ee-134">Direction</span><span class="sxs-lookup"><span data-stu-id="9b0ee-134">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b0ee-135">TCP</span><span class="sxs-lookup"><span data-stu-id="9b0ee-135">TCP</span></span></p></td>
<td><p><span data-ttu-id="9b0ee-136">Défini statiquement</span><span class="sxs-lookup"><span data-stu-id="9b0ee-136">Statically defined</span></span></p></td>
<td><p><span data-ttu-id="9b0ee-137">Entrant</span><span class="sxs-lookup"><span data-stu-id="9b0ee-137">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a><span data-ttu-id="9b0ee-138">Documentation SQL Server</span><span class="sxs-lookup"><span data-stu-id="9b0ee-138">SQL Server Documentation</span></span>

<span data-ttu-id="9b0ee-139">La documentation Microsoft SQL Server 2012 fournit des instructions détaillées sur la configuration de l’accès au pare-feu pour les bases de données.</span><span class="sxs-lookup"><span data-stu-id="9b0ee-139">Microsoft SQL Server 2012 documentation provides detailed guidance on how to configure firewall access for databases.</span></span> <span data-ttu-id="9b0ee-140">Pour plus d’informations sur Microsoft SQL Server 2012, reportez-vous à la section « Configuration du pare [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031)-feu Windows pour autoriser l’accès à SQL Server » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="9b0ee-140">For details about Microsoft SQL Server 2012, see “Configuring the Windows Firewall to Allow SQL Server Access” at [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013 : Configuration système requise pour SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System requirements for SQL Server
ms:assetid: 9c235085-cbfa-4e9e-9cec-3f5749039a6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205112(v=OCS.15)
ms:contentKeyID: 48184904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d8e8bb923fd10d505eb9e1b02b0b0ee31612d40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846704"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-requirements-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="bc218-102">Configuration système requise pour SQL Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc218-102">System requirements for SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc218-103">_**Dernière modification de la rubrique:** 2013-10-25_</span><span class="sxs-lookup"><span data-stu-id="bc218-103">_**Topic Last Modified:** 2013-10-25_</span></span>

<span data-ttu-id="bc218-104">Avant de déployer Enterprise Edition Server, installez Microsoft SQL Server 2008 R2 ou Microsoft SQL Server 2012 sur un ordinateur dédié qui répond à la configuration matérielle requise.</span><span class="sxs-lookup"><span data-stu-id="bc218-104">Before you deploy Enterprise Edition server, install Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 on a dedicated computer that meets the hardware requirements.</span></span> <span data-ttu-id="bc218-105">Pour plus d’informations sur la configuration matérielle requise, voir [plates-formes matérielles pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation relative à la prise en charge.</span><span class="sxs-lookup"><span data-stu-id="bc218-105">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="bc218-106">Pour plus d’informations sur la configuration logicielle requise, voir [prise en charge de logiciels de base de données dans Lync Server 2013](lync-server-2013-database-software-support.md) dans la documentation relative à la prise en charge.</span><span class="sxs-lookup"><span data-stu-id="bc218-106">For details about software requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="bc218-107">Pour plus d’informations sur les autorisations nécessaires pour le déploiement, voir [autorisations de déploiement pour SQL Server dans Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bc218-107">For information about the permissions necessary for deployment, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<span data-ttu-id="bc218-108">Avant de créer le pool frontal, vous devez également configurer le pare-feu Windows pour autoriser l’accès de Lync Server 2013 à SQL Server via des ports spécifiques en définissant des ports pour le serveur à l’aide du gestionnaire de configuration SQL Server et en ouvrant des ports dans le pare-feu Windows avec Sécurité avancée.</span><span class="sxs-lookup"><span data-stu-id="bc218-108">Before you create the Front End pool, you must also configure Windows Firewall to allow Lync Server 2013 access to SQL Server over specific ports by defining ports for the server using SQL Server Configuration Manager and opening ports in Windows Firewall with Advanced Security.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


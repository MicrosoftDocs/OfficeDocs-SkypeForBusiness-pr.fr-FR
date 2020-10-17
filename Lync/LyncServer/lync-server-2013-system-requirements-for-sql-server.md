---
title: 'Lync Server 2013 : configuration système requise pour SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System requirements for SQL Server
ms:assetid: 9c235085-cbfa-4e9e-9cec-3f5749039a6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205112(v=OCS.15)
ms:contentKeyID: 48184904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b9aa4a51ed7e75b413b0712297d02f5e8050fa2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497371"
---
# <a name="system-requirements-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="4a377-102">Configuration système requise pour SQL Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a377-102">System requirements for SQL Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a377-103">_**Dernière modification de la rubrique :** 2013-10-25_</span><span class="sxs-lookup"><span data-stu-id="4a377-103">_**Topic Last Modified:** 2013-10-25_</span></span>

<span data-ttu-id="4a377-104">Avant de déployer Enterprise Edition Server, installez Microsoft SQL Server 2008 R2 ou Microsoft SQL Server 2012 sur un ordinateur dédié qui répond à la configuration matérielle requise.</span><span class="sxs-lookup"><span data-stu-id="4a377-104">Before you deploy Enterprise Edition server, install Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 on a dedicated computer that meets the hardware requirements.</span></span> <span data-ttu-id="4a377-105">Pour plus d’informations sur la configuration matérielle requise, voir [Server Hardware Platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="4a377-105">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="4a377-106">Pour plus d’informations sur la configuration logicielle requise, voir [Database Software support in Lync Server 2013](lync-server-2013-database-software-support.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="4a377-106">For details about software requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="4a377-107">Pour plus d’informations sur les autorisations nécessaires au déploiement, reportez-vous à la rubrique [autorisations de déploiement pour SQL Server dans Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4a377-107">For information about the permissions necessary for deployment, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<span data-ttu-id="4a377-108">Avant de créer le pool frontal, vous devez également configurer le pare-feu Windows pour autoriser l’accès de Lync Server 2013 à SQL Server sur des ports spécifiques en définissant des ports pour le serveur à l’aide du gestionnaire de configuration SQL Server et en ouvrant les ports dans le pare-feu Windows avec fonctions avancées de sécurité.</span><span class="sxs-lookup"><span data-stu-id="4a377-108">Before you create the Front End pool, you must also configure Windows Firewall to allow Lync Server 2013 access to SQL Server over specific ports by defining ports for the server using SQL Server Configuration Manager and opening ports in Windows Firewall with Advanced Security.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013 : Windows Update pour Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Windows Update for Lync Server 2013
ms:assetid: fe26ab32-b1a9-421d-9227-506703d4b834
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518337(v=OCS.15)
ms:contentKeyID: 62625495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8df575ac6c42bd62db57ed4e6595ced0af32014a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-update-for-lync-server-2013"></a><span data-ttu-id="e0b26-102">Windows Update pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0b26-102">Windows Update for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0b26-103">_**Dernière modification de la rubrique:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="e0b26-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="e0b26-104">Recherchez et appliquez fréquemment des mises à jour et des mises à jour de sécurité à l’aide de Windows Update Services.</span><span class="sxs-lookup"><span data-stu-id="e0b26-104">Frequently check for and apply updates and security updates using Windows Update Services.</span></span> <span data-ttu-id="e0b26-105">Cette opération permet d’éviter des vulnérabilités dans d’autres composants système susceptibles de permettre aux agresseurs d’accéder aux serveurs exécutant Microsoft Lync Server 2013 avec des droits d’administrateur et de par conséquent de compromettre Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0b26-105">Doing so helps prevents vulnerabilities in other system components that might lead to attackers being able to gain access to servers running Microsoft Lync Server 2013 with administrator rights and thereby compromise Lync Server 2013.</span></span>

<span data-ttu-id="e0b26-106">Les mises à jour de Microsoft SQL Server 2008 Express (64-bit Edition) s’exécutent sur chaque serveur Lync Server 2013 Standard Edition Server (pour la base de données principale) et sur tous les autres rôles de serveur Lync Server 2013 (pour le magasin de configuration local), sauf si vous avez effectué une mise à niveau bases de données vers SQL Server 2008 R2 Express.</span><span class="sxs-lookup"><span data-stu-id="e0b26-106">Updates for Microsoft SQL Server 2008 Express (64-bit edition) runs on each Lync Server 2013 Standard Edition server (for the back-end database) and on all other Lync Server 2013 server roles (for the Local Configuration Store), unless you have upgraded these databases to SQL Server 2008 R2 Express.</span></span> <span data-ttu-id="e0b26-107">Nous vous conseillons de prendre en compte ces bases de données dans le cadre de la mise à jour des mises à jour de sécurité routinière, comme le doit SQL Server sur la base de données principale d’un pool frontal, la base de données de surveillance et la base de données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="e0b26-107">You should consider these databases as part of routine security update maintenance, as should SQL Server on the back-end database of a Front End pool, the Monitoring database, and the Archiving database.</span></span>

<div>

## <a name="best-practice"></a><span data-ttu-id="e0b26-108">Meilleure pratique</span><span class="sxs-lookup"><span data-stu-id="e0b26-108">Best Practice</span></span>

  - <span data-ttu-id="e0b26-109">Restez au courant avec Windows Update.</span><span class="sxs-lookup"><span data-stu-id="e0b26-109">Keep current with Windows Update.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


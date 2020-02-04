---
title: Configuration de Lync Server pour utiliser System Center Operations Manager
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0cf422ddab501acf521c26c36d8f373bd42dbf9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a><span data-ttu-id="6a5b3-102">Configuration de Lync Server 2013 pour fonctionner avec System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="6a5b3-102">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a5b3-103">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="6a5b3-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="6a5b3-104">Pour configurer votre infrastructure Microsoft Lync Server 2013 de manière à utiliser System Center Operations Manager, vous devez effectuer les trois opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6a5b3-104">In order to configure your Microsoft Lync Server 2013 infrastructure to work with System Center Operations Manager you must do three things:</span></span>

  - <span data-ttu-id="6a5b3-105">Identifiez et configurez votre serveur de gestion Operations Manager principal.</span><span class="sxs-lookup"><span data-stu-id="6a5b3-105">Identify and configure your primary System Center Operations Manager management server.</span></span> <span data-ttu-id="6a5b3-106">La configuration du serveur de gestion inclut l’installation de System Center Operations Manager 2012 ou System Center Operations Manager 2007 R2, ainsi que la configuration d’une base de données principale à l’aide de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6a5b3-106">Configuring the management server includes installing System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, as well as setting up a back-end database using SQL Server.</span></span> <span data-ttu-id="6a5b3-107">La version réelle de SQL Server que vous devez utiliser dépend de la version de System Center Operations Manager que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="6a5b3-107">The actual version of SQL Server that you need to be use depends on the version of System Center Operations Manager you are using.</span></span> <span data-ttu-id="6a5b3-108">Pour plus d’informations, reportez-vous à [configuration du serveur de gestion principal dans Lync server 2013](lync-server-2013-configuring-the-primary-management-server.md).</span><span class="sxs-lookup"><span data-stu-id="6a5b3-108">For details, see [Configuring the primary management server in Lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md).</span></span>

  - <span data-ttu-id="6a5b3-109">Identifiez et configurez les ordinateurs serveur Lync que vous souhaitez surveiller.</span><span class="sxs-lookup"><span data-stu-id="6a5b3-109">Identify and configure the Lync Server computers that you want to monitor.</span></span> <span data-ttu-id="6a5b3-110">Pour surveiller un ordinateur Lync Server à l’aide de System Center Operations Manager, vous devez installer les fichiers de l’agent System Center Operations Manager et configurer chaque serveur pour qu’il serve de proxy.</span><span class="sxs-lookup"><span data-stu-id="6a5b3-110">To monitor a Lync Server computer by using System Center Operations Manager you must install the System Center Operations Manager agent files, and configure each server to act as a proxy.</span></span>

  - <span data-ttu-id="6a5b3-111">Identifiez et configurez les ordinateurs que vous voulez utiliser en tant que *nœuds d’observateur*Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6a5b3-111">Identify and configure the computers that you want to act as Lync Server *watcher nodes*.</span></span> <span data-ttu-id="6a5b3-112">Les nœuds d’observation sont des ordinateurs qui exécutent périodiquement les transactions synthétiques de Lync Server, qui sont des cmdlets Windows PowerShell qui vérifient que les composants clés de Lync Server, tels que la possibilité de se connecter au système ou la possibilité d’échanger des messages instantanés, sont travail attendu.</span><span class="sxs-lookup"><span data-stu-id="6a5b3-112">Watcher nodes are computers that periodically run Lync Server synthetic transactions, which are Windows PowerShell cmdlets that verify that key Lync Server components, such as the ability to log on to the system or the ability to exchange instant messages are working as expected.</span></span>

<span data-ttu-id="6a5b3-113">Les rubriques de cette section contiennent des instructions pour exécuter chacune de ces tâches.</span><span class="sxs-lookup"><span data-stu-id="6a5b3-113">The topics in this section contain instructions for carrying out each of these tasks.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6a5b3-114">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="6a5b3-114">In This Section</span></span>

  - [<span data-ttu-id="6a5b3-115">Configuration du serveur de gestion principal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a5b3-115">Configuring the primary management server in Lync Server 2013</span></span>](lync-server-2013-configuring-the-primary-management-server.md)

  - [<span data-ttu-id="6a5b3-116">Installation des packs d’administration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a5b3-116">Installing the Lync Server 2013 management packs</span></span>](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [<span data-ttu-id="6a5b3-117">Configuration des ordinateurs serveur Lync qui seront surveillés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a5b3-117">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [<span data-ttu-id="6a5b3-118">Installation et configuration des nœuds d’observation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a5b3-118">Installing and configuring watcher nodes in Lync Server 2013</span></span>](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


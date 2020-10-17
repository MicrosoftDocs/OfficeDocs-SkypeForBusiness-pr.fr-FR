---
title: Empêcher l’exécution de sessions de services
description: Bloquer les sessions pour les services.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a452f8091716daa0a15967e2a278e82c5bc8c4f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563690"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="2c63f-103">Empêcher l’exécution de sessions de services</span><span class="sxs-lookup"><span data-stu-id="2c63f-103">Prevent sessions for services</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c63f-104">_**Dernière modification de la rubrique :** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="2c63f-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="2c63f-105">Vous pouvez utiliser le panneau de configuration Microsoft Lync Server 2010 pour empêcher de nouvelles sessions pour tous les services Lync Server 2010 exécutés sur un ordinateur spécifique ou pour empêcher de nouvelles sessions pour un service Lync Server 2010 spécifique.</span><span class="sxs-lookup"><span data-stu-id="2c63f-105">You can use Microsoft Lync Server 2010 Control Panel to prevent new sessions for all the Lync Server 2010 services running on a specific computer or to prevent new sessions for a specific Lync Server 2010 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="2c63f-106">Pour empêcher l’exécution de nouvelles sessions de tous les services Lync Server sur un ordinateur</span><span class="sxs-lookup"><span data-stu-id="2c63f-106">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="2c63f-107">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2c63f-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="2c63f-108">Ouvrez le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2c63f-108">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="2c63f-109">Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.</span><span class="sxs-lookup"><span data-stu-id="2c63f-109">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="2c63f-110">Dans la page **État**, recherchez dans la liste l’ordinateur qui exécute les services pour lesquels vous souhaitez empêcher toute nouvelle session, puis cliquez sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="2c63f-110">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="2c63f-111">Cliquez sur **Action**.</span><span class="sxs-lookup"><span data-stu-id="2c63f-111">Click **Action**.</span></span>

6.  <span data-ttu-id="2c63f-112">Cliquez sur **Empêcher de nouvelles sessions pour tous les services**.</span><span class="sxs-lookup"><span data-stu-id="2c63f-112">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="2c63f-113">Pour empêcher l’exécution de nouvelles sessions d’un service spécifique</span><span class="sxs-lookup"><span data-stu-id="2c63f-113">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="2c63f-114">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2c63f-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="2c63f-115">Ouvrez le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2c63f-115">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="2c63f-116">Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.</span><span class="sxs-lookup"><span data-stu-id="2c63f-116">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="2c63f-117">Dans la page **État**, recherchez dans la liste l’ordinateur qui exécute le service que vous souhaitez démarrer ou arrêter, ou triez cette liste, puis cliquez sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="2c63f-117">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="2c63f-118">Cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="2c63f-118">Click **Properties**.</span></span>

6.  <span data-ttu-id="2c63f-119">Triez la liste de services, si nécessaire, et cliquez sur le service pour lequel vous souhaitez empêcher toute nouvelle session.</span><span class="sxs-lookup"><span data-stu-id="2c63f-119">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="2c63f-120">Cliquez sur **Action**.</span><span class="sxs-lookup"><span data-stu-id="2c63f-120">Click **Action**.</span></span>

8.  <span data-ttu-id="2c63f-121">Cliquez sur **Empêcher de nouvelles sessions pour le service**.</span><span class="sxs-lookup"><span data-stu-id="2c63f-121">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="2c63f-122">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="2c63f-122">Click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


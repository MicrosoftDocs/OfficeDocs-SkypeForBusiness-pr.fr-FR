---
title: Empêcher l’exécution de sessions de services
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19f3ed7c788db120782966541bfea9813328d90c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services"></a><span data-ttu-id="fb711-102">Empêcher l’exécution de sessions de services</span><span class="sxs-lookup"><span data-stu-id="fb711-102">Prevent sessions for services</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb711-103">_**Dernière modification de la rubrique:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="fb711-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="fb711-104">Vous pouvez utiliser le panneau de configuration Microsoft Lync Server 2010 pour empêcher les nouvelles sessions de tous les services Lync Server 2010 en cours d’exécution sur un ordinateur spécifique ou pour empêcher de nouvelles sessions pour un service Lync Server 2010 spécifique.</span><span class="sxs-lookup"><span data-stu-id="fb711-104">You can use Microsoft Lync Server 2010 Control Panel to prevent new sessions for all the Lync Server 2010 services running on a specific computer or to prevent new sessions for a specific Lync Server 2010 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="fb711-105">Pour empêcher de nouvelles sessions pour tous les services Lync Server sur un ordinateur</span><span class="sxs-lookup"><span data-stu-id="fb711-105">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="fb711-106">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fb711-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="fb711-107">Ouvrez le Paneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb711-107">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="fb711-108">Dans la barre de navigation de gauche, cliquez sur **Topology** , puis sur Status ( **statut**).</span><span class="sxs-lookup"><span data-stu-id="fb711-108">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="fb711-109">Dans la page **État** , triez ou effectuez une recherche dans la liste selon vos besoins pour trouver l’ordinateur exécutant les services pour lesquels vous voulez éviter de nouvelles sessions, puis cliquez dessus.</span><span class="sxs-lookup"><span data-stu-id="fb711-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="fb711-110">Cliquez sur **action**.</span><span class="sxs-lookup"><span data-stu-id="fb711-110">Click **Action**.</span></span>

6.  <span data-ttu-id="fb711-111">Cliquez sur **empêcher de nouvelles sessions pour tous les services**.</span><span class="sxs-lookup"><span data-stu-id="fb711-111">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="fb711-112">Pour empêcher de nouvelles sessions pour un service spécifique</span><span class="sxs-lookup"><span data-stu-id="fb711-112">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="fb711-113">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fb711-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="fb711-114">Ouvrez le Paneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb711-114">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="fb711-115">Dans la barre de navigation de gauche, cliquez sur **Topology** , puis sur Status ( **statut**).</span><span class="sxs-lookup"><span data-stu-id="fb711-115">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="fb711-116">Dans la page **État** , triez ou effectuez une recherche dans la liste selon vos besoins pour trouver l’ordinateur exécutant le service que vous voulez démarrer ou arrêter, puis cliquez dessus.</span><span class="sxs-lookup"><span data-stu-id="fb711-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="fb711-117">Cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="fb711-117">Click **Properties**.</span></span>

6.  <span data-ttu-id="fb711-118">Triez la liste des services, si nécessaire, puis cliquez sur le service pour lequel vous souhaitez éviter de nouvelles sessions.</span><span class="sxs-lookup"><span data-stu-id="fb711-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="fb711-119">Cliquez sur **action**.</span><span class="sxs-lookup"><span data-stu-id="fb711-119">Click **Action**.</span></span>

8.  <span data-ttu-id="fb711-120">Cliquez sur **empêcher de nouvelles sessions pour le service**.</span><span class="sxs-lookup"><span data-stu-id="fb711-120">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="fb711-121">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="fb711-121">Click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


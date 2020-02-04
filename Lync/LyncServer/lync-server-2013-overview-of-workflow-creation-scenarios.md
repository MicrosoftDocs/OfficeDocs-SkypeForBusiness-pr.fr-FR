---
title: 'Lync Server 2013 : Vue d’ensemble des scénarios de création de flux de travail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of workflow creation scenarios
ms:assetid: 05e0c175-0f1a-4bb1-b048-c68584d00649
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204646(v=OCS.15)
ms:contentKeyID: 48183309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08ecb210ea937184039587d289c5c9c57cb4fa4d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-workflow-creation-scenarios-in-lync-server-2013"></a><span data-ttu-id="ebc10-102">Vue d’ensemble des scénarios de création de flux de travail dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ebc10-102">Overview of workflow creation scenarios in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebc10-103">_**Dernière modification de la rubrique :** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="ebc10-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="ebc10-104">Lorsque vous créez des flux de travail, deux scénarios sont possibles :</span><span class="sxs-lookup"><span data-stu-id="ebc10-104">When you create workflows, there are two possible scenarios:</span></span>

  - <span data-ttu-id="ebc10-105">**L’Administrateur crée et configure le flux de travail** : le membre du rôle CsResponseGroupAdministrator (ou équivalent) crée et active le flux de travail, ainsi que tous les éléments qu’il contient, comme les groupes d’agents, les files d’attente, les congés et les heures ouvrées, la musique d’attente, etc.</span><span class="sxs-lookup"><span data-stu-id="ebc10-105">**The Administrator creates and configures the workflow** — The CsResponseGroupAdministrator role member (or equivalent) creates and activates the workflow and all elements in the workflow, such as the agent groups, queues, holiday and business hours, music on hold, and so on.</span></span>

  - <span data-ttu-id="ebc10-p101">**L’administrateur crée le flux de travail et le responsable configure les options** : le membre du rôle CsResponseGroupAdministrator (ou équivalent) définit l’URI SIP (Session Initiation Protocol) principal et le nom complet, affecte des membres du rôle CsResponseGroupManager, sélectionne une file d’attente et active le flux de travail. Le membre du rôle CsResponseGroupManager peut ensuite ouvrir une session et modifier la configuration du flux de travail en créant des groupes d’agents. Il affecte également le groupe à la file d’attente, configure le numéro de téléphone, les congés et les heures ouvrées, la musique d’attente, etc.</span><span class="sxs-lookup"><span data-stu-id="ebc10-p101">**The Administrator creates the workflow and the Manager configures options** — The CsResponseGroupAdministrator role member (or equivalent) defines the primary SIP URI, Display Name, assigns a member or members of the CsResponseGroupManager role, and selects a queue and activates the workflow. The CsResponseGroupManager can then log on and edit the configuration of the workflow by creating agent groups and also assigns the group to the queue, configuring the telephone number, holiday and business hours, music on hold, and so on.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ebc10-p102">Lorsque vous voulez créer un flux de travail géré, vous devez créer le flux travail en tant que flux de travail actif. Une fois que vous avez enregistré un flux de travail géré et actif, vous pouvez le modifier et le désactiver.</span><span class="sxs-lookup"><span data-stu-id="ebc10-p102">When you want to create a managed workflow, you need to create the workflow as active. After you save an active, managed workflow, you can then modify and deactivate the workflow.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>


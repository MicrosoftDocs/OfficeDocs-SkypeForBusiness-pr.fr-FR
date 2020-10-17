---
title: Configuration d’un nœud observateur pour participer à la découverte de System Center
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49b34e623b885bb7e85afc258c1d533c2a8feb46
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527001"
---
# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a><span data-ttu-id="0fd1e-102">Configuration d’un nœud observateur dans Lync Server 2013 pour la participation à la découverte de System Center</span><span class="sxs-lookup"><span data-stu-id="0fd1e-102">Configuring a watcher node in Lync Server 2013 to participate in System Center discovery</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0fd1e-103">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="0fd1e-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="0fd1e-104">Pour vous assurer que votre nœud observateur participe au processus de découverte de System Center Operations Manager, vous devez effectuer la procédure suivante sur un ordinateur sur lequel la console System Center Operations Manager a été installée :</span><span class="sxs-lookup"><span data-stu-id="0fd1e-104">To make sure that your watcher node participates in the discovery process for System Center Operations Manager, you must complete the following procedure on a computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="0fd1e-105">Sous l’onglet **Administration**, cliquez sur **Géré par agent**.</span><span class="sxs-lookup"><span data-stu-id="0fd1e-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="0fd1e-p101">Cliquez avec le bouton droit sur le nom de l’ordinateur du nœud observateur, puis cliquez sur **Propriétés**. Dans la boîte de dialogue **Propriétés**, sous l’onglet **Sécurité**, sélectionnez **Autoriser cet agent à agir en tant que proxy et découvrir des objets gérés sur d’autres ordinateurs**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0fd1e-p101">Right-click the name of the watcher node computer, and then click **Properties**. In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="0fd1e-108">Après avoir configuré le nœud observateur pour qu’il se comporte comme un proxy, démarrez l’ordinateur du nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="0fd1e-108">After configuring the watcher node to act as a proxy, reboot the watcher node computer.</span></span> <span data-ttu-id="0fd1e-109">Une fois l’ordinateur redémarré, vérifiez qu’aucun événement d’erreur n’est enregistré dans le journal des événements Operations Manager sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="0fd1e-109">After the computer has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span> <span data-ttu-id="0fd1e-110">Une fois que l’ordinateur est en cours d’exécution pendant 15 minutes, utilisez la console Operations Manager pour vérifier que vos ordinateurs Lync Server sont répertoriés sous la catégorie **Lync** .</span><span class="sxs-lookup"><span data-stu-id="0fd1e-110">After the computer has been running for 15 minutes or so, use the Operations Manager console to verify that your Lync Server computers are listed under the **Lync** category.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


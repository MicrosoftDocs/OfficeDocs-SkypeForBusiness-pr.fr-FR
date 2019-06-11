---
title: Configuration d’un nœud FileSystemWatcher pour participer à la découverte de System Center
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66be6bd0336471626f2ca4e41a89c3a45b073f05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a><span data-ttu-id="8736c-102">Configuration d’un nœud FileSystemWatcher dans Lync Server 2013 pour participer à la découverte de System Center</span><span class="sxs-lookup"><span data-stu-id="8736c-102">Configuring a watcher node in Lync Server 2013 to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8736c-103">_**Dernière modification de la rubrique:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="8736c-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="8736c-104">Pour vous assurer que votre nœud FileSystemWatcher participe au processus de découverte de System Center Operations Manager, vous devez effectuer la procédure suivante sur un ordinateur sur lequel la console System Center Operations Manager a été installée:</span><span class="sxs-lookup"><span data-stu-id="8736c-104">To make sure that your watcher node participates in the discovery process for System Center Operations Manager, you must complete the following procedure on a computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="8736c-105">Dans l’onglet **administration** , cliquez sur **géré par l’agent**.</span><span class="sxs-lookup"><span data-stu-id="8736c-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="8736c-106">Cliquez avec le bouton droit sur le nom de l’ordinateur du nœud d’observation, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="8736c-106">Right-click the name of the watcher node computer, and then click **Properties**.</span></span> <span data-ttu-id="8736c-107">Dans la boîte de dialogue **Propriétés** , sous l’onglet **sécurité** , sélectionnez **Autoriser cet agent à agir en tant que proxy et détecter les objets gérés sur d’autres ordinateurs**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8736c-107">In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="8736c-108">Après avoir configuré le nœud FileSystemWatcher pour qu’il serve de proxy, redémarrez l’ordinateur de nœud d’observation.</span><span class="sxs-lookup"><span data-stu-id="8736c-108">After configuring the watcher node to act as a proxy, reboot the watcher node computer.</span></span> <span data-ttu-id="8736c-109">Après le redémarrage de l’ordinateur, vérifiez qu’aucun événement d’erreur n’est enregistré dans le journal des événements Operations Manager sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="8736c-109">After the computer has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span> <span data-ttu-id="8736c-110">Une fois que l’ordinateur est en cours d’exécution pendant 15 minutes, utilisez la console Operations Manager pour vérifier que votre ordinateur serveur Lync figure dans la catégorie **Lync** .</span><span class="sxs-lookup"><span data-stu-id="8736c-110">After the computer has been running for 15 minutes or so, use the Operations Manager console to verify that your Lync Server computers are listed under the **Lync** category.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Configuration de l’ordinateur serveur Lync pour participer à la découverte de System Center
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the Lync Server computer to participate in System Center discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48183731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4b50fad3e0d197259847db9a94bf9e64618d7e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="a7217-102">Configuration de l’ordinateur Lync Server 2013 pour participer à la découverte de System Center</span><span class="sxs-lookup"><span data-stu-id="a7217-102">Configuring the Lync Server 2013 computer to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7217-103">_**Dernière modification de la rubrique:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="a7217-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="a7217-104">Pour vous assurer que votre nouvel agent Lync Server est impliqué dans le processus de découverte pour System Center Operations Manager, vous devez effectuer la procédure suivante sur chaque ordinateur sur lequel la console System Center Operations Manager a été installée:</span><span class="sxs-lookup"><span data-stu-id="a7217-104">To make sure that your new Lync Server agent participates in discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="a7217-105">Dans l’onglet **administration** , cliquez sur **géré par l’agent**.</span><span class="sxs-lookup"><span data-stu-id="a7217-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="a7217-106">Cliquez avec le bouton droit sur le nom de l’ordinateur, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a7217-106">Right-click the name of the computer, and then click **Properties**.</span></span> <span data-ttu-id="a7217-107">Dans la boîte de dialogue **Propriétés** , sous l’onglet **sécurité** , sélectionnez **Autoriser cet agent à agir en tant que proxy et détecter les objets gérés sur d’autres ordinateurs**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7217-107">In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="a7217-108">À l’issue de l’étape 2, redémarrez le service agent d’intégrité.</span><span class="sxs-lookup"><span data-stu-id="a7217-108">After completing step 2, reboot the Health Agent service.</span></span> <span data-ttu-id="a7217-109">(Le réinitialisation du service entraînera une découverte du nouvel ordinateur.</span><span class="sxs-lookup"><span data-stu-id="a7217-109">(Rebooting the service will “force” discovery of the new machine.</span></span> <span data-ttu-id="a7217-110">Si vous ne redémarrez pas le service, il peut s’écouler jusqu’à 4 heures avant la découverte du nouvel ordinateur par System Center Operations Manager.).</span><span class="sxs-lookup"><span data-stu-id="a7217-110">If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.).</span></span> <span data-ttu-id="a7217-111">Après le redémarrage du service, vérifiez qu’aucun événement d’erreur n’est enregistré dans le journal des événements Operations Manager sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="a7217-111">After the service has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


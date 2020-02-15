---
title: Configuration de l’ordinateur Lync Server pour la participation à la découverte de System Center
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computer to participate in System Center discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48183731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b59622306fbde12eb570b72c95b37cec7885c7f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="cca25-102">Configuration de l’ordinateur Lync Server 2013 pour la participation à la découverte de System Center</span><span class="sxs-lookup"><span data-stu-id="cca25-102">Configuring the Lync Server 2013 computer to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cca25-103">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="cca25-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="cca25-104">Pour vous assurer que votre nouvel agent Lync Server participe au processus de découverte de System Center Operations Manager, vous devez effectuer la procédure suivante sur chaque ordinateur sur lequel la console System Center Operations Manager a été installée :</span><span class="sxs-lookup"><span data-stu-id="cca25-104">To make sure that your new Lync Server agent participates in discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="cca25-105">Sous l’onglet **Administration**, cliquez sur **Géré par agent**.</span><span class="sxs-lookup"><span data-stu-id="cca25-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="cca25-p101">Cliquez avec le bouton droit sur le nom de l’ordinateur, puis cliquez sur **Propriétés**. Dans la boîte de dialogue **Propriétés**, sous l’onglet **Sécurité**, sélectionnez **Autoriser cet agent à agir en tant que proxy et découvrir des objets gérés sur d’autres ordinateurs**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cca25-p101">Right-click the name of the computer, and then click **Properties**. In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="cca25-p102">Une fois l’étape 2 terminée, redémarrez le service Agent d’intégrité. (Le redémarrage du service va « forcer » la découverte du nouvel ordinateur. Si vous ne redémarrez pas le service, la découverte du nouvel ordinateur par le System Center Operations Manager peut prendre jusqu’à 4 heures.). Une fois le service redémarré, vérifiez qu’aucun événement d’erreur n’a été enregistré dans le journal des événements Operations Manager sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="cca25-p102">After completing step 2, reboot the Health Agent service. (Rebooting the service will “force” discovery of the new machine. If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.). After the service has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


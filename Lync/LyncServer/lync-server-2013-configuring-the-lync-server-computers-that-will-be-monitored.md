---
title: 'Lync Server 2013 : configuration des ordinateurs Lync Server qui seront surveillés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computers that will be monitored
ms:assetid: 9f1b2b91-d5af-42ad-a27d-b0815f762ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205118(v=OCS.15)
ms:contentKeyID: 48184927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0568f13cb977fad78e8d0e704c158039165ea78a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040913"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-computers-that-will-be-monitored-in-lync-server-2013"></a><span data-ttu-id="31e27-102">Configuration des ordinateurs Lync Server qui seront surveillés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31e27-102">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31e27-103">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="31e27-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="31e27-104">Étant donné que Lync Server 2013 n’utilise pas le processus de découverte central utilisé dans Microsoft Lync Server 2010, chaque ordinateur Lync Server 2013 que vous souhaitez surveiller doit être en mesure de signaler lui-même son existence au serveur de gestion.</span><span class="sxs-lookup"><span data-stu-id="31e27-104">Because Lync Server 2013 does not use the central discovery process used in Microsoft Lync Server 2010, each Lync Server 2013 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="31e27-105">Pour ce faire, vous devez installer les fichiers de l’agent Operations Manager sur chacun des ordinateurs à surveiller.</span><span class="sxs-lookup"><span data-stu-id="31e27-105">To make this possible, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="31e27-106">Une fois les fichiers de l’agent installés, vous devez configurer l’ordinateur pour qu’il agisse en tant que proxy System Center.</span><span class="sxs-lookup"><span data-stu-id="31e27-106">After the agent files have been installed, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="31e27-107">Notez que ces procédures doivent être effectuées après l’installation et la configuration de Lync Server sur ces ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="31e27-107">Note that these procedures should be carried out after you have installed and configured Lync Server on these computers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


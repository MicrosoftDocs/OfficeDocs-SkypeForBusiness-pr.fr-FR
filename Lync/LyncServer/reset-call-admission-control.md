---
title: Réinitialisation du contrôle d’admission des appels
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf7067ba3d130c264ead39ed9d2c044a037960f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-call-admission-control"></a><span data-ttu-id="a1021-102">Réinitialisation du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="a1021-102">Reset call admission control</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1021-103">_**Dernière modification de la rubrique:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="a1021-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="a1021-104">Si un pool frontal de Lync Server 2010 est en cours d’hébergement par le biais du contrôle d’admission des appels (CAC), vous devez déplacer l’hébergement CAC vers un pool Lync Server 2013 avant de pouvoir supprimer le pool frontal de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a1021-104">If a Lync Server 2010 Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Lync Server 2013 pool before you can remove the Lync Server 2010 Front End pool.</span></span>

<div>

## <a name="to-reset-cac"></a><span data-ttu-id="a1021-105">Pour réinitialiser le CAC</span><span class="sxs-lookup"><span data-stu-id="a1021-105">To reset CAC</span></span>

1.  <span data-ttu-id="a1021-106">Ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="a1021-106">Open Topology Builder.</span></span>

2.  <span data-ttu-id="a1021-107">Cliquez avec le bouton droit sur le nœud site, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a1021-107">Right-click the site node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="a1021-108">Sous **paramètre de contrôle d’admission des appels**, assurez-vous que l’option **activer le contrôle d’admission des appels** est activée.</span><span class="sxs-lookup"><span data-stu-id="a1021-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span>

4.  <span data-ttu-id="a1021-109">Sous **pool frontal pour exécuter le contrôle d’admission des appels (CAC)**, sélectionnez le pool Lync Server 2013 à hôte CAC, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1021-109">Under **Front End pool to run call admission control (CAC)**, select the Lync Server 2013 pool that is to host CAC, and then click **OK**.</span></span>

5.  <span data-ttu-id="a1021-110">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="a1021-110">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


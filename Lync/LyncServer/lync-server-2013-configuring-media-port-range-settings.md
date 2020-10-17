---
title: 'Lync Server 2013 : configuration des paramètres de plage de ports multimédias'
description: 'Lync Server 2013 : configuration des paramètres de plage de ports multimédias.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a7670284c593197068c366f43bbb3faaaad8f63
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570740"
---
# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a><span data-ttu-id="9df12-103">Configuration des paramètres de plage de ports multimédias dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9df12-103">Configuring media port range settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9df12-104">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="9df12-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="9df12-105">Les paramètres des plages de ports multimédias peuvent affecter considérablement les performances du client et doivent donc être configurés.</span><span class="sxs-lookup"><span data-stu-id="9df12-105">Media port range settings can significantly impact client performance and should be configured.</span></span> <span data-ttu-id="9df12-106">Vous pouvez configurer ces paramètres à l’aide de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9df12-106">You can configure these settings by using Lync Server Management Shell.</span></span>

### <a name="media-port-range-settings"></a><span data-ttu-id="9df12-107">Paramètres de plage de ports multimédias</span><span class="sxs-lookup"><span data-stu-id="9df12-107">Media Port Range Settings</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9df12-108">Setting</span><span class="sxs-lookup"><span data-stu-id="9df12-108">Setting</span></span></th>
<th><span data-ttu-id="9df12-109">Description</span><span class="sxs-lookup"><span data-stu-id="9df12-109">Description</span></span></th>
<th><span data-ttu-id="9df12-110">Cmdlet Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="9df12-110">Lync Server Management Shell cmdlet</span></span></th>
<th><span data-ttu-id="9df12-111">Paramètres de l’applet de commande</span><span class="sxs-lookup"><span data-stu-id="9df12-111">Cmdlet parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9df12-112">Portrange\Enabled</span><span class="sxs-lookup"><span data-stu-id="9df12-112">Portrange\Enabled</span></span></p></td>
<td><p><span data-ttu-id="9df12-p102">Spécifie si les plages de ports envoyées par le serveur doivent être utilisées par le client pour les médias et la signalisation. Utilisée conjointement avec les sous-valeurs MinMediaPort et MaxMediaPort.</span><span class="sxs-lookup"><span data-stu-id="9df12-p102">Specifies whether the port ranges sent by the server should be used by the client for media and signaling. Used in conjunction with the subvalues MinMediaPort and MaxMediaPort.</span></span></p></td>
<td><p><span data-ttu-id="9df12-115"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="9df12-115"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="9df12-116">Paramètres clientmediaportrangeenabled</span><span class="sxs-lookup"><span data-stu-id="9df12-116">ClientMediaPortRangeEnabled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9df12-117">Portrange\MinMediaPort</span><span class="sxs-lookup"><span data-stu-id="9df12-117">Portrange\MinMediaPort</span></span></p></td>
<td><p><span data-ttu-id="9df12-p103">Spécifie le numéro de port de début à utiliser pour le média. Combinée avec MaxMediaPort pour spécifier la plage de ports. La plage minimale recommandée est 40 ports.</span><span class="sxs-lookup"><span data-stu-id="9df12-p103">Specifies the starting port number to use for media. Combines with MaxMediaPort to specify the range of ports. The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="9df12-121"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="9df12-121"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="9df12-122">ClientMediaPort (représente le numéro de port de début à utiliser pour le média client)</span><span class="sxs-lookup"><span data-stu-id="9df12-122">ClientMediaPort (represents the starting port number to use for client media)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9df12-123">Portrange\MaxMediaPort</span><span class="sxs-lookup"><span data-stu-id="9df12-123">Portrange\MaxMediaPort</span></span></p></td>
<td><p><span data-ttu-id="9df12-p104">Spécifie le numéro de port le plus élevé à utiliser pour le média. Combinée avec MinMediaPort pour spécifier la plage de ports. La plage minimale recommandée est 40 ports.</span><span class="sxs-lookup"><span data-stu-id="9df12-p104">Specifies the highest port number to use for media. Combines with MinMediaPort to specify the range of ports. The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="9df12-127"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="9df12-127"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="9df12-128">ClientMediaPortRange (indique le nombre total de ports disponibles pour le trafic multimédia client. La valeur par défaut est 40)</span><span class="sxs-lookup"><span data-stu-id="9df12-128">ClientMediaPortRange (indicates the total number of ports available for client media; default is 40)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a><span data-ttu-id="9df12-129">Pour configurer les paramètres de la plage de ports multimédias</span><span class="sxs-lookup"><span data-stu-id="9df12-129">To Configure Media Port Range Settings</span></span>

1.  <span data-ttu-id="9df12-130">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9df12-130">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9df12-131">Exécutez la cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="9df12-131">Run the following cmdlet:</span></span>
    
        Get-CsConferencingConfiguration
    
    <span data-ttu-id="9df12-132">Cette applet de commande renvoie les paramètres de configuration de conférence.</span><span class="sxs-lookup"><span data-stu-id="9df12-132">This cmdlet returns the conferencing configuration settings.</span></span>

3.  <span data-ttu-id="9df12-133">Exécutez l’applet de commande suivante avec les paramètres et les valeurs que vous souhaitez modifier (pour plus d’informations sur les paramètres de cette cmdlet, voir la documentation de Lync Server Management Shell) :</span><span class="sxs-lookup"><span data-stu-id="9df12-133">Run the following cmdlet with the parameters and values you want to change (for details about the parameters for this cmdlet, see the Lync Server Management Shell documentation):</span></span>
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9df12-134">Vous pouvez créer des ensembles de paramètres de configuration de conférence supplémentaires pour des sites spécifiques.</span><span class="sxs-lookup"><span data-stu-id="9df12-134">You can create additional sets of conferencing configuration settings for specific sites.</span></span> <span data-ttu-id="9df12-135">Utilisez l’applet de commande <STRONG>New- CsConferencingConfiguration</STRONG> avec une identité de site.</span><span class="sxs-lookup"><span data-stu-id="9df12-135">Use the <STRONG>New- CsConferencingConfiguration</STRONG> cmdlet with a site identity.</span></span> <span data-ttu-id="9df12-136">Lorsque vous créez de nouveaux paramètres de configuration de conférence pour des sites, ces paramètres prévalent sur les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="9df12-136">When you create new conferencing configuration settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="9df12-137">Pour plus d’informations, voir la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9df12-137">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


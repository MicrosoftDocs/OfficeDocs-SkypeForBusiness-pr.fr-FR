---
title: 'Lync Server 2013 : configuration des paramètres de plage de ports multimédias'
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
ms.openlocfilehash: 80e835bfcf12495c75612ecee93d87cf3c421651
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a><span data-ttu-id="c0279-102">Configuration des paramètres de plage de ports multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0279-102">Configuring media port range settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0279-103">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="c0279-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="c0279-104">Les paramètres de la plage de ports multimédias peuvent avoir un impact considérable sur les performances du client.</span><span class="sxs-lookup"><span data-stu-id="c0279-104">Media port range settings can significantly impact client performance and should be configured.</span></span> <span data-ttu-id="c0279-105">Vous pouvez configurer ces paramètres à l’aide de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c0279-105">You can configure these settings by using Lync Server Management Shell.</span></span>

### <a name="media-port-range-settings"></a><span data-ttu-id="c0279-106">Paramètres de la plage de ports multimédia</span><span class="sxs-lookup"><span data-stu-id="c0279-106">Media Port Range Settings</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0279-107">Paramètre</span><span class="sxs-lookup"><span data-stu-id="c0279-107">Setting</span></span></th>
<th><span data-ttu-id="c0279-108">Description</span><span class="sxs-lookup"><span data-stu-id="c0279-108">Description</span></span></th>
<th><span data-ttu-id="c0279-109">Cmdlet Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="c0279-109">Lync Server Management Shell cmdlet</span></span></th>
<th><span data-ttu-id="c0279-110">Paramètres de cmdlet</span><span class="sxs-lookup"><span data-stu-id="c0279-110">Cmdlet parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0279-111">Portrange\Enabled</span><span class="sxs-lookup"><span data-stu-id="c0279-111">Portrange\Enabled</span></span></p></td>
<td><p><span data-ttu-id="c0279-112">Indique si les plages de ports envoyées par le serveur doivent être utilisées par le client pour le média et le signalement.</span><span class="sxs-lookup"><span data-stu-id="c0279-112">Specifies whether the port ranges sent by the server should be used by the client for media and signaling.</span></span> <span data-ttu-id="c0279-113">Utilisé conjointement avec les sous-valeurs MinMediaPort et MaxMediaPort.</span><span class="sxs-lookup"><span data-stu-id="c0279-113">Used in conjunction with the subvalues MinMediaPort and MaxMediaPort.</span></span></p></td>
<td><p><span data-ttu-id="c0279-114"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="c0279-114"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="c0279-115">ClientMediaPortRangeEnabled</span><span class="sxs-lookup"><span data-stu-id="c0279-115">ClientMediaPortRangeEnabled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0279-116">Portrange\MinMediaPort</span><span class="sxs-lookup"><span data-stu-id="c0279-116">Portrange\MinMediaPort</span></span></p></td>
<td><p><span data-ttu-id="c0279-117">Spécifie le numéro de port de départ à utiliser pour le média.</span><span class="sxs-lookup"><span data-stu-id="c0279-117">Specifies the starting port number to use for media.</span></span> <span data-ttu-id="c0279-118">S’associe à MaxMediaPort pour spécifier la plage de ports.</span><span class="sxs-lookup"><span data-stu-id="c0279-118">Combines with MaxMediaPort to specify the range of ports.</span></span> <span data-ttu-id="c0279-119">La plage minimale recommandée est 40 ports.</span><span class="sxs-lookup"><span data-stu-id="c0279-119">The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="c0279-120"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="c0279-120"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="c0279-121">ClientMediaPort (représente le numéro du port de départ à utiliser pour le média client)</span><span class="sxs-lookup"><span data-stu-id="c0279-121">ClientMediaPort (represents the starting port number to use for client media)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0279-122">Portrange\MaxMediaPort</span><span class="sxs-lookup"><span data-stu-id="c0279-122">Portrange\MaxMediaPort</span></span></p></td>
<td><p><span data-ttu-id="c0279-123">Spécifie le numéro de port le plus élevé à utiliser pour le contenu multimédia.</span><span class="sxs-lookup"><span data-stu-id="c0279-123">Specifies the highest port number to use for media.</span></span> <span data-ttu-id="c0279-124">S’associe à MinMediaPort pour spécifier la plage de ports.</span><span class="sxs-lookup"><span data-stu-id="c0279-124">Combines with MinMediaPort to specify the range of ports.</span></span> <span data-ttu-id="c0279-125">La plage minimale recommandée est 40 ports.</span><span class="sxs-lookup"><span data-stu-id="c0279-125">The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="c0279-126"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="c0279-126"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="c0279-127">ClientMediaPortRange (indique le nombre total de ports disponibles pour le support client ; la valeur par défaut est 40)</span><span class="sxs-lookup"><span data-stu-id="c0279-127">ClientMediaPortRange (indicates the total number of ports available for client media; default is 40)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a><span data-ttu-id="c0279-128">Pour configurer les paramètres de la plage de ports multimédia</span><span class="sxs-lookup"><span data-stu-id="c0279-128">To Configure Media Port Range Settings</span></span>

1.  <span data-ttu-id="c0279-129">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c0279-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c0279-130">Exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c0279-130">Run the following cmdlet:</span></span>
    
        Get-CsConferencingConfiguration
    
    <span data-ttu-id="c0279-131">Cette cmdlet renvoie les paramètres de configuration de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="c0279-131">This cmdlet returns the conferencing configuration settings.</span></span>

3.  <span data-ttu-id="c0279-132">Exécutez l’applet de commande suivante avec les paramètres et valeurs que vous souhaitez modifier (pour plus d’informations sur les paramètres de cette applet de commande, voir la documentation Lync Server Management Shell) :</span><span class="sxs-lookup"><span data-stu-id="c0279-132">Run the following cmdlet with the parameters and values you want to change (for details about the parameters for this cmdlet, see the Lync Server Management Shell documentation):</span></span>
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c0279-133">Vous pouvez créer des ensembles de paramètres de configuration de conférences supplémentaires pour des sites spécifiques.</span><span class="sxs-lookup"><span data-stu-id="c0279-133">You can create additional sets of conferencing configuration settings for specific sites.</span></span> <span data-ttu-id="c0279-134">Utilisez l’applet <STRONG>de nouvelle applet de nouveau-CsConferencingConfiguration</STRONG> avec une identité de site.</span><span class="sxs-lookup"><span data-stu-id="c0279-134">Use the <STRONG>New- CsConferencingConfiguration</STRONG> cmdlet with a site identity.</span></span> <span data-ttu-id="c0279-135">Quand vous créez de nouveaux paramètres de configuration de conférence pour les sites, les paramètres du site sont prioritaires sur les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="c0279-135">When you create new conferencing configuration settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="c0279-136">Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c0279-136">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


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
ms.openlocfilehash: e13e491037346d9c3186a8f15aada949c46ac8df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502091"
---
# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a>Configuration des paramètres de plage de ports multimédias dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-18_

Les paramètres des plages de ports multimédias peuvent affecter considérablement les performances du client et doivent donc être configurés. Vous pouvez configurer ces paramètres à l’aide de Lync Server Management Shell.

### <a name="media-port-range-settings"></a>Paramètres de plage de ports multimédias

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Setting</th>
<th>Description</th>
<th>Cmdlet Lync Server Management Shell</th>
<th>Paramètres de l’applet de commande</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Portrange\Enabled</p></td>
<td><p>Spécifie si les plages de ports envoyées par le serveur doivent être utilisées par le client pour les médias et la signalisation. Utilisée conjointement avec les sous-valeurs MinMediaPort et MaxMediaPort.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>Paramètres clientmediaportrangeenabled</p></td>
</tr>
<tr class="even">
<td><p>Portrange\MinMediaPort</p></td>
<td><p>Spécifie le numéro de port de début à utiliser pour le média. Combinée avec MaxMediaPort pour spécifier la plage de ports. La plage minimale recommandée est 40 ports.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPort (représente le numéro de port de début à utiliser pour le média client)</p></td>
</tr>
<tr class="odd">
<td><p>Portrange\MaxMediaPort</p></td>
<td><p>Spécifie le numéro de port le plus élevé à utiliser pour le média. Combinée avec MinMediaPort pour spécifier la plage de ports. La plage minimale recommandée est 40 ports.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRange (indique le nombre total de ports disponibles pour le trafic multimédia client. La valeur par défaut est 40)</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a>Pour configurer les paramètres de la plage de ports multimédias

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Exécutez la cmdlet suivante :
    
        Get-CsConferencingConfiguration
    
    Cette applet de commande renvoie les paramètres de configuration de conférence.

3.  Exécutez l’applet de commande suivante avec les paramètres et les valeurs que vous souhaitez modifier (pour plus d’informations sur les paramètres de cette cmdlet, voir la documentation de Lync Server Management Shell) :
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez créer des ensembles de paramètres de configuration de conférence supplémentaires pour des sites spécifiques. Utilisez l’applet de commande <STRONG>New- CsConferencingConfiguration</STRONG> avec une identité de site. Lorsque vous créez de nouveaux paramètres de configuration de conférence pour des sites, ces paramètres prévalent sur les paramètres globaux. Pour plus d’informations, voir la documentation Lync Server Management Shell.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


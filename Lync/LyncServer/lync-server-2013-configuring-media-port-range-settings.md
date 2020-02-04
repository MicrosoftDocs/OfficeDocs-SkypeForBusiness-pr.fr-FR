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

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a>Configuration des paramètres de plage de ports multimédia dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-18_

Les paramètres de la plage de ports multimédias peuvent avoir un impact considérable sur les performances du client. Vous pouvez configurer ces paramètres à l’aide de Lync Server Management Shell.

### <a name="media-port-range-settings"></a>Paramètres de la plage de ports multimédia

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Paramètre</th>
<th>Description</th>
<th>Cmdlet Lync Server Management Shell</th>
<th>Paramètres de cmdlet</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Portrange\Enabled</p></td>
<td><p>Indique si les plages de ports envoyées par le serveur doivent être utilisées par le client pour le média et le signalement. Utilisé conjointement avec les sous-valeurs MinMediaPort et MaxMediaPort.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRangeEnabled</p></td>
</tr>
<tr class="even">
<td><p>Portrange\MinMediaPort</p></td>
<td><p>Spécifie le numéro de port de départ à utiliser pour le média. S’associe à MaxMediaPort pour spécifier la plage de ports. La plage minimale recommandée est 40 ports.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPort (représente le numéro du port de départ à utiliser pour le média client)</p></td>
</tr>
<tr class="odd">
<td><p>Portrange\MaxMediaPort</p></td>
<td><p>Spécifie le numéro de port le plus élevé à utiliser pour le contenu multimédia. S’associe à MinMediaPort pour spécifier la plage de ports. La plage minimale recommandée est 40 ports.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRange (indique le nombre total de ports disponibles pour le support client ; la valeur par défaut est 40)</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a>Pour configurer les paramètres de la plage de ports multimédia

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande suivante :
    
        Get-CsConferencingConfiguration
    
    Cette cmdlet renvoie les paramètres de configuration de la Conférence.

3.  Exécutez l’applet de commande suivante avec les paramètres et valeurs que vous souhaitez modifier (pour plus d’informations sur les paramètres de cette applet de commande, voir la documentation Lync Server Management Shell) :
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez créer des ensembles de paramètres de configuration de conférences supplémentaires pour des sites spécifiques. Utilisez l’applet <STRONG>de nouvelle applet de nouveau-CsConferencingConfiguration</STRONG> avec une identité de site. Quand vous créez de nouveaux paramètres de configuration de conférence pour les sites, les paramètres du site sont prioritaires sur les paramètres globaux. Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


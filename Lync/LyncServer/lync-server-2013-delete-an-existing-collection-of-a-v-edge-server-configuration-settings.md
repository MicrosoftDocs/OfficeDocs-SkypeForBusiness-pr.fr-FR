---
title: Supprimer une collection existante de paramètres de configuration de serveur Edge A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6af42c338cb7032231ce562ac2227ff4089729ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Supprimer une collection existante de paramètres de configuration de serveur Edge A/V dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Le service Edge A/V offre aux utilisateurs internes (qui sont connectés à votre réseau d’entreprise) un moyen de partager des fichiers audio et vidéo avec des utilisateurs externes (les utilisateurs qui ne sont pas connectés au réseau de votre organisation). Le service Edge A/V est essentiellement géré à l’aide des paramètres de configuration d’un serveur à l’aide d’une/V, le paramétrage qui peut être configuré sur l’étendue du site ou au niveau de l’étendue de service (autrement dit, peut être configuré pour un serveur Edge A/V individuel).

Lorsque vous installez Lync Server, une collection globale des paramètres de configuration de Microsoft Edge a/V est créée pour vous. Cette collection globale ne peut pas être supprimée. Toutefois, vous pouvez utiliser Windows PowerShell et l’applet de passe Remove-CsAVEdgeConfiguration pour «réinitialiser» la collection globale. Cela signifie simplement que toutes les valeurs de propriété de la collection globale seront réinitialisées à leur valeur par défaut. Par exemple, si vous avez défini la propriété MaxTokenLifetime pendant 16 heures, cette propriété sera réinitialisée sur sa valeur par défaut de 8 heures.

Toutefois, les collections de paramètres personnalisés que vous avez créées sur l’étendue du site ou sur l’étendue du service peuvent être supprimées à l’aide de l’applet de passe Remove-CsAVEdgeConfiguration. Si vous supprimez les paramètres du site, les serveurs Edge A/V de ce site seront gérés par les paramètres globaux. Si vous supprimez les paramètres d’étendue des services, ce serveur est alors géré par ses paramètres de site, le cas échéant, ou par les paramètres globaux si aucun paramètre de site n’est disponible.

Pour plus d’informations, reportez-vous à la rubrique d’aide relative à l’applet de passe [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15)) .

<div>

## <a name="to-reset-the-global-collection"></a>Pour réinitialiser la collection globale

  - La commande suivante réinitialise la collection globale des paramètres de configuration de Edge A/V:
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a>Pour supprimer une collection de l’étendue du site

  - Cette commande supprime les paramètres de configuration d’une application A/V appliqués au site de Redmond:
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a>Pour supprimer une collection de l’étendue du service

  - Cette commande supprime les paramètres appliqués au serveur Edge A/V atl-edge-001.litwareinc.com:
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Renvoyer des informations de configuration de serveur Edge A/V dans Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Créer ou modifier un ensemble de paramètres de configuration de serveur Edge A/V dans Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[Serveurs périphériques audio/vidéo (A/V) dans Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


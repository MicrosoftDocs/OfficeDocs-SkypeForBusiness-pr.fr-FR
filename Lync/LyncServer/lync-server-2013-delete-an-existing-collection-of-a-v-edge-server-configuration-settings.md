---
title: Supprimer une collection existante de paramètres de configuration de serveur Edge A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7043b2ce5fd35e36615b7b92d1561d725a86cc92
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Supprimer une collection existante de paramètres de configuration de serveur Edge A/V dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Le service Edge A/V permet à vos utilisateurs internes (les utilisateurs connectés au réseau de votre organisation) de partager des fichiers audio et vidéo avec des utilisateurs externes (des utilisateurs qui ne sont pas connectés au réseau de votre organisation). La gestion du service Edge A/V s’effectue à l’aide des paramètres de configuration de ce service. Les paramètres peuvent être configurés au niveau du site ou du service (c’est-à-dire pour un serveur Edge A/V).

Lorsque vous installez Lync Server, une collection globale de paramètres de configuration Edge A/V est créée pour vous. Cette collection globale ne peut pas être supprimée. Toutefois, vous pouvez utiliser Windows PowerShell et l’applet de commande Remove-CsAVEdgeConfiguration pour « réinitialiser » la collection globale ; Cela signifie simplement que toutes les valeurs de propriété de la collection globale seront réinitialisées à leur valeur par défaut. Par exemple, si vous avez affecté à la propriété MaxTokenLifetime un nombre d’heures égal à 16, la valeur par défaut (à savoir 8 heures) de cette propriété est rétablie.

Toutefois, vous pouvez supprimer les collections de paramètres personnalisées que vous avez créées au niveau de l’étendue du site ou du service à l’aide de l’applet de commande Remove-CsAVEdgeConfiguration. Si vous supprimez les paramètres au niveau du site, les serveurs Edge A/V dans ce site sont alors gérés par les paramètres globaux. Si vous supprimez les paramètres au niveau du service, ce serveur est alors géré par ses paramètres de site (le cas échéant) ou par les paramètres globaux si aucun paramètre de site n’est disponible.

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) .

<div>

## <a name="to-reset-the-global-collection"></a>Pour réinitialiser la collection globale

  - La commande suivante réinitialise la collection globale des paramètres de configuration Edge A/V :
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a>Pour supprimer une collection de l’étendue site

  - Cette commande supprime les paramètres de configuration Edge A/V appliqués au site Redmond :
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a>Pour supprimer une collection de l’étendue service

  - Cette commande supprime les paramètres appliqués au serveur Edge A/V atl-edge-001.litwareinc.com :
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Renvoyer les informations de configuration du serveur Edge A/V dans Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Créer ou modifier une collection de paramètres de configuration de serveur Edge A/V dans Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[Serveurs Edge audio/vidéo (A/V) dans Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Création ou modification d’une collection de paramètres de configuration de serveur Edge A/V
description: Créez ou modifiez une collection de paramètres de configuration de serveur Edge A/V.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cdf7dca19446f4eac584564eed776f7fde47bfe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578340"
---
# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Créer ou modifier une collection de paramètres de configuration de serveur Edge A/V dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Le service Edge A/V permet à vos utilisateurs internes (les utilisateurs connectés au réseau de votre organisation) de partager des fichiers audio et vidéo avec des utilisateurs externes (des utilisateurs qui ne sont pas connectés au réseau de votre organisation). La gestion du service Edge A/V s’effectue à l’aide des paramètres de configuration de ce service. Les paramètres peuvent être configurés au niveau du site ou du service (c’est-à-dire pour un serveur Edge A/V).

Lorsque vous installez Lync Server, une collection globale de paramètres de configuration Edge A/V est créée pour vous. En outre, vous pouvez utiliser les applets de commande Windows PowerShell et New-CsAVEdgeConfiguration pour créer des paramètres au niveau de l’étendue site ou de l’étendue service (c’est-à-dire, pour un serveur Edge A/V individuel). Si vous créez des paramètres, gardez à l’esprit les aspects suivants :

  - Les paramètres configurés au niveau du service (c’est-à-dire sur un serveur) prévalent sur tous les autres paramètres.

  - Les paramètres configurés au niveau du site prévalent sur les paramètres configurés au niveau global. Les paramètres au niveau du service, quant à eux, prévalent sur les paramètres au niveau du site.

  - Les paramètres au niveau global seront utilisés uniquement si aucun autre paramètre du service n’est configuré sur le serveur et s’il n’existe aucun paramètre pour le site où ce serveur est situé.

Tous vos paramètres peuvent ensuite être modifiés à l’aide de l’applet de commande Set-CsAVEdgeConfiguration. Pour plus d’informations, reportez-vous aux rubriques d’aide pour les cmdlets [New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) et [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) .

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a>Pour créer des paramètres de configuration de serveur Edge A/V au niveau de l’étendue site

  - La commande suivante crée une collection de paramètres de configuration Edge A/V pour le site Redmond :
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a>Pour créer des paramètres de configuration Edge A/V personnalisés au niveau de l’étendue site

  - Dans la mesure où aucun paramètre supplémentaire n’a été inclus, ces nouveaux paramètres utilisent les valeurs par défaut pour le service Edge A/V. Vous pouvez également ajouter des paramètres et des valeurs de paramètres supplémentaires pour créer une collection personnalisée. Par exemple, cette commande définit la propriété MaxTokenLifetime à 4 heures (04 heures : 00 minute : 00 seconde) :
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a>Pour créer des paramètres de configuration Edge A/V personnalisés au niveau de l’étendue service

  - Cette commande crée une collection similaire appliquée au serveur Edge A/V atl-edge-001.litwareinc.com :
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a>Pour modifier les paramètres de configuration Edge A/V existants

  - Dans cet exemple, l’applet de commande Set-CsAVEdgeConfiguration est utilisée pour changer la durée de vie maximale du jeton du site Redmond en la définissant à 12 heures :
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Renvoyer les informations de configuration du serveur Edge A/V dans Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Supprimer une collection existante de paramètres de configuration de serveur Edge A/V dans Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Serveurs Edge audio/vidéo (A/V) dans Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))  
[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


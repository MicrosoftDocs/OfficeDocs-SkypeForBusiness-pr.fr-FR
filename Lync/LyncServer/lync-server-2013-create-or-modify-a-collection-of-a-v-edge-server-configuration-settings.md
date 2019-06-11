---
title: Créer ou modifier un ensemble de paramètres de configuration de serveur Edge A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a4010c209e1231c47c328d616f686f55fc89008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Créer ou modifier un ensemble de paramètres de configuration de serveur Edge A/V dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Le service Edge A/V offre aux utilisateurs internes (qui sont connectés à votre réseau d’entreprise) un moyen de partager des fichiers audio et vidéo avec des utilisateurs externes (les utilisateurs qui ne sont pas connectés au réseau de votre organisation). Le service Edge A/V est essentiellement géré à l’aide des paramètres de configuration d’un serveur à l’aide d’une/V, le paramétrage qui peut être configuré sur l’étendue du site ou au niveau de l’étendue de service (autrement dit, peut être configuré pour un serveur Edge A/V individuel).

Lorsque vous installez Lync Server, une collection globale des paramètres de configuration de Microsoft Edge a/V est créée pour vous. De plus, vous pouvez utiliser Windows PowerShell et l’applet de nouvelle applet de nouveau-CsAVEdgeConfiguration pour créer des paramètres au niveau de l’étendue du site ou l’étendue du service (autrement dit, pour un serveur Edge A/V individuel). Si vous créez de nouveaux paramètres, n’oubliez pas que:

  - Les paramètres configurés au niveau de l’étendue de service (autrement dit, sur un serveur individuel) sont prioritaires sur tout.

  - Les paramètres configurés lors de l’étendue du site sont prioritaires sur les paramètres configurés au niveau de l’étendue globale. Toutefois, les paramètres d’étendue de service remplacent également les paramètres d’étendue de site.

  - Les paramètres au niveau de l’étendue globale seront utilisés uniquement s’il n’y a aucun paramètre de service configuré sur le serveur individuel et s’il n’y a aucun paramètre de site pour le site sur lequel se trouve le serveur.

Vous pouvez ensuite modifier les paramètres à l’aide de l’applet de applet Set-CsAVEdgeConfiguration. Pour plus d’informations, consultez les rubriques d’aide pour les applets de [nouvelle-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15)) et [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15)) .

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a>Pour créer des paramètres de configuration de niveau A/V sur l’étendue du site

  - La commande suivante crée une nouvelle collection de paramètres de configuration Edge A/V pour le site de Redmond:
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a>Pour créer des paramètres de configuration de bord A/V personnalisés sur l’étendue du site

  - Aucun paramètre supplémentaire n’ayant été inclus, ces nouveaux paramètres utiliseront les valeurs par défaut pour le service Edge A/V. Vous pouvez également ajouter des paramètres et des valeurs de paramètre supplémentaires pour créer une collection personnalisée. Par exemple, cette commande définit la propriété MaxTokenLifetime sur 4 heures (04 heures: 00 minutes: 00 secondes):
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a>Pour créer des paramètres de configuration de bord A/V personnalisés sur l’étendue du service

  - Cette commande crée une collection similaire appliquée au serveur Edge A/V atl-edge-001.litwareinc.com:
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a>Pour modifier les paramètres de configuration de bord A/V existants

  - Dans cet exemple, l’applet de passe Set-CsAVEdgeConfiguration est utilisée pour remplacer la durée de vie du jeton maximale du site de Redmond par 12 heures:
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Renvoyer des informations de configuration de serveur Edge A/V dans Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Supprimer une collection existante de paramètres de configuration de serveur Edge A/V dans Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Serveurs périphériques audio/vidéo (A/V) dans Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Nouveau-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))  
[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


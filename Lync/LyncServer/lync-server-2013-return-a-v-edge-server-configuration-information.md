---
title: 'Lync Server 2013 : renvoi des informations de configuration du serveur Edge A/V'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 920c45abf98678c3e866650e094b9e4a52a418a4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a>Renvoyer les informations de configuration du serveur Edge A/V dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Le service Edge A/V permet à vos utilisateurs internes (les utilisateurs connectés au réseau de votre organisation) de partager des fichiers audio et vidéo avec des utilisateurs externes (des utilisateurs qui ne sont pas connectés au réseau de votre organisation). La gestion du service Edge A/V s’effectue à l’aide des paramètres de configuration de ce service. Les paramètres peuvent être configurés au niveau du site ou du service (c’est-à-dire pour un serveur Edge A/V).

Pour renvoyer des informations sur les paramètres de configuration Edge A/V utilisés dans votre organisation, vous devez utiliser Windows PowerShell et la cmdlet Get-CsAVEdgeConfiguration. Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) .

Les informations retournées par l’applet de commande Get-CsAVEdgeConfiguration ressemblent à ceci :

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a>Pour renvoyer des informations sur tous vos paramètres de configuration de serveur Edge A/V

  - La commande suivante retourne les informations relatives à tous les paramètres de configuration de serveur Edge A/V actuellement utilisés dans votre organisation :
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a>Pour retourner des informations pour les paramètres de configuration Edge A/V d’étendue site

  - Pour retourner les informations relatives à une collection spécifique de paramètres de configuration Edge A/V, spécifiez l’identité de cette collection lors de l’exécution de l’applet de commande Get-CsAVEdgeConfiguration. Par exemple, la commande suivante retourne uniquement les informations relatives aux paramètres appliqués au site Redmond :
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a>Pour renvoyer des informations sur les paramètres de configuration Edge A/V à étendue de service

  - La commande suivante retourne uniquement les informations relatives aux paramètres appliqués à un serveur Edge A/V spécifique :
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Créer ou modifier une collection de paramètres de configuration de serveur Edge A/V dans Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[Supprimer une collection existante de paramètres de configuration de serveur Edge A/V dans Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Serveurs Edge audio/vidéo (A/V) dans Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


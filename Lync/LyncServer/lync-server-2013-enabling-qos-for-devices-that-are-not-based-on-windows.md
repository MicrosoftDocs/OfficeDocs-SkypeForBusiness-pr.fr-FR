---
title: 'Lync Server 2013: activation de la qualité de service (QoS) pour les appareils qui ne sont pas basés sur Windows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d993a6905dfad9f5f2eda10a48553f2ae29b58ef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a>Activation de la qualité de service (QoS) dans Lync Server 2013 pour les appareils qui ne sont pas basés sur Windows

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Lorsque vous installez Microsoft Lync Server 2013, la qualité de service (QoS) n’est pas activée pour les appareils utilisés dans votre organisation qui utilisent un système d’exploitation autre que Windows. Vous pouvez vérifier ceci en exécutant la commande suivante à partir de Lync Server 2013 Management Shell:

    Get-CsMediaConfiguration

Si vous avez apporté des modifications à vos paramètres de configuration de média, vous devez obtenir des informations similaires à ce qui suit:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Si la propriété EnableQoS est définie sur false (comme dans la sortie précédente), cela signifie que la qualité de service n’est pas activée pour les ordinateurs et appareils utilisant un système d’exploitation autre que Windows. La QoS est activée par défaut pour les appareils Lync Phone Edition; Néanmoins, il est possible de désactiver la qualité de service pour Lync Phone Edition.

Pour activer la qualité de service sur l’étendue globale, exécutez la commande suivante à partir de Lync Server Management Shell:

    Set-CsMediaConfiguration -EnableQoS $True

La commande précédente autorise la qualité de service (QoS) au niveau de l’étendue globale. Néanmoins, il est important de noter que les paramètres de configuration de média peuvent également être appliqués à l’étendue du site. Si vous devez activer la qualité de service pour un site, vous devez inclure l’identité des paramètres de configuration lors de l’appel de Set-CsMediaConfiguration. Par exemple, cette commande active QoS pour le site de Redmond:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> Avez-vous besoin d’activer la qualité de service (QoS) sur l’étendue du site? Cela dépend. Les paramètres assignés à l’étendue du site sont prioritaires sur les paramètres attribués à l’étendue globale. Supposez que la qualité de service (QoS) soit activée sur l’étendue globale mais désactivée sur l’étendue du site (pour le site de Redmond). Dans ce cas, la qualité de service sera désactivée pour le site de Redmond; ce n’est pas parce que les paramètres du site sont prioritaires. Pour activer la qualité de service (QoS) pour le site de Redmond, vous devez utiliser les paramètres de configuration de média appliqués au site.



</div>

Si vous souhaitez activer simultanément la qualité de service (QoS) pour tous les paramètres de configuration de média (quelle que soit l’étendue), exécutez cette commande à partir de Lync Server Management Shell:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Vous pouvez désactiver la qualité de service (QoS) pour les appareils qui utilisent un système d’exploitation différent de Windows en définissant la valeur de la propriété EnableQoS sur false. Par exemple :

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Cette fonctionnalité vous permet d’implémenter la qualité de service (QoS) sur certaines parties de votre réseau (par exemple, sur le site de Redmond) tout en laissant la qualité de service désactivée sur d’autres parties de votre réseau.

La qualité de service (QoS) peut uniquement être activée et désactivée à l’aide de Windows PowerShell ces options ne sont pas disponibles dans le panneau de configuration de Lync Server.

</div>

<span> </span>

</div>

</div>

</div>


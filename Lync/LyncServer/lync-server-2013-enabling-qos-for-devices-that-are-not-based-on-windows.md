---
title: 'Lync Server 2013 : activation de la qualité de service pour les appareils qui ne sont pas basés sur Windows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 447c19b96e2189953db81db6ce4f022e4d0f6e6f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a>Activation de la qualité de service dans Lync Server 2013 pour les appareils qui ne sont pas basés sur Windows

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Lorsque vous installez Microsoft Lync Server 2013, la qualité de service (QoS) n’est pas activée pour les appareils utilisés dans votre organisation qui utilisent un système d’exploitation autre que Windows. Vous pouvez vérifier cela en exécutant la commande suivante à partir de Lync Server 2013 Management Shell :

    Get-CsMediaConfiguration

Si vous n’avez apporté aucune modification à vos paramètres de configuration multimédia, vous devriez obtenir des informations de ce type :

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Si la propriété EnableQoS est définie sur false (comme dans la sortie précédente), cela signifie que la qualité de service n’est pas activée pour les ordinateurs et les appareils qui utilisent un système d’exploitation autre que Windows. La qualité de service est activée par défaut pour les appareils Lync Phone Edition ; Toutefois, il est possible de désactiver la qualité de service pour Lync Phone Edition.

Pour activer la qualité de service au niveau global, exécutez la commande suivante à partir de Lync Server Management Shell :

    Set-CsMediaConfiguration -EnableQoS $True

La commande précédente active la QoS au niveau global, mais notez que les paramètres de configuration multimédia peuvent aussi être appliqués au niveau du site. Si vous avez besoin d’activer la qualité de service pour un site, vous devez inclure l’identité des paramètres de configuration lorsque vous appelez l’applet de commande Set-CsMediaConfiguration. Cette commande, par exemple, active la QoS pour le site de Redmond :

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> Est-il nécessaire d’activer la QoS au niveau du site ? Cela dépend. Les paramètres affectés au site sont prioritaires sur ceux affectés à l’étendue globale. Supposons que vous avez activé la QoS au niveau global, mais qu’elle est désactivée au niveau du site (le site de Redmond). Dans ce cas, la qualité de service sera désactivée pour le site de Redmond, car le site est prioritaire. Pour activer la qualité de service sur le site de Redmond, vous devez modifier les paramètres de configuration multimédia appliqués à ce site.



</div>

Si vous souhaitez activer simultanément QoS pour tous vos paramètres de configuration multimédia (quelle que soit l’étendue), exécutez cette commande à partir de Lync Server Management Shell :

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Vous pouvez désactiver la qualité de service pour les appareils qui utilisent un système d’exploitation autre que Windows en définissant la valeur de la propriété EnableQoS sur false. Par exemple :

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Cela vous donne la possibilité d’implémenter la QoS sur des parties de votre réseau (par exemple, sur le site de Redmond), tout en la gardant désactivée sur d’autres.

QoS ne peut être activée et désactivée qu’à l’aide de Windows PowerShell ces options ne sont pas disponibles dans le panneau de configuration Lync Server.

</div>

<span> </span>

</div>

</div>

</div>


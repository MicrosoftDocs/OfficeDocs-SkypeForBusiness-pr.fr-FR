---
title: Activation de la qualité de service pour les appareils non basés sur Windows
TOCTitle: Activation de la qualité de service pour les appareils non basés sur Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204750(v=OCS.15)
ms:contentKeyID: 49296631
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation de la qualité de service pour les appareils non basés sur Windows

 

_**Dernière rubrique modifiée :** 2012-11-01_

Quand vous installez Microsoft Lync Server 2013, la qualité de service (QoS) n’est activée pour aucun appareil de votre organisation utilisant un système d’exploitation autre que Windows. Vous pouvez le vérifier en exécutant la commande suivante dans Lync Server 2013 Management Shell :

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

Si la propriété EnableQoS est définie sur False (comme dans les résultats précédents), la qualité de service n’est pas activée pour les ordinateurs et les appareils qui utilisent un système d’exploitation autre que Windows. La QoS est activée par défaut pour les appareils Lync Phone Edition, mais il est toutefois possible de la désactiver pour Lync Phone Edition.

Pour activer la qualité de service au niveau global, exécutez la commande suivante dans Lync Server Management Shell :

    Set-CsMediaConfiguration -EnableQoS $True

La commande précédente active la QoS au niveau global, mais notez que les paramètres de configuration multimédia peuvent aussi être appliqués au niveau du site. Si vous avez besoin d’activer la qualité de service pour un site, vous devez inclure l’identité des paramètres de configuration lorsque vous appelez l’applet de commande Set-CsMediaConfiguration. Cette commande, par exemple, active la QoS pour le site de Redmond :

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

> [!NOTE]  
> Est-il nécessaire d’activer la QoS au niveau du site ? Cela dépend. Les paramètres affectés au site sont prioritaires sur ceux affectés à l’étendue globale. Supposons que vous avez activé la QoS au niveau global, mais qu’elle est désactivée au niveau du site (le site de Redmond). Dans ce cas, la qualité de service sera désactivée pour le site de Redmond, car le site est prioritaire. Pour activer la qualité de service sur le site de Redmond, vous devez modifier les paramètres de configuration multimédia appliqués à ce site.

Si vous voulez activer simultanément la QoS pour tous vos paramètres de configuration multimédia (indépendamment de l’étendue), exécutez cette commande dans Lync Server Management Shell :

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Vous pouvez désactiver la QoS pour les appareils qui utilisent un système d’exploitation autre que Windows en affectant la valeur False à la propriété EnableQoS. Par exemple :

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Cela vous donne la possibilité d’implémenter la QoS sur des parties de votre réseau (par exemple, sur le site de Redmond), tout en la gardant désactivée sur d’autres.

La QoS peut seulement être activée et désactivée dans Lync Server Management Shell. Ces options ne sont pas disponibles dans le Panneau de configuration Lync Server.


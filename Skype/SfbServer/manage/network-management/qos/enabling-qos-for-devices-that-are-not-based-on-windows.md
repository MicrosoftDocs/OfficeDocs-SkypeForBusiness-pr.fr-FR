---
title: Activation de la qualité de service pour les périphériques non basés sur Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Découvrez comment activer la qualité de service (QoS) pour les appareils utilisés au sein de votre organisation qui utilisent un système d’exploitation autre que Windows.
ms.openlocfilehash: adb879d2319c5eeeb84578907ce57a3a408d9a13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279409"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Activation de la qualité de service (QoS) dans Skype entreprise Server pour les appareils qui ne sont pas basés sur Windows


Lorsque vous installez Skype entreprise Server, la qualité de service (QoS) n’est pas activée pour les appareils utilisés dans votre organisation qui utilisent un système d’exploitation autre que Windows. Vous pouvez vérifier ceci en exécutant la commande suivante à partir de l’interpréteur de commandes de Skype entreprise ServerManagement:

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

Si la propriété EnableQoS est définie sur false (comme dans la sortie précédente), cela signifie que la qualité de service n’est pas activée pour les ordinateurs et appareils utilisant un système d’exploitation autre que Windows.

Pour activer la qualité de service sur l’étendue globale, exécutez la commande suivante à partir de Skype entreprise Server Management Shell:

    Set-CsMediaConfiguration -EnableQoS $True

La commande précédente autorise la qualité de service (QoS) au niveau de l’étendue globale. Néanmoins, il est important de noter que les paramètres de configuration de média peuvent également être appliqués à l’étendue du site. Si vous devez activer la qualité de service pour un site, vous devez inclure l’identité des paramètres de configuration lors de l’appel de Set-CsMediaConfiguration. Par exemple, cette commande active QoS pour le site de Redmond:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> Avez-vous besoin d’activer la qualité de service (QoS) sur l’étendue du site? Cela dépend. Les paramètres assignés à l’étendue du site sont prioritaires sur les paramètres attribués à l’étendue globale. Supposez que la qualité de service (QoS) soit activée sur l’étendue globale mais désactivée sur l’étendue du site (pour le site de Redmond). Dans ce cas, la qualité de service est désactivée pour le site de Redmond; ce n’est pas parce que les paramètres du site sont prioritaires. Pour activer la qualité de service (QoS) pour le site de Redmond, vous devez le faire à l’aide des paramètres de configuration de média appliqués au site.


Si vous souhaitez activer simultanément la qualité de service (QoS) pour tous les paramètres de configuration de média (quelle que soit l’étendue), exécutez la commande suivante à partir de LSkype pour Business Server Management Shell:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Vous pouvez désactiver la qualité de service (QoS) pour les appareils qui utilisent un système d’exploitation différent de Windows en définissant la valeur de la propriété EnableQoS sur false. Par exemple :

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Cette fonctionnalité vous permet d’implémenter la qualité de service (QoS) sur certaines parties de votre réseau (par exemple, sur le site de Redmond) tout en laissant la qualité de service désactivée sur d’autres parties de votre réseau.

La qualité de service (QoS) peut uniquement être activée et désactivée à l’aide de Windows PowerShell. Ces options ne sont pas disponibles dans le panneau de configuration Skype entreprise Server.



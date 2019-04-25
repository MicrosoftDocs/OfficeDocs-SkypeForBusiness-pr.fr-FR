---
title: Activation de la qualité de service pour les périphériques non basés sur Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Découvrez comment activer QoS pour les appareils utilisés dans votre organisation qui utilisent un système d’exploitation autre que Windows.
ms.openlocfilehash: b1f3dae2d2b499b334995d7754282c56872ce111
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232712"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Activation de QoS dans Skype pour Business Server pour les périphériques qui ne sont pas basés sur Windows


Lorsque vous installez Skype pour Business Server, qualité de Service (QoS) ne sera pas activée pour tous les périphériques utilisés dans votre organisation qui utilisent un système d’exploitation autre que Windows. Vous pouvez le vérifier en exécutant la commande suivante à partir de la Skype pour Business ServerManagement Shell :

    Get-CsMediaConfiguration

En supposant que vous n’avez apporté des modifications à vos paramètres de configuration multimédia, vous devriez obtenir des informations semblables à ceci :

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Si la propriété EnableQoS est définie sur False (comme dans la sortie précédente), cela signifie que la qualité de Service n’est pas activée pour les ordinateurs et périphériques qui utilisent un système d’exploitation autre que Windows.

Pour activer la qualité de Service dans l’étendue globale, exécutez la commande suivante à partir de la Skype pour Business Server Management Shell :

    Set-CsMediaConfiguration -EnableQoS $True

La commande précédente Active QoS dans l’étendue globale ; Toutefois, il est important de noter que les paramètres de configuration multimédia peuvent également s’appliquer à l’étendue du site. Si vous souhaitez activer la qualité de Service pour un site, vous devez inclure l’identité des paramètres de configuration lors de l’appel de Set-CsMediaConfiguration. Par exemple, cette commande permet de qualité de service pour le site Redmond :

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> Vous devez activer QoS au niveau du site ? Cela dépend. Les paramètres définis au niveau du site sont prioritaires sur les paramètres assignés à l’étendue globale. Supposons que vous ayez QoS activée dans l’étendue globale, mais désactivé au niveau du site (pour le site de Redmond). Dans ce cas, la qualité de Service serait désactivée pour le site de Redmond. C’est parce que les paramètres du site sont prioritaires. Pour activer QoS pour le site Redmond, vous devrez faire à l’aide des paramètres de configuration multimédia appliqué à ce site.


Si vous souhaitez activer simultanément la QoS pour tous vos paramètres de configuration multimédia (indépendamment de l’étendue), exécutez cette commande à partir de la LSkype pour Business Server Management Shell :

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Vous pouvez désactiver la qualité de service pour les périphériques qui utilisent un système d’exploitation autre que Windows en définissant la valeur de la propriété EnableQoS sur False. Par exemple :

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Cela vous donne la possibilité de mettre en œuvre QoS sur certaines parties de votre réseau (par exemple, sur le site de Redmond) tout en laissant la qualité de Service désactivé sur d’autres parties de votre réseau.

Qualité de service peut uniquement être activée et désactivée à l’aide de Windows PowerShell. Ces options ne sont pas disponibles dans le Skype pour le panneau de configuration serveur Business.



---
title: Activation de la qualité de service pour les appareils non basés sur Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Découvrez comment activer la QoS pour les appareils utilisés dans votre organisation qui utilisent un système d’exploitation autre que Windows.
ms.openlocfilehash: 597f2df19ac2379bea3f618280ea1c86b2e1f8eb
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60750173"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Activation de la QoS dans Skype Entreprise Server pour les appareils qui ne sont pas basés sur Windows


Lorsque vous installez Skype Entreprise Server, la qualité de service (QoS) n’est activée pour aucun appareil utilisé dans votre organisation qui utilise un système d’exploitation autre que Windows. Vous pouvez le vérifier en exécutant la commande suivante à partir de Skype Entreprise ServerManagement Shell :

**Get-CsMediaConfiguration**

En supposant que vous n’avez pas apporté de modifications à vos paramètres de configuration multimédia, vous devez obtenir des informations semblables à ceci :

Identité : global<br/>
EnableQoS : False<br/>
EncryptionLevel : RequireEncryption<br/>
EnableSiren : False<br/>
MaxVideoRateAllowed : VGA600K<br/>
EnableG722StereoCodec : True<br/>
EnableH264Codec : True<br/>
EnableAdaptiveBandwidthEstimation : True<br/>

Si la propriété EnableQoS est définie sur False (comme dans la sortie précédente), cela signifie que la qualité de service n’est pas activée pour les ordinateurs et les appareils qui utilisent un système d’exploitation autre que Windows.

Pour activer la qualité de service au niveau global, exécutez la commande suivante à partir de Skype Entreprise Server Management Shell :

**Set-CsMediaConfiguration -EnableQoS $True**

La commande précédente active la QoS au niveau global, mais notez que les paramètres de configuration multimédia peuvent aussi être appliqués au niveau du site. Si vous devez activer la qualité de service pour un site, vous devez inclure l’identité des paramètres de configuration lors de l’appel de Set-CsMediaConfiguration. Cette commande, par exemple, active la QoS pour le site de Redmond :

**Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True**


> [!NOTE]
> Est-il nécessaire d’activer la QoS au niveau du site ? Cela dépend. Les paramètres affectés au site sont prioritaires sur ceux affectés à l’étendue globale. Supposons que la QoS soit activée au niveau de l’étendue globale, mais désactivée au niveau de l’étendue Site (pour le site redmond). Dans ce cas, la qualité de service est désactivée pour le site redmond ; En raison du fait que les paramètres du site sont prioritaire. Pour activer la QoS pour le site Redmond, vous devez utiliser les paramètres de configuration multimédia appliqués à ce site.


Si vous souhaitez activer simultanément QoS pour tous vos paramètres de configuration multimédia (quelle que soit l’étendue), exécutez cette commande à partir de LSkype for Business Server Management Shell :

**Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True**

Vous pouvez désactiver la qualité de service pour les appareils qui utilisent un système d’exploitation autre que Windows en fixant la valeur de la propriété EnableQoS sur False. Par exemple :

**Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False**

Cela vous donne la possibilité d’implémenter la QoS sur des parties de votre réseau (par exemple, sur le site de Redmond), tout en la gardant désactivée sur d’autres.

La QoS ne peut être activée et désactivée qu’à l’aide Windows PowerShell. Ces options ne sont pas disponibles dans le Panneau de Skype Entreprise Server de contrôle.

> [!NOTE]
> Skype Entreprise clients pour iOS version 6.17 et ultérieures peuvent désormais la prise en charge de QoS.  Cette fonctionnalité de QoS s’applique uniquement aux clients Skype Entreprise et aux périphériques téléphoniques IP qui sont enregistrés directement sur un serveur de pool Skype Entreprise ou Lync interne sur des réseaux gérés. La QoS n’est pas applicable pour le trafic acheminé sur Internet.

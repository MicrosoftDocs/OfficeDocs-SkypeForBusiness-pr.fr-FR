---
title: Configuration de la qualité de service sur les appareils Microsoft Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9f7f96e90aa07da193f9ffb714fc3437ba46cd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a>Configuration de la qualité de service sur les appareils Microsoft Lync Phone Edition dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Même si la qualité de service (QoS) n’est pas activée par défaut pour les appareils tels que les iPhone, la qualité de service (QoS) est activée par défaut pour les appareils exécutant Lync Phone Edition. (Ces appareils sont généralement désignés sous le nom de téléphones de communications unifiées ou unifiées.) Pour vérifier cela, exécutez la commande Windows PowerShell suivante à partir de Lync Server Management Shell:

    Get-CsUCPhoneConfiguration

Si vous n’avez apporté aucune modification aux paramètres de configuration de votre téléphone UC, vous obtiendrez des informations similaires à ce qui suit:

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

Pour des raisons de qualité de service, une seule de ces propriétés est particulièrement intéressante: VoiceDiffServTag. Le VoiceDiffServTag représente la valeur DSCP affectée au trafic vocal émis à partir d’un appareil Lync Phone Edition.

<div>


> [!NOTE]
> Le paramètre Voice8021p n’est plus pris en charge dans Lync Server 2013. Le paramètre reste valide pour la compatibilité descendante avec Microsoft Lync Server 2010; Néanmoins, il n’a aucun effet sur les appareils utilisés avec Lync Server 2013.



</div>

Dans la plupart des réseaux, le marquage de paquets Lync Phone Edition avec un VoiceDiffServTag de 40 ne doit pas provoquer de problèmes. À la place, le trafic audio est presque toujours marqué avec le le code DSCP 46. Pour garantir la cohérence de votre réseau, il peut être préférable de changer la propriété VoiceDiffServTag de vos téléphones UC vers 46.

Pour ce faire, vous pouvez utiliser Windows PowerShell ou le panneau de configuration de Lync Server. Pour modifier la valeur VoiceDiffServTag à l’aide de Windows PowerShell, exécutez la commande suivante à partir de Lync Server Management Shell:

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

La commande précédente modifie la collection globale des paramètres de configuration de téléphone UC. Notez, toutefois, que les paramètres de téléphone monouc peuvent également être attribués à l’étendue du site. Pour modifier les paramètres de configuration de téléphone UC sur l’étendue du site, vous devez spécifier l’identité du site. Par exemple :

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

Vous pouvez également utiliser la commande suivante pour modifier simultanément l’ensemble des paramètres de configuration du téléphone de communications unifiées:

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Si vous préférez apporter cette modification à l’aide du panneau de configuration de Lync Server, démarrez le panneau de configuration, puis procédez comme suit:

1.  Cliquez sur **clients** , puis sur Configuration de l' **appareil**.

2.  Dans l’onglet Configuration de l' **appareil** , double-cliquez sur l’ensemble de paramètres que vous souhaitez modifier (par exemple, **Global**).

3.  Dans la boîte de dialogue **modifier la configuration** de l’appareil, définissez la valeur de la zone **qualité de service (QoS)** sur **46** , puis cliquez sur **valider**.

Si vous avez plusieurs collections, vous devrez répéter ce processus pour chaque ensemble de paramètres de téléphone de communications unifiées. Le panneau de configuration de Lync Server ne vous permet pas de modifier simultanément plusieurs collections de paramètres.

Si vous disposez de périphériques qui ne sont pas basés sur le système d’exploitation Windows (par exemple, iPhone) au sein de votre organisation, ces appareils ne sont pas touchés par le changement du paramètre VoiceDiffServTag. Pour modifier les valeurs DSCP sur ces appareils, vous devez vous référer au manuel d’administration de chaque type d’appareil.

</div>

<span> </span>

</div>

</div>

</div>


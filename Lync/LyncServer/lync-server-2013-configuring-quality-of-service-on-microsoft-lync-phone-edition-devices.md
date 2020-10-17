---
title: Configuration de la qualité de service sur les appareils Microsoft Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c69bf438965c536a3ba424699a7109308368397
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534961"
---
# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a>Configuration de la qualité de service sur les appareils Microsoft Lync Phone Edition dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Bien que la qualité de service (QoS) ne soit pas activée par défaut pour les appareils tels que les iPhone, la qualité de service (QoS) est activée par défaut pour les appareils exécutant Lync Phone Edition. (Ces appareils sont communément appelés téléphones cu ou Unified Communication.) Pour vérifier cela, exécutez la commande Windows PowerShell suivante à partir de Lync Server Management Shell :

    Get-CsUCPhoneConfiguration

Si vous n’avez apporté aucune modification à vos paramètres de configuration de téléphone UC, vous obtiendrez des informations similaires à ce qui suit :

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

Pour des raisons de qualité de service, seule l’une de ces propriétés est intéressante : VoiceDiffServTag. Le VoiceDiffServTag représente la valeur DSCP affectée au trafic vocal émanant d’un appareil Lync Phone Edition.

<div>


> [!NOTE]
> Le paramètre Voice8021p n’est plus pris en charge dans Lync Server 2013. Le paramètre est toujours valide pour la compatibilité descendante avec Microsoft Lync Server 2010 ; Toutefois, il n’a aucun effet sur les appareils utilisés avec Lync Server 2013.



</div>

Dans la plupart des réseaux, le marquage de paquets Lync Phone Edition avec un VoiceDiffServTag de 40 ne doit pas causer de problème. Toutefois, 40 n’est pas la valeur généralement utilisée pour le trafic audio ; au lieu de cela, le trafic audio est presque toujours marqué avec le code DSCP 46. Afin de préserver la cohérence au sein de votre réseau, vous pouvez modifier la propriété VoiceDiffServTag de vos téléphones UC sur 46.

Pour ce faire, vous pouvez utiliser Windows PowerShell ou le panneau de configuration Lync Server. Pour modifier la valeur VoiceDiffServTag à l’aide de Windows PowerShell, exécutez la commande suivante à partir de Lync Server Management Shell :

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

La commande précédente modifie la collection globale des paramètres de configuration de téléphonie de communications unifiées. Notez toutefois que les paramètres de téléphone UC peuvent également être attribués à l’étendue site. Pour modifier les paramètres de configuration du téléphone de communications unifiées au niveau de l’étendue site, vous devez spécifier l’identité du site. Par exemple :

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

Vous pouvez également utiliser la commande suivante pour modifier simultanément tous les paramètres de configuration de votre téléphone de communications unifiées :

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Si vous préférez effectuer cette modification à l’aide du panneau de configuration Lync Server, démarrez le panneau de configuration, puis procédez comme suit :

1.  Cliquez sur **clients** , puis sur Configuration de l' **appareil**.

2.  Dans l’onglet **configuration du périphérique** , double-cliquez sur la collection de paramètres à modifier (par exemple, **Global**).

3.  Dans la boîte de dialogue **modifier la configuration** de l’appareil, définissez la valeur de la zone **voix de service (QoS)** sur **46** , puis cliquez sur **valider**.

Si vous avez plusieurs collections, vous devez répéter ce processus pour chaque ensemble de paramètres de téléphone de communications unifiées. Le panneau de configuration Lync Server ne vous permet pas de modifier simultanément plusieurs collections de paramètres.

Si vous avez des appareils qui ne sont pas basés sur le système d’exploitation Windows (comme les iPhone) de votre organisation, ces appareils ne seront pas affectés par la modification du paramètre VoiceDiffServTag. Si vous souhaitez modifier les valeurs DSCP sur ces appareils, vous devez vous référer au manuel d’administration pour chacun de vos types d’appareils.

</div>

<span> </span>

</div>

</div>

</div>


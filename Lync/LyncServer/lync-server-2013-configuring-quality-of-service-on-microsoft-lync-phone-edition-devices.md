---
title: "Conf. de la qual. de service sur les appareils Microsoft Lync Phone Edition"
TOCtitle: "Conf. de la qual. de service sur les appareils Microsoft Lync Phone Edition"
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205137(v=OCS.15)
ms:contentKeyID: 49298452
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la qualité de service sur les appareils Microsoft Lync Phone Edition

 

_**Dernière rubrique modifiée :** 2012-11-01_

Bien que la Qualité de service (QoS) ne soit pas activée par défaut pour les appareils tels que les iPhones, elle l’est pour les appareils exécutant Lync Phone Edition. (Ces appareils portent généralement le nom de téléphones de communications unifiées.) Pour vérifier que c’est le cas, exécutez la commande Windows PowerShell suivante à partir de Lync Server Management Shell :

    Get-CsUCPhoneConfiguration

Si vous n’avez apporté aucune modification à vos paramètres de configuration de téléphone de communications unifiées, vous recevrez des informations semblables aux suivantes :

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

En ce qui concerne la Qualité de service, une seule de ces propriétés est digne d’intérêt : VoiceDiffServTag. Elle représente la valeur DSCP assignée au trafic vocal provenant d’un appareil Lync Phone Edition.

> [!NOTE]  
> Le paramètre Voice8021p n’est plus pris en charge dans Lync Server 2013. Il est encore valide pour des raisons de compatibilité descendante avec Microsoft Lync Server 2010 ; toutefois, il n’a aucun effet sur les appareils utilisés avec Lync Server 2013.

Sur la plupart des réseaux, le marquage de paquets Lync Phone Edition avec une propriété VoiceDiffServTag de 40 ne doit pas causer de problème. Toutefois, 40 n’est pas la valeur généralement utilisé pour le trafic audio. Au lieu de cela, ce trafic est presque toujours marqué avec le code DSCP 46. Afin de conserver une cohérence sur l’ensemble de votre réseau, il peut être préférable de modifier la propriété VoiceDiffServTag de vos appareils de communications unifiées et de lui affecter la valeur 46.

Pour cela, vous pouvez utiliser Windows PowerShell ou le Panneau de configuration Lync Server. Pour modifier la valeur de VoiceDiffServTag à l’aide de Windows PowerShell, exécutez la commande suivante à partir de Lync Server Management Shell :

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

La commande ci-dessus modifie la collection globale de paramètres de configuration des téléphones de communications unifiées. Notez toutefois que les paramètres de ces téléphones peuvent également être assignés à l’échelle du site. Pour modifier les paramètres de configuration des téléphones de communications unifiées à l’échelle du site, vous devez spécifier l’identité du site. Par exemple :

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

Vous pouvez également utiliser la commande suivante pour modifier simultanément tous les paramètres de configuration de vos téléphones de communications unifiées :

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Si vous préférez apporter cette modification à l’aide du Panneau de configuration Lync Server, démarrez le Panneau de configuration, puis appliquez la procédure suivante :

1.  Cliquez sur **Clients**, puis sur **Configuration du périphérique**.

2.  Sous l’onglet **Configuration du périphérique**, double-cliquez sur la collection de paramètres que vous souhaitez modifier (par exemple, **Global**).

3.  Dans la boîte de dialogue **Modifier la configuration de l’appareil**, affectez la valeur **46** à **Qualité de service de la voix (QoS)**, puis cliquez sur **Valider**.

Si vous avez plusieurs collections, vous devez répéter cette procédure pour chaque collection de paramètres des téléphones de communications unifiées. Le Panneau de configuration Lync Server n’autorise pas la modification simultanée de plusieurs collections de paramètres.

Si vous avez des appareils qui ne sont pas basés sur le système d’exploitation Windows (tels que des iPhones) dans votre organisation, ces appareils ne seront pas affectés par la modification du paramètre VoiceDiffServTag. Si vous voulez modifier les valeurs DSCP sur ces appareils, consultez le manuel d’administration de chacun de vos types d’appareils.


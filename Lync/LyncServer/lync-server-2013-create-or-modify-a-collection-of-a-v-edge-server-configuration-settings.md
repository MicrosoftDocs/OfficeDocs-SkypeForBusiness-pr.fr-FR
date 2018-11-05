---
title: "Créa. ou mod. d’une collection de param. de configuration de serveur Edge A/V"
TOCtitle: "Créa. ou mod. d’une collection de param. de configuration de serveur Edge A/V"
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49891327
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création ou modification d’une collection de paramètres de configuration de serveur Edge A/V

 

_**Dernière rubrique modifiée :** 2012-11-01_

Le service Edge A/V permet à vos utilisateurs internes (les utilisateurs connectés au réseau de votre organisation) de partager des fichiers audio et vidéo avec des utilisateurs externes (des utilisateurs qui ne sont pas connectés au réseau de votre organisation). La gestion du service Edge A/V s’effectue à l’aide des paramètres de configuration de ce service. Les paramètres peuvent être configurés au niveau du site ou du service (c’est-à-dire pour un serveur Edge A/V).

Quand vous installez Lync Server, un ensemble global de paramètres de configuration Edge A/V est créé automatiquement. Par ailleurs, vous pouvez utiliser Lync Server Management Shell et l’applet de commande New-CsAVEdgeConfiguration pour créer des paramètres au niveau de l’étendue Site ou de l’étendue Service (en d’autres termes, pour un serveur Edge A/V précis). Si vous créez des paramètres, gardez à l’esprit les aspects suivants :

  - Les paramètres configurés au niveau de l’étendue Service (c’est-à-dire sur un serveur) prévalent sur tous les autres paramètres.

  - Les paramètres configurés au niveau de l’étendue Site prévalent sur les paramètres configurés au niveau de l’étendue Global. Les paramètres au niveau de l’étendue Service, quant à eux, prévalent sur les paramètres au niveau de l’étendue Site.

  - Les paramètres au niveau de l’étendue Global seront utilisés uniquement si aucun autre paramètre du service n’est configuré sur le serveur et s’il n’existe aucun paramètre pour le site où ce serveur est situé.

Tous vos paramètres peuvent ensuite être modifiés à l’aide de l’applet de commande Set-CsAVEdgeConfiguration. Pour plus d’informations, voir les rubriques d’aide relatives aux applets de commande [New-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAVEdgeConfiguration) et [Set-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsAVEdgeConfiguration).

## Création de paramètres de configuration Edge A/V au niveau de l’étendue Site

  - La commande suivante crée une collection de paramètres de configuration Edge A/V pour le site Redmond :
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

## Création de paramètres de configuration Edge A/V personnalisés au niveau de l’étendue Site

  - Dans la mesure où aucun paramètre supplémentaire n’a été inclus, ces nouveaux paramètres utilisent les valeurs par défaut pour le service Edge A/V. Vous pouvez également ajouter des paramètres et des valeurs de paramètres supplémentaires pour créer une collection personnalisée. Par exemple, cette commande définit la propriété MaxTokenLifetime à 4 heures (04 heures : 00 minute : 00 seconde) :
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

## Création de paramètres de configuration Edge A/V personnalisés au niveau de l’étendue Service

  - Cette commande crée une collection similaire appliquée au serveur Edge A/V atl-edge-001.litwareinc.com :
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

## Modification des paramètres de configuration Edge A/V existants

  - Dans cet exemple, l’applet de commande Set-CsAVEdgeConfiguration est utilisée pour changer la durée de vie maximale du jeton du site Redmond en la définissant à 12 heures :
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

## Voir aussi

#### Tâches

[Renvoi des informations de configuration du serveur Edge A/V](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Suppression d’une collection existante de paramètres de configuration d’un serveur Edge A/V](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  

#### Autres ressources

[Serveurs Edge Audio/Vidéo (A/V) dans Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[New-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAVEdgeConfiguration)  
[Set-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsAVEdgeConfiguration)


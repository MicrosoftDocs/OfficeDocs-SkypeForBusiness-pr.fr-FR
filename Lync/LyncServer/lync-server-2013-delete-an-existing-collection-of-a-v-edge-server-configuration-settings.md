---
title: "Suppr. d’une collection existante de par. de conf. d’un serveur Edge A/V"
TOCtitle: "Suppr. d’une collection existante de par. de conf. d’un serveur Edge A/V"
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49891376
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression d’une collection existante de paramètres de configuration d’un serveur Edge A/V

 

_**Dernière rubrique modifiée :** 2012-11-01_

Le service Edge A/V permet à vos utilisateurs internes (les utilisateurs connectés au réseau de votre organisation) de partager des fichiers audio et vidéo avec des utilisateurs externes (des utilisateurs qui ne sont pas connectés au réseau de votre organisation). La gestion du service Edge A/V s’effectue à l’aide des paramètres de configuration de ce service. Les paramètres peuvent être configurés au niveau du site ou du service (c’est-à-dire pour un serveur Edge A/V).

Lorsque vous installez Lync Server, une collection globale de paramètres de configuration Edge A/V est créée pour vous. Cette collection globale ne peut pas être supprimée. Toutefois, vous pouvez utiliser Lync Server Management Shell et l’applet de commande Remove-CsAVEdgeConfiguration pour « réinitialiser » la collection globale ; cela signifie simplement que les valeurs par défaut de toutes les propriétés de la collection globale sont rétablies. Par exemple, si vous avez affecté à la propriété MaxTokenLifetime un nombre d’heures égal à 16, la valeur par défaut (à savoir 8 heures) de cette propriété est rétablie.

Toutefois, vous pouvez supprimer les collections de paramètres personnalisées que vous avez créées au niveau de l’étendue du site ou du service à l’aide de l’applet de commande Remove-CsAVEdgeConfiguration. Si vous supprimez les paramètres au niveau du site, les serveurs Edge A/V dans ce site sont alors gérés par les paramètres globaux. Si vous supprimez les paramètres au niveau du service, ce serveur est alors géré par ses paramètres de site (le cas échéant) ou par les paramètres globaux si aucun paramètre de site n’est disponible.

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Remove-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAVEdgeConfiguration).

## Réinitialisation de la collection globale

  - La commande suivante réinitialise la collection globale des paramètres de configuration Edge A/V :
    
        Remove-CsAVEdgeConfiguration -Identity "global"

## Suppression d’une collection de l’étendue du site

  - Cette commande supprime les paramètres de configuration Edge A/V appliqués au site Redmond :
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

## Suppression d’une collection de l’étendue du service

  - Cette commande supprime les paramètres appliqués au serveur Edge A/V atl-edge-001.litwareinc.com :
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

## Voir aussi

#### Tâches

[Renvoi des informations de configuration du serveur Edge A/V](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Création ou modification d’une collection de paramètres de configuration de serveur Edge A/V](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  

#### Autres ressources

[Serveurs Edge Audio/Vidéo (A/V) dans Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Remove-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAVEdgeConfiguration)


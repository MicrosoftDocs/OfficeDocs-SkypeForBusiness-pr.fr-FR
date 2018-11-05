---
title: Renvoi des informations de configuration du serveur Edge A/V
TOCTitle: Renvoi des informations de configuration du serveur Edge A/V
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49891496
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Renvoi des informations de configuration du serveur Edge A/V

 

_**Dernière rubrique modifiée :** 2012-11-01_

Le service Edge A/V permet à vos utilisateurs internes (les utilisateurs connectés au réseau de votre organisation) de partager des fichiers audio et vidéo avec des utilisateurs externes (des utilisateurs qui ne sont pas connectés au réseau de votre organisation). La gestion du service Edge A/V s’effectue à l’aide des paramètres de configuration de ce service. Les paramètres peuvent être configurés au niveau du site ou du service (c’est-à-dire pour un serveur Edge A/V).

Pour retourner les informations relatives aux paramètres de configuration de serveur Edge A/V appliqués dans votre organisation, vous devez utiliser Lync Server Management Shell et l’applet de commande Get-CsAVEdgeConfiguration. Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAVEdgeConfiguration).

Les informations retournées par l’applet de commande Get-CsAVEdgeConfiguration ressemblent à ceci :

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

## Retour d’informations pour tous vos paramètres de configuration de serveur Edge A/V

  - La commande suivante retourne les informations relatives à tous les paramètres de configuration de serveur Edge A/V actuellement utilisés dans votre organisation :
    
        Get-CsAVEdgeConfiguration

## Retour d’informations pour les paramètres de configuration de serveur Edge A/V étendus aux sites

  - Pour retourner les informations relatives à une collection spécifique de paramètres de configuration Edge A/V, spécifiez l’identité de cette collection lors de l’exécution de l’applet de commande Get-CsAVEdgeConfiguration. Par exemple, la commande suivante retourne uniquement les informations relatives aux paramètres appliqués au site Redmond :
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

## Retour d’informations pour les paramètres de configuration de serveur Edge A/V étendus aux services

  - La commande suivante retourne uniquement les informations relatives aux paramètres appliqués à un serveur Edge A/V spécifique :
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

## Voir aussi

#### Tâches

[Création ou modification d’une collection de paramètres de configuration de serveur Edge A/V](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[Suppression d’une collection existante de paramètres de configuration d’un serveur Edge A/V](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  

#### Autres ressources

[Serveurs Edge Audio/Vidéo (A/V) dans Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)


---
title: "LS 2013 : Exp. top. LS 2013 et copie vers le support ext. de l’install. Edge"
TOCTitle: Exportation de la topologie et copie vers le support externe de l’installation Edge
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398983(v=OCS.15)
ms:contentKeyID: 49299065
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exportation de la topologie Lync Server 2013 et copie vers le support externe de l’installation Edge

 

_**Dernière rubrique modifiée :** 2012-09-08_

Après avoir publié votre topologie, l’Assistant Déploiement de Lync Server doit accéder aux données du magasin central de gestion pour lancer le processus de déploiement sur le serveur. Dans le réseau interne, les données sont disponibles directement depuis les serveurs, mais les serveurs Edge ne figurant pas dans le domaine interne ne peuvent pas accéder à ces informations. Pour que les données de configuration de topologie soient disponibles pour un déploiement de serveur Edge, vous devez exporter les données de topologie dans un fichier à copier sur un support externe (par exemple, une clé USB ou un partage réseau disponible depuis le serveur Edge) avant d’exécuter l’Assistant Déploiement de Lync Server sur le serveur Edge. Utilisez la procédure suivante pour rendre vos données de configuration de topologie accessibles au serveur Edge que vous déployez.

> [!NOTE]  
> Après avoir installé Lync Server 2013 sur un serveur Edge, vous gérez le serveur Edge à l’aide des outils d’administration du réseau interne, ce qui réplique automatiquement la configuration sur tous les serveurs Edge de votre déploiement. Les seules exceptions concernent l’attribution et l’installation de certificats, ainsi que l’arrêt et le démarrage des services, qui doivent tous deux être effectués sur le serveur Edge.

## Pour rendre vos données de topologie accessibles sur un serveur Edge à l’aide de Lync Server Management Shell

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Dans Lync Server Management Shell, exécutez l’applet de commande suivante :
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  Copiez le fichier exporté sur un support externe (par exemple, une clé USB ou un partage réseau disponible depuis le serveur Edge lors du déploiement).


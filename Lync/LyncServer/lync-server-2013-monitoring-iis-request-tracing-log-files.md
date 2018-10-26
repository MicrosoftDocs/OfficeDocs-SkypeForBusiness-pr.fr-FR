---
title: Surveillance des fichiers journaux de suivi des demandes IIS
TOCTitle: Surveillance des fichiers journaux de suivi des demandes IIS
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh690034(v=OCS.15)
ms:contentKeyID: 49298608
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Surveillance des fichiers journaux de suivi des demandes IIS

 

_**Dernière rubrique modifiée :** 2016-12-08_

Lorsque vous activez le suivi des demandes des services Internet (IIS) pour le service Mobility Service Lync Server, les fichiers journaux générés peuvent consommer jusqu’à trois gigaoctets d’espace disque par jour. La journalisation du suivi IIS est activée par défaut. Vous devez surveiller les serveurs frontaux afin de vous assurer que la quantité d’espace disque libre est suffisante.

Par défaut, les services Internet (IIS) stockent les fichiers journaux dans %SystemDrive%\\inetpub\\logs\\LogFiles.

Pour désactiver le suivi des demandes IIS pour un serveur entier, tapez ce qui suit sur la ligne de commande :

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

Pour plus d’informations sur la commande **httpLogging**, voir [http://go.microsoft.com/fwlink/?linkid=234927\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=234927%26clcid=0x40c).


---
title: Prise en charge du stockage des fichiers dans Lync Server 2013
TOCTitle: Prise en charge du stockage des fichiers
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg399073(v=OCS.15)
ms:contentKeyID: 49299234
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prise en charge du stockage des fichiers dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Lync Server 2013 utilise le même magasin de fichiers pour tout le stockage de fichiers. Le stockage de fichiers comprend les éléments suivants :

  - Un partage de fichiers sur un stockage DAS (Direct Attached Storage) ou un réseau de stockage SAN (Storage Area Network), dont un système de fichiers distribués (DFS) et sur une solution RAID (Redundant Array Of Independent Disks) pour les magasins de fichiers. Pour plus d’informations sur les exigences de stockage, reportez-vous à [Configuration requise pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) et à [Configuration matérielle et logicielle requise pour le directeur dans Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) dans la documentation de planification. Pour plus d’informatios sur DFS pour système d’exploitation Windows Server 2008, reportez-vous au Guide pas à pas des systèmes de fichiers DFS pour Windows Server 2008 à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835).

  - Un cluster partagé pour le partage de fichiers. Si vous utilisez un cluster partagé, vous devez utiliser des serveurs de clusters exécutant Windows Server 2008 ou Windows Server 2008 R2. Utiliser des serveurs de clusters exécutant une ancienne version de Windows peut provoquer des problèmes d’autorisation rendant certaines fonctionnalités indisponibles. Utilisez l’administrateur de clusters pour créer les partages de fichiers. Pour plus d’informations sur son utilisation, reportez-vous à l’article 284838 de la base de connaissances Windows, « Comment créer un partage de fichiers de clusters de serveurs avec Cluster.exe » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899).


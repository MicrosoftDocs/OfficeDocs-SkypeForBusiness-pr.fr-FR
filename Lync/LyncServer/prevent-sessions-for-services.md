---
title: Interdiction des sessions pour les services
TOCTitle: Interdiction des sessions pour les services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49891341
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Interdiction des sessions pour les services

 

_**Dernière rubrique modifiée :** 2012-10-04_

Le Panneau de configuration Microsoft Lync Server 2010 vous permet d’empêcher l’exécution de nouvelles sessions de tous les services Lync Server 2010 exécutés sur un ordinateur spécifique ou de nouvelles sessions d’un service Lync Server 2010 spécifique.

## Pour empêcher l’exécution de nouvelles sessions de tous les services Lync Server sur un ordinateur

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez le Panneau de configuration Lync Server.

3.  Dans la barre de navigation de gauche, cliquez sur **Topologie** , puis sur **État** .

4.  Dans la page **État** , recherchez dans la liste l’ordinateur qui exécute les services pour lesquels vous souhaitez empêcher toute nouvelle session, puis cliquez sur cet ordinateur.

5.  Cliquez sur **Action** .

6.  Cliquez sur **Empêcher de nouvelles sessions pour tous les services** .

## Pour empêcher l’exécution de nouvelles sessions d’un service spécifique

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez le Panneau de configuration Lync Server.

3.  Dans la barre de navigation de gauche, cliquez sur **Topologie** , puis sur **État** .

4.  Dans la page **État** , recherchez dans la liste l’ordinateur qui exécute le service que vous souhaitez démarrer ou arrêter, ou triez cette liste, puis cliquez sur cet ordinateur.

5.  Cliquez sur **Propriétés** .

6.  Triez la liste de services, si nécessaire, et cliquez sur le service pour lequel vous souhaitez empêcher toute nouvelle session.

7.  Cliquez sur **Action** .

8.  Cliquez sur **Empêcher de nouvelles sessions pour le service** .

9.  Cliquez sur **Fermer** .


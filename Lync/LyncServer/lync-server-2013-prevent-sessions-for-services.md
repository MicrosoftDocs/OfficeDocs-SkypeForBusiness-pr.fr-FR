---
title: Empêcher l’exécution de sessions de services dans Lync Server 2013
TOCTitle: Empêcher l’exécution de sessions de services dans Lync Server 2013
ms:assetid: 977dcc5c-2aac-48ef-86a1-a8d47b4d9e74
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182553(v=OCS.15)
ms:contentKeyID: 49298181
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Empêcher l’exécution de sessions de services dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Le Panneau de configuration Lync Server vous permet d’empêcher l’exécution de nouvelles sessions de tous les services Lync Server 2013 exécutés sur un ordinateur spécifique ou de nouvelles sessions d’un service Lync Server 2013 spécifique.

## Pour empêcher l’exécution de nouvelles sessions de tous les services Lync Server sur un ordinateur

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.

4.  Dans la page **État**, recherchez dans la liste l’ordinateur qui exécute les services pour lesquels vous souhaitez empêcher toute nouvelle session, puis cliquez sur cet ordinateur.

5.  Cliquez sur **Action**.

6.  Cliquez sur **Empêcher de nouvelles sessions pour tous les services**.

## Pour empêcher l’exécution de nouvelles sessions d’un service spécifique

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.

4.  Dans la page **État**, recherchez dans la liste l’ordinateur qui exécute le service que vous souhaitez démarrer ou arrêter, puis cliquez sur cet ordinateur.

5.  Cliquez sur **Propriétés**.

6.  Triez la liste de services, si nécessaire, et cliquez sur le service pour lequel vous souhaitez empêcher toute nouvelle session.

7.  Cliquez sur **Action**.

8.  Cliquez sur **Empêcher de nouvelles sessions pour le service**.

9.  Cliquez sur **Fermer**.

## Voir aussi

#### Autres ressources

[Gestion de la topologie Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)


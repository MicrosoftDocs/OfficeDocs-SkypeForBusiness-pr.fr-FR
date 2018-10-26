---
title: Vérification de la coexistence du pool pilote avec le pool hérité
TOCTitle: Vérification de la coexistence du pool pilote avec le pool hérité
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204914(v=OCS.15)
ms:contentKeyID: 49297265
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vérification de la coexistence du pool pilote avec le pool hérité

 

_**Dernière rubrique modifiée :** 2012-09-28_

## Vérifier le pool dans les outils d’administration d’Office Communications Server 2007 R2

1.  Ouvrez l’outil d’administration Office Communications Server 2007 R2.

2.  Développez le nœud **Forêt**, le nœud **Serveurs Standard Edition** ou **Pools Enterprise**, puis le nom du serveur ou du pool.

3.  Assurez-vous que les services Office Communications Server 2007 R2 s’exécutent sur le pool frontal.
    
    ![Office Communications Server 2007 R2 - Console d’administration](images/JJ204914.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 - Console d’administration")  

## Vérifier le pool pilote dans le Panneau de configuration Lync Server 2013

1.  À partir d’un compte d’utilisateur membre du rôle CsAdministrator, ouvrez une session sur le serveur frontal Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Cliquez sur **Topologie** .

4.  Vérifiez que les serveurs que vous avez déployés sont présents dans votre pool pilote.
    
    ![Page Topologie du Panneau de configuration Lync Server](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Page Topologie du Panneau de configuration Lync Server")  

## Vérifier que les services Lync Server 2013 ont démarré

1.  Sur le serveur frontal Lync Server 2013, ouvrez l’applet **Services** dans le groupe **Outils d’administration** .

2.  Vérifiez que les services répertoriés correspondent à la liste présentée dans la figure suivante.
    
    ![Page des services montrant les services Lync démarrés](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Page des services montrant les services Lync démarrés")


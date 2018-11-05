---
title: Suppression d’un serveur frontal d’un pool
TOCTitle: Suppression d’un serveur frontal d’un pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49891400
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression d’un serveur frontal d’un pool

 

_**Dernière rubrique modifiée :** 2012-10-04_

Le serveur frontalMicrosoft Lync Server 2010 Enterprise Edition ne peut pas exister en tant qu’ordinateur autonome. Il doit être défini comme pool de serveurs frontaux, même si le pool ne comporte qu’un seul ordinateur.

Cette rubrique décrit le processus de suppression d’un serveur frontal dans un pool de serveurs frontaux existant. Si le serveur frontal est le dernier serveur du pool ou si vous supprimez entièrement le pool, reportez-vous à [Suppression d’un pool frontal ou un serveur Standard Edition](remove-front-end-pool-or-standard-edition-server.md). Il n’est pas nécessaire de supprimer les différents serveurs frontaux avant de supprimer le pool de serveurs frontaux. La suppression du pool entraîne la suppression de chaque serveur frontal.

## Pour supprimer un serveur frontal d’un pool

1.  Ouvrez le serveur frontal Lync Server 2013 et le générateur de topologie.

2.  Accédez au nœud Lync Server 2010.

3.  Développez **Pools frontaux Enterprise Edition** , développez le pool de serveurs frontaux où se trouve le serveur frontal que vous souhaitez supprimer, cliquez avec le bouton droit sur le serveur frontal à supprimer, puis cliquez sur **Supprimer** .


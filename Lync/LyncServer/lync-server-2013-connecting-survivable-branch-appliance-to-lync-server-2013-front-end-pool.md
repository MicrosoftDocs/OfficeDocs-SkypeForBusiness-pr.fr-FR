---
title: "Lync Server 2013 : Connexion d’un SBA à un pool de serveurs frontaux"
TOCTitle: Connexion d’un Survivable Branch Appliance à un pool de serveurs frontaux Lync Server 2013
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49891313
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Connexion d’un Survivable Branch Appliance à un pool de serveurs frontaux Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-05_

Chaque Survivable Branch Appliance (SBA) est associé à un pool de serveurs frontaux, qui fait office de serveur d’inscriptions de sauvegarde pour le SBA. Si le pool de serveurs frontaux doit être mis à niveau vers Lync Server 2013, le SBA doit être dissocié du pool de serveurs frontaux pendant la mise à niveau du pool de serveurs frontaux. Une fois la mise à niveau du pool de serveurs frontaux effectuée, le SBA peut de nouveau être associé au pool de serveurs frontaux. Cela implique de supprimer le SBA de la topologie dans le générateur de topologie, puis de l’ajouter à nouveau au générateur de topologie. Avant de supprimer le SBA de la topologie, les utilisateurs hébergés sur le SBA doivent être déplacés vers un autre pool de serveurs frontaux. Une fois que le SBA a été rajouté à la topologie, ces utilisateurs peuvent réintégrer le SBA.

Voici un récapitulatif de ces étapes :

1.  Déplacez les utilisateurs de succursale hébergés sur le SBA sur un autre pool de serveurs frontaux.

2.  Supprimez le SBA de votre topologie pour dissocier le pool de serveurs frontaux existant en tant que serveur d’inscriptions de sauvegarde.

3.  Mettez à niveau le pool de serveurs frontaux vers Microsoft Lync Server 2013.

4.  Rajoutez le SBA à votre topologie.

5.  Associez le nouveau pool de serveurs frontaux au SBA en tant que serveur d’inscriptions de sauvegarde.

6.  Réintégrez les utilisateurs au SBA.

## Dans cette section

  - [Ajout d’un site de succursale Survivable Branch Appliance Lync Server 2013 à votre topologie](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [Ajout d’un site de succursale Survivable Branch Appliance Lync Server 2010 à votre topologie](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)


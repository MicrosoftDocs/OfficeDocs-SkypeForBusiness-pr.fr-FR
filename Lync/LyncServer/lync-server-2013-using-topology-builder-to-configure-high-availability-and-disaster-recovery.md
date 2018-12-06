---
title: "Lync Server 2013 : Ut. gén. de topo. pour conf. haute dispo. et la réc. d’urg."
TOCTitle: Utilisation du générateur de topologie pour configurer la haute disponibilité et la récupération d’urgence
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205172(v=OCS.15)
ms:contentKeyID: 49298523
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation du générateur de topologie pour configurer la haute disponibilité et la récupération d’urgence dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-06_

Effectuez les étapes suivantes dans le Générateur de topologie pour configurer la haute disponibilité et la récupération d’urgence pour le serveur de conversations permanentes.

1.  Ajoutez les bases de données miroir et les magasins SQL Server de bases de données secondaires pour l’envoi de journaux.

2.  Modifiez les propriétés du service de serveur de conversations permanentes pour :
    
    1.  activer la mise en miroir pour la base de données primaire ;
    
    2.  ajouter le magasin SQL Server miroir principal ;
    
    3.  activer la base de données pour l’envoi de journaux SQL Server ;
    
    4.  ajouter le magasin SQL Server secondaire pour l’envoi de journaux SQL Server ;
    
    5.  ajouter le miroir du magasin SQL Server pour la base de données secondaire ;
    
    6.  Publiez la topologie.


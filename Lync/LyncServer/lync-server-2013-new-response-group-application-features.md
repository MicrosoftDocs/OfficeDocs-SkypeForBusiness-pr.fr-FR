---
title: 'Lync Server 2013 : Nouvelles fonctionnalités de l’application Response Group'
TOCTitle: Nouvelles fonctionnalités de l’application Response Group
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398373(v=OCS.15)
ms:contentKeyID: 49297234
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Nouvelles fonctionnalités de l’application Response Group dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-29_

L’application Response Group vous permet de router et de placer en file d’attente des appels entrants vers des entités désignées pour des objectifs spéciaux (par exemple, un service clientèle, un service d’assistance interne ou un service d’assistance téléphonique général dédié à un service).

Les fonctionnalités suivantes de l’application Response Group constituent des nouveautés dans Lync Server 2013 :

  - **Rôle de gestionnaire**
    
    Lync Server 2013 introduit un nouveau rôle de gestionnaire Response Group. Désormais, il existe deux rôles de gestion pour les groupes Response Group : gestionnaire Response Group et administrateur Response Group. Les administrateurs Response Group peuvent toujours configurer un élément d’un groupe Response Group alors que les gestionnaires ne peuvent configurer que certains éléments, uniquement dans les groupes Response Group dont ils sont propriétaires.
    
    Cette amélioration du modèle d’administration tire parti de l’extensibilité Response Group, en particulier pour les scénarios de déploiement de grande taille.

  - **Haute disponibilité**
    
    La prise en charge de la haute disponibilité pour l’application Response Group, sous la forme d’une mise en miroir SQL Server, est activée dans le cadre de la configuration et du déploiement d’ensemble de la haute disponibilité pour Lync Server 2013. Si vous configurez la haute disponibilité et si vous perdez la connectivité au serveur principal, la fonctionnalité Response Group n’est pas affectée, car elle tire profit du serveur principal en miroir.
    
    La prise en charge de la mise en miroir SQL Server pour l’application Response Group ne peut pas être activée ou configurée individuellement en dehors de la configuration d’ensemble de la haute disponibilité pour Lync Server 2013.

  - **Récupération d’urgence**
    
    La prise en charge de la récupération d’urgence pour l’application Response Group est activée dans le cadre de la configuration et du déploiement des pools de serveurs frontaux appariés, qui font partie de la configuration d’ensemble de la récupération d’urgence pour Lync Server 2013. En outre, les applets de commande d’importation et d’exportation Response Group prennent en charge le processus de basculement vers le pool de sauvegarde, ainsi que le processus de restauration automatique vers le pool principal ou un nouveau pool. Si une panne survient dans le pool principal, les groupes Response Group peuvent faire l’objet d’un basculement vers le pool de sauvegarde, puis d’une restauration automatique vers le pool principal ou un nouveau pool une fois la panne terminée.

## Voir aussi

#### Autres ressources

[Planification des groupes Response Group dans Lync Server 2013](lync-server-2013-planning-for-response-groups.md)


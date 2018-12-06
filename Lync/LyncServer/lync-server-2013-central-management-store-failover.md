---
title: Basculement du magasin central de gestion dans Lync Server 2013
TOCTitle: Basculement du magasin central de gestion
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205376(v=OCS.15)
ms:contentKeyID: 49299324
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Basculement du magasin central de gestion dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-18_

Le magasin central de gestion contient des données de configuration relatives aux serveurs et aux services dans votre déploiement Lync 2013. Il procure un stockage robuste et schématisé des données nécessaires pour définir, configurer, maintenir, décrire et exploiter un déploiement de Lync 2013. Il valide également les données afin de garantir la cohérence de la configuration.

Chaque déploiement Lync inclut un magasin central de gestion, hébergé par le serveur principal dans un pool de serveurs frontaux.

Lorsque vous établissez établissez un couplage de pools incluant le pool hébergeant le magasin central de gestion, une base de données de sauvegarde du magasin central de gestion est configurée dans le pool de sauvegarde, et les services magasin central de gestion sont installés dans les deux pools. À tout moment, l’une des deux bases de données du magasin central de gestion est définie en tant que Réplicateur principal actif, tandis que l’autre est le Réplicateur de secours. Le contenu est répliqué par le service de sauvegarde, depuis le Réplicateur principal actif vers le Réplicateur de secours.

Durant un basculement de pool impliquant les pools hébergeant le magasin central de gestion, l’administrateur doit faire basculer le magasin central de gestion avant le basculement du pool de serveurs frontaux.

Une fois la récupération d’urgence effectuée, il n’est pas nécessaire de rebasculer le magasin central de gestion. Après la réparation, le magasin central de gestion du pool de sauvegarde d’origine peut rester Réplicateur principal actif.

Les objectifs d’ingénierie du basculement de magasin central de gestion sont les suivants : un objectif de durée de reprise (RTO) de 5 minutes et 5 minutes pour chaque objectif de point de reprise (RPO).


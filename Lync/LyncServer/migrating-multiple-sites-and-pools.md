---
title: Migration de plusieurs sites et pools
TOCTitle: Migration de plusieurs sites et pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205165(v=OCS.15)
ms:contentKeyID: 49298430
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration de plusieurs sites et pools

 

_**Dernière rubrique modifiée :** 2012-09-17_

Lync Server 2013 prend en charge les déploiements de plusieurs sites et de plusieurs pools. Vous devez tenir compte des aspects suivants dans le cadre du processus de migration de plusieurs pools de Lync Server 2010 vers Lync Server 2013 :

1.  Après avoir déployé un pool pilote Lync Server 2013, vous devez définir un sous-ensemble d’utilisateurs pilotes qui seront déplacés vers le pool Lync Server 2013 et développer une méthodologie pour la validation des fonctionnalités utilisateur. Par exemple, après avoir déplacé un utilisateur vers le pool pilote, vérifiez que sa stratégie de conférence a été déplacée vers Lync Server 2013.

2.  Après avoir déployé un serveur Edge dans le pool pilote, vous devez vérifier que les utilisateurs externes peuvent communiquer avec le pool Lync Server 2013.

3.  Après avoir transitionné les itinéraires fédérés depuis les serveurs Edge Lync Server 2010 vers les serveurs Edge Lync Server 2013 pilotes, vous devez vérifier que les utilisateurs fédérés peuvent communiquer avec le pool Lync Server 2013.

4.  Après avoir déplacé tous les utilisateurs et les objets contact non-utilisateur, vous devez vérifier que le pool Lync Server 2010 est vide.

5.  Après avoir vérifié que le pool Lync Server 2010 était vide, vous pouvez le désactiver.
    
    Pour plus d’informations sur la façon de désactiver le pool et les serveurs Lync Server 2010 hérités, reportez-vous à [Phase 8 : Mise hors service des pools hérités](phase-8-decommission-legacy-pools.md).


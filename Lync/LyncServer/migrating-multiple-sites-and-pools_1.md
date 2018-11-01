---
title: Migration de plusieurs sites et pools
TOCTitle: Migration de plusieurs sites et pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49891311
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration de plusieurs sites et pools

 

_**Dernière rubrique modifiée :** 2012-08-26_

Lync Server 2013 prend en charge les déploiements de plusieurs sites et de plusieurs pools. Vous devez tenir compte des aspects suivants dans le cadre du processus de migration de plusieurs pools de Office Communications Server 2007 R2 vers Lync Server 2013 :

1.  Après avoir déployé un pool pilote Lync Server 2013, vous devez définir un sous-ensemble d’utilisateurs pilotes qui seront déplacés vers le pool Lync Server 2013 et développer une méthodologie pour la validation des fonctionnalités utilisateur.

2.  Après avoir déployé un serveur Edge dans le pool pilote, vous devez vérifier que les utilisateurs externes peuvent communiquer avec le pool Lync Server 2013.

3.  Après avoir transitionné les itinéraires fédérés depuis les serveurs Edge Office Communications Server 2007 R2 vers les serveurs Edge Lync Server 2013 pilotes, vous devez vérifier que les utilisateurs fédérés peuvent communiquer avec le pool Lync Server 2013.

4.  Après avoir déplacé tous les utilisateurs et les objets contact non-utilisateur, vous devez vérifier que le pool Office Communications Server 2007 R2 est vide.

5.  Après avoir vérifié que le pool Office Communications Server 2007 R2 était vide, vous pouvez le désactiver.
    
    Pour plus d’informations sur la façon de désactiver le pool et les serveurs Office Communications Server 2007 R2 hérités, reportez-vous à [Phase 10 : Mise hors service d’un site hérité](phase-10-decommission-legacy-site.md).


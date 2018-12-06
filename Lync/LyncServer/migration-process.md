---
title: Processus de migration
TOCTitle: Processus de migration
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204696(v=OCS.15)
ms:contentKeyID: 49296330
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Processus de migration

 

_**Dernière rubrique modifiée :** 2012-09-17_

La migration côte à côte est la procédure de migration recommandée et prise en charge pour Lync Server 2013. Cette rubrique décrit les raisons pour lesquelles il est recommandé d’effectuer une migration côte à côte et inclut en outre des informations sur le test de coexistence.

## Migration côte à côte

Il est recommandé de pratiquer la migration côte à côte dans pratiquement toutes les migrations. Dans une migration côte à côte, vous déployez un nouveau serveur avec Lync Server 2013 au côté d’un serveur correspondant qui exécute Lync Server 2010 et vous transférez ensuite les opérations au nouveau serveur. Si vous devez par la suite restaurer le système vers Lync Server 2010, il suffit de retransférer les opérations vers les serveurs d’origine. Sachez que dans ce cas, toute nouvelle réunion planifiée avec les clients mis à niveau ne fonctionnera pas, et que les clients devront également être rétrogradés.

## Test de coexistence

Après avoir déployé Lync Server 2013 parallèlement à Lync Server 2010, le déploiement représente un état de test de coexistence de Lync Server 2013 et de Lync Server 2010. Dans cet état, il est important de tester et de vérifier que ces services sont démarrés, que chaque site peut être administré et que les clients peuvent communiquer avec les utilisateurs actuels et hérités. Avant de migrer tous les utilisateurs, il est très important de comprendre l’état de chaque déploiement et de veiller à ce que chaque déploiement soit opérationnel et fonctionne correctement. En règle générale, la phase de test de coexistence se poursuit tout au long du test pilote de Lync Server 2013. Les utilisateurs hérités sont déplacés vers Lync Server 2013 pendant un certain temps afin de veiller à la compatibilité des applications et de vérifier que les fonctions et fonctionnalités fonctionnent correctement. À l’issue du test du pilote, les utilisateurs et les applications sont déplacés vers la version de production de Lync Server 2013, et les pools et les applications hérités de Lync Server 2010 sont mis hors service.


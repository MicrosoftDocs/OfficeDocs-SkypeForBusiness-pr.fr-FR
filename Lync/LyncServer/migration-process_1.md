---
title: Processus de migration
TOCTitle: Processus de migration
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205181(v=OCS.15)
ms:contentKeyID: 49298589
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Processus de migration

 

_**Dernière rubrique modifiée :** 2012-09-24_

La migration côte à côte est la procédure de migration recommandée et prise en charge pour Lync Server 2013. Cette rubrique décrit les raisons pour lesquelles il est recommandé d’effectuer une migration côte à côte et inclut également des informations sur la coexistence.

## Migration côte à côte

Il est recommandé de pratiquer la migration côte à côte dans pratiquement toutes les migrations. Dans une migration côte à côte, vous déployez un nouveau serveur avec Lync Server 2013 au côté d’un serveur correspondant qui exécute Office Communications Server 2007 R2, et vous transférez ensuite les opérations au nouveau serveur. Si vous devez par la suite restaurer le système vers Office Communications Server 2007 R2, il suffit de retransférer les opérations vers les serveurs d’origine. Sachez que dans ce cas, toute nouvelle réunion planifiée avec les clients mis à niveau ne fonctionnera pas, et que les clients devront également être rétrogradés.

## Test de coexistence

Lorsque vous avez déployé Lync Server 2013 en parallèle avec Office Communications Server 2007 R2, la topologie représente un état de test de coexistence de Lync Server 2013 et de Office Communications Server 2007 R2. Dans cet état, il est important d’effectuer des tests et de vérifier que les services sont démarrés ; chaque site peut être administré, et les clients peuvent communiquer avec les utilisateurs actuels et hérités. Avant la migration de tous les utilisateurs, il est très important de comprendre l’état de chaque déploiement et de veiller à ce que chaque déploiement soit opérationnel et fonctionne correctement. En règle générale, la phase de test de coexistence se poursuit tout au long du test pilote de Lync Server 2013. Les utilisateurs hérités sont déplacés vers Lync Server 2013 pendant un certain temps afin de veiller à la compatibilité des applications et de vérifier que les fonctions et fonctionnalités fonctionnent correctement. À l’issue du test du pilote, les utilisateurs et les applications sont déplacés vers la version de production de Lync Server 2013, et les pools et les applications hérités de Office Communications Server 2007 R2 sont mis hors service.


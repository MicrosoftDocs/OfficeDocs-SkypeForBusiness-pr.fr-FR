---
title: 'Lync Server 2013 : Remarques sur la migration et la coexistence pour IPv6'
TOCTitle: Remarques sur la migration et la coexistence pour IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205068(v=OCS.15)
ms:contentKeyID: 49298019
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remarques sur la migration et la coexistence pour IPv6 dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-06-14_

IP version 6 (IPv6) n’est pas pris en charge sur Lync Server 2010 ou Office Communications Server. Pour des pilotes, vous pouvez tester la coexistence à double pile de Lync Server 2010 et Lync Server 2013. Nous recommandons que tous les pools d’un site central donné soient mis à niveau vers Lync Server 2013 avant d’activer IPv6 (réseau à double pile) pour les pools. Si vous devez configurer un pool uniquement pour IPv6, nous recommandons que vous configuriez un pool IPv6 uniquement dans votre environnement de laboratoire pour le test.

Les scénarios suivants sont pris en charge pendant la migration et la coexistence :

  - Pools Lync Server 2013, Lync Server 2010, et Office Communications Server 2007 R2 en mode IPv4, qui coexistent avec Lync Server 2013 en mode double pile.

  - Pool Lync Server 2013 en mode IPv6 uniquement, si le pool IPv6 uniquement est mis dans un silo.


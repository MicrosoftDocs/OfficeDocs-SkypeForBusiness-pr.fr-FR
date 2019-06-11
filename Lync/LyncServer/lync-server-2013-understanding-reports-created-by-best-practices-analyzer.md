---
title: 'Lync Server 2013: présentation des rapports créés par l’analyseur de meilleures pratiques'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding reports created by Best Practices Analyzer
ms:assetid: 1386dd6c-7f3e-4da9-905b-cef1468bf14a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591344(v=OCS.15)
ms:contentKeyID: 48183471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0903c3bafc4017d5455c188c66de3e1f2cf0b178
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-reports-created-by-best-practices-analyzer-in-lync-server-2013"></a>Présentation des rapports créés par l’analyseur de meilleures pratiques dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-10_

L’analyseur de meilleures pratiques fournit plusieurs types de rapport organisés pour faciliter l’analyse et la résolution des problèmes. L’analyseur des pratiques recommandées identifie les problèmes tels que les erreurs, avertissements et autres informations.

<div>

## <a name="reports"></a>Rapports

Vous pouvez accéder aux résultats d’une analyse en consultant chacun des rapports suivants:

  - ****   Les rapports de liste de rapports sont organisés selon des critères spécifiques. Vous pouvez organiser les résultats par classe, par gravité ou par problème. Par exemple, si vous organisez les résultats par classe, les problèmes liés aux directeurs sont inclus dans la section directeurs du rapport. Vous pouvez voir tous les problèmes ou uniquement les éléments d’information. Vous pouvez rechercher des éléments spécifiques dans un rapport de liste, tels que la mémoire. Vous pouvez également imprimer le rapport ou l’exporter.

  - ****   Les rapports d’arborescence d’arborescences sont organisés selon des règles qui sont utilisées pour exécuter la numérisation ainsi que d’autres options que vous avez spécifiées au moment de l’exécution de l’analyse. Par exemple, les problèmes liés aux règles de topologie de test sont inclus dans la section Topology Topology du rapport. Vous pouvez afficher les détails de tous les problèmes ou simplement une synthèse des problèmes. Vous pouvez rechercher des éléments spécifiques dans un rapport d’arborescence, comme la mémoire. Vous pouvez également imprimer le rapport ou l’exporter.

  - **D’autres rapports**   dans d’autres rapports incluent le journal au moment de l’exécution des tâches incluses dans l’analyse. Vous pouvez effectuer une recherche dans les éléments d’autres rapports pour des éléments spécifiques, tels que la mémoire. Vous pouvez également imprimer le rapport ou l’exporter.

</div>

<div>

## <a name="issues"></a>Aspects

Les rapports générés par meilleurs pratiques Analyzer indiquent des problèmes spécifiques identifiés lors de l’analyse de votre environnement, notamment les types de problèmes suivants:

  - **Erreurs**   problèmes critiques qui nécessitent d’apporter des modifications à votre environnement. Par exemple, si les composants principaux de Lync Server 2013 ne sont pas installés, une erreur est journalisée.
    
    Les problèmes classés comme erreurs sont identifiés dans le rapport par un symbole X rouge. Les erreurs s’affichent dans l’onglet **tous les problèmes** de l’affichage **rapports de liste** , puis dans l’onglet **affichage détaillé** et l’onglet **vue récapitulative** de l’affichage **rapports d’arborescence** . Si vous ne souhaitez pas afficher d’erreur spécifique dans un rapport, vous pouvez spécifier que l’erreur ne s’affiche pas pour une instance unique ou pour toutes les instances de cette erreur dans le rapport. Le message d’erreur s’affiche uniquement sous l’onglet **éléments cachés** de l' **autre mode rapports** , sauf si vous modifiez ce paramètre et que l’erreur s’affiche dans le rapport.

  - **Alertes**   qui ne sont pas cohérentes lors de l’implémentation d’une bonne pratique. Cela risque de ne pas révéler la nécessité d’un changement dans votre environnement. Le problème peut être lié à un paramètre spécifique que vous n’avez pas besoin de modifier. Par exemple, les services non démarrés sur un serveur sont enregistrés en tant qu’avertissements.
    
    Les problèmes classés comme avertissements sont identifiés dans le rapport par un symbole d’avertissement jaune triangulaire. Les avertissements sont affichés dans l’onglet **tous les problèmes** de l’affichage **rapports de liste** , ainsi que dans les onglets **affichage détaillé** et **affichage de synthèse** de l’affichage rapports d' **arborescence** . Si vous ne souhaitez pas afficher d’erreur spécifique dans un rapport, vous pouvez spécifier que l’erreur ne s’affiche pas pour une instance unique ou pour toutes les instances de cette erreur dans le rapport. Le message d’avertissement s’affiche uniquement sous l’onglet **éléments cachés** de l' **autre mode rapports** , sauf si vous modifiez le paramètre et que l’avertissement s’affiche dans le rapport.

  - **Les informations**   incluent tous les problèmes qui ne sont pas classés comme erreurs ou avertissements. Par exemple, le nombre d’objets serveur Lync Server 2013 Standard Edition dans les services de domaine Active Directory est considéré comme un problème d’information.
    
    Les problèmes liés aux informations s’affichent dans l’onglet **tous les problèmes** de l’affichage **rapports de liste** , puis sous l’onglet **affichage détaillé** de l’affichage **rapports d’arborescence** .

L’analyseur de meilleures pratiques pour Lync Server 2013 n’apporte pas de modifications à votre environnement pour résoudre les problèmes. L’analyse détecte uniquement les problèmes potentiels et fournit des rapports contenant des informations sur la résolution de chaque problème.

Si vous cliquez sur un problème, une explication et certaines options apparaissent pour des problèmes spécifiques. Ensuite, vous pouvez effectuer l’une des opérations suivantes:

  - Recherchez des informations plus détaillées sur le problème et comment le résoudre.

  - Ne plus afficher les problèmes dans les rapports:
    
      - Ne plus afficher de problèmes pour l’instance sélectionnée.
    
      - Ne plus afficher de problèmes pour toutes les instances de ce problème.
    
    Pour afficher les problèmes que vous avez interrompus dans les rapports, accédez à l’onglet **éléments cachés** de l’affichage **autres rapports** . À partir de là, vous pouvez spécifier l’affichage des problèmes dans les rapports.

Pour plus d’informations sur la résolution des problèmes spécifiques, voir [analyser et résoudre des problèmes identifiés par l’analyseur de meilleures pratiques dans Lync Server 2013](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>


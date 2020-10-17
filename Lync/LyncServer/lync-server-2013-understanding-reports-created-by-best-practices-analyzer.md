---
title: 'Lync Server 2013 : présentation des rapports créés par Best Practices Analyzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding reports created by Best Practices Analyzer
ms:assetid: 1386dd6c-7f3e-4da9-905b-cef1468bf14a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591344(v=OCS.15)
ms:contentKeyID: 48183471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24699e685b58c718f6b67306c1eaa2d6974c87c5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527721"
---
# <a name="understanding-reports-created-by-best-practices-analyzer-in-lync-server-2013"></a>Présentation des rapports créés par Best Practices Analyzer dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-10_

Best Practices Analyzer offre plusieurs types de rapports qui sont organisés pour faciliter l’analyse et la résolution des problèmes. Best Practices Analyzer identifie les problèmes, tels que les erreurs, les avertissements et d’autres informations.

<div>

## <a name="reports"></a>Rapports

Vous pouvez accéder aux résultats d’une analyse en visualisant chacun des rapports suivants :

  - **Répertorier les rapports**     Les rapports de liste sont organisés selon des critères spécifiques. Vous pouvez classer les résultats par classe, niveau de gravité ou type de problème. Par exemple, si vous classez les résultats par classe, les problèmes liés aux directeurs sont inclus sous la section Directeurs du rapport. Vous pouvez afficher tous les problèmes ou seulement les éléments d’information. Vous pouvez rechercher des éléments spécifiques dans un rapport de liste, par exemple les problèmes ayant trait à la mémoire. Vous pouvez également imprimer le rapport ou l’exporter.

  - **Rapports**     d’arborescence Les rapports d’arborescence sont organisés selon les règles utilisées pour exécuter l’analyse et d’autres options que vous avez spécifiées au moment de l’exécution de l’analyse. Par exemple, les problèmes liés aux règles Topologie de test sont inclus sous la section Topologie de test du rapport. Vous pouvez afficher les détails de tous les problèmes ou seulement un résumé des problèmes. Vous pouvez rechercher des éléments spécifiques dans un rapport d’arborescence, par exemple les problèmes ayant trait à la mémoire. Vous pouvez également imprimer le rapport ou l’exporter.

  - **Autres rapports**     Les éléments d’autres rapports incluent le journal d’exécution des tâches qui ont été incluses dans l’analyse. Vous pouvez rechercher des éléments spécifiques dans les autres rapports, par exemple les problèmes ayant trait à la mémoire. Vous pouvez également imprimer le rapport ou l’exporter.

</div>

<div>

## <a name="issues"></a>Problèmes

Les rapports générés par Best Practices Analyzer indiquent les problèmes spécifiques qui sont identifiés au cours de l’analyse de votre environnement, notamment les types de problèmes suivants :

  - **Erreurs**     Problèmes critiques nécessitant une modification dans votre environnement. Par exemple, si les composants principaux de Lync Server 2013 ne sont pas installés, une erreur est enregistrée.

    Les problèmes classés comme des erreurs sont identifiés dans le rapport par un symbole représentant un X rouge. Les erreurs s’affichent sous l’onglet **Tous les problèmes** de la vue **Rapports de liste**, ainsi que sous les onglets **Affichage détaillé** et **Affichage de synthèse** de l’affichage **Rapports d’arborescence**. Si vous ne souhaitez pas qu’une erreur en particulier apparaisse dans un rapport, vous pouvez faire en sorte qu’une seule instance ou que toutes les instances de l’erreur ne s’affichent pas dans le rapport. L’erreur apparaît ensuite uniquement sous l’onglet **Éléments masqués** de l’affichage **Autres rapports**, sauf si vous modifiez le paramètre et spécifiez que l’erreur doit s’afficher dans le rapport.

  - **Avertissements**     Problèmes non cohérents avec l’implémentation d’une meilleure pratique. Ceci peut ou non indiquer la nécessité de modifier votre environnement. Le problème peut être un problème connu lié à un paramètre spécifique que vous n’avez pas besoin de changer. Par exemple, les services qui ne sont pas démarrés sur un serveur sont consignés sous forme d’avertissements.

    Les problèmes classés comme avertissements sont identifiés dans le rapport par un symbole triangulaire jaune. Les avertissements s’affichent sous l’onglet **Tous les problèmes** de l’affichage **Rapports de liste**, ainsi que sous les onglets **Affichage détaillé** et **Affichage de synthèse** de l’affichage **Rapports d’arborescence**. Si vous ne souhaitez pas qu’un avertissement en particulier apparaisse dans un rapport, vous pouvez faire en sorte qu’une seule instance ou que toutes les instances de l’avertissement ne s’affichent pas dans le rapport. L’avertissement apparaît ensuite uniquement sous l’onglet**Éléments masqués** de l’affichage **Autres rapports**, sauf si vous modifiez le paramètre et spécifiez que l’avertissement doit s’afficher dans le rapport.

  - **Informations**     Inclut tous les problèmes qui ne sont pas considérés comme des erreurs ou des avertissements. Par exemple, le nombre d’objets serveur Lync Server 2013 Standard Edition dans les services de domaine Active Directory est classé comme un problème d’information.

    Les problèmes d’information s’affichent sous l’onglet **Tous les problèmes** de l’affichage **Rapports de liste** et sous l’onglet **Affichage détaillé** de l’affichage **Rapports d’arborescence**.

Lync Server 2013, Best Practices Analyzer ne modifie pas votre environnement pour résoudre les problèmes. L’analyse détecte simplement les problèmes potentiels et fournit des rapports offrant des informations sur la résolution de chaque problème.

Si vous cliquez sur un problème, une explication et certaines options apparaissent pour des problèmes donnés. Vous pouvez ensuite procéder comme suit :

  - Recherchez plus d’informations détaillées sur le problème et sur sa résolution.

  - Ne plus afficher les problèmes dans les rapports :

      - Arrêtez d’afficher les problèmes liés à l’instance sélectionnée.

      - Arrêtez d’afficher les problèmes liés à toutes les instances du problème.

    Pour voir les problèmes que vous avez arrêté d’afficher dans les rapports, accédez à l’onglet **Éléments masqués** de l’affichage **Autres rapports**. Ensuite, vous pouvez recommencer à afficher les problèmes dans les rapports.

Pour plus d’informations sur la résolution des problèmes spécifiques, voir [analyse et résolution des problèmes identifiés par Best Practices Analyzer dans Lync Server 2013](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

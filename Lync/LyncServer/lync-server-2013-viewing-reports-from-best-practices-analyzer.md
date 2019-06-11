---
title: 'Lync Server 2013: affichage de rapports issus de l’analyseur de recommandations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing reports from Best Practices Analyzer
ms:assetid: 7217a47b-36b1-4923-81ea-df754cff29bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg607690(v=OCS.15)
ms:contentKeyID: 48184465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb2c229d683ecd0dcf4fee94b456514527226152
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a>Affichage de rapports issus de l’analyseur de meilleures pratiques dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-21_

Lorsque vous utilisez l’outil d’analyse des pratiques recommandées pour analyser votre environnement, vous spécifiez un nom pour l’analyse. Une fois que le meilleur analyseur effectue une analyse, il stocke les résultats de l’analyse dans les rapports et les enregistre sous le nom de la numérisation. À l’issue de l’analyse, vous pouvez afficher les rapports générés pour cette analyse en cliquant sur **afficher un rapport de cette analyse des meilleures pratiques** directement à partir de la page **analyse terminée** . Vous pouvez également afficher les rapports à partir de cette analyse ou des analyses précédentes ultérieurement. Vous pouvez afficher les rapports sur l’ordinateur local sur lequel l’analyse a été exécutée, importer les résultats de l’analyse à partir d’un autre ordinateur ou exporter les résultats de l’analyse pour afficher les rapports sur un autre ordinateur sur lequel le système d’analyse des recommandations est installé.

Les résultats de l’analyse sont présentés dans les types de rapports suivants:

  - Rapports de liste

  - Rapports d’arborescence

  - Autres rapports

Ces rapports incluent des erreurs, des avertissements et d’autres informations. Pour plus d’informations sur chacun de ces types de rapports et de problèmes, voir [Présentation des rapports créés par l’analyseur de meilleures pratiques dans Lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).

Utilisez la procédure suivante pour afficher les résultats de l’analyse déjà générés par les meilleurs analyseurs.

<div>

## <a name="to-view-reports-from-a-previous-scan"></a>Pour afficher les rapports d’une analyse précédente

1.  Connectez-vous à un ordinateur sur lequel le système d’analyse des recommandations est installé à l’aide d’un compte membre du compte d’utilisateur local.
    
    > [!NOTE]  
    > Vous pouvez afficher les résultats d’une analyse à l’aide d’un compte membre du groupe Administrateurs local, mais vous ne pouvez pas exécuter une analyse sauf si vous disposez des droits d’utilisateur et des autorisations appropriés. Pour plus d’informations, consultez la section <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">appartenances aux groupes et conditions d’utilisation requise pour l’analyseur de meilleures pratiques dans Lync Server 2013</A>.

2.  Cliquez sur **Démarrer**, pointez sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis cliquez sur **recommandations Analyzer**.

3.  Dans l’écran d' **Accueil** , cliquez sur **sélectionnez les résultats de l’analyse à afficher**.

4.  Dans la page Sélectionner les recommandations **à afficher** , effectuez l’une des opérations suivantes:
    
      - Pour afficher les rapports de la liste des résultats d’une analyse stockée en local, cliquez sur le nom de l’analyse, puis cliquez sur **afficher un rapport de cette analyse**.
        
        > [!NOTE]  
        > L’outil d’analyse des pratiques recommandées crée la liste des fichiers locaux &lt;à&gt;\\partir du dossier\\&lt;lecteur_système&gt;documents and Settings utilisateur \Application Data\Microsoft\RtcBPA.
    
      - Pour afficher les rapports sur les résultats d’une analyse qui sont stockés à un autre emplacement, cliquez sur **Importer la numérisation**, recherchez le fichier contenant les résultats de l’analyse, puis cliquez sur **ouvrir**.
        
        > [!NOTE]  
        > Si la version de l’analyseur de compatibilité des applications de cet ordinateur ne correspond pas à la version utilisée pour collecter les données dans le fichier importé, l’outil sur votre ordinateur peut analyser de nouveau le fichier après son importation.

5.  Dans la page **afficher le rapport** des recommandations, effectuez l’une des opérations suivantes:
    
      - Pour afficher les rapports dans une liste organisée par composant serveur, cliquez sur **rapports de liste**, puis sur l’onglet **tous les problèmes** ou **éléments d’information** .
    
      - Pour afficher les rapports sous forme de liste hiérarchique organisée par type de résultat, cliquez sur **rapports d’arborescence**, puis sur l’onglet **affichage détaillé** ou **affichage de synthèse** .
    
      - Pour afficher d’autres rapports, cliquez sur **autres rapports**.
    
    > [!NOTE]  
    > Pour plus d’informations sur les meilleurs rapports d’analyseurs et les problèmes qu’ils identifient, voir <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">afficher et utiliser les rapports créés par meilleurs analyseurs dans Lync Server 2013</A> et <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analyser et résoudre les problèmes identifiés par les meilleures pratiques. Analyzer dans Lync Server 2013</A>.

</div>

</div>

</div>

</div>

</div>


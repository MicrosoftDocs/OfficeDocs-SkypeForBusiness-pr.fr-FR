---
title: 'Lync Server 2013 : affichage des rapports de Best Practices Analyzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing reports from Best Practices Analyzer
ms:assetid: 7217a47b-36b1-4923-81ea-df754cff29bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg607690(v=OCS.15)
ms:contentKeyID: 48184465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93ce3e013f5c0578c78db3ceee8ab1d65481efbb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211109"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a>Affichage des rapports de Best Practices Analyzer dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Lorsque vous utilisez Best Practices Analyzer pour analyser votre environnement, vous spécifiez un nom pour l’analyse. Une fois que Best Practices Analyzer a terminé une analyse, les résultats sont stockés dans des rapports et enregistrés sous le nom de cette analyse. Dès la fin de l’analyse, vous pouvez consulter les rapports correspondants générés en cliquant sur **Afficher le rapport de cette analyse** directement depuis la page **Analyse terminée**. Vous pouvez également consulter les rapports de cette analyse ou d’analyses précédentes ultérieurement. Vous pouvez consulter les rapports sur l’ordinateur local sur lequel l’analyse a été exécutée, importer des résultats d’analyse depuis un autre ordinateur ou en exporter afin de consulter les rapports sur un autre ordinateur sur lequel Best Practices Analyzer est installé.

Les résultats d’analyse sont présentés dans les types de rapports suivants :

  - Rapports de liste

  - Rapports d’arborescence

  - Autres rapports

Ces rapports incluent les erreurs, les avertissements et d’autres informations. Pour plus d’informations sur chacun de ces types de rapports et de problèmes, voir [Présentation des rapports créés par Best Practices Analyzer dans Lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).

Utilisez la procédure suivante pour afficher les résultats d’analyse précédemment générés par Best Practices Analyzer.

<div>

## <a name="to-view-reports-from-a-previous-scan"></a>Pour afficher les rapports d’une analyse précédente

1.  Ouvrez une session sur un ordinateur sur lequel Best Practices Analyzer est installé à l’aide d’un compte membre du compte d’utilisateur local.
    
    > [!NOTE]  
    > Vous pouvez afficher les résultats d’une analyse à l’aide d’un compte membre du groupe Administrateurs local, mais vous ne pouvez pas exécuter une analyse si vous ne possédez pas les droits d’utilisateur ou autorisations appropriés. Pour plus d’informations, reportez-vous aux <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">appartenances aux groupes et aux droits des utilisateurs pour Best Practices Analyzer dans Lync Server 2013</A>.

2.  Cliquez sur **Démarrer**, pointez sur **tous les programmes**, cliquez sur **Microsoft Lync Server 2013**, puis sur **Best Practices Analyzer**.

3.  Dans l’écran **Bienvenue**, cliquez sur **Sélectionner les résultats d’analyse à afficher**.

4.  Dans la page **Sélectionner une analyse à afficher**, effectuez l’une des opérations suivantes :
    
      - Pour afficher des rapports figurant dans la liste des résultats d’analyse stockés localement, cliquez sur le nom de l’analyse, puis sur **Afficher un rapport de cette analyse**.
        
        > [!NOTE]  
        > Best Practices Analyzer crée la liste des fichiers locaux à partir du dossier &lt;lecteur_système&gt;\\documents and\\&lt;Settings&gt;utilisateur \Application Data\Microsoft\RtcBPA.
    
      - Pour afficher les rapports liés à des résultats d’analyse stockés à un autre emplacement, cliquez sur **Importer analyse**, localisez le fichier contenant les résultats d’analyse, puis cliquez sur **Ouvrir**.
        
        > [!NOTE]  
        > Si la version de Best Practices Analyzer disponible sur cet ordinateur ne correspond pas à celle qui a été utilisée pour collecter les données dans le fichier importé, l’outil disponible sur votre ordinateur risque d’analyser de nouveau le fichier, après son importation.

5.  Dans la page **Afficher le rapport Best Practices**, effectuez l’une des opérations suivantes :
    
      - Pour afficher les rapports dans une liste organisée par composant serveur, cliquez sur **Rapports de liste**, puis cliquez sur l’onglet **Tous les problèmes** ou sur l’onglet **Éléments d’information**.
    
      - Pour afficher les rapports sous forme de liste hiérarchique organisée par type de résultat, cliquez sur **Rapports d’arborescence**, puis cliquez sur l’onglet **Affichage détaillé** ou sur l’onglet **Affichage de synthèse**.
    
      - Pour afficher d’autres rapports, cliquez sur **Autres rapports**.
    
    > [!NOTE]  
    > Pour plus d’informations sur les rapports de Best Practices Analyzer et les problèmes qu’ils identifient, voir <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">affichage et utilisation des rapports créés par Best Practices Analyzer dans Lync server 2013</A> et <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analyse et résolution des problèmes identifiés par Best Practices Analyzer dans Lync Server 2013</A>.

</div>

</div>

</div>

</div>

</div>


---
title: 'Lync Server 2013 : affichage des rapports de Best Practices Analyzer'
description: 'Lync Server 2013 : affichage des rapports de Best Practices Analyzer.'
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
ms.openlocfilehash: 44e0f1ed8d48f5c8fb7e35187ecdda2778091407
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542360"
---
# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="af336-103">Affichage des rapports de Best Practices Analyzer dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af336-103">Viewing reports from Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af336-104">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="af336-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="af336-p101">Lorsque vous utilisez Best Practices Analyzer pour analyser votre environnement, vous spécifiez un nom pour l’analyse. Une fois que Best Practices Analyzer a terminé une analyse, les résultats sont stockés dans des rapports et enregistrés sous le nom de cette analyse. Dès la fin de l’analyse, vous pouvez consulter les rapports correspondants générés en cliquant sur **Afficher le rapport de cette analyse** directement depuis la page **Analyse terminée**. Vous pouvez également consulter les rapports de cette analyse ou d’analyses précédentes ultérieurement. Vous pouvez consulter les rapports sur l’ordinateur local sur lequel l’analyse a été exécutée, importer des résultats d’analyse depuis un autre ordinateur ou en exporter afin de consulter les rapports sur un autre ordinateur sur lequel Best Practices Analyzer est installé.</span><span class="sxs-lookup"><span data-stu-id="af336-p101">When you use Best Practices Analyzer to scan your environment, you specify a name for the scan. After Best Practices Analyzer completes a scan, it stores the scan results in reports and saves them under the name of the scan. Upon completion of the scan, you can view the reports generated for that scan by clicking **View a report of this Best Practices scan** directly from the **Scanning Completed** page. You can also view the reports from that scan or previous scans at a later time. You can view reports on the local computer on which the scan was run, import scan results from another computer, or export scan results to view the reports on another computer on which Best Practices Analyzer is installed.</span></span>

<span data-ttu-id="af336-110">Les résultats d’analyse sont présentés dans les types de rapports suivants :</span><span class="sxs-lookup"><span data-stu-id="af336-110">Scan results are presented in the following types of reports:</span></span>

  - <span data-ttu-id="af336-111">Rapports de liste</span><span class="sxs-lookup"><span data-stu-id="af336-111">List reports</span></span>

  - <span data-ttu-id="af336-112">Rapports d’arborescence</span><span class="sxs-lookup"><span data-stu-id="af336-112">Tree reports</span></span>

  - <span data-ttu-id="af336-113">Autres rapports</span><span class="sxs-lookup"><span data-stu-id="af336-113">Other reports</span></span>

<span data-ttu-id="af336-114">Ces rapports incluent les erreurs, les avertissements et d’autres informations.</span><span class="sxs-lookup"><span data-stu-id="af336-114">These reports include errors, warnings, and other information.</span></span> <span data-ttu-id="af336-115">Pour plus d’informations sur chacun de ces types de rapports et de problèmes, voir [Présentation des rapports créés par Best Practices Analyzer dans Lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="af336-115">For details about each of these types of reports and issues, see [Understanding reports created by Best Practices Analyzer in Lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).</span></span>

<span data-ttu-id="af336-116">Utilisez la procédure suivante pour afficher les résultats d’analyse précédemment générés par Best Practices Analyzer.</span><span class="sxs-lookup"><span data-stu-id="af336-116">Use the following procedure to view scan results previously generated by Best Practices Analyzer.</span></span>

<div>

## <a name="to-view-reports-from-a-previous-scan"></a><span data-ttu-id="af336-117">Pour afficher les rapports d’une analyse précédente</span><span class="sxs-lookup"><span data-stu-id="af336-117">To view reports from a previous scan</span></span>

1.  <span data-ttu-id="af336-118">Ouvrez une session sur un ordinateur sur lequel Best Practices Analyzer est installé à l’aide d’un compte membre du compte d’utilisateur local.</span><span class="sxs-lookup"><span data-stu-id="af336-118">Log on to a computer on which Best Practices Analyzer is installed using an account that is a member of the local User account.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="af336-119">Vous pouvez afficher les résultats d’une analyse à l’aide d’un compte membre du groupe Administrateurs local, mais vous ne pouvez pas exécuter une analyse si vous ne possédez pas les droits d’utilisateur ou autorisations appropriés.</span><span class="sxs-lookup"><span data-stu-id="af336-119">You can view the results of a scan using an account that is a member of the local Administrators group, but you cannot run a scan unless you have appropriate user rights and permissions.</span></span> <span data-ttu-id="af336-120">Pour plus d’informations, reportez-vous aux <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">appartenances aux groupes et aux droits des utilisateurs pour Best Practices Analyzer dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="af336-120">For details, see <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</A>.</span></span>

2.  <span data-ttu-id="af336-121">Cliquez sur **Démarrer**, pointez sur **tous les programmes**, cliquez sur **Microsoft Lync Server 2013**, puis sur **Best Practices Analyzer**.</span><span class="sxs-lookup"><span data-stu-id="af336-121">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="af336-122">Dans l’écran **Bienvenue**, cliquez sur **Sélectionner les résultats d’analyse à afficher**.</span><span class="sxs-lookup"><span data-stu-id="af336-122">On the **Welcome** screen, click **Select the scan results to view**.</span></span>

4.  <span data-ttu-id="af336-123">Dans la page **Sélectionner une analyse à afficher**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="af336-123">On the **Select a Best Practices Scan to View** page, do one of the following:</span></span>
    
      - <span data-ttu-id="af336-124">Pour afficher des rapports figurant dans la liste des résultats d’analyse stockés localement, cliquez sur le nom de l’analyse, puis sur **Afficher un rapport de cette analyse**.</span><span class="sxs-lookup"><span data-stu-id="af336-124">To view reports from the list of locally stored scan results, click the name of scan, and then click **View a report of this scan**.</span></span>
        
        > [!NOTE]  
        > <span data-ttu-id="af336-125">Best Practices Analyzer crée la liste des fichiers locaux à partir du dossier &lt; lecteur_système &gt; \\ Documents and Settings \\ &lt; utilisateur &gt; \Application Data\Microsoft\RtcBPA.</span><span class="sxs-lookup"><span data-stu-id="af336-125">The Best Practices Analyzer creates the list of local files from the folder &lt;systemDrive&gt;\\Documents and Settings\\&lt;user&gt;\Application Data\Microsoft\RtcBPA.</span></span>
    
      - <span data-ttu-id="af336-126">Pour afficher les rapports liés à des résultats d’analyse stockés à un autre emplacement, cliquez sur **Importer analyse**, localisez le fichier contenant les résultats d’analyse, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="af336-126">To view reports for results of a scan that are stored at another location, click **Import scan**, locate the file containing the scan results, and then click **Open**.</span></span>
        
        > [!NOTE]  
        > <span data-ttu-id="af336-127">Si la version de Best Practices Analyzer disponible sur cet ordinateur ne correspond pas à celle qui a été utilisée pour collecter les données dans le fichier importé, l’outil disponible sur votre ordinateur risque d’analyser de nouveau le fichier, après son importation.</span><span class="sxs-lookup"><span data-stu-id="af336-127">If the version of Best Practices Analyzer on this computer does not match the version that was used to collect the data in the imported file, the tool on your computer might analyze the file again, after it is imported.</span></span>

5.  <span data-ttu-id="af336-128">Dans la page **Afficher le rapport Best Practices**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="af336-128">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="af336-129">Pour afficher les rapports dans une liste organisée par composant serveur, cliquez sur **Rapports de liste**, puis cliquez sur l’onglet **Tous les problèmes** ou sur l’onglet **Éléments d’information**.</span><span class="sxs-lookup"><span data-stu-id="af336-129">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="af336-130">Pour afficher les rapports sous forme de liste hiérarchique organisée par type de résultat, cliquez sur **Rapports d’arborescence**, puis cliquez sur l’onglet **Affichage détaillé** ou sur l’onglet **Affichage de synthèse**.</span><span class="sxs-lookup"><span data-stu-id="af336-130">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="af336-131">Pour afficher d’autres rapports, cliquez sur **Autres rapports**.</span><span class="sxs-lookup"><span data-stu-id="af336-131">To view other reports, click **Other Reports**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="af336-132">Pour plus d’informations sur les rapports de Best Practices Analyzer et les problèmes qu’ils identifient, voir <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">affichage et utilisation des rapports créés par Best Practices Analyzer dans Lync server 2013</A> et <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analyse et résolution des problèmes identifiés par Best Practices Analyzer dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="af336-132">For details about the Best Practices Analyzer reports and the issues that they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

</div>

</div>

</div>

</div>

</div>


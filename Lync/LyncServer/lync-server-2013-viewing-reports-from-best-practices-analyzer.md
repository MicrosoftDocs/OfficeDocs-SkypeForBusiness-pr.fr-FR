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

# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="94522-102">Affichage de rapports issus de l’analyseur de meilleures pratiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94522-102">Viewing reports from Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94522-103">_**Dernière modification de la rubrique:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="94522-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="94522-104">Lorsque vous utilisez l’outil d’analyse des pratiques recommandées pour analyser votre environnement, vous spécifiez un nom pour l’analyse.</span><span class="sxs-lookup"><span data-stu-id="94522-104">When you use Best Practices Analyzer to scan your environment, you specify a name for the scan.</span></span> <span data-ttu-id="94522-105">Une fois que le meilleur analyseur effectue une analyse, il stocke les résultats de l’analyse dans les rapports et les enregistre sous le nom de la numérisation.</span><span class="sxs-lookup"><span data-stu-id="94522-105">After Best Practices Analyzer completes a scan, it stores the scan results in reports and saves them under the name of the scan.</span></span> <span data-ttu-id="94522-106">À l’issue de l’analyse, vous pouvez afficher les rapports générés pour cette analyse en cliquant sur **afficher un rapport de cette analyse des meilleures pratiques** directement à partir de la page **analyse terminée** .</span><span class="sxs-lookup"><span data-stu-id="94522-106">Upon completion of the scan, you can view the reports generated for that scan by clicking **View a report of this Best Practices scan** directly from the **Scanning Completed** page.</span></span> <span data-ttu-id="94522-107">Vous pouvez également afficher les rapports à partir de cette analyse ou des analyses précédentes ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="94522-107">You can also view the reports from that scan or previous scans at a later time.</span></span> <span data-ttu-id="94522-108">Vous pouvez afficher les rapports sur l’ordinateur local sur lequel l’analyse a été exécutée, importer les résultats de l’analyse à partir d’un autre ordinateur ou exporter les résultats de l’analyse pour afficher les rapports sur un autre ordinateur sur lequel le système d’analyse des recommandations est installé.</span><span class="sxs-lookup"><span data-stu-id="94522-108">You can view reports on the local computer on which the scan was run, import scan results from another computer, or export scan results to view the reports on another computer on which Best Practices Analyzer is installed.</span></span>

<span data-ttu-id="94522-109">Les résultats de l’analyse sont présentés dans les types de rapports suivants:</span><span class="sxs-lookup"><span data-stu-id="94522-109">Scan results are presented in the following types of reports:</span></span>

  - <span data-ttu-id="94522-110">Rapports de liste</span><span class="sxs-lookup"><span data-stu-id="94522-110">List reports</span></span>

  - <span data-ttu-id="94522-111">Rapports d’arborescence</span><span class="sxs-lookup"><span data-stu-id="94522-111">Tree reports</span></span>

  - <span data-ttu-id="94522-112">Autres rapports</span><span class="sxs-lookup"><span data-stu-id="94522-112">Other reports</span></span>

<span data-ttu-id="94522-113">Ces rapports incluent des erreurs, des avertissements et d’autres informations.</span><span class="sxs-lookup"><span data-stu-id="94522-113">These reports include errors, warnings, and other information.</span></span> <span data-ttu-id="94522-114">Pour plus d’informations sur chacun de ces types de rapports et de problèmes, voir [Présentation des rapports créés par l’analyseur de meilleures pratiques dans Lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="94522-114">For details about each of these types of reports and issues, see [Understanding reports created by Best Practices Analyzer in Lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).</span></span>

<span data-ttu-id="94522-115">Utilisez la procédure suivante pour afficher les résultats de l’analyse déjà générés par les meilleurs analyseurs.</span><span class="sxs-lookup"><span data-stu-id="94522-115">Use the following procedure to view scan results previously generated by Best Practices Analyzer.</span></span>

<div>

## <a name="to-view-reports-from-a-previous-scan"></a><span data-ttu-id="94522-116">Pour afficher les rapports d’une analyse précédente</span><span class="sxs-lookup"><span data-stu-id="94522-116">To view reports from a previous scan</span></span>

1.  <span data-ttu-id="94522-117">Connectez-vous à un ordinateur sur lequel le système d’analyse des recommandations est installé à l’aide d’un compte membre du compte d’utilisateur local.</span><span class="sxs-lookup"><span data-stu-id="94522-117">Log on to a computer on which Best Practices Analyzer is installed using an account that is a member of the local User account.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="94522-118">Vous pouvez afficher les résultats d’une analyse à l’aide d’un compte membre du groupe Administrateurs local, mais vous ne pouvez pas exécuter une analyse sauf si vous disposez des droits d’utilisateur et des autorisations appropriés.</span><span class="sxs-lookup"><span data-stu-id="94522-118">You can view the results of a scan using an account that is a member of the local Administrators group, but you cannot run a scan unless you have appropriate user rights and permissions.</span></span> <span data-ttu-id="94522-119">Pour plus d’informations, consultez la section <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">appartenances aux groupes et conditions d’utilisation requise pour l’analyseur de meilleures pratiques dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="94522-119">For details, see <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</A>.</span></span>

2.  <span data-ttu-id="94522-120">Cliquez sur **Démarrer**, pointez sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis cliquez sur **recommandations Analyzer**.</span><span class="sxs-lookup"><span data-stu-id="94522-120">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="94522-121">Dans l’écran d' **Accueil** , cliquez sur **sélectionnez les résultats de l’analyse à afficher**.</span><span class="sxs-lookup"><span data-stu-id="94522-121">On the **Welcome** screen, click **Select the scan results to view**.</span></span>

4.  <span data-ttu-id="94522-122">Dans la page Sélectionner les recommandations **à afficher** , effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="94522-122">On the **Select a Best Practices Scan to View** page, do one of the following:</span></span>
    
      - <span data-ttu-id="94522-123">Pour afficher les rapports de la liste des résultats d’une analyse stockée en local, cliquez sur le nom de l’analyse, puis cliquez sur **afficher un rapport de cette analyse**.</span><span class="sxs-lookup"><span data-stu-id="94522-123">To view reports from the list of locally stored scan results, click the name of scan, and then click **View a report of this scan**.</span></span>
        
        > [!NOTE]  
        > <span data-ttu-id="94522-124">L’outil d’analyse des pratiques recommandées crée la liste des fichiers locaux &lt;à&gt;\\partir du dossier\\&lt;lecteur_système&gt;documents and Settings utilisateur \Application Data\Microsoft\RtcBPA.</span><span class="sxs-lookup"><span data-stu-id="94522-124">The Best Practices Analyzer creates the list of local files from the folder &lt;systemDrive&gt;\\Documents and Settings\\&lt;user&gt;\Application Data\Microsoft\RtcBPA.</span></span>
    
      - <span data-ttu-id="94522-125">Pour afficher les rapports sur les résultats d’une analyse qui sont stockés à un autre emplacement, cliquez sur **Importer la numérisation**, recherchez le fichier contenant les résultats de l’analyse, puis cliquez sur **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="94522-125">To view reports for results of a scan that are stored at another location, click **Import scan**, locate the file containing the scan results, and then click **Open**.</span></span>
        
        > [!NOTE]  
        > <span data-ttu-id="94522-126">Si la version de l’analyseur de compatibilité des applications de cet ordinateur ne correspond pas à la version utilisée pour collecter les données dans le fichier importé, l’outil sur votre ordinateur peut analyser de nouveau le fichier après son importation.</span><span class="sxs-lookup"><span data-stu-id="94522-126">If the version of Best Practices Analyzer on this computer does not match the version that was used to collect the data in the imported file, the tool on your computer might analyze the file again, after it is imported.</span></span>

5.  <span data-ttu-id="94522-127">Dans la page **afficher le rapport** des recommandations, effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="94522-127">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="94522-128">Pour afficher les rapports dans une liste organisée par composant serveur, cliquez sur **rapports de liste**, puis sur l’onglet **tous les problèmes** ou **éléments d’information** .</span><span class="sxs-lookup"><span data-stu-id="94522-128">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="94522-129">Pour afficher les rapports sous forme de liste hiérarchique organisée par type de résultat, cliquez sur **rapports d’arborescence**, puis sur l’onglet **affichage détaillé** ou **affichage de synthèse** .</span><span class="sxs-lookup"><span data-stu-id="94522-129">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="94522-130">Pour afficher d’autres rapports, cliquez sur **autres rapports**.</span><span class="sxs-lookup"><span data-stu-id="94522-130">To view other reports, click **Other Reports**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="94522-131">Pour plus d’informations sur les meilleurs rapports d’analyseurs et les problèmes qu’ils identifient, voir <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">afficher et utiliser les rapports créés par meilleurs analyseurs dans Lync Server 2013</A> et <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analyser et résoudre les problèmes identifiés par les meilleures pratiques. Analyzer dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="94522-131">For details about the Best Practices Analyzer reports and the issues that they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

</div>

</div>

</div>

</div>

</div>


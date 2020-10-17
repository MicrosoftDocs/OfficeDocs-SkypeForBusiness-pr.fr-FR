---
title: Utilisation de Best Practices Analyzer pour analyser les problèmes éventuels dans votre déploiement
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20a7b43056071ddc2322ff5147de72d818548b86
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535881"
---
# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a><span data-ttu-id="b270d-102">Utilisation de Best Practices Analyzer pour analyser le déploiement de Lync Server 2013 à la recherche de problèmes éventuels</span><span class="sxs-lookup"><span data-stu-id="b270d-102">Using Best Practices Analyzer to scan your Lync Server 2013 deployment for potential issues</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b270d-103">_**Dernière modification de la rubrique :** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="b270d-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="b270d-104">Pour lancer une analyse Best Practices Analyzer, vous devez spécifier ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="b270d-104">To run a Best Practices Analyzer scan, you must specify the following:</span></span>

  - <span data-ttu-id="b270d-105">**Informations d’identification**     Pour exécuter une analyse, vous devez vous connecter à un ordinateur sur lequel Best Practices Analyzer est installé à l’aide d’un compte membre du groupe Administrateurs local.</span><span class="sxs-lookup"><span data-stu-id="b270d-105">**Credentials**   To run a scan, you must log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group.</span></span> <span data-ttu-id="b270d-106">En outre, ce compte doit disposer des droits et autorisations requis pour lancer les analyses appropriées ou vous devez spécifier des informations d’identification disposant des droits et autorisations appropriés pour exécuter Best Practices Analyzer.</span><span class="sxs-lookup"><span data-stu-id="b270d-106">Additionally, you need to log on by using a user account that has the user rights and permissions required to run the appropriate scans, or you must specify credentials that have the appropriate user rights and permissions when you run Best Practices Analyzer.</span></span> <span data-ttu-id="b270d-107">Pour plus d’informations, reportez-vous aux [appartenances aux groupes et aux droits des utilisateurs pour Best Practices Analyzer dans Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="b270d-107">For details, see [Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span></span>

  - <span data-ttu-id="b270d-108">**Étendue de l’analyse**     Pour spécifier l’étendue de l’analyse, sélectionnez les catégories et les serveurs que vous souhaitez analyser.</span><span class="sxs-lookup"><span data-stu-id="b270d-108">**Scope of scan**   To specify the scope of the scan, select the categories and servers that you want to scan.</span></span> <span data-ttu-id="b270d-109">Vous pouvez sélectionner toutes les catégories, une ou plusieurs catégories ou un ou plusieurs serveurs d’une catégorie spécifique dans votre environnement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b270d-109">You can select all categories, one or more categories, or one or more servers within a specific category in your Lync Server environment.</span></span>

  - <span data-ttu-id="b270d-110">**Type d’analyse**     Actuellement, l’analyse du contrôle d’intégrité est le seul type d’analyse disponible (sélectionné par défaut).</span><span class="sxs-lookup"><span data-stu-id="b270d-110">**Type of scan**   Currently, the Health Check scan is the only type of scan available (selected by default).</span></span> <span data-ttu-id="b270d-111">L’analyse de vérification de l’intégrité génère un rapport qui comprend les erreurs, les avertissements et d’autres informations pour tous les serveurs spécifiés dans l’étendue de l’analyse.</span><span class="sxs-lookup"><span data-stu-id="b270d-111">The Health Check scan generates a report that includes errors, warnings, and other information for all servers specified in the scope.</span></span>

  - <span data-ttu-id="b270d-112">**Vitesse**     du réseau Les options de vitesse du réseau sont les suivants : Fast LAN (100 Mbits/s ou plus), LAN (10 Mbits/s), Fast WAN (1,5 Mbits/s) ou WAN (64 Kbits/s).</span><span class="sxs-lookup"><span data-stu-id="b270d-112">**Network speed**   Network speed options include Fast LAN (100 Mbps or more), LAN (10 Mbps), Fast WAN (1.5 Mbps), or WAN (64 kbps).</span></span> <span data-ttu-id="b270d-113">Le temps estimé pour réaliser l’analyse dépend de ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="b270d-113">The estimated time to complete the scan is based on this setting.</span></span> <span data-ttu-id="b270d-114">Ce paramètre est également utilisé pour définir le délai d’expiration.</span><span class="sxs-lookup"><span data-stu-id="b270d-114">This setting is also used to set the time-out period.</span></span> <span data-ttu-id="b270d-115">Au cours de l’analyse, Best Practices Analyzer attend une réponse d’un serveur dans un délai spécifié.</span><span class="sxs-lookup"><span data-stu-id="b270d-115">During the scan, the Best Practices Analyzer waits for a response from a server for a specified time.</span></span> <span data-ttu-id="b270d-116">S’il ne reçoit aucune réponse dans ce délai, il passe au serveur suivant dans l’analyse.</span><span class="sxs-lookup"><span data-stu-id="b270d-116">If it does not receive a response within the specified time-out period, it moves to the next server in the scan.</span></span> <span data-ttu-id="b270d-117">Sur les réseaux plus lents, ce délai est plus long pour prendre en compte les latences réseau plus longues.</span><span class="sxs-lookup"><span data-stu-id="b270d-117">On slower networks, this specified time-out period is longer to account for longer network latencies.</span></span> <span data-ttu-id="b270d-118">Nous vous recommandons de sélectionner la liaison la plus lente dans votre topologie pour ce paramètre afin que l’exécution de l’outil n’expire pas non plus.</span><span class="sxs-lookup"><span data-stu-id="b270d-118">We recommend that you select the slowest link in your topology for this parameter so that the tool does not time out too quickly.</span></span>

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a><span data-ttu-id="b270d-119">Pour analyser votre déploiement Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b270d-119">To scan your Lync Server 2013 deployment</span></span>

1.  <span data-ttu-id="b270d-120">Ouvrez une session sur un ordinateur, sur lequel Best Practices Analyzer est installé, avec un compte membre du groupe Administrateurs local et qui dispose d’autres droits et autorisations requis.</span><span class="sxs-lookup"><span data-stu-id="b270d-120">Log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group, and has other required user rights and permissions.</span></span>

2.  <span data-ttu-id="b270d-121">Cliquez sur **Démarrer**, pointez sur **tous les programmes**, cliquez sur **Microsoft Lync Server 2013**, puis sur **Best Practices Analyzer**.</span><span class="sxs-lookup"><span data-stu-id="b270d-121">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="b270d-122">Dans l’écran d’**accueil**, cliquez sur **Sélectionner des options pour une nouvelle analyse**.</span><span class="sxs-lookup"><span data-stu-id="b270d-122">On the **Welcome** screen, click **Select options for a new scan**.</span></span>

4.  <span data-ttu-id="b270d-123">Dans la page **Connexion à Active Directory**, vérifiez le nom spécifié dans **Serveur Active Directory**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b270d-123">On the **Connect to Active Directory** page, verify the name specified in **Active Directory Server**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="b270d-124">Pour lancer une analyse avec les informations d’identification que vous avez utilisées pour ouvrir une session sur l’ordinateur, cliquez sur **Connexion au serveur Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="b270d-124">To run a scan using the credentials that you used to log on to the computer, click **Connect to the Active Directory server**.</span></span>
    
      - <span data-ttu-id="b270d-125">Pour spécifier d’autres informations d’identification que celles que vous souhaitez utiliser pour les services de domaine Active Directory, les serveurs Edge ou les serveurs Exchange, cliquez sur **Afficher les options d’ouverture de session avancées**, activez les cases à cocher pour lesquelles des informations d’identification distinctes sont requises, spécifiez les informations d’identification pour chacune des cases à cocher activées, puis cliquez sur **Connexion au serveur Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="b270d-125">To specify different credentials that you want to use for Active Directory Domain Services, Edge Server, or Exchange Server, click **Show advanced logon options**, select each check box for which separate credentials are required, specify the credentials for each selected check box, and then click **Connect to the Active Directory server**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b270d-p105">Avant de commencer l’analyse, Best Practices Analyzer effectue une vérification du réseau et des autorisations pour s’assurer que les informations d’identification spécifiées sont valides et qu’il peut se connecter aux services de domaine Active Directory. Si l’outil est exécuté sur un serveur de groupe de travail, il vérifie également qu’il peut se connecter aux serveurs Edge dans le réseau de périmètre (s’ils sont inclus dans l’analyse).</span><span class="sxs-lookup"><span data-stu-id="b270d-p105">Before beginning the scan, Best Practices Analyzer performs a network and permissions check to ensure that the specified account credentials are valid and that Best Practices Analyzer can connect to Active Directory Domain Services. If the tool is running on a workgroup server, the tool also verifies that it can connect to Edge Servers in the perimeter network (that is, if they are included in the scan).</span></span>

    
    </div>

5.  <span data-ttu-id="b270d-128">Dans la page **Démarrer une nouvelle analyse Best Practices**, sélectionnez les options que vous souhaitez inclure dans l’analyse, spécifiez la vitesse du réseau, puis cliquez sur **Démarrer l’analyse**.</span><span class="sxs-lookup"><span data-stu-id="b270d-128">On the **Start a new Best Practices scan** page, select the options that you want to include in the scan, specify the network speed, and then click **Start scanning**.</span></span>

6.  <span data-ttu-id="b270d-129">Dans la page **Analyse terminée**, cliquez sur **Afficher un rapport de cette analyse**.</span><span class="sxs-lookup"><span data-stu-id="b270d-129">On the **Scanning Completed** page, click **View a report of this Best Practices scan**.</span></span>

7.  <span data-ttu-id="b270d-130">Dans la page **Afficher le rapport Best Practices**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b270d-130">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="b270d-131">Pour afficher les rapports dans une liste organisée par composant serveur, cliquez sur **Rapports de liste**, puis cliquez sur l’onglet **Tous les problèmes** ou sur l’onglet **Éléments d’information**.</span><span class="sxs-lookup"><span data-stu-id="b270d-131">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="b270d-132">Pour afficher les rapports sous forme de liste hiérarchique organisée par type de résultat, cliquez sur **Rapports d’arborescence**, puis cliquez sur l’onglet **Affichage détaillé** ou sur l’onglet **Affichage de synthèse**.</span><span class="sxs-lookup"><span data-stu-id="b270d-132">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="b270d-133">Pour afficher d’autres rapports, cliquez sur **Autres rapports**.</span><span class="sxs-lookup"><span data-stu-id="b270d-133">To view other reports, click **Other Reports**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b270d-134">Pour plus d’informations sur les rapports de Best Practices Analyzer et les problèmes qu’ils identifient, voir <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">affichage et utilisation des rapports créés par Best Practices Analyzer dans Lync server 2013</A> et <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analyse et résolution des problèmes identifiés par Best Practices Analyzer dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b270d-134">For details about the Best Practices Analyzer reports and the issues they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


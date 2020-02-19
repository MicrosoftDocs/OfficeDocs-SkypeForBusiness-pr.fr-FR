---
title: 'Lync Server 2013 : lecture de journaux de capture à partir du service de journalisation centralisée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reading capture logs from the Centralized Logging Service
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49733813
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebb1ec3ebde4f1277d6304190aceafa2e0fe2884
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="78a35-102">Lecture des journaux de capture à partir du service de journalisation centralisée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78a35-102">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78a35-103">_**Dernière modification de la rubrique :** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="78a35-103">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="78a35-104">Vous profitez de l’avantage réel du service de journalisation centralisée après avoir exécuté la recherche et vous disposez d’un fichier que vous pouvez utiliser pour repérer un problème signalé.</span><span class="sxs-lookup"><span data-stu-id="78a35-104">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="78a35-105">Vous pouvez lire le fichier de plusieurs façons.</span><span class="sxs-lookup"><span data-stu-id="78a35-105">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="78a35-106">Le fichier de sortie est au format texte standard et vous pouvez utiliser Notepad. exe ou tout autre programme qui vous permettra d’ouvrir et de lire un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="78a35-106">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="78a35-107">Pour les fichiers plus volumineux et les problèmes plus complexes, vous pouvez utiliser un outil tel que Snooper. exe qui est conçu pour lire et analyser la sortie de journalisation à partir du service de journalisation centralisée.</span><span class="sxs-lookup"><span data-stu-id="78a35-107">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="78a35-108">Snooper est inclus avec les outils de débogage Lync Server 2013, qui peuvent être téléchargés séparément.</span><span class="sxs-lookup"><span data-stu-id="78a35-108">Snooper is included with the Lync Server 2013 Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="78a35-109">Vous pouvez télécharger les outils de débogage Lync Server 2013 [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)ici :.</span><span class="sxs-lookup"><span data-stu-id="78a35-109">You can download the Lync Server 2013 Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257).</span></span> <span data-ttu-id="78a35-110">Lorsque vous installez les outils de débogage Lync Server 2013, les raccourcis et les éléments de menu ne sont pas créés.</span><span class="sxs-lookup"><span data-stu-id="78a35-110">When you install the Lync Server 2013 Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="78a35-111">Une fois que vous avez installé les outils de débogage Lync Server 2013, ouvrez l’Explorateur Windows, une fenêtre de ligne de commande ou Lync Server Management Shell et accédez au répertoire (\\emplacement par\\défaut) C :\\Program Files Microsoft Lync Server 2013 Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="78a35-111">After you install the Lync Server 2013 Debug Tools, open Windows Explorer, a command-line window, or Lync Server Management Shell and go to the directory (default location) C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="78a35-112">Double-cliquez sur Snooper. exe ou sur Snooper. exe, puis appuyez sur entrée si vous utilisez la ligne de commande ou Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="78a35-112">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Lync Server Management Shell.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="78a35-113">L’objectif de cette rubrique n’est pas de détailler et de discuter des techniques de résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="78a35-113">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="78a35-114">Le dépannage et les processus qui l’entourent constituent un sujet complexe.</span><span class="sxs-lookup"><span data-stu-id="78a35-114">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="78a35-115">Pour plus d’informations sur la résolution des problèmes de base et sur la résolution des charges de travail spécifiques, <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>consultez le Guide du kit de ressources Microsoft Lync Server 2010 à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="78a35-115">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>.</span></span> <span data-ttu-id="78a35-116">Les processus et procédures s’appliquent toujours à Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="78a35-116">The processes and procedures still apply to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="78a35-117">Lync Server 2013 introduit une version mise à jour du Snooper qui inclut quelques nouvelles fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="78a35-117">Lync Server 2013 introduces an updated version of Snooper that includes some new features.</span></span> <span data-ttu-id="78a35-118">La capture d’écran suivante montre la version d’un Snooping à partir d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="78a35-118">The following screen shot shows the version of Snooper from Office Communications Server 2007.</span></span>

<span data-ttu-id="78a35-119">![Version d’Office Communications 2007 de Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Version d’Office Communications 2007 de Snooper.")</span><span class="sxs-lookup"><span data-stu-id="78a35-119">![Office Communications 2007 version of Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 version of Snooper.")</span></span>

<span data-ttu-id="78a35-120">La capture d’écran suivante montre la nouvelle version de Snooper incluse dans les outils de débogage Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="78a35-120">The following screen shot shows the new version of Snooper included in the Lync Server 2013 Debug Tools.</span></span>

<span data-ttu-id="78a35-121">![Version Lync Server 2013 de Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Version Lync Server 2013 de Snooper.")</span><span class="sxs-lookup"><span data-stu-id="78a35-121">![Lync Server 2013 version of Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 version of Snooper.")</span></span>

<span data-ttu-id="78a35-122">La capture d’écran suivante montre la barre d’outils avec des fonctions fréquemment utilisées.</span><span class="sxs-lookup"><span data-stu-id="78a35-122">The following screen shot shows the toolbar with frequently used functions.</span></span>

<span data-ttu-id="78a35-123">![Snooper 2013 barre d’outils.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 barre d’outils.")</span><span class="sxs-lookup"><span data-stu-id="78a35-123">![Snooper 2013 toolbar.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 toolbar.")</span></span>

<span data-ttu-id="78a35-124">La dernière fonctionnalité qui ajoute value est l’affichage Diagramme de l’organigramme (flux d’appels).</span><span class="sxs-lookup"><span data-stu-id="78a35-124">And, the newest feature that adds value is the Flow Chart (call flow) diagram view.</span></span> <span data-ttu-id="78a35-125">Sélectionnez un flux de messages dans l’onglet **message** , puis cliquez sur le bouton **flux d’appels** .</span><span class="sxs-lookup"><span data-stu-id="78a35-125">You select a message flow in the **Message** tab and click the **Call Flow** button.</span></span> <span data-ttu-id="78a35-126">Lorsque vous parcourez les messages, le schéma de flux d’appels est mis à jour avec les nouvelles données.</span><span class="sxs-lookup"><span data-stu-id="78a35-126">As you proceed through the messages, the call flow diagram updates with new data.</span></span>

<span data-ttu-id="78a35-127">![Le diagramme de flux d’appels Snooper 2013.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Le diagramme de flux d’appels Snooper 2013.")</span><span class="sxs-lookup"><span data-stu-id="78a35-127">![Snooper 2013 call flow diagram.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 call flow diagram.")</span></span>

<span data-ttu-id="78a35-128">Vous pouvez pointer sur l’affichage Diagramme et obtenir des détails sur les messages et le contenu des flux et des messages, ainsi que sur les éléments serveur.</span><span class="sxs-lookup"><span data-stu-id="78a35-128">You can hover over the diagram view and get details about the messages and content of the flows and messages as well as the server elements.</span></span> <span data-ttu-id="78a35-129">Cliquez sur une flèche de flux d’appels pour accéder au message dans la vue messages.</span><span class="sxs-lookup"><span data-stu-id="78a35-129">Click on any call flow arrow to go to the message in the Messages view.</span></span>

<span data-ttu-id="78a35-130">![Détails du message du diagramme de flux d’appels.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Détails du message du diagramme de flux d’appels.")</span><span class="sxs-lookup"><span data-stu-id="78a35-130">![Call flow diagram message details.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Call flow diagram message details.")</span></span>

<div>

## <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="78a35-131">Pour ouvrir un fichier journal dans Snooper</span><span class="sxs-lookup"><span data-stu-id="78a35-131">To open a log file in Snooper</span></span>

1.  <span data-ttu-id="78a35-132">Pour utiliser le Snooper et les fichiers journaux ouverts, vous avez besoin d’un accès en lecture aux fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="78a35-132">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="78a35-133">Pour utiliser Snooper et accéder aux fichiers journaux, vous devez être membre du groupe de sécurité CsAdministrator ou du contrôle d’accès basé sur le rôle CsServerAdministrator (RBAC), ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes.</span><span class="sxs-lookup"><span data-stu-id="78a35-133">To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="78a35-134">Après l’installation des outils de débogage Lync Server (LyncDebugTools. msi), remplacez le répertoire par l’emplacement de Snooper. exe à l’aide de l’Explorateur Windows ou de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="78a35-134">After the installation of the Lync Server Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="78a35-135">Par défaut, les outils de débogage se trouvent dans C :\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="78a35-135">By default, the debugging tools are located in C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="78a35-136">Double-cliquez sur ou exécutez Snooper. exe.</span><span class="sxs-lookup"><span data-stu-id="78a35-136">Double-click or run Snooper.exe.</span></span>

3.  <span data-ttu-id="78a35-137">Une fois le Snooper ouvert, cliquez avec le bouton droit sur **fichier**, cliquez sur **OpenFile**, recherchez vos fichiers journaux, sélectionnez un fichier dans la boîte de dialogue **ouvrir** , puis cliquez sur **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="78a35-137">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>

4.  <span data-ttu-id="78a35-138">Les messages de **suivi** du fichier journal sont affichés sous l’onglet **suivi** . cliquez sur l’onglet **messages** pour afficher le contenu des messages des traces collectées.</span><span class="sxs-lookup"><span data-stu-id="78a35-138">The log file’s **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="78a35-139">Pour afficher un diagramme de flux d’appels</span><span class="sxs-lookup"><span data-stu-id="78a35-139">To display a call flow diagram</span></span>

1.  <span data-ttu-id="78a35-140">Pour utiliser le Snooper et les fichiers journaux ouverts, vous avez besoin d’un accès en lecture aux fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="78a35-140">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="78a35-141">Pour utiliser Snooper et accéder aux fichiers journaux, vous devez être membre des groupes de sécurité CsAdministrator ou RBAC (contrôle d’accès basé sur un rôle CsServerAdministrator), ou un rôle RBAC personnalisé qui contient l’un de ces deux groupes.</span><span class="sxs-lookup"><span data-stu-id="78a35-141">To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="78a35-142">Ouvrez un fichier journal, cliquez sur l’onglet **messages** , sélectionnez une conversation dans la vue messages ou sélectionnez un composant de suivi dans l’onglet **suivi** .</span><span class="sxs-lookup"><span data-stu-id="78a35-142">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>

3.  <span data-ttu-id="78a35-143">Cliquez sur **flux des appels**.</span><span class="sxs-lookup"><span data-stu-id="78a35-143">Click **Call Flow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="78a35-144">Si vous cliquez sur un message ou un suivi qui ne fait pas partie d’un flux d’appels, le diagramme n’apparaît pas et un message d’État apparaît au bas du Snooping, indiquant « ce message n’est pas éligible pour callfow ».</span><span class="sxs-lookup"><span data-stu-id="78a35-144">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating “This message is not eligible for callfow”.</span></span> <span data-ttu-id="78a35-145">Choisissez un autre message ou suivi et le flux d’appels s’affichera si le message ou le suivi fait partie d’un flux d’appels.</span><span class="sxs-lookup"><span data-stu-id="78a35-145">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span>

    
    </div>

4.  <span data-ttu-id="78a35-146">Parcourez les messages ou les lignes de suivi et notez si le diagramme de flux des appels est mis à jour ou modifié pour afficher un nouveau diagramme.</span><span class="sxs-lookup"><span data-stu-id="78a35-146">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>

5.  <span data-ttu-id="78a35-147">Pointez sur les éléments pour obtenir des informations sur les messages d’appel, les points de terminaison et les autres composants.</span><span class="sxs-lookup"><span data-stu-id="78a35-147">Hover over elements to get information about call messages, endpoints, and other components.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


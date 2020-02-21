---
title: 'Lync Server 2013 : configuration des scénarios pour le service de journalisation centralisée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring scenarios for the Centralized Logging Service
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49733682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc58e0f29ca0a562a94f771857d88da49d616064
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-scenarios-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="2f457-102">Configuration des scénarios pour le service de journalisation centralisée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f457-102">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f457-103">_**Dernière modification de la rubrique :** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="2f457-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="2f457-104">Les scénarios définissent l’étendue (globale, de site, de pool ou d’ordinateur) et les fournisseurs à utiliser dans le service de journalisation centralisée.</span><span class="sxs-lookup"><span data-stu-id="2f457-104">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="2f457-105">À l’aide de scénarios, vous activez ou désactivez le suivi des fournisseurs (par exemple, S4, SIPStack, messagerie instantanée et présence).</span><span class="sxs-lookup"><span data-stu-id="2f457-105">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="2f457-106">En configurant un scénario, vous pouvez regrouper tous les fournisseurs d’une collection logique donnée qui répondent à une condition de problème spécifique.</span><span class="sxs-lookup"><span data-stu-id="2f457-106">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="2f457-107">Si vous constatez qu’un scénario doit être modifié pour répondre à vos besoins de résolution des problèmes et de journalisation, les outils de débogage Lync Server 2013 vous fournissent un module Windows PowerShell nommé *ClsController. psm1* qui contient une fonction nommée *Edit-CsClsScenario*.</span><span class="sxs-lookup"><span data-stu-id="2f457-107">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Lync Server 2013 Debug Tools provides you a Windows PowerShell module named *ClsController.psm1* that contains a function named *Edit-CsClsScenario*.</span></span> <span data-ttu-id="2f457-108">Grâce à ce module, vous pouvez modifier les propriétés du scénario nommé.</span><span class="sxs-lookup"><span data-stu-id="2f457-108">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="2f457-109">Des exemples d’utilisation de ce module sont fournis dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="2f457-109">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="2f457-110">Les outils de débogage Lync Server 2013 sont téléchargés à partir du lien suivant :[https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)</span><span class="sxs-lookup"><span data-stu-id="2f457-110">The Lync Server 2013 Debug Tools are downloaded from the following link: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2f457-111">Pour une étendue donnée (globale, site, pool ou ordinateur), deux scénarios au maximum peuvent être exécutés en même temps.</span><span class="sxs-lookup"><span data-stu-id="2f457-111">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="2f457-112">Pour déterminer les scénarios en cours d’exécution, utilisez Windows PowerShell et <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>.</span><span class="sxs-lookup"><span data-stu-id="2f457-112">To determine which scenarios are currently running, use Windows PowerShell and <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>.</span></span> <span data-ttu-id="2f457-113">À l’aide de Windows PowerShell et de <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">Set-CsClsScenario</A>, vous pouvez modifier dynamiquement les scénarios en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="2f457-113">By using Windows PowerShell and <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">Set-CsClsScenario</A>, you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="2f457-114">Cette opération peut s’avérer utile lors d’une session de journalisation pour ajuster ou affiner les données que vous collectez et les fournisseurs d’où ces données sont issues.</span><span class="sxs-lookup"><span data-stu-id="2f457-114">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span>



</div>

<span data-ttu-id="2f457-115">Pour exécuter les fonctions du service de journalisation centralisée à l’aide de Lync Server Management Shell, vous devez être membre des groupes de sécurité CsAdministrator ou RBAC (contrôle d’accès basé sur un rôle) CsServerAdministrator, ou d’un rôle RBAC personnalisé contenant soit de ces deux groupes.</span><span class="sxs-lookup"><span data-stu-id="2f457-115">To run the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="2f457-116">Pour renvoyer la liste de tous les rôles RBAC auxquels cette applet de commande a été affectée, y compris les rôles RBAC personnalisés que vous avez créés vous-même, exécutez la commande suivante à partir de Lync Server Management Shell ou de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="2f457-116">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="2f457-117">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="2f457-117">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="2f457-118">Le reste de cette rubrique met l’accent sur la définition d’un scénario, la modification d’un scénario, la récupération des scénarios en cours d’exécution, la suppression d’un scénario et la spécification du contenu d’un scénario afin d’optimiser votre dépannage.</span><span class="sxs-lookup"><span data-stu-id="2f457-118">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="2f457-119">Il existe deux façons d’émettre des commandes de service de journalisation centralisée.</span><span class="sxs-lookup"><span data-stu-id="2f457-119">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="2f457-120">Vous pouvez utiliser le CLSController. exe qui se trouve, par défaut, dans le répertoire C :\\Program Files\\Common files\\Microsoft Lync Server 2013\\CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="2f457-120">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="2f457-121">Vous pouvez utiliser Lync Server Management Shell pour émettre des commandes Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f457-121">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="2f457-122">Il est important de noter que lorsque vous utilisez CLSController.exe à la ligne de commande, la sélection de scénarios disponibles est limitée.</span><span class="sxs-lookup"><span data-stu-id="2f457-122">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available.</span></span> <span data-ttu-id="2f457-123">Lorsque vous utilisez Windows PowerShell, vous pouvez définir de nouveaux scénarios à utiliser dans vos sessions de journalisation.</span><span class="sxs-lookup"><span data-stu-id="2f457-123">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>

<span data-ttu-id="2f457-124">Comme présenté dans la [rubrique vue d’ensemble du service de journalisation centralisée dans Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), les éléments d’un scénario sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="2f457-124">As introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the elements of a scenario are:</span></span>

  - <span data-ttu-id="2f457-125">**Fournisseurs**   si vous êtes familiarisé avec OCSLogger, les fournisseurs sont les composants que vous choisissez pour indiquer à OCSLogger ce que le moteur de suivi doit collecter dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="2f457-125">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="2f457-126">Les fournisseurs sont les mêmes composants et, dans de nombreux cas, ont le même nom que les composants dans OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="2f457-126">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="2f457-127">Si vous n’êtes pas familiarisé avec OCSLogger, les fournisseurs sont des composants spécifiques au rôle serveur, dont le service de journalisation centralisée peut collecter des journaux.</span><span class="sxs-lookup"><span data-stu-id="2f457-127">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="2f457-128">Pour plus d’informations sur la configuration des fournisseurs, voir [Configuration des fournisseurs pour le service de journalisation centralisée dans Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).</span><span class="sxs-lookup"><span data-stu-id="2f457-128">For details about the configuration of providers, see [Configuring providers for Centralized Logging Service in Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).</span></span>

  - <span data-ttu-id="2f457-129">**Identity**   le paramètre – Identity définit l’étendue et le nom du scénario.</span><span class="sxs-lookup"><span data-stu-id="2f457-129">**Identity**   The parameter –Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="2f457-130">Par exemple, vous pouvez définir une étendue « global » et nommer le scénario « LyssServiceScenario ».</span><span class="sxs-lookup"><span data-stu-id="2f457-130">For example, you could set a scope of “global” and identify the scenario with “LyssServiceScenario”.</span></span> <span data-ttu-id="2f457-131">Lorsque vous combinez les deux, vous définissez l’identité (par exemple, « global/LyssServiceScenario »).</span><span class="sxs-lookup"><span data-stu-id="2f457-131">When you combine the two, you define the Identity (for example, “global/LyssServiceScenario”).</span></span>
    
    <span data-ttu-id="2f457-p107">Vous pouvez éventuellement utiliser les paramètres –Name et –Parent. Le paramètre Name permet d’identifier le scénario de manière unique. Si vous utilisez Name, vous devez également utiliser Parent pour ajouter le scénario à global ou site.</span><span class="sxs-lookup"><span data-stu-id="2f457-p107">Optionally, you can use the –Name and –Parent parameters. You define the Name parameter to uniquely identify the scenario. If you use Name, you must also use Parent to add the scenario to either global or site.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2f457-135">Si vous utilisez les paramètres Name et Parent, vous ne pouvez pas utiliser le paramètre <STRONG>–Identity</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="2f457-135">If you use the Name and Parent parameters, you cannot use the <STRONG>–Identity</STRONG> parameter.</span></span>

    
    </div>

<div>

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="2f457-136">Pour créer un scénario avec l’applet de commande New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="2f457-136">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="2f457-137">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2f457-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2f457-138">Pour créer un scénario pour une session de journalisation, utilisez [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) et définissez le nom du scénario (c’est-à-dire comment il va être identifié de manière unique).</span><span class="sxs-lookup"><span data-stu-id="2f457-138">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) and define the name of the scenario (that is, how it will be uniquely identified).</span></span> <span data-ttu-id="2f457-139">Choisissez un type de format de journalisation : vous avez le choix entre WPP (préprocesseur de suivi de logiciel Windows ; la valeur par défaut), EventLog (format de journal des événements Windows) et IISLog (fichier au format ASCII basé sur le format du fichier journal IIS).</span><span class="sxs-lookup"><span data-stu-id="2f457-139">Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format).</span></span> <span data-ttu-id="2f457-140">Ensuite, définissez Level (voir la définition sous Niveaux de journalisation dans cette rubrique) et Flags (voir la définition sous Indicateurs dans cette rubrique).</span><span class="sxs-lookup"><span data-stu-id="2f457-140">Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="2f457-141">Dans cet exemple de scénario, nous utilisons LyssProvider comme exemple de variable de fournisseur.</span><span class="sxs-lookup"><span data-stu-id="2f457-141">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="2f457-142">Pour créer un scénario en utilisant les options définies, tapez :</span><span class="sxs-lookup"><span data-stu-id="2f457-142">To create a scenario using the options defined, type:</span></span>
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    <span data-ttu-id="2f457-143">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="2f457-143">For example:</span></span>
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    <span data-ttu-id="2f457-144">Autre format utilisant –Name et –Parent :</span><span class="sxs-lookup"><span data-stu-id="2f457-144">The alternate format using –Name and –Parent:</span></span>
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

</div>

<div>

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="2f457-145">Pour créer un scénario avec plusieurs fournisseurs à l’aide de l’applet de commande New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="2f457-145">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="2f457-146">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2f457-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2f457-147">Vous êtes limité à deux scénarios par étendue.</span><span class="sxs-lookup"><span data-stu-id="2f457-147">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="2f457-148">Cependant, le nombre de fournisseurs n’est pas limité.</span><span class="sxs-lookup"><span data-stu-id="2f457-148">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="2f457-149">Dans cet exemple, supposons que vous avez créé trois fournisseurs et que vous souhaitez les affecter tous les trois au scénario que vous définissez.</span><span class="sxs-lookup"><span data-stu-id="2f457-149">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="2f457-150">Les noms des variables de fournisseur sont LyssProvider, ABServerProvider et SIPStackProvider.</span><span class="sxs-lookup"><span data-stu-id="2f457-150">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="2f457-151">Pour définir et affecter plusieurs fournisseurs à un scénario, tapez ce qui suit dans une invite de commande Lync Server Management Shell ou Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="2f457-151">To define and assign multiple providers to a scenario, type the following at a Lync Server Management Shell or Windows PowerShell command prompt:</span></span>
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2f457-152">Comme il est connu dans Windows PowerShell, la Convention de création d’une table de hachage des <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> valeurs à l’aide de est appelée « <EM>projection</EM>».</span><span class="sxs-lookup"><span data-stu-id="2f457-152">As it is known in Windows PowerShell, the convention for creating a hash table of values using <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> is known as <EM>splatting</EM>.</span></span> <span data-ttu-id="2f457-153">Pour plus d’informations sur la projection dans Windows PowerShell, <A href="https://go.microsoft.com/fwlink/p/?linkid=267760">https://go.microsoft.com/fwlink/p/?LinkId=267760</A>reportez-vous à la rubrique.</span><span class="sxs-lookup"><span data-stu-id="2f457-153">For details about splatting in Windows PowerShell, see <A href="https://go.microsoft.com/fwlink/p/?linkid=267760">https://go.microsoft.com/fwlink/p/?LinkId=267760</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="2f457-154">Pour modifier un scénario existant avec l’applet de commande Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="2f457-154">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="2f457-155">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2f457-155">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2f457-p111">Vous êtes limité à deux scénarios par étendue. Vous pouvez modifier les scénarios qui s’ exécutent à tout moment, même lorsqu’une session de capture de journalisation est en cours. Si vous redéfinissez les scénarios en cours d’exécution, la session de journalisation actuelle cesse d’utiliser le scénario qui a été supprimé et utilise ensuite le nouveau scénario. Toutefois, les informations de journalisation qui ont été capturées avec le scénario supprimé sont conservées dans les journaux capturés. Pour définir un nouveau scénario, procédez comme suit (pour cela, nous partons du principe qu’un fournisseur déjà défini nommé « S4Provider » a été ajouté) :</span><span class="sxs-lookup"><span data-stu-id="2f457-p111">You are limited to two scenarios per scope. You can change which scenarios are running at any time, even when a logging capture session is in process. If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario. However, the logging information that was captured with the removed scenario remains in the captured logs. To define a new scenario, do the following (that is, assuming the addition of an already defined provider named “S4Provider”):</span></span>
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    <span data-ttu-id="2f457-161">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="2f457-161">For example:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    <span data-ttu-id="2f457-p112">Si vous souhaitez remplacer des fournisseurs, définissez un fournisseur unique ou une liste séparée par des virgules des fournisseurs pour remplacer l’ensemble actuel. Si vous souhaitez seulement remplacer l’un des fournisseurs, ajoutez les fournisseurs actuels aux nouveaux fournisseurs pour créer un nouvel ensemble de fournisseurs contenant les nouveaux fournisseurs et les fournisseurs existants. Pour remplacer tous les fournisseurs par un nouvel ensemble, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="2f457-p112">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set. If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers. To replace all providers with a new set, type the following:</span></span>
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    <span data-ttu-id="2f457-165">Par exemple, pour remplacer l’ensemble actuel comprenant $LyssProvider, $ABServerProvider et $SIPStackProvider par $LyssServiceProvider :</span><span class="sxs-lookup"><span data-stu-id="2f457-165">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    <span data-ttu-id="2f457-166">Pour remplacer seulement le fournisseur $LyssProvider de l’ensemble actuel comprenant $LyssProvider, $ABServerProvider et $SIPStackProvider par $LyssServiceProvider, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="2f457-166">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

</div>

<div>

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="2f457-167">Pour supprimer un scénario existant avec l’applet de commande Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="2f457-167">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="2f457-168">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2f457-168">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2f457-169">Si vous souhaitez supprimer un scénario précédemment défini, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="2f457-169">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    <span data-ttu-id="2f457-170">Par exemple, pour supprimer le scénario défini site:Redmond/LyssServiceScenario :</span><span class="sxs-lookup"><span data-stu-id="2f457-170">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

<span data-ttu-id="2f457-171">L’applet de commande **Remove-CsClsScenario** supprime le scénario spécifié, mais vous pouvez toujours accéder aux suivis capturés dans les journaux et lancer des recherches dans ceux-ci.</span><span class="sxs-lookup"><span data-stu-id="2f457-171">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>

</div>

<div>

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clscontrollerpsm1-module"></a><span data-ttu-id="2f457-172">Pour charger et décharger l’applet de commande Edit-CsClsScenario à l’aide du module ClsController.psm1</span><span class="sxs-lookup"><span data-stu-id="2f457-172">To load and unload the Edit-CsClsScenario cmdlet using the ClsController.psm1 module</span></span>

1.  <span data-ttu-id="2f457-173">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2f457-173">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2f457-174">Le module ClsController.psm1 est fourni sous forme d’un téléchargement web distinct.</span><span class="sxs-lookup"><span data-stu-id="2f457-174">The ClsController.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="2f457-175">Le module fait partie des outils de débogage Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2f457-175">The module is part of the Lync Server 2013 Debugging tools.</span></span> <span data-ttu-id="2f457-176">Par défaut, les outils de débogage sont installés dans le répertoire C:\Program Files\Lync Server 2013\Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="2f457-176">By default, the debugging tools are installed in the directory C:\Program Files\Lync Server 2013\Debugging Tools.</span></span>

    
    </div>

2.  <span data-ttu-id="2f457-177">À partir de Windows PowerShell, tapez :</span><span class="sxs-lookup"><span data-stu-id="2f457-177">From the Windows PowerShell, type:</span></span>
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="2f457-178">Le chargement réussi du module vous renvoie à l’invite de commandes Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f457-178">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="2f457-179">Pour vérifier que le module est chargé et que Edit-CsClsScenario est disponible, tapez <CODE>Get-Help Edit-CsClsScenario</CODE>.</span><span class="sxs-lookup"><span data-stu-id="2f457-179">To confirm that the module is loaded and that Edit-CsClsScenario is available, type <CODE>Get-Help Edit-CsClsScenario</CODE>.</span></span> <span data-ttu-id="2f457-180">Le résumé de base de la syntaxe pour EditCsClsScenario doit apparaître.</span><span class="sxs-lookup"><span data-stu-id="2f457-180">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span>

    
    </div>

3.  <span data-ttu-id="2f457-181">Pour décharger les modules, tapez :</span><span class="sxs-lookup"><span data-stu-id="2f457-181">To unload the modules, type:</span></span>
    
        Remove-Module ClsController
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="2f457-182">Si le déchargement du module réussit, vous revenez à l’invite de commandes Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f457-182">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="2f457-183">Pour confirmer que le module est déchargé, tapez <CODE>Get-Help Edit-CsClsScenario</CODE>.</span><span class="sxs-lookup"><span data-stu-id="2f457-183">To confirm that the module is unloaded, type <CODE>Get-Help Edit-CsClsScenario</CODE>.</span></span> <span data-ttu-id="2f457-184">Windows PowerShell essaiera de trouver l’aide de la cmdlet et échouera.</span><span class="sxs-lookup"><span data-stu-id="2f457-184">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="2f457-185">Pour supprimer un fournisseur existant d’un scénario avec le module Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="2f457-185">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1.  <span data-ttu-id="2f457-186">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2f457-186">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2f457-187">Pour supprimer un fournisseur du scénario AlwaysOn, tapez :</span><span class="sxs-lookup"><span data-stu-id="2f457-187">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    <span data-ttu-id="2f457-188">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="2f457-188">For Example:</span></span>
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    <span data-ttu-id="2f457-p116">Les paramètres ScenarioName et ProviderName sont positionnels (c’est-à-dire qu’ils doivent être définis dans la position attendue dans la ligne de commande). Il n’est pas nécessaire de définir explicitement le nom du paramètre si le nom du scénario est en position deux et que le fournisseur est en position trois par rapport au nom de l’applet de commande (en position un). Compte tenu de ces informations, la commande précédente ressemble alors à ceci :</span><span class="sxs-lookup"><span data-stu-id="2f457-p116">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters. The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one. Using this information, the previous command would be typed as:</span></span>
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    <span data-ttu-id="2f457-p117">Le placement positionnel des valeurs de paramètre s’applique uniquement à –Scenario et à –Provider. Tous les autres paramètres doivent être définis explicitement.</span><span class="sxs-lookup"><span data-stu-id="2f457-p117">The positional placing of the parameter values applies only to –Scenario and –Provider. All other parameters must be explicitly defined.</span></span>

</div>

<div>

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="2f457-194">Pour ajouter un fournisseur à un scénario avec le module Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="2f457-194">To add a provider to a scenario with the Edit-ClsController module</span></span>

1.  <span data-ttu-id="2f457-195">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2f457-195">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2f457-196">Pour ajouter un fournisseur au scénario AlwaysOn, tapez :</span><span class="sxs-lookup"><span data-stu-id="2f457-196">To add a provider to the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    <span data-ttu-id="2f457-197">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="2f457-197">For Example:</span></span>
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    <span data-ttu-id="2f457-198">\-LogLevel peut être de type fatal, Error, Warning, info, Verbose, Debug ou All.</span><span class="sxs-lookup"><span data-stu-id="2f457-198">\-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="2f457-199">– Les indicateurs peuvent être n’importe quel indicateur pris en charge par le fournisseur,\_comme le composant\_TF, TF diag.</span><span class="sxs-lookup"><span data-stu-id="2f457-199">–Flags can be any of the flags that the provider supports, such as TF\_COMPONENT, TF\_DIAG.</span></span> <span data-ttu-id="2f457-200">–Flags peut également avoir la valeur ALL.</span><span class="sxs-lookup"><span data-stu-id="2f457-200">–Flags can also be of value ALL</span></span>
    
    <span data-ttu-id="2f457-p119">Il est aussi possible de taper l’exemple précédent à l’aide de la fonctionnalité positionnelle de l’applet de commande. Par exemple, pour ajouter le fournisseur ChatServer au scénario AlwaysOn, tapez :</span><span class="sxs-lookup"><span data-stu-id="2f457-p119">The previous example can also be typed using the positional feature of the cmdlet. For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

</div>

</div>

<span> </span>

</div>

</div>

</div>


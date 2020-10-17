---
title: 'Lync Server 2013 : configuration des fournisseurs pour le service de journalisation centralisée'
description: 'Lync Server 2013 : configuration des fournisseurs pour le service de journalisation centralisée.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9146865b3856f7956c6ae393ef38614b0fea168e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547950"
---
# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="c1496-103">Configuration des fournisseurs pour le service de journalisation centralisée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1496-103">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1496-104">_**Dernière modification de la rubrique :** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="c1496-104">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="c1496-105">Les concepts et la configuration des *fournisseurs* dans le service de journalisation centralisée sont les plus importants à comprendre.</span><span class="sxs-lookup"><span data-stu-id="c1496-105">The concepts and configuration of *providers* in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="c1496-106">Les *fournisseurs* mappent directement vers les composants de rôle serveur Lync Server dans le modèle de suivi Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c1496-106">The *providers* map directly to Lync Server server role components in the Lync Server tracing model.</span></span> <span data-ttu-id="c1496-107">Le fournisseur définit les composants d’un Lync Server 2013 qui seront suivis, le type de messages (par exemple, fatal, erreur ou avertissement) à collecter, ainsi que les indicateurs (par exemple, TF \_ Connection ou TF \_ diag).</span><span class="sxs-lookup"><span data-stu-id="c1496-107">The provider defines the components of a Lync Server 2013 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF\_Connection or TF\_Diag).</span></span> <span data-ttu-id="c1496-108">Les fournisseurs sont les composants traçables dans chaque rôle serveur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c1496-108">Providers are the traceable components in each Lync Server server role.</span></span> <span data-ttu-id="c1496-109">À l’aide de fournisseurs, vous définissez le niveau et le type de suivi sur les composants (par exemple, S4, SIPStack, Messagerie instantanée et Présence).</span><span class="sxs-lookup"><span data-stu-id="c1496-109">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="c1496-110">Le fournisseur défini est utilisé dans un scénario pour regrouper tous les fournisseurs d’une collection logique donnée qui répondent à une condition de problème spécifique.</span><span class="sxs-lookup"><span data-stu-id="c1496-110">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>

<span data-ttu-id="c1496-111">Pour exécuter les fonctions du service de journalisation centralisée à l’aide de Lync Server Management Shell, vous devez être membre des groupes de sécurité CsAdministrator ou RBAC (contrôle d’accès basé sur un rôle CsServerAdministrator), ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes.</span><span class="sxs-lookup"><span data-stu-id="c1496-111">To run the Centralized Logging Service functions using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="c1496-112">Pour renvoyer la liste de tous les rôles RBAC (contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de Lync Server Management Shell ou de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="c1496-112">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="c1496-113">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="c1496-113">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="c1496-114">Le reste de cette rubrique porte sur la définition des fournisseurs, la modification d’un fournisseur et ce que contient une définition de fournisseur afin d’optimiser le dépannage.</span><span class="sxs-lookup"><span data-stu-id="c1496-114">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="c1496-115">Il existe deux façons d’émettre des commandes de service de journalisation centralisée.</span><span class="sxs-lookup"><span data-stu-id="c1496-115">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="c1496-116">Vous pouvez utiliser le CLSController.exe qui se trouve, par défaut, dans le répertoire C : \\ Program Files \\ Common Files \\ Microsoft Lync Server 2013 \\ CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="c1496-116">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="c1496-117">Vous pouvez utiliser Lync Server Management Shell pour émettre des commandes Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1496-117">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="c1496-118">Il est important de noter que lorsque vous utilisez CLSController.exe à la ligne de commande, la sélection de scénarios disponibles dans lesquels les fournisseurs sont déjà définis est limitée et non modifiable ; toutefois, vous pouvez définir le niveau de journalisation.</span><span class="sxs-lookup"><span data-stu-id="c1496-118">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available in which the providers are already defined and are not changeable, but you can define the log level.</span></span> <span data-ttu-id="c1496-119">À l’aide de Windows PowerShell, vous pouvez définir de nouveaux fournisseurs à utiliser dans vos sessions de journalisation et disposer d’un contrôle total sur leur création, leur collecte et leur niveau de collecte des données.</span><span class="sxs-lookup"><span data-stu-id="c1496-119">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="c1496-p104">Comme nous l’avons précédemment mentionné, les fournisseurs sont très puissants. Cependant, les scénarios le sont davantage, et ce du fait qu’ils contiennent toutes les informations nécessaires pour définir et exécuter le suivi sur les composants que les fournisseurs représentent. Les scénarios étant une collection de fournisseurs, une certaine analogie peut être établie entre, d’une part, l’exécution d’un fichier de commandes qui contient des centaines de commandes destinées à collecter une grande quantité d’informations et, d’autre part, l’émission de centaines de commandes, une à la fois, à la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="c1496-p104">As mentioned, providers are very powerful. However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent. With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span><BR><span data-ttu-id="c1496-123">Au lieu de vous demander d’approfondir les détails des fournisseurs, le service de journalisation centralisée fournit un certain nombre de scénarios qui sont déjà définis pour vous.</span><span class="sxs-lookup"><span data-stu-id="c1496-123">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="c1496-124">Les scénarios fournis couvrent la grande majorité des problèmes que vous êtes susceptible de rencontrer.</span><span class="sxs-lookup"><span data-stu-id="c1496-124">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="c1496-125">Dans de rares cas, vous devrez créer et définir des fournisseurs et les affecter à des scénarios.</span><span class="sxs-lookup"><span data-stu-id="c1496-125">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="c1496-126">Nous vous recommandons fortement de vous familiariser avec chacun des scénarios fournis avant d’étudier la nécessité de créer de nouveaux scénarios et de nouveaux fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="c1496-126">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="c1496-127">Bien que des informations sur la création de fournisseurs sont données ici pour vous familiariser avec la façon dont les scénarios utilisent les éléments des fournisseurs pour collecter des informations de suivi, aucun détail sur les fournisseurs eux-mêmes n’est fourni pour le moment.</span><span class="sxs-lookup"><span data-stu-id="c1496-127">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span>



</div>

<span data-ttu-id="c1496-128">Introduits dans [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), les éléments clés de la définition d’un fournisseur à utiliser dans un scénario sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="c1496-128">Introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>

  - <span data-ttu-id="c1496-129">**Fournisseurs**     Si vous êtes familiarisé avec OCSLogger, les fournisseurs sont les composants que vous choisissez pour indiquer OCSLogger ce que le moteur de suivi doit collecter dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="c1496-129">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="c1496-130">Les fournisseurs sont les mêmes composants et, dans de nombreux cas, ont le même nom que les composants dans OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="c1496-130">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="c1496-131">Si vous n’êtes pas familiarisé avec OCSLogger, les fournisseurs sont des composants spécifiques au rôle serveur, dont le service de journalisation centralisée peut collecter des journaux.</span><span class="sxs-lookup"><span data-stu-id="c1496-131">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="c1496-132">Dans le cas du service de journalisation centralisée, le CLSAgent est la partie architecturale du service de journalisation centralisée qui effectue le suivi des composants que vous définissez dans la configuration des fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="c1496-132">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>

  - <span data-ttu-id="c1496-133">Niveaux de journalisation **Logging levels**     OCSLogger a fourni la possibilité de choisir un certain nombre de niveaux de détail pour les données collectées.</span><span class="sxs-lookup"><span data-stu-id="c1496-133">**Logging levels**   OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="c1496-134">Cette fonctionnalité fait partie intégrante du service de journalisation centralisée et des scénarios, et est définie par le paramètre **type** .</span><span class="sxs-lookup"><span data-stu-id="c1496-134">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="c1496-135">Vous pouvez choisir l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="c1496-135">You can choose from the following:</span></span>
    
      - <span data-ttu-id="c1496-136">**Tous les**     Collecte les messages de suivi de type fatal, Error, Warning et info dans le journal pour le fournisseur défini.</span><span class="sxs-lookup"><span data-stu-id="c1496-136">**All**   Collects trace messages of type fatal, error, warning, and info to the log for the defined provider.</span></span>
    
      - <span data-ttu-id="c1496-137">**Irrécupérable**     Collecte uniquement les messages de suivi qui indiquent un échec pour le fournisseur défini.</span><span class="sxs-lookup"><span data-stu-id="c1496-137">**Fatal**   Collects only the trace messages that indicate a failure for the defined provider.</span></span>
    
      - <span data-ttu-id="c1496-138">**Erreur**     Collecte uniquement les messages de suivi qui indiquent une erreur pour le fournisseur défini, ainsi que les messages irrécupérables.</span><span class="sxs-lookup"><span data-stu-id="c1496-138">**Error**   Collects only the trace messages that indicate an error for the defined provider, plus fatal messages.</span></span>
    
      - <span data-ttu-id="c1496-139">**Avertissement**     Collecte uniquement les messages de suivi qui indiquent un avertissement pour le fournisseur défini, ainsi que les messages d’erreur et d’erreur irrécupérable.</span><span class="sxs-lookup"><span data-stu-id="c1496-139">**Warning**   Collects only the trace messages that indicate a warning for the defined provider, plus fatal and error messages.</span></span>
    
      - <span data-ttu-id="c1496-140">**Info**     Collecte uniquement les messages de suivi qui indiquent un message d’information pour le fournisseur défini, ainsi que les messages d’erreur et d’avertissement fatals.</span><span class="sxs-lookup"><span data-stu-id="c1496-140">**Info**   Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
      - <span data-ttu-id="c1496-141">**Commentaires**     Collecte tous les messages de suivi de type fatal, Error, Warning et info pour le fournisseur défini.</span><span class="sxs-lookup"><span data-stu-id="c1496-141">**Verbose**   Collects all trace messages of type fatal, error, warning and info for the defined provider.</span></span>

  - <span data-ttu-id="c1496-142">**Indicateurs**     OCSLogger a fourni l’option permettant de choisir des indicateurs pour chaque fournisseur qui a défini le type d’informations que vous pouvez récupérer dans les fichiers de suivi.</span><span class="sxs-lookup"><span data-stu-id="c1496-142">**Flags**   OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="c1496-143">Vous pouvez choisir les indicateurs suivants selon le fournisseur :</span><span class="sxs-lookup"><span data-stu-id="c1496-143">You can chose the following flags, based on the provider:</span></span>
    
      - <span data-ttu-id="c1496-144">**Tf \_ Connection**     fournit des entrées de journal liées à la connexion.</span><span class="sxs-lookup"><span data-stu-id="c1496-144">**TF\_Connection**   Provides connection-related log entries.</span></span> <span data-ttu-id="c1496-145">Ces journaux incluent des informations sur les connexions établies depuis et vers un composant particulier.</span><span class="sxs-lookup"><span data-stu-id="c1496-145">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="c1496-146">Ils peuvent également comprendre des informations importantes au niveau du réseau (c’est-à-dire, pour les composants sans le concept d’une connexion).</span><span class="sxs-lookup"><span data-stu-id="c1496-146">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
      - <span data-ttu-id="c1496-147">**Tf \_ La sécurité**     fournit tous les événements/entrées du journal liés à la sécurité.</span><span class="sxs-lookup"><span data-stu-id="c1496-147">**TF\_Security**   Provides all events/log entries related to security.</span></span> <span data-ttu-id="c1496-148">Par exemple, pour SipStack, il s’agit d’événements de sécurité tels que les échecs de validation de domaine et les échecs d’authentification ou d’autorisation du client.</span><span class="sxs-lookup"><span data-stu-id="c1496-148">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
      - <span data-ttu-id="c1496-149">**Tf \_ Diag**     fournit des événements de diagnostic que vous pouvez utiliser pour diagnostiquer ou dépanner le composant.</span><span class="sxs-lookup"><span data-stu-id="c1496-149">**TF\_Diag**   Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="c1496-150">Par exemple, pour SipStack, il s’agit d’échecs de certificat ou d’avertissements/erreurs DNS.</span><span class="sxs-lookup"><span data-stu-id="c1496-150">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
      - <span data-ttu-id="c1496-151">**Tf \_ Protocole**     fournit des messages de protocole, tels que SIP et les messages du Pack de codecs communautaires combinés.</span><span class="sxs-lookup"><span data-stu-id="c1496-151">**TF\_Protocol**   Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
      - <span data-ttu-id="c1496-152">**Tf \_ Le composant**     active la journalisation sur les composants spécifiés dans le cadre des fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="c1496-152">**TF\_Component**   Enables logging on the components specified as part of the providers.</span></span>
    
      - <span data-ttu-id="c1496-153">**Tous les**     Définit tous les indicateurs disponibles pour le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="c1496-153">**All**   Sets all available flags available for the provider.</span></span>

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="c1496-154">Pour consulter les informations sur les fournisseurs de scénarios de service de journalisation centralisée existants</span><span class="sxs-lookup"><span data-stu-id="c1496-154">To review information about existing Centralized Logging Service scenario providers</span></span>

1.  <span data-ttu-id="c1496-155">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c1496-155">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c1496-156">Pour examiner la configuration de fournisseurs existants, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="c1496-156">To review the configuration of existing providers, type the following:</span></span>
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    <span data-ttu-id="c1496-157">Par exemple, pour examiner des informations sur l’Intendant Conférence global, tapez :</span><span class="sxs-lookup"><span data-stu-id="c1496-157">For example, to review information about the global conferencing attendant, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA"
    
    <span data-ttu-id="c1496-158">La commande affiche une liste de fournisseurs avec les indicateurs, paramètres et composants associés.</span><span class="sxs-lookup"><span data-stu-id="c1496-158">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="c1496-159">Si les informations affichées ne sont pas suffisantes ou si la liste est trop longue pour le format de liste Windows PowerShell par défaut, vous pouvez afficher des informations supplémentaires en définissant une autre méthode de sortie.</span><span class="sxs-lookup"><span data-stu-id="c1496-159">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="c1496-160">Pour cela, tapez :</span><span class="sxs-lookup"><span data-stu-id="c1496-160">To do this, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    <span data-ttu-id="c1496-161">La sortie de cette commande affiche chaque fournisseur sur cinq lignes avec le nom du fournisseur, le type de journalisation, le niveau d’enregistrement, les indicateurs, le GUID et le rôle sur une ligne distincte.</span><span class="sxs-lookup"><span data-stu-id="c1496-161">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span>

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="c1496-162">Pour définir un nouveau fournisseur de scénario de service de journalisation centralisée</span><span class="sxs-lookup"><span data-stu-id="c1496-162">To define a new Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="c1496-163">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c1496-163">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c1496-p113">Un fournisseur de scénario se compose d’un composant à suivre, d’indicateurs à utiliser et d’un niveau de détail à collecter. Pour cela, tapez :</span><span class="sxs-lookup"><span data-stu-id="c1496-p113">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect. You do this by typing:</span></span>
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    <span data-ttu-id="c1496-166">Par exemple, une définition de fournisseur de suivi qui définit ce qu’il faut collecter à partir du fournisseur Lyss et à quel niveau de détail ressemble à ceci :</span><span class="sxs-lookup"><span data-stu-id="c1496-166">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

<span data-ttu-id="c1496-167">–Level collecte les messages Fatal, Error, Warning et Info.</span><span class="sxs-lookup"><span data-stu-id="c1496-167">The –Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="c1496-168">Les indicateurs utilisés sont tous ceux définis pour le fournisseur Lyss, et incluent la \_ connexion TF, TF \_ diag et TF \_ Protocol.</span><span class="sxs-lookup"><span data-stu-id="c1496-168">The flags used are all of those defined for the Lyss provider, and include TF\_Connection, TF\_Diag and TF\_Protocol.</span></span>

<span data-ttu-id="c1496-169">Après avoir défini la variable $LyssProvider, vous pouvez l’utiliser avec la nouvelle applet de commande **New-CsClsScenario** pour collecter des suivis à partir du fournisseur Lyss.</span><span class="sxs-lookup"><span data-stu-id="c1496-169">After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="c1496-170">Pour terminer la création du fournisseur et son affectation à un nouveau scénario, tapez :</span><span class="sxs-lookup"><span data-stu-id="c1496-170">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="c1496-171">Où $LyssProvider est la variable qui contient le scénario défini créé avec **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="c1496-171">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="c1496-172">Pour modifier un fournisseur de scénario de service de journalisation centralisé existant</span><span class="sxs-lookup"><span data-stu-id="c1496-172">To change an existing Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="c1496-173">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c1496-173">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c1496-174">Pour mettre à jour ou modifier la configuration d’un fournisseur existant, tapez :</span><span class="sxs-lookup"><span data-stu-id="c1496-174">To update or change the configuration of an existing provider, type:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    <span data-ttu-id="c1496-175">Vous pouvez ensuite mettre à jour le scénario pour affecter le fournisseur en tapant ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="c1496-175">You then update the scenario to assign the provider by typing the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="c1496-176">À l’issue de l’exécution de la commande, des indicateurs et un niveau mis à jour pour le fournisseur sont affectés au scénario site:Redmond/RedmondLyssInfo.</span><span class="sxs-lookup"><span data-stu-id="c1496-176">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="c1496-177">Vous pouvez examiner le nouveau scénario en utilisant Get-CsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="c1496-177">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="c1496-178">Pour plus d’informations, voir [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).</span><span class="sxs-lookup"><span data-stu-id="c1496-178">For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).</span></span>

<div class="">


> [!WARNING]  
> <span data-ttu-id="c1496-179"><STRONG>New-ClsCsProvider</STRONG> ne vérifie pas si les indicateurs sont valides.</span><span class="sxs-lookup"><span data-stu-id="c1496-179"><STRONG>New-ClsCsProvider</STRONG> does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="c1496-180">Assurez-vous que les indicateurs (par exemple, TF_DIAG ou TF_CONNECTION) sont correctement épelés.</span><span class="sxs-lookup"><span data-stu-id="c1496-180">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="c1496-181">Si ce n’est pas le cas, le fournisseur ne peut pas retourner les informations du journal attendues.</span><span class="sxs-lookup"><span data-stu-id="c1496-181">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>



</div>

<span data-ttu-id="c1496-182">Si vous souhaitez ajouter des fournisseurs supplémentaires à ce scénario, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="c1496-182">If you want to add additional providers to this scenario, type the following:</span></span>

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

<span data-ttu-id="c1496-183">Où chaque fournisseur défini avec la directive Add a déjà été défini à l’aide du processus **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="c1496-183">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="c1496-184">Pour supprimer un fournisseur de scénario</span><span class="sxs-lookup"><span data-stu-id="c1496-184">To remove a scenario provider</span></span>

1.  <span data-ttu-id="c1496-185">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c1496-185">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c1496-186">Les applets de commande fournies vous permettent de mettre à jour des fournisseurs existants et de créer de nouveaux fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="c1496-186">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="c1496-187">Pour supprimer un fournisseur, vous devez utiliser la directive Replace pour le paramètre Provider pour **Set-CsClsScenario**.</span><span class="sxs-lookup"><span data-stu-id="c1496-187">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="c1496-188">La seule façon de supprimer complètement un fournisseur est de le remplacer par un fournisseur redéfini du même nom et d’utiliser la directive Update.</span><span class="sxs-lookup"><span data-stu-id="c1496-188">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="c1496-189">Par exemple, notre fournisseur LyssProvider est défini avec WPP comme type de journal, niveau défini sur déboguer et ensemble d’indicateurs sont \_ connexion TF et TF \_ diag.</span><span class="sxs-lookup"><span data-stu-id="c1496-189">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF\_CONNECTION and TF\_DIAG.</span></span> <span data-ttu-id="c1496-190">Vous devez affecter aux indicateurs la valeur « All ».</span><span class="sxs-lookup"><span data-stu-id="c1496-190">You need to change the flags to “All”.</span></span> <span data-ttu-id="c1496-191">Pour modifier le fournisseur, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="c1496-191">To change the provider, type the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  <span data-ttu-id="c1496-192">Si vous souhaitez supprimer complètement un scénario et les fournisseurs associés à celui-ci, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="c1496-192">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    <span data-ttu-id="c1496-193">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="c1496-193">For example:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="c1496-194">L’applet de commande <STRONG>Remove-CsClsScenario</STRONG> ne vous demande pas confirmation.</span><span class="sxs-lookup"><span data-stu-id="c1496-194">The cmdlet <STRONG>Remove-CsClsScenario</STRONG> does not prompt you for confirmation.</span></span> <span data-ttu-id="c1496-195">Le scénario est supprimé, ainsi que les fournisseurs affectés à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="c1496-195">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="c1496-196">Vous pouvez recréer le scénario en réexécutant les commandes que vous avez utilisées pour le créer initialement.</span><span class="sxs-lookup"><span data-stu-id="c1496-196">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="c1496-197">Il n’existe aucune procédure pour récupérer des scénarios ou des fournisseurs supprimés.</span><span class="sxs-lookup"><span data-stu-id="c1496-197">There is no procedure to recover removed scenarios or providers.</span></span>

    
    </div>

<span data-ttu-id="c1496-198">Lorsque vous supprimez un scénario à l’aide de l’applet de commande **Remove-CsClsScenario**, vous supprimez complètement le scénario de l’étendue.</span><span class="sxs-lookup"><span data-stu-id="c1496-198">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="c1496-199">Pour utiliser les scénarios que vous avez créés et les fournisseurs qui faisaient partie du scénario, vous devez créer de nouveaux fournisseurs et les affecter à un nouveau scénario.</span><span class="sxs-lookup"><span data-stu-id="c1496-199">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c1496-200">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c1496-200">See Also</span></span>


[<span data-ttu-id="c1496-201">Get-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="c1496-201">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[<span data-ttu-id="c1496-202">New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="c1496-202">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[<span data-ttu-id="c1496-203">Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="c1496-203">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[<span data-ttu-id="c1496-204">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="c1496-204">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[<span data-ttu-id="c1496-205">New-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="c1496-205">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


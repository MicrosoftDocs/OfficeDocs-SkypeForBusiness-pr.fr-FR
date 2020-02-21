---
title: 'Lync Server 2013 : configuration des fournisseurs pour le service de journalisation centralisée'
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
ms.openlocfilehash: 1bc8ad2f5372ee9b434a1236e9d0cbba0f34a5de
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="444da-102">Configuration des fournisseurs pour le service de journalisation centralisée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="444da-102">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="444da-103">_**Dernière modification de la rubrique :** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="444da-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="444da-104">Les concepts et la configuration des *fournisseurs* dans le service de journalisation centralisée sont les plus importants à comprendre.</span><span class="sxs-lookup"><span data-stu-id="444da-104">The concepts and configuration of *providers* in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="444da-105">Les *fournisseurs* mappent directement vers les composants de rôle serveur Lync Server dans le modèle de suivi Lync Server.</span><span class="sxs-lookup"><span data-stu-id="444da-105">The *providers* map directly to Lync Server server role components in the Lync Server tracing model.</span></span> <span data-ttu-id="444da-106">Le fournisseur définit les composants d’un Lync Server 2013 qui seront suivis, le type de messages (par exemple, fatal, erreur ou avertissement) à collecter, ainsi que les indicateurs (par exemple, TF\_Connection ou TF\_diag).</span><span class="sxs-lookup"><span data-stu-id="444da-106">The provider defines the components of a Lync Server 2013 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF\_Connection or TF\_Diag).</span></span> <span data-ttu-id="444da-107">Les fournisseurs sont les composants traçables dans chaque rôle serveur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="444da-107">Providers are the traceable components in each Lync Server server role.</span></span> <span data-ttu-id="444da-108">À l’aide de fournisseurs, vous définissez le niveau et le type de suivi sur les composants (par exemple, S4, SIPStack, Messagerie instantanée et Présence).</span><span class="sxs-lookup"><span data-stu-id="444da-108">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="444da-109">Le fournisseur défini est utilisé dans un scénario pour regrouper tous les fournisseurs d’une collection logique donnée qui répondent à une condition de problème spécifique.</span><span class="sxs-lookup"><span data-stu-id="444da-109">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>

<span data-ttu-id="444da-110">Pour exécuter les fonctions du service de journalisation centralisée à l’aide de Lync Server Management Shell, vous devez être membre des groupes de sécurité CsAdministrator ou RBAC (contrôle d’accès basé sur un rôle) CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’une des ces deux groupes.</span><span class="sxs-lookup"><span data-stu-id="444da-110">To run the Centralized Logging Service functions using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="444da-111">Pour renvoyer la liste de tous les rôles RBAC (contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de Lync Server Management Shell ou de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="444da-111">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="444da-112">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="444da-112">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="444da-113">Le reste de cette rubrique porte sur la définition des fournisseurs, la modification d’un fournisseur et ce que contient une définition de fournisseur afin d’optimiser le dépannage.</span><span class="sxs-lookup"><span data-stu-id="444da-113">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="444da-114">Il existe deux façons d’émettre des commandes de service de journalisation centralisée.</span><span class="sxs-lookup"><span data-stu-id="444da-114">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="444da-115">Vous pouvez utiliser le CLSController. exe qui se trouve, par défaut, dans le répertoire C :\\Program Files\\Common files\\Microsoft Lync Server 2013\\CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="444da-115">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="444da-116">Vous pouvez utiliser Lync Server Management Shell pour émettre des commandes Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="444da-116">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="444da-117">Il est important de noter que lorsque vous utilisez CLSController.exe à la ligne de commande, la sélection de scénarios disponibles dans lesquels les fournisseurs sont déjà définis est limitée et non modifiable ; toutefois, vous pouvez définir le niveau de journalisation.</span><span class="sxs-lookup"><span data-stu-id="444da-117">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available in which the providers are already defined and are not changeable, but you can define the log level.</span></span> <span data-ttu-id="444da-118">À l’aide de Windows PowerShell, vous pouvez définir de nouveaux fournisseurs à utiliser dans vos sessions de journalisation et disposer d’un contrôle total sur leur création, leur collecte et leur niveau de collecte des données.</span><span class="sxs-lookup"><span data-stu-id="444da-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="444da-p104">Comme nous l’avons précédemment mentionné, les fournisseurs sont très puissants. Cependant, les scénarios le sont davantage, et ce du fait qu’ils contiennent toutes les informations nécessaires pour définir et exécuter le suivi sur les composants que les fournisseurs représentent. Les scénarios étant une collection de fournisseurs, une certaine analogie peut être établie entre, d’une part, l’exécution d’un fichier de commandes qui contient des centaines de commandes destinées à collecter une grande quantité d’informations et, d’autre part, l’émission de centaines de commandes, une à la fois, à la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="444da-p104">As mentioned, providers are very powerful. However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent. With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span><BR><span data-ttu-id="444da-122">Au lieu de vous demander d’approfondir les détails des fournisseurs, le service de journalisation centralisée fournit un certain nombre de scénarios qui sont déjà définis pour vous.</span><span class="sxs-lookup"><span data-stu-id="444da-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="444da-123">Les scénarios fournis couvrent la grande majorité des problèmes que vous êtes susceptible de rencontrer.</span><span class="sxs-lookup"><span data-stu-id="444da-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="444da-124">Dans de rares cas, vous devrez créer et définir des fournisseurs et les affecter à des scénarios.</span><span class="sxs-lookup"><span data-stu-id="444da-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="444da-125">Nous vous recommandons fortement de vous familiariser avec chacun des scénarios fournis avant d’étudier la nécessité de créer de nouveaux scénarios et de nouveaux fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="444da-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="444da-126">Bien que des informations sur la création de fournisseurs sont données ici pour vous familiariser avec la façon dont les scénarios utilisent les éléments des fournisseurs pour collecter des informations de suivi, aucun détail sur les fournisseurs eux-mêmes n’est fourni pour le moment.</span><span class="sxs-lookup"><span data-stu-id="444da-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span>



</div>

<span data-ttu-id="444da-127">Introduits dans [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), les éléments clés de la définition d’un fournisseur à utiliser dans un scénario sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="444da-127">Introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>

  - <span data-ttu-id="444da-128">**Fournisseurs**   si vous êtes familiarisé avec OCSLogger, les fournisseurs sont les composants que vous choisissez pour indiquer à OCSLogger ce que le moteur de suivi doit collecter dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="444da-128">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="444da-129">Les fournisseurs sont les mêmes composants et, dans de nombreux cas, ont le même nom que les composants dans OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="444da-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="444da-130">Si vous n’êtes pas familiarisé avec OCSLogger, les fournisseurs sont des composants spécifiques au rôle serveur, dont le service de journalisation centralisée peut collecter des journaux.</span><span class="sxs-lookup"><span data-stu-id="444da-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="444da-131">Dans le cas du service de journalisation centralisée, le CLSAgent est la partie architecturale du service de journalisation centralisée qui effectue le suivi des composants que vous définissez dans la configuration des fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="444da-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>

  - <span data-ttu-id="444da-132">**Niveaux de journalisation**   OCSLogger offre la possibilité de choisir un certain nombre de niveaux de détail pour les données collectées.</span><span class="sxs-lookup"><span data-stu-id="444da-132">**Logging levels**   OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="444da-133">Cette fonctionnalité fait partie intégrante du service de journalisation centralisée et des scénarios, et est définie par le paramètre **type** .</span><span class="sxs-lookup"><span data-stu-id="444da-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="444da-134">Vous pouvez choisir l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="444da-134">You can choose from the following:</span></span>
    
      - <span data-ttu-id="444da-135">**All collecte les**   messages de suivi de type fatal, Error, Warning et info dans le journal pour le fournisseur défini.</span><span class="sxs-lookup"><span data-stu-id="444da-135">**All**   Collects trace messages of type fatal, error, warning, and info to the log for the defined provider.</span></span>
    
      - <span data-ttu-id="444da-136">**Fatal**   collecte uniquement les messages de suivi qui indiquent un échec pour le fournisseur défini.</span><span class="sxs-lookup"><span data-stu-id="444da-136">**Fatal**   Collects only the trace messages that indicate a failure for the defined provider.</span></span>
    
      - <span data-ttu-id="444da-137">**Error**   collecte uniquement les messages de suivi qui indiquent une erreur pour le fournisseur défini, ainsi que les messages irrécupérables.</span><span class="sxs-lookup"><span data-stu-id="444da-137">**Error**   Collects only the trace messages that indicate an error for the defined provider, plus fatal messages.</span></span>
    
      - <span data-ttu-id="444da-138">**Warning**   collecte uniquement les messages de suivi qui indiquent un avertissement pour le fournisseur défini, ainsi que les messages d’erreur et fatale.</span><span class="sxs-lookup"><span data-stu-id="444da-138">**Warning**   Collects only the trace messages that indicate a warning for the defined provider, plus fatal and error messages.</span></span>
    
      - <span data-ttu-id="444da-139">**Info**   collecte uniquement les messages de suivi qui indiquent un message d’information pour le fournisseur défini, ainsi que les messages d’erreur fatale, d’erreur et d’avertissement.</span><span class="sxs-lookup"><span data-stu-id="444da-139">**Info**   Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
      - <span data-ttu-id="444da-140">**Verbose**   collecte tous les messages de suivi de type fatal, Error, Warning et info pour le fournisseur défini.</span><span class="sxs-lookup"><span data-stu-id="444da-140">**Verbose**   Collects all trace messages of type fatal, error, warning and info for the defined provider.</span></span>

  - <span data-ttu-id="444da-141">**Indicateurs**   OCSLogger offre la possibilité de choisir des indicateurs pour chaque fournisseur définissant le type d’informations que vous pouvez récupérer dans les fichiers de suivi.</span><span class="sxs-lookup"><span data-stu-id="444da-141">**Flags**   OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="444da-142">Vous pouvez choisir les indicateurs suivants selon le fournisseur :</span><span class="sxs-lookup"><span data-stu-id="444da-142">You can chose the following flags, based on the provider:</span></span>
    
      - <span data-ttu-id="444da-143">**TF\_Connection**   fournit des entrées de journal liées à la connexion.</span><span class="sxs-lookup"><span data-stu-id="444da-143">**TF\_Connection**   Provides connection-related log entries.</span></span> <span data-ttu-id="444da-144">Ces journaux incluent des informations sur les connexions établies depuis et vers un composant particulier.</span><span class="sxs-lookup"><span data-stu-id="444da-144">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="444da-145">Ils peuvent également comprendre des informations importantes au niveau du réseau (c’est-à-dire, pour les composants sans le concept d’une connexion).</span><span class="sxs-lookup"><span data-stu-id="444da-145">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
      - <span data-ttu-id="444da-146">**TF\_Security**   fournit tous les événements/entrées de journal liés à la sécurité.</span><span class="sxs-lookup"><span data-stu-id="444da-146">**TF\_Security**   Provides all events/log entries related to security.</span></span> <span data-ttu-id="444da-147">Par exemple, pour SipStack, il s’agit d’événements de sécurité tels que les échecs de validation de domaine et les échecs d’authentification ou d’autorisation du client.</span><span class="sxs-lookup"><span data-stu-id="444da-147">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
      - <span data-ttu-id="444da-148">**TF\_diag**   fournit des événements de diagnostic que vous pouvez utiliser pour diagnostiquer ou dépanner le composant.</span><span class="sxs-lookup"><span data-stu-id="444da-148">**TF\_Diag**   Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="444da-149">Par exemple, pour SipStack, il s’agit d’échecs de certificat ou d’avertissements/erreurs DNS.</span><span class="sxs-lookup"><span data-stu-id="444da-149">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
      - <span data-ttu-id="444da-150">**Le\_protocole**   TF fournit des messages de protocole, tels que SIP et les messages du Pack de codecs communautaires combinés.</span><span class="sxs-lookup"><span data-stu-id="444da-150">**TF\_Protocol**   Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
      - <span data-ttu-id="444da-151">**Le\_composant**   TF active la journalisation sur les composants spécifiés dans le cadre des fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="444da-151">**TF\_Component**   Enables logging on the components specified as part of the providers.</span></span>
    
      - <span data-ttu-id="444da-152">**All**   définit tous les indicateurs disponibles pour le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="444da-152">**All**   Sets all available flags available for the provider.</span></span>

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="444da-153">Pour consulter les informations sur les fournisseurs de scénarios de service de journalisation centralisée existants</span><span class="sxs-lookup"><span data-stu-id="444da-153">To review information about existing Centralized Logging Service scenario providers</span></span>

1.  <span data-ttu-id="444da-154">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="444da-154">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="444da-155">Pour examiner la configuration de fournisseurs existants, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="444da-155">To review the configuration of existing providers, type the following:</span></span>
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    <span data-ttu-id="444da-156">Par exemple, pour examiner des informations sur l’Intendant Conférence global, tapez :</span><span class="sxs-lookup"><span data-stu-id="444da-156">For example, to review information about the global conferencing attendant, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA"
    
    <span data-ttu-id="444da-157">La commande affiche une liste de fournisseurs avec les indicateurs, paramètres et composants associés.</span><span class="sxs-lookup"><span data-stu-id="444da-157">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="444da-158">Si les informations affichées ne sont pas suffisantes ou si la liste est trop longue pour le format de liste Windows PowerShell par défaut, vous pouvez afficher des informations supplémentaires en définissant une autre méthode de sortie.</span><span class="sxs-lookup"><span data-stu-id="444da-158">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="444da-159">Pour cela, tapez :</span><span class="sxs-lookup"><span data-stu-id="444da-159">To do this, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    <span data-ttu-id="444da-160">La sortie de cette commande affiche chaque fournisseur sur cinq lignes avec le nom du fournisseur, le type de journalisation, le niveau d’enregistrement, les indicateurs, le GUID et le rôle sur une ligne distincte.</span><span class="sxs-lookup"><span data-stu-id="444da-160">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span>

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="444da-161">Pour définir un nouveau fournisseur de scénario de service de journalisation centralisée</span><span class="sxs-lookup"><span data-stu-id="444da-161">To define a new Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="444da-162">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="444da-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="444da-p113">Un fournisseur de scénario se compose d’un composant à suivre, d’indicateurs à utiliser et d’un niveau de détail à collecter. Pour cela, tapez :</span><span class="sxs-lookup"><span data-stu-id="444da-p113">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect. You do this by typing:</span></span>
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    <span data-ttu-id="444da-165">Par exemple, une définition de fournisseur de suivi qui définit ce qu’il faut collecter à partir du fournisseur Lyss et à quel niveau de détail ressemble à ceci :</span><span class="sxs-lookup"><span data-stu-id="444da-165">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

<span data-ttu-id="444da-166">–Level collecte les messages Fatal, Error, Warning et Info.</span><span class="sxs-lookup"><span data-stu-id="444da-166">The –Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="444da-167">Les indicateurs utilisés sont tous ceux définis pour le fournisseur Lyss, et incluent la connexion\_TF, TF\_diag et TF\_Protocol.</span><span class="sxs-lookup"><span data-stu-id="444da-167">The flags used are all of those defined for the Lyss provider, and include TF\_Connection, TF\_Diag and TF\_Protocol.</span></span>

<span data-ttu-id="444da-168">Après avoir défini la variable $LyssProvider, vous pouvez l’utiliser avec la nouvelle applet de commande **New-CsClsScenario** pour collecter des suivis à partir du fournisseur Lyss.</span><span class="sxs-lookup"><span data-stu-id="444da-168">After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="444da-169">Pour terminer la création du fournisseur et son affectation à un nouveau scénario, tapez :</span><span class="sxs-lookup"><span data-stu-id="444da-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="444da-170">Où $LyssProvider est la variable qui contient le scénario défini créé avec **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="444da-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="444da-171">Pour modifier un fournisseur de scénario de service de journalisation centralisé existant</span><span class="sxs-lookup"><span data-stu-id="444da-171">To change an existing Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="444da-172">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="444da-172">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="444da-173">Pour mettre à jour ou modifier la configuration d’un fournisseur existant, tapez :</span><span class="sxs-lookup"><span data-stu-id="444da-173">To update or change the configuration of an existing provider, type:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    <span data-ttu-id="444da-174">Vous pouvez ensuite mettre à jour le scénario pour affecter le fournisseur en tapant ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="444da-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="444da-175">À l’issue de l’exécution de la commande, des indicateurs et un niveau mis à jour pour le fournisseur sont affectés au scénario site:Redmond/RedmondLyssInfo.</span><span class="sxs-lookup"><span data-stu-id="444da-175">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="444da-176">Vous pouvez examiner le nouveau scénario en utilisant Get-CsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="444da-176">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="444da-177">Pour plus d’informations, voir [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).</span><span class="sxs-lookup"><span data-stu-id="444da-177">For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).</span></span>

<div class="">


> [!WARNING]  
> <span data-ttu-id="444da-178"><STRONG>New-ClsCsProvider</STRONG> ne vérifie pas si les indicateurs sont valides.</span><span class="sxs-lookup"><span data-stu-id="444da-178"><STRONG>New-ClsCsProvider</STRONG> does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="444da-179">Assurez-vous que les indicateurs (par exemple, TF_DIAG ou TF_CONNECTION) sont correctement épelés.</span><span class="sxs-lookup"><span data-stu-id="444da-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="444da-180">Si ce n’est pas le cas, le fournisseur ne peut pas retourner les informations du journal attendues.</span><span class="sxs-lookup"><span data-stu-id="444da-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>



</div>

<span data-ttu-id="444da-181">Si vous souhaitez ajouter des fournisseurs supplémentaires à ce scénario, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="444da-181">If you want to add additional providers to this scenario, type the following:</span></span>

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

<span data-ttu-id="444da-182">Où chaque fournisseur défini avec la directive Add a déjà été défini à l’aide du processus **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="444da-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="444da-183">Pour supprimer un fournisseur de scénario</span><span class="sxs-lookup"><span data-stu-id="444da-183">To remove a scenario provider</span></span>

1.  <span data-ttu-id="444da-184">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="444da-184">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="444da-185">Les applets de commande fournies vous permettent de mettre à jour des fournisseurs existants et de créer de nouveaux fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="444da-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="444da-186">Pour supprimer un fournisseur, vous devez utiliser la directive Replace pour le paramètre Provider pour **Set-CsClsScenario**.</span><span class="sxs-lookup"><span data-stu-id="444da-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="444da-187">La seule façon de supprimer complètement un fournisseur est de le remplacer par un fournisseur redéfini du même nom et d’utiliser la directive Update.</span><span class="sxs-lookup"><span data-stu-id="444da-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="444da-188">Par exemple, notre fournisseur LyssProvider est défini avec WPP comme type de journal, niveau défini sur déboguer et ensemble d’indicateurs\_sont connexion TF\_et TF diag.</span><span class="sxs-lookup"><span data-stu-id="444da-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF\_CONNECTION and TF\_DIAG.</span></span> <span data-ttu-id="444da-189">Vous devez affecter aux indicateurs la valeur « All ».</span><span class="sxs-lookup"><span data-stu-id="444da-189">You need to change the flags to “All”.</span></span> <span data-ttu-id="444da-190">Pour modifier le fournisseur, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="444da-190">To change the provider, type the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  <span data-ttu-id="444da-191">Si vous souhaitez supprimer complètement un scénario et les fournisseurs associés à celui-ci, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="444da-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    <span data-ttu-id="444da-192">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="444da-192">For example:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="444da-193">L’applet de commande <STRONG>Remove-CsClsScenario</STRONG> ne vous demande pas confirmation.</span><span class="sxs-lookup"><span data-stu-id="444da-193">The cmdlet <STRONG>Remove-CsClsScenario</STRONG> does not prompt you for confirmation.</span></span> <span data-ttu-id="444da-194">Le scénario est supprimé, ainsi que les fournisseurs affectés à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="444da-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="444da-195">Vous pouvez recréer le scénario en réexécutant les commandes que vous avez utilisées pour le créer initialement.</span><span class="sxs-lookup"><span data-stu-id="444da-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="444da-196">Il n’existe aucune procédure pour récupérer des scénarios ou des fournisseurs supprimés.</span><span class="sxs-lookup"><span data-stu-id="444da-196">There is no procedure to recover removed scenarios or providers.</span></span>

    
    </div>

<span data-ttu-id="444da-197">Lorsque vous supprimez un scénario à l’aide de l’applet de commande **Remove-CsClsScenario**, vous supprimez complètement le scénario de l’étendue.</span><span class="sxs-lookup"><span data-stu-id="444da-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="444da-198">Pour utiliser les scénarios que vous avez créés et les fournisseurs qui faisaient partie du scénario, vous devez créer de nouveaux fournisseurs et les affecter à un nouveau scénario.</span><span class="sxs-lookup"><span data-stu-id="444da-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="444da-199">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="444da-199">See Also</span></span>


[<span data-ttu-id="444da-200">Get-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="444da-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[<span data-ttu-id="444da-201">New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="444da-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[<span data-ttu-id="444da-202">Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="444da-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[<span data-ttu-id="444da-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="444da-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[<span data-ttu-id="444da-204">New-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="444da-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


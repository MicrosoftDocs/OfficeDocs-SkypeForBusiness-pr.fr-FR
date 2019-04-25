---
title: Configuration des fournisseurs pour le service de journalisation centralisée dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 'Résumé : Découvrez comment configurer des fournisseurs de scénario pour le Service de journalisation centralisée Skype pour Business Server 2015.'
ms.openlocfilehash: 36eb16eb1aea584e1ca28670ea75bd3a262ceb1a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217501"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="a286d-103">Configuration des fournisseurs pour le service de journalisation centralisée dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="a286d-103">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a286d-104">**Résumé :** Découvrez comment configurer des fournisseurs de scénario pour le Service de journalisation centralisée Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a286d-104">**Summary:** Learn how to configure scenario providers for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a286d-105">Les concepts et la configuration de fournisseurs de Service de journalisation centralisée est un des plus importants à comprendre.</span><span class="sxs-lookup"><span data-stu-id="a286d-105">The concepts and configuration of providers in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="a286d-106">Theproviders correspondent directement aux Skype pour les composants de rôle de serveur Business Server dans le Skype pour le modèle de suivi du serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="a286d-106">Theproviders map directly to Skype for Business Server server role components in the Skype for Business Server tracing model.</span></span> <span data-ttu-id="a286d-107">Le fournisseur définit les composants d’un Skype pour Business Server 2015 qui vont être tracées, le type de messages (par exemple, irrécupérable, erreur ou avertissement) pour collecter et les indicateurs (par exemple, TF_Connection ou TF_Diag).</span><span class="sxs-lookup"><span data-stu-id="a286d-107">The provider defines the components of a Skype for Business Server 2015 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF_Connection or TF_Diag).</span></span> <span data-ttu-id="a286d-108">Fournisseurs sont les composants reconstituer dans chaque Skype pour le rôle de serveur Business Server.</span><span class="sxs-lookup"><span data-stu-id="a286d-108">Providers are the traceable components in each Skype for Business Server server role.</span></span> <span data-ttu-id="a286d-109">À l’aide de fournisseurs, vous définissez le niveau et le type de suivi sur les composants (par exemple, S4, SIPStack, Messagerie instantanée et Présence).</span><span class="sxs-lookup"><span data-stu-id="a286d-109">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="a286d-110">Le fournisseur défini est utilisé dans un scénario pour regrouper tous les fournisseurs d’une collection logique donnée qui répondent à une condition de problème spécifique.</span><span class="sxs-lookup"><span data-stu-id="a286d-110">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>
  
<span data-ttu-id="a286d-111">Pour exécuter les fonctions de Service de journalisation centralisée à l’aide de la Skype pour Business Server Management Shell, vous devez être un membre de la CsAdministrator ou les groupes de sécurité CsServerAdministrator accès basé sur un rôle RBAC (contrôle) ou un rôle RBAC personnalisé qui contient une de ces deux groupes.</span><span class="sxs-lookup"><span data-stu-id="a286d-111">To run the Centralized Logging Service functions using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="a286d-112">Pour retourner une liste de tous les rôles RBAC (contrôle) d’accès basé sur le rôle de cette applet de commande a été assigné (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de la Skype pour Business Server Management Shell ou de Windows PowerShell invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="a286d-112">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="a286d-113">Exemple :</span><span class="sxs-lookup"><span data-stu-id="a286d-113">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="a286d-114">Le reste de cette rubrique met l’accent sur la définition des fournisseurs, la modification d’un fournisseur et la spécification du contenu d’un fournisseur afin d’optimiser votre dépannage.</span><span class="sxs-lookup"><span data-stu-id="a286d-114">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="a286d-115">Il existe deux façons d’émettre des commandes de Service de journalisation centralisée.</span><span class="sxs-lookup"><span data-stu-id="a286d-115">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="a286d-116">Vous pouvez utiliser le fichier CLSController.exe qui se trouve, par défaut, dans le répertoire C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="a286d-116">You can use the CLSController.exe that is located, by default, in the directory C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent.</span></span> <span data-ttu-id="a286d-117">Ou bien, vous pouvez utiliser la Skype pour Business Server Management Shell pour exécuter des commandes de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a286d-117">Or, you can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="a286d-118">À l’aide de Windows PowerShell, vous pouvez définir des nouveaux fournisseurs à utiliser dans vos sessions de journalisation et contrôler leur création, qu’ils collectent, et à quel niveau collecter des données.</span><span class="sxs-lookup"><span data-stu-id="a286d-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a286d-p104">Comme nous l’avons précédemment mentionné, les fournisseurs sont très puissants. Cependant, les scénarios le sont davantage, et ce du fait qu’ils contiennent toutes les informations nécessaires pour définir et exécuter le suivi sur les composants que les fournisseurs représentent. Les scénarios étant une collection de fournisseurs, une certaine analogie peut être établie entre, d’une part, l’exécution d’un fichier de commandes qui contient des centaines de commandes destinées à collecter une grande quantité d’informations et, d’autre part, l’émission de centaines de commandes, une à la fois, à la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="a286d-p104">As mentioned, providers are very powerful. However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent. With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span> 
  
<span data-ttu-id="a286d-122">Au lieu de devoir approfondir profondément les détails des fournisseurs, le Service de journalisation centralisée fournit un certain nombre de scénarios qui sont déjà définies pour vous.</span><span class="sxs-lookup"><span data-stu-id="a286d-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="a286d-123">Les scénarios fournis couvrent la grande majorité des problèmes que vous êtes susceptible de rencontrer.</span><span class="sxs-lookup"><span data-stu-id="a286d-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="a286d-124">Dans de rares cas, vous devrez créer et définir des fournisseurs et les affecter à des scénarios.</span><span class="sxs-lookup"><span data-stu-id="a286d-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="a286d-125">Nous vous recommandons fortement de vous familiariser avec chacun des scénarios fournis avant d’étudier la nécessité de créer de nouveaux scénarios et de nouveaux fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="a286d-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="a286d-126">Bien que des informations sur la création de fournisseurs sont données ici pour vous familiariser avec la façon dont les scénarios utilisent les éléments des fournisseurs pour collecter des informations de suivi, aucun détail sur les fournisseurs eux-mêmes n’est fourni pour le moment.</span><span class="sxs-lookup"><span data-stu-id="a286d-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span> 
  
<span data-ttu-id="a286d-127">Introduite dans [Centralized Logging Service dans Skype pour Business 2015](centralized-logging-service.md), les éléments clés de la définition d’un fournisseur à utiliser dans un scénario sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="a286d-127">Introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>
  
- <span data-ttu-id="a286d-128">**Fournisseurs** Si vous êtes familiarisé avec OCSLogger, fournisseurs sont les composants que vous choisissez pour indiquer OCSLogger quel le moteur de suivi doit collecter des journaux.</span><span class="sxs-lookup"><span data-stu-id="a286d-128">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="a286d-129">Les fournisseurs sont les mêmes composants et, dans de nombreux cas, ont le même nom que les composants dans OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="a286d-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="a286d-130">Si vous n’êtes pas familiarisé avec OCSLogger, les fournisseurs sont server-role certains composants qui le Service de journalisation centralisée peut collecter les journaux de.</span><span class="sxs-lookup"><span data-stu-id="a286d-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="a286d-131">Dans le cas du Service de journalisation centralisée, et le CLSAgent est la partie architecturale de the Centralized Logging Service qui effectue le suivi des composants que vous définissez dans la configuration des fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="a286d-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>
    
- <span data-ttu-id="a286d-132">**Niveaux d’enregistrement** OCSLogger fourni l’option pour choisir un nombre de niveaux de détail des données collectées.</span><span class="sxs-lookup"><span data-stu-id="a286d-132">**Logging levels** OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="a286d-133">Cette fonctionnalité fait partie intégrante du Service de journalisation centralisée et des scénarios et est définie par le paramètre de **Type** .</span><span class="sxs-lookup"><span data-stu-id="a286d-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="a286d-134">Vous avez le choix entre les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="a286d-134">You can choose from the following:</span></span>
    
  - <span data-ttu-id="a286d-135">**Tous les** Collecte de messages de type fatal, erreur, avertissement, commentaires et les informations de débogage dans le journal de suivi pour le fournisseur défini.</span><span class="sxs-lookup"><span data-stu-id="a286d-135">**All** Collects trace messages of type fatal, error, warning, verbose, and debug info to the log for the defined provider.</span></span>
    
  - <span data-ttu-id="a286d-136">**Irrécupérable** Collecte uniquement les messages de suivi définies en tant que « Fatal ».</span><span class="sxs-lookup"><span data-stu-id="a286d-136">**Fatal** Collects only the trace messages defined as "Fatal."</span></span>
    
  - <span data-ttu-id="a286d-137">**Erreur** Collecte uniquement les messages de suivi définis comme « Erreur » ou « Fatal ».</span><span class="sxs-lookup"><span data-stu-id="a286d-137">**Error** Collects only the trace messages defined as "Error" or "Fatal."</span></span>
    
  - <span data-ttu-id="a286d-138">**Avertissement** Collecte uniquement les messages de suivi de type « Warning », « Erreur » et « Irrécupérable ».</span><span class="sxs-lookup"><span data-stu-id="a286d-138">**Warning** Collects only the trace messages of type "Warning," "Error" and "Fatal."</span></span>
    
  - <span data-ttu-id="a286d-139">**Info** Collecte uniquement les messages de suivi qui indiquent un message d’information pour le fournisseur défini, ainsi qu’irrécupérable, erreur et messages d’avertissement.</span><span class="sxs-lookup"><span data-stu-id="a286d-139">**Info** Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
  - <span data-ttu-id="a286d-140">**Verbose** Collecte tous les messages de suivi de l’erreur irrécupérable, type, d’avertissement et verbose pour le fournisseur défini.</span><span class="sxs-lookup"><span data-stu-id="a286d-140">**Verbose** Collects all trace messages of type fatal, error, warning and verbose for the defined provider.</span></span>
    
  - <span data-ttu-id="a286d-141">**Débogage** c’est essentiellement l’équivalent de « Tous » - traces de collecte de type Fatal, erreur, avertissement, informations, commentaires et débogage pour le fournisseur défini.</span><span class="sxs-lookup"><span data-stu-id="a286d-141">**Debug** this is essentially an equivalent of 'All' - collects traces of type Fatal, Error, Warning, Info, Verbose and Debug for the defined provider.</span></span>
    
- <span data-ttu-id="a286d-142">**Indicateurs** OCSLogger fourni l’option pour choisir les indicateurs pour chaque fournisseur défini le type d’informations que vous pouvez récupérer à partir des fichiers de suivi.</span><span class="sxs-lookup"><span data-stu-id="a286d-142">**Flags** OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="a286d-143">Vous pouvez choisir les indicateurs suivants selon le fournisseur :</span><span class="sxs-lookup"><span data-stu-id="a286d-143">You can chose the following flags, based on the provider:</span></span>
    
  - <span data-ttu-id="a286d-144">**TF_Connection** Fournit des entrées du journal liées à la connexion.</span><span class="sxs-lookup"><span data-stu-id="a286d-144">**TF_Connection** Provides connection-related log entries.</span></span> <span data-ttu-id="a286d-145">Ces journaux incluent des informations sur les connexions établies depuis et vers un composant particulier.</span><span class="sxs-lookup"><span data-stu-id="a286d-145">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="a286d-146">Ils peuvent également comprendre des informations importantes au niveau du réseau (c’est-à-dire, pour les composants sans le concept d’une connexion).</span><span class="sxs-lookup"><span data-stu-id="a286d-146">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
  - <span data-ttu-id="a286d-147">**TF_Security** Fournit toutes les entrées du journal des événements liées à la sécurité.</span><span class="sxs-lookup"><span data-stu-id="a286d-147">**TF_Security** Provides all events/log entries related to security.</span></span> <span data-ttu-id="a286d-148">Par exemple, pour SipStack, il s’agit d’événements de sécurité tels que les échecs de validation de domaine et les échecs d’authentification ou d’autorisation du client.</span><span class="sxs-lookup"><span data-stu-id="a286d-148">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
  - <span data-ttu-id="a286d-149">**TF_Diag** Fournit des événements de diagnostic que vous pouvez utiliser pour diagnostiquer ou de résoudre le composant.</span><span class="sxs-lookup"><span data-stu-id="a286d-149">**TF_Diag** Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="a286d-150">Par exemple, pour SipStack, il s’agit d’échecs de certificat ou d’avertissements/erreurs DNS.</span><span class="sxs-lookup"><span data-stu-id="a286d-150">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
  - <span data-ttu-id="a286d-151">**TF_Protocol** Fournit des messages de protocole tels que les messages SIP et combinés Communauté Codec Pack.</span><span class="sxs-lookup"><span data-stu-id="a286d-151">**TF_Protocol** Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
  - <span data-ttu-id="a286d-152">**TF_Component** Active la journalisation sur les composants spécifiés dans le cadre des fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="a286d-152">**TF_Component** Enables logging on the components specified as part of the providers.</span></span>
    
  - <span data-ttu-id="a286d-153">**Tous les** Définit tous les indicateurs disponibles pour le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="a286d-153">**All** Sets all available flags available for the provider.</span></span>
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="a286d-154">Pour passer en revue les informations sur les fournisseurs de scénario de Service de journalisation centralisée existants</span><span class="sxs-lookup"><span data-stu-id="a286d-154">To review information about existing Centralized Logging Service scenario providers</span></span>

1. <span data-ttu-id="a286d-155">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a286d-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="a286d-156">Pour examiner la configuration de fournisseurs existants, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="a286d-156">To review the configuration of existing providers, type the following:</span></span>
    
   ```
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    <span data-ttu-id="a286d-157">Par exemple, pour examiner des informations sur l’Intendant Conférence global, tapez :</span><span class="sxs-lookup"><span data-stu-id="a286d-157">For example, to review information about the global conferencing attendant, type:</span></span>
    
   ```
   Get-CsClsScenario -Identity "global/CAA"
   ```

    <span data-ttu-id="a286d-158">La commande affiche une liste de fournisseurs avec les indicateurs, paramètres et composants associés.</span><span class="sxs-lookup"><span data-stu-id="a286d-158">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="a286d-159">Si les informations affichées ne sont pas suffisamment ou la liste est trop longue pour le format par défaut de Windows PowerShell, vous pouvez afficher des informations supplémentaires en définissant une méthode de sortie différent.</span><span class="sxs-lookup"><span data-stu-id="a286d-159">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="a286d-160">Pour cela, tapez :</span><span class="sxs-lookup"><span data-stu-id="a286d-160">To do this, type:</span></span>
    
   ```
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    <span data-ttu-id="a286d-161">La sortie de cette commande affiche chaque fournisseur sur cinq lignes avec le nom du fournisseur, le type de journalisation, le niveau d’enregistrement, les indicateurs, le GUID et le rôle sur une ligne distincte.</span><span class="sxs-lookup"><span data-stu-id="a286d-161">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span> 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="a286d-162">Pour définir un nouveau fournisseur de scénario de Service de journalisation centralisée</span><span class="sxs-lookup"><span data-stu-id="a286d-162">To define a new Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="a286d-163">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a286d-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="a286d-p113">Un fournisseur de scénario se compose d’un composant à suivre, d’indicateurs à utiliser et d’un niveau de détail à collecter. Pour cela, tapez :</span><span class="sxs-lookup"><span data-stu-id="a286d-p113">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect. You do this by typing:</span></span>
    
   ```
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    <span data-ttu-id="a286d-166">Par exemple, une définition de fournisseur de suivi qui définit ce qu’il faut collecter à partir du fournisseur Lyss et à quel niveau de détail ressemble à ceci :</span><span class="sxs-lookup"><span data-stu-id="a286d-166">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

<span data-ttu-id="a286d-167">-Collectées par niveau irrécupérable, erreur, avertissement et informations les messages.</span><span class="sxs-lookup"><span data-stu-id="a286d-167">The -Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="a286d-168">Les indicateurs utilisés sont tous les paramètres définis pour le fournisseur Lyss et incluent TF_Connection, TF_Diag et TF_Protocol.After la variable $LyssProvider est définie, vous pouvez l’utiliser avec l’applet de commande **New-CsClsScenario** à collecter les suivis à partir du fournisseur Lyss.</span><span class="sxs-lookup"><span data-stu-id="a286d-168">The flags used are all of those defined for the Lyss provider, and include TF_Connection, TF_Diag and TF_Protocol.After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="a286d-169">Pour terminer la création du fournisseur et son affectation à un nouveau scénario, tapez :</span><span class="sxs-lookup"><span data-stu-id="a286d-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

```
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

<span data-ttu-id="a286d-170">Où $LyssProvider est la variable qui contient le scénario défini créé avec **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="a286d-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="a286d-171">Pour modifier un fournisseur de scénario de Service de journalisation centralisée existant</span><span class="sxs-lookup"><span data-stu-id="a286d-171">To change an existing Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="a286d-172">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a286d-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="a286d-173">Pour mettre à jour ou modifier la configuration d’un fournisseur existant, tapez :</span><span class="sxs-lookup"><span data-stu-id="a286d-173">To update or change the configuration of an existing provider, type:</span></span>
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    <span data-ttu-id="a286d-174">Vous pouvez ensuite mettre à jour le scénario pour affecter le fournisseur en tapant ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="a286d-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

<span data-ttu-id="a286d-p115">À l’issue de l’exécution de la commande, des indicateurs et un niveau mis à jour pour le fournisseur sont affectés au scénario site:Redmond/RedmondLyssInfo. Vous pouvez examiner le nouveau scénario en utilisant Get-CsClsScenario. Pour plus d’informations, voir [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="a286d-p115">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it. You can view the new scenario by using Get-CsClsScenario. For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span>
> [!CAUTION]
> <span data-ttu-id="a286d-178">**New-ClsCsProvider** ne vérifie pas si les indicateurs sont valides.</span><span class="sxs-lookup"><span data-stu-id="a286d-178">**New-ClsCsProvider** does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="a286d-179">Assurez-vous que les indicateurs (par exemple, TF_DIAG ou TF_CONNECTION) sont correctement épelés.</span><span class="sxs-lookup"><span data-stu-id="a286d-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="a286d-180">Si ce n’est pas le cas, le fournisseur ne peut pas retourner les informations du journal attendues.</span><span class="sxs-lookup"><span data-stu-id="a286d-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>
  
<span data-ttu-id="a286d-181">Si vous souhaitez ajouter des fournisseurs supplémentaires à ce scénario, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="a286d-181">If you want to add additional providers to this scenario, type the following:</span></span>

```
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

<span data-ttu-id="a286d-182">Où chaque fournisseur défini avec la directive Add a déjà été défini à l’aide du processus **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="a286d-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>
### <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="a286d-183">Pour supprimer un fournisseur de scénario</span><span class="sxs-lookup"><span data-stu-id="a286d-183">To remove a scenario provider</span></span>

1. <span data-ttu-id="a286d-184">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a286d-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="a286d-185">Les applets de commande fournies vous permettent de mettre à jour des fournisseurs existants et de créer de nouveaux fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="a286d-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="a286d-186">Pour supprimer un fournisseur, vous devez utiliser la directive Replace pour le paramètre Provider pour **Set-CsClsScenario**.</span><span class="sxs-lookup"><span data-stu-id="a286d-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="a286d-187">La seule façon de supprimer complètement un fournisseur est de le remplacer par un fournisseur redéfini du même nom et d’utiliser la directive Update.</span><span class="sxs-lookup"><span data-stu-id="a286d-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="a286d-188">Par exemple, le fournisseur LyssProvider est défini comme suit : WPP comme type de journal, Debug comme niveau, et TF_CONNECTION et TF_DIAG comme indicateurs.</span><span class="sxs-lookup"><span data-stu-id="a286d-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF_CONNECTION and TF_DIAG.</span></span> <span data-ttu-id="a286d-189">Vous devez modifier les indicateurs à « Toutes ».</span><span class="sxs-lookup"><span data-stu-id="a286d-189">You need to change the flags to "All".</span></span> <span data-ttu-id="a286d-190">Pour modifier le fournisseur, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="a286d-190">To change the provider, type the following:</span></span>
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. <span data-ttu-id="a286d-191">Si vous souhaitez supprimer complètement un scénario et les fournisseurs associés à celui-ci, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="a286d-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
   ```
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    <span data-ttu-id="a286d-192">Exemple :</span><span class="sxs-lookup"><span data-stu-id="a286d-192">For example:</span></span>
    
   ```
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > <span data-ttu-id="a286d-193">L’applet de commande **Remove-CsClsScenario** ne vous demande pas confirmation.</span><span class="sxs-lookup"><span data-stu-id="a286d-193">The cmdlet **Remove-CsClsScenario** does not prompt you for confirmation.</span></span> <span data-ttu-id="a286d-194">Le scénario est supprimé, ainsi que les fournisseurs affectés à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="a286d-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="a286d-195">Vous pouvez recréer le scénario en réexécutant les commandes que vous avez utilisées pour le créer initialement.</span><span class="sxs-lookup"><span data-stu-id="a286d-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="a286d-196">Il n’existe aucune procédure pour récupérer des scénarios ou des fournisseurs supprimés.</span><span class="sxs-lookup"><span data-stu-id="a286d-196">There is no procedure to recover removed scenarios or providers.</span></span>
  
<span data-ttu-id="a286d-197">Lorsque vous supprimez un scénario à l’aide de l’applet de commande **Remove-CsClsScenario**, vous supprimez complètement le scénario de l’étendue.</span><span class="sxs-lookup"><span data-stu-id="a286d-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="a286d-198">Pour utiliser les scénarios que vous avez créés et les fournisseurs qui faisaient partie du scénario, vous devez créer de nouveaux fournisseurs et les affecter à un nouveau scénario.</span><span class="sxs-lookup"><span data-stu-id="a286d-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>
## <a name="see-also"></a><span data-ttu-id="a286d-199">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a286d-199">See also</span></span>

[<span data-ttu-id="a286d-200">Get-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="a286d-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="a286d-201">New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="a286d-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="a286d-202">Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="a286d-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="a286d-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="a286d-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="a286d-204">New-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="a286d-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)

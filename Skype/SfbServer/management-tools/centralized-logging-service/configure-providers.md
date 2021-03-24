---
title: Configuration des fournisseurs pour le service de journalisation centralisée dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 'Résumé : Découvrez comment configurer des fournisseurs de scénarios pour le service de journalisation centralisée dans Skype Entreprise Server 2015.'
ms.openlocfilehash: cd0364d6497aa53d258b5346090d6cdd7c338cc3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098850"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="2e785-103">Configuration des fournisseurs pour le service de journalisation centralisée dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="2e785-103">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2e785-104">**Résumé :** Découvrez comment configurer des fournisseurs de scénarios pour le service de journalisation centralisée dans Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2e785-104">**Summary:** Learn how to configure scenario providers for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2e785-105">Les concepts et la configuration des fournisseurs dans le service de journalisation centralisée sont l’un des concepts les plus importants à comprendre.</span><span class="sxs-lookup"><span data-stu-id="2e785-105">The concepts and configuration of providers in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="2e785-106">Lesprovideurs mappent directement aux composants de rôle serveur Skype Entreprise Server dans le modèle de suivi Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="2e785-106">Theproviders map directly to Skype for Business Server server role components in the Skype for Business Server tracing model.</span></span> <span data-ttu-id="2e785-107">Le fournisseur définit les composants d’un skype entreprise Server 2015 qui seront suivis, le type de messages (par exemple, fatal, erreur ou avertissement) à collecter et les indicateurs (par exemple, TF_Connection ou TF_Diag).</span><span class="sxs-lookup"><span data-stu-id="2e785-107">The provider defines the components of a Skype for Business Server 2015 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF_Connection or TF_Diag).</span></span> <span data-ttu-id="2e785-108">Les fournisseurs sont les composants de suivi dans chaque rôle serveur Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="2e785-108">Providers are the traceable components in each Skype for Business Server server role.</span></span> <span data-ttu-id="2e785-109">À l’aide de fournisseurs, vous définissez le niveau et le type de suivi sur les composants (par exemple, S4, SIPStack, Messagerie instantanée et Présence).</span><span class="sxs-lookup"><span data-stu-id="2e785-109">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="2e785-110">Le fournisseur défini est utilisé dans un scénario pour regrouper tous les fournisseurs d’une collection logique donnée qui répondent à une condition de problème spécifique.</span><span class="sxs-lookup"><span data-stu-id="2e785-110">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>
  
<span data-ttu-id="2e785-111">Pour exécuter les fonctions du service de journalisation centralisée à l’aide de Skype Entreprise Server Management Shell, vous devez être membre des groupes de sécurité RBAC CsAdministrator ou CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes.</span><span class="sxs-lookup"><span data-stu-id="2e785-111">To run the Centralized Logging Service functions using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="2e785-112">Pour retourner la liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) attribués à cette cmdlet (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de Skype Entreprise Server Management Shell ou de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="2e785-112">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="2e785-113">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="2e785-113">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="2e785-114">Le reste de cette rubrique porte sur la définition des fournisseurs, la modification d’un fournisseur et ce que contient une définition de fournisseur afin d’optimiser le dépannage.</span><span class="sxs-lookup"><span data-stu-id="2e785-114">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="2e785-115">Il existe deux façons d’émettre des commandes du service de journalisation centralisée.</span><span class="sxs-lookup"><span data-stu-id="2e785-115">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="2e785-116">Vous pouvez utiliser la CLSController.exe qui se trouve, par défaut, dans le répertoire C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="2e785-116">You can use the CLSController.exe that is located, by default, in the directory C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent.</span></span> <span data-ttu-id="2e785-117">Vous pouvez également utiliser l’environnement de ligne de commande Skype Entreprise Server Management Shell pour émettre Windows PowerShell commandes.</span><span class="sxs-lookup"><span data-stu-id="2e785-117">Or, you can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="2e785-118">À l’aide de Windows PowerShell, vous pouvez définir de nouveaux fournisseurs à utiliser dans vos sessions de journalisation et avoir un contrôle total sur leur création, ce qu’ils collectent et à quel niveau ils collectent des données.</span><span class="sxs-lookup"><span data-stu-id="2e785-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2e785-p104">Comme nous l’avons précédemment mentionné, les fournisseurs sont très puissants. Cependant, les scénarios le sont davantage, et ce du fait qu’ils contiennent toutes les informations nécessaires pour définir et exécuter le suivi sur les composants que les fournisseurs représentent. Les scénarios étant une collection de fournisseurs, une certaine analogie peut être établie entre, d’une part, l’exécution d’un fichier de commandes qui contient des centaines de commandes destinées à collecter une grande quantité d’informations et, d’autre part, l’émission de centaines de commandes, une à la fois, à la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="2e785-p104">As mentioned, providers are very powerful. However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent. With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span> 
  
<span data-ttu-id="2e785-122">Au lieu de vous demander d’en détailler les détails des fournisseurs, le service de journalisation centralisée fournit un certain nombre de scénarios qui sont déjà définis pour vous.</span><span class="sxs-lookup"><span data-stu-id="2e785-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="2e785-123">Les scénarios fournis couvrent la grande majorité des problèmes que vous êtes susceptible de rencontrer.</span><span class="sxs-lookup"><span data-stu-id="2e785-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="2e785-124">Dans de rares cas, vous devrez créer et définir des fournisseurs et les affecter à des scénarios.</span><span class="sxs-lookup"><span data-stu-id="2e785-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="2e785-125">Nous vous recommandons fortement de vous familiariser avec chacun des scénarios fournis avant d’étudier la nécessité de créer de nouveaux scénarios et de nouveaux fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="2e785-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="2e785-126">Bien que des informations sur la création de fournisseurs sont données ici pour vous familiariser avec la façon dont les scénarios utilisent les éléments des fournisseurs pour collecter des informations de suivi, aucun détail sur les fournisseurs eux-mêmes n’est fourni pour le moment.</span><span class="sxs-lookup"><span data-stu-id="2e785-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span> 
  
<span data-ttu-id="2e785-127">Introduits dans le service de journalisation centralisée dans Skype Entreprise [2015,](centralized-logging-service.md)les éléments clés de la définition d’un fournisseur à utiliser dans un scénario sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="2e785-127">Introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>
  
- <span data-ttu-id="2e785-128">**Fournisseurs** Si vous êtes familiarisé avec OCSLogger, les fournisseurs sont les composants que vous choisissez d’indiquer à OCSLogger à partir de quoi le moteur de suivi doit collecter les journaux.</span><span class="sxs-lookup"><span data-stu-id="2e785-128">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="2e785-129">Les fournisseurs sont les mêmes composants et, dans de nombreux cas, ont le même nom que les composants dans OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="2e785-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="2e785-130">Si vous n’êtes pas familiarisé avec OCSLogger, les fournisseurs sont des composants spécifiques au rôle de serveur à partir desse que le service de journalisation centralisée peut collecter des journaux.</span><span class="sxs-lookup"><span data-stu-id="2e785-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="2e785-131">Dans le cas du service de journalisation centralisée, le CLSAgent est la partie architecturale du service de journalisation centralisée qui fait le suivi des composants que vous définissez dans la configuration des fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="2e785-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>
    
- <span data-ttu-id="2e785-132">**Niveaux de journalisation** OCSLogger a fourni la possibilité de choisir un certain nombre de niveaux de détails pour les données collectées.</span><span class="sxs-lookup"><span data-stu-id="2e785-132">**Logging levels** OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="2e785-133">Cette fonctionnalité fait partie intégrante du service de journalisation centralisée et des scénarios et est définie par le **paramètre Type.**</span><span class="sxs-lookup"><span data-stu-id="2e785-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="2e785-134">Vous pouvez choisir l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="2e785-134">You can choose from the following:</span></span>
    
  - <span data-ttu-id="2e785-135">**Tout** Collecte les messages de suivi de type Fatal, Error, Warning, Verbose et Debug info dans le journal du fournisseur défini.</span><span class="sxs-lookup"><span data-stu-id="2e785-135">**All** Collects trace messages of type fatal, error, warning, verbose, and debug info to the log for the defined provider.</span></span>
    
  - <span data-ttu-id="2e785-136">**Fatal** Collecte uniquement les messages de suivi définis comme « Fatal ».</span><span class="sxs-lookup"><span data-stu-id="2e785-136">**Fatal** Collects only the trace messages defined as "Fatal."</span></span>
    
  - <span data-ttu-id="2e785-137">**Erreur** Collecte uniquement les messages de suivi définis comme « Erreur » ou « Fatal ».</span><span class="sxs-lookup"><span data-stu-id="2e785-137">**Error** Collects only the trace messages defined as "Error" or "Fatal."</span></span>
    
  - <span data-ttu-id="2e785-138">**Avertissement** Collecte uniquement les messages de suivi de type « Avertissement », « Erreur » et « Fatal ».</span><span class="sxs-lookup"><span data-stu-id="2e785-138">**Warning** Collects only the trace messages of type "Warning," "Error" and "Fatal."</span></span>
    
  - <span data-ttu-id="2e785-139">**Informations** Collecte uniquement les messages de suivi qui indiquent un message d’information pour le fournisseur défini, ainsi que les messages fatals, d’erreur et d’avertissement.</span><span class="sxs-lookup"><span data-stu-id="2e785-139">**Info** Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
  - <span data-ttu-id="2e785-140">**Verbose** Collecte tous les messages de suivi de type Fatal, Error, Warning et Verbose pour le fournisseur défini.</span><span class="sxs-lookup"><span data-stu-id="2e785-140">**Verbose** Collects all trace messages of type fatal, error, warning and verbose for the defined provider.</span></span>
    
  - <span data-ttu-id="2e785-141">**Déboguer** ceci est essentiellement l’équivalent de « All » : collecte des traces de type Fatal, Error, Warning, Info, Verbose et Debug pour le fournisseur défini.</span><span class="sxs-lookup"><span data-stu-id="2e785-141">**Debug** this is essentially an equivalent of 'All' - collects traces of type Fatal, Error, Warning, Info, Verbose and Debug for the defined provider.</span></span>
    
- <span data-ttu-id="2e785-142">**Indicateurs** OCSLogger fournissait la possibilité de choisir des indicateurs pour chaque fournisseur qui définissaient le type d’informations que vous pouviez récupérer à partir des fichiers de suivi.</span><span class="sxs-lookup"><span data-stu-id="2e785-142">**Flags** OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="2e785-143">Vous pouvez choisir les indicateurs suivants selon le fournisseur :</span><span class="sxs-lookup"><span data-stu-id="2e785-143">You can chose the following flags, based on the provider:</span></span>
    
  - <span data-ttu-id="2e785-144">**TF_Connection** Fournit des entrées de journal liées à la connexion.</span><span class="sxs-lookup"><span data-stu-id="2e785-144">**TF_Connection** Provides connection-related log entries.</span></span> <span data-ttu-id="2e785-145">Ces journaux incluent des informations sur les connexions établies depuis et vers un composant particulier.</span><span class="sxs-lookup"><span data-stu-id="2e785-145">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="2e785-146">Ils peuvent également comprendre des informations importantes au niveau du réseau (c’est-à-dire, pour les composants sans le concept d’une connexion).</span><span class="sxs-lookup"><span data-stu-id="2e785-146">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
  - <span data-ttu-id="2e785-147">**TF_Security** Fournit toutes les entrées d’événements/journaux liées à la sécurité.</span><span class="sxs-lookup"><span data-stu-id="2e785-147">**TF_Security** Provides all events/log entries related to security.</span></span> <span data-ttu-id="2e785-148">Par exemple, pour SipStack, il s’agit d’événements de sécurité tels que les échecs de validation de domaine et les échecs d’authentification ou d’autorisation du client.</span><span class="sxs-lookup"><span data-stu-id="2e785-148">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
  - <span data-ttu-id="2e785-149">**TF_Diag** Fournit des événements de diagnostic que vous pouvez utiliser pour diagnostiquer ou dépanner le composant.</span><span class="sxs-lookup"><span data-stu-id="2e785-149">**TF_Diag** Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="2e785-150">Par exemple, pour SipStack, il s’agit d’échecs de certificat ou d’avertissements/erreurs DNS.</span><span class="sxs-lookup"><span data-stu-id="2e785-150">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
  - <span data-ttu-id="2e785-151">**TF_Protocol** Fournit des messages de protocole tels que les messages SIP et Combined Community Codec Pack.</span><span class="sxs-lookup"><span data-stu-id="2e785-151">**TF_Protocol** Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
  - <span data-ttu-id="2e785-152">**TF_Component** Active la journalisation sur les composants spécifiés dans le cadre des fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="2e785-152">**TF_Component** Enables logging on the components specified as part of the providers.</span></span>
    
  - <span data-ttu-id="2e785-153">**Tout** Définit tous les indicateurs disponibles pour le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="2e785-153">**All** Sets all available flags available for the provider.</span></span>
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="2e785-154">Pour passer en revue les informations sur les fournisseurs de scénarios du service de journalisation centralisée existants</span><span class="sxs-lookup"><span data-stu-id="2e785-154">To review information about existing Centralized Logging Service scenario providers</span></span>

1. <span data-ttu-id="2e785-155">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="2e785-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2e785-156">Pour examiner la configuration de fournisseurs existants, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="2e785-156">To review the configuration of existing providers, type the following:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    <span data-ttu-id="2e785-157">Par exemple, pour examiner des informations sur l’Intendant Conférence global, tapez :</span><span class="sxs-lookup"><span data-stu-id="2e785-157">For example, to review information about the global conferencing attendant, type:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA"
   ```

    <span data-ttu-id="2e785-158">La commande affiche une liste de fournisseurs avec les indicateurs, paramètres et composants associés.</span><span class="sxs-lookup"><span data-stu-id="2e785-158">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="2e785-159">Si les informations affichées ne sont pas suffisantes ou si la liste est trop longue pour le format de liste Windows PowerShell par défaut, vous pouvez afficher des informations supplémentaires en définissant une méthode de sortie différente.</span><span class="sxs-lookup"><span data-stu-id="2e785-159">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="2e785-160">Pour cela, tapez :</span><span class="sxs-lookup"><span data-stu-id="2e785-160">To do this, type:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    <span data-ttu-id="2e785-161">La sortie de cette commande affiche chaque fournisseur sur cinq lignes avec le nom du fournisseur, le type de journalisation, le niveau d’enregistrement, les indicateurs, le GUID et le rôle sur une ligne distincte.</span><span class="sxs-lookup"><span data-stu-id="2e785-161">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span> 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="2e785-162">Pour définir un nouveau fournisseur de scénarios de service de journalisation centralisée</span><span class="sxs-lookup"><span data-stu-id="2e785-162">To define a new Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="2e785-163">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="2e785-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2e785-p113">Un fournisseur de scénario se compose d’un composant à suivre, d’indicateurs à utiliser et d’un niveau de détail à collecter. Pour cela, tapez :</span><span class="sxs-lookup"><span data-stu-id="2e785-p113">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect. You do this by typing:</span></span>
    
   ```PowerShell
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    <span data-ttu-id="2e785-166">Par exemple, une définition de fournisseur de suivi qui définit ce qu’il faut collecter à partir du fournisseur Lyss et à quel niveau de détail ressemble à ceci :</span><span class="sxs-lookup"><span data-stu-id="2e785-166">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

<span data-ttu-id="2e785-167">Le niveau collecte les messages fatals, d’erreur, d’avertissement et d’informations.</span><span class="sxs-lookup"><span data-stu-id="2e785-167">The -Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="2e785-168">Les indicateurs utilisés sont tous ceux définis pour le fournisseur Lyss et incluent TF_Connection, TF_Diag et TF_Protocol.Une fois la $LyssProvider variable définie, vous pouvez l’utiliser avec l';cmdlet **New-CsClsScenario** pour collecter les suivis à partir du fournisseur Lyss.</span><span class="sxs-lookup"><span data-stu-id="2e785-168">The flags used are all of those defined for the Lyss provider, and include TF_Connection, TF_Diag and TF_Protocol.After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="2e785-169">Pour terminer la création du fournisseur et son affectation à un nouveau scénario, tapez :</span><span class="sxs-lookup"><span data-stu-id="2e785-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

```PowerShell
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

<span data-ttu-id="2e785-170">Où $LyssProvider est la variable qui contient le scénario défini créé avec **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="2e785-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="2e785-171">Pour modifier un fournisseur de scénarios de service de journalisation centralisée existant</span><span class="sxs-lookup"><span data-stu-id="2e785-171">To change an existing Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="2e785-172">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="2e785-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2e785-173">Pour mettre à jour ou modifier la configuration d’un fournisseur existant, tapez :</span><span class="sxs-lookup"><span data-stu-id="2e785-173">To update or change the configuration of an existing provider, type:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    <span data-ttu-id="2e785-174">Vous pouvez ensuite mettre à jour le scénario pour affecter le fournisseur en tapant ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="2e785-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

<span data-ttu-id="2e785-175">À l’issue de l’exécution de la commande, des indicateurs et un niveau mis à jour pour le fournisseur sont affectés au scénario site:Redmond/RedmondLyssInfo.</span><span class="sxs-lookup"><span data-stu-id="2e785-175">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="2e785-176">Vous pouvez examiner le nouveau scénario en utilisant Get-CsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="2e785-176">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="2e785-177">Pour plus d’informations, voir [Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2e785-177">For details, see [Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span>
> [!CAUTION]
> <span data-ttu-id="2e785-178">**New-ClsCsProvider** ne vérifie pas si les indicateurs sont valides.</span><span class="sxs-lookup"><span data-stu-id="2e785-178">**New-ClsCsProvider** does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="2e785-179">Assurez-vous que les indicateurs (par exemple, TF_DIAG ou TF_CONNECTION) sont correctement épelés.</span><span class="sxs-lookup"><span data-stu-id="2e785-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="2e785-180">Si ce n’est pas le cas, le fournisseur ne peut pas retourner les informations du journal attendues.</span><span class="sxs-lookup"><span data-stu-id="2e785-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>
  
<span data-ttu-id="2e785-181">Si vous souhaitez ajouter des fournisseurs supplémentaires à ce scénario, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="2e785-181">If you want to add additional providers to this scenario, type the following:</span></span>

```PowerShell
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

<span data-ttu-id="2e785-182">Où chaque fournisseur défini avec la directive Add a déjà été défini à l’aide du processus **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="2e785-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>
### <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="2e785-183">Pour supprimer un fournisseur de scénario</span><span class="sxs-lookup"><span data-stu-id="2e785-183">To remove a scenario provider</span></span>

1. <span data-ttu-id="2e785-184">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="2e785-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2e785-185">Les applets de commande fournies vous permettent de mettre à jour des fournisseurs existants et de créer de nouveaux fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="2e785-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="2e785-186">Pour supprimer un fournisseur, vous devez utiliser la directive Replace pour le paramètre Provider pour **Set-CsClsScenario**.</span><span class="sxs-lookup"><span data-stu-id="2e785-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="2e785-187">La seule façon de supprimer complètement un fournisseur est de le remplacer par un fournisseur redéfini du même nom et d’utiliser la directive Update.</span><span class="sxs-lookup"><span data-stu-id="2e785-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="2e785-188">Par exemple, le fournisseur LyssProvider est défini comme suit : WPP comme type de journal, Debug comme niveau, et TF_CONNECTION et TF_DIAG comme indicateurs.</span><span class="sxs-lookup"><span data-stu-id="2e785-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF_CONNECTION and TF_DIAG.</span></span> <span data-ttu-id="2e785-189">Vous devez modifier les indicateurs en « Tous ».</span><span class="sxs-lookup"><span data-stu-id="2e785-189">You need to change the flags to "All".</span></span> <span data-ttu-id="2e785-190">Pour modifier le fournisseur, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="2e785-190">To change the provider, type the following:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. <span data-ttu-id="2e785-191">Si vous souhaitez supprimer complètement un scénario et les fournisseurs associés à celui-ci, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="2e785-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    <span data-ttu-id="2e785-192">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="2e785-192">For example:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > <span data-ttu-id="2e785-193">L’applet de commande **Remove-CsClsScenario** ne vous demande pas confirmation.</span><span class="sxs-lookup"><span data-stu-id="2e785-193">The cmdlet **Remove-CsClsScenario** does not prompt you for confirmation.</span></span> <span data-ttu-id="2e785-194">Le scénario est supprimé, ainsi que les fournisseurs affectés à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="2e785-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="2e785-195">Vous pouvez recréer le scénario en réexécutant les commandes que vous avez utilisées pour le créer initialement.</span><span class="sxs-lookup"><span data-stu-id="2e785-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="2e785-196">Il n’existe aucune procédure pour récupérer des scénarios ou des fournisseurs supprimés.</span><span class="sxs-lookup"><span data-stu-id="2e785-196">There is no procedure to recover removed scenarios or providers.</span></span>
  
<span data-ttu-id="2e785-197">Lorsque vous supprimez un scénario à l’aide de l’applet de commande **Remove-CsClsScenario**, vous supprimez complètement le scénario de l’étendue.</span><span class="sxs-lookup"><span data-stu-id="2e785-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="2e785-198">Pour utiliser les scénarios que vous avez créés et les fournisseurs qui faisaient partie du scénario, vous devez créer de nouveaux fournisseurs et les affecter à un nouveau scénario.</span><span class="sxs-lookup"><span data-stu-id="2e785-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>
## <a name="see-also"></a><span data-ttu-id="2e785-199">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2e785-199">See also</span></span>

[<span data-ttu-id="2e785-200">Get-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="2e785-200">Get-CsClsScenario</span></span>](/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="2e785-201">New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="2e785-201">New-CsClsScenario</span></span>](/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="2e785-202">Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="2e785-202">Remove-CsClsScenario</span></span>](/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="2e785-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="2e785-203">Set-CsClsScenario</span></span>](/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="2e785-204">New-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="2e785-204">New-CsClsProvider</span></span>](/powershell/module/skype/new-csclsprovider?view=skype-ps)
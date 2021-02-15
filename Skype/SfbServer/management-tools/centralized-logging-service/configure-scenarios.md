---
title: Configurer des scénarios pour le service de journalisation centralisée dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 'Résumé : Découvrez comment créer, modifier et supprimer des scénarios pour le service de journalisation centralisée dans Skype Entreprise Server 2015.'
ms.openlocfilehash: 8778530826cdbd0c3ecc5128385644f2191a858e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835184"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="61fa0-103">Configurer des scénarios pour le service de journalisation centralisée dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="61fa0-103">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="61fa0-104">**Résumé :** Découvrez comment créer, modifier et supprimer des scénarios pour le service de journalisation centralisée dans Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="61fa0-104">**Summary:** Learn how to create, modify, and remove scenarios for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="61fa0-105">Les scénarios définissent l’étendue (globale, de site, de pool ou d’ordinateur) et les fournisseurs à utiliser dans le service de journalisation centralisée.</span><span class="sxs-lookup"><span data-stu-id="61fa0-105">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="61fa0-106">À l’aide de scénarios, vous activez ou désactivez le suivi des fournisseurs (par exemple, S4, SIPStack, messagerie instantanée et présence).</span><span class="sxs-lookup"><span data-stu-id="61fa0-106">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="61fa0-107">En configurant un scénario, vous pouvez regrouper tous les fournisseurs d’une collection logique donnée qui répondent à une condition de problème spécifique.</span><span class="sxs-lookup"><span data-stu-id="61fa0-107">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="61fa0-108">Si vous trouvez qu’un scénario doit être modifié pour répondre à vos besoins de dépannage et de journalisation, les outils de débogage de Skype Entreprise Server 2015 vous fournissent un module Windows PowerShell nommé ClsScenarioEdit.psm1 qui contient une fonction nomméeEdit-CsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="61fa0-108">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Skype for Business Server 2015 Debug Tools provides you a Windows PowerShell module named ClsScenarioEdit.psm1 that contains a function namedEdit-CsClsScenario.</span></span> <span data-ttu-id="61fa0-109">Grâce à ce module, vous pouvez modifier les propriétés du scénario nommé.</span><span class="sxs-lookup"><span data-stu-id="61fa0-109">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="61fa0-110">Des exemples d’utilisation de ce module sont fournis dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="61fa0-110">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="61fa0-111">Téléchargez les outils de débogage de Skype Entreprise Server 2015 [](https://go.microsoft.com/fwlink/p/?LinkId=285257) avant d’aller plus loin.</span><span class="sxs-lookup"><span data-stu-id="61fa0-111">Download the Skype for Business Server 2015 [Debugging Tools](https://go.microsoft.com/fwlink/p/?LinkId=285257) before going any further.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="61fa0-112">Pour une étendue donnée (globale, site, pool ou ordinateur), deux scénarios au maximum peuvent être exécutés en même temps.</span><span class="sxs-lookup"><span data-stu-id="61fa0-112">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="61fa0-113">Pour déterminer les scénarios en cours d’exécution, utilisez Windows PowerShell et [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="61fa0-113">To determine which scenarios are currently running, use Windows PowerShell and [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span> <span data-ttu-id="61fa0-114">En utilisant Windows PowerShell [et Set-CsClsScenario,](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)vous pouvez modifier dynamiquement les scénarios en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="61fa0-114">By using Windows PowerShell and [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="61fa0-115">Cette opération peut s’avérer utile lors d’une session de journalisation pour ajuster ou affiner les données que vous collectez et les fournisseurs d’où ces données sont issues.</span><span class="sxs-lookup"><span data-stu-id="61fa0-115">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span> 
  
<span data-ttu-id="61fa0-116">Pour exécuter les fonctions du service de journalisation centralisée à l’aide de Skype Entreprise Server Management Shell, vous devez être membre des groupes de sécurité RBAC CsAdministrator ou CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes.</span><span class="sxs-lookup"><span data-stu-id="61fa0-116">To run the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="61fa0-117">Pour retourner la liste de tous les rôles RBAC attribués à cette cmdlet, y compris les rôles RBAC personnalisés que vous avez créés vous-même, exécutez la commande suivante à partir de Skype Entreprise Server Management Shell ou de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="61fa0-117">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="61fa0-118">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="61fa0-118">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="61fa0-119">Le reste de cette rubrique met l’accent sur la définition d’un scénario, la modification d’un scénario, la récupération des scénarios en cours d’exécution, la suppression d’un scénario et la spécification du contenu d’un scénario afin d’optimiser votre dépannage.</span><span class="sxs-lookup"><span data-stu-id="61fa0-119">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="61fa0-120">Vous pouvez utiliser Skype Entreprise Server Management Shell pour émettre Windows PowerShell commandes.</span><span class="sxs-lookup"><span data-stu-id="61fa0-120">You can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="61fa0-121">Lorsque vous utilisez Windows PowerShell, vous pouvez définir de nouveaux scénarios à utiliser dans vos sessions de journalisation.</span><span class="sxs-lookup"><span data-stu-id="61fa0-121">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>
  
<span data-ttu-id="61fa0-122">Comme introduit dans le service de journalisation centralisée dans Skype Entreprise [2015,](centralized-logging-service.md)les éléments d’un scénario sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="61fa0-122">As introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the elements of a scenario are:</span></span>
  
- <span data-ttu-id="61fa0-123">**Fournisseurs** Si vous êtes familiarisé avec OCSLogger, les fournisseurs sont les composants que vous choisissez d’indiquer à OCSLogger à partir de quoi le moteur de suivi doit collecter les journaux.</span><span class="sxs-lookup"><span data-stu-id="61fa0-123">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="61fa0-124">Les fournisseurs sont les mêmes composants et, dans de nombreux cas, ont le même nom que les composants dans OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="61fa0-124">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="61fa0-125">Si vous n’êtes pas familiarisé avec OCSLogger, les fournisseurs sont des composants spécifiques au rôle de serveur à partir desse que le service de journalisation centralisée peut collecter des journaux.</span><span class="sxs-lookup"><span data-stu-id="61fa0-125">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="61fa0-126">Pour plus d’informations sur la configuration des fournisseurs, voir [Configure providers for Centralized Logging Service in Skype for Business Server 2015](configure-providers.md).</span><span class="sxs-lookup"><span data-stu-id="61fa0-126">For details about the configuration of providers, see [Configure providers for Centralized Logging Service in Skype for Business Server 2015](configure-providers.md).</span></span>
    
- <span data-ttu-id="61fa0-127">**Identité** Le paramètre -Identity définit l’étendue et le nom du scénario.</span><span class="sxs-lookup"><span data-stu-id="61fa0-127">**Identity** The parameter -Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="61fa0-128">Par exemple, vous pouvez définir une étendue « globale » et identifier le scénario avec « LyssServiceScenario ».</span><span class="sxs-lookup"><span data-stu-id="61fa0-128">For example, you could set a scope of "global" and identify the scenario with "LyssServiceScenario".</span></span> <span data-ttu-id="61fa0-129">Lorsque vous combinez les deux, vous définissez l’identité (par exemple, « global/LyssServiceScenario »).</span><span class="sxs-lookup"><span data-stu-id="61fa0-129">When you combine the two, you define the Identity (for example, "global/LyssServiceScenario").</span></span>
    
    <span data-ttu-id="61fa0-130">Si vous le souhaitez, vous pouvez utiliser les paramètres -Name et -Parent.</span><span class="sxs-lookup"><span data-stu-id="61fa0-130">Optionally, you can use the -Name and -Parent parameters.</span></span> <span data-ttu-id="61fa0-131">Le paramètre Name permet d’identifier le scénario de manière unique.</span><span class="sxs-lookup"><span data-stu-id="61fa0-131">You define the Name parameter to uniquely identify the scenario.</span></span> <span data-ttu-id="61fa0-132">Si vous utilisez Name, vous devez également utiliser Parent pour ajouter le scénario à global ou site.</span><span class="sxs-lookup"><span data-stu-id="61fa0-132">If you use Name, you must also use Parent to add the scenario to either global or site.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="61fa0-133">Si vous utilisez les paramètres Name et Parent, vous ne pouvez pas utiliser le **paramètre -Identity.**</span><span class="sxs-lookup"><span data-stu-id="61fa0-133">If you use the Name and Parent parameters, you cannot use the **-Identity** parameter.</span></span>
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="61fa0-134">Pour créer un scénario avec l’applet de commande New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="61fa0-134">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="61fa0-135">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="61fa0-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="61fa0-136">Pour créer un scénario pour une session de journalisation, utilisez [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) et définissez le nom du scénario (c’est-à-dire comment il va être identifié de manière unique).</span><span class="sxs-lookup"><span data-stu-id="61fa0-136">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) and define the name of the scenario (that is, how it will be uniquely identified).</span></span> <span data-ttu-id="61fa0-137">Choisissez un type de format de journalisation : vous avez le choix entre WPP (préprocesseur de suivi de logiciel Windows ; la valeur par défaut), EventLog (format de journal des événements Windows) et IISLog (fichier au format ASCII basé sur le format du fichier journal IIS).</span><span class="sxs-lookup"><span data-stu-id="61fa0-137">Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format).</span></span> <span data-ttu-id="61fa0-138">Ensuite, définissez Level (voir la définition sous Niveaux de journalisation dans cette rubrique) et Flags (voir la définition sous Indicateurs dans cette rubrique).</span><span class="sxs-lookup"><span data-stu-id="61fa0-138">Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="61fa0-139">Dans cet exemple de scénario, nous utilisons LyssProvider comme exemple de variable de fournisseur.</span><span class="sxs-lookup"><span data-stu-id="61fa0-139">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="61fa0-140">Pour créer un scénario en utilisant les options définies, tapez :</span><span class="sxs-lookup"><span data-stu-id="61fa0-140">To create a scenario using the options defined, type:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    <span data-ttu-id="61fa0-141">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="61fa0-141">For example:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    <span data-ttu-id="61fa0-142">Autre format utilisant -Name et -Parent :</span><span class="sxs-lookup"><span data-stu-id="61fa0-142">The alternate format using -Name and -Parent:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="61fa0-143">Pour créer un scénario avec plusieurs fournisseurs à l’aide de l’applet de commande New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="61fa0-143">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="61fa0-144">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="61fa0-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="61fa0-145">Vous êtes limité à deux scénarios par étendue.</span><span class="sxs-lookup"><span data-stu-id="61fa0-145">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="61fa0-146">Cependant, le nombre de fournisseurs n’est pas limité.</span><span class="sxs-lookup"><span data-stu-id="61fa0-146">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="61fa0-147">Dans cet exemple, supposons que vous avez créé trois fournisseurs et que vous souhaitez les affecter tous les trois au scénario que vous définissez.</span><span class="sxs-lookup"><span data-stu-id="61fa0-147">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="61fa0-148">Les noms des variables de fournisseur sont LyssProvider, ABServerProvider et SIPStackProvider.</span><span class="sxs-lookup"><span data-stu-id="61fa0-148">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="61fa0-149">Pour définir et affecter plusieurs fournisseurs à un scénario, tapez ce qui suit à l’invite de commandes Skype Entreprise Server Management Shell ou Windows PowerShell commande suivante :</span><span class="sxs-lookup"><span data-stu-id="61fa0-149">To define and assign multiple providers to a scenario, type the following at a Skype for Business Server Management Shell or Windows PowerShell command prompt:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > <span data-ttu-id="61fa0-150">Comme il est connu dans Windows PowerShell, la convention de création d’une table de hachage de valeurs à l’aide est appelée  `@{<variable>=<value1>, <value2>, <value>…}` « platting ».</span><span class="sxs-lookup"><span data-stu-id="61fa0-150">As it is known in Windows PowerShell, the convention for creating a hash table of values using  `@{<variable>=<value1>, <value2>, <value>…}` is known assplatting.</span></span> <span data-ttu-id="61fa0-151">Pour plus d’informations sur la splatting dans Windows PowerShell, voir [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760) .</span><span class="sxs-lookup"><span data-stu-id="61fa0-151">For details about splatting in Windows PowerShell, see [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760).</span></span> 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="61fa0-152">Pour modifier un scénario existant avec l’applet de commande Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="61fa0-152">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="61fa0-153">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="61fa0-153">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="61fa0-154">Vous êtes limité à deux scénarios par étendue.</span><span class="sxs-lookup"><span data-stu-id="61fa0-154">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="61fa0-155">Vous pouvez modifier les scénarios qui s’ exécutent à tout moment, même lorsqu’une session de capture de journalisation est en cours.</span><span class="sxs-lookup"><span data-stu-id="61fa0-155">You can change which scenarios are running at any time, even when a logging capture session is in process.</span></span> <span data-ttu-id="61fa0-156">Si vous redéfinissez les scénarios en cours d’exécution, la session de journalisation actuelle cesse d’utiliser le scénario qui a été supprimé et utilise ensuite le nouveau scénario.</span><span class="sxs-lookup"><span data-stu-id="61fa0-156">If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario.</span></span> <span data-ttu-id="61fa0-157">Toutefois, les informations de journalisation qui ont été capturées avec le scénario supprimé sont conservées dans les journaux capturés.</span><span class="sxs-lookup"><span data-stu-id="61fa0-157">However, the logging information that was captured with the removed scenario remains in the captured logs.</span></span> <span data-ttu-id="61fa0-158">Pour définir un nouveau scénario, faites ce qui suit (autrement dit, en supposant l’ajout d’un fournisseur déjà défini nommé « S4Provider » ) :</span><span class="sxs-lookup"><span data-stu-id="61fa0-158">To define a new scenario, do the following (that is, assuming the addition of an already defined provider named "S4Provider"):</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    <span data-ttu-id="61fa0-159">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="61fa0-159">For example:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    <span data-ttu-id="61fa0-p112">Si vous souhaitez remplacer des fournisseurs, définissez un fournisseur unique ou une liste séparée par des virgules des fournisseurs pour remplacer l’ensemble actuel. Si vous souhaitez seulement remplacer l’un des fournisseurs, ajoutez les fournisseurs actuels aux nouveaux fournisseurs pour créer un nouvel ensemble de fournisseurs contenant les nouveaux fournisseurs et les fournisseurs existants. Pour remplacer tous les fournisseurs par un nouvel ensemble, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="61fa0-p112">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set. If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers. To replace all providers with a new set, type the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    <span data-ttu-id="61fa0-163">Par exemple, pour remplacer l’ensemble actuel comprenant $LyssProvider, $ABServerProvider et $SIPStackProvider par $LyssServiceProvider :</span><span class="sxs-lookup"><span data-stu-id="61fa0-163">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    <span data-ttu-id="61fa0-164">Pour remplacer seulement le fournisseur $LyssProvider de l’ensemble actuel comprenant $LyssProvider, $ABServerProvider et $SIPStackProvider par $LyssServiceProvider, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="61fa0-164">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="61fa0-165">Pour supprimer un scénario existant avec l’applet de commande Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="61fa0-165">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="61fa0-166">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="61fa0-166">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="61fa0-167">Si vous souhaitez supprimer un scénario précédemment défini, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="61fa0-167">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    <span data-ttu-id="61fa0-168">Par exemple, pour supprimer le scénario défini site:Redmond/LyssServiceScenario :</span><span class="sxs-lookup"><span data-stu-id="61fa0-168">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

<span data-ttu-id="61fa0-169">L’applet de commande **Remove-CsClsScenario** supprime le scénario spécifié, mais vous pouvez toujours accéder aux suivis capturés dans les journaux et lancer des recherches dans ceux-ci.</span><span class="sxs-lookup"><span data-stu-id="61fa0-169">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a><span data-ttu-id="61fa0-170">Pour charger et décharger lEdit-CsClsScenario cmdlet à l’aide du module ClsScenarioEdit.psm1</span><span class="sxs-lookup"><span data-stu-id="61fa0-170">To load and unload the Edit-CsClsScenario cmdlet using the ClsScenarioEdit.psm1 module</span></span>

1. <span data-ttu-id="61fa0-171">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="61fa0-171">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="61fa0-172">Le module ClsScenarioEdit.psm1 est fourni en tant que téléchargement Web distinct.</span><span class="sxs-lookup"><span data-stu-id="61fa0-172">The ClsScenarioEdit.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="61fa0-173">Le module fait partie des outils de débogage de Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="61fa0-173">The module is part of the Skype for Business Server 2015 Debugging tools.</span></span> <span data-ttu-id="61fa0-174">Par défaut, les outils de débogage sont installés dans le répertoire C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="61fa0-174">By default, the debugging tools are installed in the directory C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> 
  
2. <span data-ttu-id="61fa0-175">Dans la Windows PowerShell, tapez :</span><span class="sxs-lookup"><span data-stu-id="61fa0-175">From the Windows PowerShell, type:</span></span>
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="61fa0-176">Le chargement réussi du module vous renvoie à l’invite Windows PowerShell commande.</span><span class="sxs-lookup"><span data-stu-id="61fa0-176">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="61fa0-177">Pour confirmer que le module est chargé et que Edit-CsClsScenario est disponible, tapez  `Get-Help Edit-CsClsScenario` .</span><span class="sxs-lookup"><span data-stu-id="61fa0-177">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="61fa0-178">Le résumé de base de la syntaxe pour EditCsClsScenario doit apparaître.</span><span class="sxs-lookup"><span data-stu-id="61fa0-178">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="61fa0-179">Pour décharger les modules, tapez :</span><span class="sxs-lookup"><span data-stu-id="61fa0-179">To unload the modules, type:</span></span>
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > <span data-ttu-id="61fa0-180">Le déchargement réussi du module vous renvoie à l’invite Windows PowerShell commande.</span><span class="sxs-lookup"><span data-stu-id="61fa0-180">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="61fa0-181">Pour confirmer que le module est déchargé, tapez  `Get-Help Edit-CsClsScenario` .</span><span class="sxs-lookup"><span data-stu-id="61fa0-181">To confirm that the module is unloaded, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="61fa0-182">Windows PowerShell tenteront de trouver l’aide de la cmdlet et échoueront.</span><span class="sxs-lookup"><span data-stu-id="61fa0-182">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span> 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="61fa0-183">Pour supprimer un fournisseur existant d’un scénario avec le module Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="61fa0-183">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="61fa0-184">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="61fa0-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="61fa0-185">Dans la Windows PowerShell, tapez :</span><span class="sxs-lookup"><span data-stu-id="61fa0-185">From the Windows PowerShell, type:</span></span>
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="61fa0-186">Le chargement réussi du module vous renvoie à l’invite Windows PowerShell commande.</span><span class="sxs-lookup"><span data-stu-id="61fa0-186">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="61fa0-187">Pour confirmer que le module est chargé et que Edit-CsClsScenario est disponible, tapez  `Get-Help Edit-CsClsScenario` .</span><span class="sxs-lookup"><span data-stu-id="61fa0-187">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="61fa0-188">Le résumé de base de la syntaxe pour EditCsClsScenario doit apparaître.</span><span class="sxs-lookup"><span data-stu-id="61fa0-188">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="61fa0-189">Pour supprimer un fournisseur du scénario AlwaysOn, tapez :</span><span class="sxs-lookup"><span data-stu-id="61fa0-189">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   <span data-ttu-id="61fa0-190">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="61fa0-190">For Example:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   <span data-ttu-id="61fa0-p117">Les paramètres ScenarioName et ProviderName sont positionnels (c’est-à-dire qu’ils doivent être définis dans la position attendue dans la ligne de commande). Il n’est pas nécessaire de définir explicitement le nom du paramètre si le nom du scénario est en position deux et que le fournisseur est en position trois par rapport au nom de l’applet de commande (en position un). Compte tenu de ces informations, la commande précédente ressemble alors à ceci :</span><span class="sxs-lookup"><span data-stu-id="61fa0-p117">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters. The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one. Using this information, the previous command would be typed as:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   <span data-ttu-id="61fa0-194">Le placement positionnel des valeurs de paramètre s’applique uniquement à -Scenario et -Provider.</span><span class="sxs-lookup"><span data-stu-id="61fa0-194">The positional placing of the parameter values applies only to -Scenario and -Provider.</span></span> <span data-ttu-id="61fa0-195">Tous les autres paramètres doivent être définis explicitement.</span><span class="sxs-lookup"><span data-stu-id="61fa0-195">All other parameters must be explicitly defined.</span></span>
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="61fa0-196">Pour ajouter un fournisseur à un scénario avec le module Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="61fa0-196">To add a provider to a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="61fa0-197">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="61fa0-197">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="61fa0-198">Pour ajouter un fournisseur au scénario AlwaysOn, tapez :</span><span class="sxs-lookup"><span data-stu-id="61fa0-198">To add a provider to the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    <span data-ttu-id="61fa0-199">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="61fa0-199">For Example:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    <span data-ttu-id="61fa0-200">-Loglevel peut être du type Fatal, Error, Warning, Info, Verbose, Debug ou All.</span><span class="sxs-lookup"><span data-stu-id="61fa0-200">-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="61fa0-201">-Flags peut être l’un des indicateurs que le fournisseur prend en charge, tels que TF_COMPONENT, TF_DIAG.</span><span class="sxs-lookup"><span data-stu-id="61fa0-201">-Flags can be any of the flags that the provider supports, such as TF_COMPONENT, TF_DIAG.</span></span> <span data-ttu-id="61fa0-202">-Flags peut également être de valeur ALL</span><span class="sxs-lookup"><span data-stu-id="61fa0-202">-Flags can also be of value ALL</span></span>
    
   <span data-ttu-id="61fa0-p120">Il est aussi possible de taper l’exemple précédent à l’aide de la fonctionnalité positionnelle de l’applet de commande. Par exemple, pour ajouter le fournisseur ChatServer au scénario AlwaysOn, tapez :</span><span class="sxs-lookup"><span data-stu-id="61fa0-p120">The previous example can also be typed using the positional feature of the cmdlet. For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```

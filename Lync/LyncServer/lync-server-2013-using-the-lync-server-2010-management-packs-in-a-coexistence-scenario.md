---
title: Utiliser les packs d’administration de Lync Server 2010 dans un scénario de coexistence
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 159aaa55e61068356701abaed3c0a67a60265c75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a><span data-ttu-id="dc336-102">Utiliser les packs d’administration de Lync Server 2010 dans un scénario de coexistence</span><span class="sxs-lookup"><span data-stu-id="dc336-102">Using the Lync Server 2010 management packs in a coexistence scenario</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc336-103">_**Dernière modification de la rubrique:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="dc336-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="dc336-104">De nombreux clients adoptent un programme de déploiement au sein de leur entreprise, dans lequel les utilisateurs sont progressivement migrés de Microsoft Lync Server 2010 vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dc336-104">Many customers adopt a rollout program inside of their enterprises in which users are progressively migrated from Microsoft Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="dc336-105">Les administrateurs de ces entreprises se soucient de surveiller les deux versions de Lync Server pour s’assurer que tous leurs utilisateurs finaux bénéficient d’une meilleure utilisation de communication possible.</span><span class="sxs-lookup"><span data-stu-id="dc336-105">The administrators at these companies will care about monitoring both versions of Lync Server to help ensure that all of their end users are getting the best possible communication experience.</span></span> <span data-ttu-id="dc336-106">Dans le cas présent, le pack d’administration de Lync Server 2013 prend en charge un chemin de migration côte à côte avec le pack d’administration de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="dc336-106">For this scenario, the Lync Server 2013 Management Pack supports a side-by-side migration path with the Lync Server 2010 Management Pack.</span></span>

<span data-ttu-id="dc336-107">Sur Lync Server 2010, les ordinateurs Lync Server étaient détectés par le biais du document topologique stocké auprès du magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="dc336-107">In the Lync Server 2010, Lync Server computers were discovered through the topology document stored with the Central Management store.</span></span> <span data-ttu-id="dc336-108">Dans cette configuration, un ordinateur unique signale l’existence de tous les autres ordinateurs Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc336-108">In this configuration, a single computer would report the existence of all the other Lync Server computers.</span></span>

<span data-ttu-id="dc336-109">Les packs de gestion pour Lync Server 2013 utilisent désormais une découverte au niveau de l’ordinateur au lieu du mécanisme de découverte centralisé utilisé dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="dc336-109">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism that was used in Lync Server 2010.</span></span> <span data-ttu-id="dc336-110">Cela signifie que chaque agent système Centre de systèmes Découvre son existence et signale son existence à System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="dc336-110">This means that each System Center agent essentially discovers itself and reports its existence to System Center Operations Manager.</span></span> <span data-ttu-id="dc336-111">L’utilisation de la découverte au niveau de l’ordinateur simplifie l’administration de votre infrastructure de centre système et permet d’utiliser différentes versions des packs de gestion Lync Server (par exemple, les packs d’administration de Lync Server 2010 et les packs de gestion pour Lync Server 2013) pour pouvoir cohabiter plus facilement.</span><span class="sxs-lookup"><span data-stu-id="dc336-111">Using machine-level discovery simplifies administration of your System Center infrastructure and also enables different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist more easily.</span></span>

<span data-ttu-id="dc336-112">Pour prendre en charge cette migration, vous devez tout d’abord mettre à niveau votre analyse Lync Server 2010 existante afin d’éviter les lacunes en couverture.</span><span class="sxs-lookup"><span data-stu-id="dc336-112">To support this migration, you will first need to upgrade your existing Lync Server 2010 monitoring to avoid gaps in coverage.</span></span> <span data-ttu-id="dc336-113">Pour cela, vous devez choisir un ordinateur Lync Server 2010 existant pour gérer le script de découverte central pour Lync Server 2010 avant de mettre à niveau votre magasin de gestion centrale vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dc336-113">To do this, elect an existing Lync Server 2010 computer to service the Central Discovery script for the Lync Server 2010 before upgrading your Central Management store to Lync Server 2013.</span></span> <span data-ttu-id="dc336-114">Il s’agit d’un processus en quatre étapes:</span><span class="sxs-lookup"><span data-stu-id="dc336-114">This is a four-step process:</span></span>

1.  <span data-ttu-id="dc336-115">Effectuez la mise à niveau des packs d’administration de Lync Server 2010 vers la mise à jour cumulative 7.</span><span class="sxs-lookup"><span data-stu-id="dc336-115">Upgrade the Lync Server 2010 Management Packs to Cumulative Update 7.</span></span>

2.  <span data-ttu-id="dc336-116">Demandez à un ordinateur 2010 Lync Server d’exécuter le script de découverte central.</span><span class="sxs-lookup"><span data-stu-id="dc336-116">Instruct a Lync Server 2010 computer to run the Central Discovery script.</span></span>

3.  <span data-ttu-id="dc336-117">Remplacez le candidat de découverte central dans Microsoft Lync Server 2010 Management Pack.</span><span class="sxs-lookup"><span data-stu-id="dc336-117">Override the Central Discovery Candidate in the Microsoft Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="dc336-118">Vérifiez que le nouveau prototype de découverte centralisé a été découvert.</span><span class="sxs-lookup"><span data-stu-id="dc336-118">Verify that the new Central Discovery Candidate has been discovered.</span></span>

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a><span data-ttu-id="dc336-119">Demande à un ordinateur Lync Server 2010 d’exécuter le script de découverte central</span><span class="sxs-lookup"><span data-stu-id="dc336-119">Instructing a Lync Server 2010 Computer to Run the Central Discovery script</span></span>

<span data-ttu-id="dc336-120">Pour nommer un serveur du magasin de gestion non central (par exemple, un serveur frontal Lync Server) pour gérer la découverte centralisée, vous devez créer la clé de Registre suivante sur le serveur du magasin de gestion non central:</span><span class="sxs-lookup"><span data-stu-id="dc336-120">To nominate a non-Central Management store computer (for example, a Lync Server Front End) server to handle central discovery, you will need to create the following registry key on the non-Central Management store server:</span></span>

<span data-ttu-id="dc336-121">Programme\\HKLM\\logiciel\\Microsoft CentralDiscoveryCandidate de l'\\intégrité\\des communications en temps réel</span><span class="sxs-lookup"><span data-stu-id="dc336-121">HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span></span>

<span data-ttu-id="dc336-122">Vous pouvez créer cette clé de registre en effectuant les étapes suivantes:</span><span class="sxs-lookup"><span data-stu-id="dc336-122">You can create this registry key by completing the following procedure:</span></span>

1.  <span data-ttu-id="dc336-123">Cliquez sur **Démarrer** , puis sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="dc336-123">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="dc336-124">Dans la boîte de dialogue **exécuter** , tapez **regedit** , puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="dc336-124">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="dc336-125">Dans l’éditeur du Registre, développez l’application **HKEY\_\_local**, développez **logiciel**, développez **Microsoft**, puis développez **communications en temps réel**.</span><span class="sxs-lookup"><span data-stu-id="dc336-125">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, and then expand **Real-Time Communications**.</span></span>

4.  <span data-ttu-id="dc336-126">Cliquez avec le bouton droit sur **État**, cliquez sur **nouveau**, puis sur **clé**.</span><span class="sxs-lookup"><span data-stu-id="dc336-126">Right-click **Health**, click **New**, and then click **Key**.</span></span> <span data-ttu-id="dc336-127">S’il n’existe pas de clé d' **intégrité** , cliquez avec le bouton droit sur **communications en temps réel**, pointez sur **nouveau**, puis cliquez sur **clé**.</span><span class="sxs-lookup"><span data-stu-id="dc336-127">If the **Health** key does not exist, then right-click **Real-Time Communications**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="dc336-128">Lorsque la nouvelle clé est créée, tapez santé, puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="dc336-128">When the new key is created, type Health, and then press ENTER.</span></span>
    
    <span data-ttu-id="dc336-129">Une fois la nouvelle clé créée, tapez **CentralDiscoveryCandidate** , puis appuyez sur entrée pour renommer la clé.</span><span class="sxs-lookup"><span data-stu-id="dc336-129">After the new key has been created, type **CentralDiscoveryCandidate** and then press ENTER to rename the key.</span></span>

<span data-ttu-id="dc336-130">Le choix de l’ordinateur est susceptible de durer quelques heures.</span><span class="sxs-lookup"><span data-stu-id="dc336-130">It may take the computer several hours to pick up this change.</span></span> <span data-ttu-id="dc336-131">Pour que la modification prenne effet immédiatement, arrêtez, puis redémarrez le service agent d’intégrité.</span><span class="sxs-lookup"><span data-stu-id="dc336-131">To make the change take effect immediately, stop and then restart the Health Agent service.</span></span> <span data-ttu-id="dc336-132">Pour redémarrer le service agent d’intégrité, procédez comme suit sur l’ordinateur Lync Server 2010:</span><span class="sxs-lookup"><span data-stu-id="dc336-132">To restart the Health Agent service, complete the following procedure on the Lync Server 2010 computer:</span></span>

1.  <span data-ttu-id="dc336-133">Cliquez sur **Démarrer**, **sur tous les programmes**, sur **accessoires**, cliquez avec le bouton droit sur **invite de commandes**, puis cliquez sur **exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="dc336-133">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="dc336-134">Dans la fenêtre de la console, tapez la commande suivante, puis appuyez sur entrée:</span><span class="sxs-lookup"><span data-stu-id="dc336-134">In the console window, type the following command and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="dc336-135">Un message s’affiche, indiquant que le service de gestion de centre de systèmes s’arrête, suivi d’un deuxième message vous indiquant que le service a été arrêté.</span><span class="sxs-lookup"><span data-stu-id="dc336-135">You will see a message that states "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped.</span></span> <span data-ttu-id="dc336-136">Lorsque le service s’est arrêté, vous pouvez le redémarrer en entrant la commande suivante et en appuyant sur entrée:</span><span class="sxs-lookup"><span data-stu-id="dc336-136">After the service has stopped, you can restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a><span data-ttu-id="dc336-137">Remplacement du candidat de découverte central dans le pack d’administration de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="dc336-137">Overriding the Central Discovery Candidate in the Lync Server 2010 Management Pack</span></span>

<span data-ttu-id="dc336-138">Après avoir demandé à un ordinateur Lync Server 2010 de signaler des ordinateurs Lync Server 2010, vous devez en informer le pack d’administration de Lync Server 2010 à propos de cette modification.</span><span class="sxs-lookup"><span data-stu-id="dc336-138">After instructing a Lync Server 2010 computer to report on Lync Server 2010 computers, you will need to inform the Lync Server 2010 Management Pack about this change as well.</span></span> <span data-ttu-id="dc336-139">Pour cela, vous devez créer un remplacement dans le pack d’administration.</span><span class="sxs-lookup"><span data-stu-id="dc336-139">To do this, you will need to create an override in the Management Pack.</span></span> <span data-ttu-id="dc336-140">Pour cela, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="dc336-140">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="dc336-141">Dans la console Operations Manager, cliquez sur **création**.</span><span class="sxs-lookup"><span data-stu-id="dc336-141">In the Operations Manager console, click **Authoring**.</span></span>

2.  <span data-ttu-id="dc336-142">Dans l’onglet création, développez **objets du pack d’administration**, cliquez sur **découvertes d’objets**, puis cliquez sur **étendue**.</span><span class="sxs-lookup"><span data-stu-id="dc336-142">On the Authoring tab, expand **Management Pack Objects**, click **Object Discoveries**, and then click **Scope**.</span></span>

3.  <span data-ttu-id="dc336-143">Dans la boîte de dialogue **objets du pack d’administration** d’étendues, sélectionnez l’élément avec le **candidat de découverte Target LS** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc336-143">In the **Scope Management Pack Objects** dialog box, select the item with the Target **LS Discovery Candidate** and then click **OK**.</span></span> <span data-ttu-id="dc336-144">Notez que le prototype de découverte ne s’affichera que si vous avez installé le pack d’administration 2010 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc336-144">Note that LS Discovery Candidate will appear only if you have installed the Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="dc336-145">Dans la console Operations Manager, cliquez avec le bouton droit sur **candidat de découverte de LS**, pointez sur **remplacements**, pointez sur **remplacer la découverte d’objets**, puis cliquez sur **tous les objets de classe: ls découverte candidat**.</span><span class="sxs-lookup"><span data-stu-id="dc336-145">In the Operations Manager console, right-click **LS Discovery Candidate**, point to **Overrides**, point to **Override the Object Discovery**, and then click **For all objects of class: LS Discovery Candidate**.</span></span>

5.  <span data-ttu-id="dc336-146">Dans la boîte de dialogue **Propriétés de remplacement** , activez la case à cocher **remplacer** en regard du **nom de domaine complet de découverte WatcherNode**.</span><span class="sxs-lookup"><span data-stu-id="dc336-146">In the **Override Properties** dialog box, select the **Override** check box next to the parameter **Central Discovery WatcherNode Fqdn**.</span></span> <span data-ttu-id="dc336-147">Tapez le nom de domaine complet de l’ordinateur Lync Server 2010 dans les zones **valeur de remplacement** et **valeur effective** .</span><span class="sxs-lookup"><span data-stu-id="dc336-147">Type the fully qualified domain name of the Lync Server 2010 computer in the **Override Value** and **Effective Value** boxes.</span></span> <span data-ttu-id="dc336-148">Cochez la case **appliqué** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc336-148">Select the **Enforced** check box and click **OK**.</span></span>

<span data-ttu-id="dc336-149">Une fois que vous avez créé la substitution, vous devez redémarrer le service d’intégrité sur le serveur de gestion racine.</span><span class="sxs-lookup"><span data-stu-id="dc336-149">After you have created the override, you need to restart the health service on the Root Management Server.</span></span> <span data-ttu-id="dc336-150">Pour redémarrer le service d’intégrité, procédez comme suit sur le serveur de gestion racine:</span><span class="sxs-lookup"><span data-stu-id="dc336-150">To restart the health service, complete the following procedure on the Root Management Server:</span></span>

1.  <span data-ttu-id="dc336-151">Cliquez sur **Démarrer**, **sur tous les programmes**, sur **accessoires**, cliquez avec le bouton droit sur **invite de commandes**, puis cliquez sur **exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="dc336-151">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="dc336-152">Dans la fenêtre de la console, tapez la commande suivante, puis appuyez sur entrée:</span><span class="sxs-lookup"><span data-stu-id="dc336-152">In the console window, type the following command, and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="dc336-153">Un message s’affiche, indiquant que le service de gestion de centre de systèmes s’arrête, suivi d’un second message indiquant que le service a été arrêté.</span><span class="sxs-lookup"><span data-stu-id="dc336-153">You will see a message stating that "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped.</span></span> <span data-ttu-id="dc336-154">Lorsque le service s’est arrêté, vous pouvez le redémarrer en entrant la commande suivante et en appuyant sur entrée:</span><span class="sxs-lookup"><span data-stu-id="dc336-154">After the service has stopped, you can then restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a><span data-ttu-id="dc336-155">Vérifier que le nouveau candidat de découverte centralisé a été découvert</span><span class="sxs-lookup"><span data-stu-id="dc336-155">Verifying that the New Central Discovery Candidate Was Discovered</span></span>

<span data-ttu-id="dc336-156">Avant de procéder à la mise à niveau du magasin centralisé de gestion, vous devez vous assurer que le nouveau prototype de découverte central a été détecté par le pack d’administration 2010 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc336-156">The final step before upgrading Central Management store is to make sure that the new central discovery candidate was discovered by the Lync Server 2010 Management Pack.</span></span> <span data-ttu-id="dc336-157">Pour cela, ouvrez la console Operations Manager, puis cliquez sur surveillance.</span><span class="sxs-lookup"><span data-stu-id="dc336-157">To do this, open the Operations Manager console and then click Monitoring.</span></span> <span data-ttu-id="dc336-158">Dans l’onglet analyse, développez **État de Microsoft Lync Server 2010**, développez découverte de la **topologie**, puis cliquez sur **affichage État de découverte**.</span><span class="sxs-lookup"><span data-stu-id="dc336-158">On the Monitoring tab, expand **Microsoft Lync Server 2010 Health**, expand **Topology Discovery**, and then click **Discovery State View**.</span></span> <span data-ttu-id="dc336-159">Vérifiez qu’une ligne dans l’affichage comporte un **chemin d’accès** qui recense le nom de domaine complet de la fonction de découverte centrale.</span><span class="sxs-lookup"><span data-stu-id="dc336-159">Verify that a row in the display has a **Path** that lists the fully qualified domain name of the central discovery candidate.</span></span> <span data-ttu-id="dc336-160">Vous devez également vérifier que l’état de l’ordinateur est **correctement**signalé.</span><span class="sxs-lookup"><span data-stu-id="dc336-160">You should also verify that the computer state is reported as **Healthy**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


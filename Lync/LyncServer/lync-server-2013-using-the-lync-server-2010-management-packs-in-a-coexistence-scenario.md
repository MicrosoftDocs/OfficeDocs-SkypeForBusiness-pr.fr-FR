---
title: Utilisation des packs d’administration Lync Server 2010 dans un scénario de coexistence
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffc2aed62b9ad26fd1498787ecd3d58144a005b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a><span data-ttu-id="449c3-102">Utilisation des packs d’administration Lync Server 2010 dans un scénario de coexistence</span><span class="sxs-lookup"><span data-stu-id="449c3-102">Using the Lync Server 2010 management packs in a coexistence scenario</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="449c3-103">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="449c3-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="449c3-104">De nombreux clients adoptent un programme de déploiement au sein de leur entreprise, dans lequel les utilisateurs sont progressivement migrés de Microsoft Lync Server 2010 vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="449c3-104">Many customers adopt a rollout program inside of their enterprises in which users are progressively migrated from Microsoft Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="449c3-105">Les administrateurs de ces sociétés se soucient de surveiller les deux versions de Lync Server afin de s’assurer que tous les utilisateurs finaux bénéficient de la meilleure expérience de communication possible.</span><span class="sxs-lookup"><span data-stu-id="449c3-105">The administrators at these companies will care about monitoring both versions of Lync Server to help ensure that all of their end users are getting the best possible communication experience.</span></span> <span data-ttu-id="449c3-106">Dans ce scénario, le pack d’administration Lync Server 2013 prend en charge un chemin de migration côte à côte avec le pack d’administration Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="449c3-106">For this scenario, the Lync Server 2013 Management Pack supports a side-by-side migration path with the Lync Server 2010 Management Pack.</span></span>

<span data-ttu-id="449c3-107">Dans Lync Server 2010, les ordinateurs Lync Server ont été découverts via le document de topologie stocké avec le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="449c3-107">In the Lync Server 2010, Lync Server computers were discovered through the topology document stored with the Central Management store.</span></span> <span data-ttu-id="449c3-108">Dans cette configuration, un ordinateur unique signale l’existence de tous les autres ordinateurs Lync Server.</span><span class="sxs-lookup"><span data-stu-id="449c3-108">In this configuration, a single computer would report the existence of all the other Lync Server computers.</span></span>

<span data-ttu-id="449c3-109">Les packs d’administration de Lync Server 2013 utilisent désormais la découverte au niveau de l’ordinateur au lieu du mécanisme de découverte central utilisé dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="449c3-109">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism that was used in Lync Server 2010.</span></span> <span data-ttu-id="449c3-110">Cela signifie que chaque agent System Center se découvre lui-même et signale son existence à System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="449c3-110">This means that each System Center agent essentially discovers itself and reports its existence to System Center Operations Manager.</span></span> <span data-ttu-id="449c3-111">L’utilisation de la découverte au niveau de l’ordinateur simplifie l’administration de votre infrastructure System Center et permet également différentes versions des packs d’administration Lync Server (par exemple, les packs d’administration pour Lync Server 2010 et les packs d’administration pour Lync Server 2013) coexister plus facilement.</span><span class="sxs-lookup"><span data-stu-id="449c3-111">Using machine-level discovery simplifies administration of your System Center infrastructure and also enables different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist more easily.</span></span>

<span data-ttu-id="449c3-112">Pour prendre en charge cette migration, vous devez d’abord mettre à niveau votre surveillance Lync Server 2010 existante afin d’éviter les lacunes dans la couverture.</span><span class="sxs-lookup"><span data-stu-id="449c3-112">To support this migration, you will first need to upgrade your existing Lync Server 2010 monitoring to avoid gaps in coverage.</span></span> <span data-ttu-id="449c3-113">Pour ce faire, électionnez un ordinateur Lync Server 2010 existant afin de traiter le script de découverte centrale pour Lync Server 2010 avant de mettre à niveau votre magasin central de gestion vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="449c3-113">To do this, elect an existing Lync Server 2010 computer to service the Central Discovery script for the Lync Server 2010 before upgrading your Central Management store to Lync Server 2013.</span></span> <span data-ttu-id="449c3-114">Il s’agit d’un processus en quatre étapes :</span><span class="sxs-lookup"><span data-stu-id="449c3-114">This is a four-step process:</span></span>

1.  <span data-ttu-id="449c3-115">Mettez à niveau les packs d’administration Lync Server 2010 vers la mise à jour cumulative 7.</span><span class="sxs-lookup"><span data-stu-id="449c3-115">Upgrade the Lync Server 2010 Management Packs to Cumulative Update 7.</span></span>

2.  <span data-ttu-id="449c3-116">Demandez à un ordinateur Lync Server 2010 d’exécuter le script de découverte centrale.</span><span class="sxs-lookup"><span data-stu-id="449c3-116">Instruct a Lync Server 2010 computer to run the Central Discovery script.</span></span>

3.  <span data-ttu-id="449c3-117">Remplacez le candidat de détection centrale dans le pack d’administration Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="449c3-117">Override the Central Discovery Candidate in the Microsoft Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="449c3-118">Vérifier que le nouveau candidat de détection centrale a été détecté.</span><span class="sxs-lookup"><span data-stu-id="449c3-118">Verify that the new Central Discovery Candidate has been discovered.</span></span>

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a><span data-ttu-id="449c3-119">Indiquer à un ordinateur Lync Server 2010 d’exécuter le script de détection centrale</span><span class="sxs-lookup"><span data-stu-id="449c3-119">Instructing a Lync Server 2010 Computer to Run the Central Discovery script</span></span>

<span data-ttu-id="449c3-120">Pour désigner un ordinateur de magasin de gestion non central (par exemple, un serveur frontal Lync Server) pour gérer la découverte centrale, vous devrez créer la clé de Registre suivante sur le serveur de magasin de gestion non central :</span><span class="sxs-lookup"><span data-stu-id="449c3-120">To nominate a non-Central Management store computer (for example, a Lync Server Front End) server to handle central discovery, you will need to create the following registry key on the non-Central Management store server:</span></span>

<span data-ttu-id="449c3-121">HKLM\\Software\\Microsoft\\Real-Time communications\\Health\\CentralDiscoveryCandidate</span><span class="sxs-lookup"><span data-stu-id="449c3-121">HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span></span>

<span data-ttu-id="449c3-122">Vous pouvez créer cette clé de registre en procédant ainsi :</span><span class="sxs-lookup"><span data-stu-id="449c3-122">You can create this registry key by completing the following procedure:</span></span>

1.  <span data-ttu-id="449c3-123">Cliquez sur **Démarrer**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="449c3-123">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="449c3-124">Dans la boîte de dialogue **Exécuter**, tapez **regedit**, puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="449c3-124">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="449c3-125">Dans l’éditeur du Registre, développez **HKEY\_\_local machine**, **Software**, **Microsoft**, puis **Real-Time communications**.</span><span class="sxs-lookup"><span data-stu-id="449c3-125">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, and then expand **Real-Time Communications**.</span></span>

4.  <span data-ttu-id="449c3-p105">Cliquez avec le bouton droit sur **Health**, cliquez sur **Nouveau**, sur **Clé**. Si la clé **Health** n’existe pas, cliquez avec le bouton droit sur **Real-Time Communications**, pointez sur **Nouveau**, puis cliquez sur **Clé**. Une fois la nouvelle clé créée, tapez Health, et appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="449c3-p105">Right-click **Health**, click **New**, and then click **Key**. If the **Health** key does not exist, then right-click **Real-Time Communications**, point to **New**, and then click **Key**. When the new key is created, type Health, and then press ENTER.</span></span>
    
    <span data-ttu-id="449c3-129">Une fois la nouvelle clé créée, tapez **CentralDiscoveryCandidate** et appuyez sur Entrée pour renommer la clé.</span><span class="sxs-lookup"><span data-stu-id="449c3-129">After the new key has been created, type **CentralDiscoveryCandidate** and then press ENTER to rename the key.</span></span>

<span data-ttu-id="449c3-130">L’application de cette modification peut prendre plusieurs heures.</span><span class="sxs-lookup"><span data-stu-id="449c3-130">It may take the computer several hours to pick up this change.</span></span> <span data-ttu-id="449c3-131">Pour que cette modification soit appliquée immédiatement, arrêtez et redémarrez le service de l’agent d’intégrité.</span><span class="sxs-lookup"><span data-stu-id="449c3-131">To make the change take effect immediately, stop and then restart the Health Agent service.</span></span> <span data-ttu-id="449c3-132">Pour redémarrer le service d’agent d’intégrité, effectuez la procédure suivante sur l’ordinateur Lync Server 2010 :</span><span class="sxs-lookup"><span data-stu-id="449c3-132">To restart the Health Agent service, complete the following procedure on the Lync Server 2010 computer:</span></span>

1.  <span data-ttu-id="449c3-133">Cliquez sur **Démarrer**, sur **Tous les programmes**, puis sur **Accessoires**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="449c3-133">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="449c3-134">Dans la fenêtre de console, tapez la commande suivante, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="449c3-134">In the console window, type the following command and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="449c3-p107">Un message s’affiche indiquant que « Le service System Center Management est en cours d’arrêt », suivi par un second message qui vous indique que le service est arrêté. Une fois le service arrêté, vous pouvez le redémarrer en tapant la commande suivante et en appuyant sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="449c3-p107">You will see a message that states "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped. After the service has stopped, you can restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a><span data-ttu-id="449c3-137">Remplacement du candidat de détection centrale dans le pack d’administration Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="449c3-137">Overriding the Central Discovery Candidate in the Lync Server 2010 Management Pack</span></span>

<span data-ttu-id="449c3-138">Après avoir demandé à un ordinateur Lync Server 2010 de générer des rapports sur les ordinateurs Lync Server 2010, vous devrez également informer le pack d’administration Lync Server 2010 de cette modification.</span><span class="sxs-lookup"><span data-stu-id="449c3-138">After instructing a Lync Server 2010 computer to report on Lync Server 2010 computers, you will need to inform the Lync Server 2010 Management Pack about this change as well.</span></span> <span data-ttu-id="449c3-139">Pour ce faire, vous devez créer un remplacement dans le pack d’administration.</span><span class="sxs-lookup"><span data-stu-id="449c3-139">To do this, you will need to create an override in the Management Pack.</span></span> <span data-ttu-id="449c3-140">Pour cela, effectuez la procédure suivante :</span><span class="sxs-lookup"><span data-stu-id="449c3-140">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="449c3-141">Dans la console Operations Manager, cliquez sur **Création**.</span><span class="sxs-lookup"><span data-stu-id="449c3-141">In the Operations Manager console, click **Authoring**.</span></span>

2.  <span data-ttu-id="449c3-142">Sous l’onglet Création, développez **Objets du pack d’administration**, cliquez sur **Détections d’objets**, puis sur **Étendue**.</span><span class="sxs-lookup"><span data-stu-id="449c3-142">On the Authoring tab, expand **Management Pack Objects**, click **Object Discoveries**, and then click **Scope**.</span></span>

3.  <span data-ttu-id="449c3-143">Dans la boîte de dialogue **Étendre les objets du pack d’administration**, sélectionnez l’élément avec le **Candidat de détection LS** cible, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="449c3-143">In the **Scope Management Pack Objects** dialog box, select the item with the Target **LS Discovery Candidate** and then click **OK**.</span></span> <span data-ttu-id="449c3-144">Notez que le candidat de détection LS n’apparaîtra que si vous avez installé le pack d’administration Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="449c3-144">Note that LS Discovery Candidate will appear only if you have installed the Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="449c3-145">Dans la console Operations Manager, cliquez avec le bouton droit sur **Candidat de détection LS**, pointez sur **Remplacements**, sur **Remplacer la détection d’objets**, puis cliquez sur **Pour tous les objets de la classe : candidat de détection LS**.</span><span class="sxs-lookup"><span data-stu-id="449c3-145">In the Operations Manager console, right-click **LS Discovery Candidate**, point to **Overrides**, point to **Override the Object Discovery**, and then click **For all objects of class: LS Discovery Candidate**.</span></span>

5.  <span data-ttu-id="449c3-146">Dans la boîte de dialogue **Propriétés du remplacement**, cochez la case **Remplacer** en regard du paramètre **Fqdn nœud observateur détection centrale**.</span><span class="sxs-lookup"><span data-stu-id="449c3-146">In the **Override Properties** dialog box, select the **Override** check box next to the parameter **Central Discovery WatcherNode Fqdn**.</span></span> <span data-ttu-id="449c3-147">Tapez le nom de domaine complet de l’ordinateur Lync Server 2010 dans les zones **valeur de remplacement** et **valeur effective** .</span><span class="sxs-lookup"><span data-stu-id="449c3-147">Type the fully qualified domain name of the Lync Server 2010 computer in the **Override Value** and **Effective Value** boxes.</span></span> <span data-ttu-id="449c3-148">Cochez la case **Appliqué**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="449c3-148">Select the **Enforced** check box and click **OK**.</span></span>

<span data-ttu-id="449c3-p111">Une fois le remplacement créé, vous devez redémarrer le service de contrôle d’intégrité sur le serveur d’administration racine. Pour redémarrer le service, procédez ainsi sur le serveur d’administration racine :</span><span class="sxs-lookup"><span data-stu-id="449c3-p111">After you have created the override, you need to restart the health service on the Root Management Server. To restart the health service, complete the following procedure on the Root Management Server:</span></span>

1.  <span data-ttu-id="449c3-151">Cliquez sur **Démarrer**, sur **Tous les programmes**, puis sur **Accessoires**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="449c3-151">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="449c3-152">Dans la fenêtre de console, tapez la commande suivante, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="449c3-152">In the console window, type the following command, and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="449c3-p112">Un message s’affiche indiquant que « Le service System Center Management est en cours d’arrêt », suivi par un second message qui vous indique que le service est arrêté. Une fois le service arrêté, vous pouvez le redémarrer en tapant la commande suivante et en appuyant sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="449c3-p112">You will see a message stating that "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped. After the service has stopped, you can then restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a><span data-ttu-id="449c3-155">Vérification que le nouveau candidat de détection centrale a été détecté</span><span class="sxs-lookup"><span data-stu-id="449c3-155">Verifying that the New Central Discovery Candidate Was Discovered</span></span>

<span data-ttu-id="449c3-156">La dernière étape avant la mise à niveau du magasin central de gestion est de s’assurer que le nouveau candidat de découverte central a été découvert par le pack d’administration Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="449c3-156">The final step before upgrading Central Management store is to make sure that the new central discovery candidate was discovered by the Lync Server 2010 Management Pack.</span></span> <span data-ttu-id="449c3-157">Pour ce faire, ouvrez la console Operations Manager, puis cliquez sur Analyse.</span><span class="sxs-lookup"><span data-stu-id="449c3-157">To do this, open the Operations Manager console and then click Monitoring.</span></span> <span data-ttu-id="449c3-158">Sous l’onglet Analyse, développez **Intégrité Microsoft Lync Server 2010**, **Découverte de la topologie**, puis cliquez sur **Affichage des états de détection**.</span><span class="sxs-lookup"><span data-stu-id="449c3-158">On the Monitoring tab, expand **Microsoft Lync Server 2010 Health**, expand **Topology Discovery**, and then click **Discovery State View**.</span></span> <span data-ttu-id="449c3-159">Vérifiez qu’une ligne de l’affichage comprend un **Chemin** qui répertorie le nom de domaine complet du candidat de détection central.</span><span class="sxs-lookup"><span data-stu-id="449c3-159">Verify that a row in the display has a **Path** that lists the fully qualified domain name of the central discovery candidate.</span></span> <span data-ttu-id="449c3-160">Vérifiez également que l’état de l’ordinateur est **Sain**.</span><span class="sxs-lookup"><span data-stu-id="449c3-160">You should also verify that the computer state is reported as **Healthy**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


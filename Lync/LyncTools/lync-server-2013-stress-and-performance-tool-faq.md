---
title: Forum aux questions sur l’outil contraintes et performances de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffcfbca3a2cf58e4e7b87619bb78dabbe42b16bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a><span data-ttu-id="d16da-102">Forum aux questions sur l’outil contraintes et performances de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d16da-102">Lync Server 2013 Stress and Performance Tool FAQ</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d16da-103">_**Dernière modification de la rubrique:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="d16da-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="d16da-104">Forum aux questions</span><span class="sxs-lookup"><span data-stu-id="d16da-104">Frequently Asked Questions</span></span>

<span data-ttu-id="d16da-105">Voici quelques questions fréquemment posées sur l’outil de stress et de performances de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d16da-105">Here are some frequently asked questions about the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="d16da-106">Est-il possible d’exécuter LyncPerfTool. exe en production?</span><span class="sxs-lookup"><span data-stu-id="d16da-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="d16da-107">Nous déconseillons de le faire.</span><span class="sxs-lookup"><span data-stu-id="d16da-107">We do not recommend this.</span></span> <span data-ttu-id="d16da-108">Cet outil aura un impact sur les performances, la sécurité et l’interface utilisateur du serveur.</span><span class="sxs-lookup"><span data-stu-id="d16da-108">This tool will impact server performance, security, and user experience.</span></span>

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a><span data-ttu-id="d16da-109">Je me connecte pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="d16da-109">I am logging on my users for the first time.</span></span> <span data-ttu-id="d16da-110">Pourquoi les serveurs s’exécutent-ils sur une telle charge?</span><span class="sxs-lookup"><span data-stu-id="d16da-110">Why are the servers running at such high load?</span></span>

<span data-ttu-id="d16da-111">La première fois que les utilisateurs se connectent, il existe d’autres opérations.</span><span class="sxs-lookup"><span data-stu-id="d16da-111">The first time the users log on, there are additional operations that occur.</span></span> <span data-ttu-id="d16da-112">C’est la raison pour laquelle les performances du serveur principal Microsoft SQL Server sont détériorées.</span><span class="sxs-lookup"><span data-stu-id="d16da-112">As a result, the performance on the Microsoft SQL Server Back End Server will be degraded.</span></span> <span data-ttu-id="d16da-113">Nous vous recommandons d’effectuer un test de courte durée de connexion pour tous les utilisateurs, puis de redémarrer les clients avant de procéder à la mesure des résultats.</span><span class="sxs-lookup"><span data-stu-id="d16da-113">We recommend that you run a short test that logs on all of the users, and then restart the clients before you measure results.</span></span> <span data-ttu-id="d16da-114">Nous ne prenons pas en charge plus de 12 sessions d’ouverture de session simultanées par seconde, mais cela dépend de votre configuration matérielle.</span><span class="sxs-lookup"><span data-stu-id="d16da-114">We do not support more than 12 concurrent user logon sessions per second, but this depends on your hardware configuration.</span></span>

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="d16da-115">Mes clients manquent de mémoire.</span><span class="sxs-lookup"><span data-stu-id="d16da-115">My clients are running out of memory.</span></span> <span data-ttu-id="d16da-116">Que dois-je faire?</span><span class="sxs-lookup"><span data-stu-id="d16da-116">What should I do?</span></span>

<span data-ttu-id="d16da-117">Si vos clients manquent de mémoire, vous devez réduire le nombre d’utilisateurs par ordinateur.</span><span class="sxs-lookup"><span data-stu-id="d16da-117">If your clients are running out of memory, you need to reduce the number of users per computer.</span></span>

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a><span data-ttu-id="d16da-118">Mes clients utilisent tout le temps de 100%.</span><span class="sxs-lookup"><span data-stu-id="d16da-118">My clients are at 100 percent CPU all the time.</span></span> <span data-ttu-id="d16da-119">Que dois-je faire?</span><span class="sxs-lookup"><span data-stu-id="d16da-119">What should I do?</span></span>

<span data-ttu-id="d16da-120">Si vos clients s’exécutent avec une UC très élevée alors que tous les utilisateurs sont connectés, vous devez réduire le nombre d’utilisateurs par ordinateur.</span><span class="sxs-lookup"><span data-stu-id="d16da-120">If your clients are running with very high CPU after all the users have logged on, you need to reduce the number of users per computer.</span></span> <span data-ttu-id="d16da-121">Les pics d’UC élevés sont acceptables, mais si la charge est soutenue, vous devez réduire la charge.</span><span class="sxs-lookup"><span data-stu-id="d16da-121">High CPU spikes are acceptable, but if it is sustained, you need to reduce the load.</span></span>

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a><span data-ttu-id="d16da-122">Est-il possible d’exécuter l’outil sur le serveur lui-même?</span><span class="sxs-lookup"><span data-stu-id="d16da-122">Can I run the tool on the server itself?</span></span>

<span data-ttu-id="d16da-123">Non.</span><span class="sxs-lookup"><span data-stu-id="d16da-123">No.</span></span> <span data-ttu-id="d16da-124">Ce scénario n’est pas pris en charge et peut échouer en raison d’une incompatibilité binaire.</span><span class="sxs-lookup"><span data-stu-id="d16da-124">This scenario is not supported and may fail due to a binary mismatch.</span></span> <span data-ttu-id="d16da-125">Par ailleurs, dans la mesure où le point est de mesurer la consommation de ressources sur le serveur, l’exécution de l’outil génère un rendu inutile des mesures.</span><span class="sxs-lookup"><span data-stu-id="d16da-125">Also, because the point is to measure resource consumption on the server, running the tool there would render the measurements meaningless.</span></span>

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="d16da-126">Est-il possible d’exécuter LyncPerfTool. exe sur un serveur virtuel ou sur Microsoft Hyper-V Server 2008/2012?</span><span class="sxs-lookup"><span data-stu-id="d16da-126">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="d16da-127">Oui.</span><span class="sxs-lookup"><span data-stu-id="d16da-127">Yes.</span></span>

</div>

<div>

## <a name="what-does-mpop-mean"></a><span data-ttu-id="d16da-128">Qu’est-ce que MPOP?</span><span class="sxs-lookup"><span data-stu-id="d16da-128">What does MPOP mean?</span></span>

<span data-ttu-id="d16da-129">MPOP représente plusieurs points de présence.</span><span class="sxs-lookup"><span data-stu-id="d16da-129">MPOP stands for multiple points of presence.</span></span> <span data-ttu-id="d16da-130">Il est conçu pour simuler le scénario dans lequel les utilisateurs sont connectés à Lync 2013 à partir de plusieurs ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="d16da-130">It is meant to simulate the scenario where users are logged on to Lync 2013 from multiple machines.</span></span> <span data-ttu-id="d16da-131">Notez que dans LyncPerfTool. exe, chaque point de terminaison utilise le profil par défaut (autrement dit, le profil n’est pas fractionné entre les deux points de présence).</span><span class="sxs-lookup"><span data-stu-id="d16da-131">Note that in LyncPerfTool.exe, each endpoint uses the default profile (that is, the profile is not split between the two points of presence).</span></span>

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="d16da-132">J’ai démarré LyncPerfTool. exe, mais rien ne se passe.</span><span class="sxs-lookup"><span data-stu-id="d16da-132">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="d16da-133">Que se passe-t-il?</span><span class="sxs-lookup"><span data-stu-id="d16da-133">What’s going on?</span></span>

<span data-ttu-id="d16da-134">Vérifiez le compteur total de points de terminaison actifs sur les clients pour voir si les utilisateurs se connectent.</span><span class="sxs-lookup"><span data-stu-id="d16da-134">Check the Total Active Endpoints counter on the clients to see if the users are connecting.</span></span> <span data-ttu-id="d16da-135">Si les utilisateurs ne se connectent pas, vérifiez votre configuration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d16da-135">If users are not connecting, verify your Lync Server 2013 configuration.</span></span> <span data-ttu-id="d16da-136">Ce problème se produit généralement lorsque le nom du serveur, le préfixe d’utilisateur ou le mot de passe est incorrect.</span><span class="sxs-lookup"><span data-stu-id="d16da-136">This issue usually occurs because the server name, the user prefix, or the password is incorrect.</span></span> <span data-ttu-id="d16da-137">Notez que les clients externes doivent spécifier le proxy d’accès comme valeur TargetServer.</span><span class="sxs-lookup"><span data-stu-id="d16da-137">Note that external clients should specify the Access Proxy as the TargetServer value.</span></span> <span data-ttu-id="d16da-138">Vérifiez le port dans le fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="d16da-138">Verify the port in the configuration file.</span></span>

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a><span data-ttu-id="d16da-139">Comment savoir si un événement se produit?</span><span class="sxs-lookup"><span data-stu-id="d16da-139">How do I know something is happening?</span></span>

<span data-ttu-id="d16da-140">Les différents compteurs de performance LyncPerfTool indiquent si les utilisateurs se connectent et exécutent des actions.</span><span class="sxs-lookup"><span data-stu-id="d16da-140">The various LyncPerfTool performance counters indicate whether or not users are connecting and performing actions.</span></span> <span data-ttu-id="d16da-141">Toutefois, une méthode simple pour vérifier consiste à se connecter à l’un des comptes à l’aide de Lync 2013 et à effectuer l’action souhaitée.</span><span class="sxs-lookup"><span data-stu-id="d16da-141">However, an easy way to check is to log on to one of the accounts by using Lync 2013 and performing the action you want.</span></span>

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a><span data-ttu-id="d16da-142">J’ai installé les outils de planification de capacité de Live Communications Server 2007 R2 et/ou Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d16da-142">I have Live Communications Server 2007 R2 Capacity Planning Tools and/or Lync Server 2010 installed.</span></span> <span data-ttu-id="d16da-143">C’est tout!</span><span class="sxs-lookup"><span data-stu-id="d16da-143">Is that OK?</span></span>

<span data-ttu-id="d16da-144">Non.</span><span class="sxs-lookup"><span data-stu-id="d16da-144">No.</span></span> <span data-ttu-id="d16da-145">Il existe des problèmes d’interopérabilité et vous devez désinstaller toutes les versions précédentes de ce produit.</span><span class="sxs-lookup"><span data-stu-id="d16da-145">There are interoperability issues, and you must uninstall all previous versions of this product.</span></span>

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="d16da-146">Les outils de stress et de performance configureront-ils la topologie du serveur des informations d’appel CAA?</span><span class="sxs-lookup"><span data-stu-id="d16da-146">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="d16da-147">Non.</span><span class="sxs-lookup"><span data-stu-id="d16da-147">No.</span></span> <span data-ttu-id="d16da-148">Les outils créent uniquement des utilisateurs, des contacts et des listes de distribution et simulent la charge des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d16da-148">The tools only create users, contacts, and distribution lists, and simulate user load.</span></span>

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="d16da-149">Quel est le nombre maximal d’utilisateurs pris en charge par les outils?</span><span class="sxs-lookup"><span data-stu-id="d16da-149">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="d16da-150">Nous avons créé un total de 80 000 utilisateurs et des tests exécutés totalisant 30 000 utilisateurs, à l’aide de ces outils.</span><span class="sxs-lookup"><span data-stu-id="d16da-150">We have created up to a total of 80,000 users and executed tests totaling 30,000 users, using these tools.</span></span> <span data-ttu-id="d16da-151">Nous vous suggérons d’utiliser un maximum de 120 000 utilisateurs, même si les limitations techniques autorisent une plus grande valeur, en fonction du matériel du serveur et du serveur disponibles.</span><span class="sxs-lookup"><span data-stu-id="d16da-151">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher value, depending on the client and server hardware available.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


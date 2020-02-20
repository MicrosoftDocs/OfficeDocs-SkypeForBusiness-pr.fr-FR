---
title: Forum aux questions sur l’outil de contrainte et de performances de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6c4a9909bfecd8157fe3afe9f653a684fe1053b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a><span data-ttu-id="da80f-102">Forum aux questions sur l’outil de contrainte et de performances de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da80f-102">Lync Server 2013 Stress and Performance Tool FAQ</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da80f-103">_**Dernière modification de la rubrique :** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="da80f-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="da80f-104">Forum Aux Questions</span><span class="sxs-lookup"><span data-stu-id="da80f-104">Frequently Asked Questions</span></span>

<span data-ttu-id="da80f-105">Voici quelques questions fréquemment posées sur l’outil de contrainte et de performances de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="da80f-105">Here are some frequently asked questions about the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="da80f-106">Puis-je exécuter LyncPerfTool. exe en production ?</span><span class="sxs-lookup"><span data-stu-id="da80f-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="da80f-107">Nous vous déconseillons de le faire.</span><span class="sxs-lookup"><span data-stu-id="da80f-107">We do not recommend this.</span></span> <span data-ttu-id="da80f-108">Cet outil aura un impact sur les performances, la sécurité et l’expérience utilisateur du serveur.</span><span class="sxs-lookup"><span data-stu-id="da80f-108">This tool will impact server performance, security, and user experience.</span></span>

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a><span data-ttu-id="da80f-109">Je me connecte pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="da80f-109">I am logging on my users for the first time.</span></span> <span data-ttu-id="da80f-110">Pourquoi les serveurs fonctionnent-ils à cette charge élevée ?</span><span class="sxs-lookup"><span data-stu-id="da80f-110">Why are the servers running at such high load?</span></span>

<span data-ttu-id="da80f-111">La première fois que les utilisateurs se connectent, des opérations supplémentaires se produisent.</span><span class="sxs-lookup"><span data-stu-id="da80f-111">The first time the users log on, there are additional operations that occur.</span></span> <span data-ttu-id="da80f-112">Par conséquent, les performances du serveur principal Microsoft SQL Server seront dégradées.</span><span class="sxs-lookup"><span data-stu-id="da80f-112">As a result, the performance on the Microsoft SQL Server Back End Server will be degraded.</span></span> <span data-ttu-id="da80f-113">Nous vous recommandons d’exécuter un test court qui ouvre une session sur tous les utilisateurs, puis de redémarrer les clients avant de mesurer les résultats.</span><span class="sxs-lookup"><span data-stu-id="da80f-113">We recommend that you run a short test that logs on all of the users, and then restart the clients before you measure results.</span></span> <span data-ttu-id="da80f-114">Nous ne prenons pas en charge plus de 12 sessions de connexion utilisateur simultanées par seconde, mais cela dépend de votre configuration matérielle.</span><span class="sxs-lookup"><span data-stu-id="da80f-114">We do not support more than 12 concurrent user logon sessions per second, but this depends on your hardware configuration.</span></span>

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="da80f-115">Mes clients manquent de mémoire.</span><span class="sxs-lookup"><span data-stu-id="da80f-115">My clients are running out of memory.</span></span> <span data-ttu-id="da80f-116">Que dois-je faire ?</span><span class="sxs-lookup"><span data-stu-id="da80f-116">What should I do?</span></span>

<span data-ttu-id="da80f-117">Si la mémoire de vos clients est insuffisante, vous devez réduire le nombre d’utilisateurs par ordinateur.</span><span class="sxs-lookup"><span data-stu-id="da80f-117">If your clients are running out of memory, you need to reduce the number of users per computer.</span></span>

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a><span data-ttu-id="da80f-118">Mon client dispose d’un processeur de 100% en tout temps.</span><span class="sxs-lookup"><span data-stu-id="da80f-118">My clients are at 100 percent CPU all the time.</span></span> <span data-ttu-id="da80f-119">Que dois-je faire ?</span><span class="sxs-lookup"><span data-stu-id="da80f-119">What should I do?</span></span>

<span data-ttu-id="da80f-120">Si vos clients s’exécutent avec un processeur très élevé une fois que tous les utilisateurs ont ouvert une session, vous devez réduire le nombre d’utilisateurs par ordinateur.</span><span class="sxs-lookup"><span data-stu-id="da80f-120">If your clients are running with very high CPU after all the users have logged on, you need to reduce the number of users per computer.</span></span> <span data-ttu-id="da80f-121">Les pics d’utilisation du processeur élevés sont acceptables, mais si elle est soutenue, vous devez réduire la charge.</span><span class="sxs-lookup"><span data-stu-id="da80f-121">High CPU spikes are acceptable, but if it is sustained, you need to reduce the load.</span></span>

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a><span data-ttu-id="da80f-122">Puis-je exécuter l’outil sur le serveur lui-même ?</span><span class="sxs-lookup"><span data-stu-id="da80f-122">Can I run the tool on the server itself?</span></span>

<span data-ttu-id="da80f-123">Non.</span><span class="sxs-lookup"><span data-stu-id="da80f-123">No.</span></span> <span data-ttu-id="da80f-124">Ce scénario n’est pas pris en charge et peut échouer en raison d’une incompatibilité binaire.</span><span class="sxs-lookup"><span data-stu-id="da80f-124">This scenario is not supported and may fail due to a binary mismatch.</span></span> <span data-ttu-id="da80f-125">En outre, étant donné que le point est de mesurer la consommation des ressources sur le serveur, l’exécution de l’outil peut rendre les mesures sans signification.</span><span class="sxs-lookup"><span data-stu-id="da80f-125">Also, because the point is to measure resource consumption on the server, running the tool there would render the measurements meaningless.</span></span>

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="da80f-126">Puis-je exécuter LyncPerfTool. exe sur un serveur virtuel ou sur Microsoft Hyper-V Server 2008/2012 ?</span><span class="sxs-lookup"><span data-stu-id="da80f-126">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="da80f-127">Oui.</span><span class="sxs-lookup"><span data-stu-id="da80f-127">Yes.</span></span>

</div>

<div>

## <a name="what-does-mpop-mean"></a><span data-ttu-id="da80f-128">Qu’est-ce que MPOP signifie ?</span><span class="sxs-lookup"><span data-stu-id="da80f-128">What does MPOP mean?</span></span>

<span data-ttu-id="da80f-129">MPOP signifie plusieurs points de présence.</span><span class="sxs-lookup"><span data-stu-id="da80f-129">MPOP stands for multiple points of presence.</span></span> <span data-ttu-id="da80f-130">Il est conçu pour simuler le scénario dans lequel les utilisateurs sont connectés à Lync 2013 à partir de plusieurs machines.</span><span class="sxs-lookup"><span data-stu-id="da80f-130">It is meant to simulate the scenario where users are logged on to Lync 2013 from multiple machines.</span></span> <span data-ttu-id="da80f-131">Notez que dans LyncPerfTool. exe, chaque point de terminaison utilise le profil par défaut (autrement dit, le profil n’est pas fractionné entre les deux points de présence).</span><span class="sxs-lookup"><span data-stu-id="da80f-131">Note that in LyncPerfTool.exe, each endpoint uses the default profile (that is, the profile is not split between the two points of presence).</span></span>

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="da80f-132">J’ai démarré LyncPerfTool. exe mais rien ne se passe.</span><span class="sxs-lookup"><span data-stu-id="da80f-132">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="da80f-133">Que se passe-t-il ?</span><span class="sxs-lookup"><span data-stu-id="da80f-133">What’s going on?</span></span>

<span data-ttu-id="da80f-134">Vérifiez le compteur nombre total de points de terminaison actifs sur les clients pour voir si les utilisateurs se connectent.</span><span class="sxs-lookup"><span data-stu-id="da80f-134">Check the Total Active Endpoints counter on the clients to see if the users are connecting.</span></span> <span data-ttu-id="da80f-135">Si les utilisateurs ne se connectent pas, vérifiez votre configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="da80f-135">If users are not connecting, verify your Lync Server 2013 configuration.</span></span> <span data-ttu-id="da80f-136">Ce problème se produit généralement lorsque le nom du serveur, le préfixe d’utilisateur ou le mot de passe est incorrect.</span><span class="sxs-lookup"><span data-stu-id="da80f-136">This issue usually occurs because the server name, the user prefix, or the password is incorrect.</span></span> <span data-ttu-id="da80f-137">Notez que les clients externes doivent spécifier le proxy d’accès comme valeur de TargetServer.</span><span class="sxs-lookup"><span data-stu-id="da80f-137">Note that external clients should specify the Access Proxy as the TargetServer value.</span></span> <span data-ttu-id="da80f-138">Vérifiez le port dans le fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="da80f-138">Verify the port in the configuration file.</span></span>

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a><span data-ttu-id="da80f-139">Comment puis-je savoir ce qu’il se passe ?</span><span class="sxs-lookup"><span data-stu-id="da80f-139">How do I know something is happening?</span></span>

<span data-ttu-id="da80f-140">Les différents compteurs de performance LyncPerfTool indiquent si les utilisateurs se connectent et exécutent des actions.</span><span class="sxs-lookup"><span data-stu-id="da80f-140">The various LyncPerfTool performance counters indicate whether or not users are connecting and performing actions.</span></span> <span data-ttu-id="da80f-141">Toutefois, il est facile de vérifier qu’il est possible de se connecter à l’un des comptes à l’aide de Lync 2013 et d’effectuer l’action souhaitée.</span><span class="sxs-lookup"><span data-stu-id="da80f-141">However, an easy way to check is to log on to one of the accounts by using Lync 2013 and performing the action you want.</span></span>

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a><span data-ttu-id="da80f-142">Les outils de planification de capacité de Live Communications Server 2007 R2 et/ou Lync Server 2010 sont installés.</span><span class="sxs-lookup"><span data-stu-id="da80f-142">I have Live Communications Server 2007 R2 Capacity Planning Tools and/or Lync Server 2010 installed.</span></span> <span data-ttu-id="da80f-143">Est-ce OK ?</span><span class="sxs-lookup"><span data-stu-id="da80f-143">Is that OK?</span></span>

<span data-ttu-id="da80f-144">Non.</span><span class="sxs-lookup"><span data-stu-id="da80f-144">No.</span></span> <span data-ttu-id="da80f-145">Il existe des problèmes d’interopérabilité et vous devez désinstaller toutes les versions précédentes de ce produit.</span><span class="sxs-lookup"><span data-stu-id="da80f-145">There are interoperability issues, and you must uninstall all previous versions of this product.</span></span>

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="da80f-146">Les outils de stress et de performances configurent-ils la topologie du serveur d’informations d’appel CAA ?</span><span class="sxs-lookup"><span data-stu-id="da80f-146">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="da80f-147">Non.</span><span class="sxs-lookup"><span data-stu-id="da80f-147">No.</span></span> <span data-ttu-id="da80f-148">Les outils créent uniquement des utilisateurs, des contacts et des listes de distribution et simulent la charge utilisateur.</span><span class="sxs-lookup"><span data-stu-id="da80f-148">The tools only create users, contacts, and distribution lists, and simulate user load.</span></span>

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="da80f-149">Quel est le nombre maximal d’utilisateurs pris en charge par les outils ?</span><span class="sxs-lookup"><span data-stu-id="da80f-149">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="da80f-150">Nous avons créé un total de 80 000 utilisateurs et des tests exécutés totalisant 30 000 utilisateurs, à l’aide de ces outils.</span><span class="sxs-lookup"><span data-stu-id="da80f-150">We have created up to a total of 80,000 users and executed tests totaling 30,000 users, using these tools.</span></span> <span data-ttu-id="da80f-151">Nous vous suggérons un maximum de 120 000 utilisateurs, même si les limitations techniques permettent une plus grande valeur, en fonction du matériel du client et du serveur disponible.</span><span class="sxs-lookup"><span data-stu-id="da80f-151">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher value, depending on the client and server hardware available.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


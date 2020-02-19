---
title: 'Lync Server 2013 : configuration de l’intégrité dans Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee193ba28b10e8f209513d5bd6c8b58ae8c4fff9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a><span data-ttu-id="c9e7b-102">Configuration de l’intégrité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9e7b-102">Health configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9e7b-103">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="c9e7b-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="c9e7b-104">Entre différents sites Web, les Articles de la base de connaissances Microsoft et les outils du kit de ressources Lync Server, les administrateurs qui rencontrent des problèmes lors de l’exécution de Lync Server ne sont pas loin d’un moyen de résoudre ces problèmes.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-104">Between various websites, Microsoft Knowledge Base articles, and Lync Server Resource Kit tools, administrators who encounter problems when running Lync Server are never far from a way to solve those problems.</span></span>

<span data-ttu-id="c9e7b-105">Évidemment, il n’est pas possible de vous assurer que vous ne rencontrerez jamais de problèmes avec Lync Server 2013 car Lync Server peut être affecté par de nombreux éléments, tels que les pannes de réseau et les défaillances matérielles, que le produit lui-même ne peut pas contrôler.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-105">Obviously there is no way to guarantee that you will never encounter problems with Lync Server 2013 because Lync Server can be affected by many things—like network crashes and hardware failures—that the product itself cannot control.</span></span> <span data-ttu-id="c9e7b-106">En implémentant la surveillance de l’intégrité, les administrateurs peuvent identifier les problèmes potentiels avant de se transformer en problèmes réels.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-106">By implementing health monitoring, administrators can identify potential problems before they turn into actual problems.</span></span> <span data-ttu-id="c9e7b-107">Par exemple, les administrateurs peuvent utiliser la surveillance de Lync Server pour identifier des tendances et des Tendencies.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-107">For example, administrators can use Lync Server monitoring to identify trends and tendencies.</span></span> <span data-ttu-id="c9e7b-108">Par exemple, une augmentation constante du nombre de conférences audio/vidéo peut suggérer de devoir ajouter de la capacité avant que le système ne soit surchargé.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-108">For example, a steady increase in the number of audio/video conferences might suggest a need to add capacity before the system becomes overloaded.</span></span>

<span data-ttu-id="c9e7b-109">De la même manière, les administrateurs peuvent utiliser System Center Operations Manager pour effectuer des alertes en temps réel lorsque des événements spécifiés se produisent, et pour exécuter des transactions synthétiques qui testent le système de manière proactive.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-109">In a similar fashion, administrators can use System Center Operations Manager to do such things as issue real-time alerts when specified events occur, and to run synthetic transactions that proactively test the system.</span></span> <span data-ttu-id="c9e7b-110">Les transactions synthétiques sont utilisées dans Lync Server pour vérifier que les utilisateurs peuvent effectuer correctement des tâches courantes, telles que la connexion au système, l’échange de messages instantanés ou l’appel à un téléphone situé sur le réseau téléphonique commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="c9e7b-110">Synthetic transactions are used in Lync Server to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="c9e7b-111">Par exemple, l’exécution périodique de ces tests peut vous avertir en cas de problème avec les utilisateurs qui se connectent à Lync Server, et vous donner la possibilité de corriger le problème avant que votre équipe de support ne soit saturée d’appels provenant d’utilisateurs incapables d’établir une connexion.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-111">For example, periodically running these tests can alert you to potential problems with users logging on to Lync Server, and give you a chance to correct the problem before your support team is flooded with calls from users unable to make a connection.</span></span> <span data-ttu-id="c9e7b-112">À l’aide de System Center Operations Manager pour exécuter ces transactions synthétiques, les administrateurs peuvent surveiller régulièrement leur déploiement de Lync Server en continu pendant 24 heures sur 24, sans avoir à effectuer une grande partie des alertes pouvant être émis.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-112">By using System Center Operations Manager to run these synthetic transactions, administrators can routinely monitor their deployment of Lync Server continuously for 24 hours every day without having to do much of anything beyond responding to any alerts that might be issued.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c9e7b-113">Pour Lync Server 2013, le pack d’administration de System Center Operations Manager peut également détecter les problèmes « externes » susceptibles d’avoir un impact négatif sur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-113">For Lync Server 2013, the Management Pack for System Center Operations Manager is also able to detect "external" issues that can adversely affect Lync Server.</span></span> <span data-ttu-id="c9e7b-114">Par exemple, les administrateurs peuvent être avertis si les services Internet (IIS) se déconnectent, les ressources système sur un ordinateur Lync Server descendent en dessous d’une quantité spécifiée, ou un ordinateur Lync Server rencontre une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-114">For example, administrators can be notified if Internet Information Services (IIS) goes offline, system resources on a Lync Server computer fall below a specified amount, or a Lync Server computer experiences a hardware failure.</span></span>



</div>

<span data-ttu-id="c9e7b-115">La configuration de l’intégrité dans Lync Server 2013 est basée sur System Center Operations Manager et sur l’utilisation des packs d’administration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-115">Health configuration in Lync Server 2013 is built around System Center Operations Manager and the use of Lync Server Management Packs.</span></span> <span data-ttu-id="c9e7b-116">Ces packs d’administration incluent un certain nombre de nouvelles fonctionnalités et d’améliorations, notamment :</span><span class="sxs-lookup"><span data-stu-id="c9e7b-116">These Management Packs include a number of new features and enhancements, including:</span></span>

  - <span data-ttu-id="c9e7b-117">**Disponibilité des scénarios à partir de n’importe quel emplacement.**</span><span class="sxs-lookup"><span data-stu-id="c9e7b-117">**Scenario availability from any location.**</span></span> <span data-ttu-id="c9e7b-118">Le pack d’administration Lync Server 2010 a introduit le concept de surveillance de la disponibilité des scénarios des utilisateurs finaux avec les transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-118">The Lync Server 2010 Management Pack introduced the concept of monitoring end user scenario availability with synthetic transactions.</span></span> <span data-ttu-id="c9e7b-119">Dans Lync Server 2013, ces agents ont plus de transactions synthétiques et peuvent être exécutés à partir d’un grand nombre d’emplacements à l’intérieur de l’entreprise, à partir d’emplacements géographiques distants en dehors de l’entreprise, sur des appareils de succursale et sur Lync Server 2010 les déploiements pour ajouter la couverture aux déploiements de serveurs Edge hérités.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-119">In Lync Server 2013, these agents have more synthetic transactions and can be run from a variety of locations inside the enterprise, from remote geographic locations outside of the enterprise, against branch office appliances and against Lync Server 2010 deployments to add coverage to legacy Edge deployments.</span></span>

  - <span data-ttu-id="c9e7b-120">**Journaux de transactions synthétiques.**</span><span class="sxs-lookup"><span data-stu-id="c9e7b-120">**Synthetic transaction logs.**</span></span> <span data-ttu-id="c9e7b-121">Lorsqu’une transaction synthétique échoue, les administrateurs ont accès aux journaux HTML afin de déterminer ce qui a échoué.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-121">When a synthetic transaction fails, administrators have access to HTML logs to help determine what failed.</span></span> <span data-ttu-id="c9e7b-122">Cela inclut la compréhension de l’action qui a échoué, de la latence de chaque action, de la ligne de commande utilisée pour exécuter le test et de l’erreur rencontrée.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-122">This includes understanding which action failed, the latency of each action, the command-line used to run the test, and the error that was encountered.</span></span>

  - <span data-ttu-id="c9e7b-123">**Couverture accrue des appels.**</span><span class="sxs-lookup"><span data-stu-id="c9e7b-123">**Increased call reliability coverage.**</span></span> <span data-ttu-id="c9e7b-124">Le pack d’administration Lync Server 2010 a introduit les alertes de fiabilité des appels pour détecter les problèmes de connectivité graves affectant les appels audio des utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-124">The Lync Server 2010 Management Pack introduced call reliability alerting to detect severe connectivity issues that affect the audio calls of end users.</span></span> <span data-ttu-id="c9e7b-125">Les packs d’administration Lync Server 2013 ajoutent une couverture pour la messagerie instantanée d’égal à égal et d’autres fonctionnalités de conférence de base pour maximiser la couverture tout en réduisant le bruit.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-125">The Lync Server 2013 Management Packs add coverage for peer-to-peer instant messaging (IM) and other basic conferencing features to maximize coverage while reducing noise.</span></span>

  - <span data-ttu-id="c9e7b-126">**Surveillance des dépendances.**</span><span class="sxs-lookup"><span data-stu-id="c9e7b-126">**Dependency monitoring.**</span></span> <span data-ttu-id="c9e7b-127">Les scénarios Lync Server peuvent échouer en raison d’un certain nombre de facteurs externes, tels que les services Internet (IIS) hors connexion, les ressources de mémoire et de processeur limitées, ainsi que les problèmes de disque.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-127">Lync Server scenarios can fail due to a variety of external factors such as IIS being offline, limited CPU and memory resources, and disk issues.</span></span> <span data-ttu-id="c9e7b-128">Les nouveaux packs d’administration vérifient plusieurs dépendances critiques afin de s’assurer que les administrateurs connaissent leur impact.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-128">The new management packs check several critical dependencies to ensure administrators are aware of their impact.</span></span>

  - <span data-ttu-id="c9e7b-129">**Création de rapports améliorée.**</span><span class="sxs-lookup"><span data-stu-id="c9e7b-129">**Enhanced reporting.**</span></span> <span data-ttu-id="c9e7b-130">Ensemble de rapports permettant aux administrateurs d’estimer la disponibilité des scénarios, de planifier la capacité et de voir les composants qui rencontrent le plus de problèmes.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-130">A set of reports to help administrators estimate scenario availability, plan for capacity, and see which components are experiencing the most issues.</span></span>

<span data-ttu-id="c9e7b-131">Les packs d’administration incluent également un grand nombre de fonctionnalités pour vous aider à détecter et à diagnostiquer une visibilité en temps réel sur l’état de votre déploiement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-131">The Management Packs also include a variety of features to help detect and diagnose provide real-time visibility into the health your Lync Server deployment.</span></span> <span data-ttu-id="c9e7b-132">Ces fonctions sont répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-132">These features are listed in the following table.</span></span>

### <a name="management-pack-features"></a><span data-ttu-id="c9e7b-133">Fonctionnalités du pack d’administration</span><span class="sxs-lookup"><span data-stu-id="c9e7b-133">Management Pack Features</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9e7b-134">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="c9e7b-134">Feature</span></span></th>
<th><span data-ttu-id="c9e7b-135">Description</span><span class="sxs-lookup"><span data-stu-id="c9e7b-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9e7b-136">Transactions synthétiques</span><span class="sxs-lookup"><span data-stu-id="c9e7b-136">Synthetic Transactions</span></span></p></td>
<td><p><span data-ttu-id="c9e7b-137">Applets de commande Windows PowerShell pouvant être exécutées à partir de différents emplacements afin de s’assurer que les scénarios d’utilisateur final, tels que la connexion, la présence, la messagerie instantanée et la Conférence, sont immédiatement disponibles pour les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-137">Windows PowerShell cmdlets that can be run from various locations to ensure that end user scenarios such as sign-in, presence, IM, and conferencing are readily available to end users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9e7b-138">Alertes de fiabilité des appels</span><span class="sxs-lookup"><span data-stu-id="c9e7b-138">Call Reliability Alerts</span></span></p></td>
<td><p><span data-ttu-id="c9e7b-139">Requêtes de base de données pour les enregistrements des détails des appels (CDR).</span><span class="sxs-lookup"><span data-stu-id="c9e7b-139">Database queries for Call Detail Records (CDR).</span></span> <span data-ttu-id="c9e7b-140">Ces enregistrements sont écrits par les serveurs frontaux pour indiquer si les utilisateurs finaux ont pu se connecter à un appel ou la raison de l’arrêt d’un appel.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-140">These records are written by Front End Servers to reflect whether end users were able to connect to a call or why a call was terminated.</span></span> <span data-ttu-id="c9e7b-141">Ces requêtes génèrent des alertes qui indiquent quand un grand nombre d’utilisateurs finaux rencontrent des problèmes de connectivité pour les appels P2P ou les fonctionnalités de conférence de base.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-141">These queries result in alerts that indicate when a wide range of end users are experiencing connectivity issues for peer-to-peer calls or basic conferencing functionality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9e7b-142">Alertes de qualité des médias</span><span class="sxs-lookup"><span data-stu-id="c9e7b-142">Media Quality Alerts</span></span></p></td>
<td><p><span data-ttu-id="c9e7b-143">Requêtes de base de données qui examinent les rapports de qualité de l’expérience publiés par les clients à la fin de chaque appel.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-143">Database queries that look at Quality of Experience (QoE) reports published by clients at the end of each call.</span></span> <span data-ttu-id="c9e7b-144">Ces requêtes génèrent des alertes qui identifient les scénarios dans lesquels les utilisateurs sont susceptibles de rencontrer des problèmes de qualité des médias pendant les appels et les conférences.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-144">These queries result in alerts that pinpoint scenarios where users are likely to be experiencing poor media quality during calls and conferences.</span></span> <span data-ttu-id="c9e7b-145">Les données sont basées sur des mesures clés, telles que la latence et la perte de paquets, qui sont connues pour contribuer directement à la qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-145">The data is built upon key metrics such as packet latency and loss, metrics that are known to directly contribute to call quality.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9e7b-146">Intégrité des composants</span><span class="sxs-lookup"><span data-stu-id="c9e7b-146">Component Health</span></span></p></td>
<td><p><span data-ttu-id="c9e7b-147">Les composants serveur individuels déclenchent des alertes à l’aide de journaux d’événements et de compteurs de performance.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-147">Individual server components raise alerts by using event logs and performance counters.</span></span> <span data-ttu-id="c9e7b-148">Ces alertes indiquent des conditions d’échec qui peuvent sérieusement affecter un ou plusieurs scénarios d’utilisateur final.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-148">These alerts indicate failure conditions that can severely impact one or more end user scenarios.</span></span> <span data-ttu-id="c9e7b-149">Ces alertes peuvent également indiquer diverses autres conditions d’échec, notamment les services non exécutés, les taux d’échec élevés, la latence de messages élevée ou des problèmes de connectivité.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-149">These alerts can also indicate a variety of other failure conditions, including services not running, high failure rates, high message latency, or connectivity issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9e7b-150">Intégrité des dépendances</span><span class="sxs-lookup"><span data-stu-id="c9e7b-150">Dependency Health</span></span></p></td>
<td><p><span data-ttu-id="c9e7b-151">Des échecs peuvent se produire pour diverses raisons externes.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-151">Failures can occur for a variety of external reasons.</span></span> <span data-ttu-id="c9e7b-152">Les packs d’administration surveillent et collectent des données pour certaines dépendances externes critiques susceptibles d’indiquer des problèmes sérieux, notamment la disponibilité des services Internet, l’utilisation du processeur et de la mémoire des serveurs et des processus, ainsi que les mesures de disque.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-152">The management packs now monitor and collect data for some of the critical external dependencies that might indicate severe issues, including IIS availability, CPU and memory usage of servers and processes, and disk metrics.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c9e7b-153">Les alertes émises par le système ont été classées en trois catégories générales :</span><span class="sxs-lookup"><span data-stu-id="c9e7b-153">The alerts issued by the system have been classified into three general categories:</span></span>

  - <span data-ttu-id="c9e7b-154">**Alertes à priorité élevée.**</span><span class="sxs-lookup"><span data-stu-id="c9e7b-154">**High-priority Alerts.**</span></span> <span data-ttu-id="c9e7b-155">Ces alertes indiquent les conditions qui provoquent des pannes de service pour des groupes d’utilisateurs importants.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-155">These alerts indicate conditions that will cause service outages for large groups of users.</span></span> <span data-ttu-id="c9e7b-156">Par exemple, une défaillance de composant sur un seul ordinateur n’est pas une alerte de haute priorité, car Lync Server 2013 possède des fonctionnalités de haute disponibilité intégrées.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-156">For example, a component failure on a single machine is not a high-priority alert because Lync Server 2013 has built-in high availability features.</span></span> <span data-ttu-id="c9e7b-157">Au lieu de cela, les alertes de haute priorité représentent des problèmes assez graves» pour réveiller les administrateurs la nuit.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-157">Instead, high-priority alerts represent problems serious enough “to wake up administrators at night.”</span></span> <span data-ttu-id="c9e7b-158">Les pannes détectées par les transactions synthétiques et les services hors ligne (par exemple, conférence audio/vidéo) sont considérées comme des alertes de haute priorité.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-158">Outages detected by synthetic transactions and offline services (for example, audio/video conferencing) qualify as high-priority alerts.</span></span>

  - <span data-ttu-id="c9e7b-159">**Alertes de priorité moyenne.**.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-159">**Medium-priority alerts.**.</span></span> <span data-ttu-id="c9e7b-160">Ces alertes indiquent les conditions qui affectent un sous-ensemble d’utilisateurs ou indiquent une dégradation de la qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-160">These alerts indicate conditions that affect a subset of users or indicate call quality degradation.</span></span> <span data-ttu-id="c9e7b-161">Cela inclut des problèmes comme les défaillances de composants, la latence dans l’établissement d’appel ou la qualité audio dégradée dans l’appel.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-161">That includes problems such as component failures, latency in call establishment, or degraded audio quality in call.</span></span> <span data-ttu-id="c9e7b-162">Les alertes de cette catégorie sont avec état et indiquent l’état actuel du problème.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-162">Alerts in this category are stateful and indicate the current status of the issue.</span></span> <span data-ttu-id="c9e7b-163">Par exemple, supposons que les heures d’établissement de votre appel dépassent le seuil d’alerte.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-163">For example, suppose your call establishment times exceed the alert threshold.</span></span> <span data-ttu-id="c9e7b-164">Si les heures d’établissement d’appel reviennent à la normale, ces alertes seront résolues automatiquement dans System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-164">If call establishment times return to normal, these alerts will be auto-resolved in System Center Operations Manager.</span></span> <span data-ttu-id="c9e7b-165">L’attente de ces alertes est qu’un administrateur les consultera le même jour ouvré.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-165">The expectation for these alerts is that an administrator will look at them on the same business day.</span></span>

  - <span data-ttu-id="c9e7b-166">**Autres alertes.**</span><span class="sxs-lookup"><span data-stu-id="c9e7b-166">**Other alerts.**</span></span> <span data-ttu-id="c9e7b-167">Il s’agit d’alertes provenant de composants susceptibles d’affecter un utilisateur spécifique ou un sous-ensemble d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-167">These are alerts from components that might affect a specific user or subset of users.</span></span> <span data-ttu-id="c9e7b-168">Par exemple, le service de carnet d’adresses n’a peut-être pas pu analyser l’entrée Active Directory d’un utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-168">For example, perhaps the Address Book service could not parse the Active Directory entry of a given user.</span></span> <span data-ttu-id="c9e7b-169">L’attente de ces alertes est que les administrateurs y accéderont lorsqu’ils auront le temps de se rendre disponible.</span><span class="sxs-lookup"><span data-stu-id="c9e7b-169">The expectation for these alerts is that administrators will get to them when they have time available.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c9e7b-170">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="c9e7b-170">In This Section</span></span>

  - [<span data-ttu-id="c9e7b-171">Configuration de Lync Server 2013 pour qu’il fonctionne avec System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="c9e7b-171">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [<span data-ttu-id="c9e7b-172">Utilisation d’une journalisation enrichie pour les transactions synthétiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9e7b-172">Using rich logging for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [<span data-ttu-id="c9e7b-173">Utilisation de Microsoft SQL Server 2008 R2 comme base de données System Center Operations Manager pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9e7b-173">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


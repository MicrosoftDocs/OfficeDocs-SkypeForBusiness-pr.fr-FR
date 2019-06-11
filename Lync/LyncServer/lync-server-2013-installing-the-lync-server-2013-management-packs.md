---
title: 'Lync Server 2013: installation des packs d’administration de Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fea443225744bfd0d0e2dfa90a317ffa4cc890ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a><span data-ttu-id="96943-102">Installation des packs d’administration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96943-102">Installing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96943-103">_**Dernière modification de la rubrique:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="96943-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="96943-104">Le gestionnaire des opérations de System Center a la possibilité de surveiller uniquement une petite partie du système d’exploitation Windows.</span><span class="sxs-lookup"><span data-stu-id="96943-104">By itself, System Center Operations Manager has the ability to monitor only a small portion of the Windows operating system.</span></span> <span data-ttu-id="96943-105">Toutefois, vous pouvez développer les fonctionnalités de System Center Operations Manager en installant des packs d’administration, des logiciels qui déterminent les éléments que System Center Operations Manager peut surveiller, y compris la façon dont ces éléments doivent être surveillés et la façon dont les alertes doivent être déclenché et signalé.</span><span class="sxs-lookup"><span data-stu-id="96943-105">However, you can extend the capabilities of System Center Operations Manager by installing management packs, software that dictates which items System Center Operations Manager can monitor, including how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="96943-106">Microsoft Lync Server 2013 inclut deux packs d’administration System Center Operations Manager qui fournissent les fonctionnalités suivantes:</span><span class="sxs-lookup"><span data-stu-id="96943-106">Microsoft Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="96943-107">Le Pack de gestion des utilisateurs et des composants (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) effectue le suivi des problèmes du serveur Lync enregistrés dans les journaux d’événements, inscrits par des compteurs de performance ou enregistrés dans les enregistrements des détails des appels ou sur la qualité de l’utilisation (QoE). bases de données.</span><span class="sxs-lookup"><span data-stu-id="96943-107">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="96943-108">Pour les problèmes critiques, System Center Operations Manager peut être configuré pour notifier immédiatement les administrateurs par courrier électronique, message instantané ou messagerie de courte durée de réception de messages.</span><span class="sxs-lookup"><span data-stu-id="96943-108">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="96943-109">SMS est la technologie utilisée pour envoyer des messages texte d’un appareil mobile à un autre.</span><span class="sxs-lookup"><span data-stu-id="96943-109">SMS is the technology used to send text messages from one mobile device to another.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="96943-110">Pour plus d’informations sur la configuration de la notification Operations Manager, consultez la rubrique Configuration de <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>la notification dans la bibliothèque TechNet à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="96943-110">For more information on configuring Operations Manager notification, see Configuring Notification in the TechNet Library at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="96943-111">Le pack d’analyse actif (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) vérifie de manière proactive les principaux composants du serveur Lync tels que la connexion au système, l’échange de messages instantanés ou l’appel d’appels vers un téléphone situé sur le téléphone public commuté réseau commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="96943-111">The Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="96943-112">Ces tests sont effectués à l’aide des cmdlets de transaction synthétique de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96943-112">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="96943-113">Par exemple, l’applet de **contrôle test-CsIM** est utilisée pour simuler une conversation par messagerie instantanée entre deux utilisateurs de test.</span><span class="sxs-lookup"><span data-stu-id="96943-113">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="96943-114">Si cette conversation de messagerie simulée échoue, une alerte est générée.</span><span class="sxs-lookup"><span data-stu-id="96943-114">If this simulated messaging conversation fails an alert will be generated.</span></span>

<span data-ttu-id="96943-115">Les deux packages d’administration inclus dans Lync Server 2013 incluent un grand nombre d’améliorations sur les packs de gestion utilisés avec Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="96943-115">The two management packs included with Lync Server 2013 include a large number of enhancements over the management packs used with Microsoft Lync Server 2010.</span></span> <span data-ttu-id="96943-116">Par exemple, le Pack de gestion des composants de Lync Server 2013 n’est pas limité à la surveillance de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96943-116">For example, the Lync Server 2013 Component Management Pack is not limited to monitoring Lync Server itself.</span></span> <span data-ttu-id="96943-117">Outre le suivi des journaux d’événements et des compteurs de performance pour Lync Server, le Pack de gestion des composants peut également suivre les performances des éléments cruciaux et en émettre des alertes, tels que:</span><span class="sxs-lookup"><span data-stu-id="96943-117">In addition to monitoring event logs and performance counters for Lync Server, the Component Management pack can also track the performance of, and issue alerts for, crucial items such as:</span></span>

  - <span data-ttu-id="96943-118">**Des alertes d’Internet Information Services (IIS)**   seront émises si Internet Information Services se déconnecte.</span><span class="sxs-lookup"><span data-stu-id="96943-118">**Internet Information Services (IIS)**   Alerts will be issued if Internet Information Services goes offline.</span></span> <span data-ttu-id="96943-119">C’est important, car les services Web de Lync Server dépendent d’IIS.</span><span class="sxs-lookup"><span data-stu-id="96943-119">This is important, because the Lync Server web services rely on IIS.</span></span>

  - <span data-ttu-id="96943-120">\*\*\*\*   Les alertes d’utilisation du processus sont émises si les ressources système (telles que la mémoire disponible) commencent à s’exécuter faiblement.</span><span class="sxs-lookup"><span data-stu-id="96943-120">**Process usage**   Alerts will be issued if system resources (such as available memory) begin to run low.</span></span> <span data-ttu-id="96943-121">Ces alertes sont émises même si Lync Server n’est pas responsable de l’utilisation importante du système.</span><span class="sxs-lookup"><span data-stu-id="96943-121">These alerts will be issued even if Lync Server is not responsible for the high system usage.</span></span>

  - <span data-ttu-id="96943-122">\*\*\*\*   Les alertes d’événements d’échec d’ordinateur sont émises en cas de problème matériel ou logiciel qui menace la viabilité d’un serveur.</span><span class="sxs-lookup"><span data-stu-id="96943-122">**Computer failure events**   Alerts will be issued in case of a hardware or software issue that threatens the viability of a server.</span></span> <span data-ttu-id="96943-123">Par exemple, les administrateurs du serveur Lync seront avertis si un serveur semble être menacé par une défaillance de disque dur.</span><span class="sxs-lookup"><span data-stu-id="96943-123">For example, Lync Server administrators will be notified if a server appears to be in danger of experiencing a hard disk failure.</span></span>

<span data-ttu-id="96943-124">Les nouveaux modules de gestion permettent également d’améliorer la création de rapports.</span><span class="sxs-lookup"><span data-stu-id="96943-124">The new management packs also feature enhanced reporting.</span></span> <span data-ttu-id="96943-125">Les nouveaux rapports pour Lync Server 2013 incluent:</span><span class="sxs-lookup"><span data-stu-id="96943-125">New reports for Lync Server 2013 include:</span></span>

  - <span data-ttu-id="96943-126">**Rapport de disponibilité du scénario de bout en bout**   ce rapport décrit en détail la disponibilité des services principaux de Lync Server tels que l’inscription ou la présence.</span><span class="sxs-lookup"><span data-stu-id="96943-126">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="96943-127">**Rapport de capacité**   utilisant des informations de compteurs de performance, ce rapport affiche des tendances pour les composants système tels que la disponibilité de la mémoire et l’utilisation du processeur.</span><span class="sxs-lookup"><span data-stu-id="96943-127">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="96943-128">**Rapport de composant**   ce rapport répertorie les principaux générateurs d’alertes regroupés par composant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96943-128">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="96943-129">Outre ces rapports prédéfinis, les packs de gestion pour Lync Server 2013 signalent automatiquement les alertes pour la fiabilité des appels (métriques mesurées par enregistrement des détails des appels) et les États QoE (métriques mesurées par qualité d’expérimentation).</span><span class="sxs-lookup"><span data-stu-id="96943-129">In addition to these predesigned reports, the management packs for Lync Server 2013 automatically report alerts for both Call Reliability (metrics measured by Call Detail Recording) and QoE states (metrics measured by Quality of Experience).</span></span> <span data-ttu-id="96943-130">Si vous avez activé l’enregistrement des détails des appels, vous pouvez passer en revue les alertes de fiabilité des appels en effectuant les étapes suivantes à partir de la console System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="96943-130">If you have enabled Call Detail Recording, you can review Call Reliability alerts by completing the following procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="96943-131">Développez **analyse**, développez **État de Microsoft Lync Server 2013**, développez **fiabilité des appels et qualité multimédia**, puis cliquez sur **fiabilité des appels**.</span><span class="sxs-lookup"><span data-stu-id="96943-131">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then click **Call Reliability**.</span></span>

<span data-ttu-id="96943-132">Pour afficher des alertes de qualité de l’utilisation, procédez comme suit dans la console System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="96943-132">To view Quality of Experience alerts, complete this procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="96943-133">Développez **analyse**, développez **État de Microsoft Lync Server 2013**, développez **fiabilité des appels et qualité multimédia**, puis développez **qualité multimédia**.</span><span class="sxs-lookup"><span data-stu-id="96943-133">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then expand **Media Quality**.</span></span>

<span data-ttu-id="96943-134">Les packs de gestion pour Lync Server 2013 utilisent désormais une découverte au niveau de l’ordinateur au lieu du mécanisme de découverte centralisé utilisé dans Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="96943-134">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism used in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="96943-135">En d’autres termes, chacun de ses agents s’en charge et signale son existence au serveur de gestion central.</span><span class="sxs-lookup"><span data-stu-id="96943-135">This means that each System Center agent essentially discovers itself and reports its existence to the Central Management Server.</span></span> <span data-ttu-id="96943-136">L’utilisation de la découverte au niveau de l’ordinateur simplifie l’administration de votre infrastructure de centre système et permet également d’utiliser différentes versions des packs de gestion Lync Server (par exemple, les packs d’administration de Lync Server 2010 et les modules de gestion pour Lync Server 2013) sur coexister.</span><span class="sxs-lookup"><span data-stu-id="96943-136">Using machine-level discovery simplifies administration of your System Center infrastructure and also allows different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


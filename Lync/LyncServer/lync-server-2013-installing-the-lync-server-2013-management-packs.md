---
title: 'Lync Server 2013 : installation des packs d’administration Lync Server 2013'
description: 'Lync Server 2013 : installation des packs d’administration Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbb50146474211c12dbd95801ed2b20f6bbfd8c9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573830"
---
# <a name="installing-the-lync-server-2013-management-packs"></a><span data-ttu-id="c4469-103">Installation des packs d’administration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4469-103">Installing the Lync Server 2013 management packs</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4469-104">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="c4469-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="c4469-105">Par lui-même, System Center Operations Manager a la possibilité de surveiller uniquement une petite partie du système d’exploitation Windows.</span><span class="sxs-lookup"><span data-stu-id="c4469-105">By itself, System Center Operations Manager has the ability to monitor only a small portion of the Windows operating system.</span></span> <span data-ttu-id="c4469-106">Toutefois, vous pouvez étendre les fonctionnalités de System Center Operations Manager en installant des packs d’administration, des logiciels qui déterminent les éléments que System Center Operations Manager peut surveiller, y compris comment ces éléments doivent être surveillés et comment les alertes doivent être déclenchées et signalées.</span><span class="sxs-lookup"><span data-stu-id="c4469-106">However, you can extend the capabilities of System Center Operations Manager by installing management packs, software that dictates which items System Center Operations Manager can monitor, including how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="c4469-107">Microsoft Lync Server 2013 comprend deux packs d’administration System Center Operations Manager qui offrent les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="c4469-107">Microsoft Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="c4469-108">Le pack d’administration des composants et des utilisateurs (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) effectue le suivi des problèmes Lync Server enregistrés dans les journaux des événements, enregistrés par des compteurs de performance ou consignés dans les bases de données des enregistrements des détails des appels ou de la qualité de l’expérience (QoE).</span><span class="sxs-lookup"><span data-stu-id="c4469-108">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="c4469-109">Pour les problèmes critiques, System Center Operations Manager peut être configuré pour informer immédiatement les administrateurs via la messagerie électronique, la messagerie instantanée ou la messagerie SMS (Short Message Service).</span><span class="sxs-lookup"><span data-stu-id="c4469-109">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="c4469-110">La technologie des SMS est utilisée pour envoyer des messages texte d’un appareil mobile à un autre.</span><span class="sxs-lookup"><span data-stu-id="c4469-110">SMS is the technology used to send text messages from one mobile device to another.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c4469-111">Pour plus d’informations sur la configuration de la notification Operations Manager, voir Configuration de la notification dans la bibliothèque TechNet à l’adresse <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?linkid=268785</A> .</span><span class="sxs-lookup"><span data-stu-id="c4469-111">For more information on configuring Operations Manager notification, see Configuring Notification in the TechNet Library at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?linkid=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="c4469-112">Le Pack de surveillance active (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) vérifie de manière proactive les principaux composants de Lync Server, tels que la connexion au système, l’échange de messages instantanés ou l’appel à un téléphone situé sur le réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="c4469-112">The Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="c4469-113">Ces tests sont effectués à l’aide des applets de commande de transaction synthétique Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c4469-113">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="c4469-114">Par exemple, l’applet de commande **Test-CsIM** est utilisée pour simuler une conversation de messagerie instantanée entre deux utilisateurs de test.</span><span class="sxs-lookup"><span data-stu-id="c4469-114">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="c4469-115">Si la conversation de messagerie simulée échoue, une alerte est générée.</span><span class="sxs-lookup"><span data-stu-id="c4469-115">If this simulated messaging conversation fails an alert will be generated.</span></span>

<span data-ttu-id="c4469-116">Les deux packs d’administration fournis avec Lync Server 2013 incluent un grand nombre d’améliorations par rapport aux packs d’administration utilisés avec Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c4469-116">The two management packs included with Lync Server 2013 include a large number of enhancements over the management packs used with Microsoft Lync Server 2010.</span></span> <span data-ttu-id="c4469-117">Par exemple, le pack d’administration des composants Lync Server 2013 n’est pas limité à la surveillance de Lync Server lui-même.</span><span class="sxs-lookup"><span data-stu-id="c4469-117">For example, the Lync Server 2013 Component Management Pack is not limited to monitoring Lync Server itself.</span></span> <span data-ttu-id="c4469-118">Outre la surveillance des journaux d’événements et des compteurs de performance pour Lync Server, le pack d’administration des composants peut également suivre les performances des alertes et émettre des alertes pour les éléments cruciaux tels que :</span><span class="sxs-lookup"><span data-stu-id="c4469-118">In addition to monitoring event logs and performance counters for Lync Server, the Component Management pack can also track the performance of, and issue alerts for, crucial items such as:</span></span>

  - <span data-ttu-id="c4469-119">**Internet Information Services (IIS)**     Des alertes seront émises si Internet Information Services se déconnecte.</span><span class="sxs-lookup"><span data-stu-id="c4469-119">**Internet Information Services (IIS)**   Alerts will be issued if Internet Information Services goes offline.</span></span> <span data-ttu-id="c4469-120">Ceci est important, car les services Web Lync Server s’appuient sur IIS.</span><span class="sxs-lookup"><span data-stu-id="c4469-120">This is important, because the Lync Server web services rely on IIS.</span></span>

  - <span data-ttu-id="c4469-121">**Utilisation**     des processus Des alertes seront émises si les ressources système (telles que la mémoire disponible) commencent à manquer.</span><span class="sxs-lookup"><span data-stu-id="c4469-121">**Process usage**   Alerts will be issued if system resources (such as available memory) begin to run low.</span></span> <span data-ttu-id="c4469-122">Ces alertes seront émises même si Lync Server n’est pas responsable de l’utilisation élevée du système.</span><span class="sxs-lookup"><span data-stu-id="c4469-122">These alerts will be issued even if Lync Server is not responsible for the high system usage.</span></span>

  - <span data-ttu-id="c4469-123">Événements de défaillance d' **ordinateur**     Des alertes seront émises en cas de problème matériel ou logiciel susceptible de menacer la viabilité d’un serveur.</span><span class="sxs-lookup"><span data-stu-id="c4469-123">**Computer failure events**   Alerts will be issued in case of a hardware or software issue that threatens the viability of a server.</span></span> <span data-ttu-id="c4469-124">Par exemple, les administrateurs Lync Server seront avertis si un serveur semble être menacé par une défaillance du disque dur.</span><span class="sxs-lookup"><span data-stu-id="c4469-124">For example, Lync Server administrators will be notified if a server appears to be in danger of experiencing a hard disk failure.</span></span>

<span data-ttu-id="c4469-125">Les nouveaux packs d’administration proposent également une création de rapports améliorée.</span><span class="sxs-lookup"><span data-stu-id="c4469-125">The new management packs also feature enhanced reporting.</span></span> <span data-ttu-id="c4469-126">Les nouveaux rapports pour Lync Server 2013 sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="c4469-126">New reports for Lync Server 2013 include:</span></span>

  - <span data-ttu-id="c4469-127">Rapport de disponibilité des **scénarios de bout en bout**     Ce rapport décrit en détail la disponibilité et la durée de fonctionnement des services Lync Server clés tels que l’inscription ou la présence.</span><span class="sxs-lookup"><span data-stu-id="c4469-127">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="c4469-128">**Rapport**     de capacité À l’aide des informations des compteurs de performance, ce rapport affiche des tendances pour les composants système, tels que la disponibilité de la mémoire et l’utilisation du processeur.</span><span class="sxs-lookup"><span data-stu-id="c4469-128">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="c4469-129">**Rapport**     de composant Ce rapport répertorie les principaux générateurs d’alertes regroupés par composant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c4469-129">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="c4469-130">En plus de ces rapports prédéfinis, les packs d’administration de Lync Server 2013 signalent automatiquement les alertes pour la fiabilité des appels (mesures mesurées par l’enregistrement des détails des appels) et les États de QoE (mesures mesurées par qualité de l’expérience).</span><span class="sxs-lookup"><span data-stu-id="c4469-130">In addition to these predesigned reports, the management packs for Lync Server 2013 automatically report alerts for both Call Reliability (metrics measured by Call Detail Recording) and QoE states (metrics measured by Quality of Experience).</span></span> <span data-ttu-id="c4469-131">Si vous avez activé l’enregistrement des détails des appels, vous pouvez passer en revue les alertes de fiabilité des appels en effectuant la procédure suivante à partir de la console System Center Operations Manager :</span><span class="sxs-lookup"><span data-stu-id="c4469-131">If you have enabled Call Detail Recording, you can review Call Reliability alerts by completing the following procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="c4469-132">Développez **Surveillance**, **Intégrité de Microsoft Lync Server 2013** et **Fiabilité des appels et qualité des médias**, puis cliquez sur **Fiabilité des appels**.</span><span class="sxs-lookup"><span data-stu-id="c4469-132">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then click **Call Reliability**.</span></span>

<span data-ttu-id="c4469-133">Pour afficher les alertes de qualité de l’expérience, effectuez cette procédure à partir de la console System Center Operations Manager :</span><span class="sxs-lookup"><span data-stu-id="c4469-133">To view Quality of Experience alerts, complete this procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="c4469-134">Développez **Surveillance**, **Intégrité de Microsoft Lync Server 2013** et **Fiabilité des appels et qualité des médias**, puis cliquez sur **Qualité des médias**.</span><span class="sxs-lookup"><span data-stu-id="c4469-134">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then expand **Media Quality**.</span></span>

<span data-ttu-id="c4469-135">Les packs d’administration de Lync Server 2013 utilisent désormais la découverte au niveau de l’ordinateur au lieu du mécanisme de découverte central utilisé dans Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c4469-135">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism used in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="c4469-136">Cela signifie que chaque agent System Center se trouve essentiellement et rend compte de son existence au serveur de gestion centralisée.</span><span class="sxs-lookup"><span data-stu-id="c4469-136">This means that each System Center agent essentially discovers itself and reports its existence to the Central Management Server.</span></span> <span data-ttu-id="c4469-137">L’utilisation de la découverte au niveau de l’ordinateur simplifie l’administration de votre infrastructure System Center et permet également différentes versions des packs d’administration Lync Server (par exemple, les packs d’administration pour Lync Server 2010 et les packs d’administration pour Lync Server 2013) de coexister.</span><span class="sxs-lookup"><span data-stu-id="c4469-137">Using machine-level discovery simplifies administration of your System Center infrastructure and also allows different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


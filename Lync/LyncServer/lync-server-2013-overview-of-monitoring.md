---
title: 'Lync Server 2013 : vue d’ensemble de la surveillance'
description: 'Lync Server 2013 : vue d’ensemble de la surveillance.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64f27d6aff71442c6193c220154af231481399ac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577320"
---
# <a name="overview-of-monitoring-in-lync-server-2013"></a><span data-ttu-id="dd065-103">Vue d’ensemble de la surveillance dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd065-103">Overview of monitoring in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd065-104">_**Dernière modification de la rubrique :** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="dd065-104">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="dd065-105">Dans Microsoft Lync Server 2013, la surveillance est utilisée pour collecter des informations sur l’utilisation et des données de qualité de l’expérience (QoE) sur les sessions de communication auxquelles vos utilisateurs sont impliqués.</span><span class="sxs-lookup"><span data-stu-id="dd065-105">In Microsoft Lync Server 2013, monitoring is used to collect usage information and Quality of Experience (QoE) data about the communication sessions that your users are involved in.</span></span> <span data-ttu-id="dd065-106">Une session est un terme générique qui couvre la connexion d’un utilisateur à un :</span><span class="sxs-lookup"><span data-stu-id="dd065-106">A session is a generic term that covers a user’s connection to a:</span></span>

  - <span data-ttu-id="dd065-107">Conférence</span><span class="sxs-lookup"><span data-stu-id="dd065-107">Conference</span></span>

  - <span data-ttu-id="dd065-108">Modalité de conférence (comme l’audio/vidéo ou le partage d’application)</span><span class="sxs-lookup"><span data-stu-id="dd065-108">Conferencing modality (such as Audio/Video or Application Sharing)</span></span>

  - <span data-ttu-id="dd065-109">Un autre utilisateur via une conversation d’égal à égal telle qu’une messagerie instantanée ou un appel audio</span><span class="sxs-lookup"><span data-stu-id="dd065-109">Another user via a peer-to-peer conversation such as instant messaging or an audio call</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd065-110">Lync Server 2013 effectue le suivi des informations relatives à chaque session : qui a appelé personne ; Quels points de terminaison ont été utilisés dans la session ; la durée de la dernière session ; quelle était la qualité perçue de la session ; et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="dd065-110">Lync Server 2013 keeps track of information about each session: who called who; which endpoints were used in the session; how long did the session last; what was the perceived quality of the session; and so on.</span></span> <span data-ttu-id="dd065-111">Toutefois, Lync Server n’enregistre pas et ne stocke pas l’appel réel lui-même.</span><span class="sxs-lookup"><span data-stu-id="dd065-111">However, Lync Server does not record and store the actual call itself.</span></span> <span data-ttu-id="dd065-112">Cela inclut également les sessions de messagerie instantanée : même si Lync Server enregistre des informations sur les sessions de messagerie instantanée, il ne conserve pas d’enregistrement de chaque message instantané envoyé pendant la session.</span><span class="sxs-lookup"><span data-stu-id="dd065-112">That includes instant messaging sessions as well: although Lync Server records information about instant messaging sessions, it does not maintain a record of each instant message that was sent during the session.</span></span>



</div>

<span data-ttu-id="dd065-113">Les informations détaillées sur l’appel collectées par Lync Server peuvent être utilisées pour n’importe quel nombre d’utilisations, notamment :</span><span class="sxs-lookup"><span data-stu-id="dd065-113">The call detail information collected by Lync Server can be employed for any number of uses, including:</span></span>

  - <span data-ttu-id="dd065-114">**Retour sur investissement (roi)**.</span><span class="sxs-lookup"><span data-stu-id="dd065-114">**Return on Investment (ROI)**.</span></span> <span data-ttu-id="dd065-115">Les administrateurs peuvent comparer les données d’utilisation collectées par le serveur de surveillance aux données similaires collectées pour leur système de téléphonie précédent afin d’afficher des économies de coûts et de justifier le déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dd065-115">Administrators can compare the usage data collected by Monitoring Server to similar data collected for their previous telephony system in order to show cost savings and help justify the deployment of Lync Server.</span></span>

  - <span data-ttu-id="dd065-116">**Gestion**de l’inventaire des appareils.</span><span class="sxs-lookup"><span data-stu-id="dd065-116">**Device Inventory Management**.</span></span> <span data-ttu-id="dd065-117">Les informations de gestion des biens aident les administrateurs à identifier les anciens appareils encore en cours d’utilisation qui doivent être remplacés, ainsi qu’à identifier les appareils onéreux qui ne semblent pas être utilisés du tout.</span><span class="sxs-lookup"><span data-stu-id="dd065-117">Asset management information helps administrators identify old devices still in use that need to be replaced, as well as identify expensive devices that do not appear to be getting used at all.</span></span>

  - <span data-ttu-id="dd065-118">Support technique.</span><span class="sxs-lookup"><span data-stu-id="dd065-118">Help Desk.</span></span> <span data-ttu-id="dd065-119">Les données de dépannage permettent aux ingénieurs de la prise en charge de déterminer pourquoi l’appel d’un utilisateur a échoué, et de le faire sans avoir à collecter les journaux côté serveur ou côté client.</span><span class="sxs-lookup"><span data-stu-id="dd065-119">Troubleshooting data enables support engineers to determine why a user’s call failed, and to do so without having to collect server or client side logs.</span></span> <span data-ttu-id="dd065-120">Ces informations sont facilement accessibles et compréhensibles par le personnel du support technique qui ne possède pas de connaissances techniques approfondies de Microsoft Lync 2013 et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dd065-120">This information can be readily accessed and understood by support personnel who do not have a deep technical knowledge of Microsoft Lync 2013 and Lync Server 2013.</span></span>

  - <span data-ttu-id="dd065-121">**Dépannage du système**.</span><span class="sxs-lookup"><span data-stu-id="dd065-121">**System Troubleshooting**.</span></span> <span data-ttu-id="dd065-122">Permet aux administrateurs de détecter les problèmes majeurs susceptibles d’empêcher les utilisateurs finaux d’effectuer des tâches de base comme rejoindre une conférence, établir un appel ou envoyer un message instantané.</span><span class="sxs-lookup"><span data-stu-id="dd065-122">Enables administrators to detect major issues that might prevent end users from performing basic tasks like joining a conference, establishing a call, or sending an instant message.</span></span>

<span data-ttu-id="dd065-123">Outre ces informations d’appel de base, le serveur de surveillance fournit également un mécanisme qui permet aux points de terminaison SIP (par exemple, Lync 2013) de fournir des informations de résolution des problèmes auxquelles le serveur n’a pas accès autrement :</span><span class="sxs-lookup"><span data-stu-id="dd065-123">In addition to this basic call information, the Monitoring Server also provides a mechanism that allows SIP endpoints (such as Lync 2013) to provide troubleshooting information that the server would not otherwise have access to:</span></span>

  - <span data-ttu-id="dd065-124">**Métriques multimédias ayant un impact sur la qualité**.</span><span class="sxs-lookup"><span data-stu-id="dd065-124">**Media Metrics that Impact Quality**.</span></span> <span data-ttu-id="dd065-125">Ces mesures traitent de la transmission effective de l’appel lui-même ; autrement dit, ils fournissent une sorte de journal de voyage lorsque l’appel passe sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="dd065-125">These metrics deal with the actual transmission of the call itself; that is, they provide a sort of travel log as the call journeys across the network.</span></span> <span data-ttu-id="dd065-126">Ces mesures (qui incluent notamment des pertes de paquets, des instabilités et des durées d’aller-retour) fournissent des informations sur ce qui est arrivé à l’appel entre le moment où il a quitté votre point de terminaison et le moment où il est arrivé au point de terminaison de l’autre personne.</span><span class="sxs-lookup"><span data-stu-id="dd065-126">These metrics (which include such things as packet loss, jitter, and round trip times) provide information on what happened to the call from the time it left your endpoint to the time it arrived at the other person's endpoint.</span></span>

  - <span data-ttu-id="dd065-127">**Problèmes signalés à l’utilisateur final**.</span><span class="sxs-lookup"><span data-stu-id="dd065-127">**Issues Reported to the End User**.</span></span> <span data-ttu-id="dd065-128">Ces mesures incluent les notifications de qualité médiocre que Lync 2013 présente aux utilisateurs finals lorsqu’ils sont trop éloignés d’un microphone, parlant trop peu, ont une mauvaise connexion réseau ou présentent une qualité médiocre, car un autre programme sur l’ordinateur utilise les ressources disponibles.</span><span class="sxs-lookup"><span data-stu-id="dd065-128">These metrics include poor quality notifications that Lync 2013 presents to end users in cases where they are too far from a microphone, speaking too softly, have a poor network connection, or are experiencing poor quality because another program on the computer is consuming the available resources.</span></span>

  - <span data-ttu-id="dd065-129">**Informations sur l’environnement**.</span><span class="sxs-lookup"><span data-stu-id="dd065-129">**Environment Information**.</span></span> <span data-ttu-id="dd065-130">Ces critères de qualité des appels de mesure, tels que le type de microphone et les haut-parleurs utilisés, le fait que l’utilisateur est connecté via une connexion VPN et que l’utilisateur se trouve sur une connexion sans fil.</span><span class="sxs-lookup"><span data-stu-id="dd065-130">These metrics detail call quality factors such as the type of microphone and speakers being used, whether the user is connected through a VPN connection, and whether the user is on a wireless connection.</span></span>

<span data-ttu-id="dd065-131">À la fin de chaque appel, les points de terminaison compatibles avec SIP transmettent automatiquement ces informations au serveur frontal qui a facilité l’appel.</span><span class="sxs-lookup"><span data-stu-id="dd065-131">At the end of each call, SIP-compliant endpoints automatically transmit this information to the Front End server that facilitated the call.</span></span> <span data-ttu-id="dd065-132">Vous n’avez rien à faire pour obtenir des points de terminaison afin de transmettre ces informations ; ce comportement est intégré au protocole SIP.</span><span class="sxs-lookup"><span data-stu-id="dd065-132">You don't have to do anything to get endpoints to transmit that information; that behavior is built into the SIP protocol.</span></span> <span data-ttu-id="dd065-133">Toutefois, si vous souhaitez collecter et stocker ces informations, vous devez installer et activer la surveillance.</span><span class="sxs-lookup"><span data-stu-id="dd065-133">However, if you want to collect and store that information, then you need to install and enable monitoring.</span></span> <span data-ttu-id="dd065-134">Si vous installez et activez la surveillance, les informations d’appel sont rassemblées par des agents s’exécutant sur le serveur frontal et relayées vers une paire de bases de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dd065-134">If you do install and enable monitoring, then call information is gathered by agents running on the Front End server and relayed to a pair of SQL Server databases.</span></span>

<span data-ttu-id="dd065-135">Notez que le processus d’installation et de configuration de la surveillance a été simplifié dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dd065-135">Note that the process of installing and configuring monitoring has been simplified in Lync Server 2013.</span></span> <span data-ttu-id="dd065-136">Dans les versions précédentes du logiciel, la surveillance impliquait un rôle serveur de surveillance distinct, qui signifiait généralement un ordinateur distinct mis de côté pour être utilisé en tant que serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="dd065-136">In prior versions of the software, monitoring required a separate Monitoring Server role, which typically meant a separate computer set aside for use as the Monitoring Server.</span></span> <span data-ttu-id="dd065-137">Dans Lync Server 2013, toutefois, le rôle serveur de surveillance a été éliminé.</span><span class="sxs-lookup"><span data-stu-id="dd065-137">In Lync Server 2013, however, the Monitoring Server role has been eliminated.</span></span> <span data-ttu-id="dd065-138">Au lieu de cela, le service de surveillance (sous la forme d' « agents de collecte de données unifiées ») est colocalisé sur tous les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="dd065-138">Instead, the monitoring service (in the form of "unified data collection agents") has been collocated into all Front End servers.</span></span> <span data-ttu-id="dd065-139">Cela comporte au moins deux avantages majeurs.</span><span class="sxs-lookup"><span data-stu-id="dd065-139">This has at least two major benefits.</span></span> <span data-ttu-id="dd065-140">Colocalisation du service de surveillance :</span><span class="sxs-lookup"><span data-stu-id="dd065-140">Collocation of the monitoring service:</span></span>

  - <span data-ttu-id="dd065-141">Réduit le nombre de rôles serveur requis lors de l’implémentation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dd065-141">Decreases the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="dd065-142">La décrémentation du rôle de serveur de surveillance contribue également à réduire les coûts en supprimant le besoin de maintenir des serveurs dédiés à la surveillance.</span><span class="sxs-lookup"><span data-stu-id="dd065-142">Decrementing the Monitoring Server role also helps reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="dd065-143">Réduit la complexité de l’installation et de l’administration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dd065-143">Reduces the complexity of Lync Server 2013 setup and administration.</span></span> <span data-ttu-id="dd065-144">En colocaliser les services de surveillance sur chaque serveur frontal, vous n’avez plus besoin d’installer, de configurer et de gérer le rôle de serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="dd065-144">By collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<span data-ttu-id="dd065-145">Pour plus d’informations, reportez-vous à la rubrique [Deploying Monitoring in Lync server 2013](lync-server-2013-deploying-monitoring.md) dans le Guide de déploiement de lync Server 2013 2013.</span><span class="sxs-lookup"><span data-stu-id="dd065-145">For more information see the topic [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md) in the Lync Server 2013 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


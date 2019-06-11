---
title: 'Lync Server 2013: vue d’ensemble de la surveillance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88bfb8170b2334c322c612628daa1f8b9db2473c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a><span data-ttu-id="dee45-102">Vue d’ensemble de l’analyse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dee45-102">Overview of monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dee45-103">_**Dernière modification de la rubrique:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="dee45-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="dee45-104">Dans Microsoft Lync Server 2013, le contrôle permet de collecter les informations d’utilisation et les données de qualité d’utilisation (QoE) sur les sessions de communication auxquelles les utilisateurs participent.</span><span class="sxs-lookup"><span data-stu-id="dee45-104">In Microsoft Lync Server 2013, monitoring is used to collect usage information and Quality of Experience (QoE) data about the communication sessions that your users are involved in.</span></span> <span data-ttu-id="dee45-105">Une session est un terme générique qui couvre la connexion d’un utilisateur à:</span><span class="sxs-lookup"><span data-stu-id="dee45-105">A session is a generic term that covers a user’s connection to a:</span></span>

  - <span data-ttu-id="dee45-106">Conférence</span><span class="sxs-lookup"><span data-stu-id="dee45-106">Conference</span></span>

  - <span data-ttu-id="dee45-107">Modalité de conférences (par exemple, audio/vidéo ou partage d’applications)</span><span class="sxs-lookup"><span data-stu-id="dee45-107">Conferencing modality (such as Audio/Video or Application Sharing)</span></span>

  - <span data-ttu-id="dee45-108">un autre utilisateur via une conversation P2P (comme la messagerie instantanée ou un appel audio).</span><span class="sxs-lookup"><span data-stu-id="dee45-108">Another user via a peer-to-peer conversation such as instant messaging or an audio call</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dee45-109">Lync Server 2013 effectue le suivi des informations relatives à chaque session: qui a appelé qui; Quels points de terminaison utilisés dans la session; durée de la session, Quelle a été la qualité perçue de la session; et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="dee45-109">Lync Server 2013 keeps track of information about each session: who called who; which endpoints were used in the session; how long did the session last; what was the perceived quality of the session; and so on.</span></span> <span data-ttu-id="dee45-110">Toutefois, Lync Server n’enregistre et ne stocke pas l’appel réel.</span><span class="sxs-lookup"><span data-stu-id="dee45-110">However, Lync Server does not record and store the actual call itself.</span></span> <span data-ttu-id="dee45-111">Qui inclut également des sessions de messagerie instantanée: bien que Lync Server enregistre des informations sur les sessions de messagerie instantanée, il ne conserve aucun enregistrement de chaque message instantané envoyé lors de la session.</span><span class="sxs-lookup"><span data-stu-id="dee45-111">That includes instant messaging sessions as well: although Lync Server records information about instant messaging sessions, it does not maintain a record of each instant message that was sent during the session.</span></span>



</div>

<span data-ttu-id="dee45-112">Les informations détaillées des appels collectées par Lync Server peuvent être utilisées pour n’importe quel nombre d’usages, y compris:</span><span class="sxs-lookup"><span data-stu-id="dee45-112">The call detail information collected by Lync Server can be employed for any number of uses, including:</span></span>

  - <span data-ttu-id="dee45-113">**Retour sur investissement**.</span><span class="sxs-lookup"><span data-stu-id="dee45-113">**Return on Investment (ROI)**.</span></span> <span data-ttu-id="dee45-114">Les administrateurs peuvent comparer les données d’utilisation collectées par Monitoring Server à des données similaires collectées pour leur précédent système de téléphonie afin d’afficher des économies de coûts et de justifier le déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dee45-114">Administrators can compare the usage data collected by Monitoring Server to similar data collected for their previous telephony system in order to show cost savings and help justify the deployment of Lync Server.</span></span>

  - <span data-ttu-id="dee45-115">La **Gestion des stocks de périphériques**.</span><span class="sxs-lookup"><span data-stu-id="dee45-115">**Device Inventory Management**.</span></span> <span data-ttu-id="dee45-116">Les informations sur la gestion des ressources permettent aux administrateurs d’identifier les anciens appareils toujours en cours d’utilisation qui doivent être remplacés, ainsi que d’identifier les appareils coûteux qui ne semblent pas être utilisés du tout.</span><span class="sxs-lookup"><span data-stu-id="dee45-116">Asset management information helps administrators identify old devices still in use that need to be replaced, as well as identify expensive devices that do not appear to be getting used at all.</span></span>

  - <span data-ttu-id="dee45-117">Support technique.</span><span class="sxs-lookup"><span data-stu-id="dee45-117">Help Desk.</span></span> <span data-ttu-id="dee45-118">Les données de dépannage permettent aux ingénieurs de la prise en charge de déterminer la raison pour laquelle l’appel d’un utilisateur a échoué et de ne pas avoir à collecter les journaux côté serveur ou client.</span><span class="sxs-lookup"><span data-stu-id="dee45-118">Troubleshooting data enables support engineers to determine why a user’s call failed, and to do so without having to collect server or client side logs.</span></span> <span data-ttu-id="dee45-119">Il est possible d’accéder à ces informations et de les comprendre par le personnel du support technique disposant d’une connaissance technique approfondie de Microsoft Lync 2013 et de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dee45-119">This information can be readily accessed and understood by support personnel who do not have a deep technical knowledge of Microsoft Lync 2013 and Lync Server 2013.</span></span>

  - <span data-ttu-id="dee45-p106">**Identification et résolution des problèmes du système**. Permet aux administrateurs de détecter les problèmes majeurs qui peuvent empêcher les utilisateurs finaux d’effectuer des tâches de base comme la participation à une conférence, l’émission d’un appel ou l’envoi d’un message instantané.</span><span class="sxs-lookup"><span data-stu-id="dee45-p106">**System Troubleshooting**. Enables administrators to detect major issues that might prevent end users from performing basic tasks like joining a conference, establishing a call, or sending an instant message.</span></span>

<span data-ttu-id="dee45-122">En plus de ces informations de base, le serveur de surveillance fournit également un mécanisme qui permet aux points de terminaison SIP (par exemple, Lync 2013) de fournir des informations de dépannage auxquelles le serveur n’aura pas accès.</span><span class="sxs-lookup"><span data-stu-id="dee45-122">In addition to this basic call information, the Monitoring Server also provides a mechanism that allows SIP endpoints (such as Lync 2013) to provide troubleshooting information that the server would not otherwise have access to:</span></span>

  - <span data-ttu-id="dee45-123">**Mesures qui affectent la qualité**.</span><span class="sxs-lookup"><span data-stu-id="dee45-123">**Media Metrics that Impact Quality**.</span></span> <span data-ttu-id="dee45-124">Ces mesures traitent la transmission effective de l’appel. ils fournissent ainsi une sorte de journaux de voyages lors du déplacement de l’appel sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="dee45-124">These metrics deal with the actual transmission of the call itself; that is, they provide a sort of travel log as the call journeys across the network.</span></span> <span data-ttu-id="dee45-125">Ces mesures (qui incluent des éléments tels que la perte de paquets, la gigue et les temps d’aller-retour) fournissent des informations sur ce qui est arrivé à l’appel à partir du moment où il est parvenu au point de terminaison de l’autre personne.</span><span class="sxs-lookup"><span data-stu-id="dee45-125">These metrics (which include such things as packet loss, jitter, and round trip times) provide information on what happened to the call from the time it left your endpoint to the time it arrived at the other person's endpoint.</span></span>

  - <span data-ttu-id="dee45-126">**Problèmes signalés à l’utilisateur final**.</span><span class="sxs-lookup"><span data-stu-id="dee45-126">**Issues Reported to the End User**.</span></span> <span data-ttu-id="dee45-127">Ces mesures incluent des notifications de bonne qualité que Lync 2013 présenter aux utilisateurs finaux dans les cas où ceux-ci sont trop éloignés d’un micro, parlant trop de manière modérée, disposant d’une connexion réseau médiocre ou dont la qualité est médiocre, car un autre programme de l’ordinateur est utilisation des ressources disponibles.</span><span class="sxs-lookup"><span data-stu-id="dee45-127">These metrics include poor quality notifications that Lync 2013 presents to end users in cases where they are too far from a microphone, speaking too softly, have a poor network connection, or are experiencing poor quality because another program on the computer is consuming the available resources.</span></span>

  - <span data-ttu-id="dee45-p109">**Informations sur l’environnement**. Ces mesures détaillent des facteurs de qualité d’appel, notamment le type de micro et les haut-parleurs utilisés, si l’utilisateur est connecté via une connexion VPN et si l’utilisateur utilise une connexion sans fil.</span><span class="sxs-lookup"><span data-stu-id="dee45-p109">**Environment Information**. These metrics detail call quality factors such as the type of microphone and speakers being used, whether the user is connected through a VPN connection, and whether the user is on a wireless connection.</span></span>

<span data-ttu-id="dee45-130">À la fin de chaque appel, des points de terminaison compatibles SIP transmettent automatiquement ces informations au serveur frontal qui facilite l’appel.</span><span class="sxs-lookup"><span data-stu-id="dee45-130">At the end of each call, SIP-compliant endpoints automatically transmit this information to the Front End server that facilitated the call.</span></span> <span data-ttu-id="dee45-131">Aucune opération n’est nécessaire pour que les points de terminaison transmettent ces informations ; ce comportement est intégré au protocole SIP.</span><span class="sxs-lookup"><span data-stu-id="dee45-131">You don't have to do anything to get endpoints to transmit that information; that behavior is built into the SIP protocol.</span></span> <span data-ttu-id="dee45-132">Cependant, si vous souhaitez collecter et stocker ces informations, vous devez installer et activer la surveillance.</span><span class="sxs-lookup"><span data-stu-id="dee45-132">However, if you want to collect and store that information, then you need to install and enable monitoring.</span></span> <span data-ttu-id="dee45-133">Si vous installez et activez la surveillance, les informations relatives aux appels sont collectées par des agents exécutés sur le serveur frontal et relayées à une paire de bases de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dee45-133">If you do install and enable monitoring, then call information is gathered by agents running on the Front End server and relayed to a pair of SQL Server databases.</span></span>

<span data-ttu-id="dee45-134">Notez que le processus d’installation et de configuration de la surveillance a été simplifié dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dee45-134">Note that the process of installing and configuring monitoring has been simplified in Lync Server 2013.</span></span> <span data-ttu-id="dee45-135">Dans les versions antérieures du logiciel, la surveillance nécessitait un rôle serveur de surveillance distinct, qui signifiait en général un autre ordinateur mis en réserve pour une utilisation comme serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="dee45-135">In prior versions of the software, monitoring required a separate Monitoring Server role, which typically meant a separate computer set aside for use as the Monitoring Server.</span></span> <span data-ttu-id="dee45-136">Par le biais de Lync Server 2013, le rôle serveur de surveillance a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="dee45-136">In Lync Server 2013, however, the Monitoring Server role has been eliminated.</span></span> <span data-ttu-id="dee45-137">Au lieu de cela, le service de surveillance (qui se présente sous la forme d’agents de collection de données unifiées) a été colocalisé sur tous les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="dee45-137">Instead, the monitoring service (in the form of "unified data collection agents") has been collocated into all Front End servers.</span></span> <span data-ttu-id="dee45-138">Vous avez au moins deux avantages principaux.</span><span class="sxs-lookup"><span data-stu-id="dee45-138">This has at least two major benefits.</span></span> <span data-ttu-id="dee45-139">Colocalisation du service de surveillance:</span><span class="sxs-lookup"><span data-stu-id="dee45-139">Collocation of the monitoring service:</span></span>

  - <span data-ttu-id="dee45-140">Réduit le nombre de rôles de serveur requis lors de l’implémentation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dee45-140">Decreases the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="dee45-141">Le fait de décrémenter le rôle du serveur de surveillance permet également de réduire les coûts en éliminant le besoin de mettre à jour les serveurs dédiés pour la surveillance.</span><span class="sxs-lookup"><span data-stu-id="dee45-141">Decrementing the Monitoring Server role also helps reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="dee45-142">Simplifie la configuration et l’administration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dee45-142">Reduces the complexity of Lync Server 2013 setup and administration.</span></span> <span data-ttu-id="dee45-143">En collocatingant les services de surveillance sur chaque serveur frontal, vous n’avez plus besoin d’installer, de configurer et de gérer le rôle du serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="dee45-143">By collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<span data-ttu-id="dee45-144">Pour plus d’informations, reportez-vous à la rubrique [déploiement de la surveillance dans Lync server 2013](lync-server-2013-deploying-monitoring.md) dans le Guide de déploiement de lync Server 2013 2013.</span><span class="sxs-lookup"><span data-stu-id="dee45-144">For more information see the topic [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md) in the Lync Server 2013 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


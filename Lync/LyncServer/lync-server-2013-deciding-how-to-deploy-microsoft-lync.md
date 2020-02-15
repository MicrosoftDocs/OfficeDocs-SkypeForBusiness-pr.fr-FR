---
title: 'Lync Server 2013 : choix du mode de déploiement de Microsoft Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a731b4385dbe46da39fc195e1de6be13057e649d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a><span data-ttu-id="d4c88-102">Choix du mode de déploiement de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4c88-102">Deciding how to deploy Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4c88-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="d4c88-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="d4c88-104">Lors de la planification de Lync, la première décision majeure concerne le déploiement de Microsoft Lync : Lync Server 2013 sur site ou Lync Online avec Microsoft Office 365 dans le Cloud.</span><span class="sxs-lookup"><span data-stu-id="d4c88-104">When planning for Lync, the first major decision is how to deploy Microsoft Lync: as Lync Server 2013 on premises, or Lync Online with Microsoft Office 365 in the cloud.</span></span>

  - <span data-ttu-id="d4c88-105">**Lync Server 2013 en local** : ce choix fournit l’ensemble de fonctionnalités Lync complet et offre une flexibilité optimale pour la configuration, la personnalisation et l’exploitation de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="d4c88-105">**Lync Server 2013 on-premises** : This choice provides the complete Lync feature set and provides ultimate flexibility in configuring, customizing, and operating your deployment.</span></span> <span data-ttu-id="d4c88-106">Tous les serveurs sont installés sur site et gérés par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d4c88-106">All servers are installed onsite and maintained by your organization.</span></span> <span data-ttu-id="d4c88-107">Un déploiement sur site fournit toute la gamme de fonctionnalités Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d4c88-107">An on-premises deployment provides the full range of Lync Server features.</span></span>

  - <span data-ttu-id="d4c88-108">**Lync Online dans le Cloud** Lync Online est conçu pour les organisations qui souhaitent bénéficier des avantages offerts par la messagerie instantanée, la présence et les réunions en nuage sans sacrifier les fonctionnalités professionnelles de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d4c88-108">**Lync Online in the cloud** Lync Online is designed for organizations that want the cost and agility benefits of cloud-based instant messaging, presence, and meetings without sacrificing the business-class capabilities of Lync Server.</span></span> <span data-ttu-id="d4c88-109">Avec Lync Online, Microsoft déploie et gère l’infrastructure serveur requise, et gère la maintenance, les correctifs et les mises à niveau en continu.</span><span class="sxs-lookup"><span data-stu-id="d4c88-109">With Lync Online, Microsoft deploys and maintains the required server infrastructure, and handles ongoing maintenance, patches, and upgrades.</span></span> <span data-ttu-id="d4c88-110">Certaines fonctionnalités disponibles dans un déploiement local ne sont pas disponibles dans Lync Online.</span><span class="sxs-lookup"><span data-stu-id="d4c88-110">Some features available in an on-premises deployment are not available in Lync Online.</span></span>

<span data-ttu-id="d4c88-111">Le type de déploiement qui vous convient le mieux dépend des charges de travail à déployer, ainsi que du statut d’entreprise et de l’emplacement géographique de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d4c88-111">Which type of deployment would be best for you depends on the workloads you want to deploy, and your organization’s geographical and business status.</span></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="d4c88-112">Lync Server</span><span class="sxs-lookup"><span data-stu-id="d4c88-112">Lync Server</span></span>

<span data-ttu-id="d4c88-113">Un déploiement Lync Server local est plus adapté aux scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="d4c88-113">An on-premises Lync Server deployment is best for the following scenarios:</span></span>

  - <span data-ttu-id="d4c88-114">**Fonctionnalités voix entreprise complètes**   si vous envisagez de déployer une solution voix entreprise complète pour remplacer votre système PBX ou qui utilise des fonctionnalités d’appel avancées, un déploiement Lync Server local est requis.</span><span class="sxs-lookup"><span data-stu-id="d4c88-114">**Full Enterprise Voice Capabilities**   If you plan to deploy a full Enterprise Voice solution to replace your PBX or which uses advanced calling features, an on-premises Lync Server deployment is required.</span></span> <span data-ttu-id="d4c88-115">Le déploiement local prend en charge la connectivité directe avec des systèmes et jonctions PBX, ainsi que des fonctionnalités de téléphonie avancées telles que les groupes de réponses et le parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="d4c88-115">On-premises supports direct connectivity with PBX systems and trunks, and advanced phone features such as response groups and call park.</span></span> <span data-ttu-id="d4c88-116">Lync Online ne prend actuellement pas en charge ces fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="d4c88-116">Lync Online does not currently support these features.</span></span>

  - <span data-ttu-id="d4c88-117">**Contrôles**   de la qualité des médias si vous souhaitez bénéficier de toutes les fonctionnalités d’assurance qualité des médias, telles que les fonctionnalités de contrôle d’admission des appels (CAC) et de qualité de service (QoS), vous devez disposer d’un déploiement local.</span><span class="sxs-lookup"><span data-stu-id="d4c88-117">**Media Quality Controls**   If you want the full range of media quality assurance features, such as Call Admission Control (CAC) and Quality of Service (QoS) features, you will want an on-premises deployment .</span></span>

  - <span data-ttu-id="d4c88-118">**Conversation permanente si**   vous devez déployer une conversation permanente pour votre organisation, vous devez choisir un déploiement local.</span><span class="sxs-lookup"><span data-stu-id="d4c88-118">**Persistent Chat**   If you need to deploy Persistent chat for your organization, you must choose an on-premises deployment.</span></span>

  - <span data-ttu-id="d4c88-119">**applications serveur tierces**   seuls les déploiements locaux peuvent fonctionner avec des applications tierces approuvées qui utilisent Microsoft Unified Communications Managed API (UCMA).</span><span class="sxs-lookup"><span data-stu-id="d4c88-119">**3rd-Party Server Applications**   Only on-premises deployments can work with trusted 3rd-party applications that use the Microsoft Unified Communications Managed API (UCMA).</span></span>

  - <span data-ttu-id="d4c88-120">**Sociétés multinationales/multirégionaless ayant besoin**   d’un support régional si vous avez des centres de recherche dans plusieurs pays ou régions et que vous avez besoin de déployer et de gérer des serveurs au niveau régional, il est préférable d’utiliser un déploiement local, car il fournit ce type de fonctionnalités de gestion régionale.</span><span class="sxs-lookup"><span data-stu-id="d4c88-120">**Multi-National/Multi-Regional Companies Needing Regional Support**   If you have datacenters in multiple countries or regions and need servers to be deployed and managed on a regional basis, an on-premises deployment is best, as it provides this type of regional management capabilities.</span></span>

  - <span data-ttu-id="d4c88-121">**Contrôle total des stratégies, des rapports et des mises à niveau**   avec un déploiement Lync Server local, vous avez accès à l’ensemble complet des stratégies de serveur et de client, de surveillance et autres rapports, ainsi que du minutage des mises à niveau.</span><span class="sxs-lookup"><span data-stu-id="d4c88-121">**Complete control over policies, reports, and upgrades**   With an on premises Lync Server deployment, you have access to the full set of server and client policies, Monitoring and other reports, and timing of upgrades.</span></span> <span data-ttu-id="d4c88-122">Lync Online fournit un sous-ensemble de paramètres et de rapports de stratégie, et fournit une fenêtre limitée, bien qu’significative, pour l’acceptation des mises à niveau.</span><span class="sxs-lookup"><span data-stu-id="d4c88-122">Lync Online provides a subset of policy setting and reports, and provides a limited, though significant, window for accepting upgrades.</span></span>

</div>

<div>

## <a name="lync-online"></a><span data-ttu-id="d4c88-123">Lync Online</span><span class="sxs-lookup"><span data-stu-id="d4c88-123">Lync Online</span></span>

<span data-ttu-id="d4c88-124">Si aucun des facteurs figurant dans la liste précédente n’est essentiel pour vous, vous pouvez choisir Lync Online, pour un déploiement plus simple et une facilité de gestion.</span><span class="sxs-lookup"><span data-stu-id="d4c88-124">If none of the factors in the preceding list are critical for you, you may want to choose Lync Online, for simpler deployment and manageability.</span></span> <span data-ttu-id="d4c88-125">Lync Online offre un ensemble de fonctionnalités de messagerie instantanée, de présence et de conférence, ainsi que des appels vocaux et vidéo sur IP entre les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d4c88-125">Lync Online provides a robust IM, presence and conferencing feature set, and also enables voice and video calls over IP between users in your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


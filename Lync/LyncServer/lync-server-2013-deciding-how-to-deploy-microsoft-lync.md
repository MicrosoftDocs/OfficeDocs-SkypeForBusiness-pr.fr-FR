---
title: 'Lync Server 2013 : Choix des modalités de déploiement de Microsoft Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d641f4da1884c1fb6e84eefb2127490f2ed3c4a9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a><span data-ttu-id="06823-102">Choix des modalités de déploiement de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06823-102">Deciding how to deploy Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06823-103">_**Dernière modification de la rubrique:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="06823-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="06823-104">Lors de la planification de Lync, la première décision majeure consiste à déployer Microsoft Lync: comme Lync Server 2013 en local ou Lync Online avec Microsoft Office 365 dans le Cloud.</span><span class="sxs-lookup"><span data-stu-id="06823-104">When planning for Lync, the first major decision is how to deploy Microsoft Lync: as Lync Server 2013 on premises, or Lync Online with Microsoft Office 365 in the cloud.</span></span>

  - <span data-ttu-id="06823-105">**Lync Server 2013 local** : ce choix fournit l’ensemble des fonctionnalités Lync complètes et offre une souplesse de configuration, de personnalisation et d’utilisation de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="06823-105">**Lync Server 2013 on-premises** : This choice provides the complete Lync feature set and provides ultimate flexibility in configuring, customizing, and operating your deployment.</span></span> <span data-ttu-id="06823-106">Tous les serveurs sont installés sur site et gérés par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="06823-106">All servers are installed onsite and maintained by your organization.</span></span> <span data-ttu-id="06823-107">Un déploiement local fournit une gamme complète de fonctionnalités de serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="06823-107">An on-premises deployment provides the full range of Lync Server features.</span></span>

  - <span data-ttu-id="06823-108">**Lync Online dans le Cloud** Lync Online est conçu pour les organisations qui souhaitent bénéficier de coûts et de compétences en matière de messagerie instantanée, de présence et de réunions dans le Cloud sans sacrifier les fonctionnalités de niveau professionnel de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06823-108">**Lync Online in the cloud** Lync Online is designed for organizations that want the cost and agility benefits of cloud-based instant messaging, presence, and meetings without sacrificing the business-class capabilities of Lync Server.</span></span> <span data-ttu-id="06823-109">Avec Lync Online, Microsoft déploie et met à jour l’infrastructure de serveur requise, ainsi que les mises à jour, les correctifs et les mises à niveau en continu.</span><span class="sxs-lookup"><span data-stu-id="06823-109">With Lync Online, Microsoft deploys and maintains the required server infrastructure, and handles ongoing maintenance, patches, and upgrades.</span></span> <span data-ttu-id="06823-110">Certaines fonctionnalités disponibles dans un déploiement local ne sont pas disponibles dans Lync Online.</span><span class="sxs-lookup"><span data-stu-id="06823-110">Some features available in an on-premises deployment are not available in Lync Online.</span></span>

<span data-ttu-id="06823-111">Le type de déploiement le plus approprié dépend des charges de travail que vous voulez déployer et du statut géographique et commercial de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="06823-111">Which type of deployment would be best for you depends on the workloads you want to deploy, and your organization’s geographical and business status.</span></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="06823-112">Lync Server</span><span class="sxs-lookup"><span data-stu-id="06823-112">Lync Server</span></span>

<span data-ttu-id="06823-113">Le déploiement de Lync Server local est préférable pour les scénarios suivants:</span><span class="sxs-lookup"><span data-stu-id="06823-113">An on-premises Lync Server deployment is best for the following scenarios:</span></span>

  - <span data-ttu-id="06823-114">**Fonctionnalités vocales complètes d’entreprise**   si vous envisagez de déployer une solution voix entreprise complète pour remplacer votre PBX ou qui utilise des fonctionnalités d’appel avancées, un déploiement Lync Server local est requis.</span><span class="sxs-lookup"><span data-stu-id="06823-114">**Full Enterprise Voice Capabilities**   If you plan to deploy a full Enterprise Voice solution to replace your PBX or which uses advanced calling features, an on-premises Lync Server deployment is required.</span></span> <span data-ttu-id="06823-115">Locale prend en charge la connectivité directe avec les systèmes et les Trunks PBX, ainsi que les fonctionnalités de téléphone avancées telles que les Response Groups et le parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="06823-115">On-premises supports direct connectivity with PBX systems and trunks, and advanced phone features such as response groups and call park.</span></span> <span data-ttu-id="06823-116">Pour le moment, Lync Online ne prend pas en charge ces fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="06823-116">Lync Online does not currently support these features.</span></span>

  - <span data-ttu-id="06823-117">**Contrôles qualité multimédia**   si vous voulez bénéficier de la gamme complète de fonctionnalités d’assurance qualité multimédia, comme les fonctionnalités de contrôle d’admission des appels (CAC) et de qualité de service (QoS), vous devez disposer d’un déploiement local.</span><span class="sxs-lookup"><span data-stu-id="06823-117">**Media Quality Controls**   If you want the full range of media quality assurance features, such as Call Admission Control (CAC) and Quality of Service (QoS) features, you will want an on-premises deployment .</span></span>

  - <span data-ttu-id="06823-118">**Discussions permanentes**   si vous devez déployer une conversation permanente pour votre organisation, vous devez choisir un déploiement local.</span><span class="sxs-lookup"><span data-stu-id="06823-118">**Persistent Chat**   If you need to deploy Persistent chat for your organization, you must choose an on-premises deployment.</span></span>

  - <span data-ttu-id="06823-119">**les applications**   serveur tierces uniquement les déploiements locaux peuvent fonctionner avec des applications tierces approuvées qui utilisent l’API Microsoft Unified Communications Managed API (UCMA).</span><span class="sxs-lookup"><span data-stu-id="06823-119">**3rd-Party Server Applications**   Only on-premises deployments can work with trusted 3rd-party applications that use the Microsoft Unified Communications Managed API (UCMA).</span></span>

  - <span data-ttu-id="06823-120">**Les sociétés multinationales/multiterritoriales ont besoin d’une prise en charge**   régionale si vous disposez de centres de donneurs dans plusieurs pays ou régions et que vous avez besoin de déployer et de gérer des serveurs sur une base régionale, il est préférable d’utiliser un déploiement local, car il fournit ce type de capacités de gestion régionale.</span><span class="sxs-lookup"><span data-stu-id="06823-120">**Multi-National/Multi-Regional Companies Needing Regional Support**   If you have datacenters in multiple countries or regions and need servers to be deployed and managed on a regional basis, an on-premises deployment is best, as it provides this type of regional management capabilities.</span></span>

  - <span data-ttu-id="06823-121">**Contrôle complet sur les stratégies, les rapports et les mises à niveau**   avec un déploiement de Lync Server sur site, vous avez accès à l’ensemble des stratégies du serveur et du client, à la surveillance et aux autres rapports et au minutage des mises à niveau.</span><span class="sxs-lookup"><span data-stu-id="06823-121">**Complete control over policies, reports, and upgrades**   With an on premises Lync Server deployment, you have access to the full set of server and client policies, Monitoring and other reports, and timing of upgrades.</span></span> <span data-ttu-id="06823-122">Lync Online fournit un sous-ensemble du paramètre de stratégie et des rapports, et fournit une fenêtre limitée, même importante, pour accepter les mises à niveau.</span><span class="sxs-lookup"><span data-stu-id="06823-122">Lync Online provides a subset of policy setting and reports, and provides a limited, though significant, window for accepting upgrades.</span></span>

</div>

<div>

## <a name="lync-online"></a><span data-ttu-id="06823-123">Lync Online</span><span class="sxs-lookup"><span data-stu-id="06823-123">Lync Online</span></span>

<span data-ttu-id="06823-124">Si aucun des facteurs de la liste précédente n’est essentiel pour vous, vous pouvez choisir Lync Online pour faciliter le déploiement et la gestion.</span><span class="sxs-lookup"><span data-stu-id="06823-124">If none of the factors in the preceding list are critical for you, you may want to choose Lync Online, for simpler deployment and manageability.</span></span> <span data-ttu-id="06823-125">Lync Online fournit un ensemble de fonctionnalités de messagerie instantanée, de présence et de conférence puissantes, ainsi que des appels audio et vidéo sur IP entre les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="06823-125">Lync Online provides a robust IM, presence and conferencing feature set, and also enables voice and video calls over IP between users in your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013 : Déploiement de l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying external user access
ms:assetid: d40c9574-c16b-4fe6-b848-21ae0b7e4f0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398918(v=OCS.15)
ms:contentKeyID: 48185495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e8522eac5ace72f615cc3cb7b9271981d1b84c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-external-user-access-in-lync-server-2013"></a><span data-ttu-id="6eed6-102">Déploiement de l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eed6-102">Deploying external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6eed6-103">_**Dernière modification de la rubrique:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="6eed6-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="6eed6-104">Le déploiement de composants Edge pour Microsoft Lync Server 2013 permet aux utilisateurs externes qui ne sont pas connectés au réseau interne de votre organisation, notamment les utilisateurs distants authentifiés et anonymes, les partenaires fédérés (y compris les partenaires XMPP), clients mobiles et utilisateurs de services de messagerie instantanée publics pour communiquer avec d’autres utilisateurs de votre organisation à l’aide de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6eed6-104">Deploying edge components for Microsoft Lync Server 2013 makes it possible for external users who are not logged into your organization’s internal network, including authenticated and anonymous remote users, federated partners (including XMPP partners), mobile clients and users of public instant messaging (IM) services, to communicate with other users in your organization using Lync Server.</span></span> <span data-ttu-id="6eed6-105">Les processus de déploiement et de configuration de Lync Server 2013 ne sont pas très différents de ceux de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6eed6-105">The deployment and configuration processes for Lync Server 2013 are not significantly different from Lync Server 2010.</span></span> <span data-ttu-id="6eed6-106">Les outils d’installation et d’administration sont similaires à ceux de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6eed6-106">The tools for installation and administration are much the same as in Lync Server 2010.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6eed6-107">L’installation et la&nbsp;configuration de Microsoft Lync Server 2013 Edge Server peuvent être un processus complexe nécessitant une quantité ou une coordination significative de la planification et de la coordination avec vos équipes internes, y compris, mais sans s’y limiter, la sécurité, le réseau, le pare-feu, le système de nom de domaine (DNS), l’équilibrage de charge et les considérations en matière d’infrastructure à clé publique (PKI).</span><span class="sxs-lookup"><span data-stu-id="6eed6-107">Microsoft Lync Server 2013&nbsp;Edge Server installation and configuration can be a complex process requiring a potentially significant amount of planning and coordination with your internal teams, including – but not limited to – security, networking, firewall, domain name system (DNS), load balancer, and public key infrastructure (PKI) considerations.</span></span> <span data-ttu-id="6eed6-108">Nous vous conseillons vivement de passer en revue et d’utiliser le processus de planification et la documentation fournies avant de déployer vos composants Access externes.</span><span class="sxs-lookup"><span data-stu-id="6eed6-108">It is strongly recommended that you review and use the planning process and documentation provided before deploying your external access components.</span></span> <span data-ttu-id="6eed6-109">Cela vous permettra de limiter le nombre et la fréquence de modifications et de problèmes indésirables lors du processus de déploiement.</span><span class="sxs-lookup"><span data-stu-id="6eed6-109">This will assist in limiting the number and frequency of undesired changes and problems as you proceed through the deployment process.</span></span> <span data-ttu-id="6eed6-110">Pour plus d’informations sur la planification de l’accès aux utilisateurs externes, voir <A href="lync-server-2013-planning-for-external-user-access.md">planification d’un accès utilisateur externe dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6eed6-110">For information on planning you external user access, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6eed6-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="6eed6-111">In This Section</span></span>

  - [<span data-ttu-id="6eed6-112">Liste de vérification du déploiement pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eed6-112">Deployment checklist for external user access in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-external-user-access.md)

  - [<span data-ttu-id="6eed6-113">Configuration système requise pour les composants d’accès des utilisateurs externes pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eed6-113">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="6eed6-114">Préparation de l’installation des serveurs sur le réseau de périmètre pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eed6-114">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>](lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md)

  - [<span data-ttu-id="6eed6-115">Création d’une topologie de serveurs Edge et directeurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eed6-115">Building an edge and Director topology in Lync Server 2013</span></span>](lync-server-2013-building-an-edge-and-director-topology.md)

  - <span data-ttu-id="6eed6-116">[Configuration du réalisateur dans Lync Server 2013](lync-server-2013-setting-up-the-director.md) facultatif</span><span class="sxs-lookup"><span data-stu-id="6eed6-116">[Setting up the Director in Lync Server 2013](lync-server-2013-setting-up-the-director.md) (optional)</span></span>

  - [<span data-ttu-id="6eed6-117">Configuration des serveurs Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eed6-117">Setting up Edge Servers in Lync Server 2013</span></span>](lync-server-2013-setting-up-edge-servers.md)

  - [<span data-ttu-id="6eed6-118">Configuration des serveurs proxy inverses pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eed6-118">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)

  - [<span data-ttu-id="6eed6-119">Configuration de la prise en charge de l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eed6-119">Configuring support for external user access in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-external-user-access.md)

  - [<span data-ttu-id="6eed6-120">Guide d’approvisionnement pour la connectivité Lync-Skype dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eed6-120">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

  - [<span data-ttu-id="6eed6-121">Configuration des fédérations SIP et XMPP et de la messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eed6-121">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="6eed6-122">Déploiement de la mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eed6-122">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="6eed6-123">Vérification de votre déploiement Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eed6-123">Verifying your edge deployment in Lync Server 2013</span></span>](lync-server-2013-verifying-your-edge-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


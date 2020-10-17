---
title: 'Lync Server 2013 : installation de logiciels facultatifs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f56d856aa0a97125812f68ede9a2bff5b49f036
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498531"
---
# <a name="installing-optional-software-in-lync-server-2013"></a><span data-ttu-id="962ca-102">Installation de logiciels facultatifs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="962ca-102">Installing optional software in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="962ca-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="962ca-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="962ca-104">L’outil de planification Microsoft Lync Server 2013 est conçu pour l’exportation vers Microsoft Excel et Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="962ca-104">The Microsoft Lync Server 2013, Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="962ca-105">Bien que ces applications ne soient pas requises pour le fonctionnement de l’outil de planification, elles ajoutent une valeur significative au déploiement et à la documentation de votre conception.</span><span class="sxs-lookup"><span data-stu-id="962ca-105">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

<div>

## <a name="optional-software"></a><span data-ttu-id="962ca-106">Logiciels facultatifs</span><span class="sxs-lookup"><span data-stu-id="962ca-106">Optional Software</span></span>

<div>

## <a name="microsoft-excel"></a><span data-ttu-id="962ca-107">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="962ca-107">Microsoft Excel</span></span>

<span data-ttu-id="962ca-108">L’exportation de votre conception vers Microsoft Excel crée un rapport qui affiche sept onglets dans la feuille de calcul :</span><span class="sxs-lookup"><span data-stu-id="962ca-108">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

  - <span data-ttu-id="962ca-109">Résumé : affiche des informations sur la configuration du site, notamment le nombre d’utilisateurs, les paramètres de capacité et les informations de profil de serveur.</span><span class="sxs-lookup"><span data-stu-id="962ca-109">Summary – Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

  - <span data-ttu-id="962ca-110">Profil matériel : affiche un rapport détaillant les configurations matérielles recommandées pour les serveurs spécifiés dans la topologie, y compris le processeur, la mémoire, le disque et l’interface réseau.</span><span class="sxs-lookup"><span data-stu-id="962ca-110">Hardware Profile – Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="962ca-111">La quantité et les spécifications recommandées pour les composants serveur sont également incluses.</span><span class="sxs-lookup"><span data-stu-id="962ca-111">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="962ca-112">Par ailleurs, chaque serveur est défini par site pour fournir une représentation complète des exigences en matière de serveur par site.</span><span class="sxs-lookup"><span data-stu-id="962ca-112">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

  - <span data-ttu-id="962ca-113">Ports Requirements : affiche un rapport de tous les ports activés, ainsi que l’association avec l’équilibrage de charge DNS (Domain Name System) et les programmes d’équilibrage de la charge matérielle (charge matérielle).</span><span class="sxs-lookup"><span data-stu-id="962ca-113">Ports Requirements – Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="962ca-114">Vous devez utiliser ce rapport pour planifier vos configurations de pare-feu et de DNS et charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="962ca-114">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

  - <span data-ttu-id="962ca-115">Rapport de synthèse : affiche le résumé général des paramètres requis pour configurer votre réseau de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="962ca-115">Summary Report – Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

  - <span data-ttu-id="962ca-116">Certificate Report : affiche le nom de l’objet et les autres noms du sujet requis pour les certificats nécessaires pour obtenir les serveurs Edge en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="962ca-116">Certificates Report – Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

  - <span data-ttu-id="962ca-117">Rapport de pare-feu : affiche les adresses IP et les ports source et de destination pour les interfaces internes et externes.</span><span class="sxs-lookup"><span data-stu-id="962ca-117">Firewall Report – Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

  - <span data-ttu-id="962ca-118">Rapport DNS : affiche le nom de domaine complet (FQDN) et les adresses IP/VIP requises pour chaque entrée DNS que vous créez.</span><span class="sxs-lookup"><span data-stu-id="962ca-118">DNS Report – Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

</div>

<div>

## <a name="microsoft-visio"></a><span data-ttu-id="962ca-119">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="962ca-119">Microsoft Visio</span></span>

<span data-ttu-id="962ca-p104">L’exportation de votre conception vers Microsoft Visio crée un diagramme à utiliser dans la documentation de votre topologie et infrastructure configurée. Le diagramme importé peut être modifié et réorganisé pour répondre aux besoins de votre documentation. Un diagramme Visio classique inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="962ca-p104">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="962ca-123">Si votre conception est suffisamment importante pour nécessiter plus de trois serveurs frontaux, une page supplémentaire est créée pour le pool frontal, les serveurs frontaux, l’ordinateur exécutant SQL Server, les adresses IP et les noms de domaine complets.</span><span class="sxs-lookup"><span data-stu-id="962ca-123">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>



</div>

  - <span data-ttu-id="962ca-124">Topologie globale : diagramme des sites Lync Server 2013 configurés.</span><span class="sxs-lookup"><span data-stu-id="962ca-124">Global Topology – Diagram of configured Lync Server 2013 sites.</span></span>

  - <span data-ttu-id="962ca-125">Onglet nom du site – affiche la topologie de configuration de site avec le serveur Edge, le pare-feu, le réseau téléphonique commuté (RTC) avec passerelles et le déploiement du serveur interne.</span><span class="sxs-lookup"><span data-stu-id="962ca-125">Site Name tab – Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="962ca-126">Le déploiement interne se compose de serveurs et de pools configurés, y compris les pools frontaux, les serveurs SQL Server, les services de domaine Active Directory, les directeurs, les serveurs de messagerie unifiée Exchange, les serveurs de boîtes aux lettres Exchange, les serveurs Office Web Apps, les serveurs de médiation et les serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="962ca-126">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

  - <span data-ttu-id="962ca-127">Diagramme de réseau Edge : diagramme détaillant la configuration du serveur Edge avec des adresses IP et des noms de domaine complets associés.</span><span class="sxs-lookup"><span data-stu-id="962ca-127">Edge Network Diagram – Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="962ca-128">L’équilibrage de charge DNS et les programmes d’équilibrage de la charge matérielle sont également inclus.</span><span class="sxs-lookup"><span data-stu-id="962ca-128">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="962ca-129">De plus, les directeurs et le serveur frontal ou le pool frontal sont affichés, avec le DNS charge matérielle associé et l’adresse IP affectée (l’outil de planification prend en charge les adresses IPv4 et IPv6) et le nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="962ca-129">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="962ca-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="962ca-130">See Also</span></span>


[<span data-ttu-id="962ca-131">Installation de l’outil de planification dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="962ca-131">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


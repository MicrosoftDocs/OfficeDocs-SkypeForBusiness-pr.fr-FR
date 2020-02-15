---
title: 'Lync Server 2013 : surveillance des performances du réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8524499737ae1e52a36a80fbc636f005b687a6a0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-network-performance-in-lync-server-2013"></a><span data-ttu-id="a5435-102">Surveillance des performances réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5435-102">Monitoring network performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5435-103">_**Dernière modification de la rubrique :** 2016-04-27_</span><span class="sxs-lookup"><span data-stu-id="a5435-103">_**Topic Last Modified:** 2016-04-27_</span></span>

<span data-ttu-id="a5435-104">Lync Server 2013 est une technologie de communication en temps réel qui repose largement sur le réseau pour permettre la communication entre les utilisateurs, via la messagerie instantanée, les appels vocaux ou la communication vidéo.</span><span class="sxs-lookup"><span data-stu-id="a5435-104">Lync Server 2013 is a real-time communications technology that relies heavily on the network to enable communication between users—either through instant messaging (IM), voice calls, or video communication.</span></span> <span data-ttu-id="a5435-105">Il est donc important de surveiller en permanence les performances du réseau afin de garantir que la modalité de communication choisie par un utilisateur offre la meilleure expérience possible.</span><span class="sxs-lookup"><span data-stu-id="a5435-105">It is therefore important to monitor the network performance continuously to help guarantee that a user’s chosen communication modality provides the best possible experience.</span></span>

<span data-ttu-id="a5435-106">Les performances du réseau peuvent être mesurées à deux niveaux :</span><span class="sxs-lookup"><span data-stu-id="a5435-106">Network performance can be measured at two levels:</span></span>

  - <span data-ttu-id="a5435-107">**Performances réseau globales**   ce niveau de mesure des performances permet à une organisation de créer une vue « grande image » de son réseau et est généralement implémentée par le biais de systèmes de surveillance réseau tiers.</span><span class="sxs-lookup"><span data-stu-id="a5435-107">**Overall network performance**   This level of performance measurement will allow an organization to create a "big-picture" view of their network and is usually implemented through third-party network monitoring systems.</span></span> <span data-ttu-id="a5435-108">Ces systèmes recevront des données de performances et de capacité provenant d’appareils réseau distants tels que des routeurs et basculés sur le réseau pour permettre aux administrateurs de déterminer l’intégrité d’un composant réseau donné à tout moment de la journée.</span><span class="sxs-lookup"><span data-stu-id="a5435-108">These systems will receive performance and capacity data from remote network devices such as routers and switched throughout the network to allow administrators to determine the health of any given network component at any time of day.</span></span>

  - <span data-ttu-id="a5435-109">**Performances des serveurs individuels**   ce niveau de mesure des performances est limité à un serveur spécifique et aide les administrateurs à évaluer les performances réseau d’un serveur spécifique en vue d’aider à résoudre un problème de performances spécifique ou à évaluer les performances du serveur respectif sur une période donnée dans le cadre d’un processus de planification de la capacité.</span><span class="sxs-lookup"><span data-stu-id="a5435-109">**Individual server performance**   This level of performance measurement is limited to a specific server and will help administrators with gauging the network performance of a specific server to either help with troubleshooting a specific performance issue or to gauge the respective server’s performance over a given period as part of a capacity planning process.</span></span>

<span data-ttu-id="a5435-110">Vous pouvez surveiller le réseau à l’aide des outils décrits dans les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="a5435-110">You can monitor the network by using the tools described in the following sections.</span></span>

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a><span data-ttu-id="a5435-111">Outils d’analyse des performances réseau globales</span><span class="sxs-lookup"><span data-stu-id="a5435-111">Tools for Overall Network Performance Monitoring</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="a5435-112">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="a5435-112">System Center Operations Manager 2012</span></span>

<span data-ttu-id="a5435-113">System Center Operations Manager offre une gestion des services de bout en bout, facile à personnaliser et permettant d’étendre les niveaux de service améliorés au sein d’un environnement informatique.</span><span class="sxs-lookup"><span data-stu-id="a5435-113">System Center Operations Manager provides end-to-end service management that is easy to customize and extend for improved service levels across an IT environment.</span></span> <span data-ttu-id="a5435-114">Cela permet aux équipes opérationnelles et de gestion informatique d’identifier et de résoudre les problèmes affectant l’intégrité des services informatiques distribués.</span><span class="sxs-lookup"><span data-stu-id="a5435-114">This enables Operations and IT Management teams to identify, and resolve issues affecting the health of distributed IT services.</span></span> <span data-ttu-id="a5435-115">La gestion des services de bout en bout n’est pas limitée aux environnements Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a5435-115">End-to-end service management is not restricted to Microsoft-based environments.</span></span> <span data-ttu-id="a5435-116">La prise en charge des services Web pour la gestion (WS-Management), le protocole SNMP (simple Network Management Protocol) et les solutions partenaires permettent aux systèmes qui n’exécutent pas les systèmes d’exploitation et le matériel Microsoft d’être inclus dans l’analyse de service au sein de System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="a5435-116">Support for Web Services for Management (WS-Management), Simple Network Management Protocol (SNMP), and partner solutions allow for systems that do not run Microsoft operating systems and hardware to be included in service monitoring within System Center Operations Manager 2012.</span></span>

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a><span data-ttu-id="a5435-117">System Center Operations Manager 2012 et solutions de gestion de réseau tierces</span><span class="sxs-lookup"><span data-stu-id="a5435-117">System Center Operations Manager 2012 and Third-Party Network Management Solutions</span></span>

<span data-ttu-id="a5435-118">**EMC Smarts**   EMC Solutions for Operations Manager vous aident à résoudre rapidement les problèmes affectant les niveaux de service tout au long de.</span><span class="sxs-lookup"><span data-stu-id="a5435-118">**EMC Smarts**   EMC Solutions for Operations Manager help you quickly resolve issues affecting service levels throughout.</span></span> <span data-ttu-id="a5435-119">En utilisant les solutions EMC pour les opérations Manager, vous pouvez gérer et surveiller l’ensemble de votre chaîne de service informatique à l’aide d’une solution automatisée intégrée.</span><span class="sxs-lookup"><span data-stu-id="a5435-119">By using EMC Solutions for Operations Manager, you can manage and monitor your whole IT service chain with one integrated, automated solution.</span></span> <span data-ttu-id="a5435-120">Vous identifierez facilement les causes des problèmes de performances et de disponibilité, et vous les corrigerez plus rapidement, ce qui réduira les effets et les coûts.</span><span class="sxs-lookup"><span data-stu-id="a5435-120">You'll easily identify the root causes of performance and availability issues, and resolve them faster which reduces effects and costs.</span></span> <span data-ttu-id="a5435-121">Les principaux avantages sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="a5435-121">Key benefits include the following:</span></span>

  - <span data-ttu-id="a5435-122">Une gestion avancée et facile à utiliser permet de fournir une valeur commerciale stratégique au lieu de trier et de filtrer manuellement les alertes.</span><span class="sxs-lookup"><span data-stu-id="a5435-122">Advanced, easy-to-use management   Focus on delivering strategic business value instead of manually sorting and filtering confusing alerts.</span></span>

  - <span data-ttu-id="a5435-123">**Une résolution**   plus rapide permet de résoudre les problèmes informatiques et de répondre aux besoins de l’entreprise plus rapidement, en réduisant l’impact et les coûts.</span><span class="sxs-lookup"><span data-stu-id="a5435-123">**Faster resolution**   Solve IT issues and respond to business needs faster, reducing effect and cost.</span></span>

  - <span data-ttu-id="a5435-124">**Les opérations**   rationalisées évitent la complexité informatique en combinant plusieurs outils de gestion, applications et terminaux.</span><span class="sxs-lookup"><span data-stu-id="a5435-124">**Streamlined operations**   Avoid IT complexity by combining multiple management tools, applications, and terminals.</span></span>

<span data-ttu-id="a5435-125">Des informations supplémentaires sont disponibles ici :</span><span class="sxs-lookup"><span data-stu-id="a5435-125">More information can be found here:</span></span>

[<span data-ttu-id="a5435-126">Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="a5435-126">Microsoft System Center Operations Manager</span></span>](http://go.microsoft.com/fwlink/p/?linkid=243651)

[<span data-ttu-id="a5435-127">Solutions pour Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="a5435-127">Solutions for Microsoft System Center Operations Manager</span></span>](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a><span data-ttu-id="a5435-128">Solutions tierces</span><span class="sxs-lookup"><span data-stu-id="a5435-128">Third-Party Solutions</span></span>

<span data-ttu-id="a5435-129">**HP Network Management Center (précédemment appelé HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) offre une gestion intégrée des pannes et des performances pour améliorer la disponibilité et les performances du réseau.</span><span class="sxs-lookup"><span data-stu-id="a5435-129">**HP Network Management Center (previously known as HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) provides integrated fault and performance management to improve network availability and performance.</span></span> <span data-ttu-id="a5435-130">Network Management Center fait partie de la solution HP Automated Network Management qui unifie les pannes, les performances, la configuration et la gestion des modifications.</span><span class="sxs-lookup"><span data-stu-id="a5435-130">Network Management Center is part of the HP automated network management solution that unifies fault, performance, configuration, and change management.</span></span>

<span data-ttu-id="a5435-131">**Produits d’automatisation et de gestion réseau Cisco**   pour l’entreprise, Cisco dispose de plusieurs produits de gestion disponibles, dont la solution de gestion LAN CiscoWorks et le module Cisco Network Analysis, afin d’améliorer l’efficacité opérationnelle et de réduire les temps morts du réseau.</span><span class="sxs-lookup"><span data-stu-id="a5435-131">**Cisco Network Management and Automation products**   For the Enterprise, Cisco has several management products available including CiscoWorks LAN Management Solution and Cisco Network Analysis Module, to help improve operational efficiency and reduce network downtime.</span></span> <span data-ttu-id="a5435-132">Pour plus d’informations sur ces produits, reportez-vous [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html)au site Web de Cisco à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="a5435-132">For additional data on these products, refer to the Cisco website at [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html).</span></span>

<span data-ttu-id="a5435-133">Le protocole SNMP (simple Network Management Protocol) (SNMP) est une norme de gestion réseau qui définit une stratégie de gestion des réseaux TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="a5435-133">Simple Network Management Protocol (SNMP)   Simple Network Management Protocol (SNMP) is a network management standard that defines a strategy for managing TCP/IP networks.</span></span> <span data-ttu-id="a5435-134">SNMP vous permet de capturer des informations de configuration et d’État relatives au réseau, et d’envoyer les informations à un ordinateur désigné pour la surveillance des événements.</span><span class="sxs-lookup"><span data-stu-id="a5435-134">SNMP enables you to capture configuration and status information about the network, and send the information to a designated computer for event monitoring.</span></span> <span data-ttu-id="a5435-135">Ce protocole de gestion de réseau basé sur des normes utilise une architecture distribuée qui inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a5435-135">This standards based network management protocol uses a distributed architecture that includes the following:</span></span>

  - <span data-ttu-id="a5435-136">Plusieurs nœuds gérés, chacun avec une entité SNMP appelée agent qui fournit l’accès à distance à l’instrumentation de gestion.</span><span class="sxs-lookup"><span data-stu-id="a5435-136">Multiple managed nodes, each with an SNMP entity called an agent which provides remote access to management instrumentation.</span></span>

  - <span data-ttu-id="a5435-137">Au moins une entité SNMP appelée gestionnaire qui exécute les applications de gestion pour surveiller et contrôler les éléments gérés.</span><span class="sxs-lookup"><span data-stu-id="a5435-137">At least one SNMP entity known as a manager which runs management applications to monitor and control managed elements.</span></span> <span data-ttu-id="a5435-138">Les éléments gérés sont des périphériques tels que des hôtes, des routeurs et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="a5435-138">Managed elements are devices such as hosts, routers, and so on.</span></span> <span data-ttu-id="a5435-139">Ils sont surveillés et contrôlés en accédant à leurs informations de gestion.</span><span class="sxs-lookup"><span data-stu-id="a5435-139">They are monitored and controlled by accessing their management information.</span></span>

  - <span data-ttu-id="a5435-140">Un protocole de gestion, SNMP, est utilisé pour communiquer les informations de gestion entre les stations de gestion et les agents.</span><span class="sxs-lookup"><span data-stu-id="a5435-140">A management protocol, SNMP, is used to communicate management information between the management stations and agents.</span></span> <span data-ttu-id="a5435-141">Les informations de gestion font référence à une collection d’objets gérés qui résident dans une banque d’informations virtuelle appelée MIB (Management Information base).</span><span class="sxs-lookup"><span data-stu-id="a5435-141">Management information refers to a collection of managed objects that live in a virtual information store called a Management Information Base (MIB).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a5435-142">Des exemples de solutions de surveillance réseau tierces sont fournis ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="a5435-142">Examples of third-party network monitoring solutions are provided above.</span></span> <span data-ttu-id="a5435-143">Cette liste n’est pas définitive et Microsoft ne privilégie pas une solution de fournisseur spécifique.</span><span class="sxs-lookup"><span data-stu-id="a5435-143">This list is not definitive and Microsoft does not favor any specific vendor solution.</span></span> <span data-ttu-id="a5435-144">Consultez un fournisseur de services réseau et ou votre fournisseur de technologies pour déterminer la meilleure solution de surveillance réseau pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a5435-144">Consult with a network service provider and or your respective technology provider to determine the best network monitoring solution for your organization.</span></span>



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a><span data-ttu-id="a5435-145">Outils de surveillance des performances du réseau d’un serveur individuel</span><span class="sxs-lookup"><span data-stu-id="a5435-145">Tools for Monitoring Individual Server Network Performance</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="a5435-146">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="a5435-146">System Center Operations Manager 2012</span></span>

<span data-ttu-id="a5435-147">System Center Operations Manager 2012 permettrait aux administrateurs d’afficher les performances réseau de chaque serveur via le pack d’administration Windows Server 2012 : le pack d’administration du système d’exploitation Windows Server inclut un pack d’administration « performances ». Cela permettra aux administrateurs de surveiller les performances des cartes réseau et l’intégrité de la carte.</span><span class="sxs-lookup"><span data-stu-id="a5435-147">System Center Operations Manager 2012 would allow administrators to view network performance of individual servers through the Windows Server 2012 Management Pack: The Windows Server operating system management pack includes a "Performance" management pack that would allow administrators to monitor Network Adapter performance and adapter health.</span></span>

</div>

<div>

## <a name="windows-network-monitor"></a><span data-ttu-id="a5435-148">Moniteur réseau Windows</span><span class="sxs-lookup"><span data-stu-id="a5435-148">Windows Network Monitor</span></span>

<span data-ttu-id="a5435-149">Collecte, affiche, analyse l’utilisation des ressources sur un serveur et mesure le trafic réseau.</span><span class="sxs-lookup"><span data-stu-id="a5435-149">Collects, displays, analyzes resource usage on a server, and measures network traffic.</span></span> <span data-ttu-id="a5435-150">Le moniteur réseau surveille exclusivement l’activité réseau.</span><span class="sxs-lookup"><span data-stu-id="a5435-150">Network Monitor exclusively monitors network activity.</span></span> <span data-ttu-id="a5435-151">En capturant et en analysant les données réseau, et en utilisant ces données avec les journaux de performances, vous pouvez déterminer l’utilisation du réseau, identifier les problèmes réseau et prévoir les futurs besoins en matière de réseau.</span><span class="sxs-lookup"><span data-stu-id="a5435-151">By capturing and analyzing network data, and using this data with performance logs, you can determine the network usage, identify network issues, and forecast future network needs.</span></span>

<span data-ttu-id="a5435-152">Pour plus d’informations sur le moniteur réseau 3,4 et sur l’installation et la configuration du moniteur réseau, ainsi que sur la capture et l’analyse des données, consultez cette session : Moniteur réseau 3,3.</span><span class="sxs-lookup"><span data-stu-id="a5435-152">For more information about Network Monitor 3.4, and to learn how to install and configure Network Monitor and capture and analyze data, review this session: Network Monitor 3.3 Overview.</span></span> <span data-ttu-id="a5435-153">Consultez également le [blog du moniteur réseau](http://blogs.technet.com/b/netmon/).</span><span class="sxs-lookup"><span data-stu-id="a5435-153">Also, review the [Network Monitor blog](http://blogs.technet.com/b/netmon/).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


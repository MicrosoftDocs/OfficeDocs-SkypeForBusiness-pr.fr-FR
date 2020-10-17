---
title: 'Lync Server 2013 : gestion de la configuration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de390f21c76a9636fc9ba2d6a7d3ee017681b6ba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507831"
---
# <a name="configuration-management-in-lync-server-2013"></a><span data-ttu-id="8412d-102">Gestion de la configuration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8412d-102">Configuration management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8412d-103">_**Dernière modification de la rubrique :** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="8412d-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="8412d-104">La gestion de la configuration est le processus d’enregistrement et de suivi des ressources matérielles et logicielles, ainsi que des informations de configuration système.</span><span class="sxs-lookup"><span data-stu-id="8412d-104">Configuration management is the process of recording and tracking hardware and software assets and system configuration information.</span></span> <span data-ttu-id="8412d-105">Il est généralement utilisé pour effectuer le suivi des licences logicielles, maintenir une version matérielle et logicielle standard pour les ordinateurs clients et les serveurs, et définir des normes d’attribution de noms pour les nouveaux ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="8412d-105">It is generally used to track software licenses, maintain a standard hardware and software build for client computers and servers, and define naming standards for new computers.</span></span> <span data-ttu-id="8412d-106">La gestion de la configuration couvre généralement les catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="8412d-106">Configuration management generally covers the following categories:</span></span>

  - <span data-ttu-id="8412d-107">**Matériel**     Cette catégorie effectue le suivi des éléments d’équipement dont l’organisation informatique est propriétaire, où se trouve l’équipement et qui utilise l’équipement.</span><span class="sxs-lookup"><span data-stu-id="8412d-107">**Hardware**   This category tracks the pieces of equipment that the IT organization owns, where equipment is located, and who uses equipment.</span></span> <span data-ttu-id="8412d-108">Ces informations permettent à une organisation de planifier et de budgétiser les mises à niveau, de tenir des builds matérielles standard, de générer des rapports sur la valeur des ressources informatiques à des fins de comptabilité et d’empêcher le vol.</span><span class="sxs-lookup"><span data-stu-id="8412d-108">This information enables an organization to plan and budget for upgrades, maintain standard hardware builds, report on the value of IT assets for accounting purposes, and help prevent theft.</span></span>

  - <span data-ttu-id="8412d-109">**Logiciels**     Cette catégorie effectue le suivi des logiciels installés sur chaque ordinateur, des numéros de version et de l’emplacement de stockage des licences.</span><span class="sxs-lookup"><span data-stu-id="8412d-109">**Software**   This category tracks software that is installed on each computer, the version numbers, and where the licenses are held.</span></span> <span data-ttu-id="8412d-110">Ces informations permettent de planifier les mises à niveau, de s’assurer que les logiciels sont sous licence et de détecter la présence de logiciels non autorisés (et sans licence).</span><span class="sxs-lookup"><span data-stu-id="8412d-110">This information helps plan upgrades, to ensure that software is licensed, and detect the presence of unauthorized (and unlicensed) software.</span></span>

  - <span data-ttu-id="8412d-111">**Builds standard**     Cette catégorie effectue le suivi de la version standard actuelle pour les serveurs et les ordinateurs clients, et indique si les ordinateurs clients et les serveurs satisfont à cette norme.</span><span class="sxs-lookup"><span data-stu-id="8412d-111">**Standard Builds**   This category tracks the current standard build for the client computers and servers and whether the client computers and servers meet this standard.</span></span> <span data-ttu-id="8412d-112">La définition et l’application des builds standard permettent au personnel de prendre en charge, car le personnel est tenu de ne conserver qu’un nombre limité de versions de chaque logiciel.</span><span class="sxs-lookup"><span data-stu-id="8412d-112">Defining and enforcing standard builds helps support staff because the staff is required to maintain only a limited number of versions of each piece of software.</span></span>

  - <span data-ttu-id="8412d-113">**Mises à jour cumulatives et correctifs**     Cette catégorie effectue le suivi des service packs testés et approuvés pour une utilisation et des ordinateurs mis à jour.</span><span class="sxs-lookup"><span data-stu-id="8412d-113">**Cumulative Updates and Hotfixes**   This category tracks which service packs are tested and approved for use and which computers are up to date.</span></span> <span data-ttu-id="8412d-114">Ces informations sont importantes pour réduire le risque de compromission des ordinateurs et pour détecter les utilisateurs qui ont installé des mises à jour non approuvées.</span><span class="sxs-lookup"><span data-stu-id="8412d-114">This information is important to reduce the risk of computers being compromised and to detect users who have installed unapproved updates.</span></span>

  - <span data-ttu-id="8412d-115">**Informations sur**     la configuration du système Cette catégorie effectue le suivi de la fonction d’un système, de l’interaction entre les éléments du système et des processus qui dépendent d’un système qui s’exécute sans problème.</span><span class="sxs-lookup"><span data-stu-id="8412d-115">**System Configuration Information**   This category tracks the function of a system, the interaction between system elements, and the processes that depend on a system that is running smoothly.</span></span> <span data-ttu-id="8412d-116">Par exemple, un serveur proxy tiers peut être configuré sur un seul serveur.</span><span class="sxs-lookup"><span data-stu-id="8412d-116">For example, third-party proxy server may be configured on a single server.</span></span> <span data-ttu-id="8412d-117">La dépendance du serveur proxy sur ce serveur doit être comprise et les plans d’intervention peuvent être nécessaires en cas de défaillance.</span><span class="sxs-lookup"><span data-stu-id="8412d-117">The proxy server’s dependence on this server should be understood and contingency plans may be required if there is a failure.</span></span> <span data-ttu-id="8412d-118">Si le serveur proxy peut être configuré pour communiquer également avec un autre serveur frontal, les dépendances et plans d’urgence changent probablement.</span><span class="sxs-lookup"><span data-stu-id="8412d-118">If the proxy server can be configured to also communicate with another front-end server, dependencies and contingency plans will probably change.</span></span>

<div>

## <a name="implementing-configuration-management"></a><span data-ttu-id="8412d-119">Implémentation de la gestion de la configuration</span><span class="sxs-lookup"><span data-stu-id="8412d-119">Implementing configuration management</span></span>

<span data-ttu-id="8412d-120">Une fois que vous avez déterminé les éléments nécessaires à la gestion, implémentez la gestion de la configuration en recueillant les données et les données de rapports.</span><span class="sxs-lookup"><span data-stu-id="8412d-120">After you determine what items need managing, implement configuration management by collecting data and reporting data.</span></span> <span data-ttu-id="8412d-121">L’approche la plus simple pour les petites organisations est de collecter les données manuellement (nombre et modèle d’ordinateurs clients, de systèmes d’exploitation, de logiciels installés) et de les enregistrer dans un document Office Word ou Office Excel.</span><span class="sxs-lookup"><span data-stu-id="8412d-121">The simplest approach for small organizations is to collect data manually (number and model of client computers, operating system, installed software) and save it in an Office Word or Office Excel document.</span></span> <span data-ttu-id="8412d-122">Pour les systèmes plus volumineux, plus complexes et en constante évolution, la découverte des biens et la collecte d’informations détaillées doivent être automatisées.</span><span class="sxs-lookup"><span data-stu-id="8412d-122">For larger, more complex, and constantly changing systems, the discovery of assets and collection of detailed information must be automated.</span></span> <span data-ttu-id="8412d-123">Déterminez les informations pertinentes pour votre organisation et enregistrez-la dans une base de données.</span><span class="sxs-lookup"><span data-stu-id="8412d-123">Decide what information is relevant to your organization and record it in a database.</span></span>

<span data-ttu-id="8412d-124">La base de données de gestion de la configuration est un outil utile pour le personnel de support et la gestion dans les domaines suivants :</span><span class="sxs-lookup"><span data-stu-id="8412d-124">The configuration management database is a useful tool for support staff and management in the following areas:</span></span>

  - <span data-ttu-id="8412d-125">**Audits**     de sécurité La base de données vous permet d’identifier les serveurs qui exécutent Lync Server et les systèmes d’ordinateurs clients sur lesquels des correctifs logiciels doivent être appliqués ou qui ont manqué l’installation d’un service pack ou les dernières mises à jour antivirus.</span><span class="sxs-lookup"><span data-stu-id="8412d-125">**Security Audits**   The database enables you to identify servers that are running Lync Server and client computer systems that must have hotfixes applied or that have missed the installation of a service pack or the latest antivirus updates.</span></span>

  - <span data-ttu-id="8412d-126">**Installation**     de logiciels L’identification des versions du logiciel client et leur suivi aideront les administrateurs à planifier les mises à jour de version et les nouvelles installations, ainsi qu’en aidant la documentation et la conformité des licences.</span><span class="sxs-lookup"><span data-stu-id="8412d-126">**Software Installation**   Identifying client software versions and tracking them will aid administrators in planning version updates and new installs and also by helping with licensing documentation and compliance.</span></span>

  - <span data-ttu-id="8412d-127">**Informations**     de configuration Si vous conservez une liste à jour de tous les paramètres qui ont été modifiés par rapport à leur valeur par défaut, vous pourrez résoudre les problèmes rapidement et plus efficacement.</span><span class="sxs-lookup"><span data-stu-id="8412d-127">**Configuration Information**   If you maintain an up-to-date list of all settings that were changed from their default, then you'll be able to troubleshoot issues quickly and more effectively.</span></span>

  - <span data-ttu-id="8412d-128">**Planification des mises à niveau**     Si un examen de capacité révèle que de l’espace de stockage supplémentaire est requis sur vos serveurs de bases de données Lync, il est important de savoir si chaque serveur possède un contrôleur RAID interne.</span><span class="sxs-lookup"><span data-stu-id="8412d-128">**Planning Upgrades**   If a capacity review reveals that additional storage space is required on your Lync database servers, it’s important to know whether each server has an internal RAID controller.</span></span> <span data-ttu-id="8412d-129">Si c’est le cas, est-ce le même modèle ?</span><span class="sxs-lookup"><span data-stu-id="8412d-129">If they do, then are they the same model?</span></span> <span data-ttu-id="8412d-130">Ont-ils le même nombre de disques installés ?</span><span class="sxs-lookup"><span data-stu-id="8412d-130">Do they have the same number of disks installed?</span></span> <span data-ttu-id="8412d-131">La base de données de gestion de la configuration indique le type de disque qui peut être installé, le numéro et le chemin de mise à niveau dans chaque cas.</span><span class="sxs-lookup"><span data-stu-id="8412d-131">The configuration management database will indicate the type of disk that can be installed, the number, and the upgrade path in each case.</span></span>

</div>

<div>

## <a name="tools-used-for-configuration-management"></a><span data-ttu-id="8412d-132">Outils utilisés pour la gestion de la configuration</span><span class="sxs-lookup"><span data-stu-id="8412d-132">Tools used for configuration management</span></span>

<span data-ttu-id="8412d-133">Il existe de nombreux outils permettant de découvrir, d’auditer et de présenter des biens.</span><span class="sxs-lookup"><span data-stu-id="8412d-133">There are many tools to discover, audit, and report assets.</span></span> <span data-ttu-id="8412d-134">Certains de ces outils sont présentés dans cette section.</span><span class="sxs-lookup"><span data-stu-id="8412d-134">Some of these tools are discussed in this section.</span></span>

  - <span data-ttu-id="8412d-135">**Scripts**     automatisés Vous pouvez écrire des scripts simples pour signaler des éléments tels que le système d’exploitation, le niveau de Service Pack et indiquer si le logiciel existe sur un ensemble spécifique d’ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="8412d-135">**Automated Scripts**   You can write simple scripts to report items such as the operating system, service pack level, and whether software exists on a specific set of computers.</span></span> <span data-ttu-id="8412d-136">Vous pouvez écrire ces scripts aux exigences d’une organisation.</span><span class="sxs-lookup"><span data-stu-id="8412d-136">You can write these scripts to an organization’s exact requirements.</span></span> <span data-ttu-id="8412d-137">Toutefois, le nombre requis de scripts et leur complexité peuvent rendre les scripts chers à créer et à gérer.</span><span class="sxs-lookup"><span data-stu-id="8412d-137">However, the required number of scripts and their complexity can make scripts expensive to create and maintain.</span></span>

  - <span data-ttu-id="8412d-138">**Outils**     automatisés En fonction de la taille de votre entreprise et des besoins de votre organisation, vous pouvez envisager d’utiliser des outils automatisés.</span><span class="sxs-lookup"><span data-stu-id="8412d-138">**Automated Tools**   Depending on the size of your business and your organizational needs, you may want to consider using automated tools.</span></span> <span data-ttu-id="8412d-139">Des outils tels que le gestionnaire de configuration de point de terminaison Microsoft incorporent des modèles de rapport standard (tels que le niveau de Service Pack) et vous permettent également de créer des rapports personnalisés, par exemple, pour une application personnalisée.</span><span class="sxs-lookup"><span data-stu-id="8412d-139">Tools such as Microsoft Endpoint Configuration Manager incorporate standard report templates (such as service pack level) and also enable you to create customized reports, for example, for a custom application.</span></span> <span data-ttu-id="8412d-140">Le gestionnaire de configuration de point de terminaison Microsoft peut également être utilisé pour signaler les configurations matérielles et logicielles.</span><span class="sxs-lookup"><span data-stu-id="8412d-140">The Microsoft Endpoint Configuration Manager can also be used to report on hardware and software configurations.</span></span>

</div>

<div>

## <a name="relationship-with-change-management"></a><span data-ttu-id="8412d-141">Relation avec la gestion des modifications</span><span class="sxs-lookup"><span data-stu-id="8412d-141">Relationship with change management</span></span>

<span data-ttu-id="8412d-142">La gestion de la configuration est étroitement liée à la gestion des modifications.</span><span class="sxs-lookup"><span data-stu-id="8412d-142">Configuration management is closely related to change management.</span></span> <span data-ttu-id="8412d-143">La gestion de la configuration identifie le besoin de modification et identifie et enregistre qu’une modification a eu lieu.</span><span class="sxs-lookup"><span data-stu-id="8412d-143">Configuration management identifies the need for change and identifies and records that a change has occurred.</span></span> <span data-ttu-id="8412d-144">Par exemple, la base de données de gestion de la configuration peut être utilisée pour identifier les serveurs qui nécessitent un correctif.</span><span class="sxs-lookup"><span data-stu-id="8412d-144">For example, the configuration management database can be used to identify servers that require a hotfix.</span></span> <span data-ttu-id="8412d-145">Gestion des modifications définit ensuite le processus d’application du correctif.</span><span class="sxs-lookup"><span data-stu-id="8412d-145">Change management then defines the process for applying the hotfix.</span></span>

<span data-ttu-id="8412d-146">À l’inverse, si une nouvelle mise à jour cumulative est déployée, le processus de gestion des modifications doit fournir ces informations au système de gestion de la configuration.</span><span class="sxs-lookup"><span data-stu-id="8412d-146">Conversely, if a new cumulative update is rolled out, the change management process should supply this information to the configuration management system.</span></span> <span data-ttu-id="8412d-147">Les outils de gestion de la configuration devront probablement être configurés pour identifier le nouveau logiciel afin qu’ils puissent découvrir et suivre où et quand le logiciel est déployé.</span><span class="sxs-lookup"><span data-stu-id="8412d-147">The configuration management tools will probably need to be configured to identify the new software so that they can discover and track where and when the software is deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


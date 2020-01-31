---
title: 'Lync Server 2013 : gestion de la configuration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb652485b03bcaee5e63bc4fc23d25fd5df958bd
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-management-in-lync-server-2013"></a><span data-ttu-id="c9752-102">Gestion de la configuration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9752-102">Configuration management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9752-103">_**Dernière modification de la rubrique :** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="c9752-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="c9752-104">La gestion de la configuration est le processus d’enregistrement et de suivi des ressources matérielles et logicielles, ainsi que des informations sur la configuration du système.</span><span class="sxs-lookup"><span data-stu-id="c9752-104">Configuration management is the process of recording and tracking hardware and software assets and system configuration information.</span></span> <span data-ttu-id="c9752-105">Il est généralement utilisé pour effectuer le suivi des licences logicielles, de mettre à jour une build matérielle et logicielle standard pour les ordinateurs et serveurs clients et de définir des normes d’appellation pour les nouveaux ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="c9752-105">It is generally used to track software licenses, maintain a standard hardware and software build for client computers and servers, and define naming standards for new computers.</span></span> <span data-ttu-id="c9752-106">La gestion de la configuration couvre généralement les catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="c9752-106">Configuration management generally covers the following categories:</span></span>

  - <span data-ttu-id="c9752-107">**Matériel**   cette catégorie effectue le suivi des éléments d’un équipement dont dispose l’organisation informatique, l’emplacement de l’équipement et qui utilise des équipements.</span><span class="sxs-lookup"><span data-stu-id="c9752-107">**Hardware**   This category tracks the pieces of equipment that the IT organization owns, where equipment is located, and who uses equipment.</span></span> <span data-ttu-id="c9752-108">Grâce à ces informations, une organisation est en mesure de planifier et de budgétiser les mises à jour, de mettre à jour les builds matérielles standard, de signaler la valeur des ressources informatiques à des fins comptables et d’éviter le vol.</span><span class="sxs-lookup"><span data-stu-id="c9752-108">This information enables an organization to plan and budget for upgrades, maintain standard hardware builds, report on the value of IT assets for accounting purposes, and help prevent theft.</span></span>

  - <span data-ttu-id="c9752-109">**Logiciel**   cette catégorie effectue le suivi des logiciels installés sur chaque ordinateur, des numéros de version et de l’emplacement des licences.</span><span class="sxs-lookup"><span data-stu-id="c9752-109">**Software**   This category tracks software that is installed on each computer, the version numbers, and where the licenses are held.</span></span> <span data-ttu-id="c9752-110">Ces informations permettent de planifier les mises à niveau, de garantir que le logiciel est concédé sous licence et de détecter la présence de logiciels non autorisés (et sans licence).</span><span class="sxs-lookup"><span data-stu-id="c9752-110">This information helps plan upgrades, to ensure that software is licensed, and detect the presence of unauthorized (and unlicensed) software.</span></span>

  - <span data-ttu-id="c9752-111">**Builds standard cette**   catégorie effectue le suivi de la build standard actuelle pour les ordinateurs et serveurs clients, et si les ordinateurs et serveurs clients répondent à cette norme.</span><span class="sxs-lookup"><span data-stu-id="c9752-111">**Standard Builds**   This category tracks the current standard build for the client computers and servers and whether the client computers and servers meet this standard.</span></span> <span data-ttu-id="c9752-112">La définition et l’application des builds standard permettent de soutenir le personnel, car le personnel est tenu de ne conserver qu’un nombre limité de versions de chaque logiciel.</span><span class="sxs-lookup"><span data-stu-id="c9752-112">Defining and enforcing standard builds helps support staff because the staff is required to maintain only a limited number of versions of each piece of software.</span></span>

  - <span data-ttu-id="c9752-113">**Mises à jour et Hotfix cumulés**   cette catégorie suit les service packs testés et approuvés pour une utilisation et les ordinateurs à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="c9752-113">**Cumulative Updates and Hotfixes**   This category tracks which service packs are tested and approved for use and which computers are up to date.</span></span> <span data-ttu-id="c9752-114">Ces informations sont importantes pour réduire le risque d’intrusion sur des ordinateurs et de détecter les utilisateurs qui ont installé des mises à jour non approuvées.</span><span class="sxs-lookup"><span data-stu-id="c9752-114">This information is important to reduce the risk of computers being compromised and to detect users who have installed unapproved updates.</span></span>

  - <span data-ttu-id="c9752-115">**Informations sur**   la configuration du système cette catégorie effectue le suivi de la fonction d’un système, l’interaction entre les éléments système et les processus qui dépendent d’un système qui s’exécute de façon fluide.</span><span class="sxs-lookup"><span data-stu-id="c9752-115">**System Configuration Information**   This category tracks the function of a system, the interaction between system elements, and the processes that depend on a system that is running smoothly.</span></span> <span data-ttu-id="c9752-116">Par exemple, un serveur proxy tiers est configuré sur un serveur unique.</span><span class="sxs-lookup"><span data-stu-id="c9752-116">For example, third-party proxy server may be configured on a single server.</span></span> <span data-ttu-id="c9752-117">La dépendance du serveur proxy sur ce serveur doit être comprise et les plans d’urgence peuvent être requis en cas d’échec.</span><span class="sxs-lookup"><span data-stu-id="c9752-117">The proxy server’s dependence on this server should be understood and contingency plans may be required if there is a failure.</span></span> <span data-ttu-id="c9752-118">Si le serveur proxy peut être configuré pour communiquer avec un autre serveur frontal, les dépendances et les plans d’urgence seront probablement modifiés.</span><span class="sxs-lookup"><span data-stu-id="c9752-118">If the proxy server can be configured to also communicate with another front-end server, dependencies and contingency plans will probably change.</span></span>

<div>

## <a name="implementing-configuration-management"></a><span data-ttu-id="c9752-119">Mise en œuvre de la gestion de la configuration</span><span class="sxs-lookup"><span data-stu-id="c9752-119">Implementing configuration management</span></span>

<span data-ttu-id="c9752-120">Lorsque vous déterminez les éléments qui doivent être gérés, implémentez la gestion de la configuration en collectant des données et en rapportant des données.</span><span class="sxs-lookup"><span data-stu-id="c9752-120">After you determine what items need managing, implement configuration management by collecting data and reporting data.</span></span> <span data-ttu-id="c9752-121">Pour les petites entreprises, l’approche la plus simple consiste à collecter les données manuellement (nombre et modèle d’ordinateurs clients, de systèmes d’exploitation, de logiciels installés) et de les enregistrer dans un document Office Word ou Office Excel.</span><span class="sxs-lookup"><span data-stu-id="c9752-121">The simplest approach for small organizations is to collect data manually (number and model of client computers, operating system, installed software) and save it in an Office Word or Office Excel document.</span></span> <span data-ttu-id="c9752-122">Pour les systèmes plus volumineux, plus complexes et en perpétuelle évolution, la découverte des ressources et la collecte des informations détaillées doit être automatisée.</span><span class="sxs-lookup"><span data-stu-id="c9752-122">For larger, more complex, and constantly changing systems, the discovery of assets and collection of detailed information must be automated.</span></span> <span data-ttu-id="c9752-123">Déterminez les informations pertinentes pour votre organisation et enregistrez-les dans une base de données.</span><span class="sxs-lookup"><span data-stu-id="c9752-123">Decide what information is relevant to your organization and record it in a database.</span></span>

<span data-ttu-id="c9752-124">La base de données de gestion de la configuration est un outil utile pour le personnel d’assistance et la gestion des domaines suivants :</span><span class="sxs-lookup"><span data-stu-id="c9752-124">The configuration management database is a useful tool for support staff and management in the following areas:</span></span>

  - <span data-ttu-id="c9752-125">**Audits de sécurité**   la base de données vous permet d’identifier les serveurs exécutant Lync Server et les systèmes d’ordinateur client pour lesquels des correctifs ont été appliqués ou qui n’ont pas pu installer un service pack ou les dernières mises à jour antivirus.</span><span class="sxs-lookup"><span data-stu-id="c9752-125">**Security Audits**   The database enables you to identify servers that are running Lync Server and client computer systems that must have hotfixes applied or that have missed the installation of a service pack or the latest antivirus updates.</span></span>

  - <span data-ttu-id="c9752-126">**L’installation**   logicielle identifiant les versions des logiciels clients et en assurer le suivi permettra aux administrateurs de planifier les mises à jour de la version ainsi que de nouvelles installations, et en vous aidant de la documentation et de la conformité.</span><span class="sxs-lookup"><span data-stu-id="c9752-126">**Software Installation**   Identifying client software versions and tracking them will aid administrators in planning version updates and new installs and also by helping with licensing documentation and compliance.</span></span>

  - <span data-ttu-id="c9752-127">**Informations de configuration**   si vous conservez une liste à jour de tous les paramètres qui ont été modifiés par défaut, vous serez en mesure de résoudre les problèmes de manière rapide et plus efficace.</span><span class="sxs-lookup"><span data-stu-id="c9752-127">**Configuration Information**   If you maintain an up-to-date list of all settings that were changed from their default, then you'll be able to troubleshoot issues quickly and more effectively.</span></span>

  - <span data-ttu-id="c9752-128">**Planification des mises à jour**   si un avis de capacité révèle que de l’espace de stockage supplémentaire est requis sur les serveurs de base de données Lync, il est important de savoir si chaque serveur possède un contrôleur RAID interne.</span><span class="sxs-lookup"><span data-stu-id="c9752-128">**Planning Upgrades**   If a capacity review reveals that additional storage space is required on your Lync database servers, it’s important to know whether each server has an internal RAID controller.</span></span> <span data-ttu-id="c9752-129">Si tel est le cas, sont-ils le même modèle ?</span><span class="sxs-lookup"><span data-stu-id="c9752-129">If they do, then are they the same model?</span></span> <span data-ttu-id="c9752-130">Est-ce que le nombre de disques est déjà installé ?</span><span class="sxs-lookup"><span data-stu-id="c9752-130">Do they have the same number of disks installed?</span></span> <span data-ttu-id="c9752-131">La base de données de gestion de la configuration indique le type de disque qui peut être installé, le numéro et le chemin de mise à niveau dans chaque cas.</span><span class="sxs-lookup"><span data-stu-id="c9752-131">The configuration management database will indicate the type of disk that can be installed, the number, and the upgrade path in each case.</span></span>

</div>

<div>

## <a name="tools-used-for-configuration-management"></a><span data-ttu-id="c9752-132">Outils utilisés pour la gestion de la configuration</span><span class="sxs-lookup"><span data-stu-id="c9752-132">Tools used for configuration management</span></span>

<span data-ttu-id="c9752-133">De nombreux outils permettent de détecter, d’auditer et de signaler des ressources.</span><span class="sxs-lookup"><span data-stu-id="c9752-133">There are many tools to discover, audit, and report assets.</span></span> <span data-ttu-id="c9752-134">Certains de ces outils sont abordés dans cette section.</span><span class="sxs-lookup"><span data-stu-id="c9752-134">Some of these tools are discussed in this section.</span></span>

  - <span data-ttu-id="c9752-135">**Scripts automatisés**   vous pouvez écrire des scripts simples pour signaler des éléments tels que le système d’exploitation, le niveau du Service Pack et la présence de logiciels sur un ensemble spécifique d’ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="c9752-135">**Automated Scripts**   You can write simple scripts to report items such as the operating system, service pack level, and whether software exists on a specific set of computers.</span></span> <span data-ttu-id="c9752-136">Vous pouvez écrire ces scripts dans la configuration requise exacte d’une organisation.</span><span class="sxs-lookup"><span data-stu-id="c9752-136">You can write these scripts to an organization’s exact requirements.</span></span> <span data-ttu-id="c9752-137">Toutefois, le nombre requis de scripts et leur complexité peuvent compliquer la création et la gestion des scripts.</span><span class="sxs-lookup"><span data-stu-id="c9752-137">However, the required number of scripts and their complexity can make scripts expensive to create and maintain.</span></span>

  - <span data-ttu-id="c9752-138">**Outils automatisés**   en fonction de la taille de votre entreprise et des besoins de votre organisation, vous pouvez envisager d’utiliser des outils automatisés.</span><span class="sxs-lookup"><span data-stu-id="c9752-138">**Automated Tools**   Depending on the size of your business and your organizational needs, you may want to consider using automated tools.</span></span> <span data-ttu-id="c9752-139">Les outils tels que Microsoft Endpoint Configuration Manager contiennent des modèles de rapports standard (par exemple, le niveau de Service Pack) et vous permettent également de créer des rapports personnalisés, par exemple pour une application personnalisée.</span><span class="sxs-lookup"><span data-stu-id="c9752-139">Tools such as Microsoft Endpoint Configuration Manager incorporate standard report templates (such as service pack level) and also enable you to create customized reports, for example, for a custom application.</span></span> <span data-ttu-id="c9752-140">Le gestionnaire de configuration de point de terminaison Microsoft peut également être utilisé pour signaler des configurations matérielle et logicielle.</span><span class="sxs-lookup"><span data-stu-id="c9752-140">The Microsoft Endpoint Configuration Manager can also be used to report on hardware and software configurations.</span></span>

</div>

<div>

## <a name="relationship-with-change-management"></a><span data-ttu-id="c9752-141">Relation avec la gestion des modifications</span><span class="sxs-lookup"><span data-stu-id="c9752-141">Relationship with change management</span></span>

<span data-ttu-id="c9752-142">La gestion de la configuration est étroitement liée à la gestion des modifications.</span><span class="sxs-lookup"><span data-stu-id="c9752-142">Configuration management is closely related to change management.</span></span> <span data-ttu-id="c9752-143">La gestion de la configuration identifie le besoin de modifier et d’identifier les modifications apportées aux enregistrements.</span><span class="sxs-lookup"><span data-stu-id="c9752-143">Configuration management identifies the need for change and identifies and records that a change has occurred.</span></span> <span data-ttu-id="c9752-144">Par exemple, la base de données de gestion de la configuration peut être utilisée pour identifier les serveurs qui nécessitent un correctif.</span><span class="sxs-lookup"><span data-stu-id="c9752-144">For example, the configuration management database can be used to identify servers that require a hotfix.</span></span> <span data-ttu-id="c9752-145">La gestion des modifications définit alors le processus d’application du correctif.</span><span class="sxs-lookup"><span data-stu-id="c9752-145">Change management then defines the process for applying the hotfix.</span></span>

<span data-ttu-id="c9752-146">À l’inverse, si une nouvelle mise à jour cumulative est déployée, le processus de gestion des modifications doit fournir ces informations au système de gestion de la configuration.</span><span class="sxs-lookup"><span data-stu-id="c9752-146">Conversely, if a new cumulative update is rolled out, the change management process should supply this information to the configuration management system.</span></span> <span data-ttu-id="c9752-147">Il est probable que les outils de gestion de la configuration doivent être configurés pour identifier le nouveau logiciel de sorte qu’ils puissent détecter et suivre l’emplacement et le moment de déploiement du logiciel.</span><span class="sxs-lookup"><span data-stu-id="c9752-147">The configuration management tools will probably need to be configured to identify the new software so that they can discover and track where and when the software is deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


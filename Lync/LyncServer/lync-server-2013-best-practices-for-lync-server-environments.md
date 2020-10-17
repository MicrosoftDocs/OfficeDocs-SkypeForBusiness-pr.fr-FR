---
title: 'Lync Server 2013 : meilleures pratiques pour les environnements Lync Server'
description: 'Lync Server 2013 : meilleures pratiques pour les environnements Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for Lync Server environments
ms:assetid: b0e45d84-09c8-4d3e-aad0-bc6f34ce233b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720348(v=OCS.15)
ms:contentKeyID: 63969642
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae6c02621bd6506d2a1d379aeaf92b20ce3f7ae1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552210"
---
# <a name="best-practices-for-lync-server-2013-environments"></a><span data-ttu-id="8d58d-103">Meilleures pratiques pour les environnements Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d58d-103">Best practices for Lync Server 2013 environments</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d58d-104">_**Dernière modification de la rubrique :** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="8d58d-104">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="8d58d-105">Les principes généraux suivants doivent être appliqués aux opérations en cours de votre système :</span><span class="sxs-lookup"><span data-stu-id="8d58d-105">The following general principles should be applied to ongoing operations of your system:</span></span>

  - <span data-ttu-id="8d58d-106">**Comprendre et utiliser MOF**     MOF est une collection de meilleures pratiques, de principes et de modèles qui fournissent aux organisations des instructions techniques sur la gestion des ressources informatiques, telles que les opérations quotidiennes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8d58d-106">**Understand and utilize MOF**   MOF is a collection of best practices, principles, and models that provide organizations technical guidance about the management of IT assets, such as daily Lync Server 2013 operations.</span></span> <span data-ttu-id="8d58d-107">Les instructions MOF suivantes peuvent vous aider à améliorer la fiabilité, la disponibilité, la prise en charge et la facilité de gestion des systèmes de production critiques pour les produits Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8d58d-107">Following MOF guidelines can help you achieve mission-critical production system reliability, availability, supportability, and manageability for Microsoft products.</span></span> <span data-ttu-id="8d58d-108">Pour plus d’informations, consultez la rubrique [Microsoft Operations Framework 4,0](https://go.microsoft.com/fwlink/p/?linkid=40939).</span><span class="sxs-lookup"><span data-stu-id="8d58d-108">For more information, see [Microsoft Operations Framework 4.0](https://go.microsoft.com/fwlink/p/?linkid=40939).</span></span>

  - <span data-ttu-id="8d58d-109">**En savoir plus sur les meilleures pratiques pour Lync Server 2013**     Nous vous recommandons d’implémenter des procédures pratiques et éprouvées pour gérer Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8d58d-109">**Learn about best practices for Lync Server 2013**   We recommend that you implement practical and proven procedures to manage Lync Server 2013.</span></span> <span data-ttu-id="8d58d-110">En utilisant les méthodes testées, testées et documentées de gestion des opérations peut être plus efficace que le développement de vos propres méthodes.</span><span class="sxs-lookup"><span data-stu-id="8d58d-110">By using tried, tested, and documented methods of managing operations may be more efficient than developing your own methods.</span></span>

  - <span data-ttu-id="8d58d-111">**Séparer les opérations en processus quotidiens, hebdomadaires et mensuels**     Documentez les tâches opérationnelles requises que vous effectuerez régulièrement.</span><span class="sxs-lookup"><span data-stu-id="8d58d-111">**Separate operations into daily, weekly, and monthly processes**   Document the required operational tasks that you'll regularly perform.</span></span> <span data-ttu-id="8d58d-112">La documentation de la façon dont vous effectuez les tâches permet de s’assurer que vos informations sont conservées en cas de modification de votre environnement opérationnel, par exemple lors du déploiement de nouvelles technologies ou de la modification du personnel.</span><span class="sxs-lookup"><span data-stu-id="8d58d-112">Documenting how you perform tasks helps make sure that your information is preserved when there is a change in your operational environment such as when new technologies are deployed or staff changes occur.</span></span> <span data-ttu-id="8d58d-113">Nous vous recommandons de séparer les tâches opérationnelles en charges de travail gérables où les tâches sont effectuées quotidiennement, toutes les semaines et tous les mois.</span><span class="sxs-lookup"><span data-stu-id="8d58d-113">We recommend that operational tasks be separated into manageable workloads where tasks are performed daily, weekly, and monthly.</span></span> <span data-ttu-id="8d58d-114">Les tâches quotidiennes se concentrent sur le fonctionnement d’un système, et les tâches mensuelles se concentrent davantage sur l’intégrité du système à long terme.</span><span class="sxs-lookup"><span data-stu-id="8d58d-114">Daily tasks would focus efforts on the functioning of a system, and monthly tasks would focus more on ensuring the long-term health of a system.</span></span>
    
    <span data-ttu-id="8d58d-115">Ce document peut être utilisé dans les environnements déployant uniquement les composants de messagerie instantanée/présence (IM/P) ou la messagerie instantanée/P avec voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="8d58d-115">This document can be used in environments deploying only instant messaging/presence (IM/P) components or IM/P with Enterprise Voice.</span></span> <span data-ttu-id="8d58d-116">Lorsque des tâches ou des éléments de liste de contrôle sont spécifiques à voix entreprise, cela est mentionné et, si votre environnement n’inclut pas la fonctionnalité voix entreprise, la partie peut être ignorée.</span><span class="sxs-lookup"><span data-stu-id="8d58d-116">When tasks or checklist items are specific to Enterprise Voice, this is mentioned and if your environment does not include Enterprise Voice the portion may be skipped.</span></span>

  - <span data-ttu-id="8d58d-117">**Déployer les outils requis pour l’exploitation de Lync Server 2013**     De nombreux outils sont disponibles pour vous aider à résoudre des problèmes, automatiser des tâches et surveiller et gérer l’environnement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8d58d-117">**Deploy the tools that are required for operating Lync Server 2013**   Many tools are available to help troubleshoot issues, automate tasks, and help monitor and maintain the Lync Server 2013 environment.</span></span> <span data-ttu-id="8d58d-118">Définissez un ensemble d’outils standard pour votre organisation afin que les tâches effectuées par l’équipe des opérations soient réalisées avec précision, efficacement, de façon cohérente et de manière contrôlée.</span><span class="sxs-lookup"><span data-stu-id="8d58d-118">Define a standard set of tools for your organization so the tasks that are performed by the operations team are performed accurately, efficiently, consistently, and in a controlled manner.</span></span> <span data-ttu-id="8d58d-119">Vous devez également implémenter des processus pour assurer le suivi des incidents et des changements de configuration importants.</span><span class="sxs-lookup"><span data-stu-id="8d58d-119">You should also implement processes to track incidents and major configuration changes.</span></span>

<div>

## <a name="reference"></a><span data-ttu-id="8d58d-120">Référence</span><span class="sxs-lookup"><span data-stu-id="8d58d-120">Reference</span></span>

<span data-ttu-id="8d58d-121">Pour les utilisateurs qui ne sont pas déjà familiarisés avec les notions de base de la gestion de serveur en général, nous proposons une vue d’ensemble des pratiques de gestion de serveur.</span><span class="sxs-lookup"><span data-stu-id="8d58d-121">For the benefit of readers not already familiar with the basics of server management in general, we provide an overview of server management practices.</span></span> <span data-ttu-id="8d58d-122">Les lecteurs déjà familiarisés avec la gestion des serveurs peuvent choisir d’ignorer cette section.</span><span class="sxs-lookup"><span data-stu-id="8d58d-122">Readers already familiar with server management may choose to skip this section.</span></span>

<span data-ttu-id="8d58d-123">Les meilleures pratiques sont des recommandations basées sur les connaissances et l’expérience que les professionnels de l’informatique ont acquis dans de nombreux environnements.</span><span class="sxs-lookup"><span data-stu-id="8d58d-123">Best practices are recommendations that are based on the knowledge and experience that IT professionals have gained across many environments.</span></span> <span data-ttu-id="8d58d-124">Elles fournissent des procédures standard pour les tâches courantes que vos administrateurs Lync Server doivent effectuer quotidiennement et répertorient les outils qu’ils doivent utiliser pour gérer un environnement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8d58d-124">They provide standard procedures for typical tasks that your Lync Server administrators must perform daily, and list the tools that they should use to manage a Lync Server environment.</span></span>

<span data-ttu-id="8d58d-125">Les tâches courantes pour les administrateurs Lync sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="8d58d-125">Typical tasks for Lync administrators include the following:</span></span>

  - <span data-ttu-id="8d58d-126">Gestion de la **capacité et de la disponibilité**     Définir le mode et les éléments à mesurer afin de prévoir les besoins futurs en matière de capacité et de rapport sur la capacité, la fiabilité et la disponibilité de vos systèmes.</span><span class="sxs-lookup"><span data-stu-id="8d58d-126">**Capacity and Availability Management**   Define how and what to measure to predict future capacity requirements and to report about the capacity, reliability, and availability of your systems.</span></span> <span data-ttu-id="8d58d-127">Vous devez vérifier que les serveurs qui exécutent Lync Server sont dimensionnés de façon à gérer la charge sur le système, et que les temps morts non planifiés sont maintenus selon les niveaux définis dans le contrat de niveau de service (SLA).</span><span class="sxs-lookup"><span data-stu-id="8d58d-127">You must verify that servers that are running Lync Server are sized to handle the load on the system, and that unplanned downtime is kept under the levels defined in the service level agreement (SLA).</span></span> <span data-ttu-id="8d58d-128">De plus, vous devez mettre à niveau le matériel pour continuer à respecter les exigences définies.</span><span class="sxs-lookup"><span data-stu-id="8d58d-128">Additionally, you'll have to upgrade hardware to continue to meet the defined requirements.</span></span>

  - <span data-ttu-id="8d58d-129">Gestion **des modifications et gestion**     de la configuration Contrôle de la façon dont les modifications sont apportées aux systèmes informatiques.</span><span class="sxs-lookup"><span data-stu-id="8d58d-129">**Change Management and Configuration Management**   Control how changes are made to IT systems.</span></span> <span data-ttu-id="8d58d-130">Cela doit inclure les tests, les commentaires d’application et les plans d’urgence, la documentation de toutes les modifications et l’approbation de la direction en cas de problèmes.</span><span class="sxs-lookup"><span data-stu-id="8d58d-130">This should include testing, application feedback and contingency plans, documentation of all changes, and approval from management if issues occur.</span></span> <span data-ttu-id="8d58d-131">Conservez un enregistrement de vos ressources logicielles et matérielles, ainsi que leurs configurations.</span><span class="sxs-lookup"><span data-stu-id="8d58d-131">Keep a record of your software and hardware assets and their configurations.</span></span>

  - <span data-ttu-id="8d58d-132">**Administration**     du système Mode plan standard permettant d’effectuer des tâches administratives telles que l’administration des bases de données et l’administration des sites.</span><span class="sxs-lookup"><span data-stu-id="8d58d-132">**System Administration**   Outline standard methods for doing administrative tasks such as database administration and site administration.</span></span>

  - <span data-ttu-id="8d58d-133">Administration de la **sécurité**     Disposer d’une stratégie et d’un plan détaillés qui protège la confidentialité des données, l’intégrité des données et la disponibilité des données de l’infrastructure informatique.</span><span class="sxs-lookup"><span data-stu-id="8d58d-133">**Security Administration**   Have a detailed policy and plan that protects data confidentiality, data integrity, and data availability of the IT infrastructure.</span></span> <span data-ttu-id="8d58d-134">Cela inclut les activités quotidiennes et les tâches liées à la maintenance et à l’ajustement de l’infrastructure de sécurité informatique.</span><span class="sxs-lookup"><span data-stu-id="8d58d-134">This includes day-to-day activities and tasks that are related to maintaining and adjusting the IT security infrastructure.</span></span>

  - <span data-ttu-id="8d58d-135">**Dépannage**     du système Hiérarchisation des méthodes de traitement des problèmes inattendus, y compris les étapes permettant d’éviter des problèmes similaires à l’avenir.</span><span class="sxs-lookup"><span data-stu-id="8d58d-135">**System Troubleshooting**   Outline methods for dealing with unexpected issues, including steps to prevent similar issues in the future.</span></span>

  - <span data-ttu-id="8d58d-136">Contrats de niveau de **service**     Conservez un ensemble d’objectifs pour les performances des systèmes informatiques et mesurez régulièrement les performances par rapport à ces objectifs.</span><span class="sxs-lookup"><span data-stu-id="8d58d-136">**Service Level Agreements**   Maintain a set of goals for the performance of the IT systems and regularly measure performance against these goals.</span></span>

  - <span data-ttu-id="8d58d-137">**Documentation relative**     Documentez les procédures standard, telles que les informations de configuration et les leçons apprises, et rendez-les accessibles aux membres du personnel qui en ont besoin.</span><span class="sxs-lookup"><span data-stu-id="8d58d-137">**Documentation**   Document standard procedures, such as configuration information and lessons learned, and make them available to the staff members that need them.</span></span> <span data-ttu-id="8d58d-138">Lorsque les modifications apportées à la configuration sont effectuées, mettez à jour la documentation en conséquence.</span><span class="sxs-lookup"><span data-stu-id="8d58d-138">As changes to the configuration are made, update the documentation accordingly.</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="8d58d-139">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="8d58d-139">Related Sections</span></span>

<span data-ttu-id="8d58d-140">Consultez les rubriques suivantes concernant les opérations système avant de continuer :</span><span class="sxs-lookup"><span data-stu-id="8d58d-140">Review the following topics concerning system operations before proceeding:</span></span>

  - [<span data-ttu-id="8d58d-141">Gestion de la capacité et de la disponibilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d58d-141">Capacity and availability management in Lync Server 2013</span></span>](lync-server-2013-capacity-and-availability-management.md)

  - [<span data-ttu-id="8d58d-142">Gestion des modifications dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d58d-142">Change management in Lync Server 2013</span></span>](lync-server-2013-change-management.md)

  - [<span data-ttu-id="8d58d-143">Gestion de la configuration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d58d-143">Configuration management in Lync Server 2013</span></span>](lync-server-2013-configuration-management.md)

  - [<span data-ttu-id="8d58d-144">Administration système dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d58d-144">System administration in Lync Server 2013</span></span>](lync-server-2013-system-administration.md)

  - [<span data-ttu-id="8d58d-145">Contrats de niveau de service dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d58d-145">Service level agreements in Lync Server 2013</span></span>](lync-server-2013-service-level-agreements.md)

  - [<span data-ttu-id="8d58d-146">Documentation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d58d-146">Documentation in Lync Server 2013</span></span>](lync-server-2013-documentation.md)

  - [<span data-ttu-id="8d58d-147">Procédures standard dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d58d-147">Standard procedures in Lync Server 2013</span></span>](lync-server-2013-standard-procedures.md)

  - [<span data-ttu-id="8d58d-148">Procédures d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d58d-148">Emergency procedures in Lync Server 2013</span></span>](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8d58d-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8d58d-149">See Also</span></span>


[<span data-ttu-id="8d58d-150">Microsoft Operations Framework 4,0</span><span class="sxs-lookup"><span data-stu-id="8d58d-150">Microsoft Operations Framework 4.0</span></span>](https://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: meilleures pratiques pour les environnements Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for Lync Server environments
ms:assetid: b0e45d84-09c8-4d3e-aad0-bc6f34ce233b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720348(v=OCS.15)
ms:contentKeyID: 63969642
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00dbbf95990875b8366ce5a03f1d2d70e6652828
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-lync-server-2013-environments"></a><span data-ttu-id="7fa9e-102">Recommandations en matière d’environnements Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fa9e-102">Best practices for Lync Server 2013 environments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fa9e-103">_**Dernière modification de la rubrique:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="7fa9e-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="7fa9e-104">Les principes généraux suivants doivent être appliqués aux opérations en cours de votre système:</span><span class="sxs-lookup"><span data-stu-id="7fa9e-104">The following general principles should be applied to ongoing operations of your system:</span></span>

  - <span data-ttu-id="7fa9e-105">**Comprenez et utilisez**   MOF MOF est une collection de meilleures pratiques, de principes et de modèles qui fournissent aux organisations des recommandations techniques sur la gestion des ressources informatiques, telles que les opérations quotidiennes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-105">**Understand and utilize MOF**   MOF is a collection of best practices, principles, and models that provide organizations technical guidance about the management of IT assets, such as daily Lync Server 2013 operations.</span></span> <span data-ttu-id="7fa9e-106">Les instructions MOF suivantes vous permettent de bénéficier de la fiabilité, de la disponibilité, de la prise en charge et de la gestion des systèmes de production stratégiques pour les produits Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-106">Following MOF guidelines can help you achieve mission-critical production system reliability, availability, supportability, and manageability for Microsoft products.</span></span> <span data-ttu-id="7fa9e-107">Pour plus d’informations, consultez [Microsoft Operations Framework 4,0](http://go.microsoft.com/fwlink/p/?linkid=40939).</span><span class="sxs-lookup"><span data-stu-id="7fa9e-107">For more information, see [Microsoft Operations Framework 4.0](http://go.microsoft.com/fwlink/p/?linkid=40939).</span></span>

  - <span data-ttu-id="7fa9e-108">**En savoir plus sur les meilleures pratiques en matière de Lync Server 2013**   , nous vous recommandons de mettre en œuvre des procédures pratiques et éprouvées pour gérer Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-108">**Learn about best practices for Lync Server 2013**   We recommend that you implement practical and proven procedures to manage Lync Server 2013.</span></span> <span data-ttu-id="7fa9e-109">L’utilisation de méthodes essayées, testées et documentées lors de la gestion d’opérations risque d’être plus efficace que de développer vos propres méthodes.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-109">By using tried, tested, and documented methods of managing operations may be more efficient than developing your own methods.</span></span>

  - <span data-ttu-id="7fa9e-110">**Séparez les opérations en processus**   quotidiens, hebdomadaires et mensuels pour documenter les tâches opérationnelles requises que vous effectuerez régulièrement.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-110">**Separate operations into daily, weekly, and monthly processes**   Document the required operational tasks that you'll regularly perform.</span></span> <span data-ttu-id="7fa9e-111">La documentation du mode d’exécution des tâches permet de garantir la conservation de vos informations en cas de modification de votre environnement opérationnel, par exemple lors du déploiement de nouvelles technologies ou du changement du personnel.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-111">Documenting how you perform tasks helps make sure that your information is preserved when there is a change in your operational environment such as when new technologies are deployed or staff changes occur.</span></span> <span data-ttu-id="7fa9e-112">Nous vous recommandons d’intégrer les tâches opérationnelles dans des charges de travail gérables, où les tâches sont effectuées quotidiennement, par semaine et par mois.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-112">We recommend that operational tasks be separated into manageable workloads where tasks are performed daily, weekly, and monthly.</span></span> <span data-ttu-id="7fa9e-113">Les tâches quotidiennes concentrent les efforts sur le fonctionnement d’un système, et les tâches mensuelles se focalisent davantage sur la façon de garantir l’intégrité du système sur le long terme.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-113">Daily tasks would focus efforts on the functioning of a system, and monthly tasks would focus more on ensuring the long-term health of a system.</span></span>
    
    <span data-ttu-id="7fa9e-114">Ce document peut être utilisé dans les environnements qui déploient uniquement les composants de messagerie instantanée et de présence (IM/P) ou de messagerie instantanée/P avec Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-114">This document can be used in environments deploying only instant messaging/presence (IM/P) components or IM/P with Enterprise Voice.</span></span> <span data-ttu-id="7fa9e-115">Lorsque des tâches ou des éléments de liste de vérification sont spécifiques aux voix entreprise, cela est mentionné et si votre environnement n’inclut pas d’entreprise voix, la partie peut être ignorée.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-115">When tasks or checklist items are specific to Enterprise Voice, this is mentioned and if your environment does not include Enterprise Voice the portion may be skipped.</span></span>

  - <span data-ttu-id="7fa9e-116">**Déploiement des outils requis pour l’utilisation de Lync Server 2013**   de nombreux outils sont disponibles pour résoudre les problèmes, automatiser les tâches et surveiller et mettre à jour l’environnement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-116">**Deploy the tools that are required for operating Lync Server 2013**   Many tools are available to help troubleshoot issues, automate tasks, and help monitor and maintain the Lync Server 2013 environment.</span></span> <span data-ttu-id="7fa9e-117">Définissez un ensemble standard d’outils pour votre organisation de sorte que les tâches effectuées par l’équipe d’opérations soient effectuées de manière précise, efficace, cohérente et de manière contrôlée.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-117">Define a standard set of tools for your organization so the tasks that are performed by the operations team are performed accurately, efficiently, consistently, and in a controlled manner.</span></span> <span data-ttu-id="7fa9e-118">Vous devez également implémenter des processus pour suivre les incidents et les changements de configuration importants.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-118">You should also implement processes to track incidents and major configuration changes.</span></span>

<div>

## <a name="reference"></a><span data-ttu-id="7fa9e-119">Référence</span><span class="sxs-lookup"><span data-stu-id="7fa9e-119">Reference</span></span>

<span data-ttu-id="7fa9e-120">Dans le souci des utilisateurs qui ne connaissent pas encore les notions de base de la gestion de serveur, nous proposons une vue d’ensemble des pratiques de gestion du serveur.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-120">For the benefit of readers not already familiar with the basics of server management in general, we provide an overview of server management practices.</span></span> <span data-ttu-id="7fa9e-121">Les lecteurs déjà familiarisés avec la gestion du serveur pourront choisir d’ignorer cette section.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-121">Readers already familiar with server management may choose to skip this section.</span></span>

<span data-ttu-id="7fa9e-122">Les pratiques recommandées sont des recommandations fondées sur les connaissances et les compétences des informaticiens ayant gagné dans de nombreux environnements.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-122">Best practices are recommendations that are based on the knowledge and experience that IT professionals have gained across many environments.</span></span> <span data-ttu-id="7fa9e-123">Ils fournissent des procédures standard pour les tâches courantes que les administrateurs de votre serveur Lync doivent exécuter quotidiennement et répertorient les outils qu’ils doivent utiliser pour gérer un environnement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-123">They provide standard procedures for typical tasks that your Lync Server administrators must perform daily, and list the tools that they should use to manage a Lync Server environment.</span></span>

<span data-ttu-id="7fa9e-124">Les tâches typiques pour les administrateurs Lync sont les suivantes:</span><span class="sxs-lookup"><span data-stu-id="7fa9e-124">Typical tasks for Lync administrators include the following:</span></span>

  - <span data-ttu-id="7fa9e-125">**Gestion de la capacité et**   de la disponibilité définir le mode de mesure et les mesures à prendre pour prévoir les exigences de capacité future et pour signaler la capacité, la fiabilité et la disponibilité des systèmes.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-125">**Capacity and Availability Management**   Define how and what to measure to predict future capacity requirements and to report about the capacity, reliability, and availability of your systems.</span></span> <span data-ttu-id="7fa9e-126">Vous devez vérifier que les serveurs qui exécutent Lync Server sont dimensionnés de manière à gérer la charge sur le système et que le temps d’arrêt non planifié est maintenu conformément aux niveaux définis dans le contrat de niveau de service (SLA).</span><span class="sxs-lookup"><span data-stu-id="7fa9e-126">You must verify that servers that are running Lync Server are sized to handle the load on the system, and that unplanned downtime is kept under the levels defined in the service level agreement (SLA).</span></span> <span data-ttu-id="7fa9e-127">Par ailleurs, vous devez mettre à niveau le matériel pour continuer à respecter les exigences définies.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-127">Additionally, you'll have to upgrade hardware to continue to meet the defined requirements.</span></span>

  - <span data-ttu-id="7fa9e-128">**Gestion des changements et gestion**   de la configuration: contrôle des modifications apportées aux systèmes informatiques.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-128">**Change Management and Configuration Management**   Control how changes are made to IT systems.</span></span> <span data-ttu-id="7fa9e-129">Il doit s’agir de tests, de commentaires sur les applications et de plans d’urgence, de la documentation relative à toutes les modifications et de l’approbation de la gestion en cas de problème.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-129">This should include testing, application feedback and contingency plans, documentation of all changes, and approval from management if issues occur.</span></span> <span data-ttu-id="7fa9e-130">Enregistrez vos ressources logicielles et matérielles et leurs configurations.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-130">Keep a record of your software and hardware assets and their configurations.</span></span>

  - <span data-ttu-id="7fa9e-131">\*\*\*\*   Méthodes standard d’administration du système permettant d’effectuer des tâches administratives telles que l’administration de la base de données et l’administration du site.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-131">**System Administration**   Outline standard methods for doing administrative tasks such as database administration and site administration.</span></span>

  - <span data-ttu-id="7fa9e-132">**L’administration**   de la sécurité a une stratégie et un plan détaillés qui protège la confidentialité des données, l’intégrité des données et la disponibilité des données de l’infrastructure informatique.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-132">**Security Administration**   Have a detailed policy and plan that protects data confidentiality, data integrity, and data availability of the IT infrastructure.</span></span> <span data-ttu-id="7fa9e-133">Cela inclut les activités quotidiennes et les tâches qui sont liées à la mise à jour et à l’ajustement de l’infrastructure de sécurité informatique.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-133">This includes day-to-day activities and tasks that are related to maintaining and adjusting the IT security infrastructure.</span></span>

  - <span data-ttu-id="7fa9e-134">\*\*\*\*   Processus de résolution des problèmes de configuration du système pour traiter les problèmes inattendus, y compris les étapes pour éviter des problèmes similaires à l’avenir.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-134">**System Troubleshooting**   Outline methods for dealing with unexpected issues, including steps to prevent similar issues in the future.</span></span>

  - <span data-ttu-id="7fa9e-135">**Les contrats**   de niveau de service maintiennent un ensemble d’objectifs pour la performance des systèmes informatiques et mesurent régulièrement les performances par rapport à ces objectifs.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-135">**Service Level Agreements**   Maintain a set of goals for the performance of the IT systems and regularly measure performance against these goals.</span></span>

  - <span data-ttu-id="7fa9e-136">\*\*\*\*   Documents de documentation procédures standard, tels que les informations de configuration et les leçons tirées, et les mettre à la disposition des membres du personnel enseignant qui en ont besoin.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-136">**Documentation**   Document standard procedures, such as configuration information and lessons learned, and make them available to the staff members that need them.</span></span> <span data-ttu-id="7fa9e-137">À mesure que des modifications sont apportées à la configuration, mettez à jour la documentation en conséquence.</span><span class="sxs-lookup"><span data-stu-id="7fa9e-137">As changes to the configuration are made, update the documentation accordingly.</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="7fa9e-138">Sections associées</span><span class="sxs-lookup"><span data-stu-id="7fa9e-138">Related Sections</span></span>

<span data-ttu-id="7fa9e-139">Pour plus d’informations, consultez les rubriques suivantes concernant les opérations système:</span><span class="sxs-lookup"><span data-stu-id="7fa9e-139">Review the following topics concerning system operations before proceeding:</span></span>

  - [<span data-ttu-id="7fa9e-140">Gestion de la capacité et de la disponibilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fa9e-140">Capacity and availability management in Lync Server 2013</span></span>](lync-server-2013-capacity-and-availability-management.md)

  - [<span data-ttu-id="7fa9e-141">Gestion des modifications dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fa9e-141">Change management in Lync Server 2013</span></span>](lync-server-2013-change-management.md)

  - [<span data-ttu-id="7fa9e-142">Gestion de la configuration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fa9e-142">Configuration management in Lync Server 2013</span></span>](lync-server-2013-configuration-management.md)

  - [<span data-ttu-id="7fa9e-143">Administration du système dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fa9e-143">System administration in Lync Server 2013</span></span>](lync-server-2013-system-administration.md)

  - [<span data-ttu-id="7fa9e-144">Contrats de niveau de service dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fa9e-144">Service level agreements in Lync Server 2013</span></span>](lync-server-2013-service-level-agreements.md)

  - [<span data-ttu-id="7fa9e-145">Documentation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fa9e-145">Documentation in Lync Server 2013</span></span>](lync-server-2013-documentation.md)

  - [<span data-ttu-id="7fa9e-146">Procédures standard dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fa9e-146">Standard procedures in Lync Server 2013</span></span>](lync-server-2013-standard-procedures.md)

  - [<span data-ttu-id="7fa9e-147">Procédures d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fa9e-147">Emergency procedures in Lync Server 2013</span></span>](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7fa9e-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7fa9e-148">See Also</span></span>


[<span data-ttu-id="7fa9e-149">Microsoft Operations Framework 4,0</span><span class="sxs-lookup"><span data-stu-id="7fa9e-149">Microsoft Operations Framework 4.0</span></span>](http://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013 : établissement d’un plan de sauvegarde et de restauration'
description: 'Lync Server 2013 : établissement d’un plan de sauvegarde et de restauration.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration plan
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202183(v=OCS.15)
ms:contentKeyID: 51541499
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06d93c713364bf6b5f230b255b68a2c1dfe1d04a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555050"
---
# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a><span data-ttu-id="1d88f-103">Établissement d’un plan de sauvegarde et de restauration pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d88f-103">Establishing a backup and restoration plan for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d88f-104">_**Dernière modification de la rubrique :** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="1d88f-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="1d88f-105">La création d’un plan de sauvegarde et de restauration nécessite d’effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="1d88f-105">Creating a backup and restoration plan involves the following steps:</span></span>

  - <span data-ttu-id="1d88f-106">Développement du plan.</span><span class="sxs-lookup"><span data-stu-id="1d88f-106">Developing the plan.</span></span>

  - <span data-ttu-id="1d88f-107">Implémentation du plan.</span><span class="sxs-lookup"><span data-stu-id="1d88f-107">Implementing the plan.</span></span>

  - <span data-ttu-id="1d88f-108">Maintenance du plan.</span><span class="sxs-lookup"><span data-stu-id="1d88f-108">Maintaining the plan.</span></span>

<div>

## <a name="developing-a-backup-and-restoration-plan"></a><span data-ttu-id="1d88f-109">Développement d’un plan de sauvegarde et de restauration</span><span class="sxs-lookup"><span data-stu-id="1d88f-109">Developing a Backup and Restoration Plan</span></span>

<span data-ttu-id="1d88f-110">Une fois que vous avez développé votre stratégie de sauvegarde et de restauration pour Lync Server, utilisez-la pour documenter un plan de sauvegarde et de restauration détaillé.</span><span class="sxs-lookup"><span data-stu-id="1d88f-110">After you develop your backup and restoration strategy for Lync Server, use it to document a detailed backup and restoration plan.</span></span> <span data-ttu-id="1d88f-111">Ce plan doit identifier clairement les priorités et exigences de sauvegarde des données et paramètres.</span><span class="sxs-lookup"><span data-stu-id="1d88f-111">Your plan should clearly convey the priorities and requirements for backing up data and settings.</span></span> <span data-ttu-id="1d88f-112">Vous pouvez utiliser les informations contenues dans la [définition d’une stratégie de sauvegarde et de restauration pour Lync server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) et les feuilles de calcul dans les [feuilles de calcul de sauvegarde et de restauration pour Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) afin de faciliter la documentation de votre stratégie.</span><span class="sxs-lookup"><span data-stu-id="1d88f-112">You can use the information in [Establishing a backup and restoration strategy for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) and the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) to facilitate the documentation of your strategy.</span></span> <span data-ttu-id="1d88f-113">Votre plan doit également contenir des critères identifiant quand et comment restaurer le service.</span><span class="sxs-lookup"><span data-stu-id="1d88f-113">Your plan should also contain criteria for deciding when and how to restore service.</span></span>

<span data-ttu-id="1d88f-114">Lorsque vous développez votre plan, vous devez prendre en compte les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="1d88f-114">As you develop your plan, you need to consider, and account for, the following:</span></span>

  - <span data-ttu-id="1d88f-115">la façon dont vous procéderez à la récupération des serveurs sur le nouveau matériel ;</span><span class="sxs-lookup"><span data-stu-id="1d88f-115">How you will recover servers on new hardware.</span></span>

  - <span data-ttu-id="1d88f-116">la façon dont vous procéderez à la récupération des services qui requièrent une action de la part de plusieurs unités professionnelles ou départements ;</span><span class="sxs-lookup"><span data-stu-id="1d88f-116">How you will recover services that require action on the part of multiple business areas or departments.</span></span>

  - <span data-ttu-id="1d88f-117">le meilleur moyen d’acquérir rapidement des serveurs de secours ;</span><span class="sxs-lookup"><span data-stu-id="1d88f-117">How you can acquire spare servers quickly.</span></span>

  - <span data-ttu-id="1d88f-118">la durée nécessaire pour effectuer la récupération conformément à votre stratégie.</span><span class="sxs-lookup"><span data-stu-id="1d88f-118">The time it takes to recover by using your strategy.</span></span> <span data-ttu-id="1d88f-119">Tenez compte des exigences de votre organisation concernant l’objectif de temps de récupération (RTO).</span><span class="sxs-lookup"><span data-stu-id="1d88f-119">Consider your organization’s requirements for recovery time objective (RTO).</span></span>

<span data-ttu-id="1d88f-120">Modifiez les procédures de sauvegarde et de restauration décrites dans cette rubrique, en ajoutant et en supprimant les procédures appropriées, afin de refléter les serveurs et les composants de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="1d88f-120">Modify the backup and restoration procedures in this topic, adding and deleting procedures as appropriate, to reflect the servers and components in your deployment.</span></span> <span data-ttu-id="1d88f-121">Vous pouvez également ajouter des détails appropriés, tels que la planification de sauvegarde, aux procédures appropriées pour vous assurer que les informations ne sont pas négligées.</span><span class="sxs-lookup"><span data-stu-id="1d88f-121">You can also add appropriate details, such as the backup schedule, to the appropriate procedures to make sure that the information is not overlooked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d88f-122">Il est recommandé de créer des scripts pour autant d’étapes que possible afin de garantir la qualité et la reproductibilité des procédures.</span><span class="sxs-lookup"><span data-stu-id="1d88f-122">It is good practice to create scripts for as many steps as possible, to help ensure the quality and reproducibility of procedures.</span></span>



</div>

<span data-ttu-id="1d88f-123">Dans votre plan, indiquez qui est responsable de l’examen du plan, qui est responsable du test et de la validation des nouvelles procédures ou outils, et qui doit approuver les modifications apportées au plan et aux procédures connexes.</span><span class="sxs-lookup"><span data-stu-id="1d88f-123">In your plan, specify who is responsible for reviewing the plan, who is responsible for testing and validating any new procedures or tools, and who must approve any changes to the plan and related procedures.</span></span>

<span data-ttu-id="1d88f-124">Pour vous assurer que votre plan de sauvegarde et de restauration répond entièrement à tous les objectifs et priorités établis, obtenez l’approbation des décideurs d’entreprise et des décisionnaires techniques appropriés dans votre organisation avant d’implémenter le plan.</span><span class="sxs-lookup"><span data-stu-id="1d88f-124">To make sure that your backup and restoration plan fully meets all established goals and priorities, get the approval of the appropriate business decision makers and technical decision makers in your organization before you implement the plan.</span></span>

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a><span data-ttu-id="1d88f-125">Implémentation du plan de sauvegarde et de restauration</span><span class="sxs-lookup"><span data-stu-id="1d88f-125">Implementing the Backup and Restoration Plan</span></span>

<span data-ttu-id="1d88f-126">L’implémentation d’un plan de sauvegarde et de restauration nécessite les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="1d88f-126">Implementing a backup and restoration plan requires the following steps:</span></span>

  - <span data-ttu-id="1d88f-127">Test et validation du plan.</span><span class="sxs-lookup"><span data-stu-id="1d88f-127">Testing and validating the plan.</span></span>

  - <span data-ttu-id="1d88f-128">Communication du plan.</span><span class="sxs-lookup"><span data-stu-id="1d88f-128">Communicating the plan.</span></span>

  - <span data-ttu-id="1d88f-129">Validation des opérations de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="1d88f-129">Validating backup and restoration operations.</span></span>

<div>

## <a name="testing-and-validating-the-plan"></a><span data-ttu-id="1d88f-130">Test et validation du plan</span><span class="sxs-lookup"><span data-stu-id="1d88f-130">Testing and Validating the Plan</span></span>

<span data-ttu-id="1d88f-131">Les procédures décrites ici ont été testées et validées dans un environnement de laboratoire.</span><span class="sxs-lookup"><span data-stu-id="1d88f-131">The procedures described here have been tested and validated in a lab environment.</span></span> <span data-ttu-id="1d88f-132">Pour vous assurer que ces procédures ou d’autres procédures fonctionnent dans votre environnement, vous devez tester et valider chaque procédure que vous envisagez d’implémenter.</span><span class="sxs-lookup"><span data-stu-id="1d88f-132">To make sure that these or any other procedures work in your environment, you should test and validate each procedure you intend to implement.</span></span> <span data-ttu-id="1d88f-133">Terminez les tests et la validation avant d’envoyer votre plan pour approbation finale.</span><span class="sxs-lookup"><span data-stu-id="1d88f-133">Complete the testing and the validation before you submit your plan for final approval.</span></span>

</div>

<div>

## <a name="communicating-the-plan"></a><span data-ttu-id="1d88f-134">Communication du plan</span><span class="sxs-lookup"><span data-stu-id="1d88f-134">Communicating the Plan</span></span>

<span data-ttu-id="1d88f-135">Votre plan de sauvegarde et de restauration doit identifier clairement qui implémente les procédures et fournir des instructions pas à pas pour l’exécution de ces procédures.</span><span class="sxs-lookup"><span data-stu-id="1d88f-135">Your backup and restoration plan should clearly describe who implements procedures and step-by-step instructions for carrying out the procedures.</span></span> <span data-ttu-id="1d88f-136">Assurez-vous que toutes les personnes responsables de tous les aspects de la sauvegarde et de la restauration comprennent le plan, la façon dont il doit être implémenté, ainsi que son rôle.</span><span class="sxs-lookup"><span data-stu-id="1d88f-136">You should make sure that everyone responsible for any aspect of backup and restoration understands the plan, how it is to be implemented, and what their role is.</span></span> <span data-ttu-id="1d88f-137">Cela comprend toutes les exigences d’implémentation pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="1d88f-137">This includes all implementation requirements for the following:</span></span>

  - <span data-ttu-id="1d88f-138">Sauvegarde des pools et des serveurs.</span><span class="sxs-lookup"><span data-stu-id="1d88f-138">Pool and server backup.</span></span>

  - <span data-ttu-id="1d88f-139">Restauration du service.</span><span class="sxs-lookup"><span data-stu-id="1d88f-139">Restoration of service.</span></span>

<span data-ttu-id="1d88f-140">**Sauvegarde des pools et des serveurs**</span><span class="sxs-lookup"><span data-stu-id="1d88f-140">**Pool and server backup**</span></span>

<span data-ttu-id="1d88f-p106">Le plan de sauvegarde et de restauration doit contenir toutes les informations requises pour effectuer les procédures de sauvegarde de manière régulière. Les principales informations à communiquer aux membres d’équipe responsables sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="1d88f-p106">The backup and restoration plan should include all information required to complete backup procedures on an ongoing basis. The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="1d88f-143">Équipe ou personne (spécifiée en tant qu’individu ou rôle) responsable de la sauvegarde de chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="1d88f-143">Team or person (specified as an individual or role) responsible for backing up each server.</span></span>

  - <span data-ttu-id="1d88f-144">Planifications spécifiques pour la sauvegarde de chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="1d88f-144">Specific schedules for backing up each server.</span></span>

  - <span data-ttu-id="1d88f-145">Emplacements de sauvegarde pour chaque type de données (paramètres, base de données et partages de fichiers).</span><span class="sxs-lookup"><span data-stu-id="1d88f-145">Backup locations for each type of data (settings, database, and file shares).</span></span>

  - <span data-ttu-id="1d88f-146">Procédures de sauvegarde à utiliser, y compris les outils nécessaires pour effectuer chaque procédure.</span><span class="sxs-lookup"><span data-stu-id="1d88f-146">Backup procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="1d88f-147">Informations requises pour effectuer les sauvegardes, comme indiqué dans la [fiche de travail de sauvegarde et de restauration pour Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span><span class="sxs-lookup"><span data-stu-id="1d88f-147">Information required to complete backups, as covered in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="1d88f-148">Méthodes de validation à utiliser pour garantir que les données et les paramètres sont correctement sauvegardés et disponibles pour la restauration, ce qui peut inclure des audits périodiques et des restaurations de test.</span><span class="sxs-lookup"><span data-stu-id="1d88f-148">Validation methods to be used to help ensure that data and settings are appropriately backed up and available for restoration, which can include periodic audits and test restorations.</span></span>

<span data-ttu-id="1d88f-149">**Restauration du service**</span><span class="sxs-lookup"><span data-stu-id="1d88f-149">**Restoration of service**</span></span>

<span data-ttu-id="1d88f-150">Le plan de sauvegarde et de restauration doit inclure toutes les informations nécessaires pour restaurer le service, au cas où un ou plusieurs serveurs subiront une perte de disponibilité du service.</span><span class="sxs-lookup"><span data-stu-id="1d88f-150">The backup and restoration plan should include all information required to restore service, in case one or more servers experience a loss that makes service unavailable.</span></span> <span data-ttu-id="1d88f-151">Les principales informations à communiquer aux membres d’équipe responsables sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="1d88f-151">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="1d88f-152">équipe ou personne (identifiée personnellement ou par rôle) chargée de déterminer quand une restauration du service est requise et les procédures à appliquer pour restaurer le service, ainsi que l’équipe ou la personne responsable de l’implémentation des procédures pour chaque scénario de restauration ;</span><span class="sxs-lookup"><span data-stu-id="1d88f-152">Team or person (specified as an individual or a role) that is responsible for determining when restoration of service is required and the procedures to be used to restore service, and also the team or person responsible for implementing procedures for each restoration scenario.</span></span>

  - <span data-ttu-id="1d88f-153">critères permettant d’identifier les procédures de restauration les plus appropriées pour une situation spécifique ;</span><span class="sxs-lookup"><span data-stu-id="1d88f-153">Criteria for determining which restoration procedures are most appropriate for a specific situation.</span></span>

  - <span data-ttu-id="1d88f-154">Estimations de temps pour la restauration des objectifs de temps de service et de temps de récupération dans chaque scénario de restauration.</span><span class="sxs-lookup"><span data-stu-id="1d88f-154">Time estimates for restoration of service and recovery time objective (RTO) in each restoration scenario.</span></span>

  - <span data-ttu-id="1d88f-155">procédures de restauration à appliquer, y compris les outils nécessaires pour effectuer chaque procédure ;</span><span class="sxs-lookup"><span data-stu-id="1d88f-155">Restoration procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="1d88f-156">informations requises pour restaurer les données et paramètres.</span><span class="sxs-lookup"><span data-stu-id="1d88f-156">Information required to restore data and settings.</span></span> <span data-ttu-id="1d88f-157">Les feuilles de calcul sont fournies dans les [feuilles de calcul de sauvegarde et de restauration pour Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span><span class="sxs-lookup"><span data-stu-id="1d88f-157">Worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a><span data-ttu-id="1d88f-158">Validation des opérations de sauvegarde et de restauration</span><span class="sxs-lookup"><span data-stu-id="1d88f-158">Validating Backup and Restoration Operations</span></span>

<span data-ttu-id="1d88f-159">Après avoir effectué les tâches de sauvegarde initiales dans votre environnement de production et à intervalles spécifiés (tel qu’indiqué dans votre plan de sauvegarde et de restauration), vérifiez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="1d88f-159">After completing initial backup efforts in your production environment and at specified intervals (as covered in your backup and restoration plan), you should verify the following:</span></span>

  - <span data-ttu-id="1d88f-160">les sauvegardes ont lieu au moment voulu ;</span><span class="sxs-lookup"><span data-stu-id="1d88f-160">Backups are occurring as required.</span></span>

  - <span data-ttu-id="1d88f-161">Les données et les paramètres sauvegardés sont accessibles.</span><span class="sxs-lookup"><span data-stu-id="1d88f-161">Backed-up data and settings are accessible.</span></span>

  - <span data-ttu-id="1d88f-162">Les procédures de restauration peuvent être effectuées au cours des objectifs de temps de récupération (RTO) spécifiés dans le plan de sauvegarde et de restauration, et les résultats satisfont à tous les besoins de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="1d88f-162">Restoration procedures can be performed within the recovery time objective (RTO) times specified in the backup and restoration plan, and the results meet all business requirements.</span></span>

  - <span data-ttu-id="1d88f-163">les fiches de travail de sauvegarde ont été remplies et vérifiées et elles sont stockées à un emplacement sécurisé.</span><span class="sxs-lookup"><span data-stu-id="1d88f-163">Backup worksheets have been completed and verified, and they are stored in a secure location.</span></span> <span data-ttu-id="1d88f-164">Ces feuilles de calcul sont fournies dans les [feuilles de calcul de sauvegarde et de restauration pour Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span><span class="sxs-lookup"><span data-stu-id="1d88f-164">These worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="1d88f-165">les procédures de restauration ont été testées et leur fonctionnement a été vérifié, comme indiqué dans votre plan de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="1d88f-165">Restoration procedures have been tested and verified to work as expected, as specified in your backup and restoration plan.</span></span>

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a><span data-ttu-id="1d88f-166">Maintenance du plan de sauvegarde et de restauration</span><span class="sxs-lookup"><span data-stu-id="1d88f-166">Maintaining the Backup and Restoration Plan</span></span>

<span data-ttu-id="1d88f-167">Une topologie Lync Server est un environnement dynamique qui est modifié avec votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1d88f-167">A Lync Server topology is a dynamic environment that changes with your organization.</span></span> <span data-ttu-id="1d88f-168">Réévaluez votre plan de sauvegarde et de restauration au fur et à mesure que votre organisation change, puis examinez-la régulièrement pour vous assurer qu’elle continue de répondre aux besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="1d88f-168">Reassess your backup and restoration plan as your organization changes, and review it periodically to make sure that it continues to meet the needs of your business.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


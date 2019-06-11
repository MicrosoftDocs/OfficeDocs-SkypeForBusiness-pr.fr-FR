---
title: 'Lync Server 2013: établissement d’un plan de sauvegarde et de restauration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Establishing a backup and restoration plan
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202183(v=OCS.15)
ms:contentKeyID: 51541499
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b3516e63a7cbada4a89fad3540406e38b299fef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a><span data-ttu-id="866f1-102">Établissement d’un plan de sauvegarde et de restauration pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="866f1-102">Establishing a backup and restoration plan for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="866f1-103">_**Dernière modification de la rubrique:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="866f1-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="866f1-104">Pour créer un plan de sauvegarde et de restauration, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="866f1-104">Creating a backup and restoration plan involves the following steps:</span></span>

  - <span data-ttu-id="866f1-105">Développement du plan.</span><span class="sxs-lookup"><span data-stu-id="866f1-105">Developing the plan.</span></span>

  - <span data-ttu-id="866f1-106">Implémentation du plan.</span><span class="sxs-lookup"><span data-stu-id="866f1-106">Implementing the plan.</span></span>

  - <span data-ttu-id="866f1-107">Maintenance du plan.</span><span class="sxs-lookup"><span data-stu-id="866f1-107">Maintaining the plan.</span></span>

<div>

## <a name="developing-a-backup-and-restoration-plan"></a><span data-ttu-id="866f1-108">Développement d’un plan de sauvegarde et de restauration</span><span class="sxs-lookup"><span data-stu-id="866f1-108">Developing a Backup and Restoration Plan</span></span>

<span data-ttu-id="866f1-109">Après avoir développé votre stratégie de sauvegarde et de restauration pour Lync Server, utilisez-la pour documenter une planification de sauvegarde et de restauration détaillées.</span><span class="sxs-lookup"><span data-stu-id="866f1-109">After you develop your backup and restoration strategy for Lync Server, use it to document a detailed backup and restoration plan.</span></span> <span data-ttu-id="866f1-110">Votre plan doit indiquer clairement les priorités et les exigences en matière de sauvegarde des données et des paramètres.</span><span class="sxs-lookup"><span data-stu-id="866f1-110">Your plan should clearly convey the priorities and requirements for backing up data and settings.</span></span> <span data-ttu-id="866f1-111">Pour plus d’informations sur la [création d’une stratégie de sauvegarde et de restauration de lync 2013 server](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) 2013, vous pouvez utiliser les informations contenues dans la création d’une stratégie de sauvegarde et de restauration pour [Lync Server](lync-server-2013-backup-and-restoration-worksheets.md) et faciliter la documentation de votre stratégie.</span><span class="sxs-lookup"><span data-stu-id="866f1-111">You can use the information in [Establishing a backup and restoration strategy for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) and the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) to facilitate the documentation of your strategy.</span></span> <span data-ttu-id="866f1-112">Votre plan doit également contenir des critères de décision concernant le mode de restauration du service.</span><span class="sxs-lookup"><span data-stu-id="866f1-112">Your plan should also contain criteria for deciding when and how to restore service.</span></span>

<span data-ttu-id="866f1-113">Lorsque vous développez votre plan, vous devez prendre en compte les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="866f1-113">As you develop your plan, you need to consider, and account for, the following:</span></span>

  - <span data-ttu-id="866f1-114">Le mode de récupération des serveurs sur le nouveau matériel.</span><span class="sxs-lookup"><span data-stu-id="866f1-114">How you will recover servers on new hardware.</span></span>

  - <span data-ttu-id="866f1-115">Le mode de récupération des services nécessitant une action de la part de plusieurs domaines ou services commerciaux.</span><span class="sxs-lookup"><span data-stu-id="866f1-115">How you will recover services that require action on the part of multiple business areas or departments.</span></span>

  - <span data-ttu-id="866f1-116">Comment vous pouvez obtenir des serveurs de réserve rapidement.</span><span class="sxs-lookup"><span data-stu-id="866f1-116">How you can acquire spare servers quickly.</span></span>

  - <span data-ttu-id="866f1-117">Le temps nécessaire à la récupération en utilisant votre stratégie.</span><span class="sxs-lookup"><span data-stu-id="866f1-117">The time it takes to recover by using your strategy.</span></span> <span data-ttu-id="866f1-118">Prenez en compte les exigences de votre organisation concernant les objectifs de temps de récupération.</span><span class="sxs-lookup"><span data-stu-id="866f1-118">Consider your organization’s requirements for recovery time objective (RTO).</span></span>

<span data-ttu-id="866f1-119">Modifiez les procédures de sauvegarde et de restauration décrites dans cette rubrique, en ajoutant et en supprimant les procédures le cas échéant, afin de répercuter les serveurs et les composants dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="866f1-119">Modify the backup and restoration procedures in this topic, adding and deleting procedures as appropriate, to reflect the servers and components in your deployment.</span></span> <span data-ttu-id="866f1-120">Vous pouvez également ajouter des détails appropriés, comme le planning de sauvegarde, aux procédures appropriées pour vous assurer que les informations ne sont pas ignorées.</span><span class="sxs-lookup"><span data-stu-id="866f1-120">You can also add appropriate details, such as the backup schedule, to the appropriate procedures to make sure that the information is not overlooked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="866f1-121">Il est recommandé de créer des scripts pour autant de étapes que possible afin de garantir la qualité et la reproductibilité des procédures.</span><span class="sxs-lookup"><span data-stu-id="866f1-121">It is good practice to create scripts for as many steps as possible, to help ensure the quality and reproducibility of procedures.</span></span>



</div>

<span data-ttu-id="866f1-122">Dans votre plan, spécifiez qui est responsable de la consultation du plan, qui est chargé de tester et de valider tout nouveau mode ou outil, et qui doit approuver les modifications apportées au plan et aux procédures associées.</span><span class="sxs-lookup"><span data-stu-id="866f1-122">In your plan, specify who is responsible for reviewing the plan, who is responsible for testing and validating any new procedures or tools, and who must approve any changes to the plan and related procedures.</span></span>

<span data-ttu-id="866f1-123">Pour vous assurer que votre plan de sauvegarde et de restauration répond bien à toutes les priorités et buts définis, obtenez l’approbation des décideurs et des décisions techniques appropriés de votre organisation avant d’implémenter le plan.</span><span class="sxs-lookup"><span data-stu-id="866f1-123">To make sure that your backup and restoration plan fully meets all established goals and priorities, get the approval of the appropriate business decision makers and technical decision makers in your organization before you implement the plan.</span></span>

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a><span data-ttu-id="866f1-124">Implémentation du plan de sauvegarde et de restauration</span><span class="sxs-lookup"><span data-stu-id="866f1-124">Implementing the Backup and Restoration Plan</span></span>

<span data-ttu-id="866f1-125">Pour implémenter un plan de sauvegarde et de restauration, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="866f1-125">Implementing a backup and restoration plan requires the following steps:</span></span>

  - <span data-ttu-id="866f1-126">Test et validation du plan.</span><span class="sxs-lookup"><span data-stu-id="866f1-126">Testing and validating the plan.</span></span>

  - <span data-ttu-id="866f1-127">Communication du plan.</span><span class="sxs-lookup"><span data-stu-id="866f1-127">Communicating the plan.</span></span>

  - <span data-ttu-id="866f1-128">Valider les opérations de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="866f1-128">Validating backup and restoration operations.</span></span>

<div>

## <a name="testing-and-validating-the-plan"></a><span data-ttu-id="866f1-129">Test et validation du plan</span><span class="sxs-lookup"><span data-stu-id="866f1-129">Testing and Validating the Plan</span></span>

<span data-ttu-id="866f1-130">Les procédures décrites dans cet article ont été testées et validées dans un environnement Lab.</span><span class="sxs-lookup"><span data-stu-id="866f1-130">The procedures described here have been tested and validated in a lab environment.</span></span> <span data-ttu-id="866f1-131">Pour vous assurer que les procédures suivantes s’appliquent à votre environnement, testez et validez les procédures que vous envisagez d’implémenter.</span><span class="sxs-lookup"><span data-stu-id="866f1-131">To make sure that these or any other procedures work in your environment, you should test and validate each procedure you intend to implement.</span></span> <span data-ttu-id="866f1-132">Finalisez le test et la validation avant de remettre votre plan pour approbation finale.</span><span class="sxs-lookup"><span data-stu-id="866f1-132">Complete the testing and the validation before you submit your plan for final approval.</span></span>

</div>

<div>

## <a name="communicating-the-plan"></a><span data-ttu-id="866f1-133">Communication du plan</span><span class="sxs-lookup"><span data-stu-id="866f1-133">Communicating the Plan</span></span>

<span data-ttu-id="866f1-134">Votre plan de sauvegarde et de restauration doit clairement décrire les personnes qui mettent en œuvre des procédures et des instructions détaillées pour la réalisation des procédures.</span><span class="sxs-lookup"><span data-stu-id="866f1-134">Your backup and restoration plan should clearly describe who implements procedures and step-by-step instructions for carrying out the procedures.</span></span> <span data-ttu-id="866f1-135">Assurez-vous que toutes les personnes responsables de la sauvegarde et de la restauration comprennent le plan, la manière dont il doit être implémenté et son rôle.</span><span class="sxs-lookup"><span data-stu-id="866f1-135">You should make sure that everyone responsible for any aspect of backup and restoration understands the plan, how it is to be implemented, and what their role is.</span></span> <span data-ttu-id="866f1-136">Cela inclut toutes les exigences en matière d’implémentation pour les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="866f1-136">This includes all implementation requirements for the following:</span></span>

  - <span data-ttu-id="866f1-137">Sauvegarde du pool et du serveur.</span><span class="sxs-lookup"><span data-stu-id="866f1-137">Pool and server backup.</span></span>

  - <span data-ttu-id="866f1-138">Restauration du service.</span><span class="sxs-lookup"><span data-stu-id="866f1-138">Restoration of service.</span></span>

<span data-ttu-id="866f1-139">**Sauvegarde du serveur et du pool**</span><span class="sxs-lookup"><span data-stu-id="866f1-139">**Pool and server backup**</span></span>

<span data-ttu-id="866f1-140">Le plan de sauvegarde et de restauration doit inclure toutes les informations nécessaires à l’achèvement régulier des procédures de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="866f1-140">The backup and restoration plan should include all information required to complete backup procedures on an ongoing basis.</span></span> <span data-ttu-id="866f1-141">Les principales informations à communiquer aux membres de l’équipe responsable incluent les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="866f1-141">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="866f1-142">Équipe ou personne (spécifiée en tant qu’individu ou rôle) responsable de la sauvegarde de chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="866f1-142">Team or person (specified as an individual or role) responsible for backing up each server.</span></span>

  - <span data-ttu-id="866f1-143">Plannings spécifiques de sauvegarde de chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="866f1-143">Specific schedules for backing up each server.</span></span>

  - <span data-ttu-id="866f1-144">Emplacements de sauvegarde pour chaque type de données (paramètres, base de données et partages de fichiers).</span><span class="sxs-lookup"><span data-stu-id="866f1-144">Backup locations for each type of data (settings, database, and file shares).</span></span>

  - <span data-ttu-id="866f1-145">Procédures de sauvegarde à utiliser, y compris les outils nécessaires à la réalisation de chaque procédure.</span><span class="sxs-lookup"><span data-stu-id="866f1-145">Backup procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="866f1-146">Les informations nécessaires à la réalisation des sauvegardes, telles qu’elles sont décrites dans les [feuilles de calcul de sauvegarde et de restauration pour Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span><span class="sxs-lookup"><span data-stu-id="866f1-146">Information required to complete backups, as covered in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="866f1-147">Les méthodes de validation à utiliser pour garantir que les données et paramètres soient correctement sauvegardés et disponibles à des fins de restauration, qui peuvent inclure des audits périodiques et des restaurations de tests.</span><span class="sxs-lookup"><span data-stu-id="866f1-147">Validation methods to be used to help ensure that data and settings are appropriately backed up and available for restoration, which can include periodic audits and test restorations.</span></span>

<span data-ttu-id="866f1-148">**Restauration du service**</span><span class="sxs-lookup"><span data-stu-id="866f1-148">**Restoration of service**</span></span>

<span data-ttu-id="866f1-149">Le plan de sauvegarde et de restauration doit inclure toutes les informations nécessaires à la restauration du service, en cas de perte de l’un ou de plusieurs serveurs pour lesquels le service n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="866f1-149">The backup and restoration plan should include all information required to restore service, in case one or more servers experience a loss that makes service unavailable.</span></span> <span data-ttu-id="866f1-150">Les principales informations à communiquer aux membres de l’équipe responsable incluent les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="866f1-150">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="866f1-151">Une équipe ou une personne (spécifiée en tant qu’individu ou rôle) qui est responsable de la détermination du moment où la restauration du service est requise et des procédures à utiliser pour restaurer le service ainsi que de l’équipe ou de la personne responsable de la mise en œuvre de procédures pour chacun d’eux. scénario de restauration.</span><span class="sxs-lookup"><span data-stu-id="866f1-151">Team or person (specified as an individual or a role) that is responsible for determining when restoration of service is required and the procedures to be used to restore service, and also the team or person responsible for implementing procedures for each restoration scenario.</span></span>

  - <span data-ttu-id="866f1-152">Critères permettant de déterminer quelles procédures de restauration conviennent le mieux pour une situation spécifique.</span><span class="sxs-lookup"><span data-stu-id="866f1-152">Criteria for determining which restoration procedures are most appropriate for a specific situation.</span></span>

  - <span data-ttu-id="866f1-153">Temps d’estimation pour la restauration de l’objectif de temps de service et de temps de reprise (RTO) dans chaque scénario de restauration.</span><span class="sxs-lookup"><span data-stu-id="866f1-153">Time estimates for restoration of service and recovery time objective (RTO) in each restoration scenario.</span></span>

  - <span data-ttu-id="866f1-154">Procédures de restauration à utiliser, y compris les outils nécessaires à la réalisation de chaque procédure.</span><span class="sxs-lookup"><span data-stu-id="866f1-154">Restoration procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="866f1-155">Informations nécessaires à la restauration des données et des paramètres.</span><span class="sxs-lookup"><span data-stu-id="866f1-155">Information required to restore data and settings.</span></span> <span data-ttu-id="866f1-156">Les feuilles de calcul sont fournies dans les [feuilles de calcul et de restauration pour Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span><span class="sxs-lookup"><span data-stu-id="866f1-156">Worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a><span data-ttu-id="866f1-157">Valider les opérations de sauvegarde et de restauration</span><span class="sxs-lookup"><span data-stu-id="866f1-157">Validating Backup and Restoration Operations</span></span>

<span data-ttu-id="866f1-158">Après avoir effectué les efforts de sauvegarde initiale dans votre environnement de production et à des intervalles spécifiques (comme décrit dans votre plan de sauvegarde et de restauration), vous devez vérifier les points suivants:</span><span class="sxs-lookup"><span data-stu-id="866f1-158">After completing initial backup efforts in your production environment and at specified intervals (as covered in your backup and restoration plan), you should verify the following:</span></span>

  - <span data-ttu-id="866f1-159">Les sauvegardes se produisent selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="866f1-159">Backups are occurring as required.</span></span>

  - <span data-ttu-id="866f1-160">Les données et paramètres sauvegardés sont accessibles.</span><span class="sxs-lookup"><span data-stu-id="866f1-160">Backed-up data and settings are accessible.</span></span>

  - <span data-ttu-id="866f1-161">Les procédures de restauration peuvent être exécutées dans les temps d’objectif de temps de restauration spécifiés dans le plan de sauvegarde et de restauration, et les résultats répondent à toutes les exigences métiers.</span><span class="sxs-lookup"><span data-stu-id="866f1-161">Restoration procedures can be performed within the recovery time objective (RTO) times specified in the backup and restoration plan, and the results meet all business requirements.</span></span>

  - <span data-ttu-id="866f1-162">Les feuilles de calcul de sauvegarde sont achevées et vérifiées, et sont stockées dans un emplacement sécurisé.</span><span class="sxs-lookup"><span data-stu-id="866f1-162">Backup worksheets have been completed and verified, and they are stored in a secure location.</span></span> <span data-ttu-id="866f1-163">Ces feuilles de calcul sont fournies dans les [feuilles de calcul et de restauration pour Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span><span class="sxs-lookup"><span data-stu-id="866f1-163">These worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="866f1-164">Les procédures de restauration ont été testées et vérifiées pour fonctionner comme prévu, comme indiqué dans votre plan de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="866f1-164">Restoration procedures have been tested and verified to work as expected, as specified in your backup and restoration plan.</span></span>

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a><span data-ttu-id="866f1-165">Maintenance du plan de sauvegarde et de restauration</span><span class="sxs-lookup"><span data-stu-id="866f1-165">Maintaining the Backup and Restoration Plan</span></span>

<span data-ttu-id="866f1-166">Une topologie de serveur Lync est un environnement dynamique modifié par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="866f1-166">A Lync Server topology is a dynamic environment that changes with your organization.</span></span> <span data-ttu-id="866f1-167">Réévaluez votre plan de sauvegarde et de restauration au fur et à mesure de l’évolution de votre organisation et examinez-le régulièrement pour vous assurer qu’il continue de répondre aux besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="866f1-167">Reassess your backup and restoration plan as your organization changes, and review it periodically to make sure that it continues to meet the needs of your business.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


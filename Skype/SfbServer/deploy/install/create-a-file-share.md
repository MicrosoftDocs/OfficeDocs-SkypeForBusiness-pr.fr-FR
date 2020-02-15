---
title: Créer un partage de fichiers dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Résumé : Découvrez comment créer un partage de fichiers Windows Server dans le cadre de l’installation de Skype entreprise Server. Téléchargez une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverMicrosoft à l’adresse suivante :.'
ms.openlocfilehash: 74c2c8ddedfb6c2a751822fec51636dddd7747dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028295"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a><span data-ttu-id="9f4e7-104">Créer un partage de fichiers dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9f4e7-104">Create a file share in Skype for Business Server</span></span>
 
<span data-ttu-id="9f4e7-105">**Résumé :** Découvrez comment créer un partage de fichiers Windows Server dans le cadre de l’installation de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server.</span></span> <span data-ttu-id="9f4e7-106">Téléchargez une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Microsoft à l’adresse suivante :.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="9f4e7-107">Skype entreprise Server nécessite un partage de fichiers pour que les ordinateurs de la topologie puissent échanger des fichiers.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="9f4e7-108">La création d’un partage de fichiers est l’étape 2 sur 8 du processus d’installation de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server.</span></span> <span data-ttu-id="9f4e7-109">Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="9f4e7-110">Toutefois, vous devez effectuer les étapes 6, 7 et 8 dans l’ordre et après les étapes 1 à 5 comme indiqué dans le diagramme.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="9f4e7-111">Pour plus d’informations sur la planification du partage de fichiers, voir [Environmental Requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server Requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f4e7-111">For planning details about file share, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![Diagramme de vue d’ensemble](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="9f4e7-113">Créer un partage de fichiers de base</span><span class="sxs-lookup"><span data-stu-id="9f4e7-113">Create a basic file share</span></span>

<span data-ttu-id="9f4e7-114">Cette section vous guide tout au long de la création d’un partage de fichiers Windows Server de base.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="9f4e7-115">Un partage de fichiers Windows Server de base est pris en charge avec Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="9f4e7-116">Toutefois, il ne fournit pas de manière explicite la haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="9f4e7-117">Pour un environnement à haute disponibilité, un partage de fichiers DFS (Distributed File System) est recommandé.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="9f4e7-118">Pour plus d’informations sur un partage de fichiers haute disponibilité et DFS, reportez-vous à la rubrique [plan for High Availability and Disaster Recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="9f4e7-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9f4e7-119">Windows Server 2012 R2 a fait des bonds importants en fournissant des solutions de partage de fichiers de type SAN (Storage Area Network) à l’aide de la plateforme Windows Server.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="9f4e7-120">Par rapport à un appareil SAN traditionnel, une solution de stockage Windows Server 2012 R2 peut réduire les coûts en deux, avec un impact minime sur les performances.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="9f4e7-121">Pour plus d’informations sur les options de partage de fichiers dans Windows Server 2012 R2, reportez-vous au livre blanc téléchargeable [Windows server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span><span class="sxs-lookup"><span data-stu-id="9f4e7-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="9f4e7-122">Regardez les étapes vidéo pour **créer un partage de fichiers**:</span><span class="sxs-lookup"><span data-stu-id="9f4e7-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="9f4e7-123">Créer un partage de fichiers de base</span><span class="sxs-lookup"><span data-stu-id="9f4e7-123">Create a basic file share</span></span>

1. <span data-ttu-id="9f4e7-124">Ouvrez une session sur l’ordinateur qui hébergera le partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="9f4e7-125">Cliquez avec le bouton droit sur le dossier que vous prévoyez de partager, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="9f4e7-126">Sélectionnez l’onglet **partage** , puis cliquez sur **partage avancé**.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="9f4e7-127">Cliquez sur **partager ce dossier**.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="9f4e7-128">Cliquez sur **Autorisations**.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="9f4e7-129">Ajoutez le groupe **administrateurs** local du serveur qui héberge le partage de fichiers, octroyez les droits de **contrôle total, de modification et de lecture** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="9f4e7-130">Cliquez de nouveau sur **OK** et prenez note du chemin d’accès réseau.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="9f4e7-131">Cliquez sur **Terminer** pour fermer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-131">Click **Done** to close the wizard.</span></span>
    
     ![Onglet partage pour le partage d’un dossier.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
><span data-ttu-id="9f4e7-133">Si le magasin de fichiers est hébergé sur un partage DFS, l’avertissement suivant s’affiche :</span><span class="sxs-lookup"><span data-stu-id="9f4e7-133">If the file store is hosted on a DFS share, the following warning will be received:</span></span>

<span data-ttu-id="9f4e7-134">AVERTISSEMENT : impossible d’accéder aux autorisations de partage\\<domain>\<pour « partager> ».</span><span class="sxs-lookup"><span data-stu-id="9f4e7-134">Warning: Unable to access share permissions for "\\<domain>\<share>".</span></span>

><span data-ttu-id="9f4e7-135">Cela est attendu si vous n’êtes pas administrateur sur le serveur de fichiers ou s’il s’agit d’un partage de système de fichiers DFS (Distributed File System).</span><span class="sxs-lookup"><span data-stu-id="9f4e7-135">This is expected if you are not an administrator on the file server, or if this is a Distributed File System (DFS) share.</span></span> <span data-ttu-id="9f4e7-136">Si les autorisations de partage ont déjà été configurées, cet avertissement peut être ignoré.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-136">If the share permissions have already been configured, this warning can be ignored.</span></span> <span data-ttu-id="9f4e7-137">S’il s’agit d’un nouveau partage, reportez-vous à la documentation pour plus d’informations sur la configuration manuelle des autorisations de partage.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-137">If it is a new share, refer to the documentation for details on manually configuring share permissions.</span></span>

><span data-ttu-id="9f4e7-138">En raison de l’impossibilité d’accéder aux autorisations de partage sur un partage DFS, Skype entreprise Server ne peut pas définir explicitement les groupes sur le partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-138">Due to the inability to access the share permissions on a DFS share, Skype for Business Server will not be able to explicitly set groups on the file share.</span></span> <span data-ttu-id="9f4e7-139">Pour vous assurer que les composants Skype entreprise Server peuvent accéder au partage de fichiers avec les autorisations appropriées, vérifiez que les groupes RTC suivants sont ajoutés avec des autorisations de partage de lecture et de modification en plus des autorisations de partage de contrôle total des administrateurs locaux autorisations.</span><span class="sxs-lookup"><span data-stu-id="9f4e7-139">To ensure Skype for Business Server components can access the file share with the appropriate permissions, ensure the following RTC groups are added with Read and Change level share permissions in addition to the local Administrators with Full Control share permissions.</span></span>
* <span data-ttu-id="9f4e7-140">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="9f4e7-140">RTCHSUniversalServices</span></span>
* <span data-ttu-id="9f4e7-141">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="9f4e7-141">RTCComponentUniversalServices</span></span>
* <span data-ttu-id="9f4e7-142">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9f4e7-142">RTCUniversalServerAdmins</span></span>

---
title: Création d’un partage de fichiers dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Summary: Learn how to create a Windows Server file share as part of the installation of Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: db2f92bd921acb8fc4784c6f485a74105c632d9a
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="create-a-file-share-in-skype-for-business-server-2015"></a><span data-ttu-id="7b39c-104">Création d’un partage de fichiers dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="7b39c-104">Create a file share in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7b39c-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7b39c-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server 2015.</span></span> <span data-ttu-id="7b39c-106">Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="7b39c-106">Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="7b39c-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span><span class="sxs-lookup"><span data-stu-id="7b39c-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="7b39c-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7b39c-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server 2015.</span></span> <span data-ttu-id="7b39c-109">Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="7b39c-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="7b39c-110">Cependant, vous devez exécuter les étapes 6, 7 et 8 dans l’ordre, et après les étapes 1 à 5 comme indiqué sur le diagramme.</span><span class="sxs-lookup"><span data-stu-id="7b39c-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="7b39c-111">For planning details about file share, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b39c-111">For planning details about file share, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span>
  
![Schéma de vue d’ensemble](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="7b39c-113">Créer un partage de fichiers basique</span><span class="sxs-lookup"><span data-stu-id="7b39c-113">Create a basic file share</span></span>

<span data-ttu-id="7b39c-114">Cette section vous indique comment créer un partage de fichiers Serveur Windows basique.</span><span class="sxs-lookup"><span data-stu-id="7b39c-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="7b39c-115">A basic Windows Server file share is supported with Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7b39c-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="7b39c-116">However, it does not explicitly provide high availability.</span><span class="sxs-lookup"><span data-stu-id="7b39c-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="7b39c-117">Pour un environnement à haute disponibilité, un partage de fichiers Système de fichiers distribué DFS est recommandé.</span><span class="sxs-lookup"><span data-stu-id="7b39c-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="7b39c-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="7b39c-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7b39c-119">Windows Server 2012 R2 a effectué un bond de géant en offrant des solutions de partage de fichiers de type SAN (Storage Area Network) à l’aide de la plateforme Windows Server.</span><span class="sxs-lookup"><span data-stu-id="7b39c-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="7b39c-120">Comparée à un dispositif SAN traditionnel, une solution de stockage Windows Server 2012 R2 permet de diviser les coûts par deux sans réelles incidences sur les performances.</span><span class="sxs-lookup"><span data-stu-id="7b39c-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="7b39c-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span><span class="sxs-lookup"><span data-stu-id="7b39c-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="7b39c-122">Regardez la vidéo des étapes pour **créer un partage de fichiers** :</span><span class="sxs-lookup"><span data-stu-id="7b39c-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="7b39c-123">Créer un partage de fichiers basique</span><span class="sxs-lookup"><span data-stu-id="7b39c-123">Create a basic file share</span></span>

1. <span data-ttu-id="7b39c-124">Connectez-vous à l’ordinateur qui hébergera le partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="7b39c-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="7b39c-125">Cliquez avec le bouton droit sur le dossier que vous souhaitez partager, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="7b39c-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="7b39c-126">Sélectionnez l’onglet **Partage**, puis cliquez sur **Partage avancé**.</span><span class="sxs-lookup"><span data-stu-id="7b39c-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="7b39c-127">Cliquez sur **Partager ce dossier**.</span><span class="sxs-lookup"><span data-stu-id="7b39c-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="7b39c-128">Cliquez sur **Autorisations**.</span><span class="sxs-lookup"><span data-stu-id="7b39c-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="7b39c-129">Ajoutez le groupe **Administrateurs** local sur le serveur qui héberge le partage de fichiers, accordez les droits d’**Autorisation : Contrôle intégral, Changement et Lecture**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7b39c-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="7b39c-130">Cliquez de nouveau sur **OK** et notez le chemin d’accès réseau.</span><span class="sxs-lookup"><span data-stu-id="7b39c-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="7b39c-131">Cliquez sur **Terminé** pour fermer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="7b39c-131">Click **Done** to close the wizard.</span></span>
    
     ![Partage d’onglets pour partager des dossiers.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  


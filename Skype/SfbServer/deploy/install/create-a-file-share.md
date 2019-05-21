---
title: Création d’un partage de fichiers dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Résumé: Découvrez comment créer un partage de fichiers Windows Server dans le cadre de l’installation de Skype entreprise Server. Télécharger une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverMicrosoft pour:.'
ms.openlocfilehash: d6a34ad4807948a5580fc572628a4fd6333dd9f8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292164"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a><span data-ttu-id="2def1-104">Création d’un partage de fichiers dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2def1-104">Create a file share in Skype for Business Server</span></span>
 
<span data-ttu-id="2def1-105">**Résumé:** Découvrez comment créer un partage de fichiers Windows Server dans le cadre de l’installation de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="2def1-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server.</span></span> <span data-ttu-id="2def1-106">Télécharger une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Microsoft pour:.</span><span class="sxs-lookup"><span data-stu-id="2def1-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="2def1-107">Pour pouvoir échanger des fichiers, Skype entreprise Server a besoin d’un partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="2def1-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="2def1-108">La création d’un partage de fichiers est l’étape 2 sur 8 du processus d’installation de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="2def1-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server.</span></span> <span data-ttu-id="2def1-109">Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="2def1-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="2def1-110">Cependant, vous devez exécuter les étapes 6, 7 et 8 dans l’ordre, et après les étapes 1 à 5 comme indiqué sur le diagramme.</span><span class="sxs-lookup"><span data-stu-id="2def1-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="2def1-111">Pour plus d’informations sur la planification du partage de fichiers, voir la [Configuration requise pour Skype entreprise Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [serveur requise pour skype entreprise Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2def1-111">For planning details about file share, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![Schéma de vue d’ensemble](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="2def1-113">Créer un partage de fichiers basique</span><span class="sxs-lookup"><span data-stu-id="2def1-113">Create a basic file share</span></span>

<span data-ttu-id="2def1-114">Cette section vous indique comment créer un partage de fichiers Serveur Windows basique.</span><span class="sxs-lookup"><span data-stu-id="2def1-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="2def1-115">Un partage de fichiers Windows Server de base est pris en charge avec Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="2def1-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="2def1-116">Toutefois, elle ne fournit pas explicitement une haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="2def1-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="2def1-117">Pour un environnement à haute disponibilité, un partage de fichiers Système de fichiers distribué DFS est recommandé.</span><span class="sxs-lookup"><span data-stu-id="2def1-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="2def1-118">Pour plus d’informations sur le partage de fichiers et le système de fichiers DFS de haute disponibilité, voir [planifier une disponibilité élevée et une reprise après sinistre dans Skype entreprise Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="2def1-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2def1-119">Windows Server 2012 R2 a effectué un bond de géant en offrant des solutions de partage de fichiers de type SAN (Storage Area Network) à l’aide de la plateforme Windows Server.</span><span class="sxs-lookup"><span data-stu-id="2def1-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="2def1-120">Comparée à un dispositif SAN traditionnel, une solution de stockage Windows Server 2012 R2 permet de diviser les coûts par deux sans réelles incidences sur les performances.</span><span class="sxs-lookup"><span data-stu-id="2def1-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="2def1-121">Pour plus d’informations sur les options de partage de fichiers dans Windows Server 2012 R2, voir le livre blanc téléchargeable [Windows server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span><span class="sxs-lookup"><span data-stu-id="2def1-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="2def1-122">Regardez la vidéo des étapes pour **créer un partage de fichiers** :</span><span class="sxs-lookup"><span data-stu-id="2def1-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="2def1-123">Créer un partage de fichiers basique</span><span class="sxs-lookup"><span data-stu-id="2def1-123">Create a basic file share</span></span>

1. <span data-ttu-id="2def1-124">Connectez-vous à l’ordinateur qui hébergera le partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="2def1-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="2def1-125">Cliquez avec le bouton droit sur le dossier que vous souhaitez partager, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="2def1-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="2def1-126">Sélectionnez l’onglet **Partage**, puis cliquez sur **Partage avancé**.</span><span class="sxs-lookup"><span data-stu-id="2def1-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="2def1-127">Cliquez sur **Partager ce dossier**.</span><span class="sxs-lookup"><span data-stu-id="2def1-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="2def1-128">Cliquez sur **Autorisations**.</span><span class="sxs-lookup"><span data-stu-id="2def1-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="2def1-129">Ajoutez le groupe **Administrateurs** local sur le serveur qui héberge le partage de fichiers, accordez les droits d’**Autorisation : Contrôle intégral, Changement et Lecture**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2def1-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="2def1-130">Cliquez de nouveau sur **OK** et notez le chemin d’accès réseau.</span><span class="sxs-lookup"><span data-stu-id="2def1-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="2def1-131">Cliquez sur **Terminé** pour fermer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="2def1-131">Click **Done** to close the wizard.</span></span>
    
     ![Partage d’onglets pour partager des dossiers.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
><span data-ttu-id="2def1-133">Si le magasin de fichiers est hébergé sur un partage DFS, le message d’avertissement suivant est reçu:</span><span class="sxs-lookup"><span data-stu-id="2def1-133">If the file store is hosted on a DFS share, the following warning will be received:</span></span>

<span data-ttu-id="2def1-134">AVERTISSEMENT: impossible d’accéder aux autorisations de partage\\<domain>\<pour «share>».</span><span class="sxs-lookup"><span data-stu-id="2def1-134">Warning: Unable to access share permissions for "\\<domain>\<share>".</span></span>

><span data-ttu-id="2def1-135">Cela peut se produire si vous n’êtes pas administrateur sur le serveur de fichiers ou s’il s’agit d’un partage du système de fichiers DFS.</span><span class="sxs-lookup"><span data-stu-id="2def1-135">This is expected if you are not an administrator on the file server, or if this is a Distributed File System (DFS) share.</span></span> <span data-ttu-id="2def1-136">Si les autorisations de partage ont déjà été configurées, cet avertissement peut être ignoré.</span><span class="sxs-lookup"><span data-stu-id="2def1-136">If the share permissions have already been configured, this warning can be ignored.</span></span> <span data-ttu-id="2def1-137">S’il s’agit d’un nouveau partage, reportez-vous à la documentation pour plus d’informations sur la configuration manuelle des autorisations de partage.</span><span class="sxs-lookup"><span data-stu-id="2def1-137">If it is a new share, refer to the documentation for details on manually configuring share permissions.</span></span>

><span data-ttu-id="2def1-138">En raison de l’incapacité d’accéder aux autorisations de partage sur un partage DFS, Skype entreprise Server ne peut pas définir explicitement les groupes sur le partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="2def1-138">Due to the inability to access the share permissions on a DFS share, Skype for Business Server will not be able to explicitly set groups on the file share.</span></span> <span data-ttu-id="2def1-139">Pour vous assurer que les composants de Skype entreprise Server peuvent accéder au partage de fichiers avec les autorisations appropriées, assurez-vous que les groupes RTC suivants sont ajoutés en plus des autorisations de partage de niveau supérieur.</span><span class="sxs-lookup"><span data-stu-id="2def1-139">To ensure Skype for Business Server components can access the file share with the appropriate permissions, ensure the following RTC groups are added with Change level share permissions in addition to the local Administrators with Full Control share permissions.</span></span>

<span data-ttu-id="2def1-140">RTCHSUniversalServices RTCComponentUniversalServices RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2def1-140">RTCHSUniversalServices RTCComponentUniversalServices RTCUniversalServerAdmins</span></span>

---
title: Conditions préalables et configuration de l’outil stress and performance de Skype outil
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Conditions requises ou conditions préalables pour l’outil de contrainte et de performances de Skype entreprise Server 2015. Comment installer ou configurer l’outil stress and performance.
ms.openlocfilehash: 9389feedb21948604b1ea68319c5fc068a561679
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005979"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="b7dc7-104">Conditions préalables et configuration de l’outil stress and performance de Skype outil</span><span class="sxs-lookup"><span data-stu-id="b7dc7-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="b7dc7-105">Conditions requises ou conditions préalables pour l’outil de contrainte et de performances de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-105">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool.</span></span> <span data-ttu-id="b7dc7-106">Comment installer ou configurer l’outil stress and performance.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-106">How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="b7dc7-107">Nous avons les sections suivantes relatives à la configuration matérielle, logicielle et système requise avant d’exécuter l’outil stress and performance :</span><span class="sxs-lookup"><span data-stu-id="b7dc7-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="b7dc7-108">Configuration matérielle requise pour le client</span><span class="sxs-lookup"><span data-stu-id="b7dc7-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="b7dc7-109">Configuration logicielle requise pour le client</span><span class="sxs-lookup"><span data-stu-id="b7dc7-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="b7dc7-110">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="b7dc7-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="b7dc7-111">De plus, nous avons également une section ci-dessous pour l' [installation de l’outil de contrainte et de performances de Skype entreprise Server 2015](prerequisites-and-setup.md#Installing)</span><span class="sxs-lookup"><span data-stu-id="b7dc7-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="b7dc7-112">Configuration matérielle requise pour le client</span><span class="sxs-lookup"><span data-stu-id="b7dc7-112">Client hardware requirements</span></span>
<span data-ttu-id="b7dc7-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="b7dc7-113"><a name="ClientHardwareReqs"> </a></span></span>

<span data-ttu-id="b7dc7-114">Lors de l’exécution de l’outil stress and performance sur votre déploiement de Skype entreprise Server 2015, vous aurez au minimum besoin de ces exigences matérielles pour tous les 4500 utilisateurs de votre test :</span><span class="sxs-lookup"><span data-stu-id="b7dc7-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="b7dc7-115">carte réseau 1 Gigabit</span><span class="sxs-lookup"><span data-stu-id="b7dc7-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="b7dc7-116">8 Go de mémoire vive (RAM)</span><span class="sxs-lookup"><span data-stu-id="b7dc7-116">8 GB RAM</span></span>
    
- <span data-ttu-id="b7dc7-117">2 processeurs double cœur</span><span class="sxs-lookup"><span data-stu-id="b7dc7-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="b7dc7-118">Configuration logicielle requise pour le client</span><span class="sxs-lookup"><span data-stu-id="b7dc7-118">Client software requirements</span></span>
<span data-ttu-id="b7dc7-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="b7dc7-119"><a name="ClientSoftwareReqs"> </a></span></span>

<span data-ttu-id="b7dc7-120">Les systèmes d’exploitation pris en charge pour l’outil stress and performance sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="b7dc7-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="b7dc7-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="b7dc7-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="b7dc7-122">Windows Server 2008 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="b7dc7-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="b7dc7-123">En outre, les ordinateurs doivent respecter les configurations logicielles suivantes :</span><span class="sxs-lookup"><span data-stu-id="b7dc7-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="b7dc7-124">L’infrastructure Microsoft .NET 4,5 est installée.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="b7dc7-125">Téléchargez .net 4,5 Framework ici.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/download/details.aspx?id=30653)
    
- <span data-ttu-id="b7dc7-126">Vous aurez besoin de la fonctionnalité expérience utilisateur activée dans Windows.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="b7dc7-127">Microsoft Visual C++ 2013 (x64) doit être installé.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="b7dc7-128">Téléchargez Visual C++ 2013 ici</span><span class="sxs-lookup"><span data-stu-id="b7dc7-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/download/details.aspx?id=40784)
    
- <span data-ttu-id="b7dc7-129">Vous allez avoir besoin du déploiement de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="b7dc7-130">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="b7dc7-130">Configuration requirements</span></span>
<span data-ttu-id="b7dc7-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="b7dc7-131"><a name="ConfigReqs"> </a></span></span>

<span data-ttu-id="b7dc7-132">Vous aurez besoin de ces configurations supplémentaires pour exécuter l’outil stress and performance :</span><span class="sxs-lookup"><span data-stu-id="b7dc7-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="b7dc7-133">Vous devez vous connecter au serveur en tant que membre du groupe d’administrateurs de domaine ou local.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="b7dc7-134">Vous ne pouvez pas installer l’outil de création d’utilisateur Skype entreprise Server 2015 (UserProvisioningTool. exe) sur un serveur frontal ou un serveur Standard Edition où les comptes d’utilisateur doivent résider.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="b7dc7-135">Lorsque l’outil de création d’utilisateur est exécuté plusieurs fois, chaque utilisateur activé pour les communications unifiées de Microsoft doit disposer d’un numéro de téléphone unique.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="b7dc7-136">La taille du fichier d’échange doit être gérée par les systèmes ou doit être au moins égale à 1,5 fois la quantité de RAM dans le système informatique.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="b7dc7-137">Installation de l’outil de contrainte et de performances de Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="b7dc7-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="b7dc7-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="b7dc7-138"><a name="Installing"> </a></span></span>

<span data-ttu-id="b7dc7-139">L’installation ne peut pas être simplifiée.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-139">Installing couldn't be simpler.</span></span> <span data-ttu-id="b7dc7-140">Vous devez exécuter le fichier Windows Installer, **CapacityPlanningTool. msi**, sur chaque ordinateur client que vous allez utiliser pour simuler le trafic des utilisateurs et sur un serveur frontal dans chaque pool où vous allez créer des utilisateurs et des contacts.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-140">You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="b7dc7-141">Pour télécharger le fichier. msi, ainsi que les exemples de scripts mentionnés dans nos autres articles, accédez au lien du centre [de téléchargement : Skype entreprise Server 2015, stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="b7dc7-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  


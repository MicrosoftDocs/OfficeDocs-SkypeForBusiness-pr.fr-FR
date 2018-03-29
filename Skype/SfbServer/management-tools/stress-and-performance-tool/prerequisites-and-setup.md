---
title: Conditions préalables et configuration pour l'outil Stress and Performance de Skype Entreprise
ms.author: heidip
author: microsoftheidi
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Configuration requise ou conditions préalables pour l'outil Stress and Performance de Skype Entreprise Server 2015. Comment installer ou configurer l'outil Stress and Performance.
ms.openlocfilehash: 9e59c314b546cf0e9204047eb9a86096fbdd5cd8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="80868-104">Conditions préalables et configuration pour l'outil Stress and Performance de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="80868-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="80868-105">Configuration requise ou conditions préalables pour l'outil Stress and Performance de Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="80868-105">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool.</span></span> <span data-ttu-id="80868-106">Comment installer ou configurer l'outil Stress and Performance.</span><span class="sxs-lookup"><span data-stu-id="80868-106">How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="80868-107">Vous devez avoir pris connaissance des sections suivantes relatives à la configuration matérielle, logicielle et système requise avant d'exécuter l'outil Stress and Performance :</span><span class="sxs-lookup"><span data-stu-id="80868-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="80868-108">Configuration matérielle cliente requise</span><span class="sxs-lookup"><span data-stu-id="80868-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="80868-109">Configuration logicielle du client</span><span class="sxs-lookup"><span data-stu-id="80868-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="80868-110">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="80868-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="80868-111">En outre, une section concernant [l'installation de l'outil Stress and Performance de Skype Entreprise Server 2015](prerequisites-and-setup.md#Installing) figure ci-dessous</span><span class="sxs-lookup"><span data-stu-id="80868-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="80868-112">Configuration matérielle client requise</span><span class="sxs-lookup"><span data-stu-id="80868-112">Client hardware requirements</span></span>
<span data-ttu-id="80868-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="80868-113"></span></span>

<span data-ttu-id="80868-114">Lorsque vous exécutez l'outil Stress and Performance pour votre déploiement Skype Entreprise Server 2015, vous devez disposer, au minimum, de la configuration matérielle suivante, pour chaque groupe de 4500 utilisateurs de votre test :</span><span class="sxs-lookup"><span data-stu-id="80868-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="80868-115">carte réseau 1 gigabit</span><span class="sxs-lookup"><span data-stu-id="80868-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="80868-116">8 Go de mémoire vive</span><span class="sxs-lookup"><span data-stu-id="80868-116">8 GB RAM</span></span>
    
- <span data-ttu-id="80868-117">2 processeurs double cœur</span><span class="sxs-lookup"><span data-stu-id="80868-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="80868-118">Configuration logicielle client requise</span><span class="sxs-lookup"><span data-stu-id="80868-118">Client software requirements</span></span>
<span data-ttu-id="80868-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="80868-119"></span></span>

<span data-ttu-id="80868-120">Systèmes d'exploitation pris en charge par l'outil Stress and Performance :</span><span class="sxs-lookup"><span data-stu-id="80868-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="80868-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="80868-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="80868-122">Windows Server 2008 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="80868-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="80868-123">De plus, l'ordinateur requiert la configuration logicielle suivante :</span><span class="sxs-lookup"><span data-stu-id="80868-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="80868-124">Microsoft .NET 4.5 Framework doit être installé.</span><span class="sxs-lookup"><span data-stu-id="80868-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="80868-125">Téléchargez le .net 4.5 Framework ici.</span><span class="sxs-lookup"><span data-stu-id="80868-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=30653)
    
- <span data-ttu-id="80868-126">Dans Windows, la fonctionnalité Expérience utilisateur doit être activée.</span><span class="sxs-lookup"><span data-stu-id="80868-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="80868-127">Microsoft Visual C++ 2013 (x64) doit être installé.</span><span class="sxs-lookup"><span data-stu-id="80868-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="80868-128">Télécharger Visual C++ 2013 ici</span><span class="sxs-lookup"><span data-stu-id="80868-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=40784)
    
- <span data-ttu-id="80868-129">Un déploiement réussi de Skype Entreprise Server 2015 est requis.</span><span class="sxs-lookup"><span data-stu-id="80868-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="80868-130">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="80868-130">Configuration requirements</span></span>
<span data-ttu-id="80868-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="80868-131"></span></span>

<span data-ttu-id="80868-132">Pour que l'outil Stress and Performance fonctionne correctement, les configurations supplémentaires suivantes sont nécessaires :</span><span class="sxs-lookup"><span data-stu-id="80868-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="80868-133">Connectez-vous au serveur en tant que membre du groupe du domaine ou de l'administrateur local.</span><span class="sxs-lookup"><span data-stu-id="80868-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="80868-134">Vous ne pouvez pas installer l'outil Création d'utilisateur de Skype Entreprise Server 2015 sur n'importe quel serveur frontal ou Standard Edition où les comptes de l'utilisateur résideront.</span><span class="sxs-lookup"><span data-stu-id="80868-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="80868-135">Lorsque l'outil Création d'utilisateur est exécuté plusieurs fois, chaque utilisateur actif pour Microsoft Unified Communications doit présenter un numéro de téléphone unique.</span><span class="sxs-lookup"><span data-stu-id="80868-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="80868-136">La taille de fichier de la page doit être gérée par les systèmes ou correspondre à au moins 1,5 fois la quantité de mémoire vive du système de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="80868-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="80868-137">Installation de l'outil Stress and Performance de Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="80868-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="80868-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="80868-138"></span></span>

<span data-ttu-id="80868-139">L'installation ne pourrait être plus facile.</span><span class="sxs-lookup"><span data-stu-id="80868-139">Installing couldn't be simpler.</span></span> <span data-ttu-id="80868-140">Exécutez le fichier d'installation Windows, **CapacityPlanningTool.msi**, sur tous les ordinateurs client qui seront utilisés pour simuler le trafic utilisateur et sur un serveur frontal de chaque pool où des utilisateurs et des contacts seront créés.</span><span class="sxs-lookup"><span data-stu-id="80868-140">You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="80868-141">Pour télécharger le fichier .msi, ainsi que des exemples de scripts mentionné dans nos autres articles, visitez le lien Centre de téléchargement : [Skype pour Business Server 2015, Stress et outil de performances](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="80868-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  


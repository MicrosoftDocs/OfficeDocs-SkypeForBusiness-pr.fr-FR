---
title: Pourquoi ne puis-je pas utiliser le centre d’administration de Skype entreprise Online pour le moment?
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c182d564-1674-4491-b1d9-3e0cb657d4cc
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.lync.lac.TenantInMigration
ms.custom:
- Setup
description: 'Apprenez et ne pouvez pas utiliser le centre d’administration Skype entreprise, ainsi que d’autres fonctionnalités lorsque votre service est migré vers un autre centre de données Microsoft. '
ms.openlocfilehash: 006caf6542abfeeb38e9563b6866fb119c47b88f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284876"
---
# <a name="why-cant-i-use-the-skype-for-business-online-admin-center-right-now"></a><span data-ttu-id="5870f-103">Pourquoi ne puis-je pas utiliser le centre d’administration de Skype entreprise Online pour le moment?</span><span class="sxs-lookup"><span data-stu-id="5870f-103">Why can't I use the Skype for Business Online admin center right now?</span></span>

<span data-ttu-id="5870f-104">Nous savons qu’il n’est pas possible d’effectuer votre travail, donc nous expliquons ce qui se passe ici et pourquoi il est utile d’en attendre.</span><span class="sxs-lookup"><span data-stu-id="5870f-104">We know it's frustrating when you can't get your work done, so we're going to explain what's happening here and why it'll be worth the wait.</span></span> 
  
<span data-ttu-id="5870f-105">Pour commencer, voici l’explication technique:</span><span class="sxs-lookup"><span data-stu-id="5870f-105">First, here's the technical explanation:</span></span>
  
<span data-ttu-id="5870f-106">Nous effectuons la migration de votre service Skype entreprise Online (c’est-à-dire, les utilisateurs et les paramètres d’organisation) vers un autre centre de travail Microsoft qui vous rapproche.</span><span class="sxs-lookup"><span data-stu-id="5870f-106">We're migrating your Skype for Business Online service (meaning your users and organizational settings) to another Microsoft datacenter that's closer to you.</span></span> <span data-ttu-id="5870f-107">Cela permet d’améliorer votre service et de réduire la latence.</span><span class="sxs-lookup"><span data-stu-id="5870f-107">This will improve your service and reduce latency.</span></span> 
  
<span data-ttu-id="5870f-108">Pour plus d’informations techniques, voir [pendant et après le déplacement de vos données]( https://go.microsoft.com/fwlink/?LinkId=526418).</span><span class="sxs-lookup"><span data-stu-id="5870f-108">For more technical details, see [During and after your data move]( https://go.microsoft.com/fwlink/?LinkId=526418).</span></span>
  
## <a name="ok-so-what-does-that-mean"></a><span data-ttu-id="5870f-109">Alors, qu’est-ce que cela signifie?</span><span class="sxs-lookup"><span data-stu-id="5870f-109">OK, so what does that mean?</span></span>

<span data-ttu-id="5870f-110">Tout d’abord, nous allons répartir quelques termes.</span><span class="sxs-lookup"><span data-stu-id="5870f-110">First, let's break down a few terms.</span></span>
  
- <span data-ttu-id="5870f-111">**Centre de données** Il s’agit de l’emplacement physique où sont stockés les informations issues de votre organisation Office 365, telles que vos fichiers et messages électroniques.</span><span class="sxs-lookup"><span data-stu-id="5870f-111">**Data center** This is the physical location where the information from your Office 365 organization is stored, such as your files and email messages.</span></span> <span data-ttu-id="5870f-112">Pour plus d’informations sur les centres de données Office 365, voir[cet article](https://www.microsoft.com/online/legal/v2/?docid=25).</span><span class="sxs-lookup"><span data-stu-id="5870f-112">If you really want to dig in to what Office 365 datacenters are, check out[this article](https://www.microsoft.com/online/legal/v2/?docid=25).</span></span>
    
- <span data-ttu-id="5870f-113">**Migration** en Ce n’est pas le même que le déplacement.</span><span class="sxs-lookup"><span data-stu-id="5870f-113">**Migrating** This is pretty much the same as "moving."</span></span> <span data-ttu-id="5870f-114">Dans ce cas, cela signifie que nous transférons vos utilisateurs et vos paramètres Skype entreprise Online d’un datacenter vers un autre qui vous rapproche de votre service.</span><span class="sxs-lookup"><span data-stu-id="5870f-114">In this case, it means we're moving your Skype for Business Online users and settings from one datacenter to another that's closer to you to improve your service.</span></span>
    
- <span data-ttu-id="5870f-115">**Latence** Il s’agit du délai nécessaire pour accéder au centre d’administration Office 365, apporter des modifications aux paramètres, puis enregistrer les modifications.</span><span class="sxs-lookup"><span data-stu-id="5870f-115">**Latency** This is amount of time it takes you to access the Office 365 admin center, make a settings change, and then save those changes.</span></span>
    
- <span data-ttu-id="5870f-116">**ID de corrélation** Vous avez peut-être remarqué que cela figure dans le message que vous venez d’obtenir.</span><span class="sxs-lookup"><span data-stu-id="5870f-116">**Correlation ID** You might have seen this listed in the message you just came from.</span></span> <span data-ttu-id="5870f-117">Ces informations sont utilisées par les ingénieurs du support Microsoft pour vous aider à résoudre une erreur.</span><span class="sxs-lookup"><span data-stu-id="5870f-117">This information is used by Microsoft support engineers to help you troubleshoot an error.</span></span> <span data-ttu-id="5870f-118">Si vous contactez le support technique de Microsoft, vous pouvez être invité à entrer l’ID de corrélation.</span><span class="sxs-lookup"><span data-stu-id="5870f-118">If you contact Microsoft support, you might be asked for the Correlation ID.</span></span>
    
<span data-ttu-id="5870f-119">Tout cela signifie que nous sommes en train de déplacer tous vos utilisateurs et services Skype entreprise Online vers un autre emplacement proche de vous.</span><span class="sxs-lookup"><span data-stu-id="5870f-119">So what this all means is we're in the process of moving all your Skype for Business Online users and service settings to another location that's closer to you.</span></span> <span data-ttu-id="5870f-120">Plus il est proche.</span><span class="sxs-lookup"><span data-stu-id="5870f-120">The closer the better.</span></span> <span data-ttu-id="5870f-121">La bonne nouvelle est qu’après ce laps de temps, votre service Skype entreprise Online s’améliorera.</span><span class="sxs-lookup"><span data-stu-id="5870f-121">The good news is that after this short period of time, your Skype for Business Online service will improve.</span></span>
  
![Migration de service dans Office 365](../images/77502071-36fe-4833-a5ff-3b9ca7676542.png)
  
## <a name="what-skype-for-business-online-features-will-still-work"></a><span data-ttu-id="5870f-123">Quelles sont les fonctionnalités Skype entreprise Online qui continuent à fonctionner?</span><span class="sxs-lookup"><span data-stu-id="5870f-123">What Skype for Business Online features will still work?</span></span>

<span data-ttu-id="5870f-124">Même si vous ne pouvez pas accéder au centre d’administration de Skype entreprise Online, les fonctionnalités de Skype entreprise Online suivantes continuent de fonctionner pendant la migration:</span><span class="sxs-lookup"><span data-stu-id="5870f-124">Although you won't be able to access the Skype for Business Online admin center, the following Skype for Business Online features will still work during the migration:</span></span>
  
- <span data-ttu-id="5870f-125">Réunions en ligne</span><span class="sxs-lookup"><span data-stu-id="5870f-125">Online meetings</span></span>
    
- <span data-ttu-id="5870f-126">Informations de présence</span><span class="sxs-lookup"><span data-stu-id="5870f-126">Presence information</span></span>
    
## <a name="can-i-get-other-work-done"></a><span data-ttu-id="5870f-127">Puis-je effectuer d’autres tâches?</span><span class="sxs-lookup"><span data-stu-id="5870f-127">Can I get other work done?</span></span>

<span data-ttu-id="5870f-128">Garantit.</span><span class="sxs-lookup"><span data-stu-id="5870f-128">Sure.</span></span> <span data-ttu-id="5870f-129">Lors de la migration de votre service Skype entreprise Online, vous pouvez toujours utiliser les autres centres d’administration dans Office 365 (par exemple, les centres d’administration Office 365 et Exchange).</span><span class="sxs-lookup"><span data-stu-id="5870f-129">While we're migrating your Skype for Business Online service, you can still use the other admin centers in Office 365 (for example, the Office 365 and Exchange admin centers).</span></span> <span data-ttu-id="5870f-130">En revanche, avec le centre d’administration Skype entreprise Online, vous ne pourrez pas utiliser les applets de commande PowerShell distants de Skype entreprise Online lors de la migration.</span><span class="sxs-lookup"><span data-stu-id="5870f-130">However, along with the Skype for Business Online admin center, you won't be able to use the Skype for Business Online Remote PowerShell cmdlets during the migration.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="5870f-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5870f-131">Related topics</span></span>
[<span data-ttu-id="5870f-132">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="5870f-132">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="5870f-133">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="5870f-133">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 

---
title: Impossible d’utiliser le Skype pour le centre d’administration Business Online maintenant ?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c182d564-1674-4491-b1d9-3e0cb657d4cc
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.lync.lac.TenantInMigration
ms.custom:
- Setup
description: 'Découvrez ce que pouvez et ne pouvez pas utiliser dans Skype pour Business admin center et d’autres fonctionnalités lorsque votre service est en cours de migration vers un autre centre de données de Microsoft. '
ms.openlocfilehash: b591b5352ba0d676462fabbaac446ecc769e204a
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="why-cant-i-use-the-skype-for-business-online-admin-center-right-now"></a><span data-ttu-id="0c4fe-103">Impossible d’utiliser le Skype pour le centre d’administration Business Online maintenant ?</span><span class="sxs-lookup"><span data-stu-id="0c4fe-103">Why can't I use the Skype for Business Online admin center right now?</span></span>

<span data-ttu-id="0c4fe-104">Nous savons qu’il est frustrant lorsque vous ne parvenez pas votre travail, nous allons expliquer ce qui se passe ici et pourquoi il serait intéressant de l’attente.</span><span class="sxs-lookup"><span data-stu-id="0c4fe-104">We know it's frustrating when you can't get your work done, so we're going to explain what's happening here and why it'll be worth the wait.</span></span> 
  
<span data-ttu-id="0c4fe-105">Tout d’abord, voici les explications techniques :</span><span class="sxs-lookup"><span data-stu-id="0c4fe-105">First, here's the technical explanation:</span></span>
  
<span data-ttu-id="0c4fe-106">Nous allons migrer votre Skype pour le service Business Online (ce qui signifie que les utilisateurs et les paramètres d’organisation) vers un autre centre de données Microsoft, ce qui est plus proche de vous.</span><span class="sxs-lookup"><span data-stu-id="0c4fe-106">We're migrating your Skype for Business Online service (meaning your users and organizational settings) to another Microsoft datacenter that's closer to you.</span></span> <span data-ttu-id="0c4fe-107">Cela va améliorer votre service et diminuer la latence.</span><span class="sxs-lookup"><span data-stu-id="0c4fe-107">This will improve your service and reduce latency.</span></span> 
  
<span data-ttu-id="0c4fe-108">Pour plus de détails techniques, consultez [pendant et après le déplacement de données]( https://go.microsoft.com/fwlink/?LinkId=526418).</span><span class="sxs-lookup"><span data-stu-id="0c4fe-108">For more technical details, see [During and after your data move]( https://go.microsoft.com/fwlink/?LinkId=526418).</span></span>
  
## <a name="ok-so-what-does-that-mean"></a><span data-ttu-id="0c4fe-109">OK, ce que cela veut-il dire ?</span><span class="sxs-lookup"><span data-stu-id="0c4fe-109">OK, so what does that mean?</span></span>

<span data-ttu-id="0c4fe-110">Tout d’abord, nous allons décomposer quelques termes.</span><span class="sxs-lookup"><span data-stu-id="0c4fe-110">First, let's break down a few terms.</span></span>
  
- <span data-ttu-id="0c4fe-111">**Centre de données** Il s’agit de l’emplacement physique où sont stockées les informations de votre organisation d’Office 365, telles que vos fichiers et vos messages électroniques.</span><span class="sxs-lookup"><span data-stu-id="0c4fe-111">**Data center** This is the physical location where the information from your Office 365 organization is stored, such as your files and email messages.</span></span> <span data-ttu-id="0c4fe-112">Si vous voulez vraiment Explorer ce que sont les centres de données Office 365, consultez[cet article](https://www.microsoft.com/online/legal/v2/?docid=25).</span><span class="sxs-lookup"><span data-stu-id="0c4fe-112">If you really want to dig in to what Office 365 datacenters are, check out[this article](https://www.microsoft.com/online/legal/v2/?docid=25).</span></span>
    
- <span data-ttu-id="0c4fe-113">**Migration de** Cela est quasiment identique à « déplacement ».</span><span class="sxs-lookup"><span data-stu-id="0c4fe-113">**Migrating** This is pretty much the same as "moving."</span></span> <span data-ttu-id="0c4fe-114">Dans ce cas, cela signifie que nous progressions votre Skype pour des utilisateurs professionnels en ligne et les paramètres à partir d’un centre de données à un autre qui est plus proche de vous permettre d’améliorer votre service.</span><span class="sxs-lookup"><span data-stu-id="0c4fe-114">In this case, it means we're moving your Skype for Business Online users and settings from one datacenter to another that's closer to you to improve your service.</span></span>
    
- <span data-ttu-id="0c4fe-115">**Temps de latence** Il s’agit de la quantité de temps nécessaire pour accéder au centre d’administration Office 365, vérifiez les paramètres de modifier et enregistrer ces modifications.</span><span class="sxs-lookup"><span data-stu-id="0c4fe-115">**Latency** This is amount of time it takes you to access the Office 365 admin center, make a settings change, and then save those changes.</span></span>
    
- <span data-ttu-id="0c4fe-116">**ID de corrélation** Vous avez peut-être vu que cette répertorié dans le message que d'où vous venez.</span><span class="sxs-lookup"><span data-stu-id="0c4fe-116">**Correlation ID** You might have seen this listed in the message you just came from.</span></span> <span data-ttu-id="0c4fe-117">Ces informations sont utilisées par les ingénieurs du support technique Microsoft pour vous aider à résoudre les problèmes liés à une erreur.</span><span class="sxs-lookup"><span data-stu-id="0c4fe-117">This information is used by Microsoft support engineers to help you troubleshoot an error.</span></span> <span data-ttu-id="0c4fe-118">Si vous contactez le support technique de Microsoft, vous serez peut-être invité pour l’ID de corrélation.</span><span class="sxs-lookup"><span data-stu-id="0c4fe-118">If you contact Microsoft support, you might be asked for the Correlation ID.</span></span>
    
<span data-ttu-id="0c4fe-119">Afin que tout cela signifie est nous sommes en mouvement tout votre Skype pour les utilisateurs professionnels en ligne et service de paramètres vers un autre emplacement qui est plus proche de vous.</span><span class="sxs-lookup"><span data-stu-id="0c4fe-119">So what this all means is we're in the process of moving all your Skype for Business Online users and service settings to another location that's closer to you.</span></span> <span data-ttu-id="0c4fe-120">Le plus proche possible.</span><span class="sxs-lookup"><span data-stu-id="0c4fe-120">The closer the better.</span></span> <span data-ttu-id="0c4fe-121">La bonne nouvelle est qu’après ce laps de temps, votre Skype pour Business Online service améliorera.</span><span class="sxs-lookup"><span data-stu-id="0c4fe-121">The good news is that after this short period of time, your Skype for Business Online service will improve.</span></span>
  
![Migration de service d’Office 365](../images/77502071-36fe-4833-a5ff-3b9ca7676542.png)
  
## <a name="what-skype-for-business-online-features-will-still-work"></a><span data-ttu-id="0c4fe-123">Ce que Skype pour les fonctionnalités d’entreprise en ligne continuent de fonctionner ?</span><span class="sxs-lookup"><span data-stu-id="0c4fe-123">What Skype for Business Online features will still work?</span></span>

<span data-ttu-id="0c4fe-124">Bien que vous ne pourrez pas accéder à la Skype pour le centre d’administration en ligne de Business, le suivant Skype pour les fonctionnalités d’entreprise en ligne continuent de fonctionner pendant la migration :</span><span class="sxs-lookup"><span data-stu-id="0c4fe-124">Although you won't be able to access the Skype for Business Online admin center, the following Skype for Business Online features will still work during the migration:</span></span>
  
- <span data-ttu-id="0c4fe-125">Réunions en ligne</span><span class="sxs-lookup"><span data-stu-id="0c4fe-125">Online meetings</span></span>
    
- <span data-ttu-id="0c4fe-126">Informations de présence</span><span class="sxs-lookup"><span data-stu-id="0c4fe-126">Presence information</span></span>
    
## <a name="can-i-get-other-work-done"></a><span data-ttu-id="0c4fe-127">Puis-je obtenir des travaux effectués ?</span><span class="sxs-lookup"><span data-stu-id="0c4fe-127">Can I get other work done?</span></span>

<span data-ttu-id="0c4fe-128">Assurer.</span><span class="sxs-lookup"><span data-stu-id="0c4fe-128">Sure.</span></span> <span data-ttu-id="0c4fe-129">Alors que nous allons migrer votre Skype pour service d’entreprise en ligne, vous pouvez toujours utiliser les autres centres d’administrateur dans Office 365 (par exemple, les centres administrateur Office 365 et Exchange).</span><span class="sxs-lookup"><span data-stu-id="0c4fe-129">While we're migrating your Skype for Business Online service, you can still use the other admin centers in Office 365 (for example, the Office 365 and Exchange admin centers).</span></span> <span data-ttu-id="0c4fe-130">Toutefois, avec le Skype pour Business Online Centre d’administration, vous ne pourrez utiliser le Skype pour les applets de commande PowerShell distant de professionnels en ligne pendant la migration.</span><span class="sxs-lookup"><span data-stu-id="0c4fe-130">However, along with the Skype for Business Online admin center, you won't be able to use the Skype for Business Online Remote PowerShell cmdlets during the migration.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="0c4fe-131">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="0c4fe-131">Related topics</span></span>
[<span data-ttu-id="0c4fe-132">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="0c4fe-132">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="0c4fe-133">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="0c4fe-133">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
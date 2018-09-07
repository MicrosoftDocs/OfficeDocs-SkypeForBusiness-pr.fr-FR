---
title: Impossible d’utiliser le Skype pour le centre d’administration Business Online maintenant ?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c182d564-1674-4491-b1d9-3e0cb657d4cc
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
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
description: 'Découvrez vous pouvez et ne pouvez pas utiliser de Skype pour le centre d’administration des entreprises et d’autres fonctionnalités lorsque votre service est en cours de migration vers un autre centre de données de Microsoft. '
ms.openlocfilehash: d0b67b7193d6bc56617807d3c14d1196ee66d76c
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854198"
---
# <a name="why-cant-i-use-the-skype-for-business-online-admin-center-right-now"></a><span data-ttu-id="268b2-103">Impossible d’utiliser le Skype pour le centre d’administration Business Online maintenant ?</span><span class="sxs-lookup"><span data-stu-id="268b2-103">Why can't I use the Skype for Business Online admin center right now?</span></span>

<span data-ttu-id="268b2-104">Nous savons qu’il est frustrant lorsque vous ne peuvent pas obtenir votre travail, nous allons expliquer que se passe-t-il et pourquoi il va perdre.</span><span class="sxs-lookup"><span data-stu-id="268b2-104">We know it's frustrating when you can't get your work done, so we're going to explain what's happening here and why it'll be worth the wait.</span></span> 
  
<span data-ttu-id="268b2-105">Tout d’abord, voici les explications techniques :</span><span class="sxs-lookup"><span data-stu-id="268b2-105">First, here's the technical explanation:</span></span>
  
<span data-ttu-id="268b2-106">Nous utilisons la migration de votre Skype pour Business Online service (ce qui signifie que vos utilisateurs et les paramètres d’organisation) vers un autre centre de données Microsoft qui est plus proche de vous.</span><span class="sxs-lookup"><span data-stu-id="268b2-106">We're migrating your Skype for Business Online service (meaning your users and organizational settings) to another Microsoft datacenter that's closer to you.</span></span> <span data-ttu-id="268b2-107">Cela améliorer votre service et réduire la latence.</span><span class="sxs-lookup"><span data-stu-id="268b2-107">This will improve your service and reduce latency.</span></span> 
  
<span data-ttu-id="268b2-108">Pour plus de détails techniques, voir [pendant et après le déplacement de vos données]( https://go.microsoft.com/fwlink/?LinkId=526418).</span><span class="sxs-lookup"><span data-stu-id="268b2-108">For more technical details, see [During and after your data move]( https://go.microsoft.com/fwlink/?LinkId=526418).</span></span>
  
## <a name="ok-so-what-does-that-mean"></a><span data-ttu-id="268b2-109">OK, ainsi que qui signifie ?</span><span class="sxs-lookup"><span data-stu-id="268b2-109">OK, so what does that mean?</span></span>

<span data-ttu-id="268b2-110">Tout d’abord, analysons quelques termes.</span><span class="sxs-lookup"><span data-stu-id="268b2-110">First, let's break down a few terms.</span></span>
  
- <span data-ttu-id="268b2-111">**Centre de données** Il s’agit de l’emplacement physique où sont stockées les informations à partir de votre organisation Office 365, telles que vos fichiers et les messages électroniques.</span><span class="sxs-lookup"><span data-stu-id="268b2-111">**Data center** This is the physical location where the information from your Office 365 organization is stored, such as your files and email messages.</span></span> <span data-ttu-id="268b2-112">Si vous souhaitez vraiment Explorer quelles sont les centres de données Office 365, consultez[cet article](https://www.microsoft.com/online/legal/v2/?docid=25).</span><span class="sxs-lookup"><span data-stu-id="268b2-112">If you really want to dig in to what Office 365 datacenters are, check out[this article](https://www.microsoft.com/online/legal/v2/?docid=25).</span></span>
    
- <span data-ttu-id="268b2-113">**La migration** Il est pratiquement identique à « déplacement ».</span><span class="sxs-lookup"><span data-stu-id="268b2-113">**Migrating** This is pretty much the same as "moving."</span></span> <span data-ttu-id="268b2-114">Dans ce cas, cela signifie que nous allons déplacement votre Skype pour les utilisateurs professionnels en ligne et les paramètres à partir d’un centre de données vers un autre plus proche de vous permettent d’améliorer votre service.</span><span class="sxs-lookup"><span data-stu-id="268b2-114">In this case, it means we're moving your Skype for Business Online users and settings from one datacenter to another that's closer to you to improve your service.</span></span>
    
- <span data-ttu-id="268b2-115">**Latence** Il s’agit de la quantité de temps nécessaire pour accéder au centre d’administration d’Office 365, vérifiez les paramètres de modification, puis enregistrer ces modifications.</span><span class="sxs-lookup"><span data-stu-id="268b2-115">**Latency** This is amount of time it takes you to access the Office 365 admin center, make a settings change, and then save those changes.</span></span>
    
- <span data-ttu-id="268b2-116">**ID de corrélation** Vous avez peut-être vu que cela répertoriées dans le message que provient uniquement.</span><span class="sxs-lookup"><span data-stu-id="268b2-116">**Correlation ID** You might have seen this listed in the message you just came from.</span></span> <span data-ttu-id="268b2-117">Cette information est utilisée par les ingénieurs du support technique Microsoft pour vous aider à résoudre les problèmes d’une erreur.</span><span class="sxs-lookup"><span data-stu-id="268b2-117">This information is used by Microsoft support engineers to help you troubleshoot an error.</span></span> <span data-ttu-id="268b2-118">Si vous contactez le support technique Microsoft, vous pouvez être invité pour l’ID de corrélation.</span><span class="sxs-lookup"><span data-stu-id="268b2-118">If you contact Microsoft support, you might be asked for the Correlation ID.</span></span>
    
<span data-ttu-id="268b2-119">Afin que tout cela signifie What ' s nous sommes en mouvement tous vos Skype pour les utilisateurs professionnels en ligne et de service de paramètres vers un autre emplacement qui est plus proche de vous.</span><span class="sxs-lookup"><span data-stu-id="268b2-119">So what this all means is we're in the process of moving all your Skype for Business Online users and service settings to another location that's closer to you.</span></span> <span data-ttu-id="268b2-120">Le plus proche possible.</span><span class="sxs-lookup"><span data-stu-id="268b2-120">The closer the better.</span></span> <span data-ttu-id="268b2-121">La bonne nouvelle est qu’après ce laps de temps, votre Skype pour le service Business en ligne à améliorer.</span><span class="sxs-lookup"><span data-stu-id="268b2-121">The good news is that after this short period of time, your Skype for Business Online service will improve.</span></span>
  
![Migration de service dans Office 365](../images/77502071-36fe-4833-a5ff-3b9ca7676542.png)
  
## <a name="what-skype-for-business-online-features-will-still-work"></a><span data-ttu-id="268b2-123">Ce que Skype pour les fonctionnalités en ligne Business continuent de fonctionner ?</span><span class="sxs-lookup"><span data-stu-id="268b2-123">What Skype for Business Online features will still work?</span></span>

<span data-ttu-id="268b2-124">Bien que vous ne pourrez pas accéder à la Skype Business Online Centre d’administration, la Skype suivante pour les fonctionnalités en ligne Business continuent de fonctionner pendant la migration :</span><span class="sxs-lookup"><span data-stu-id="268b2-124">Although you won't be able to access the Skype for Business Online admin center, the following Skype for Business Online features will still work during the migration:</span></span>
  
- <span data-ttu-id="268b2-125">Réunions en ligne</span><span class="sxs-lookup"><span data-stu-id="268b2-125">Online meetings</span></span>
    
- <span data-ttu-id="268b2-126">Informations de présence</span><span class="sxs-lookup"><span data-stu-id="268b2-126">Presence information</span></span>
    
## <a name="can-i-get-other-work-done"></a><span data-ttu-id="268b2-127">Puis-je obtenir des travaux effectués ?</span><span class="sxs-lookup"><span data-stu-id="268b2-127">Can I get other work done?</span></span>

<span data-ttu-id="268b2-128">Assurer.</span><span class="sxs-lookup"><span data-stu-id="268b2-128">Sure.</span></span> <span data-ttu-id="268b2-129">Pendant que nous utilisons la migration de votre Skype pour le service Business en ligne, vous pouvez toujours utiliser les autres centres d’administration dans Office 365 (par exemple, les centres d’administration Office 365 et Exchange).</span><span class="sxs-lookup"><span data-stu-id="268b2-129">While we're migrating your Skype for Business Online service, you can still use the other admin centers in Office 365 (for example, the Office 365 and Exchange admin centers).</span></span> <span data-ttu-id="268b2-130">Toutefois, ainsi que Skype pour le centre d’administration Business Online, vous ne pourrez utiliser le Skype pour les applets de commande PowerShell à distance en ligne Business pendant la migration.</span><span class="sxs-lookup"><span data-stu-id="268b2-130">However, along with the Skype for Business Online admin center, you won't be able to use the Skype for Business Online Remote PowerShell cmdlets during the migration.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="268b2-131">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="268b2-131">Related topics</span></span>
[<span data-ttu-id="268b2-132">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="268b2-132">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="268b2-133">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="268b2-133">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
---
title: Qualité des appels Analytique d’appeler utiliser pour résoudre les problèmes de mauvaise Skype pour entreprise
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Analytique d’appeler plus d’informations sur les périphériques, les réseaux et connectivité permet de résoudre les problèmes utilisateur Skype pour les réunions et les appels de l’entreprise.
ms.openlocfilehash: b7f900509506433bd2c863fb6c0c33c4f71f2ab5
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2018
---
# <a name="use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality"></a><span data-ttu-id="2f16b-103">Qualité des appels Analytique d’appeler utiliser pour résoudre les problèmes de mauvaise Skype pour entreprise</span><span class="sxs-lookup"><span data-stu-id="2f16b-103">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>

<span data-ttu-id="2f16b-104">Appel Analytique vous aide à résoudre les problèmes de connexion ou d’appel Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="2f16b-104">Call Analytics helps you to troubleshoot call or connection problems with Skype for Business.</span></span> <span data-ttu-id="2f16b-105">Appel Analytique affiche des informations détaillées sur les périphériques, les réseaux et connectivité pour les appels et les réunions de chaque utilisateur de votre Skype pour le compte de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="2f16b-105">Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Skype for Business account.</span></span> <span data-ttu-id="2f16b-106">Si la génération, du site et client informations ont été ajoutées pour appeler Analytique, elle s’affiche également pour chaque appel et la session.</span><span class="sxs-lookup"><span data-stu-id="2f16b-106">If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session.</span></span> <span data-ttu-id="2f16b-107">Les informations disponibles via l’appel d’Analytique peuvent vous aider à déterminer pourquoi un utilisateur avait un appel médiocre ou expérience de la réunion.</span><span class="sxs-lookup"><span data-stu-id="2f16b-107">Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span></span> 
  
    > [!NOTE]
    > Call Analytics is currently in preview. Text and images described here may not match your experience. 
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a><span data-ttu-id="2f16b-108">Résoudre les problèmes de qualité d’appel à l’aide d’appeler l’Analytique</span><span class="sxs-lookup"><span data-stu-id="2f16b-108">Troubleshoot call quality problems using Call Analytics</span></span>

<span data-ttu-id="2f16b-109">Le niveau d’autorisation qui vous sont assigné détermine le type d’informations que vous avez accès à en appeler un Analytique :</span><span class="sxs-lookup"><span data-stu-id="2f16b-109">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span></span>
  
- <span data-ttu-id="2f16b-110">**Skype pour l’administration de l’entreprise**: vous avez accès à toutes les informations dans Analytique d’appel et le Skype pour le centre d’administration de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="2f16b-110">**Skype for Business admin**: You have access to all the information in Call Analytics and in the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="2f16b-111">**Agent de support technique avec les autorisations de niveau 1**: affiche un ensemble limité de données Analytique d’appeler.</span><span class="sxs-lookup"><span data-stu-id="2f16b-111">**Helpdesk agent with Tier 1 permissions**: You see a limited set of data in Call Analytics.</span></span> <span data-ttu-id="2f16b-112">Vous pouvez résoudre des appels, mais vous allez remettre les problèmes liés aux réunions d’un agent de niveau 2.</span><span class="sxs-lookup"><span data-stu-id="2f16b-112">You can troubleshoot calls, but you'll hand off problems with meetings to a Tier 2 agent.</span></span> <span data-ttu-id="2f16b-113">Vous n’avez pas accès au reste de la Skype pour le centre d’administration de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="2f16b-113">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="2f16b-114">**Agent de support technique avec les autorisations de niveau 2**: vous voir toutes les données disponibles dans l’appel d’Analytique et peut aider à résoudre les problèmes avec les appels et les réunions.</span><span class="sxs-lookup"><span data-stu-id="2f16b-114">**Helpdesk agent with Tier 2 permissions**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings.</span></span> <span data-ttu-id="2f16b-115">Vous n’avez pas accès au reste de la Skype pour le centre d’administration de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="2f16b-115">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
<span data-ttu-id="2f16b-116">Consultez votre Skype pour l’administration de l’entreprise, si vous avez besoin d’aide avec les autorisations.</span><span class="sxs-lookup"><span data-stu-id="2f16b-116">See your Skype for Business admin if you need help with permissions.</span></span>
  
 <span data-ttu-id="2f16b-117">**Analytique d’appeler ouvert comme un agent de support technique de niveau 1 ou niveau 2**</span><span class="sxs-lookup"><span data-stu-id="2f16b-117">**Open Call Analytics as a Tier 1 or Tier 2 helpdesk agent**</span></span>
  
1. <span data-ttu-id="2f16b-118">Accédez au centre d’administration Office 365 et vous connecter en utilisant votre compte de travail ou l’école.</span><span class="sxs-lookup"><span data-stu-id="2f16b-118">Go to the Office 365 admin center and sign in using your work or school account.</span></span> <span data-ttu-id="2f16b-119">Dans votre navigateur web accédez à *https://adminportal.services.skypeforbusiness.com*.</span><span class="sxs-lookup"><span data-stu-id="2f16b-119">Then in your web browser go to *https://adminportal.services.skypeforbusiness.com*.</span></span>
    
2. <span data-ttu-id="2f16b-120">**Recherche d’utilisateur**, commencez à taper une adresse sip ou nom de l’utilisateur dont vous souhaitez résoudre les problèmes et puis sélectionnez l’utilisateur dans la liste les appels.</span><span class="sxs-lookup"><span data-stu-id="2f16b-120">In **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot and then select the user from the list.</span></span>
    
    ![Capture d’écran de la zone de recherche de l’utilisateur d’appeler l’Analytique dans le Skype pour Business Admin Center.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. <span data-ttu-id="2f16b-122">Dans l' **historique des appels**, sélectionnez l’appel ou la réunion que vous souhaitez dépanner.</span><span class="sxs-lookup"><span data-stu-id="2f16b-122">In **Call history**, select the call or meeting that you want to troubleshoot.</span></span>
    
    ![Capture d’écran montre la page de l’historique des appels pour un utilisateur avec des informations telles que les informations de contact de l’utilisateur, un résumé de la qualité de 7 jours et l’activité pour les réunions et les appels et une vue d’ensemble des dates et des heures, les destinataires et qualité audio,](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. <span data-ttu-id="2f16b-124">Sélectionnez l’onglet **Avancé** , puis recherchez des éléments jaunes et rouges qui indiquent des problèmes de connexion ou de qualité médiocre d’appel.</span><span class="sxs-lookup"><span data-stu-id="2f16b-124">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="2f16b-125">Dans les détails de la session pour chaque appel ou d’une réunion, des problèmes mineurs s’affichent en jaune.</span><span class="sxs-lookup"><span data-stu-id="2f16b-125">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="2f16b-126">(Par exemple, dans l’écran suivant, les valeurs sont en jaune pour variation moyenne, variation de Max et les taux de perte de paquet moyenne.) Si un élément est jaune, elle est en dehors de la plage normale et il contribue au problème, mais il n’est probablement pas la cause principale du problème.</span><span class="sxs-lookup"><span data-stu-id="2f16b-126">(For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="2f16b-127">Si quelque chose est rouge, il s’agit d’un problème important, et il est probable que la cause principale de la qualité médiocre d’appel pour cette session.</span><span class="sxs-lookup"><span data-stu-id="2f16b-127">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
    
    ![Capture d’écran montre l’onglet Avancé de l’historique des appels de l’utilisateur avec la section réseau entrant de développé pour afficher que les données de la variation moyenne, max variation et taux de perte de paquet moyenne sont affichées dans une couleur jaune, ce qui signifie qu’ils sont des problèmes mineurs.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
<span data-ttu-id="2f16b-129">Dans de rares cas, la qualité de données d’expérience n’est pas reçue pour les sessions audio.</span><span class="sxs-lookup"><span data-stu-id="2f16b-129">In rare cases, quality of experience data isn't received for audio sessions.</span></span> <span data-ttu-id="2f16b-130">Cela est souvent dû par la suppression de l’appel et la connexion avec le client termine.</span><span class="sxs-lookup"><span data-stu-id="2f16b-130">Often this is caused by the call dropping and connection with the client terminating.</span></span> <span data-ttu-id="2f16b-131">Lorsque cela se produit, la session est « non disponible ».</span><span class="sxs-lookup"><span data-stu-id="2f16b-131">When this occurs, the session rating is "unavailable".</span></span>
  
<span data-ttu-id="2f16b-132">Pour les sessions audio qui n’ont pas la qualité de données d’expérience (QoE), le tableau suivant décrit les principaux problèmes qui relèvent d’une session en tant que « médiocre ».</span><span class="sxs-lookup"><span data-stu-id="2f16b-132">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as "poor."</span></span>
  
|<span data-ttu-id="2f16b-133">**Problème**</span><span class="sxs-lookup"><span data-stu-id="2f16b-133">**Issue**</span></span>|<span data-ttu-id="2f16b-134">**Zone**</span><span class="sxs-lookup"><span data-stu-id="2f16b-134">**Area**</span></span>|<span data-ttu-id="2f16b-135">**Description**</span><span class="sxs-lookup"><span data-stu-id="2f16b-135">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2f16b-136">Appelez le programme d’installation</span><span class="sxs-lookup"><span data-stu-id="2f16b-136">Call setup</span></span>  <br/> |<span data-ttu-id="2f16b-137">Session</span><span class="sxs-lookup"><span data-stu-id="2f16b-137">Session</span></span>  <br/> |<span data-ttu-id="2f16b-138">Le code d’erreur Ms-diag 20 à 29 indique l’échec de la configuration de l’appel.</span><span class="sxs-lookup"><span data-stu-id="2f16b-138">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="2f16b-139">L’utilisateur n’a pas pu joindre l’appel ou la réunion.</span><span class="sxs-lookup"><span data-stu-id="2f16b-139">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="2f16b-140">Réseau audio classées appel médiocre</span><span class="sxs-lookup"><span data-stu-id="2f16b-140">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="2f16b-141">Session</span><span class="sxs-lookup"><span data-stu-id="2f16b-141">Session</span></span>  <br/> |<span data-ttu-id="2f16b-142">Problèmes de qualité de réseau ont été rencontrées dans les domaines de gigue, perte de paquets, de dégradation NMOS, RTT, ou masquées de rapport.</span><span class="sxs-lookup"><span data-stu-id="2f16b-142">Network quality issues were encountered in areas such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio.</span></span> <span data-ttu-id="2f16b-143">Pour plus d’informations sur les conditions utilisées pour classifier les appels médiocres, consultez ce [blog Microsoft valider](https://go.microsoft.com/fwlink/p/?linkid=852133).</span><span class="sxs-lookup"><span data-stu-id="2f16b-143">For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span></span>  <br/> |
|<span data-ttu-id="2f16b-144">Périphérique ne fonctionne ne pas</span><span class="sxs-lookup"><span data-stu-id="2f16b-144">Device not functioning</span></span>  <br/> |<span data-ttu-id="2f16b-145">DISPOSITIF</span><span class="sxs-lookup"><span data-stu-id="2f16b-145">Device</span></span>  <br/> | <span data-ttu-id="2f16b-146">Un périphérique ne fonctionne pas correctement.</span><span class="sxs-lookup"><span data-stu-id="2f16b-146">A device isn't functioning correctly.</span></span> <span data-ttu-id="2f16b-147">Périphérique ne fonctionne ne pas ratios est les suivantes :</span><span class="sxs-lookup"><span data-stu-id="2f16b-147">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="2f16b-148">DeviceRenderNotFunctioningEventRatio > = 0,005</span><span class="sxs-lookup"><span data-stu-id="2f16b-148">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="2f16b-149">DeviceCaptureNotFunctioningEventRatio > = 0,005</span><span class="sxs-lookup"><span data-stu-id="2f16b-149">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="2f16b-150">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="2f16b-150">Related topics</span></span>
[<span data-ttu-id="2f16b-151">Configurer l'analyse des appels Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="2f16b-151">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="2f16b-152">En quoi l'analyse des appels et le tableau de bord de qualité des appels sont-ils différents ?</span><span class="sxs-lookup"><span data-stu-id="2f16b-152">What's the difference between Call Analytics and Call Quality Dashboard?</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
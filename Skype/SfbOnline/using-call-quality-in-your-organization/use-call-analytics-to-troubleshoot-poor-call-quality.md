---
title: Qualité des appels Analytique d’appel utilisées pour résoudre les problèmes d’une mauvaise Skype pour les entreprises
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
description: Utilisez Analytique appeler plus d’informations sur les appareils, réseaux et la connectivité à résoudre les problèmes utilisateur Skype pour les réunions et les appels professionnels.
ms.openlocfilehash: cb887a1c582c9547616c2133c2f175ac634e2da8
ms.sourcegitcommit: 5a0b3fe49b64f08979c89443f66b15827034e755
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/17/2018
---
# <a name="use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality"></a><span data-ttu-id="da26d-103">Qualité des appels Analytique d’appel utilisées pour résoudre les problèmes d’une mauvaise Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="da26d-103">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>

<span data-ttu-id="da26d-104">Appel Analytique vous aide à résoudre les problèmes de connexion ou appel Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="da26d-104">Call Analytics helps you to troubleshoot call or connection problems with Skype for Business.</span></span> <span data-ttu-id="da26d-105">Appel Analytique affiche des informations détaillées sur les périphériques, les réseaux et connectivité pour les appels et les réunions de chaque utilisateur dans votre Skype pour un compte professionnel.</span><span class="sxs-lookup"><span data-stu-id="da26d-105">Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Skype for Business account.</span></span> <span data-ttu-id="da26d-106">Si la création, de sites et des clients informations ont été ajoutées à appeler Analytique, elle s’affichera également pour chaque appel et de la session.</span><span class="sxs-lookup"><span data-stu-id="da26d-106">If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session.</span></span> <span data-ttu-id="da26d-107">Informations disponibles par le biais d’Analytique appel peuvent vous aider à comprendre pourquoi un utilisateur avait un appel médiocre ou l’expérience de la réunion.</span><span class="sxs-lookup"><span data-stu-id="da26d-107">Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="da26d-108">Appel Analytique est actuellement en mode Aperçu.</span><span class="sxs-lookup"><span data-stu-id="da26d-108">Call Analytics is currently in preview.</span></span> <span data-ttu-id="da26d-109">Texte et images décrites ici peut ne pas correspondent votre expérience.</span><span class="sxs-lookup"><span data-stu-id="da26d-109">Text and images described here may not match your experience.</span></span>
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a><span data-ttu-id="da26d-110">Résoudre les problèmes de qualité appel à l’aide d’Analytique d’appel</span><span class="sxs-lookup"><span data-stu-id="da26d-110">Troubleshoot call quality problems using Call Analytics</span></span>

<span data-ttu-id="da26d-111">Le niveau d’autorisation attribué détermine le type d’informations que vous avez accès à dans Analytique des appels :</span><span class="sxs-lookup"><span data-stu-id="da26d-111">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span></span>
  
- <span data-ttu-id="da26d-112">**Skype pour administrateur d’entreprise**: vous avez accès à toutes les informations dans Analytique des appels et le Skype pour le centre d’administration Business.</span><span class="sxs-lookup"><span data-stu-id="da26d-112">**Skype for Business admin**: You have access to all the information in Call Analytics and in the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="da26d-113">**Agent de support technique disposant des autorisations de niveau 1**: vous voyez un ensemble limité de données d’appel d’Analytique.</span><span class="sxs-lookup"><span data-stu-id="da26d-113">**Helpdesk agent with Tier 1 permissions**: You see a limited set of data in Call Analytics.</span></span> <span data-ttu-id="da26d-114">Vous pouvez résoudre les appels, mais vous allez remettre les problèmes liés aux réunions pour un agent de niveau 2.</span><span class="sxs-lookup"><span data-stu-id="da26d-114">You can troubleshoot calls, but you'll hand off problems with meetings to a Tier 2 agent.</span></span> <span data-ttu-id="da26d-115">Vous n’avez pas accès au reste du Skype pour le centre d’administration Business.</span><span class="sxs-lookup"><span data-stu-id="da26d-115">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="da26d-116">**Agent de support technique disposant des autorisations de niveau 2**: vous voir toutes les données disponibles dans Analytique appeler et peuvent aider à résoudre des problèmes avec les appels et les réunions.</span><span class="sxs-lookup"><span data-stu-id="da26d-116">**Helpdesk agent with Tier 2 permissions**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings.</span></span> <span data-ttu-id="da26d-117">Vous n’avez pas accès au reste du Skype pour le centre d’administration Business.</span><span class="sxs-lookup"><span data-stu-id="da26d-117">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
<span data-ttu-id="da26d-118">Consultez votre Skype pour administrateur d’entreprise si vous avez besoin d’aide avec des autorisations.</span><span class="sxs-lookup"><span data-stu-id="da26d-118">See your Skype for Business admin if you need help with permissions.</span></span>
  
 <span data-ttu-id="da26d-119">**Ouvrez Analytique appeler comme un agent de support technique de niveau 1 ou de niveau 2**</span><span class="sxs-lookup"><span data-stu-id="da26d-119">**Open Call Analytics as a Tier 1 or Tier 2 helpdesk agent**</span></span>
  
1. <span data-ttu-id="da26d-120">Accédez au centre d’administration Office 365 et connectez-vous à l’aide de votre compte professionnel ou de l’école.</span><span class="sxs-lookup"><span data-stu-id="da26d-120">Go to the Office 365 admin center and sign in using your work or school account.</span></span> <span data-ttu-id="da26d-121">Accédez à dans votre navigateur web *https://adminportal.services.skypeforbusiness.com*.</span><span class="sxs-lookup"><span data-stu-id="da26d-121">Then in your web browser go to *https://adminportal.services.skypeforbusiness.com*.</span></span>
    
2. <span data-ttu-id="da26d-122">Dans la **Recherche d’un utilisateur**, commencez à taper l’adresse sip ou nom de l’utilisateur dont les appels pour résoudre les problèmes, puis sélectionnez l’utilisateur dans la liste.</span><span class="sxs-lookup"><span data-stu-id="da26d-122">In **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot and then select the user from the list.</span></span>
    
    ![Capture d’écran de la zone de recherche d’un utilisateur d’appeler les Analytique dans le Skype entreprise centre d’administration.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. <span data-ttu-id="da26d-124">Dans l' **historique des appels**, sélectionnez l’appel ou la réunion que vous souhaitez dépanner.</span><span class="sxs-lookup"><span data-stu-id="da26d-124">In **Call history**, select the call or meeting that you want to troubleshoot.</span></span>
    
    ![Capture d’écran montre la page Historique des appels pour un utilisateur avec des informations telles que les informations de contact de l’utilisateur, un résumé de l’activité pour les réunions et les appels et la qualité de 7 jours et une vue d’ensemble des dates et heures, les destinataires et la qualité audio,](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. <span data-ttu-id="da26d-126">Sélectionnez l’onglet **Avancé** , puis recherchez des éléments jaunes et rouges qui indiquent des problèmes de connexion ou de la qualité des appels médiocres.</span><span class="sxs-lookup"><span data-stu-id="da26d-126">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="da26d-127">Dans les détails de session pour chaque appel ou des réunions, des problèmes mineurs s’affichent en jaune.</span><span class="sxs-lookup"><span data-stu-id="da26d-127">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="da26d-128">(Par exemple, dans la capture d’écran suivante, les valeurs sont en jaune pour gigue moyenne et taux de pertes de paquets moyenne gigue Max.) Si un élément est jaune, il est en dehors de la plage normale et il peut contribuer au problème, mais il est peu de chances d’être la cause principale du problème.</span><span class="sxs-lookup"><span data-stu-id="da26d-128">(For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="da26d-129">Si un élément est rouge, il s’agit d’un problème majeur, et il est probable que la cause principale de la qualité des appels médiocres pour cette session.</span><span class="sxs-lookup"><span data-stu-id="da26d-129">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
    
    ![Capture d’écran montre l’onglet Avancé de l’historique d’appel d’un utilisateur avec la section réseau entrant développée pour afficher que les données de gigue moyenne, max gigue et taux de pertes de paquets moyenne sont affichées dans une couleur jaune, ce qui signifie qu’ils sont des problèmes mineurs.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
<span data-ttu-id="da26d-131">Dans les cas rares, qualité de l’expérience de données n’est pas reçue pour les sessions audio.</span><span class="sxs-lookup"><span data-stu-id="da26d-131">In rare cases, quality of experience data isn't received for audio sessions.</span></span> <span data-ttu-id="da26d-132">Souvent, cela est dû à la suppression de l’appel et la connexion avec le client abandonnée.</span><span class="sxs-lookup"><span data-stu-id="da26d-132">Often this is caused by the call dropping and connection with the client terminating.</span></span> <span data-ttu-id="da26d-133">Lorsque cela se produit, l’évaluation de la session est « non disponible ».</span><span class="sxs-lookup"><span data-stu-id="da26d-133">When this occurs, the session rating is "unavailable".</span></span>
  
<span data-ttu-id="da26d-134">Pour les sessions audio qui n’ont pas la qualité des données de l’expérience (QoE), le tableau suivant décrit les principaux problèmes associées à une session en tant que « faible ».</span><span class="sxs-lookup"><span data-stu-id="da26d-134">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as "poor."</span></span>
  
|<span data-ttu-id="da26d-135">**Problème**</span><span class="sxs-lookup"><span data-stu-id="da26d-135">**Issue**</span></span>|<span data-ttu-id="da26d-136">**Zone**</span><span class="sxs-lookup"><span data-stu-id="da26d-136">**Area**</span></span>|<span data-ttu-id="da26d-137">**Description**</span><span class="sxs-lookup"><span data-stu-id="da26d-137">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="da26d-138">Configuration des appels</span><span class="sxs-lookup"><span data-stu-id="da26d-138">Call setup</span></span>  <br/> |<span data-ttu-id="da26d-139">Session</span><span class="sxs-lookup"><span data-stu-id="da26d-139">Session</span></span>  <br/> |<span data-ttu-id="da26d-140">Le code d’erreur Ms-diagnostic 20 à 29 indique l’échec de la configuration de l’appel.</span><span class="sxs-lookup"><span data-stu-id="da26d-140">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="da26d-141">L’utilisateur n’a pas pu participer à l’appel ou la réunion.</span><span class="sxs-lookup"><span data-stu-id="da26d-141">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="da26d-142">Réseau audio classés d’appels médiocres</span><span class="sxs-lookup"><span data-stu-id="da26d-142">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="da26d-143">Session</span><span class="sxs-lookup"><span data-stu-id="da26d-143">Session</span></span>  <br/> |<span data-ttu-id="da26d-144">Problèmes de qualité réseau se sont produites dans des domaines tels que la perte de paquets, gigue, dégradation NMOS, durée aller-retour, ou réparation du rapport.</span><span class="sxs-lookup"><span data-stu-id="da26d-144">Network quality issues were encountered in areas such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio.</span></span> <span data-ttu-id="da26d-145">Pour plus d’informations sur les conditions d’utilisation pour classer les appels médiocres, consultez le [billet de blog de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133).</span><span class="sxs-lookup"><span data-stu-id="da26d-145">For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span></span>  <br/> |
|<span data-ttu-id="da26d-146">Périphérique ne fonctionne ne pas</span><span class="sxs-lookup"><span data-stu-id="da26d-146">Device not functioning</span></span>  <br/> |<span data-ttu-id="da26d-147">APPAREIL</span><span class="sxs-lookup"><span data-stu-id="da26d-147">Device</span></span>  <br/> | <span data-ttu-id="da26d-148">Un périphérique ne fonctionne pas correctement.</span><span class="sxs-lookup"><span data-stu-id="da26d-148">A device isn't functioning correctly.</span></span> <span data-ttu-id="da26d-149">Périphérique ne fonctionne ne pas ratios est les suivants :</span><span class="sxs-lookup"><span data-stu-id="da26d-149">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="da26d-150">DeviceRenderNotFunctioningEventRatio > = 0,005</span><span class="sxs-lookup"><span data-stu-id="da26d-150">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="da26d-151">DeviceCaptureNotFunctioningEventRatio > = 0,005</span><span class="sxs-lookup"><span data-stu-id="da26d-151">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="da26d-152">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="da26d-152">Related topics</span></span>
[<span data-ttu-id="da26d-153">Configurer l'analyse des appels Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="da26d-153">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="da26d-154">Appel Analytique et tableau de bord de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="da26d-154">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
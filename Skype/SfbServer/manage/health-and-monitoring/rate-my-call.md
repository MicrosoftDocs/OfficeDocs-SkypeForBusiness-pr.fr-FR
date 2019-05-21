---
title: Évaluer mon appel dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 'Résumé: en savoir plus sur la fonction taux d’appel de Skype entreprise Server.'
ms.openlocfilehash: e146bba647c9586d96682bf8056417630676726e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279857"
---
# <a name="rate-my-call-in-skype-for-business-server"></a><span data-ttu-id="22d7b-103">Évaluer mon appel dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="22d7b-103">Rate my Call in Skype for Business Server</span></span>

<span data-ttu-id="22d7b-104">**Résumé:** En savoir plus sur la fonction taux d’appel dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="22d7b-104">**Summary:** Learn about the Rate My Call feature in Skype for Business Server.</span></span>

<span data-ttu-id="22d7b-105">Le taux de l’appel est une nouvelle fonctionnalité de Skype entreprise 2015 et 2016 clients sur Windows, qui offre aux entreprises un moyen de faire part de leurs commentaires auprès des utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="22d7b-105">Rate My Call was a new feature in Skype for Business 2015 and 2016 clients on Windows that provides enterprises a way to get feedback from their end-users.</span></span>

<span data-ttu-id="22d7b-106">Le taux de fenêtre d’appel offre un système d’évaluation «Star» et des jetons prédéfinis pour les appels audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="22d7b-106">The Rate My Call window offers a "star" rating system and predefined tokens for audio and video calls.</span></span> <span data-ttu-id="22d7b-107">De plus, les administrateurs peuvent activer un champ personnalisé pour fournir des commentaires.</span><span class="sxs-lookup"><span data-stu-id="22d7b-107">In addition, administrators can enable a custom field to provide feedback.</span></span>

<span data-ttu-id="22d7b-108">Les données Évaluer mon appel qui sont collectées ne sont pas incluses dans un rapport de surveillance existant mais font l’objet d’un rapport de surveillance distinct.</span><span class="sxs-lookup"><span data-stu-id="22d7b-108">Collected Rate My Call data is not currently included in any existing monitoring report, but it has a separate monitoring report.</span></span> <span data-ttu-id="22d7b-109">Les données sont collectées dans des tables SQL accessibles en exécutant des requêtes SQL.</span><span class="sxs-lookup"><span data-stu-id="22d7b-109">Data is collected in SQL tables that can be accessed by running SQL queries.</span></span>

## <a name="rate-my-call-prerequisites"></a><span data-ttu-id="22d7b-110">Configuration requise pour Évaluer mon appel</span><span class="sxs-lookup"><span data-stu-id="22d7b-110">Rate my Call Prerequisites</span></span>

<span data-ttu-id="22d7b-111">Pour que les utilisateurs de votre déploiement Skype entreprise Server puissent accéder à la fonctionnalité taux d’appel, l’ensemble des composants suivants doit être déployé et configuré:</span><span class="sxs-lookup"><span data-stu-id="22d7b-111">Before the users in your Skype for Business Server deployment can access Rate My Call functionality, the following set of components must be deployed and configured:</span></span>

-  <span data-ttu-id="22d7b-112">Vous devez avoir installé Skype entreprise Server (version 9160 ou une version ultérieure).</span><span class="sxs-lookup"><span data-stu-id="22d7b-112">You must have Skype for Business Server installed (version 9160 or higher).</span></span>

- <span data-ttu-id="22d7b-113">Demandez à vos utilisateurs d’installer et d’effectuer une mise à jour vers la dernière version de Skype entreprise et de leur demander d’utiliser l’interface utilisateur Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="22d7b-113">Have your users install and update to the latest version of Skype for Business and also ask them to use the Skype for Business UI.</span></span>

- <span data-ttu-id="22d7b-114">Les utilisateurs doivent être hébergés dans la liste frontale de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="22d7b-114">Users must be homed on the Skype for Business Server Front End pool.</span></span>

- <span data-ttu-id="22d7b-115">Vous devez disposer d’une base de données de surveillance de Skype entreprise Server déployée et associée à vos pools de serveurs Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="22d7b-115">You must have a Skype for Business Server monitoring database deployed and associated to your Skype for Business Server pools.</span></span>

- <span data-ttu-id="22d7b-116">Nous vous recommandons de déployer le Tableau de bord de la qualité des appels (CQD)</span><span class="sxs-lookup"><span data-stu-id="22d7b-116">We recommend deploying Call Quality Dashboard (CQD).</span></span>

## <a name="configure-rate-my-call"></a><span data-ttu-id="22d7b-117">Configurer Évaluer mon appel</span><span class="sxs-lookup"><span data-stu-id="22d7b-117">Configure Rate my Call</span></span>

<span data-ttu-id="22d7b-118">La fonctionnalité taux d’appel est activée par défaut dans la stratégie client avec les paramètres suivants:</span><span class="sxs-lookup"><span data-stu-id="22d7b-118">The Rate My Call feature is enabled by default in the Client policy with the following settings:</span></span>

- <span data-ttu-id="22d7b-119">Évaluer le pourcentage d’affichage de votre appel-10%</span><span class="sxs-lookup"><span data-stu-id="22d7b-119">Rate My Call Display Percentage - 10%</span></span>

- <span data-ttu-id="22d7b-120">Taux d’utilisation de l’option autoriser les commentaires des utilisateurs personnalisés-désactivé</span><span class="sxs-lookup"><span data-stu-id="22d7b-120">Rate My Call Allow Custom User Feedback - disabled</span></span>

<span data-ttu-id="22d7b-121">Il n’y a aucune action requise pour activer la fonctionnalité de base, mais si vous souhaitez un retour personnalisé, vous devez l’activer séparément.</span><span class="sxs-lookup"><span data-stu-id="22d7b-121">There is no action required to enable the base feature, however but if you want custom feedback you will need to enable it separately.</span></span> <span data-ttu-id="22d7b-122">L’applet de commande Windows PowerShell suivante est un exemple d’activation d’un retour d’utilisateur final personnalisé et de la modification de l’intervalle de 10% en 80%.</span><span class="sxs-lookup"><span data-stu-id="22d7b-122">The following Windows PowerShell cmdlet is an example of enabling custom end user feedback and changing the interval from 10% to 80%.</span></span>

```
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 - RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a><span data-ttu-id="22d7b-123">Accès aux données Évaluer mon appel</span><span class="sxs-lookup"><span data-stu-id="22d7b-123">Accessing Rate My Call Data</span></span>

<span data-ttu-id="22d7b-124">Les données des utilisateurs sont recueillies dans deux tables de la base de données d’analyse.</span><span class="sxs-lookup"><span data-stu-id="22d7b-124">Data from users is collected in two tables in the monitoring database.</span></span>

 <span data-ttu-id="22d7b-125">**[QoeMetrics]. [dbo]. [CallQualityFeedbackToken]** -ce tableau contient les résultats de l’interrogation des jetons par les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="22d7b-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - this table contains results of token polling by end users.</span></span>

 <span data-ttu-id="22d7b-126">**[QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef]** -ce tableau contient les définitions des jetons.</span><span class="sxs-lookup"><span data-stu-id="22d7b-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - this table contains token definitions.</span></span>

<span data-ttu-id="22d7b-127">Les définitions de jetons sont codées ainsi :</span><span class="sxs-lookup"><span data-stu-id="22d7b-127">Token definitions are coded as follows:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="22d7b-128">1</span><span class="sxs-lookup"><span data-stu-id="22d7b-128">1</span></span>  <br/> |<span data-ttu-id="22d7b-129">DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="22d7b-129">DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="22d7b-130">2</span><span class="sxs-lookup"><span data-stu-id="22d7b-130">2</span></span>  <br/> | <span data-ttu-id="22d7b-131">ElectronicFeedback</span><span class="sxs-lookup"><span data-stu-id="22d7b-131">ElectronicFeedback</span></span> <br/> |
|<span data-ttu-id="22d7b-132">3</span><span class="sxs-lookup"><span data-stu-id="22d7b-132">3</span></span>  <br/> | <span data-ttu-id="22d7b-133">BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="22d7b-133">BackgroundNoise</span></span> <br/> |
|<span data-ttu-id="22d7b-134">4</span><span class="sxs-lookup"><span data-stu-id="22d7b-134">4</span></span>  <br/> |<span data-ttu-id="22d7b-135">MuffledSpeech</span><span class="sxs-lookup"><span data-stu-id="22d7b-135">MuffledSpeech</span></span>  <br/> |
|<span data-ttu-id="22d7b-136">5</span><span class="sxs-lookup"><span data-stu-id="22d7b-136">5</span></span>  <br/> |<span data-ttu-id="22d7b-137">Écho</span><span class="sxs-lookup"><span data-stu-id="22d7b-137">Echo</span></span>  <br/> |
|<span data-ttu-id="22d7b-138">vingt</span><span class="sxs-lookup"><span data-stu-id="22d7b-138">21</span></span>  <br/> | <span data-ttu-id="22d7b-139">FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="22d7b-139">FrozenVideo</span></span> <br/> |
|<span data-ttu-id="22d7b-140">22</span><span class="sxs-lookup"><span data-stu-id="22d7b-140">22</span></span>  <br/> | <span data-ttu-id="22d7b-141">PixelatedVideo</span><span class="sxs-lookup"><span data-stu-id="22d7b-141">PixelatedVideo</span></span> <br/> |
|<span data-ttu-id="22d7b-142">23</span><span class="sxs-lookup"><span data-stu-id="22d7b-142">23</span></span>  <br/> | <span data-ttu-id="22d7b-143">BlurryImage</span><span class="sxs-lookup"><span data-stu-id="22d7b-143">BlurryImage</span></span> <br/> |
|<span data-ttu-id="22d7b-144">24</span><span class="sxs-lookup"><span data-stu-id="22d7b-144">24</span></span>  <br/> | <span data-ttu-id="22d7b-145">PoorColor</span><span class="sxs-lookup"><span data-stu-id="22d7b-145">PoorColor</span></span> <br/> |
|<span data-ttu-id="22d7b-146">1,25</span><span class="sxs-lookup"><span data-stu-id="22d7b-146">25</span></span>  <br/> | <span data-ttu-id="22d7b-147">DarkVideo</span><span class="sxs-lookup"><span data-stu-id="22d7b-147">DarkVideo</span></span> <br/> |
|<span data-ttu-id="22d7b-148">101</span><span class="sxs-lookup"><span data-stu-id="22d7b-148">101</span></span>  <br/> |<span data-ttu-id="22d7b-149">Audio_SilentLocal</span><span class="sxs-lookup"><span data-stu-id="22d7b-149">Audio_SilentLocal</span></span>  <br/> |
|<span data-ttu-id="22d7b-150">102</span><span class="sxs-lookup"><span data-stu-id="22d7b-150">102</span></span>  <br/> |<span data-ttu-id="22d7b-151">Audio_SilentRemote</span><span class="sxs-lookup"><span data-stu-id="22d7b-151">Audio_SilentRemote</span></span>  <br/> |
|<span data-ttu-id="22d7b-152">103</span><span class="sxs-lookup"><span data-stu-id="22d7b-152">103</span></span>  <br/> |<span data-ttu-id="22d7b-153">Audio_Echo</span><span class="sxs-lookup"><span data-stu-id="22d7b-153">Audio_Echo</span></span>  <br/> |
|<span data-ttu-id="22d7b-154">104</span><span class="sxs-lookup"><span data-stu-id="22d7b-154">104</span></span>  <br/> |<span data-ttu-id="22d7b-155">Audio_BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="22d7b-155">Audio_BackgroundNoise</span></span>  <br/> |
|<span data-ttu-id="22d7b-156">105</span><span class="sxs-lookup"><span data-stu-id="22d7b-156">105</span></span>  <br/> |<span data-ttu-id="22d7b-157">Audio_LowSound</span><span class="sxs-lookup"><span data-stu-id="22d7b-157">Audio_LowSound</span></span>  <br/> |
|<span data-ttu-id="22d7b-158">106</span><span class="sxs-lookup"><span data-stu-id="22d7b-158">106</span></span>  <br/> |<span data-ttu-id="22d7b-159">Audio_Dropped</span><span class="sxs-lookup"><span data-stu-id="22d7b-159">Audio_Dropped</span></span>  <br/> |
|<span data-ttu-id="22d7b-160">107</span><span class="sxs-lookup"><span data-stu-id="22d7b-160">107</span></span>  <br/> |<span data-ttu-id="22d7b-161">Audio_DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="22d7b-161">Audio_DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="22d7b-162">108</span><span class="sxs-lookup"><span data-stu-id="22d7b-162">108</span></span>  <br/> |<span data-ttu-id="22d7b-163">Audio_Interrupted</span><span class="sxs-lookup"><span data-stu-id="22d7b-163">Audio_Interrupted</span></span>  <br/> |
|<span data-ttu-id="22d7b-164">109</span><span class="sxs-lookup"><span data-stu-id="22d7b-164">109</span></span>  <br/> |<span data-ttu-id="22d7b-165">Audio_Other</span><span class="sxs-lookup"><span data-stu-id="22d7b-165">Audio_Other</span></span>  <br/> |
|<span data-ttu-id="22d7b-166">201</span><span class="sxs-lookup"><span data-stu-id="22d7b-166">201</span></span>  <br/> |<span data-ttu-id="22d7b-167">Video_NoLocalVideo</span><span class="sxs-lookup"><span data-stu-id="22d7b-167">Video_NoLocalVideo</span></span>  <br/> |
|<span data-ttu-id="22d7b-168">202</span><span class="sxs-lookup"><span data-stu-id="22d7b-168">202</span></span>  <br/> |<span data-ttu-id="22d7b-169">Video_NoRemoteVideo</span><span class="sxs-lookup"><span data-stu-id="22d7b-169">Video_NoRemoteVideo</span></span>  <br/> |
|<span data-ttu-id="22d7b-170">203</span><span class="sxs-lookup"><span data-stu-id="22d7b-170">203</span></span>  <br/> |<span data-ttu-id="22d7b-171">Video_LowQuality</span><span class="sxs-lookup"><span data-stu-id="22d7b-171">Video_LowQuality</span></span>  <br/> |
|<span data-ttu-id="22d7b-172">204</span><span class="sxs-lookup"><span data-stu-id="22d7b-172">204</span></span>  <br/> |<span data-ttu-id="22d7b-173">Video_FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="22d7b-173">Video_FrozenVideo</span></span>  <br/> |
|<span data-ttu-id="22d7b-174">205</span><span class="sxs-lookup"><span data-stu-id="22d7b-174">205</span></span>  <br/> |<span data-ttu-id="22d7b-175">Video_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="22d7b-175">Video_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="22d7b-176">206</span><span class="sxs-lookup"><span data-stu-id="22d7b-176">206</span></span>  <br/> |<span data-ttu-id="22d7b-177">Video_DarkVideo</span><span class="sxs-lookup"><span data-stu-id="22d7b-177">Video_DarkVideo</span></span>  <br/> |
|<span data-ttu-id="22d7b-178">207</span><span class="sxs-lookup"><span data-stu-id="22d7b-178">207</span></span>  <br/> |<span data-ttu-id="22d7b-179">Video_NoAudioSync</span><span class="sxs-lookup"><span data-stu-id="22d7b-179">Video_NoAudioSync</span></span>  <br/> |
|<span data-ttu-id="22d7b-180">208</span><span class="sxs-lookup"><span data-stu-id="22d7b-180">208</span></span>  <br/> |<span data-ttu-id="22d7b-181">Video_Other</span><span class="sxs-lookup"><span data-stu-id="22d7b-181">Video_Other</span></span>  <br/> |
|<span data-ttu-id="22d7b-182">301</span><span class="sxs-lookup"><span data-stu-id="22d7b-182">301</span></span>  <br/> |<span data-ttu-id="22d7b-183">Pstn_DialPad</span><span class="sxs-lookup"><span data-stu-id="22d7b-183">Pstn_DialPad</span></span>  <br/> |
|<span data-ttu-id="22d7b-184">401</span><span class="sxs-lookup"><span data-stu-id="22d7b-184">401</span></span>  <br/> |<span data-ttu-id="22d7b-185">SS_NoContentLocal</span><span class="sxs-lookup"><span data-stu-id="22d7b-185">SS_NoContentLocal</span></span>  <br/> |
|<span data-ttu-id="22d7b-186">402</span><span class="sxs-lookup"><span data-stu-id="22d7b-186">402</span></span>  <br/> |<span data-ttu-id="22d7b-187">SS_NoContentRemote</span><span class="sxs-lookup"><span data-stu-id="22d7b-187">SS_NoContentRemote</span></span>  <br/> |
|<span data-ttu-id="22d7b-188">403</span><span class="sxs-lookup"><span data-stu-id="22d7b-188">403</span></span>  <br/> |<span data-ttu-id="22d7b-189">SS_CantPresent</span><span class="sxs-lookup"><span data-stu-id="22d7b-189">SS_CantPresent</span></span>  <br/> |
|<span data-ttu-id="22d7b-190">404</span><span class="sxs-lookup"><span data-stu-id="22d7b-190">404</span></span>  <br/> |<span data-ttu-id="22d7b-191">SS_LowQuality</span><span class="sxs-lookup"><span data-stu-id="22d7b-191">SS_LowQuality</span></span>  <br/> |
|<span data-ttu-id="22d7b-192">405</span><span class="sxs-lookup"><span data-stu-id="22d7b-192">405</span></span>  <br/> |<span data-ttu-id="22d7b-193">SS_Freezing</span><span class="sxs-lookup"><span data-stu-id="22d7b-193">SS_Freezing</span></span>  <br/> |
|<span data-ttu-id="22d7b-194">406</span><span class="sxs-lookup"><span data-stu-id="22d7b-194">406</span></span>  <br/> |<span data-ttu-id="22d7b-195">SS_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="22d7b-195">SS_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="22d7b-196">407</span><span class="sxs-lookup"><span data-stu-id="22d7b-196">407</span></span>  <br/> |<span data-ttu-id="22d7b-197">SS_LargeDelay</span><span class="sxs-lookup"><span data-stu-id="22d7b-197">SS_LargeDelay</span></span>  <br/> |
|<span data-ttu-id="22d7b-198">408</span><span class="sxs-lookup"><span data-stu-id="22d7b-198">408</span></span>  <br/> |<span data-ttu-id="22d7b-199">SS_Other</span><span class="sxs-lookup"><span data-stu-id="22d7b-199">SS_Other</span></span>  <br/> |
|<span data-ttu-id="22d7b-200">501</span><span class="sxs-lookup"><span data-stu-id="22d7b-200">501</span></span>  <br/> |<span data-ttu-id="22d7b-201">Reliabilty_Join</span><span class="sxs-lookup"><span data-stu-id="22d7b-201">Reliabilty_Join</span></span>  <br/> |
|<span data-ttu-id="22d7b-202">502</span><span class="sxs-lookup"><span data-stu-id="22d7b-202">502</span></span>  <br/> |<span data-ttu-id="22d7b-203">Reliabilty_Invite</span><span class="sxs-lookup"><span data-stu-id="22d7b-203">Reliabilty_Invite</span></span>  <br/> |

 <span data-ttu-id="22d7b-204">**[QoeMetrics]. [dbo]. [CallQualityFeedback]** Ce tableau présente les résultats de l’interrogation des résultats du vote en étoile et des commentaires des clients s’il est activé.</span><span class="sxs-lookup"><span data-stu-id="22d7b-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** This table contains polling results from "Star" voting and customer feedback if enabled.</span></span>

<span data-ttu-id="22d7b-205">Vous pouvez appeler des données de tables en utilisant une requête **sélection \* à partir de [table.Name]** ou en utilisant Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="22d7b-205">Data from tables can be called by using a **select \* from [Table.Name]** query or by using Microsoft SQL Server Management Studio.</span></span>

<span data-ttu-id="22d7b-206">Les requêtes SQL suivantes sont utilisables :</span><span class="sxs-lookup"><span data-stu-id="22d7b-206">The following SQL queries can be used:</span></span>

 <span data-ttu-id="22d7b-207">**Audio**</span><span class="sxs-lookup"><span data-stu-id="22d7b-207">**Audio**</span></span>

```
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [AudioStream] AS a WITH (NOLOCK) ON -- only look at Audio related feedback
            a.MediaLineLabel = m.MediaLineLabel    
            and a.ConferenceDateTime = m.ConferenceDateTime 
            and a.SessionSeq = m.SessionSeq
            and a.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
            (CallerCqfToken.TokenId < 20 or (CallerCqfToken.TokenId > 100 and CallerCqfToken.TokenId < 200)) -- only look at Audio related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

 <span data-ttu-id="22d7b-208">**Video**</span><span class="sxs-lookup"><span data-stu-id="22d7b-208">**Video**</span></span>

```
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [VideoStream] AS v WITH (NOLOCK) ON -- only look at Video related feedback
            v.MediaLineLabel = m.MediaLineLabel    
            and v.ConferenceDateTime = m.ConferenceDateTime 
            and v.SessionSeq = m.SessionSeq
            and v.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
           ((CallerCqfToken.TokenId > 20 and CallerCqfToken.TokenId < 100) or (CallerCqfToken.TokenId > 200 and CallerCqfToken.TokenId < 300)) -- only look at Video related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

## <a name="updating-token-definitions"></a><span data-ttu-id="22d7b-209">Mise à jour des définitions de jeton</span><span class="sxs-lookup"><span data-stu-id="22d7b-209">Updating Token Definitions</span></span>

<span data-ttu-id="22d7b-210">Les derniers clients Skype entreprise indiquent de nouveaux ID de jetons de\> problèmes (100) qui risquent de ne pas figurer dans votre [QoeMetrics]. [dbo]. Table [CallQualityFeedbackTokenDef].</span><span class="sxs-lookup"><span data-stu-id="22d7b-210">The latest Skype for Business clients report new problem token IDs (\> 100) that may not be present in your [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span> <span data-ttu-id="22d7b-211">Pour mettre à jour la table de base de données avec les définitions de jeton les plus récentes, vous pouvez exécuter la commande SQL suivante sur la base de données d’analyse à l’aide de Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="22d7b-211">To update the database table with the latest token definitions, the below SQL command can be run on the monitoring database using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="22d7b-212">Cette commande remplace toutes les entrées dans le [QoeMetrics]. [dbo]. Table [CallQualityFeedbackTokenDef].</span><span class="sxs-lookup"><span data-stu-id="22d7b-212">This command will replace all entries in the [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span>

```
DELETE FROM [CallQualityFeedbackTokenDef];
INSERT INTO [CallQualityFeedbackTokenDef] (TokenId, TokenDescription) VALUES
    (1,   N'DistortedSpeech'),
    (2,   N'ElectronicFeedback'),
    (3,   N'BackgroundNoise'),
    (4,   N'MuffledSpeech'),
    (5,   N'Echo'),
    (21,  N'FrozenVideo'),
    (22,  N'PixelatedVideo'),
    (23,  N'BlurryImage'),
    (24,  N'PoorColor'),
    (25,  N'DarkVideo'),
    (101, N'Audio_SilentLocal'),
    (102, N'Audio_SilentRemote'),
    (103, N'Audio_Echo'),
    (104, N'Audio_BackgroundNoise'),
    (105, N'Audio_LowSound'),
    (106, N'Audio_Dropped'),
    (107, N'Audio_DistortedSpeech'),
    (108, N'Audio_Interrupted'),
    (109, N'Audio_Other'),
    (201, N'Video_NoLocalVideo'),
    (202, N'Video_NoRemoteVideo'),
    (203, N'Video_LowQuality'),
    (204, N'Video_FrozenVideo'),
    (205, N'Video_StoppedUnexpectedly'),
    (206, N'Video_DarkVideo'),
    (207, N'Video_NoAudioSync'),
    (208, N'Video_Other'),
    (301, N'Pstn_DialPad'),
    (401, N'SS_NoContentLocal'),
    (402, N'SS_NoContentRemote'),
    (403, N'SS_CantPresent'),
    (404, N'SS_LowQuality'),
    (405, N'SS_Freezing'),
    (406, N'SS_StoppedUnexpectedly'),
    (407, N'SS_LargeDelay'),
    (408, N'SS_Other'),
    (501, N'Reliabilty_Join'),
    (502, N'Reliabilty_Invite');
```



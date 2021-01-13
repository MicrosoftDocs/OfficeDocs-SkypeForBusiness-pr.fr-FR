---
title: Évaluer mon appel dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 'Résumé : Découvrez la fonctionnalité Évaluer mon appel dans Skype Entreprise Server.'
ms.openlocfilehash: 597a8213576e7aa2316ace68ed91288475df2a0d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814334"
---
# <a name="rate-my-call-in-skype-for-business-server"></a><span data-ttu-id="e970c-103">Évaluer mon appel dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="e970c-103">Rate my Call in Skype for Business Server</span></span>

<span data-ttu-id="e970c-104">**Résumé :** Découvrez la fonctionnalité Évaluer mon appel dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="e970c-104">**Summary:** Learn about the Rate My Call feature in Skype for Business Server.</span></span>

<span data-ttu-id="e970c-105">Évaluer mon appel est une nouvelle fonctionnalité des clients Skype Entreprise 2015 et 2016 sur Windows qui permet aux entreprises d’obtenir des commentaires de leurs utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="e970c-105">Rate My Call was a new feature in Skype for Business 2015 and 2016 clients on Windows that provides enterprises a way to get feedback from their end-users.</span></span>

<span data-ttu-id="e970c-106">La fenêtre Évaluer mon appel offre un système d’évaluation « étoile » et des jetons prédéfincis pour les appels audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="e970c-106">The Rate My Call window offers a "star" rating system and predefined tokens for audio and video calls.</span></span> <span data-ttu-id="e970c-107">En outre, les administrateurs peuvent activer un champ personnalisé pour fournir des commentaires.</span><span class="sxs-lookup"><span data-stu-id="e970c-107">In addition, administrators can enable a custom field to provide feedback.</span></span>

<span data-ttu-id="e970c-108">Les données Évaluer mon appel collectées ne sont actuellement incluses dans aucun rapport de surveillance existant, mais elles disposent d’un rapport de surveillance distinct.</span><span class="sxs-lookup"><span data-stu-id="e970c-108">Collected Rate My Call data is not currently included in any existing monitoring report, but it has a separate monitoring report.</span></span> <span data-ttu-id="e970c-109">Les données sont collectées dans SQL tables accessibles en exécutant SQL requêtes.</span><span class="sxs-lookup"><span data-stu-id="e970c-109">Data is collected in SQL tables that can be accessed by running SQL queries.</span></span>

## <a name="rate-my-call-prerequisites"></a><span data-ttu-id="e970c-110">Évaluer les conditions préalables de mon appel</span><span class="sxs-lookup"><span data-stu-id="e970c-110">Rate my Call Prerequisites</span></span>

<span data-ttu-id="e970c-111">Pour que les utilisateurs de votre déploiement Skype Entreprise Server accèdent à la fonctionnalité Évaluer mon appel, l’ensemble de composants suivant doit être déployé et configuré :</span><span class="sxs-lookup"><span data-stu-id="e970c-111">Before the users in your Skype for Business Server deployment can access Rate My Call functionality, the following set of components must be deployed and configured:</span></span>

-  <span data-ttu-id="e970c-112">Skype Entreprise Server doit être installé (version 9160 ou supérieure).</span><span class="sxs-lookup"><span data-stu-id="e970c-112">You must have Skype for Business Server installed (version 9160 or higher).</span></span>

- <span data-ttu-id="e970c-113">Demandez à vos utilisateurs d’installer et de mettre à jour la dernière version de Skype Entreprise et de leur demander d’utiliser l’interface utilisateur de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="e970c-113">Have your users install and update to the latest version of Skype for Business and also ask them to use the Skype for Business UI.</span></span>

- <span data-ttu-id="e970c-114">Les utilisateurs doivent être homed sur le pool frontal Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="e970c-114">Users must be homed on the Skype for Business Server Front End pool.</span></span>

- <span data-ttu-id="e970c-115">Une base de données de surveillance Skype Entreprise Server doit être déployée et associée à vos pools Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="e970c-115">You must have a Skype for Business Server monitoring database deployed and associated to your Skype for Business Server pools.</span></span>

- <span data-ttu-id="e970c-116">Nous vous recommandons de déployer le Tableau de bord de qualité des appels (CQD).</span><span class="sxs-lookup"><span data-stu-id="e970c-116">We recommend deploying Call Quality Dashboard (CQD).</span></span>

## <a name="configure-rate-my-call"></a><span data-ttu-id="e970c-117">Configurer Évaluer mon appel</span><span class="sxs-lookup"><span data-stu-id="e970c-117">Configure Rate my Call</span></span>

<span data-ttu-id="e970c-118">La fonctionnalité Évaluer mon appel est activée par défaut dans la stratégie client avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="e970c-118">The Rate My Call feature is enabled by default in the Client policy with the following settings:</span></span>

- <span data-ttu-id="e970c-119">Taux d’affichage de mes appels - 10 %</span><span class="sxs-lookup"><span data-stu-id="e970c-119">Rate My Call Display Percentage - 10%</span></span>

- <span data-ttu-id="e970c-120">Évaluer mon appel autoriser les commentaires des utilisateurs personnalisés - désactivé</span><span class="sxs-lookup"><span data-stu-id="e970c-120">Rate My Call Allow Custom User Feedback - disabled</span></span>

<span data-ttu-id="e970c-121">Toutefois, aucune action n’est requise pour activer la fonctionnalité de base, mais si vous souhaitez des commentaires personnalisés, vous devrez l’activer séparément.</span><span class="sxs-lookup"><span data-stu-id="e970c-121">There is no action required to enable the base feature, however but if you want custom feedback you will need to enable it separately.</span></span> <span data-ttu-id="e970c-122">L’Windows PowerShell suivante est un exemple d’activation des commentaires personnalisés de l’utilisateur final et de la modification de l’intervalle de 10 % à 80 %.</span><span class="sxs-lookup"><span data-stu-id="e970c-122">The following Windows PowerShell cmdlet is an example of enabling custom end user feedback and changing the interval from 10% to 80%.</span></span>

```PowerShell
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 -RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a><span data-ttu-id="e970c-123">Accès à Évaluer mes données d’appel</span><span class="sxs-lookup"><span data-stu-id="e970c-123">Accessing Rate My Call Data</span></span>

<span data-ttu-id="e970c-124">Les données des utilisateurs sont collectées dans deux tables de la base de données de surveillance.</span><span class="sxs-lookup"><span data-stu-id="e970c-124">Data from users is collected in two tables in the monitoring database.</span></span>

 <span data-ttu-id="e970c-125">**[QoeMetrics]. [dbo]. [CallQualityFeedbackToken]** - Ce tableau contient les résultats de l’interrogation des jetons par les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="e970c-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - this table contains results of token polling by end users.</span></span>

 <span data-ttu-id="e970c-126">**[QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef]** - Ce tableau contient des définitions de jeton.</span><span class="sxs-lookup"><span data-stu-id="e970c-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - this table contains token definitions.</span></span>

<span data-ttu-id="e970c-127">Les définitions de jeton sont codées comme suit :</span><span class="sxs-lookup"><span data-stu-id="e970c-127">Token definitions are coded as follows:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e970c-128">1 </span><span class="sxs-lookup"><span data-stu-id="e970c-128">1</span></span>  <br/> |<span data-ttu-id="e970c-129">DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="e970c-129">DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="e970c-130">2 </span><span class="sxs-lookup"><span data-stu-id="e970c-130">2</span></span>  <br/> | <span data-ttu-id="e970c-131">ElectronicFeedback</span><span class="sxs-lookup"><span data-stu-id="e970c-131">ElectronicFeedback</span></span> <br/> |
|<span data-ttu-id="e970c-132">3 </span><span class="sxs-lookup"><span data-stu-id="e970c-132">3</span></span>  <br/> | <span data-ttu-id="e970c-133">BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="e970c-133">BackgroundNoise</span></span> <br/> |
|<span data-ttu-id="e970c-134">4 </span><span class="sxs-lookup"><span data-stu-id="e970c-134">4</span></span>  <br/> |<span data-ttu-id="e970c-135">MuffledSpeech</span><span class="sxs-lookup"><span data-stu-id="e970c-135">MuffledSpeech</span></span>  <br/> |
|<span data-ttu-id="e970c-136">5 </span><span class="sxs-lookup"><span data-stu-id="e970c-136">5</span></span>  <br/> |<span data-ttu-id="e970c-137">Écho</span><span class="sxs-lookup"><span data-stu-id="e970c-137">Echo</span></span>  <br/> |
|<span data-ttu-id="e970c-138"> 21</span><span class="sxs-lookup"><span data-stu-id="e970c-138">21</span></span>  <br/> | <span data-ttu-id="e970c-139">FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="e970c-139">FrozenVideo</span></span> <br/> |
|<span data-ttu-id="e970c-140">22</span><span class="sxs-lookup"><span data-stu-id="e970c-140">22</span></span>  <br/> | <span data-ttu-id="e970c-141">PixelatedVideo</span><span class="sxs-lookup"><span data-stu-id="e970c-141">PixelatedVideo</span></span> <br/> |
|<span data-ttu-id="e970c-142">23</span><span class="sxs-lookup"><span data-stu-id="e970c-142">23</span></span>  <br/> | <span data-ttu-id="e970c-143">BlurryImage</span><span class="sxs-lookup"><span data-stu-id="e970c-143">BlurryImage</span></span> <br/> |
|<span data-ttu-id="e970c-144">24</span><span class="sxs-lookup"><span data-stu-id="e970c-144">24</span></span>  <br/> | <span data-ttu-id="e970c-145">PoorColor</span><span class="sxs-lookup"><span data-stu-id="e970c-145">PoorColor</span></span> <br/> |
|<span data-ttu-id="e970c-146">25</span><span class="sxs-lookup"><span data-stu-id="e970c-146">25</span></span>  <br/> | <span data-ttu-id="e970c-147">DarkVideo</span><span class="sxs-lookup"><span data-stu-id="e970c-147">DarkVideo</span></span> <br/> |
|<span data-ttu-id="e970c-148">101</span><span class="sxs-lookup"><span data-stu-id="e970c-148">101</span></span>  <br/> |<span data-ttu-id="e970c-149">Audio_SilentLocal</span><span class="sxs-lookup"><span data-stu-id="e970c-149">Audio_SilentLocal</span></span>  <br/> |
|<span data-ttu-id="e970c-150">102</span><span class="sxs-lookup"><span data-stu-id="e970c-150">102</span></span>  <br/> |<span data-ttu-id="e970c-151">Audio_SilentRemote</span><span class="sxs-lookup"><span data-stu-id="e970c-151">Audio_SilentRemote</span></span>  <br/> |
|<span data-ttu-id="e970c-152">103</span><span class="sxs-lookup"><span data-stu-id="e970c-152">103</span></span>  <br/> |<span data-ttu-id="e970c-153">Audio_Echo</span><span class="sxs-lookup"><span data-stu-id="e970c-153">Audio_Echo</span></span>  <br/> |
|<span data-ttu-id="e970c-154">104</span><span class="sxs-lookup"><span data-stu-id="e970c-154">104</span></span>  <br/> |<span data-ttu-id="e970c-155">Audio_BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="e970c-155">Audio_BackgroundNoise</span></span>  <br/> |
|<span data-ttu-id="e970c-156">105</span><span class="sxs-lookup"><span data-stu-id="e970c-156">105</span></span>  <br/> |<span data-ttu-id="e970c-157">Audio_LowSound</span><span class="sxs-lookup"><span data-stu-id="e970c-157">Audio_LowSound</span></span>  <br/> |
|<span data-ttu-id="e970c-158">106</span><span class="sxs-lookup"><span data-stu-id="e970c-158">106</span></span>  <br/> |<span data-ttu-id="e970c-159">Audio_Dropped</span><span class="sxs-lookup"><span data-stu-id="e970c-159">Audio_Dropped</span></span>  <br/> |
|<span data-ttu-id="e970c-160">107</span><span class="sxs-lookup"><span data-stu-id="e970c-160">107</span></span>  <br/> |<span data-ttu-id="e970c-161">Audio_DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="e970c-161">Audio_DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="e970c-162">108</span><span class="sxs-lookup"><span data-stu-id="e970c-162">108</span></span>  <br/> |<span data-ttu-id="e970c-163">Audio_Interrupted</span><span class="sxs-lookup"><span data-stu-id="e970c-163">Audio_Interrupted</span></span>  <br/> |
|<span data-ttu-id="e970c-164">109</span><span class="sxs-lookup"><span data-stu-id="e970c-164">109</span></span>  <br/> |<span data-ttu-id="e970c-165">Audio_Other</span><span class="sxs-lookup"><span data-stu-id="e970c-165">Audio_Other</span></span>  <br/> |
|<span data-ttu-id="e970c-166">201</span><span class="sxs-lookup"><span data-stu-id="e970c-166">201</span></span>  <br/> |<span data-ttu-id="e970c-167">Video_NoLocalVideo</span><span class="sxs-lookup"><span data-stu-id="e970c-167">Video_NoLocalVideo</span></span>  <br/> |
|<span data-ttu-id="e970c-168">202</span><span class="sxs-lookup"><span data-stu-id="e970c-168">202</span></span>  <br/> |<span data-ttu-id="e970c-169">Video_NoRemoteVideo</span><span class="sxs-lookup"><span data-stu-id="e970c-169">Video_NoRemoteVideo</span></span>  <br/> |
|<span data-ttu-id="e970c-170">203</span><span class="sxs-lookup"><span data-stu-id="e970c-170">203</span></span>  <br/> |<span data-ttu-id="e970c-171">Video_LowQuality</span><span class="sxs-lookup"><span data-stu-id="e970c-171">Video_LowQuality</span></span>  <br/> |
|<span data-ttu-id="e970c-172">204</span><span class="sxs-lookup"><span data-stu-id="e970c-172">204</span></span>  <br/> |<span data-ttu-id="e970c-173">Video_FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="e970c-173">Video_FrozenVideo</span></span>  <br/> |
|<span data-ttu-id="e970c-174">205</span><span class="sxs-lookup"><span data-stu-id="e970c-174">205</span></span>  <br/> |<span data-ttu-id="e970c-175">Video_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="e970c-175">Video_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="e970c-176">206</span><span class="sxs-lookup"><span data-stu-id="e970c-176">206</span></span>  <br/> |<span data-ttu-id="e970c-177">Video_DarkVideo</span><span class="sxs-lookup"><span data-stu-id="e970c-177">Video_DarkVideo</span></span>  <br/> |
|<span data-ttu-id="e970c-178">207</span><span class="sxs-lookup"><span data-stu-id="e970c-178">207</span></span>  <br/> |<span data-ttu-id="e970c-179">Video_NoAudioSync</span><span class="sxs-lookup"><span data-stu-id="e970c-179">Video_NoAudioSync</span></span>  <br/> |
|<span data-ttu-id="e970c-180">208</span><span class="sxs-lookup"><span data-stu-id="e970c-180">208</span></span>  <br/> |<span data-ttu-id="e970c-181">Video_Other</span><span class="sxs-lookup"><span data-stu-id="e970c-181">Video_Other</span></span>  <br/> |
|<span data-ttu-id="e970c-182">301</span><span class="sxs-lookup"><span data-stu-id="e970c-182">301</span></span>  <br/> |<span data-ttu-id="e970c-183">Pstn_DialPad</span><span class="sxs-lookup"><span data-stu-id="e970c-183">Pstn_DialPad</span></span>  <br/> |
|<span data-ttu-id="e970c-184">401</span><span class="sxs-lookup"><span data-stu-id="e970c-184">401</span></span>  <br/> |<span data-ttu-id="e970c-185">SS_NoContentLocal</span><span class="sxs-lookup"><span data-stu-id="e970c-185">SS_NoContentLocal</span></span>  <br/> |
|<span data-ttu-id="e970c-186">402</span><span class="sxs-lookup"><span data-stu-id="e970c-186">402</span></span>  <br/> |<span data-ttu-id="e970c-187">SS_NoContentRemote</span><span class="sxs-lookup"><span data-stu-id="e970c-187">SS_NoContentRemote</span></span>  <br/> |
|<span data-ttu-id="e970c-188">403</span><span class="sxs-lookup"><span data-stu-id="e970c-188">403</span></span>  <br/> |<span data-ttu-id="e970c-189">SS_CantPresent</span><span class="sxs-lookup"><span data-stu-id="e970c-189">SS_CantPresent</span></span>  <br/> |
|<span data-ttu-id="e970c-190">404</span><span class="sxs-lookup"><span data-stu-id="e970c-190">404</span></span>  <br/> |<span data-ttu-id="e970c-191">SS_LowQuality</span><span class="sxs-lookup"><span data-stu-id="e970c-191">SS_LowQuality</span></span>  <br/> |
|<span data-ttu-id="e970c-192">405</span><span class="sxs-lookup"><span data-stu-id="e970c-192">405</span></span>  <br/> |<span data-ttu-id="e970c-193">SS_Freezing</span><span class="sxs-lookup"><span data-stu-id="e970c-193">SS_Freezing</span></span>  <br/> |
|<span data-ttu-id="e970c-194">406</span><span class="sxs-lookup"><span data-stu-id="e970c-194">406</span></span>  <br/> |<span data-ttu-id="e970c-195">SS_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="e970c-195">SS_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="e970c-196">407</span><span class="sxs-lookup"><span data-stu-id="e970c-196">407</span></span>  <br/> |<span data-ttu-id="e970c-197">SS_LargeDelay</span><span class="sxs-lookup"><span data-stu-id="e970c-197">SS_LargeDelay</span></span>  <br/> |
|<span data-ttu-id="e970c-198">408</span><span class="sxs-lookup"><span data-stu-id="e970c-198">408</span></span>  <br/> |<span data-ttu-id="e970c-199">SS_Other</span><span class="sxs-lookup"><span data-stu-id="e970c-199">SS_Other</span></span>  <br/> |
|<span data-ttu-id="e970c-200">501</span><span class="sxs-lookup"><span data-stu-id="e970c-200">501</span></span>  <br/> |<span data-ttu-id="e970c-201">Reliabilty_Join</span><span class="sxs-lookup"><span data-stu-id="e970c-201">Reliabilty_Join</span></span>  <br/> |
|<span data-ttu-id="e970c-202">502</span><span class="sxs-lookup"><span data-stu-id="e970c-202">502</span></span>  <br/> |<span data-ttu-id="e970c-203">Reliabilty_Invite</span><span class="sxs-lookup"><span data-stu-id="e970c-203">Reliabilty_Invite</span></span>  <br/> |

 <span data-ttu-id="e970c-204">**[QoeMetrics]. [dbo]. [CallQualityFeedback]** Ce tableau contient les résultats des sondages provenant du vote « Étoile » et des commentaires des clients si activés.</span><span class="sxs-lookup"><span data-stu-id="e970c-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** This table contains polling results from "Star" voting and customer feedback if enabled.</span></span>

<span data-ttu-id="e970c-205">Les données des tables peuvent être appelées à l’aide d’une requête **\* select from [Table.Name]** ou à l’aide de Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="e970c-205">Data from tables can be called by using a **select \* from [Table.Name]** query or by using Microsoft SQL Server Management Studio.</span></span>

<span data-ttu-id="e970c-206">Les requêtes SQL suivantes peuvent être utilisées :</span><span class="sxs-lookup"><span data-stu-id="e970c-206">The following SQL queries can be used:</span></span>

 <span data-ttu-id="e970c-207">**Audio**</span><span class="sxs-lookup"><span data-stu-id="e970c-207">**Audio**</span></span>

```SQL
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

 <span data-ttu-id="e970c-208">**Video**</span><span class="sxs-lookup"><span data-stu-id="e970c-208">**Video**</span></span>

```SQL
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

## <a name="updating-token-definitions"></a><span data-ttu-id="e970c-209">Mise à jour des définitions de jeton</span><span class="sxs-lookup"><span data-stu-id="e970c-209">Updating Token Definitions</span></span>

<span data-ttu-id="e970c-210">Les derniers clients Skype Entreprise signalent de nouveaux ID de jeton de problème ( 100) qui ne sont peut-être pas présents dans \> votre [QoeMetrics].[ dbo]. Table [CallQualityFeedbackTokenDef].</span><span class="sxs-lookup"><span data-stu-id="e970c-210">The latest Skype for Business clients report new problem token IDs (\> 100) that may not be present in your [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span> <span data-ttu-id="e970c-211">Pour mettre à jour la table de base de données avec les définitions de jeton les plus récentes, la commande SQL suivante peut être exécuté sur la base de données de surveillance à l’aide Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="e970c-211">To update the database table with the latest token definitions, the below SQL command can be run on the monitoring database using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="e970c-212">Cette commande remplace toutes les entrées de [QoeMetrics]. [dbo]. Table [CallQualityFeedbackTokenDef].</span><span class="sxs-lookup"><span data-stu-id="e970c-212">This command will replace all entries in the [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span>

```SQL
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



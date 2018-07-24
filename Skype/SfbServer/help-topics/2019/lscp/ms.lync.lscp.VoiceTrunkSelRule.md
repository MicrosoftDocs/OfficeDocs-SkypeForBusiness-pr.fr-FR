---
title: Sélection des règles de conversion
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: NOINDEX, NOFOLLOW
description: Voix entreprise requiert que toutes les chaînes de numérotation normaliser au format E.164 pour effectuer la recherche inversée de numéros (RNL). L’homologue de jonction (c’est-à-dire la jonction de passerelle, PBX ou SIP associée) peut exiger que les numéros soient au format de numérotation local. Pour convertir les numéros du format E.164 à un format de numérotation local, vous avez la possibilité de définir une ou plusieurs règles de conversion pour manipuler l’URI de demande avant de l’acheminer vers la jonction homologue. Par exemple, vous pouvez rédiger une règle de conversion destinée à remplacer le préfixe « +44 » au début de la chaîne de numérotation par « 0144 ».
ms.openlocfilehash: c1a8b5e3506eea97e6f9bab7c455eb31d26f4455
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20998987"
---
# <a name="select-translation-rules"></a><span data-ttu-id="df0ae-106">Sélection des règles de conversion</span><span class="sxs-lookup"><span data-stu-id="df0ae-106">Select Translation Rules</span></span>
 
 <span data-ttu-id="df0ae-107">Voix entreprise requiert que toutes les chaînes de numérotation normaliser au format E.164 pour effectuer la recherche inversée de numéros (RNL).</span><span class="sxs-lookup"><span data-stu-id="df0ae-107">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="df0ae-108">L’homologue de jonction (c’est-à-dire la jonction de passerelle, PBX ou SIP associée) peut exiger que les numéros soient au format de numérotation local.</span><span class="sxs-lookup"><span data-stu-id="df0ae-108">The trunk peer (that is, the associated gateway, PBX, or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="df0ae-109">Pour convertir les numéros du format E.164 à un format de numérotation local, vous avez la possibilité de définir une ou plusieurs règles de conversion pour manipuler l’URI de demande avant de l’acheminer vers la jonction homologue.</span><span class="sxs-lookup"><span data-stu-id="df0ae-109">To translate numbers from E.164 format to a local dialing format, you can optionally define one or more translation rules to manipulate the Request URI before routing it to the trunk peer.</span></span> <span data-ttu-id="df0ae-110">Par exemple, vous pouvez rédiger une règle de conversion destinée à remplacer le préfixe « +44 » au début de la chaîne de numérotation par « 0144 ».</span><span class="sxs-lookup"><span data-stu-id="df0ae-110">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="df0ae-111">La possibilité d’associer une ou plusieurs règles de traduction à une configuration de jonction Enterprise Voice est destinée à être utilisé en guise d’alternative à la configuration des règles de traduction sur l’homologue de jonction.</span><span class="sxs-lookup"><span data-stu-id="df0ae-111">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="df0ae-112">N’associez pas de règles de traduction à une configuration de jonction Enterprise Voice si vous avez configuré les règles de traduction sur l’homologue de jonction, car les deux règles peuvent entrer en conflit.</span><span class="sxs-lookup"><span data-stu-id="df0ae-112">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span> 
  
<span data-ttu-id="df0ae-113">Pour utiliser une règle de conversion existante, sélectionnez une règle dans la liste, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="df0ae-113">To use an existing translation rule, click a rule in the list and then click **OK**.</span></span>
  
 
  


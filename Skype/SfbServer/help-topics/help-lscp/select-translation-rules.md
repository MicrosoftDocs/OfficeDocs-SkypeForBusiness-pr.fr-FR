---
title: Sélection des règles de conversion
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
description: Voix entreprise nécessite que toutes les chaînes de numérotation soient normalisées au format E. 164 pour pouvoir effectuer une recherche de numéro inverse (RNL). L’homologue de jonction (c’est-à-dire la jonction de passerelle, PBX ou SIP associée) peut exiger que les numéros soient au format de numérotation local. Pour convertir les numéros du format E.164 à un format de numérotation local, vous avez la possibilité de définir une ou plusieurs règles de conversion pour manipuler l’URI de demande avant de l’acheminer vers la jonction homologue. Par exemple, vous pouvez rédiger une règle de conversion destinée à remplacer le préfixe « +44 » au début de la chaîne de numérotation par « 0144 ».
ms.openlocfilehash: 1825b2c234a6d2c0f1ab46ae0e62245ef54c9421
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822107"
---
# <a name="select-translation-rules"></a><span data-ttu-id="04a67-106">Sélection des règles de conversion</span><span class="sxs-lookup"><span data-stu-id="04a67-106">Select Translation Rules</span></span>
 
 <span data-ttu-id="04a67-107">Voix entreprise nécessite que toutes les chaînes de numérotation soient normalisées au format E. 164 pour pouvoir effectuer une recherche de numéro inverse (RNL).</span><span class="sxs-lookup"><span data-stu-id="04a67-107">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="04a67-108">L’homologue de jonction (c’est-à-dire la jonction de passerelle, PBX ou SIP associée) peut exiger que les numéros soient au format de numérotation local.</span><span class="sxs-lookup"><span data-stu-id="04a67-108">The trunk peer (that is, the associated gateway, PBX, or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="04a67-109">Pour convertir les numéros du format E.164 à un format de numérotation local, vous avez la possibilité de définir une ou plusieurs règles de conversion pour manipuler l’URI de demande avant de l’acheminer vers la jonction homologue.</span><span class="sxs-lookup"><span data-stu-id="04a67-109">To translate numbers from E.164 format to a local dialing format, you can optionally define one or more translation rules to manipulate the Request URI before routing it to the trunk peer.</span></span> <span data-ttu-id="04a67-110">Par exemple, vous pouvez rédiger une règle de conversion destinée à remplacer le préfixe « +44 » au début de la chaîne de numérotation par « 0144 ».</span><span class="sxs-lookup"><span data-stu-id="04a67-110">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="04a67-111">La possibilité d’associer une ou plusieurs règles de traduction à une configuration de Trunk vocale d’entreprise est conçue pour être utilisée comme alternative à la configuration de règles de traduction sur l’homologue de Trunk.</span><span class="sxs-lookup"><span data-stu-id="04a67-111">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="04a67-112">N’associez pas de règles de traduction à une configuration de Trunk vocale d’entreprise si vous avez configuré des règles de traduction sur le Trunk homologue, car les deux règles peuvent entrer en conflit.</span><span class="sxs-lookup"><span data-stu-id="04a67-112">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span> 
  
<span data-ttu-id="04a67-113">Pour utiliser une règle de conversion existante, sélectionnez une règle dans la liste, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="04a67-113">To use an existing translation rule, click a rule in the list and then click **OK**.</span></span>
  
<span data-ttu-id="04a67-114">Pour plus d’informations sur les différentes procédures que vous pouvez effectuer à l’aide du panneau de configuration Skype entreprise Server, reportez-vous à la rubrique [gestion de Skype entreprise server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="04a67-114">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  


---
title: Règle de traduction entrer une expression régulière
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceRuleRegexEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ee83724-b399-4f8d-8f6d-4b53a26296b4
description: Dans le champ respecter ce modèle, spécifiez le modèle qui sera utilisé pour correspondre aux numéros à traduire. Dans le champ règle de traduction, spécifiez un modèle pour le format des nombres traduits. Par exemple, si vous entrez ^\+(\d{9}\d +) $ dans le champ respecter ce modèle et 011 $1 dans le champ règle de traduction, la règle traduira + 441235551010 en 011441235551010.
ms.openlocfilehash: b2797d8c37e666d86eb3b25cdcd43f069eb25498
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821936"
---
# <a name="translation-rule-type-a-regular-expression"></a><span data-ttu-id="4da07-105">Règle de conversion : saisir une expression régulière</span><span class="sxs-lookup"><span data-stu-id="4da07-105">Translation Rule: Type a Regular Expression</span></span>
 
<span data-ttu-id="4da07-106">Dans le champ **respecter ce modèle** , spécifiez le modèle qui sera utilisé pour correspondre aux numéros à traduire.</span><span class="sxs-lookup"><span data-stu-id="4da07-106">In the **Match this pattern** field, specify the pattern that will be used to match the numbers to be translated.</span></span> <span data-ttu-id="4da07-107">Dans le champ **règle de traduction** , spécifiez un modèle pour le format des nombres traduits.</span><span class="sxs-lookup"><span data-stu-id="4da07-107">In the **Translation rule** field, specify a pattern for the format of translated numbers.</span></span> <span data-ttu-id="4da07-108">Par exemple, si vous entrez ^\+(\d{9}\d +) $ dans le champ **respecter ce modèle** et 011 $1 dans le champ **règle de traduction** , la règle traduira + 441235551010 en 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="4da07-108">For example, if you enter ^\+(\d{9}\d+)$ in the **Match this pattern** field and 011$1 in the **Translation rule** field, the rule will translate +441235551010 to 011441235551010.</span></span>
  
<span data-ttu-id="4da07-109">Pour plus d’informations sur les différentes procédures que vous pouvez effectuer à l’aide du panneau de configuration Skype entreprise Server, reportez-vous à la rubrique [gestion de Skype entreprise server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="4da07-109">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  


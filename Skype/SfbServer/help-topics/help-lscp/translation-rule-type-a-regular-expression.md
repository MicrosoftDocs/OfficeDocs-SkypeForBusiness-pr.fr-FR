---
title: Règle de traduction Tapez une expression régulière
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Dans le champ Suivre ce modèle, spécifiez le modèle qui sera utilisé pour correspondre aux numéros à traduire. Dans le champ Règle de traduction, spécifiez un modèle pour le format des numéros traduits. Par exemple, si vous entrez ^ (\d \d+)$ dans le champ Suivre ce modèle et 011$1 dans le champ de règle de traduction, la règle traduit \+ {9} +441235551010 en 011441235551010.
ms.openlocfilehash: badbc5a34325e6bc2b5bef7e67ae39a4c8f02dc7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818854"
---
# <a name="translation-rule-type-a-regular-expression"></a><span data-ttu-id="0e950-105">Règle de traduction : taper une expression régulière</span><span class="sxs-lookup"><span data-stu-id="0e950-105">Translation Rule: Type a Regular Expression</span></span>
 
<span data-ttu-id="0e950-106">Dans le champ **Suivre ce modèle**, spécifiez le modèle qui sera utilisé pour correspondre aux numéros à traduire.</span><span class="sxs-lookup"><span data-stu-id="0e950-106">In the **Match this pattern** field, specify the pattern that will be used to match the numbers to be translated.</span></span> <span data-ttu-id="0e950-107">Dans le champ **Règle de traduction**, spécifiez un modèle pour le format des numéros traduits.</span><span class="sxs-lookup"><span data-stu-id="0e950-107">In the **Translation rule** field, specify a pattern for the format of translated numbers.</span></span> <span data-ttu-id="0e950-108">Par exemple, si vous entrez ^ (\d \d+)$ dans le champ Suivre ce modèle et 011$1 dans le champ de règle de traduction, la règle traduit \+ {9} +441235551010 en 011441235551010.  </span><span class="sxs-lookup"><span data-stu-id="0e950-108">For example, if you enter ^\+(\d{9}\d+)$ in the **Match this pattern** field and 011$1 in the **Translation rule** field, the rule will translate +441235551010 to 011441235551010.</span></span>
  
<span data-ttu-id="0e950-109">Pour plus d’informations sur les différentes procédures que vous pouvez effectuer à l’aide du Panneau de contrôle Skype Entreprise Server, voir [Manage Skype for Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="0e950-109">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  


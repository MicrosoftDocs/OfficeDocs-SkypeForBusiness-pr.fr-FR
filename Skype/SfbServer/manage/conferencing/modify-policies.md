---
title: Modifier les stratégies de conférence dans Skype Entreprise Server
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
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Résumé : Découvrez comment modifier des stratégies de conférence dans Skype Entreprise Server.'
ms.openlocfilehash: eafeb56dd9b0c36afffab07830a9efb71bde18fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828004"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="285d6-103">Modifier les stratégies de conférence dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="285d6-103">Modify conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="285d6-104">**Résumé :** Découvrez comment modifier les stratégies de conférence dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="285d6-104">**Summary:** Learn how to modify conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="285d6-105">Vous pouvez modifier des stratégies de conférence à l’aide du Panneau de contrôle Skype Entreprise Server ou de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="285d6-105">You can modify conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="285d6-106">Modifier les stratégies de conférence à l’aide du Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="285d6-106">Modify conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="285d6-107">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="285d6-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="285d6-108">Ouvrez le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="285d6-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="285d6-109">Dans la barre de navigation de gauche, cliquez sur **Conférence,** puis sur Stratégie **de conférence.**</span><span class="sxs-lookup"><span data-stu-id="285d6-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="285d6-110">Dans la liste des stratégies de conférence, cliquez sur la stratégie de conférence souhaitée, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="285d6-110">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="285d6-111">Dans **Modifier la stratégie de conférence**, modifiez les paramètres de stratégie, à l’exception du nom de la stratégie qui ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="285d6-111">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="285d6-112">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="285d6-112">Click **Commit**.</span></span>
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="285d6-113">Modifier les stratégies de conférence à l’aide de Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="285d6-113">Modify conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="285d6-114">Pour modifier les stratégies de conférence, utilisez l’cmdlet **Set-CsConferencingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="285d6-114">To modify conferencing policies, use the **Set-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="285d6-115">L’exemple suivant modifie une valeur de propriété de la stratégie de conférence SalesConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="285d6-115">The following example modifies a property value of the conferencing policy SalesConferencingPolicy.</span></span> <span data-ttu-id="285d6-116">La commande définit la valeur de la propriété AllowConferenceRecording sur False :</span><span class="sxs-lookup"><span data-stu-id="285d6-116">The command sets the value of the AllowConferenceRecording property to False:</span></span>
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

<span data-ttu-id="285d6-117">Pour plus d’informations, notamment sur la syntaxe complète et la liste des paramètres, voir [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="285d6-117">For more information, including complete syntax and a list of parameters, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  


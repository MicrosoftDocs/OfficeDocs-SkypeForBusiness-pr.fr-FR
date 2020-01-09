---
title: Supprimer une stratégie de code confidentiel dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 'Résumé : supprimez le code confidentiel de conférence rendez-vous d’un utilisateur de Skype entreprise Server.'
ms.openlocfilehash: cfdb14ad8107c8d3450e6d50245831f723ca1153
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992321"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="635fe-103">Supprimer une stratégie de code confidentiel dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="635fe-103">Delete a PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="635fe-104">**Résumé :** Supprimez le code confidentiel de conférence rendez-vous d’un utilisateur de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="635fe-104">**Summary:** Delete a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="635fe-105">Suivez cette procédure pour supprimer une stratégie de code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="635fe-105">Follow these steps to delete a personal identification number (PIN) policy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="635fe-106">Vous ne pouvez pas supprimer la stratégie de code confidentiel globale.</span><span class="sxs-lookup"><span data-stu-id="635fe-106">You cannot delete the global PIN policy.</span></span> 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="635fe-107">Pour supprimer une stratégie de code confidentiel dans le panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="635fe-107">To delete a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="635fe-108">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .</span><span class="sxs-lookup"><span data-stu-id="635fe-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="635fe-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="635fe-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="635fe-110">Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Stratégie de code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="635fe-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="635fe-111">Dans la page **Stratégie de code confidentiel**, dans le champ de recherche, tapez entièrement ou partiellement le nom de la stratégie à supprimer.</span><span class="sxs-lookup"><span data-stu-id="635fe-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="635fe-112">Dans la liste des stratégies, cliquez sur la stratégie à supprimer, sur **Modifier**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="635fe-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="635fe-113">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="635fe-113">Click **OK**.</span></span>
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="635fe-114">Suppression de stratégies de code confidentiel à l’aide d’applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="635fe-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="635fe-115">Vous pouvez supprimer des stratégies de code confidentiel à l’aide de Windows PowerShell et de l’applet de passe Remove-CsPinPolicy.</span><span class="sxs-lookup"><span data-stu-id="635fe-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="635fe-116">Vous pouvez exécuter cette applet de commande à partir de Skype entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="635fe-116">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="635fe-117">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype entreprise Server, voir l’article sur le blog [« démarrage rapide : gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell »](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="635fe-117">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="635fe-118">Le processus est le même dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="635fe-118">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="635fe-119">Pour supprimer une stratégie de code confidentiel spécifique</span><span class="sxs-lookup"><span data-stu-id="635fe-119">To remove a specific PIN policy</span></span>

- <span data-ttu-id="635fe-120">Cette commande supprime la stratégie de code confidentiel avec l’identité RedmondPinPolicy :</span><span class="sxs-lookup"><span data-stu-id="635fe-120">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
  ```PowerShell
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="635fe-121">Pour supprimer toutes les stratégies de code confidentiel appliquées au niveau du site</span><span class="sxs-lookup"><span data-stu-id="635fe-121">To remove all the PIN policies applied to the site scope</span></span>

- <span data-ttu-id="635fe-122">Cette commande supprime toutes les stratégies de code confidentiel configurées au niveau du site :</span><span class="sxs-lookup"><span data-stu-id="635fe-122">This command removes all the PIN policies configured at the site scope:</span></span>
    
  ```PowerShell
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="635fe-123">Pour supprimer toutes les stratégies de code confidentiel qui autorisent l’utilisation de critères communs</span><span class="sxs-lookup"><span data-stu-id="635fe-123">To remove all the PIN policies that allow the use of common patterns</span></span>

- <span data-ttu-id="635fe-124">Cette commande supprime toutes les stratégies de code confidentiel qui autorisent l’utilisation de critères communs : G</span><span class="sxs-lookup"><span data-stu-id="635fe-124">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
  ```PowerShell
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

<span data-ttu-id="635fe-125">Pour plus d’informations, reportez-vous à la rubrique d’aide relative à l’applet de passe [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="635fe-125">For more information, see the help topic for the [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  


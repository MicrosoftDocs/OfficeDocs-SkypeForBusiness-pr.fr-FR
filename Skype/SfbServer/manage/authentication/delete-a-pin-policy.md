---
title: Suppression d’une stratégie de code confidentiel dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 'Résumé : Supprimer à distance conférence d’un utilisateur broche pour Skype pour Business Server 2015.'
ms.openlocfilehash: b64a4509105214358549f320cf8885d6386986f7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="delete-a-pin-policy-in-skype-for-business-server-2015"></a><span data-ttu-id="5234d-103">Suppression d’une stratégie de code confidentiel dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5234d-103">Delete a PIN policy in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5234d-104">**Résumé :** Supprimer à distance conférence d’un utilisateur broche pour Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5234d-104">**Summary:** Delete a user's dial-in conferencing PIN for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5234d-105">Suivez cette procédure pour supprimer une stratégie de code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="5234d-105">Follow these steps to delete a personal identification number (PIN) policy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5234d-106">Vous ne pouvez pas supprimer la stratégie de code confidentiel globale.</span><span class="sxs-lookup"><span data-stu-id="5234d-106">You cannot delete the global PIN policy.</span></span> 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="5234d-107">Pour supprimer une stratégie de code PIN dans Skype pour le panneau de configuration de Business Server</span><span class="sxs-lookup"><span data-stu-id="5234d-107">To delete a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="5234d-108">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou dispose de droits d’utilisateur équivalent), ou le rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur sur le réseau dans lequel vous avez déployé Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5234d-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="5234d-109">Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="5234d-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="5234d-110">Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Stratégie de code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="5234d-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="5234d-111">Dans la page **Stratégie de code confidentiel**, dans le champ de recherche, tapez entièrement ou partiellement le nom de la stratégie à supprimer.</span><span class="sxs-lookup"><span data-stu-id="5234d-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="5234d-112">Dans la liste des stratégies, cliquez sur la stratégie à supprimer, sur **Modifier**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="5234d-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="5234d-113">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5234d-113">Click **OK**.</span></span>
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5234d-114">Suppression des stratégies de code PIN à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5234d-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5234d-115">Vous pouvez supprimer des stratégies de code PIN à l’aide de Windows PowerShell et l’applet de commande Remove-CsPinPolicy.</span><span class="sxs-lookup"><span data-stu-id="5234d-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="5234d-116">Vous pouvez exécuter cette applet de commande depuis le Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5234d-116">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5234d-117">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter sur Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="5234d-117">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="5234d-118">Le processus est le même dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="5234d-118">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="5234d-119">Pour supprimer une stratégie de code confidentiel spécifique</span><span class="sxs-lookup"><span data-stu-id="5234d-119">To remove a specific PIN policy</span></span>

- <span data-ttu-id="5234d-120">Cette commande supprime la stratégie de code confidentiel avec l’identité RedmondPinPolicy :</span><span class="sxs-lookup"><span data-stu-id="5234d-120">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
  ```
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="5234d-121">Pour supprimer toutes les stratégies de code confidentiel appliquées au niveau du site</span><span class="sxs-lookup"><span data-stu-id="5234d-121">To remove all the PIN policies applied to the site scope</span></span>

- <span data-ttu-id="5234d-122">Cette commande supprime toutes les stratégies de code confidentiel configurées au niveau du site :</span><span class="sxs-lookup"><span data-stu-id="5234d-122">This command removes all the PIN policies configured at the site scope:</span></span>
    
  ```
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="5234d-123">Pour supprimer toutes les stratégies de code confidentiel qui autorisent l’utilisation de critères communs</span><span class="sxs-lookup"><span data-stu-id="5234d-123">To remove all the PIN policies that allow the use of common patterns</span></span>

- <span data-ttu-id="5234d-124">Cette commande supprime toutes les stratégies de code confidentiel qui autorisent l’utilisation de critères communs : G</span><span class="sxs-lookup"><span data-stu-id="5234d-124">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
  ```
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

<span data-ttu-id="5234d-125">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="5234d-125">For more information, see the help topic for the [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  


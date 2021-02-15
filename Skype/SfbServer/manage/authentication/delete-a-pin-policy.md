---
title: Supprimer une stratégie de code confidentiel dans Skype Entreprise Server
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
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 'Résumé : Supprimez le code confidentiel de conférence d’un utilisateur pour Skype Entreprise Server.'
ms.openlocfilehash: 6cf93d2ade053ba6e4bdbe7aabf0138206fdff88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828394"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="02bb8-103">Supprimer une stratégie de code confidentiel dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="02bb8-103">Delete a PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="02bb8-104">**Résumé :** Supprimez le code confidentiel de conférence d’un utilisateur pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="02bb8-104">**Summary:** Delete a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="02bb8-105">Suivez cette procédure pour supprimer une stratégie de code confidentiel (PIN).</span><span class="sxs-lookup"><span data-stu-id="02bb8-105">Follow these steps to delete a personal identification number (PIN) policy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="02bb8-106">Vous ne pouvez pas supprimer la stratégie de code confidentiel globale.</span><span class="sxs-lookup"><span data-stu-id="02bb8-106">You cannot delete the global PIN policy.</span></span> 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="02bb8-107">Pour supprimer une stratégie de code confidentiel dans le Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="02bb8-107">To delete a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="02bb8-108">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="02bb8-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="02bb8-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="02bb8-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="02bb8-110">Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Stratégie de code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="02bb8-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="02bb8-111">Dans la page **Stratégie de code confidentiel**, dans le champ de recherche, tapez entièrement ou partiellement le nom de la stratégie à supprimer.</span><span class="sxs-lookup"><span data-stu-id="02bb8-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="02bb8-112">Dans la liste des stratégies, cliquez sur la stratégie que vous souhaitez supprimer, cliquez sur **Modifier**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="02bb8-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="02bb8-113">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="02bb8-113">Click **OK**.</span></span>
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="02bb8-114">Suppression de stratégies de code confidentiel à l’Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="02bb8-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="02bb8-115">Vous pouvez supprimer des stratégies de code confidentiel à l’Windows PowerShell la cmdlet Remove-CsPinPolicy de code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="02bb8-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="02bb8-116">Vous pouvez exécuter cette cmdlet à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02bb8-116">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="02bb8-117">Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour se connecter à Skype Entreprise Server, consultez l’article de blog « Démarrage rapide : gestion de [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="02bb8-117">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="02bb8-118">Le processus est le même dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="02bb8-118">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="02bb8-119">Pour supprimer une stratégie de code confidentiel spécifique</span><span class="sxs-lookup"><span data-stu-id="02bb8-119">To remove a specific PIN policy</span></span>

- <span data-ttu-id="02bb8-120">Cette commande supprime la stratégie de code confidentiel avec l’identité RedmondPinPolicy :</span><span class="sxs-lookup"><span data-stu-id="02bb8-120">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
  ```PowerShell
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="02bb8-121">Pour supprimer toutes les stratégies de code confidentiel appliquées à l’étendue Site</span><span class="sxs-lookup"><span data-stu-id="02bb8-121">To remove all the PIN policies applied to the site scope</span></span>

- <span data-ttu-id="02bb8-122">Cette commande supprime toutes les stratégies de code confidentiel configurées au niveau du site :</span><span class="sxs-lookup"><span data-stu-id="02bb8-122">This command removes all the PIN policies configured at the site scope:</span></span>
    
  ```PowerShell
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="02bb8-123">Pour supprimer toutes les stratégies de code confidentiel qui autorisent l’utilisation de modèles courants</span><span class="sxs-lookup"><span data-stu-id="02bb8-123">To remove all the PIN policies that allow the use of common patterns</span></span>

- <span data-ttu-id="02bb8-124">Cette commande supprime toutes les stratégies de code confidentiel qui autorisent l’utilisation de critères communs : G</span><span class="sxs-lookup"><span data-stu-id="02bb8-124">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
  ```PowerShell
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

<span data-ttu-id="02bb8-125">Pour plus d’informations, voir la rubrique d’aide de l’cmdlet [Remove-CsPinPolicy.](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="02bb8-125">For more information, see the help topic for the [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  


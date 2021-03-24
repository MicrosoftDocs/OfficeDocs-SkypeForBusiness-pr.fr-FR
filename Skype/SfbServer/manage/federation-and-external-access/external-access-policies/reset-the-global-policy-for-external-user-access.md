---
title: Réinitialisation de la stratégie globale pour l’accès des utilisateurs externes
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Il est impossible de supprimer totalement une stratégie globale. L’utilisation de l’option **Supprimer** sur la stratégie globale la réinitialise uniquement avec les paramètres par défaut, c’est-à-dire sans prise en charge des options d’accès des utilisateurs externes.
ms.openlocfilehash: 6c74690d86f7a300b79b755db7c6111eec7810f3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098970"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="3259c-104">Réinitialiser la stratégie globale pour l’accès des utilisateurs externes dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="3259c-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="3259c-105">Si vous avez créé ou configuré des stratégies d’accès des utilisateurs externes que vous ne souhaitez plus utiliser, vous pouvez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="3259c-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="3259c-106">Supprimez toute stratégie utilisateur ou de site que vous avez créée.</span><span class="sxs-lookup"><span data-stu-id="3259c-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="3259c-p102">Réinitialisez la stratégie globale à ses paramètres par défaut. Si vous appliquez les paramètres par défaut de la stratégie globale, l’accès des utilisateurs externes est refusé. La stratégie globale ne peut pas être supprimée.</span><span class="sxs-lookup"><span data-stu-id="3259c-p102">Reset the global policy to the default settings. The default global policy settings deny any external user access. The global policy cannot be deleted.</span></span>

<span data-ttu-id="3259c-p103">Il est impossible de supprimer totalement une stratégie globale. L’utilisation de l’option **Supprimer** sur la stratégie globale la réinitialise uniquement avec les paramètres par défaut, c’est-à-dire sans prise en charge des options d’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="3259c-p103">You cannot completely delete a global policy. Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="3259c-112">Pour réinitialiser la stratégie globale avec les paramètres par défaut</span><span class="sxs-lookup"><span data-stu-id="3259c-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="3259c-113">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="3259c-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3259c-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="3259c-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="3259c-115">Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Stratégie d’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="3259c-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="3259c-116">Dans la page **Stratégie d’accès externe**, cliquez sur la stratégie globale, sur **Modifier**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="3259c-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="3259c-p104">À l’invite de confirmation de la suppression, cliquez sur **OK**. Un message s’affiche en haut de la page vous informant que la stratégie globale a été réinitialisée.</span><span class="sxs-lookup"><span data-stu-id="3259c-p104">When prompted to confirm the deletion, click **OK**. A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3259c-119">Réinitialisation de la stratégie d’accès externe globale à l’Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="3259c-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3259c-120">La stratégie d’accès externe globale peut être réinitialisée à l’Windows PowerShell l'Remove-CsExternalAccessPolicy cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3259c-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="3259c-121">Cette cmdlet peut être exécuté à partir de Skype Entreprise Server Management Shell ou d’une session distante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3259c-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="3259c-122">Pour réinitialiser la stratégie d’accès externe globale</span><span class="sxs-lookup"><span data-stu-id="3259c-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="3259c-123">Cette commande redéfinit la stratégie d’accès externe globale :</span><span class="sxs-lookup"><span data-stu-id="3259c-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="3259c-124">Pour plus d’informations, voir la rubrique d’aide de l’cmdlet [Remove-CsExternalAccessPolicy.](/powershell/module/skype/Remove-CsExternalAccessPolicy)</span><span class="sxs-lookup"><span data-stu-id="3259c-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>
---
title: Réinitialisation de la stratégie globale pour l’accès des utilisateurs externes
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous ne pouvez pas supprimer complètement une stratégie globale. L’utilisation de l’option **supprimer** dans la stratégie globale rétablit uniquement les paramètres par défaut de la stratégie globale, qui ne prennent pas en charge les options d’accès des utilisateurs externes.
ms.openlocfilehash: 339ad22e1d049510416bfc3433c6c8a104455504
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280144"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="5976b-104">Réinitialisation de la stratégie globale pour l’accès des utilisateurs externes dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="5976b-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="5976b-105">Si vous avez créé ou configuré des stratégies d’accès des utilisateurs externes que vous ne souhaitez plus utiliser, vous pouvez procéder comme suit:</span><span class="sxs-lookup"><span data-stu-id="5976b-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="5976b-106">Supprimez les stratégies de site ou d’utilisateur que vous avez créées.</span><span class="sxs-lookup"><span data-stu-id="5976b-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="5976b-107">Rétablir les paramètres par défaut de la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="5976b-107">Reset the global policy to the default settings.</span></span> <span data-ttu-id="5976b-108">Les paramètres de stratégie globale par défaut refusent tout accès utilisateur externe.</span><span class="sxs-lookup"><span data-stu-id="5976b-108">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="5976b-109">La stratégie globale ne peut pas être supprimée.</span><span class="sxs-lookup"><span data-stu-id="5976b-109">The global policy cannot be deleted.</span></span>

<span data-ttu-id="5976b-110">Vous ne pouvez pas supprimer complètement une stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="5976b-110">You cannot completely delete a global policy.</span></span> <span data-ttu-id="5976b-111">L’utilisation de l’option **supprimer** dans la stratégie globale rétablit uniquement les paramètres par défaut de la stratégie globale, qui ne prennent pas en charge les options d’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="5976b-111">Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="5976b-112">Pour rétablir les paramètres par défaut de la stratégie globale</span><span class="sxs-lookup"><span data-stu-id="5976b-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="5976b-113">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="5976b-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5976b-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="5976b-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="5976b-115">Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis sur **stratégie d’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="5976b-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="5976b-116">Dans l’onglet **stratégie d’accès externe** , cliquez sur politique globale, cliquez sur **modifier**, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="5976b-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="5976b-117">Lorsque vous êtes invité à confirmer la suppression, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5976b-117">When prompted to confirm the deletion, click **OK**.</span></span> <span data-ttu-id="5976b-118">Un message s’affiche en haut de la page vous informant que la stratégie globale a été réinitialisée.</span><span class="sxs-lookup"><span data-stu-id="5976b-118">A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5976b-119">Réinitialisation de la stratégie d’accès externe globale à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5976b-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5976b-120">La stratégie d’accès externe globale peut être réinitialisée à l’aide de Windows PowerShell et de l’applet de passe Remove-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="5976b-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="5976b-121">Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou d’une session distante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5976b-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="5976b-122">Pour réinitialiser la stratégie d’accès externe globale</span><span class="sxs-lookup"><span data-stu-id="5976b-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="5976b-123">Cette commande réinitialise la stratégie globale d’accès externe:</span><span class="sxs-lookup"><span data-stu-id="5976b-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="5976b-124">Pour plus d’informations, reportez-vous à la rubrique d’aide relative à l’applet de passe [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="5976b-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>



---
title: Suppression d’une stratégie utilisateur ou de site pour l’accès des utilisateurs externes
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous pouvez supprimer n’importe quelle stratégie de site ou d’utilisateur figurant dans le panneau de configuration Skype entreprise Server sur la page de stratégie d’accès externe.
ms.openlocfilehash: 615df309088a329e07f5417dce16e98366a371c7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280123"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="b94de-103">Suppression d’une stratégie utilisateur ou de site pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="b94de-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="b94de-104">Si vous avez créé ou configuré des stratégies d’accès des utilisateurs externes que vous ne souhaitez plus utiliser, vous pouvez procéder comme suit:</span><span class="sxs-lookup"><span data-stu-id="b94de-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="b94de-105">Supprimez les stratégies de site ou d’utilisateur que vous avez créées.</span><span class="sxs-lookup"><span data-stu-id="b94de-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="b94de-106">Rétablir les paramètres par défaut de la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="b94de-106">Reset the global policy to the default settings.</span></span> <span data-ttu-id="b94de-107">Les paramètres de stratégie globale par défaut refusent tout accès utilisateur externe.</span><span class="sxs-lookup"><span data-stu-id="b94de-107">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="b94de-108">La stratégie globale ne peut pas être supprimée.</span><span class="sxs-lookup"><span data-stu-id="b94de-108">The global policy cannot be deleted.</span></span>


<span data-ttu-id="b94de-109">Vous pouvez supprimer n’importe quelle stratégie de site ou d’utilisateur figurant dans le panneau de configuration Skype entreprise Server sur la page de **stratégie d’accès externe** .</span><span class="sxs-lookup"><span data-stu-id="b94de-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="b94de-110">La suppression de la stratégie globale n’entraîne pas la suppression effective de celle-ci, mais elle permet de rétablir les paramètres par défaut, qui n’incluent pas la prise en charge des options d’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="b94de-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="b94de-111">Pour plus d’informations sur la réinitialisation de la stratégie globale, voir [Réinitialiser la stratégie globale pour l’accès des utilisateurs externes](reset-the-global-policy-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="b94de-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="b94de-112">Pour supprimer une stratégie de site ou d’utilisateur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="b94de-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="b94de-113">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="b94de-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b94de-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b94de-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b94de-115">Cliquez sur **accès utilisateur externe**, puis sur **stratégie d’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="b94de-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="b94de-116">Dans l’onglet **stratégie d’accès externe** , cliquez sur le site ou la stratégie d’utilisateur à supprimer, cliquez sur **modifier**, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b94de-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="b94de-117">Lorsque vous êtes invité à confirmer la suppression, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b94de-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b94de-118">Suppression de stratégies de code confidentiel à l’aide d’applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b94de-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b94de-119">Les stratégies d’accès externe peuvent être supprimées à l’aide de Windows PowerShell et de l’applet de passe Remove-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="b94de-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="b94de-120">Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b94de-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="b94de-121">Pour supprimer une stratégie d’accès externe spécifique</span><span class="sxs-lookup"><span data-stu-id="b94de-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="b94de-122">Cette commande supprime la stratégie d’accès externe appliquée au site de Redmond:</span><span class="sxs-lookup"><span data-stu-id="b94de-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="b94de-123">Pour supprimer toutes les stratégies d’accès externe appliquées à l’étendue par utilisateur</span><span class="sxs-lookup"><span data-stu-id="b94de-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="b94de-124">Cette commande supprime toutes les stratégies d’accès externe configurées pour l’étendue par utilisateur:</span><span class="sxs-lookup"><span data-stu-id="b94de-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="b94de-125">Pour supprimer toutes les stratégies d’accès externes pour lesquelles l’accès des utilisateurs externes est désactivé</span><span class="sxs-lookup"><span data-stu-id="b94de-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="b94de-126">Cette commande supprime toutes les stratégies d’accès externe dont l’accès à l’utilisateur extérieur a été désactivé:</span><span class="sxs-lookup"><span data-stu-id="b94de-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="b94de-127">Pour plus d’informations, reportez-vous à la rubrique d’aide relative à l’applet de passe [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="b94de-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

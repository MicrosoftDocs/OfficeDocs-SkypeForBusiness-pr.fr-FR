---
title: Suppression d’une stratégie utilisateur ou d’un site pour l’accès des utilisateurs externes
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
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
description: Vous pouvez supprimer n’importe quelle stratégie de site ou d’utilisateur répertoriée dans le Panneau de contrôle Skype Entreprise Server dans la page Stratégie d’accès externe.
ms.openlocfilehash: 0fbde98868bfe7f8dbe9f97db2350e02dba44560
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817274"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="ca5d8-103">Suppression d’une stratégie utilisateur ou d’un site pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="ca5d8-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="ca5d8-104">Si vous avez créé ou configuré des stratégies d’accès des utilisateurs externes que vous ne souhaitez plus utiliser, vous pouvez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="ca5d8-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="ca5d8-105">Supprimez toute stratégie utilisateur ou de site que vous avez créée.</span><span class="sxs-lookup"><span data-stu-id="ca5d8-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="ca5d8-p101">Réinitialisez la stratégie globale à ses paramètres par défaut. Si vous appliquez les paramètres par défaut de la stratégie globale, l’accès des utilisateurs externes est refusé. La stratégie globale ne peut pas être supprimée.</span><span class="sxs-lookup"><span data-stu-id="ca5d8-p101">Reset the global policy to the default settings. The default global policy settings deny any external user access. The global policy cannot be deleted.</span></span>


<span data-ttu-id="ca5d8-109">Vous pouvez supprimer n’importe quelle stratégie de site ou d’utilisateur répertoriée dans le Panneau de contrôle Skype Entreprise Server dans la page Stratégie **d’accès externe.**</span><span class="sxs-lookup"><span data-stu-id="ca5d8-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="ca5d8-110">La suppression de la stratégie globale ne la supprime pas réellement, mais la réinitialise uniquement aux paramètres par défaut, qui n’incluent pas la prise en charge des options d’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="ca5d8-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="ca5d8-111">Pour plus d’informations sur la réinitialisation de la stratégie globale, voir [Réinitialiser la stratégie globale pour l’accès des utilisateurs externes.](reset-the-global-policy-for-external-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="ca5d8-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="ca5d8-112">Pour supprimer une stratégie de site ou d’utilisateur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="ca5d8-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="ca5d8-113">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ca5d8-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ca5d8-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ca5d8-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ca5d8-115">Cliquez sur **Accès des utilisateurs externes,** cliquez **sur Stratégie d’accès externe.**</span><span class="sxs-lookup"><span data-stu-id="ca5d8-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="ca5d8-116">Sous **l’onglet Stratégie d’accès** externe, cliquez sur le site ou la stratégie utilisateur que vous souhaitez supprimer, cliquez sur **Modifier,** puis cliquez sur **Supprimer.**</span><span class="sxs-lookup"><span data-stu-id="ca5d8-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="ca5d8-117">À l’invite de confirmation de la suppression, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ca5d8-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ca5d8-118">Suppression de stratégies de code confidentiel à l’Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="ca5d8-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ca5d8-119">Les stratégies d’accès externe peuvent être supprimées à l’aide Windows PowerShell et de la cmdlet Remove-CsExternalAccessPolicy externe.</span><span class="sxs-lookup"><span data-stu-id="ca5d8-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="ca5d8-120">Cette cmdlet peut être exécuté à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca5d8-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="ca5d8-121">Pour supprimer une stratégie d’accès externe spécifique</span><span class="sxs-lookup"><span data-stu-id="ca5d8-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="ca5d8-122">Cette commande supprime la stratégie d’accès externe appliquée au site Redmond :</span><span class="sxs-lookup"><span data-stu-id="ca5d8-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="ca5d8-123">Pour supprimer toutes les stratégies d’accès externe appliquées à l’étendue Utilisateur</span><span class="sxs-lookup"><span data-stu-id="ca5d8-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="ca5d8-124">Cette commande supprime toutes les stratégies d’accès externe configurées au niveau de l’étendue Utilisateur :</span><span class="sxs-lookup"><span data-stu-id="ca5d8-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="ca5d8-125">Pour supprimer toutes les stratégies d’accès externe lorsque l’accès des utilisateurs externes est désactivé</span><span class="sxs-lookup"><span data-stu-id="ca5d8-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="ca5d8-126">Cette commande supprime toutes les stratégies d’accès externe lorsque l’accès des utilisateurs externes a été désactivé :</span><span class="sxs-lookup"><span data-stu-id="ca5d8-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="ca5d8-127">Pour plus d’informations, voir la rubrique d’aide de l’cmdlet [Remove-CsExternalAccessPolicy.](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)</span><span class="sxs-lookup"><span data-stu-id="ca5d8-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

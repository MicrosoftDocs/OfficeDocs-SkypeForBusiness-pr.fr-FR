---
title: Suppression d’une stratégie utilisateur ou de site pour l’accès des utilisateurs externes
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous pouvez supprimer toute stratégie de site ou d’utilisateur qui est répertorié dans la Skype pour Business Server Control Panel dans la page Stratégie d’accès externe.
ms.openlocfilehash: 24d26e8668d04f1c11a3039b4b524d25e209e619
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197743"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="5a3c6-103">Suppression d’une stratégie utilisateur ou de site pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="5a3c6-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="5a3c6-104">Si vous avez créé ou configuré des stratégies d’accès utilisateur externe que vous ne souhaitez plus utiliser, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5a3c6-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="5a3c6-105">Supprimer une stratégie de site ou d’utilisateur que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="5a3c6-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="5a3c6-106">Réinitialiser la stratégie globale pour les paramètres par défaut.</span><span class="sxs-lookup"><span data-stu-id="5a3c6-106">Reset the global policy to the default settings.</span></span> <span data-ttu-id="5a3c6-107">Les paramètres de stratégie globale par défaut refuser tout accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="5a3c6-107">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="5a3c6-108">Impossible de supprimer la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="5a3c6-108">The global policy cannot be deleted.</span></span>


<span data-ttu-id="5a3c6-109">Vous pouvez supprimer toute stratégie de site ou d’utilisateur qui est répertorié dans la Skype pour Business Server Control Panel dans la page **Stratégie d’accès externe** .</span><span class="sxs-lookup"><span data-stu-id="5a3c6-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="5a3c6-110">Suppression de la stratégie globale n’est pas réellement supprimé, mais uniquement rétablit les paramètres par défaut, qui ne comportent pas de prise en charge pour les options d’accès utilisateur externe.</span><span class="sxs-lookup"><span data-stu-id="5a3c6-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="5a3c6-111">Pour plus d’informations sur la réinitialisation de la stratégie globale, consultez la rubrique [Réinitialiser la stratégie globale pour l’accès des utilisateurs externes](reset-the-global-policy-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="5a3c6-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="5a3c6-112">Pour supprimer une stratégie de site ou d’utilisateur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="5a3c6-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="5a3c6-113">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="5a3c6-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5a3c6-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="5a3c6-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5a3c6-115">Cliquez sur **Accès des utilisateurs externes**, cliquez sur **Stratégie d’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="5a3c6-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="5a3c6-116">Sous l’onglet **Stratégie d’accès externe** , cliquez sur la stratégie de site ou utilisateur que vous souhaitez supprimer, cliquez sur **Modifier**, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="5a3c6-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="5a3c6-117">Lorsque vous y êtes invité à confirmer la suppression, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a3c6-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5a3c6-118">Suppression des stratégies de code confidentiel à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a3c6-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5a3c6-119">Stratégies d’accès externe peuvent être supprimés à l’aide de Windows PowerShell et l’applet de commande Remove-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="5a3c6-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="5a3c6-120">Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a3c6-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="5a3c6-121">Pour supprimer une stratégie d’accès externe spécifique</span><span class="sxs-lookup"><span data-stu-id="5a3c6-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="5a3c6-122">Cette commande supprime la stratégie d’accès externe appliquée au site Redmond :</span><span class="sxs-lookup"><span data-stu-id="5a3c6-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="5a3c6-123">Pour supprimer toutes les stratégies appliquées à l’étendue utilisateur accéder à externe</span><span class="sxs-lookup"><span data-stu-id="5a3c6-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="5a3c6-124">Cette commande supprime toutes les stratégies d’accès externe configurées dans l’étendue par utilisateur :</span><span class="sxs-lookup"><span data-stu-id="5a3c6-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="5a3c6-125">Pour supprimer toutes les stratégies d’accès externe dont l’accès des utilisateurs extérieurs est désactivé</span><span class="sxs-lookup"><span data-stu-id="5a3c6-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="5a3c6-126">Cette commande supprime toutes les stratégies d’accès externe dont l’accès a été désactivé en dehors de l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="5a3c6-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="5a3c6-127">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="5a3c6-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

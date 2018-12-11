---
title: Attribuer une stratégie d’accès utilisateur externe
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si un utilisateur a été activé pour Skype pour Business Server, vous pouvez configurer la fédération SIP, l’accès des utilisateurs distants et solution PIC (PIC) dans le Skype pour le panneau de configuration serveur Business en appliquant les stratégies appropriées à des utilisateurs spécifiques.
ms.openlocfilehash: 3498b7aabaddc80053efca70b89198c224147c0e
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222841"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a><span data-ttu-id="f20d5-103">Affecter une stratégie d’accès utilisateur externe à un Skype pour un utilisateur activé</span><span class="sxs-lookup"><span data-stu-id="f20d5-103">Assign an external user access policy to a Skype for Business enabled user</span></span>

<span data-ttu-id="f20d5-104">Si un utilisateur a été activé pour Skype pour Business Server, vous pouvez configurer la fédération SIP, l’accès des utilisateurs distants et solution PIC (PIC) dans le Skype pour le panneau de configuration serveur Business en appliquant les stratégies appropriées à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="f20d5-104">If a user has been enabled for Skype for Business Server, you can configure SIP federation, remote user access, and public instant messaging (IM) connectivity in the Skype for Business Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="f20d5-105">Par exemple, si vous avez créé une stratégie pour prendre en charge l’accès des utilisateurs distants, vous devez l’appliquer à l’utilisateur avant que l’utilisateur peut se connecter à Skype pour Business Server à partir d’un emplacement distant et collaborer avec des utilisateurs internes à partir de l’emplacement distant.</span><span class="sxs-lookup"><span data-stu-id="f20d5-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Skype for Business Server from a remote location and collaborate with internal users from the remote location.</span></span>


> [!NOTE]  
> <span data-ttu-id="f20d5-106">Pour prendre en charge l’accès des utilisateurs externes, vous devez activer la prise en charge pour chaque type d’accès utilisateur externe que vous souhaitez prendre en charge et configurer les stratégies appropriées et autres options permettant de contrôler son utilisation.</span><span class="sxs-lookup"><span data-stu-id="f20d5-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="f20d5-107">Pour plus d’informations, voir [Managing fédération et accès externe aux Skype pour Business Server](../managing-federation-and-external-access.md).</span><span class="sxs-lookup"><span data-stu-id="f20d5-107">For details, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>


<span data-ttu-id="f20d5-108">Utilisez la procédure de cette rubrique pour appliquer une stratégie d’accès des utilisateurs externes créée précédemment à un ou plusieurs comptes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f20d5-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="f20d5-109">Pour appliquer une stratégie d’utilisateur externe à un compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="f20d5-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="f20d5-110">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f20d5-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f20d5-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="f20d5-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f20d5-112">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur à configurer.</span><span class="sxs-lookup"><span data-stu-id="f20d5-112">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="f20d5-113">Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="f20d5-113">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f20d5-114">Dans **Modifier les Skype pour l’utilisateur Business Server** sous **stratégie d’accès externe**, sélectionnez la stratégie d’utilisateur que vous souhaitez appliquer.</span><span class="sxs-lookup"><span data-stu-id="f20d5-114">In **Edit Skype for Business Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
     
> [!NOTE]  
> <span data-ttu-id="f20d5-115">Le \*\* \<automatique >\*\* paramètres s’appliquent les paramètres de stratégie globale ou de serveur par défaut.</span><span class="sxs-lookup"><span data-stu-id="f20d5-115">The **\<Automatic>** settings apply the default server or global policy settings.</span></span>


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f20d5-116">Affectation de stratégies d’accès externe par utilisateur à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f20d5-116">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f20d5-117">Stratégies d’accès externe par utilisateur peuvent être affectés à l’aide de Windows PowerShell et l’applet de commande Grant-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="f20d5-117">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="f20d5-118">Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f20d5-118">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="f20d5-119">Pour affecter une stratégie d’accès externe par utilisateur à un utilisateur unique</span><span class="sxs-lookup"><span data-stu-id="f20d5-119">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="f20d5-120">Cette commande attribue la stratégie d’accès externe par utilisateur RedmondExternalAccessPolicy à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="f20d5-120">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="f20d5-121">Pour affecter une stratégie d’accès externe par utilisateur à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="f20d5-121">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="f20d5-122">Cette commande attribue la stratégie d’accès externe par utilisateur USAExternalAccessPolicy à tous les utilisateurs qui disposent de comptes dans l’unité d’organisation des États-Unis dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f20d5-122">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="f20d5-123">Pour plus d’informations sur le paramètre d’unité d’organisation utilisé dans cette commande, voir la documentation de l’applet de commande [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="f20d5-123">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="f20d5-124">Pour annuler l’affectation d’une stratégie d’accès externe par utilisateur</span><span class="sxs-lookup"><span data-stu-id="f20d5-124">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="f20d5-125">Cette commande annule toute stratégie d’accès externe par utilisateur préalablement attribuée à Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="f20d5-125">This command unassigns any per-user external access policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="f20d5-126">Une fois l’affectation de la stratégie par utilisateur annulée, Ken Myer sera automatiquement géré en utilisant la stratégie globale ou, le cas échéant, sa stratégie de site local.</span><span class="sxs-lookup"><span data-stu-id="f20d5-126">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="f20d5-127">Une stratégie de site est prioritaire sur la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="f20d5-127">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



<span data-ttu-id="f20d5-128">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="f20d5-128">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>



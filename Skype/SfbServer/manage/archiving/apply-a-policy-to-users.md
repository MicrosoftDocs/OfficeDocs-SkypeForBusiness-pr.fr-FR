---
title: Appliquer une stratégie d’archivage aux utilisateurs dans Skype Entreprise Server
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
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Résumé : Découvrez comment affecter une stratégie d’archivage aux utilisateurs dans Skype Entreprise Server.'
ms.openlocfilehash: 8dc74fcc8befe39b424b89c77aebca683fe17586
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817764"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a><span data-ttu-id="1800f-103">Appliquer une stratégie d’archivage aux utilisateurs dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1800f-103">Apply an archiving policy to users in Skype for Business Server</span></span>

<span data-ttu-id="1800f-104">**Résumé :** Découvrez comment affecter une stratégie d’archivage aux utilisateurs dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1800f-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server.</span></span>
  
<span data-ttu-id="1800f-105">Si vous avez créé une ou plusieurs stratégies utilisateur pour l’archivage pour les utilisateurs de Skype Entreprise Server, vous pouvez implémenter la prise en charge de l’archivage pour des utilisateurs spécifiques en appliquant les stratégies appropriées à ces utilisateurs ou groupes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1800f-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="1800f-106">Par exemple, si vous créez une stratégie pour prendre en charge l’archivage des communications internes, vous pouvez l’appliquer à au moins un utilisateur ou groupe d’utilisateurs pour prendre en charge l’archivage des communications Skype Entreprise Server de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1800f-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1800f-107">Si vous avez activé l’intégration de Microsoft Exchange pour votre déploiement, les stratégies d’archive In-Place Exchange contrôlent si l’archivage est activé pour les utilisateurs qui sont homed on Exchange et dont les boîtes aux lettres sont mises en In-Place archive.</span><span class="sxs-lookup"><span data-stu-id="1800f-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="1800f-108">Pour plus d’informations, voir [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="1800f-108">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="1800f-109">Appliquer une stratégie utilisateur à l’aide du Panneau de contrôle</span><span class="sxs-lookup"><span data-stu-id="1800f-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="1800f-110">Pour appliquer une stratégie utilisateur à l’aide du Panneau de contrôle :</span><span class="sxs-lookup"><span data-stu-id="1800f-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="1800f-111">À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1800f-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="1800f-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1800f-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="1800f-113">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.</span><span class="sxs-lookup"><span data-stu-id="1800f-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="1800f-114">Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="1800f-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="1800f-115">Dans **Modifier l’utilisateur Lync Server sous** **stratégie** d’archivage, sélectionnez la stratégie utilisateur d’archivage à appliquer.</span><span class="sxs-lookup"><span data-stu-id="1800f-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1800f-116">Les **\<Automatic\>** paramètres appliquent les paramètres d’installation du serveur par défaut.</span><span class="sxs-lookup"><span data-stu-id="1800f-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="1800f-117">Ces paramètres sont appliqués automatiquement par le serveur.</span><span class="sxs-lookup"><span data-stu-id="1800f-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="1800f-118">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1800f-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="1800f-119">Appliquer une stratégie utilisateur à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1800f-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="1800f-120">Vous pouvez également appliquer une stratégie utilisateur à l’aide Windows PowerShell l’cmdlet **Grant-CsArchivingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="1800f-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="1800f-121">La commande suivante assigne la stratégie d’archivage par utilisateur RedmondArchivingPolicy à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="1800f-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="1800f-122">Cette commande affecte la stratégie d’archivage par utilisateur RedmondArchivingPolicy à tous les utilisateurs qui ont des comptes sur le pool de atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1800f-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="1800f-123">Pour plus d’informations sur le paramètre Filter utilisé dans cette commande, voir la documentation de l’cmdlet [Get-CsUser.](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="1800f-123">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="1800f-124">La commande suivante supprime toute stratégie d’archivage par utilisateur précédemment affectée à Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="1800f-124">The following command removes any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="1800f-125">Une fois la stratégie par utilisateur supprimée, Ken Myer est automatiquement géré à l’aide de la stratégie globale ou, le cas présent, de sa stratégie de site locale.</span><span class="sxs-lookup"><span data-stu-id="1800f-125">After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="1800f-126">La stratégie de site est prioritaire sur la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="1800f-126">A site policy takes precedence over the global policy.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="1800f-127">Pour plus d’informations, voir la documentation de l’cmdlet [Grant-CsArchivingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="1800f-127">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
  


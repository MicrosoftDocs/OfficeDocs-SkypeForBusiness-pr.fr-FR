---
title: Application d’une stratégie d’archivage pour les utilisateurs de Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Résumé : Apprenez à affecter une stratégie d’archivage pour les utilisateurs de Skype pour Business Server 2015.'
ms.openlocfilehash: fc9811aa57a1ba397dedce325f03ea2d77e4413b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server-2015"></a><span data-ttu-id="22db4-103">Application d’une stratégie d’archivage pour les utilisateurs de Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="22db4-103">Apply an archiving policy to users in Skype for Business Server 2015</span></span>

<span data-ttu-id="22db4-104">**Résumé :** Découvrez comment affecter une stratégie d’archivage pour les utilisateurs de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="22db4-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="22db4-105">Si vous avez créé une ou plusieurs stratégies d’utilisateurs pour l’archivage pour les utilisateurs hébergement sur Skype pour Business Server 2015, vous pouvez implémenter une prise en charge d’archivage pour des utilisateurs spécifiques en appliquant des stratégies appropriées aux utilisateurs ou les groupes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="22db4-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server 2015, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="22db4-106">Par exemple, si vous créez une stratégie pour prendre en charge l’archivage des communications internes, vous pouvez l’appliquer au moins un utilisateur ou groupe d’utilisateurs pour prendre en charge l’archivage de Skype de l’utilisateur pour les communications d’entreprise serveur 2015.</span><span class="sxs-lookup"><span data-stu-id="22db4-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server 2015 communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="22db4-107">Si vous activé l’intégration de Microsoft Exchange pour votre déploiement, maintenez la touche Exchange Place le contrôle les stratégies si l’archivage est activé pour les utilisateurs qui sont hébergés sur Exchange et que leurs boîtes aux lettres sur Place maintenez.</span><span class="sxs-lookup"><span data-stu-id="22db4-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="22db4-108">Pour plus d’informations, consultez [planification d’archivage dans Skype pour Business Server 2015](../../plan-your-deployment/archiving/archiving.md) et [configurer une intégration avec le stockage Exchange pour Skype pour Business Server 2015](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="22db4-108">For details, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server 2015](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="22db4-109">Appliquer une stratégie utilisateur via le Panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="22db4-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="22db4-110">Pour appliquer une stratégie utilisateur via le Panneau de configuration :</span><span class="sxs-lookup"><span data-stu-id="22db4-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="22db4-111">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="22db4-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="22db4-112">Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="22db4-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="22db4-113">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.</span><span class="sxs-lookup"><span data-stu-id="22db4-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="22db4-114">Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="22db4-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="22db4-115">**Modifier l’utilisateur Lync Server** sous **les stratégies d’archivage**, sélectionnez la stratégie d’archivage de l’utilisateur que vous souhaitez appliquer.</span><span class="sxs-lookup"><span data-stu-id="22db4-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="22db4-116">La ** \<automatique\> ** les paramètres s’appliquent les paramètres d’installation de serveur par défaut.</span><span class="sxs-lookup"><span data-stu-id="22db4-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="22db4-117">Le serveur les applique automatiquement.</span><span class="sxs-lookup"><span data-stu-id="22db4-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="22db4-118">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="22db4-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="22db4-119">Appliquer une stratégie d’utilisateur à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="22db4-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="22db4-120">Vous pouvez également appliquer une stratégie d’utilisateur à l’aide de l’applet de commande Windows PowerShell **Grant-CsArchivingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="22db4-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="22db4-121">La commande suivante assigne la stratégie d’archivage par utilisateur RedmondArchivingPolicy à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="22db4-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="22db4-122">Cette commande attribue à l’utilisateur par l’archivage RedmondArchivingPolicy de stratégie à tous les utilisateurs qui ont les comptes hébergés sur le pool Registrar atl-cs-001.contoso.com. Pour plus d’informations sur le paramètre de filtre utilisé dans cette commande, consultez la documentation d’applet de commande [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="22db4-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com. For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

```

<span data-ttu-id="22db4-p104">La commande suivante supprime l’assignation d’une stratégie d’archivage par utilisateur précédemment affectée à Ken Myer. Lorsque cette stratégie par utilisateur n’est plus assignée à Ken Myer, celui-ci est géré automatiquement par la stratégie globale ou, le cas échéant, par la stratégie de site locale associée. La stratégie de site est prioritaire sur la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="22db4-p104">The following command removes any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="22db4-126">Pour plus d’informations, consultez la documentation d’applet de commande de [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="22db4-126">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
  


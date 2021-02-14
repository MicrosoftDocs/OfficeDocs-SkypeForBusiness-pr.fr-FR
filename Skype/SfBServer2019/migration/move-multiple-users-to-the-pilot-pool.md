---
title: Déplacer plusieurs utilisateurs vers le pool pilote
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Vous pouvez déplacer plusieurs utilisateurs de votre pool hérité vers votre pool pilote Skype Entreprise Server 2019 à l’aide du Panneau de commande Skype Entreprise Server 2019 ou de Skype Entreprise Server 2019 Management Shell.
ms.openlocfilehash: d1b003c5630a0917fbecbd9b04196675657fef83
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753426"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="b7726-103">Déplacer plusieurs utilisateurs vers le pool pilote</span><span class="sxs-lookup"><span data-stu-id="b7726-103">Move multiple users to the pilot pool</span></span>

<span data-ttu-id="b7726-104">Vous pouvez déplacer plusieurs utilisateurs de votre pool hérité vers votre pool pilote Skype Entreprise Server 2019 à l’aide du Panneau de commande Skype Entreprise Server 2019 ou de Skype Entreprise Server 2019 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b7726-104">You can move multiple users from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span>

 <span data-ttu-id="b7726-105">**Contenu de cet article :**</span><span class="sxs-lookup"><span data-stu-id="b7726-105">**In this article**</span></span>
  
[<span data-ttu-id="b7726-106">Pour déplacer plusieurs utilisateurs à l’aide du Panneau de commande Skype Entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="b7726-106">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection0)
  
[<span data-ttu-id="b7726-107">Pour déplacer plusieurs utilisateurs à l’aide de Skype Entreprise Server 2019 Management Shell</span><span class="sxs-lookup"><span data-stu-id="b7726-107">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection1)
  
[<span data-ttu-id="b7726-108">Pour déplacer tous les utilisateurs en même temps à l’aide de Skype Entreprise Server 2019 Management Shell</span><span class="sxs-lookup"><span data-stu-id="b7726-108">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="b7726-109">Pour déplacer plusieurs utilisateurs à l’aide du Panneau de commande Skype Entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="b7726-109">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="b7726-110"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="b7726-110"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="b7726-111">Ouvrez le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b7726-111">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="b7726-112">Cliquez **sur Utilisateurs,** **sur** Rechercher, puis sur **Rechercher.**</span><span class="sxs-lookup"><span data-stu-id="b7726-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="b7726-113">Sélectionnez deux utilisateurs à déplacer vers le pool Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b7726-113">Select two users that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="b7726-114">Dans cet exemple, nous allons déplacer les utilisateurs Chen Yang et Claus Hansen.</span><span class="sxs-lookup"><span data-stu-id="b7726-114">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
     ![Déplacer des utilisateurs vers un pool d’inscription spécifique](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. <span data-ttu-id="b7726-116">Dans le menu **Action**, sélectionnez **Déplacer les utilisateurs sélectionnés vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="b7726-116">From the **Action** menu, select **Move selected users to pool**.</span></span>
    
5. <span data-ttu-id="b7726-117">Dans la liste de listes, sélectionnez le pool Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b7726-117">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
6. <span data-ttu-id="b7726-118">Cliquez sur **Action**, puis sur **Déplacer les utilisateurs sélectionnés vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="b7726-118">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="b7726-119">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7726-119">Click **OK**.</span></span>
    
     ![Boîte de dialogue Déplacer les utilisateurs, pool de bureaux d’inscriptions de destination](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. <span data-ttu-id="b7726-121">Vérifiez que la colonne **pool de** serveurs d’inscriptions pour les utilisateurs contient désormais le pool Skype Entreprise Server 2019, ce qui indique que les utilisateurs ont été déplacés avec succès.</span><span class="sxs-lookup"><span data-stu-id="b7726-121">Verify that the **Registrar pool** column for the users now contains the Skype for Business Server 2019 pool, which indicates that the users have been successfully moved.</span></span> 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="b7726-122">Pour déplacer plusieurs utilisateurs à l’aide de Skype Entreprise Server 2019 Management Shell</span><span class="sxs-lookup"><span data-stu-id="b7726-122">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="b7726-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="b7726-123"><a name="sectionSection1"> </a></span></span>

1. <span data-ttu-id="b7726-124">Ouvrez Skype Entreprise Server 2019 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b7726-124">Open the Skype for Business Server 2019 Management Shell.</span></span> 
    
2. <span data-ttu-id="b7726-125">Sur la ligne de commande, tapez ce qui suit et remplacez **User1** et **User2** par des noms d’utilisateurs spécifiques que vous souhaitez déplacer, et remplacez **pool_FQDN** par le nom du pool de destination.</span><span class="sxs-lookup"><span data-stu-id="b7726-125">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move, and replace **pool_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="b7726-126">Dans cet exemple, nous allons déplacer les utilisateurs Hao Chen et Katie Jordan.</span><span class="sxs-lookup"><span data-stu-id="b7726-126">In this example we will move users Hao Chen and Katie Jordan.</span></span> 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Exemple d'Get-CsUser PowerShell](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. <span data-ttu-id="b7726-128">Dans la ligne de commande, tapez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="b7726-128">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. <span data-ttu-id="b7726-129">L’identité **Registrar Pool** doit désormais pointer vers le pool que vous avez spécifié en tant que **pool_FQDN** à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="b7726-129">The **Registrar Pool** identity should now point to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="b7726-130">La présence de cette identité confirme que l’utilisateur a été déplacé avec succès.</span><span class="sxs-lookup"><span data-stu-id="b7726-130">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="b7726-131">Répétez l’étape pour **vérifier que User2** a été déplacé.</span><span class="sxs-lookup"><span data-stu-id="b7726-131">Repeat step to verify that **User2** has been moved.</span></span> 
    
     ![Sortie de l'Get-UsUser -Identity de PowerShell](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="b7726-133">Pour déplacer tous les utilisateurs en même temps à l’aide de Skype Entreprise Server 2019 Management Shell</span><span class="sxs-lookup"><span data-stu-id="b7726-133">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="b7726-134"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="b7726-134"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="b7726-135">Dans cet exemple, tous les utilisateurs ont été renvoyés au pool hérité (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="b7726-135">In this example, all users have been returned to the legacy pool (pool01.contoso.net).</span></span> <span data-ttu-id="b7726-136">À l’aide de Skype Entreprise Server 2019 Management Shell, nous allons déplacer tous les utilisateurs en même temps vers le pool Skype Entreprise Server 2019 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="b7726-136">Using the Skype for Business Server 2019 Management Shell, we will move all users at the same time to the Skype for Business Server 2019 pool (pool02.contoso.net).</span></span>
  
1. <span data-ttu-id="b7726-137">Ouvrez Skype Entreprise Server 2019 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b7726-137">Open the Skype for Business Server 2019 Management Shell.</span></span>
    
2. <span data-ttu-id="b7726-138">Dans la ligne de commande, tapez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="b7726-138">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Cmdlet PowerShell et résultats dans Management Shell](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. <span data-ttu-id="b7726-140">Exécutez **Get-CsUser** pour l’un des utilisateurs pilotes.</span><span class="sxs-lookup"><span data-stu-id="b7726-140">Run **Get-CsUser** for one of the pilot users.</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. <span data-ttu-id="b7726-141">**L’identité du pool** de bureaux d’inscriptions pour chaque utilisateur pointe maintenant vers le pool que vous avez spécifié comme **pool_FQDN** l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="b7726-141">The **Registrar Pool** identity for each user now points to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="b7726-142">Le présence de cette identité confirme que l’utilisateur a été déplacé avec succès.</span><span class="sxs-lookup"><span data-stu-id="b7726-142">The presence of this identity confirms that the user has been successfully moved.</span></span> 
    
5. <span data-ttu-id="b7726-143">En outre, nous pouvons afficher la liste des utilisateurs dans le Panneau de contrôle Skype Entreprise Server 2019 et vérifier que la valeur du pool de serveurs d’inscriptions pointe désormais vers le pool Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b7726-143">Additionally, we can view the list of users in the Skype for Business Server 2019 Control Panel and verify that the Registrar Pool value now points to the Skype for Business Server 2019 pool.</span></span>
    
     ![Liste d’utilisateurs du Panneau de contrôle Skype Entreprise Server 2019](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  


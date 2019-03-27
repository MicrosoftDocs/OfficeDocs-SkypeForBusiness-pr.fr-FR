---
title: Déplacer plusieurs utilisateurs vers le pool pilote
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous pouvez déplacer plusieurs utilisateurs à partir de votre pool hérité vers votre Skype pour le pool pilote Business Server 2019 à l’aide de Skype pour Business Server 2019 le panneau de configuration ou Skype pour Business Server 2019 Management Shell.
ms.openlocfilehash: c77598d531fa4640d64a61e22ace17e39d87b005
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888300"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="e868e-103">Déplacer plusieurs utilisateurs vers le pool pilote</span><span class="sxs-lookup"><span data-stu-id="e868e-103">Move multiple users to the pilot pool</span></span>

<span data-ttu-id="e868e-104">Vous pouvez déplacer plusieurs utilisateurs à partir de votre pool hérité vers votre Skype pour le pool pilote Business Server 2019 à l’aide de Skype pour Business Server 2019 le panneau de configuration ou Skype pour Business Server 2019 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e868e-104">You can move multiple users from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span>

 <span data-ttu-id="e868e-105">**Dans cet article**</span><span class="sxs-lookup"><span data-stu-id="e868e-105">**In this article**</span></span>
  
[<span data-ttu-id="e868e-106">Pour déplacer plusieurs utilisateurs à l’aide de la Skype pour Business Server 2019 le panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="e868e-106">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection0)
  
[<span data-ttu-id="e868e-107">Pour déplacer plusieurs utilisateurs à l’aide de la Skype pour Business Server 2019 Management Shell</span><span class="sxs-lookup"><span data-stu-id="e868e-107">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection1)
  
[<span data-ttu-id="e868e-108">Pour déplacer tous les utilisateurs en même temps à l’aide de la Skype pour Business Server 2019 Management Shell</span><span class="sxs-lookup"><span data-stu-id="e868e-108">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="e868e-109">Pour déplacer plusieurs utilisateurs à l’aide de la Skype pour Business Server 2019 le panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="e868e-109">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="e868e-110"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="e868e-110"></span></span>

1. <span data-ttu-id="e868e-111">Ouvrez le panneau de configuration serveur Business Skype.</span><span class="sxs-lookup"><span data-stu-id="e868e-111">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="e868e-112">Cliquez sur **utilisateurs**, cliquez sur **Rechercher**, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="e868e-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="e868e-113">Sélectionnez les deux utilisateurs que vous souhaitez déplacer vers le Skype pour Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="e868e-113">Select two users that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="e868e-114">Dans cet exemple, nous déplace les utilisateurs Chen Yang et Claus Hansen.</span><span class="sxs-lookup"><span data-stu-id="e868e-114">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
     ![Déplacer les utilisateurs vers le pool de Registre spécifique](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. <span data-ttu-id="e868e-116">Dans le menu **Action** , sélectionnez **déplacer les utilisateurs sélectionnés vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="e868e-116">From the **Action** menu, select **Move selected users to pool**.</span></span>
    
5. <span data-ttu-id="e868e-117">Dans la liste déroulante, sélectionnez le Skype pour Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="e868e-117">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
6. <span data-ttu-id="e868e-118">Cliquez sur **Action**, puis cliquez sur **déplacer les utilisateurs sélectionnés vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="e868e-118">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="e868e-119">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e868e-119">Click **OK**.</span></span>
    
     ![Déplacer des utilisateurs, boîte de dialogue destination du serveur d’inscriptions pool](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. <span data-ttu-id="e868e-121">Vérifiez que la colonne **pool de serveurs d’inscriptions** pour les utilisateurs contient maintenant le Skype pour Business Server 2019 pool, ce qui indique que les utilisateurs ont été déplacés avec succès.</span><span class="sxs-lookup"><span data-stu-id="e868e-121">Verify that the **Registrar pool** column for the users now contains the Skype for Business Server 2019 pool, which indicates that the users have been successfully moved.</span></span> 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="e868e-122">Pour déplacer plusieurs utilisateurs à l’aide de la Skype pour Business Server 2019 Management Shell</span><span class="sxs-lookup"><span data-stu-id="e868e-122">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="e868e-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="e868e-123"></span></span>

1. <span data-ttu-id="e868e-124">Ouvrez le Skype pour Business Server 2019 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e868e-124">Open the Skype for Business Server 2019 Management Shell.</span></span> 
    
2. <span data-ttu-id="e868e-125">Sur la ligne de commande, tapez la commande suivante et remplacez **User1** et **User2** par les noms d’utilisateur spécifiques à déplacer et **pool_fqdn par le nom du pool de destination** .</span><span class="sxs-lookup"><span data-stu-id="e868e-125">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move, and replace **pool_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="e868e-126">Dans cet exemple nous déplace les utilisateurs Hao Chen et Katie Jordan.</span><span class="sxs-lookup"><span data-stu-id="e868e-126">In this example we will move users Hao Chen and Katie Jordan.</span></span> 
    
   ```
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Exemple d’applet de commande PowerShell Get-CsUser](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. <span data-ttu-id="e868e-128">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="e868e-128">At the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -Identity "User1"
   ```

4. <span data-ttu-id="e868e-129">L’identité du **Pool de serveurs d’inscriptions** doit désormais pointer vers le pool que vous avez spécifié comme **pool_FQDN** à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="e868e-129">The **Registrar Pool** identity should now point to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="e868e-130">La présence de cette identité confirme que l’utilisateur a été déplacé avec succès.</span><span class="sxs-lookup"><span data-stu-id="e868e-130">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="e868e-131">Répétez l’étape pour vérifier que **l’utilisateur 2** a été déplacé.</span><span class="sxs-lookup"><span data-stu-id="e868e-131">Repeat step to verify that **User2** has been moved.</span></span> 
    
     ![Sortie de PowerShell Get-UsUser-Identity applet de commande](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="e868e-133">Pour déplacer tous les utilisateurs en même temps à l’aide de la Skype pour Business Server 2019 Management Shell</span><span class="sxs-lookup"><span data-stu-id="e868e-133">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="e868e-134"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="e868e-134"></span></span>

<span data-ttu-id="e868e-135">Dans cet exemple, tous les utilisateurs ont été renvoyés vers le pool hérité (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="e868e-135">In this example, all users have been returned to the legacy pool (pool01.contoso.net).</span></span> <span data-ttu-id="e868e-136">À l’aide de la Skype pour Business Server 2019 Management Shell, nous déplace tous les utilisateurs en même temps vers la Skype pour le pool d’entreprise Server 2019 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="e868e-136">Using the Skype for Business Server 2019 Management Shell, we will move all users at the same time to the Skype for Business Server 2019 pool (pool02.contoso.net).</span></span>
  
1. <span data-ttu-id="e868e-137">Ouvrez le Skype pour Business Server 2019 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e868e-137">Open the Skype for Business Server 2019 Management Shell.</span></span>
    
2. <span data-ttu-id="e868e-138">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="e868e-138">At the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Applet de commande PowerShell et les résultats dans Management Shell](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. <span data-ttu-id="e868e-140">Exécutez **Get-CsUser** pour un des utilisateurs pilotes.</span><span class="sxs-lookup"><span data-stu-id="e868e-140">Run **Get-CsUser** for one of the pilot users.</span></span> 
    
   ```
   Get-CsUser -Identity "Hao Chen"
   ```

4. <span data-ttu-id="e868e-141">L’identité du **Pool de serveurs d’inscriptions** pour chaque utilisateur pointe désormais vers le pool que vous avez spécifié comme **pool_FQDN** à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="e868e-141">The **Registrar Pool** identity for each user now points to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="e868e-142">La présence de cette identité confirme que l’utilisateur a été déplacé avec succès.</span><span class="sxs-lookup"><span data-stu-id="e868e-142">The presence of this identity confirms that the user has been successfully moved.</span></span> 
    
5. <span data-ttu-id="e868e-143">En outre, nous pouvons afficher la liste des utilisateurs dans le Skype pour Business Server 2019 le panneau de configuration et vérifiez que la valeur Registrar Pool pointe désormais vers le Skype pour Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="e868e-143">Additionally, we can view the list of users in the Skype for Business Server 2019 Control Panel and verify that the Registrar Pool value now points to the Skype for Business Server 2019 pool.</span></span>
    
     ![Skype pour la liste des utilisateurs Business Server 2019 le panneau de configuration](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  


---
title: Activation de la prise d’appel de groupe pour les utilisateurs et attribution d’un numéro de groupe dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Activer les utilisateurs pour le groupe d’appel collecte dans Skype pour Business Server Enterprise Voice, puis d’affecter un numéro de groupe.
ms.openlocfilehash: ce360bc1f66f3e7b55d3c0f8ea9e392d957f25ea
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business-2015"></a><span data-ttu-id="f12dd-103">Activation de la prise d’appel de groupe pour les utilisateurs et attribution d’un numéro de groupe dans Skype Entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="f12dd-103">Enable Group Call Pickup for users and assign a group number in Skype for Business 2015</span></span>
 
<span data-ttu-id="f12dd-104">Activer les utilisateurs pour le groupe d’appel collecte dans Skype pour Business Server Enterprise Voice, puis d’affecter un numéro de groupe.</span><span class="sxs-lookup"><span data-stu-id="f12dd-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>
  
<span data-ttu-id="f12dd-105">Après avoir ajouté le groupe collecte d’appeler des numéros à la table d’orbite de parcage d’appel, vous utilisez l’outil SEFAUtil pour attribuer les numéros de groupe aux utilisateurs et activer la collecte d’appel de groupe pour qu’ils.</span><span class="sxs-lookup"><span data-stu-id="f12dd-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f12dd-106">Dans un déploiement hybride, n’attribuez pas un groupe de collecte d’appel de groupe pour les utilisateurs hébergés en ligne.</span><span class="sxs-lookup"><span data-stu-id="f12dd-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="f12dd-107">Les utilisateurs hébergés en ligne ne peuvent pas participer à la collecte d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="f12dd-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="f12dd-108">Autrement dit, leurs appels ne peuvent pas être pris par d’autres utilisateurs et ils ne peuvent pas répondre aux appels destinés à d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f12dd-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span> 
  
### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="f12dd-109">Pour affecter un numéro de groupe et activer la collecte d’appel de groupe pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="f12dd-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="f12dd-110">Ouvrez une session sur l’ordinateur où vous avez installé l’outil SEFAUtil avec des droits d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="f12dd-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>
    
2. <span data-ttu-id="f12dd-111">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f12dd-111">At the command line, run:</span></span>
    
   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="f12dd-112">Par exemple, pour assigner le numéro de groupe 199 à un utilisateur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f12dd-112">For example, to assign group number 199 to a user:</span></span>
    
   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 
   ```

## <a name="see-also"></a><span data-ttu-id="f12dd-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f12dd-113">See also</span></span>

#### 

[<span data-ttu-id="f12dd-114">Collecte de groupe désactiver pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="f12dd-114">Disable Group Pickup for Users</span></span>](http://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)


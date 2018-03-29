---
title: Activation de la prise d’appel de groupe pour les utilisateurs et attribution d’un numéro de groupe dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Activer les utilisateurs pour la collecte d’appeler groupe dans Skype pour Business Server Voix Entreprise et affecter un numéro de groupe.
ms.openlocfilehash: aaacf080f9e7f7ae7f9bad3f8b13201972d7a72f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business-2015"></a><span data-ttu-id="7b087-103">Activation de la prise d’appel de groupe pour les utilisateurs et attribution d’un numéro de groupe dans Skype Entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="7b087-103">Enable Group Call Pickup for users and assign a group number in Skype for Business 2015</span></span>
 
<span data-ttu-id="7b087-104">Activer les utilisateurs pour la collecte d’appeler groupe dans Skype pour Business Server Voix Entreprise et affecter un numéro de groupe.</span><span class="sxs-lookup"><span data-stu-id="7b087-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>
  
<span data-ttu-id="7b087-105">Après avoir ajouté des numéros de groupe collecte d’appel à la table des appels park orbite, vous utilisez l’outil SEFAUtil pour attribuer les numéros de groupe aux utilisateurs et l’activer pour ceux-ci la collecte d’appeler de groupe.</span><span class="sxs-lookup"><span data-stu-id="7b087-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7b087-106">Dans un déploiement hybride, n’affectez pas un groupe de prise d’appel de groupe pour les utilisateurs qui sont hébergés en ligne.</span><span class="sxs-lookup"><span data-stu-id="7b087-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="7b087-107">Les utilisateurs qui sont hébergées en ligne ne peuvent pas participer à la collecte d’appeler de groupe.</span><span class="sxs-lookup"><span data-stu-id="7b087-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="7b087-108">Autrement dit, leurs appels ne peuvent pas être pris par d’autres utilisateurs et ils ne peuvent pas répondre aux appels destinés à d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7b087-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span> 
  
### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="7b087-109">Pour affecter un numéro de groupe et activer la collecte d’appeler de groupe pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="7b087-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="7b087-110">Ouvrez une session sur l’ordinateur où vous avez installé l’outil SEFAUtil avec des droits d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="7b087-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>
    
2. <span data-ttu-id="7b087-111">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7b087-111">At the command line, run:</span></span>
    
   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="7b087-112">Par exemple, pour assigner le numéro de groupe 199 à un utilisateur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="7b087-112">For example, to assign group number 199 to a user:</span></span>
    
   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 
   ```

## <a name="see-also"></a><span data-ttu-id="7b087-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7b087-113">See also</span></span>

#### 

[<span data-ttu-id="7b087-114">Remise en mains propres groupe de désactivation pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="7b087-114">Disable Group Pickup for Users</span></span>](http://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)


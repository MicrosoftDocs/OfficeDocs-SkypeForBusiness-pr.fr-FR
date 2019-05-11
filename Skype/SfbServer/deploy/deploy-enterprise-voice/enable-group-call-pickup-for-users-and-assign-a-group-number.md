---
title: Activer la collecte d’appel de groupe pour les utilisateurs et affecter un numéro de groupe dans Skype pour les entreprises
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Activer les utilisateurs pour le groupe d’appel collecte dans Skype pour Business Server Enterprise Voice, puis d’affecter un numéro de groupe.
ms.openlocfilehash: 92429e256a222d56ad7c281db57185b497f714e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892460"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="07938-103">Activer la collecte d’appel de groupe pour les utilisateurs et affecter un numéro de groupe dans Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="07938-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="07938-104">Activer les utilisateurs pour le groupe d’appel collecte dans Skype pour Business Server Enterprise Voice, puis d’affecter un numéro de groupe.</span><span class="sxs-lookup"><span data-stu-id="07938-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="07938-105">Après avoir ajouté le groupe collecte d’appeler des numéros à la table d’orbite de parcage d’appel, vous utilisez l’outil SEFAUtil pour attribuer les numéros de groupe aux utilisateurs et activer la collecte d’appel de groupe pour qu’ils.</span><span class="sxs-lookup"><span data-stu-id="07938-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="07938-106">Dans un déploiement hybride, n’attribuez pas un groupe de collecte d’appel de groupe pour les utilisateurs hébergés en ligne.</span><span class="sxs-lookup"><span data-stu-id="07938-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="07938-107">Les utilisateurs hébergés en ligne ne peuvent pas participer à la collecte d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="07938-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="07938-108">Autrement dit, leurs appels ne peuvent pas être pris par d’autres utilisateurs et ils ne peuvent pas répondre aux appels destinés à d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="07938-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="07938-109">Pour affecter un numéro de groupe et activer la collecte d’appel de groupe pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="07938-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="07938-110">Ouvrez une session sur l’ordinateur où vous avez installé l’outil SEFAUtil avec des droits d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="07938-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="07938-111">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="07938-111">At the command line, run:</span></span>

   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="07938-112">Par exemple, pour assigner le numéro de groupe 199 à un utilisateur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="07938-112">For example, to assign group number 199 to a user:</span></span>

   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="07938-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07938-113">See also</span></span>

[<span data-ttu-id="07938-114">Disable Group Pickup for Users</span><span class="sxs-lookup"><span data-stu-id="07938-114">Disable Group Pickup for Users</span></span>](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)


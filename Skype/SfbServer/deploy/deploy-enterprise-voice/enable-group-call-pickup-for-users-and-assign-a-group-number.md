---
title: Activer la prise d’appel de groupe pour les utilisateurs et attribuer un numéro de groupe dans Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Activez les utilisateurs pour la prise d’appel de groupe dans Skype Entreprise Server Voix Entreprise et attribuez un numéro de groupe.
ms.openlocfilehash: 3467aea1b9671a93cca2f66a2ac73c39f15dc26e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830964"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="6fe5e-103">Activer la prise d’appel de groupe pour les utilisateurs et attribuer un numéro de groupe dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="6fe5e-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="6fe5e-104">Activez les utilisateurs pour la prise d’appel de groupe dans Skype Entreprise Server Voix Entreprise et attribuez un numéro de groupe.</span><span class="sxs-lookup"><span data-stu-id="6fe5e-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="6fe5e-105">Après avoir ajouté des numéros de groupe de prise d’appel à la table des orbites de parcage d’appel, vous utilisez l’outil SEFAUtil pour affecter les numéros de groupe aux utilisateurs et activer la prise d’appel de groupe pour eux.</span><span class="sxs-lookup"><span data-stu-id="6fe5e-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="6fe5e-106">Dans un déploiement hybride, n’affectez pas de groupe de prise d’appel de groupe aux utilisateurs qui sont dos à dos en ligne.</span><span class="sxs-lookup"><span data-stu-id="6fe5e-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="6fe5e-107">Les utilisateurs qui sont en ligne ne peuvent pas participer à la prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="6fe5e-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="6fe5e-108">Autrement dit, leurs appels ne peuvent pas être répondus par d’autres utilisateurs et ils ne peuvent pas répondre aux appels à d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6fe5e-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="6fe5e-109">Pour affecter un numéro de groupe et activer la prise d’appel de groupe pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="6fe5e-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="6fe5e-110">Connectez-vous à l’ordinateur sur lequel vous avez installé l’outil SEFAUtil avec des droits d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="6fe5e-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="6fe5e-111">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6fe5e-111">At the command line, run:</span></span>

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="6fe5e-112">Par exemple, pour affecter le numéro de groupe 199 à un utilisateur :</span><span class="sxs-lookup"><span data-stu-id="6fe5e-112">For example, to assign group number 199 to a user:</span></span>

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="6fe5e-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6fe5e-113">See also</span></span>

[<span data-ttu-id="6fe5e-114">Désactiver la prise de groupe pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6fe5e-114">Disable Group Pickup for Users</span></span>](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)


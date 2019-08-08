---
title: Activez le prélèvement d’appel de groupe pour les utilisateurs et attribuez un numéro de groupe dans Skype entreprise.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Autorisez les utilisateurs à obtenir des appels de groupe dans Skype entreprise Server Voice et attribuez un numéro de groupe.
ms.openlocfilehash: 78bdd78bf7e5bb3a9438a60b54a89664d22666ee
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240347"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="e9adf-103">Activez le prélèvement d’appel de groupe pour les utilisateurs et attribuez un numéro de groupe dans Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="e9adf-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="e9adf-104">Autorisez les utilisateurs à obtenir des appels de groupe dans Skype entreprise Server Voice et attribuez un numéro de groupe.</span><span class="sxs-lookup"><span data-stu-id="e9adf-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="e9adf-105">Dès lors que vous ajoutez des numéros de groupe de cueillette d’appel à la table d’orbite du parc d’appels, vous utilisez l’outil SEFAUtil pour attribuer les numéros de groupe aux utilisateurs et activer le prélèvement d’appels de groupe.</span><span class="sxs-lookup"><span data-stu-id="e9adf-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="e9adf-106">Dans un déploiement hybride, n’affectez pas de groupe de collecte d’appels de groupe aux utilisateurs hébergés en ligne.</span><span class="sxs-lookup"><span data-stu-id="e9adf-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="e9adf-107">Les utilisateurs hébergés en ligne ne peuvent pas participer à la cueillette du groupe.</span><span class="sxs-lookup"><span data-stu-id="e9adf-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="e9adf-108">Autrement dit, leurs appels ne peuvent pas être pris par d’autres utilisateurs et ils ne peuvent pas répondre aux appels destinés à d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e9adf-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="e9adf-109">Pour attribuer un numéro de groupe et activer le prélèvement d’appels de groupe pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="e9adf-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="e9adf-110">Ouvrez une session sur l’ordinateur où vous avez installé l’outil SEFAUtil avec des droits d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="e9adf-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="e9adf-111">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="e9adf-111">At the command line, run:</span></span>

   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="e9adf-112">Par exemple, pour assigner le numéro de groupe 199 à un utilisateur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e9adf-112">For example, to assign group number 199 to a user:</span></span>

   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="e9adf-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e9adf-113">See also</span></span>

[<span data-ttu-id="e9adf-114">Disable Group Pickup for Users</span><span class="sxs-lookup"><span data-stu-id="e9adf-114">Disable Group Pickup for Users</span></span>](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)


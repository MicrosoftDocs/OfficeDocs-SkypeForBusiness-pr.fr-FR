---
title: Déplacer un seul utilisateur vers le pool pilote
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
description: Vous pouvez déplacer un utilisateur de votre pool hérité vers votre pool de test Skype entreprise Server 2019 à l’aide du panneau de configuration de Skype entreprise Server 2019 ou de Skype entreprise Server 2019 Management Shell. Dans l’exemple ci-dessous, dans la colonne pool de serveurs d’inscriptions, pool01.contoso.net est le pool hérité et tous les six de ces utilisateurs sont connectés à ce pool. Utilisez les procédures suivantes pour déplacer un utilisateur vers votre pool Skype entreprise Server 2019 à l’aide du panneau de configuration de Skype entreprise Server 2019 et de Skype entreprise Server Management Shell.
ms.openlocfilehash: 6be30f37987cc31835a12178d32a8337d9fc5cae
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752506"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="8c246-105">Déplacer un seul utilisateur vers le pool pilote</span><span class="sxs-lookup"><span data-stu-id="8c246-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="8c246-106">Vous pouvez déplacer un utilisateur de votre pool hérité vers votre pool de test Skype entreprise Server 2019 à l’aide du panneau de configuration de Skype entreprise Server 2019 ou de Skype entreprise Server 2019 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8c246-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="8c246-107">Dans l’exemple ci-dessous, dans la colonne pool de serveurs d' **inscriptions** , **pool01.contoso.net** est le pool hérité et tous les six de ces utilisateurs sont connectés à ce pool.</span><span class="sxs-lookup"><span data-stu-id="8c246-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="8c246-108">Utilisez les procédures suivantes pour déplacer un utilisateur vers votre pool Skype entreprise Server 2019 à l’aide du panneau de configuration de Skype entreprise Server 2019 et de Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8c246-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="8c246-109">Pour déplacer un utilisateur à l’aide du panneau de configuration de Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="8c246-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="8c246-110">Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou membre du rôle d’administrateur CsAdministrator ou CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8c246-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="8c246-111">Ouvrez **le panneau de configuration de Skype entreprise Server**.</span><span class="sxs-lookup"><span data-stu-id="8c246-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="8c246-112">Cliquez sur **utilisateurs**, sur **recherche**, puis sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="8c246-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="8c246-113">Sélectionnez un utilisateur que vous souhaitez déplacer vers le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8c246-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="8c246-114">Dans cet exemple, nous allons déplacer l’utilisateur Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="8c246-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="8c246-115">Dans le menu **Action**, sélectionnez **Déplacer les utilisateurs sélectionnés vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="8c246-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="8c246-116">Dans la liste déroulante, sélectionnez le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8c246-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="8c246-117">Cliquez sur **Action**, puis sur **Déplacer les utilisateurs sélectionnés vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="8c246-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="8c246-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c246-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="8c246-119">Vérifiez que la colonne pool de serveurs d' **inscriptions** de l’utilisateur contient désormais le pool Skype entreprise Server 2019, ce qui indique que l’utilisateur a été déplacé avec succès.</span><span class="sxs-lookup"><span data-stu-id="8c246-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="8c246-120">Pour déplacer un utilisateur à l’aide de Skype entreprise Server 2019 Management Shell</span><span class="sxs-lookup"><span data-stu-id="8c246-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="8c246-121">Ouvrez Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8c246-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="8c246-122">Sur la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="8c246-122">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="8c246-123">Ensuite, sur la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="8c246-123">Next, at the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="8c246-124">L’identité **RegistrarPool** pointe désormais vers le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8c246-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="8c246-125">Le présence de cette identité confirme que l’utilisateur a été déplacé avec succès.</span><span class="sxs-lookup"><span data-stu-id="8c246-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="8c246-126">Pour plus d’informations sur la cmdlet **Get-Csuser** , exécutez : **Get-Help Get-Csuser-detailed**</span><span class="sxs-lookup"><span data-stu-id="8c246-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  


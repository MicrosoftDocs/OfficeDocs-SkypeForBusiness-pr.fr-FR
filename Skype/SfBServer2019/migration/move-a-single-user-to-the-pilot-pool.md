---
title: Déplacer un utilisateur unique vers le pool de pilotes
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous pouvez déplacer un utilisateur de votre liste héritée vers votre pool de pilotes Skype entreprise Server 2019 à l’aide de Skype entreprise Server 2019 le panneau de configuration ou de Skype entreprise Server 2019 Management Shell. Dans l’exemple ci-dessous, dans la colonne pool d’inscriptions, pool01.contoso.net est le pool hérité, et les six de ces utilisateurs sont connectés à ce pool. Utilisez les procédures suivantes pour déplacer un utilisateur vers votre pool Skype entreprise Server 2019 à l’aide de Skype entreprise Server 2019 le panneau de configuration et de Skype entreprise Server Management Shell.
ms.openlocfilehash: 456035cfd917f620383d4dff70f6366cd73d530e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237764"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="fcc1b-105">Déplacer un utilisateur unique vers le pool de pilotes</span><span class="sxs-lookup"><span data-stu-id="fcc1b-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="fcc1b-106">Vous pouvez déplacer un utilisateur de votre liste héritée vers votre pool de pilotes Skype entreprise Server 2019 à l’aide de Skype entreprise Server 2019 le panneau de configuration ou de Skype entreprise Server 2019 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="fcc1b-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="fcc1b-107">Dans l’exemple ci-dessous, dans la colonne **pool d’inscriptions** , **pool01.contoso.net** est le pool hérité, et les six de ces utilisateurs sont connectés à ce pool.</span><span class="sxs-lookup"><span data-stu-id="fcc1b-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="fcc1b-108">Utilisez les procédures suivantes pour déplacer un utilisateur vers votre pool Skype entreprise Server 2019 à l’aide de Skype entreprise Server 2019 le panneau de configuration et de Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="fcc1b-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="fcc1b-109">Pour déplacer un utilisateur à l’aide du panneau de configuration Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="fcc1b-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="fcc1b-110">Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou du rôle d’admistrateur CsAdministrator ou CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fcc1b-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="fcc1b-111">Ouvrez **le panneau de configuration Skype entreprise Server**.</span><span class="sxs-lookup"><span data-stu-id="fcc1b-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="fcc1b-112">Cliquez sur **utilisateurs**, sur **recherche**, puis sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="fcc1b-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="fcc1b-113">Sélectionnez l’utilisateur que vous voulez déplacer vers le pool 2019 de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="fcc1b-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="fcc1b-114">Dans l’exemple suivant, nous déplacerons l’utilisateur Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="fcc1b-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="fcc1b-115">Dans le menu **Action**, sélectionnez **Déplacer les utilisateurs sélectionnés vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="fcc1b-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="fcc1b-116">Dans la liste déroulante, sélectionnez le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="fcc1b-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="fcc1b-117">Cliquez sur **action**, puis sur **déplacer les utilisateurs sélectionnés vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="fcc1b-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="fcc1b-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fcc1b-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="fcc1b-119">Vérifiez que la colonne **pool d’inscriptions** pour l’utilisateur contient désormais le pool 2019 de Skype entreprise Server, qui indique que l’utilisateur a été déplacée avec succès.</span><span class="sxs-lookup"><span data-stu-id="fcc1b-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="fcc1b-120">Pour déplacer un utilisateur à l’aide de Skype entreprise Server 2019 Management Shell</span><span class="sxs-lookup"><span data-stu-id="fcc1b-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="fcc1b-121">Ouvrez Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="fcc1b-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="fcc1b-122">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="fcc1b-122">At the command line, type the following:</span></span> 
    
   ```
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="fcc1b-123">Ensuite, dans la ligne de commande, tapez ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="fcc1b-123">Next, at the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="fcc1b-124">L’identité **RegistrarPool** pointe désormais vers le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="fcc1b-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="fcc1b-125">La présence de cette identité confirme que l’utilisateur a bien été déplacé.</span><span class="sxs-lookup"><span data-stu-id="fcc1b-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="fcc1b-126">Pour plus d’informations sur l’applet de connexion **Get-Csuser** , exécutez: **Get-Help Get-Csuser-detailed**</span><span class="sxs-lookup"><span data-stu-id="fcc1b-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  


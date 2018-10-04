---
title: Déplacement d’un utilisateur vers le pool pilote
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous pouvez déplacer un utilisateur à partir de votre pool hérité vers votre Skype pour le pool pilote Business Server 2019 à l’aide de Skype pour Business Server 2019 le panneau de configuration ou Skype pour Business Server 2019 Management Shell. Dans l’exemple ci-dessous, dans la colonne pool de serveurs d’inscriptions, pool01.contoso.net est le pool hérité et tous les six de ces utilisateurs sont connectés à ce pool. Utilisez les procédures suivantes pour déplacer un utilisateur à votre Skype pour Business Server 2019 pool à l’aide de Skype pour Business Server 2019 le panneau de configuration et Skype pour Business Server Management Shell.
ms.openlocfilehash: 6742c5fc00c9d53030ac32ee698686bb8b11fa07
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372744"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="c5ebc-105">Déplacement d’un utilisateur vers le pool pilote</span><span class="sxs-lookup"><span data-stu-id="c5ebc-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="c5ebc-106">Vous pouvez déplacer un utilisateur à partir de votre pool hérité vers votre Skype pour le pool pilote Business Server 2019 à l’aide de Skype pour Business Server 2019 le panneau de configuration ou Skype pour Business Server 2019 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c5ebc-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="c5ebc-107">Dans l’exemple ci-dessous, dans la colonne **pool de serveurs d’inscriptions** , **pool01.contoso.net** est le pool hérité et tous les six de ces utilisateurs sont connectés à ce pool.</span><span class="sxs-lookup"><span data-stu-id="c5ebc-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="c5ebc-108">Utilisez les procédures suivantes pour déplacer un utilisateur à votre Skype pour Business Server 2019 pool à l’aide de Skype pour Business Server 2019 le panneau de configuration et Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c5ebc-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="c5ebc-109">Pour déplacer un utilisateur à l’aide de la Skype pour Business Server 2019 le panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="c5ebc-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="c5ebc-110">Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou du rôle d’administrateur CsAdministrator ou CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c5ebc-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="c5ebc-111">Ouvrez **Skype pour le panneau de configuration serveur Business**.</span><span class="sxs-lookup"><span data-stu-id="c5ebc-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="c5ebc-112">Cliquez sur **utilisateurs**, cliquez sur **Rechercher**, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="c5ebc-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="c5ebc-113">Sélectionnez un utilisateur que vous souhaitez déplacer vers le Skype pour Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="c5ebc-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="c5ebc-114">Dans cet exemple, nous avons déplace utilisateur Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="c5ebc-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="c5ebc-115">Dans le menu **Action**, sélectionnez **Déplacer les utilisateurs sélectionnés vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="c5ebc-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="c5ebc-116">Dans la liste déroulante, sélectionnez le Skype pour Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="c5ebc-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="c5ebc-117">Cliquez sur **Action**, puis cliquez sur **déplacer les utilisateurs sélectionnés vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="c5ebc-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="c5ebc-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c5ebc-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="c5ebc-119">Vérifiez que la colonne **pool de serveurs d’inscriptions** de l’utilisateur contient maintenant le Skype pour Business Server 2019 pool, ce qui indique que l’utilisateur a été déplacé avec succès.</span><span class="sxs-lookup"><span data-stu-id="c5ebc-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="c5ebc-120">Pour déplacer un utilisateur à l’aide de la Skype pour Business Server 2019 Management Shell</span><span class="sxs-lookup"><span data-stu-id="c5ebc-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="c5ebc-121">Ouvrez le Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c5ebc-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="c5ebc-122">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="c5ebc-122">At the command line, type the following:</span></span> 
    
   ```
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="c5ebc-123">Ensuite, à l’invite de commandes, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="c5ebc-123">Next, at the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="c5ebc-124">L’identité **RegistrarPool** pointe désormais vers le Skype pour Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="c5ebc-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="c5ebc-125">La présence de cette identité confirme que l’utilisateur a été déplacé avec succès.</span><span class="sxs-lookup"><span data-stu-id="c5ebc-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="c5ebc-126">Pour plus d’informations sur l’applet de commande **Get-CsUser** , exécutez : **Get-Help Get-CsUser-détaillées**</span><span class="sxs-lookup"><span data-stu-id="c5ebc-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  


---
title: Activer le parcage d’appel pour les utilisateurs de Skype pour les entreprises
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Activer les utilisateurs pour la mise en garde d’appels dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 98b02294beb633e5d9a0147fcce7257a4497753d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212508"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a><span data-ttu-id="635d8-103">Activer le parcage d’appel pour les utilisateurs de Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="635d8-103">Enable Call Park for users in Skype for Business</span></span>
 
<span data-ttu-id="635d8-104">Activer les utilisateurs pour la mise en garde d’appels dans Skype pour Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="635d8-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="635d8-105">Par défaut, la mise en garde d’appels est désactivé pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="635d8-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="635d8-106">Les utilisateurs ne peuvent pas mettre en garde d’appels ou récupérer les appels mis en garde tant qu’ils sont activés pour le parcage d’appel dans la stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="635d8-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="635d8-107">Vous pouvez activer la mise en garde d’appels au niveau global ou au niveau de l’étendue site ou utilisateur.</span><span class="sxs-lookup"><span data-stu-id="635d8-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="635d8-108">L’étendue d’utilisateur est prioritaire sur l’étendue du site et l’étendue du site est prioritaire sur l’étendue globale.</span><span class="sxs-lookup"><span data-stu-id="635d8-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="635d8-109">Si vous avez plusieurs stratégies de voix, passez en revue toutes les stratégies pour activer le parcage d’appel, pas seulement la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="635d8-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="635d8-110">Pour utiliser Skype pour Business Server Control Panel pour activer le parcage d’appel pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="635d8-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="635d8-111">Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="635d8-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="635d8-112">Ouvrez le panneau de configuration serveur Business Skype.</span><span class="sxs-lookup"><span data-stu-id="635d8-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="635d8-113">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="635d8-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="635d8-114">Cliquez sur l’onglet **Stratégie de la voix**.</span><span class="sxs-lookup"><span data-stu-id="635d8-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="635d8-115">Double-cliquez sur une stratégie de voix existante pour ouvrir la boîte de dialogue **Modifier la stratégie de voix**.</span><span class="sxs-lookup"><span data-stu-id="635d8-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="635d8-116">Sous **Fonctionnalités d’appel**, sélectionnez **Activer le parcage d’appel**.</span><span class="sxs-lookup"><span data-stu-id="635d8-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="635d8-117">Cliquez sur **OK** pour enregistrer la stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="635d8-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="635d8-118">Pour utiliser les applets de commande pour activer le parcage d’appel pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="635d8-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="635d8-119">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle d’administrateur CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="635d8-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="635d8-120">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="635d8-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="635d8-121">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="635d8-121">Run:</span></span>
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="635d8-122">Par exemple, pour activer la mise en garde d’appels pour la stratégie de voix globale par défaut :</span><span class="sxs-lookup"><span data-stu-id="635d8-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="635d8-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="635d8-123">See also</span></span>



[<span data-ttu-id="635d8-124">Créer ou modifier une stratégie de voix et configurer les enregistrements d’utilisation PSTN dans Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="635d8-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)


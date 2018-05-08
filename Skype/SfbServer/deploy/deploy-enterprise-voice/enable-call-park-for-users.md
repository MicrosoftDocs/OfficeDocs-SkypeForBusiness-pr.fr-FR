---
title: Activation du parcage d’appel pour les utilisateurs dans Skype Entreprise 2015
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
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Activer les utilisateurs pour la mise en garde d’appels dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: b93a9393a095a4860bfd8f392f95d834dad6fa71
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="enable-call-park-for-users-in-skype-for-business-2015"></a><span data-ttu-id="9252f-103">Activation du parcage d’appel pour les utilisateurs dans Skype Entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="9252f-103">Enable Call Park for users in Skype for Business 2015</span></span>
 
<span data-ttu-id="9252f-104">Activer les utilisateurs pour la mise en garde d’appels dans Skype pour Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="9252f-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="9252f-105">Par défaut, la mise en garde d’appels est désactivé pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="9252f-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="9252f-106">Les utilisateurs ne peuvent pas mettre en garde d’appels ou récupérer les appels mis en garde tant qu’ils sont activés pour le parcage d’appel dans la stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="9252f-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="9252f-107">Vous pouvez activer la mise en garde d’appels au niveau global ou au niveau de l’étendue site ou utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9252f-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="9252f-108">L’étendue d’utilisateur est prioritaire sur l’étendue du site et l’étendue du site est prioritaire sur l’étendue globale.</span><span class="sxs-lookup"><span data-stu-id="9252f-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="9252f-109">Si vous avez plusieurs stratégies de voix, passez en revue toutes les stratégies pour activer le parcage d’appel, pas seulement la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="9252f-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="9252f-110">Pour utiliser Skype pour Business Server Control Panel pour activer le parcage d’appel pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="9252f-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="9252f-111">Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="9252f-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="9252f-112">Ouvrez le panneau de configuration serveur Business Skype.</span><span class="sxs-lookup"><span data-stu-id="9252f-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="9252f-113">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="9252f-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="9252f-114">Cliquez sur l’onglet **Stratégie de la voix**.</span><span class="sxs-lookup"><span data-stu-id="9252f-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="9252f-115">Double-cliquez sur une stratégie de voix existante pour ouvrir la boîte de dialogue **Modifier la stratégie de voix**.</span><span class="sxs-lookup"><span data-stu-id="9252f-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="9252f-116">Sous **Fonctionnalités d’appel**, sélectionnez **Activer le parcage d’appel**.</span><span class="sxs-lookup"><span data-stu-id="9252f-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="9252f-117">Cliquez sur **OK** pour enregistrer la stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="9252f-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="9252f-118">Pour utiliser les applets de commande pour activer le parcage d’appel pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="9252f-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="9252f-119">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle d’administrateur CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9252f-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="9252f-120">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9252f-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="9252f-121">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="9252f-121">Run:</span></span>
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="9252f-122">Par exemple, pour activer la mise en garde d’appels pour la stratégie de voix globale par défaut :</span><span class="sxs-lookup"><span data-stu-id="9252f-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="9252f-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9252f-123">See also</span></span>

#### 

[<span data-ttu-id="9252f-124">Créer ou modifier une stratégie de voix et configurer les enregistrements d’utilisation PSTN dans Skype pour Business 2015</span><span class="sxs-lookup"><span data-stu-id="9252f-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015</span></span>](voice-policy-and-pstn-usage-records.md)


---
title: Activation du parcage d’appel pour les utilisateurs dans Skype Entreprise 2015
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
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Activer les utilisateurs pour un parc d’appel dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 3af13e59541799a75c58f6e796bf07e7a978065e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="enable-call-park-for-users-in-skype-for-business-2015"></a><span data-ttu-id="cc65a-103">Activation du parcage d’appel pour les utilisateurs dans Skype Entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="cc65a-103">Enable Call Park for users in Skype for Business 2015</span></span>
 
<span data-ttu-id="cc65a-104">Activer les utilisateurs pour un parc d’appel dans Skype pour Business Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="cc65a-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="cc65a-105">Par défaut, le parc d’appel est désactivée pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="cc65a-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="cc65a-106">Les utilisateurs ne peuvent pas se les appels ou récupérer des appels en stationnement jusqu'à ce qu’ils sont activés pour le parc de l’appel dans une stratégie voice.</span><span class="sxs-lookup"><span data-stu-id="cc65a-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="cc65a-107">Vous pouvez activer le parc d’appel à la portée globale ou à la portée de site ou de la portée de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cc65a-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="cc65a-108">L’étendue d’utilisateur est prioritaire sur l’étendue du site et l’étendue du site est prioritaire sur l’étendue globale.</span><span class="sxs-lookup"><span data-stu-id="cc65a-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="cc65a-109">Si vous avez plusieurs stratégies de voix, passez en revue toutes les stratégies pour activer les appels Park, pas seulement à la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="cc65a-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="cc65a-110">Utiliser Skype pour panneau Business Server pour activer appel Park pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="cc65a-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="cc65a-111">Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="cc65a-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="cc65a-112">Ouvrez Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="cc65a-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="cc65a-113">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="cc65a-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="cc65a-114">Cliquez sur l’onglet **Stratégie de la voix**.</span><span class="sxs-lookup"><span data-stu-id="cc65a-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="cc65a-115">Double-cliquez sur une stratégie de voix existante pour ouvrir la boîte de dialogue **Modifier la stratégie de voix**.</span><span class="sxs-lookup"><span data-stu-id="cc65a-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="cc65a-116">Sous **Fonctionnalités d’appel**, sélectionnez **Activer le parcage d’appel**.</span><span class="sxs-lookup"><span data-stu-id="cc65a-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="cc65a-117">Cliquez sur **OK** pour enregistrer la stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="cc65a-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="cc65a-118">À utiliser des applets de commande pour activer appel Park d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="cc65a-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="cc65a-119">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle d’administrateur CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cc65a-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="cc65a-120">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="cc65a-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="cc65a-121">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="cc65a-121">Run:</span></span>
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="cc65a-122">Par exemple, pour activer un appel Park la stratégie par défaut vocales globales :</span><span class="sxs-lookup"><span data-stu-id="cc65a-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="cc65a-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cc65a-123">See also</span></span>

#### 

[<span data-ttu-id="cc65a-124">Créer ou modifier une stratégie de voix et configurer les enregistrements d’utilisation de TLS dans Skype pour entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="cc65a-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015</span></span>](voice-policy-and-pstn-usage-records.md)


---
title: Activer le parc d’appel pour les utilisateurs dans Skype Entreprise
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
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Activez les utilisateurs pour le parc d’appel dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: e9bbc42f5940af0cfc94ab83eae981dd023c9fcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830954"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a><span data-ttu-id="bceec-103">Activer le parc d’appel pour les utilisateurs dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="bceec-103">Enable Call Park for users in Skype for Business</span></span>
 
<span data-ttu-id="bceec-104">Activez les utilisateurs pour le parc d’appel dans Skype Entreprise Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="bceec-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="bceec-105">Par défaut, le parc d’appel est désactivé pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="bceec-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="bceec-106">Les utilisateurs ne peuvent pas parer des appels ou récupérer des appels par parcés tant qu’ils n’ont pas été activés pour le parcier d’appel dans la stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="bceec-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="bceec-107">Vous pouvez activer le parc d’appel au niveau de l’étendue globale, de l’étendue Site ou utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bceec-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="bceec-108">L’étendue d’utilisateur est prioritaire sur l’étendue du site et l’étendue du site est prioritaire sur l’étendue globale.</span><span class="sxs-lookup"><span data-stu-id="bceec-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="bceec-109">Si vous avez plusieurs stratégies de voix, examinez toutes les stratégies pour activer le parcier d’appel, pas seulement la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="bceec-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="bceec-110">Pour utiliser le Panneau de contrôle Skype Entreprise Server pour activer le parc d’appel pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="bceec-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="bceec-111">Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="bceec-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="bceec-112">Ouvrez le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="bceec-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="bceec-113">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="bceec-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="bceec-114">Cliquez sur l’onglet **Stratégie de la voix**.</span><span class="sxs-lookup"><span data-stu-id="bceec-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="bceec-115">Double-cliquez sur une stratégie de voix existante pour ouvrir la boîte de dialogue **Modifier la stratégie de voix**.</span><span class="sxs-lookup"><span data-stu-id="bceec-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="bceec-116">Sous **Fonctionnalités d’appel**, sélectionnez **Activer le parcage d’appel**.</span><span class="sxs-lookup"><span data-stu-id="bceec-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="bceec-117">Cliquez sur **OK** pour enregistrer la stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="bceec-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="bceec-118">Pour utiliser des cmdlets pour activer le parcier d’appel pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="bceec-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="bceec-119">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins, ou en tant que membre du rôle d’administrateur CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="bceec-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="bceec-120">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="bceec-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="bceec-121">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="bceec-121">Run:</span></span>
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="bceec-122">Par exemple, pour activer le parc d’appel pour la stratégie de voix globale par défaut :</span><span class="sxs-lookup"><span data-stu-id="bceec-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="bceec-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bceec-123">See also</span></span>



[<span data-ttu-id="bceec-124">Créer ou modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="bceec-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)


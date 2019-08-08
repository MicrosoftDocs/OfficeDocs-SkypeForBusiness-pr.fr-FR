---
title: Activer le parc d’appels pour les utilisateurs de Skype entreprise
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
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Autorisez les utilisateurs à utiliser le parc d’appels dans Skype entreprise Server Voice.
ms.openlocfilehash: 797b17cb3d9482d9059bedcbbc347c3dd592e478
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240374"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a><span data-ttu-id="f88cb-103">Activer le parc d’appels pour les utilisateurs de Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="f88cb-103">Enable Call Park for users in Skype for Business</span></span>
 
<span data-ttu-id="f88cb-104">Autorisez les utilisateurs à utiliser le parc d’appels dans Skype entreprise Server Voice.</span><span class="sxs-lookup"><span data-stu-id="f88cb-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="f88cb-105">Par défaut, le parc d’appels est désactivé pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f88cb-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="f88cb-106">Les utilisateurs ne peuvent pas parcer les appels ou récupérer les appels en stationnement tant qu’ils sont activés pour le parc d’appels dans la politique vocale.</span><span class="sxs-lookup"><span data-stu-id="f88cb-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="f88cb-107">Vous pouvez activer le parc d’appels au niveau de l’étendue globale, ou à l’étendue du site ou l’étendue de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f88cb-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="f88cb-108">L’étendue d’utilisateur est prioritaire sur l’étendue du site et l’étendue du site est prioritaire sur l’étendue globale.</span><span class="sxs-lookup"><span data-stu-id="f88cb-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="f88cb-109">Si vous avez plusieurs stratégies vocales, passez en revue toutes les stratégies pour activer le parc d’appels, pas seulement la politique globale.</span><span class="sxs-lookup"><span data-stu-id="f88cb-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="f88cb-110">Pour utiliser le panneau de configuration Skype entreprise Server pour activer le parc d’appels pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="f88cb-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="f88cb-111">Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="f88cb-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="f88cb-112">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f88cb-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f88cb-113">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="f88cb-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="f88cb-114">Cliquez sur l’onglet **Stratégie de la voix**.</span><span class="sxs-lookup"><span data-stu-id="f88cb-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="f88cb-115">Double-cliquez sur une stratégie de voix existante pour ouvrir la boîte de dialogue **Modifier la stratégie de voix**.</span><span class="sxs-lookup"><span data-stu-id="f88cb-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="f88cb-116">Sous **Fonctionnalités d’appel**, sélectionnez **Activer le parcage d’appel**.</span><span class="sxs-lookup"><span data-stu-id="f88cb-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="f88cb-117">Cliquez sur **OK** pour enregistrer la stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="f88cb-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="f88cb-118">Utiliser des cmdlets pour activer le parc d’appels pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="f88cb-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="f88cb-119">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle d’administrateur CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f88cb-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="f88cb-120">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f88cb-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f88cb-121">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="f88cb-121">Run:</span></span>
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="f88cb-122">Par exemple, pour activer le parc d’appels pour la stratégie vocale globale par défaut:</span><span class="sxs-lookup"><span data-stu-id="f88cb-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="f88cb-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f88cb-123">See also</span></span>



[<span data-ttu-id="f88cb-124">Création ou modification d’une stratégie de voix et configuration des enregistrements d’utilisation RTC dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="f88cb-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)


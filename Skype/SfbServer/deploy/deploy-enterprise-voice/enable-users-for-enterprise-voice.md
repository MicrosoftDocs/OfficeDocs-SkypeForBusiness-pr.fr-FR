---
title: Activer les utilisateurs pour voix entreprise dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Résumé: Découvrez comment permettre aux utilisateurs d’émettre et de recevoir des appels à l’aide d’Enterprise Voice dans Skype entreprise Server.'
ms.openlocfilehash: 8a94fe28cc492cdeac5eee476d6886fc8674ae13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303297"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="08b29-103">Activer les utilisateurs pour voix entreprise dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="08b29-103">Enable users for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="08b29-104">**Résumé:** Découvrez comment permettre aux utilisateurs d’émettre et de recevoir des appels à l’aide d’Enterprise Voice dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="08b29-104">**Summary:** Learn how to enable users to make and receive calls by using Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="08b29-105">Après avoir déployé une voix d’entreprise ou un appel par le biais de votre entreprise, vous pouvez utiliser les procédures suivantes pour permettre à un utilisateur d’effectuer des appels à l’aide de la voix entreprise:</span><span class="sxs-lookup"><span data-stu-id="08b29-105">After you deploy Enterprise Voice or Call Via Work, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>
  
> [!NOTE]
> <span data-ttu-id="08b29-106">Parmi les procédures ci-dessous, seules les premières peuvent être effectuées à l’aide du panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="08b29-106">Of the following procedures, only the first can be performed by using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="08b29-107">Pour les procédures restantes, vous pouvez uniquement utiliser Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="08b29-107">For the remaining procedures, you can use only Skype for Business Server Management Shell.</span></span> 
  
- <span data-ttu-id="08b29-108">Activez le compte d’utilisateur voix entreprise voix.</span><span class="sxs-lookup"><span data-stu-id="08b29-108">Enable the user account for Enterprise Voice.</span></span>
    
- <span data-ttu-id="08b29-109">(Facultatif) Affectez au compte d’utilisateur une stratégie de voix spécifique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="08b29-109">(Optional) Assign the user account a user-specific voice policy.</span></span>
    
- <span data-ttu-id="08b29-110">(Facultatif) Affectez au compte d’utilisateur un plan de numérotation spécifique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="08b29-110">(Optional) Assign the user account a user-specific dial plan.</span></span>
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="08b29-111">Pour activer un compte d’utilisateur pour voix entreprise</span><span class="sxs-lookup"><span data-stu-id="08b29-111">To enable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="08b29-112">Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="08b29-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="08b29-113">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="08b29-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="08b29-114">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="08b29-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="08b29-115">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur à activer, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="08b29-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="08b29-116">Dans la table, cliquez sur le compte d’utilisateur que vous souhaitez activer pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="08b29-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="08b29-117">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="08b29-117">On the **Edit** menu, click **Show details**.</span></span>
    
7. <span data-ttu-id="08b29-118">Dans la page **modifier l’utilisateur de Skype entreprise Server** , sous **téléphonie**, cliquez sur **voix entreprise**.</span><span class="sxs-lookup"><span data-stu-id="08b29-118">On the **Edit Skype for Business Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="08b29-119">Cliquez sur **URI de ligne**, puis tapez un numéro de téléphone normalisé unique (par exemple, tél :+14255550200).</span><span class="sxs-lookup"><span data-stu-id="08b29-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
9. <span data-ttu-id="08b29-120">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="08b29-120">Click **Commit**.</span></span>
    
<span data-ttu-id="08b29-121">Pour terminer l’activation d’un utilisateur pour voix entreprise, assurez-vous que l’utilisateur dispose d’une stratégie vocale et d’un plan de numérotation, qu’il s’agisse de global (attribué par défaut) ou d’utilisateur. Par défaut, tous les utilisateurs se voient attribuer une stratégie vocale globale et un plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="08b29-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="08b29-122">S’il existe une stratégie de voix ou un plan de numérotation au niveau du site sur lequel un compte d’utilisateur est hébergé, cette stratégie de site s’applique automatiquement à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="08b29-122">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="08b29-123">Pour appliquer une stratégie de voix ou un plan de numérotation à un utilisateur, vous devez exécuter les applets de commande **Grant-CsVoicePolicy** et **Grant-CsDialPlan**.</span><span class="sxs-lookup"><span data-stu-id="08b29-123">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="08b29-124">Pour plus d’informations, reportez-vous aux procédures suivantes de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="08b29-124">For details, see the following procedures in this topic.</span></span>
## <a name="voice-policy-assignment"></a><span data-ttu-id="08b29-125">Affectation d’une stratégie de voix</span><span class="sxs-lookup"><span data-stu-id="08b29-125">Voice Policy Assignment</span></span>

<span data-ttu-id="08b29-126">Les stratégies de voix globale et de niveau site sont automatiquement affectées à tous les comptes d’utilisateurs activés pour Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="08b29-126">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="08b29-127">Vous pouvez également créer des stratégies de voix qui s’appliquent à des utilisateurs ou à des groupes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="08b29-127">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="08b29-128">Ces stratégies utilisateur doivent être affectées explicitement à des utilisateurs ou à des groupes.</span><span class="sxs-lookup"><span data-stu-id="08b29-128">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="08b29-129">Si vous souhaitez utiliser la politique globale ou vocale pour tous les utilisateurs qui sont activés pour voix entreprise, vous pouvez ignorer cette section et poursuivre la section [affectation de plan](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) de numérotation plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="08b29-129">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to [Dial Plan Assignment](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) section later in this topic.</span></span>
  
### <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="08b29-130">Pour affecter une stratégie de voix spécifique à l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="08b29-130">To assign a user-specific voice policy</span></span>

1. <span data-ttu-id="08b29-131">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="08b29-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="08b29-132">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="08b29-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="08b29-133">Pour affecter une stratégie de voix utilisateur existante à un utilisateur, exécutez la commande suivante dans l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="08b29-133">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
   ```
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="08b29-134">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="08b29-134">For example:</span></span>
    
   ```
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    <span data-ttu-id="08b29-135">Dans cet exemple, l’utilisateur portant le nom d’affichage Bob Kelly reçoit la politique vocale portant le nom **VoicePolicyJapan**.</span><span class="sxs-lookup"><span data-stu-id="08b29-135">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>
    
## <a name="dial-plan-assignment"></a><span data-ttu-id="08b29-136">Affectation d’un plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="08b29-136">Dial Plan Assignment</span></span>
<span data-ttu-id="08b29-137"><a name="BKMK_DialPlanAssignment"> </a></span><span class="sxs-lookup"><span data-stu-id="08b29-137"></span></span>

<span data-ttu-id="08b29-138">Pour achever la configuration de compte d’utilisateur pour les utilisateurs d’Enterprise Voice ou les utilisateurs de conférences rendez-vous, l’utilisateur doit être affecté d’un plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="08b29-138">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="08b29-139">Les comptes d’utilisateurs utilisent automatiquement le plan de numérotation global ou, le cas échéant, le plan de numérotation au niveau du site si vous n’affectez pas explicitement un plan de numérotation utilisateur existant.</span><span class="sxs-lookup"><span data-stu-id="08b29-139">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="08b29-140">Si vous souhaitez utiliser le plan de numérotation global ou de numérotation de site pour tous les utilisateurs qui sont activés pour voix entreprise, vous pouvez ignorer cette section.</span><span class="sxs-lookup"><span data-stu-id="08b29-140">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>
  
### <a name="to-assign-a-user-specific-dial-plan"></a><span data-ttu-id="08b29-141">Affectation d’un plan de numérotation propre à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="08b29-141">To assign a user-specific dial plan</span></span>

1. <span data-ttu-id="08b29-142">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="08b29-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="08b29-143">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="08b29-143">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="08b29-144">Pour affecter un plan de numérotation spécifique à un utilisateur, exécutez la commande suivante dans l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="08b29-144">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
   ```
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="08b29-145">Exemple :</span><span class="sxs-lookup"><span data-stu-id="08b29-145">For example:</span></span>
    
   ```
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    <span data-ttu-id="08b29-146">Dans cet exemple, l’utilisateur portant le nom d’affichage Bob Kelly reçoit le plan de numérotation de l’utilisateur portant le nom **DialPlanJapan**.</span><span class="sxs-lookup"><span data-stu-id="08b29-146">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>
    


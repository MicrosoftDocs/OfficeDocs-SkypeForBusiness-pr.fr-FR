---
title: Activation des utilisateurs pour Voix Entreprise dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Résumé : Apprenez à permettre aux utilisateurs d’effectuer et de recevoir des appels à l’aide de Voix Entreprise dans Skype pour Business Server 2015.'
ms.openlocfilehash: d187723b347121400bfbce00d238851f2d0651a9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server-2015"></a><span data-ttu-id="7de83-103">Activation des utilisateurs pour Voix Entreprise dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="7de83-103">Enable users for Enterprise Voice in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7de83-104">**Résumé :** Découvrez comment permettre aux utilisateurs d’effectuer et de recevoir des appels à l’aide de Voix Entreprise dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7de83-104">**Summary:** Learn how to enable users to make and receive calls by using Enterprise Voice in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7de83-105">Après le déploiement de Voix Entreprise ou l’appeler Via le travail, vous pouvez utiliser les procédures suivantes pour activer un utilisateur effectuer des appels à l’aide de Voix Entreprise :</span><span class="sxs-lookup"><span data-stu-id="7de83-105">After you deploy Enterprise Voice or Call Via Work, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>
  
> [!NOTE]
> <span data-ttu-id="7de83-106">Des procédures suivantes, seule la première peut être effectuée à l’aide de Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="7de83-106">Of the following procedures, only the first can be performed by using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="7de83-107">Pour les autres procédures, vous pouvez utiliser Skype uniquement pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7de83-107">For the remaining procedures, you can use only Skype for Business Server Management Shell.</span></span> 
  
- <span data-ttu-id="7de83-108">Activer le compte d’utilisateur pour les Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="7de83-108">Enable the user account for Enterprise Voice.</span></span>
    
- <span data-ttu-id="7de83-109">(Facultatif) Affectez au compte d’utilisateur une stratégie de voix spécifique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7de83-109">(Optional) Assign the user account a user-specific voice policy.</span></span>
    
- <span data-ttu-id="7de83-110">(Facultatif) Affectez au compte d’utilisateur un plan de numérotation spécifique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7de83-110">(Optional) Assign the user account a user-specific dial plan.</span></span>
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="7de83-111">Pour activer un compte d’utilisateur de Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="7de83-111">To enable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="7de83-112">Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="7de83-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="7de83-113">Ouvrez Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="7de83-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="7de83-114">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="7de83-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="7de83-115">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur à activer, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="7de83-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="7de83-116">Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez activer pour les Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="7de83-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="7de83-117">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="7de83-117">On the **Edit** menu, click **Show details**.</span></span>
    
7. <span data-ttu-id="7de83-118">Dans la page **Modifier les Skype pour l’utilisateur de serveur d’entreprise** , **téléphonie**, cliquez sur **Voix Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="7de83-118">On the **Edit Skype for Business Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="7de83-119">Cliquez sur **URI de ligne**, puis tapez un numéro de téléphone normalisé unique (par exemple, tél :+14255550200).</span><span class="sxs-lookup"><span data-stu-id="7de83-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
9. <span data-ttu-id="7de83-120">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="7de83-120">Click **Commit**.</span></span>
    
<span data-ttu-id="7de83-121">Pour terminer l’activation d’un utilisateur de Voix Entreprise, assurez-vous que l’utilisateur reçoit une stratégie voice et un plan de numérotation, si global (affectée par défaut) ou spécifiques à l’utilisateur. Par défaut, tous les utilisateurs sont affectés à une stratégie voice global et plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="7de83-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="7de83-122">S’il existe une stratégie de voix ou un plan de numérotation au niveau du site sur lequel un compte d’utilisateur est hébergé, cette stratégie de site s’applique automatiquement à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7de83-122">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="7de83-123">Pour appliquer une stratégie de voix par utilisateur ou numérotation de plan à un utilisateur, vous devez exécuter les applets de commande **Grant-CsVoicePolicy** et **CsDialPlan de la subvention** .</span><span class="sxs-lookup"><span data-stu-id="7de83-123">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="7de83-124">Pour plus d’informations, reportez-vous aux procédures suivantes de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="7de83-124">For details, see the following procedures in this topic.</span></span>
## <a name="voice-policy-assignment"></a><span data-ttu-id="7de83-125">Affectation d’une stratégie de voix</span><span class="sxs-lookup"><span data-stu-id="7de83-125">Voice Policy Assignment</span></span>

<span data-ttu-id="7de83-126">Stratégies voice global et au niveau du site sont automatiquement affectés à tous les comptes d’utilisateurs qui sont activés pour les Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="7de83-126">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="7de83-127">Vous pouvez également créer des stratégies de voix qui s’appliquent à des utilisateurs ou à des groupes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="7de83-127">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="7de83-128">Ces stratégies utilisateur doivent être affectées explicitement à des utilisateurs ou à des groupes.</span><span class="sxs-lookup"><span data-stu-id="7de83-128">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="7de83-129">Si vous souhaitez utiliser le global ou site stratégie voice pour tous les utilisateurs qui sont activés pour les Voix Entreprise, vous pouvez ignorer cette section et passez à la section [Affectation de Plan d’accès](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="7de83-129">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to [Dial Plan Assignment](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) section later in this topic.</span></span>
  
### <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="7de83-130">Pour affecter une stratégie de voix spécifique à l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="7de83-130">To assign a user-specific voice policy</span></span>

1. <span data-ttu-id="7de83-131">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="7de83-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="7de83-132">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="7de83-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="7de83-133">Pour affecter une stratégie de voix utilisateur existante à un utilisateur, exécutez la commande suivante dans l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="7de83-133">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
   ```
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="7de83-134">Exemple :</span><span class="sxs-lookup"><span data-stu-id="7de83-134">For example:</span></span>
    
   ```
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    <span data-ttu-id="7de83-135">Dans cet exemple, la stratégie voice avec le nom **VoicePolicyJapan**est attribuée à l’utilisateur avec le nom d’affichage Bob Kelly.</span><span class="sxs-lookup"><span data-stu-id="7de83-135">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>
    
## <a name="dial-plan-assignment"></a><span data-ttu-id="7de83-136">Affectation d’un plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="7de83-136">Dial Plan Assignment</span></span>
<span data-ttu-id="7de83-137"><a name="BKMK_DialPlanAssignment"> </a></span><span class="sxs-lookup"><span data-stu-id="7de83-137"></span></span>

<span data-ttu-id="7de83-138">Pour terminer la configuration de compte d’utilisateur pour les utilisateurs de Voix Entreprise ou utilisateurs de conférence à distance, l’utilisateur doit être affecté à un plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="7de83-138">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="7de83-139">Les comptes d’utilisateurs utilisent automatiquement le plan de numérotation global ou, le cas échéant, le plan de numérotation au niveau du site si vous n’affectez pas explicitement un plan de numérotation utilisateur existant.</span><span class="sxs-lookup"><span data-stu-id="7de83-139">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="7de83-140">Si vous souhaitez utiliser le global ou site de plan de numérotation pour tous les utilisateurs qui sont activés pour les Voix Entreprise, vous pouvez ignorer cette section.</span><span class="sxs-lookup"><span data-stu-id="7de83-140">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>
  
### <a name="to-assign-a-user-specific-dial-plan"></a><span data-ttu-id="7de83-141">Affectation d’un plan de numérotation propre à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="7de83-141">To assign a user-specific dial plan</span></span>

1. <span data-ttu-id="7de83-142">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="7de83-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="7de83-143">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="7de83-143">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="7de83-144">Pour affecter un plan de numérotation spécifique à un utilisateur, exécutez la commande suivante dans l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="7de83-144">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
   ```
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="7de83-145">Exemple :</span><span class="sxs-lookup"><span data-stu-id="7de83-145">For example:</span></span>
    
   ```
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    <span data-ttu-id="7de83-146">Dans cet exemple, l’utilisateur avec le nom d’affichage Bob Kelly reçoit le plan de numérotation utilisateur avec le nom **DialPlanJapan**.</span><span class="sxs-lookup"><span data-stu-id="7de83-146">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>
    


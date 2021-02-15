---
title: Activer les utilisateurs Voix Entreprise dans Skype Entreprise Server
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
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Résumé : Découvrez comment permettre aux utilisateurs de prendre et de recevoir des appels à l’aide de Voix Entreprise dans Skype Entreprise Server.'
ms.openlocfilehash: 3c18836f1c2b03d2c6d50712f33d9e3a900b43b3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830874"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="3a8bc-103">Activer les utilisateurs Voix Entreprise dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="3a8bc-103">Enable users for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="3a8bc-104">**Résumé :** Découvrez comment permettre aux utilisateurs de prendre et de recevoir des appels à l’aide de Voix Entreprise dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-104">**Summary:** Learn how to enable users to make and receive calls by using Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="3a8bc-105">Après avoir déployé Voix Entreprise ou appel via le travail, vous pouvez utiliser les procédures suivantes pour permettre à un utilisateur d’effectuer des appels à l’aide Voix Entreprise :</span><span class="sxs-lookup"><span data-stu-id="3a8bc-105">After you deploy Enterprise Voice or Call Via Work, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>
  
> [!NOTE]
> <span data-ttu-id="3a8bc-106">Des procédures suivantes, seule la première peut être effectuée à l’aide du Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-106">Of the following procedures, only the first can be performed by using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="3a8bc-107">Pour les autres procédures, vous pouvez utiliser uniquement Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-107">For the remaining procedures, you can use only Skype for Business Server Management Shell.</span></span> 
  
- <span data-ttu-id="3a8bc-108">Activez le compte d’utilisateur pour Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-108">Enable the user account for Enterprise Voice.</span></span>
    
- <span data-ttu-id="3a8bc-109">(Facultatif) Attribuez au compte d’utilisateur une stratégie de voix spécifique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-109">(Optional) Assign the user account a user-specific voice policy.</span></span>
    
- <span data-ttu-id="3a8bc-110">(Facultatif) Attribuez au compte d’utilisateur un plan de numérotation spécifique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-110">(Optional) Assign the user account a user-specific dial plan.</span></span>
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="3a8bc-111">Pour activer un compte d’utilisateur pour Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="3a8bc-111">To enable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="3a8bc-112">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins, ou en tant que membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="3a8bc-113">Ouvrez le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="3a8bc-114">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3a8bc-115">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="3a8bc-116">Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez activer pour Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="3a8bc-117">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-117">On the **Edit** menu, click **Show details**.</span></span>
    
7. <span data-ttu-id="3a8bc-118">Dans la page **Modifier l’utilisateur Skype** Entreprise Server, sous **Téléphonie,** cliquez **sur Voix Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-118">On the **Edit Skype for Business Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="3a8bc-119">Cliquez **sur URI** de ligne, puis tapez un numéro de téléphone unique et normal (par exemple, tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="3a8bc-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
9. <span data-ttu-id="3a8bc-120">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-120">Click **Commit**.</span></span>
    
<span data-ttu-id="3a8bc-121">Pour terminer l’activation d’un utilisateur pour Voix Entreprise, assurez-vous qu’une stratégie de voix et un plan de numérotation lui sont affectés, qu’il soit global (affecté par défaut) ou spécifique à l’utilisateur. Par défaut, une stratégie de voix globale et un plan de numérotation sont attribués à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="3a8bc-122">Si une stratégie de voix ou un plan de numérotation existe au niveau du site sur lequel le compte d’utilisateur est homed, ces stratégies de site s’appliquent automatiquement à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-122">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="3a8bc-123">Pour appliquer une stratégie de voix ou un plan de numérotation par utilisateur à un utilisateur, vous devez exécuter les cmdlets **Grant-CsVoicePolicy** et **Grant-CsDialPlan.**</span><span class="sxs-lookup"><span data-stu-id="3a8bc-123">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="3a8bc-124">Pour plus d’informations, voir les procédures suivantes dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-124">For details, see the following procedures in this topic.</span></span>
## <a name="voice-policy-assignment"></a><span data-ttu-id="3a8bc-125">Attribution de stratégie de voix</span><span class="sxs-lookup"><span data-stu-id="3a8bc-125">Voice Policy Assignment</span></span>

<span data-ttu-id="3a8bc-126">Les stratégies de voix au niveau global et au niveau du site sont automatiquement affectées à tous les comptes d’utilisateur activés pour Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-126">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="3a8bc-127">Vous pouvez également créer des stratégies de voix qui s’appliquent à des utilisateurs ou des groupes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-127">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="3a8bc-128">Ces stratégies utilisateur doivent être explicitement attribuées aux utilisateurs ou groupes.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-128">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="3a8bc-129">Si vous souhaitez utiliser la stratégie de voix globale ou de site pour tous les utilisateurs activés pour Voix Entreprise, vous pouvez ignorer cette section et passer à la section Affectation du [plan](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) de numérotation plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-129">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to [Dial Plan Assignment](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) section later in this topic.</span></span>
  
### <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="3a8bc-130">Pour affecter une stratégie de voix spécifique à l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="3a8bc-130">To assign a user-specific voice policy</span></span>

1. <span data-ttu-id="3a8bc-131">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3a8bc-132">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="3a8bc-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="3a8bc-133">Pour assigner une stratégie de voix utilisateur existante à un utilisateur, exécutez la commande suivante à l’invite :</span><span class="sxs-lookup"><span data-stu-id="3a8bc-133">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
   ```powershell
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="3a8bc-134">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="3a8bc-134">For example:</span></span>
    
   ```powershell
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    <span data-ttu-id="3a8bc-135">Dans cet exemple, la stratégie de voix **VoicePolicyJapan** est attribuée à l’utilisateur dont le nom complet est Bob Kelly.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-135">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>
    
## <a name="dial-plan-assignment"></a><span data-ttu-id="3a8bc-136">Affectation de plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="3a8bc-136">Dial Plan Assignment</span></span>
<span data-ttu-id="3a8bc-137"><a name="BKMK_DialPlanAssignment"> </a></span><span class="sxs-lookup"><span data-stu-id="3a8bc-137"><a name="BKMK_DialPlanAssignment"> </a></span></span>

<span data-ttu-id="3a8bc-138">Pour terminer la configuration des comptes d’utilisateurs des utilisateurs de Voix Entreprise ou de conférence rendez-vous, il convient de leur assigner un plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-138">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="3a8bc-139">Les comptes d’utilisateurs utilisent automatiquement le plan de numérotation global ou, le cas présent, le plan de numérotation au niveau du site, lorsque vous n’affectez pas explicitement un plan de numérotation utilisateur existant.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-139">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="3a8bc-140">Si vous souhaitez utiliser le plan de numérotation global ou de site pour tous les utilisateurs activés pour Voix Entreprise, vous pouvez ignorer cette section.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-140">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>
  
### <a name="to-assign-a-user-specific-dial-plan"></a><span data-ttu-id="3a8bc-141">Pour affecter un plan de numérotation spécifique à l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="3a8bc-141">To assign a user-specific dial plan</span></span>

1. <span data-ttu-id="3a8bc-142">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3a8bc-143">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="3a8bc-143">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="3a8bc-144">Pour assigner un plan de numérotation spécifique à un utilisateur, exécutez la commande suivante à l’invite :</span><span class="sxs-lookup"><span data-stu-id="3a8bc-144">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
   ```powershell
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="3a8bc-145">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="3a8bc-145">For example:</span></span>
    
   ```powershell
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    <span data-ttu-id="3a8bc-146">Dans cet exemple, l’utilisateur avec le nom complet Bob Kelly se voit attribuer le plan de numérotation utilisateur nommé **DialPlanJapan**.</span><span class="sxs-lookup"><span data-stu-id="3a8bc-146">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>
    


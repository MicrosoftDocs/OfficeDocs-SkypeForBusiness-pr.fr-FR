---
title: 'Lync Server 2013 : activation des utilisateurs pour voix entreprise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d03f47cbe637e2c6fe6a0466b73a3588b842d6e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501041"
---
# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="4f224-102">Activer les utilisateurs pour voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f224-102">Enable users for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f224-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4f224-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4f224-104">Après avoir installé les fichiers d’un ou de plusieurs serveurs de médiation, configuré le routage des appels sortants et éventuellement déployé une ou plusieurs fonctionnalités voix entreprise avancées, vous pouvez utiliser les procédures suivantes pour permettre à un utilisateur d’effectuer des appels à l’aide de voix entreprise :</span><span class="sxs-lookup"><span data-stu-id="4f224-104">After you install files for one or more Mediation Servers, configure outbound call routing, and optionally deploy one or more advanced Enterprise Voice features, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4f224-105">Des procédures suivantes, seule la première peut être effectuée à l’aide du panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4f224-105">Of the following procedures, only the first can be performed by using Lync Server Control Panel.</span></span> <span data-ttu-id="4f224-106">Pour les autres procédures, vous pouvez utiliser uniquement Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="4f224-106">For the remaining procedures, you can use only Lync Server Management Shell.</span></span>



</div>

  - <span data-ttu-id="4f224-107">Activez le compte d’utilisateur pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="4f224-107">Enable the user account for Enterprise Voice.</span></span>

  - <span data-ttu-id="4f224-108">Module Affectez au compte d’utilisateur une stratégie de voix spécifique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4f224-108">(Optional) Assign the user account a user-specific voice policy.</span></span>

  - <span data-ttu-id="4f224-109">Module Affectez au compte d’utilisateur un plan de numérotation spécifique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4f224-109">(Optional) Assign the user account a user-specific dial plan.</span></span>

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="4f224-110">Pour activer un compte d’utilisateur pour voix entreprise</span><span class="sxs-lookup"><span data-stu-id="4f224-110">To enable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="4f224-111">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="4f224-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4f224-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4f224-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4f224-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4f224-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4f224-114">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="4f224-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="4f224-115">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="4f224-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="4f224-116">Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez activer pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="4f224-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="4f224-117">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="4f224-117">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="4f224-118">Dans la page **Modifier l’utilisateur Lync Server**, sous **Téléphonie**, cliquez sur **Voix Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="4f224-118">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="4f224-119">Cliquez sur **URI de ligne**, puis tapez un numéro de téléphone normalisé unique (par exemple, Tél : + 14255550200).</span><span class="sxs-lookup"><span data-stu-id="4f224-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>

9.  <span data-ttu-id="4f224-120">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="4f224-120">Click **Commit**.</span></span>

<span data-ttu-id="4f224-121">Pour terminer l’activation d’un utilisateur pour voix entreprise, assurez-vous que l’utilisateur se voit attribuer une stratégie de voix et un plan de numérotation, qu’il soit global (attribué par défaut) ou spécifique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4f224-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.</span></span>

<span data-ttu-id="4f224-122">Par défaut, tous les utilisateurs se voient attribuer une stratégie de voix globale et un plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="4f224-122">By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="4f224-123">S’il existe une stratégie de voix ou un plan de numérotation au niveau du site pour le site sur lequel le compte d’utilisateur est hébergé, ces stratégies de site s’appliquent automatiquement à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4f224-123">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="4f224-124">Pour appliquer une stratégie vocale ou un plan de numérotation par utilisateur à un utilisateur, vous devez exécuter les applets de commande **Grant-CsVoicePolicy** et **Grant-CsDialPlan** .</span><span class="sxs-lookup"><span data-stu-id="4f224-124">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="4f224-125">Pour plus d’informations, reportez-vous à la documentation de [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="4f224-125">For details, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="voice-policy-assignment"></a><span data-ttu-id="4f224-126">Affectation de stratégie de voix</span><span class="sxs-lookup"><span data-stu-id="4f224-126">Voice Policy Assignment</span></span>

<span data-ttu-id="4f224-127">Les stratégies de voix globale et de niveau site sont automatiquement affectées à tous les comptes d’utilisateur qui sont activés pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="4f224-127">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="4f224-128">Vous pouvez également créer des stratégies de voix qui s’appliquent à des utilisateurs ou à des groupes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="4f224-128">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="4f224-129">Ces stratégies par utilisateur doivent être explicitement attribuées aux utilisateurs ou aux groupes.</span><span class="sxs-lookup"><span data-stu-id="4f224-129">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="4f224-130">Si vous souhaitez utiliser la stratégie globale ou de voix de site pour tous les utilisateurs activés pour voix entreprise, vous pouvez ignorer cette section et continuer à composer le plan de numérotation plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="4f224-130">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to Dial Plan Assignment section later in this topic.</span></span>

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="4f224-131">Pour affecter une stratégie de voix spécifique à l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="4f224-131">To assign a user-specific voice policy</span></span>

1.  <span data-ttu-id="4f224-132">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="4f224-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4f224-133">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4f224-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4f224-134">Pour assigner une stratégie de voix utilisateur existante à un utilisateur, exécutez la commande suivante à l’invite :</span><span class="sxs-lookup"><span data-stu-id="4f224-134">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="4f224-135">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4f224-135">For example:</span></span>
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    <span data-ttu-id="4f224-136">Dans cet exemple, l’utilisateur dont le nom d’affichage est Bob Kelly est affecté à la stratégie de voix portant le nom **VoicePolicyJapan**.</span><span class="sxs-lookup"><span data-stu-id="4f224-136">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>

<span data-ttu-id="4f224-137">Pour plus d’informations sur l’attribution d’une stratégie de voix spécifique à l’utilisateur ou sur l’exécution de la cmdlet **Grant-CsVoicePolicy** , voir la documentation de [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="4f224-137">For details about assigning a user-specific voice policy or about running the **Grant-CsVoicePolicy** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a><span data-ttu-id="4f224-138">Affectation de plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="4f224-138">Dial Plan Assignment</span></span>

<span data-ttu-id="4f224-139">Pour terminer la configuration des comptes d’utilisateurs des utilisateurs de Voix Entreprise ou de conférence rendez-vous, il convient de leur assigner un plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="4f224-139">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="4f224-140">Les comptes d’utilisateur utiliseront automatiquement le plan de numérotation global ou, s’il en existe un, le plan de numérotation au niveau du site, lorsque vous n’assignez pas explicitement un plan de numérotation par utilisateur existant.</span><span class="sxs-lookup"><span data-stu-id="4f224-140">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="4f224-141">Si vous souhaitez utiliser le plan de numérotation de site ou global pour tous les utilisateurs activés pour voix entreprise, vous pouvez ignorer cette section.</span><span class="sxs-lookup"><span data-stu-id="4f224-141">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>

<div>

## <a name="to-assign-a-dial-plan"></a><span data-ttu-id="4f224-142">Pour affecter un plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="4f224-142">To assign a dial plan</span></span>

1.  <span data-ttu-id="4f224-143">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="4f224-143">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4f224-144">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4f224-144">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4f224-145">Pour assigner un plan de numérotation spécifique à un utilisateur, exécutez la commande suivante à l’invite :</span><span class="sxs-lookup"><span data-stu-id="4f224-145">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="4f224-146">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4f224-146">For example:</span></span>
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    <span data-ttu-id="4f224-147">Dans cet exemple, l’utilisateur dont le nom d’affichage est Bob Kelly est affecté au plan de numérotation de l’utilisateur portant le nom **DialPlanJapan**.</span><span class="sxs-lookup"><span data-stu-id="4f224-147">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>

<span data-ttu-id="4f224-148">Pour plus d’informations sur l’affectation d’un plan de numérotation utilisateur ou sur l’exécution de la cmdlet **Grant-CsDialPlan** , voir la documentation de [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="4f224-148">For details about assigning a user dial plan or about running the **Grant-CsDialPlan** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4f224-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4f224-149">See Also</span></span>


[<span data-ttu-id="4f224-150">Désactivation d’un utilisateur pour voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f224-150">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


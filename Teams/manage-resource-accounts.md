---
title: Gérer les comptes de ressource dans Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: Dans cet article, vous allez découvrir comment créer, modifier et gérer des comptes de ressources dans Microsoft Teams.
ms.openlocfilehash: 21824c360e26e568ae47a9729960fca01a100ae8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094244"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="719c3-103">Gérer les comptes de ressources dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="719c3-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="719c3-104">Un compte de ressource est un objet utilisateur désactivé dans Azure AD et peut être utilisé pour représenter des ressources en général.</span><span class="sxs-lookup"><span data-stu-id="719c3-104">A resource account is a disabled user object in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="719c3-105">Par exemple, un compte de ressource peut être utilisé dans Exchange pour représenter les salles de conférence et leur permettre d’avoir un numéro de téléphone et un calendrier.</span><span class="sxs-lookup"><span data-stu-id="719c3-105">For example, a resource account may be used in Exchange to represent conference rooms and allow them to have a phone number and calendar.</span></span> <span data-ttu-id="719c3-106">Un compte de ressource peut être homed in Microsoft 365 ou sur site à l’aide Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="719c3-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="719c3-107">Dans Microsoft Teams, un compte de ressource est requis pour chaque employé de la file d’attente d’appels ou de service automatique.</span><span class="sxs-lookup"><span data-stu-id="719c3-107">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="719c3-108">Des numéros de téléphone de service peuvent également être attribués aux comptes de ressources.</span><span class="sxs-lookup"><span data-stu-id="719c3-108">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="719c3-109">Il s’agit de la façon dont vous affectez des numéros de téléphone aux serveurs de service automatiques et aux files d’attente d’appels, ce qui permet aux appelants de l’extérieur Teams d’accéder au attendant automatique ou à la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="719c3-109">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

<span data-ttu-id="719c3-110">Cet article explique comment créer des comptes de ressources et les préparer pour une utilisation avec des files d’attente et des files d’attente automatiques.</span><span class="sxs-lookup"><span data-stu-id="719c3-110">This article covers how to create resource accounts and ready them for use with auto attendants and call queues.</span></span>

<span data-ttu-id="719c3-111">Avant de commencer les procédures de cet article, assurez-vous d’avoir effectué les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="719c3-111">Before you start the procedures in this article, ensure you've done the following:</span></span>

- [<span data-ttu-id="719c3-112">Obtenir des licences utilisateur virtuel</span><span class="sxs-lookup"><span data-stu-id="719c3-112">Obtain virtual user licenses</span></span>](#obtain-virtual-user-licenses)
- [<span data-ttu-id="719c3-113">Obtenir des numéros de service</span><span class="sxs-lookup"><span data-stu-id="719c3-113">Obtain service numbers</span></span>](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="719c3-114">Obtenir des licences utilisateur virtuel</span><span class="sxs-lookup"><span data-stu-id="719c3-114">Obtain virtual user licenses</span></span>

<span data-ttu-id="719c3-115">Chaque compte de ressource nécessite une licence pour l’utilisation des files d’attente et des files d’attente automatiques.</span><span class="sxs-lookup"><span data-stu-id="719c3-115">Each resource account requires a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="719c3-116">Vous pouvez utiliser une licence *utilisateur Microsoft 365 Système téléphonique virtuel.*</span><span class="sxs-lookup"><span data-stu-id="719c3-116">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span> <span data-ttu-id="719c3-117">Pour obtenir ces licences, consultez [la licence Utilisateur virtuel.](teams-add-on-licensing/virtual-user.md)</span><span class="sxs-lookup"><span data-stu-id="719c3-117">To obtain these licenses, see [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="719c3-118">Nous vous expliquerons comment attribuer la licence à un compte de ressource plus loin dans cet article.</span><span class="sxs-lookup"><span data-stu-id="719c3-118">We cover how to assign the license to a resource account later in this article.</span></span>

<span data-ttu-id="719c3-119">Pour obtenir la licence Utilisateur virtuel, dans le Centre d’administration Microsoft 365,  >    >  **rendez-vous** sur abonnements  au module ajout de services d’achat de facturation et faites défiler jusqu’à la fin - la licence utilisateur virtuel Système téléphonique s’affiche.</span><span class="sxs-lookup"><span data-stu-id="719c3-119">To get the Virtual User license, in the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see *Phone System - Virtual User* license.</span></span> <span data-ttu-id="719c3-120">Sélectionnez **Acheter maintenant.**</span><span class="sxs-lookup"><span data-stu-id="719c3-120">Select **Buy now**.</span></span> <span data-ttu-id="719c3-121">Il n’y a pas de coût nul, mais vous devez tout de même suivre ces étapes pour acquérir la licence.</span><span class="sxs-lookup"><span data-stu-id="719c3-121">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>

### <a name="obtain-service-numbers"></a><span data-ttu-id="719c3-122">Obtenir des numéros de service</span><span class="sxs-lookup"><span data-stu-id="719c3-122">Obtain service numbers</span></span>

<span data-ttu-id="719c3-123">Les numéros de service sont facultatifs pour les serveurs automatiques et les files d’attente. Toutefois, vous aurez besoin d’au moins un numéro de service pour que les appelants atteignent votre fournisseur automatique et la configuration de la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="719c3-123">Service numbers are optional for auto attendants and call queues, however you will need at least one service number in order for callers to reach your auto attendant and call queue configuration.</span></span> <span data-ttu-id="719c3-124">Pour un service automatique ou une file d’attente d’appels que vous souhaitez joindre directement à un numéro de service, vous devez avoir un compte de ressource associé à un numéro de service.</span><span class="sxs-lookup"><span data-stu-id="719c3-124">For any auto attendant or call queue that you want to be reachable directly by a service number, you must have a resource account with an associated service number.</span></span>

<span data-ttu-id="719c3-125">Les comptes de ressources peuvent utiliser des numéros de service gratuits ou gratuits.</span><span class="sxs-lookup"><span data-stu-id="719c3-125">Resource accounts can use either toll or toll-free service numbers.</span></span> <span data-ttu-id="719c3-126">Vous pouvez demander de nouveaux numéros ou des numéros existants à un autre opérateur.</span><span class="sxs-lookup"><span data-stu-id="719c3-126">You can request new numbers or port existing numbers from another carrier.</span></span>

<span data-ttu-id="719c3-127">Pour obtenir de nouveaux numéros de service, [consultez Obtenir des numéros de téléphone de service.](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="719c3-127">To get new service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="719c3-128">Pour transférer un numéro d’un autre opérateur, [consultez transférer les numéros de téléphone vers Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="719c3-128">To port a number from another carrier, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="719c3-129">Créer un compte de ressource</span><span class="sxs-lookup"><span data-stu-id="719c3-129">Create a resource account</span></span>

<span data-ttu-id="719c3-130">Vous pouvez créer un compte de ressource dans le Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="719c3-130">You can create a resource account in the Teams admin center.</span></span>

![Capture d’écran de l’interface utilisateur Ajouter un compte de ressource](media/resource-account-add.png)

1. <span data-ttu-id="719c3-132">Dans le Teams d’administration, développez les **paramètres** à l’échelle de l’organisation, puis cliquez **sur Comptes de ressources.**</span><span class="sxs-lookup"><span data-stu-id="719c3-132">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="719c3-133">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="719c3-133">Click **Add**.</span></span>

3. <span data-ttu-id="719c3-134">Dans le **volet Ajouter un compte de** ressource, tapez Nom **d’affichage,** Nom d’utilisateur et Type de compte de  **ressource.**</span><span class="sxs-lookup"><span data-stu-id="719c3-134">In the **Add resource account** pane, fill out **Display name**, **Username**, and the **Resource account type**.</span></span> <span data-ttu-id="719c3-135">Le type de compte de ressource peut être le **attendant automatique** ou la file d’attente d’appels, selon l’utilisation que vous comptez en faire. </span><span class="sxs-lookup"><span data-stu-id="719c3-135">The resource account type can be either **Auto attendant** or **Call queue**, depending how you intend to use this resource account.</span></span>

4. <span data-ttu-id="719c3-136">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="719c3-136">Click **Save**.</span></span>

![Capture d’écran d’une liste des comptes de ressources](media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="719c3-138">Attribuer une licence</span><span class="sxs-lookup"><span data-stu-id="719c3-138">Assign a license</span></span>

<span data-ttu-id="719c3-139">Pour chaque compte de ressource, vous devez attribuer une *Microsoft 365 Système téléphonique utilisateur* virtuel ou une *Système téléphonique* utilisateur virtuel.</span><span class="sxs-lookup"><span data-stu-id="719c3-139">For each resource account, you must assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Capture d’écran de l’interface utilisateur d’attribution de licences dans Microsoft 365 centre d’administration](media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="719c3-141">Dans le Microsoft 365 d’administration, cliquez sur le compte de ressource auquel vous voulez attribuer une licence.</span><span class="sxs-lookup"><span data-stu-id="719c3-141">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="719c3-142">Sous **l’onglet Licences et** applications, sous **Licences,** sélectionnez **Microsoft 365 Système téléphonique - Utilisateur virtuel.**</span><span class="sxs-lookup"><span data-stu-id="719c3-142">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="719c3-143">Cliquez **sur Enregistrer les modifications.**</span><span class="sxs-lookup"><span data-stu-id="719c3-143">Click **Save changes**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="719c3-144">Affecter un numéro de service</span><span class="sxs-lookup"><span data-stu-id="719c3-144">Assign a service number</span></span>

<span data-ttu-id="719c3-145">Si vous envisagez d’utiliser le compte de ressource avec un fournisseur de services automatique ou une file d’attente d’appels nécessitant un numéro de service, attribuez un numéro au compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="719c3-145">If you're planning to use the resource account with an auto attendant or call queue that requires a service number, assign a number to the resource account.</span></span>

![Capture d’écran de l’interface utilisateur affecter un numéro de service](media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="719c3-147">Dans le Teams d’administration, dans la **page** Comptes de ressources, sélectionnez le compte de ressource auquel vous voulez affecter un numéro de service, puis cliquez sur **Affecter/Désaffecter.**</span><span class="sxs-lookup"><span data-stu-id="719c3-147">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="719c3-148">Dans la **Téléphone du type de** nombre, choisissez le type de nombre à utiliser.</span><span class="sxs-lookup"><span data-stu-id="719c3-148">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="719c3-149">Dans la **zone Numéro de téléphone** affecté, recherchez le numéro à utiliser, puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="719c3-149">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

4. <span data-ttu-id="719c3-150">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="719c3-150">Click **Save**.</span></span>


<span data-ttu-id="719c3-151">Pour affecter un routage direct ou un numéro hybride à un compte de ressource, vous devez utiliser PowerShell :</span><span class="sxs-lookup"><span data-stu-id="719c3-151">To assign a direct routing or hybrid number to a resource account you need to use PowerShell:</span></span>

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a><span data-ttu-id="719c3-152">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="719c3-152">Next steps</span></span>

<span data-ttu-id="719c3-153">Une fois que vous avez terminé la configuration du compte de ressource et que vous avez attribué un numéro de service, si nécessaire, vous êtes prêt à utiliser le compte de ressource avec un responsable automatique ou une file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="719c3-153">Once you've completed the resource account setup and assigning a service number if needed, you're ready to use the resource account with an auto attendant or call queue.</span></span>

<span data-ttu-id="719c3-154">Consultez les références suivantes :</span><span class="sxs-lookup"><span data-stu-id="719c3-154">See the following references:</span></span>

 - [<span data-ttu-id="719c3-155">Attendant automatique cloud</span><span class="sxs-lookup"><span data-stu-id="719c3-155">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

 - [<span data-ttu-id="719c3-156">File d’attente d’appels cloud</span><span class="sxs-lookup"><span data-stu-id="719c3-156">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)

<span data-ttu-id="719c3-157">Vous pouvez modifier le nom d’affichage **du** compte de ressource et le type **de compte** de ressource à l’aide de **l’option** Modifier.</span><span class="sxs-lookup"><span data-stu-id="719c3-157">You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="719c3-158">Cliquez **sur Enregistrer** lorsque vous avez terminé.</span><span class="sxs-lookup"><span data-stu-id="719c3-158">Click **Save** when you are done.</span></span>

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="719c3-159">Modifier un compte de ressource existant pour utiliser une licence Utilisateur virtuel</span><span class="sxs-lookup"><span data-stu-id="719c3-159">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="719c3-160">Si vous décidez de basculer les licences de votre compte de ressource existant d’une licence **Système téléphonique** à une licence utilisateur virtuel, vous devez acquérir la licence utilisateur virtuel gratuite, puis suivre les étapes du Centre d’administration Microsoft 365 pour déplacer les utilisateurs vers un autre [abonnement.](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)</span><span class="sxs-lookup"><span data-stu-id="719c3-160">If you decide to switch the licenses on your existing resource account from a **Phone System** license to a Virtual User license, you'll need to acquire the free Virtual User license, and then follow the steps in the Microsoft 365 admin center to [Move users to a different subscription](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span></span>

> [!WARNING]
> <span data-ttu-id="719c3-161">Supprimez toujours une licence Système téléphonique licence utilisateur virtuel et attribuez-la dans la même activité de licence.</span><span class="sxs-lookup"><span data-stu-id="719c3-161">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="719c3-162">Si vous supprimez l’ancienne licence, enregistrez les modifications apportées au compte, ajoutez la nouvelle licence, puis enregistrez de nouveau les paramètres du compte, le compte de ressource peut ne plus fonctionner comme prévu.</span><span class="sxs-lookup"><span data-stu-id="719c3-162">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="719c3-163">Dans ce cas, nous vous recommandons de créer un compte de ressource pour la licence Utilisateur virtuel et de supprimer le compte de ressource rompu.</span><span class="sxs-lookup"><span data-stu-id="719c3-163">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span>

## <a name="skype-for-business-server-2019"></a><span data-ttu-id="719c3-164">Skype For Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="719c3-164">Skype For Business Server 2019</span></span>

<span data-ttu-id="719c3-165">Pour les comptes de ressources homed on Skype For Business Server 2019 qui peuvent être utilisés avec des files d’attente d’appels cloud et des serveurs automatiques cloud, voir [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants.](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)</span><span class="sxs-lookup"><span data-stu-id="719c3-165">For resource accounts homed on Skype For Business Server 2019 that can be used with cloud call queues and cloud auto attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="719c3-166">Les implémentations hybrides (numéros homed on Direct Routing) sont configurées à l’aide de l’cmdlet [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) sur un serveur Skype Entreprise Server 2019 local.</span><span class="sxs-lookup"><span data-stu-id="719c3-166">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="719c3-167">Les ID d’application que vous devez utiliser lors de la création des instances d’application sont :</span><span class="sxs-lookup"><span data-stu-id="719c3-167">The application IDs that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="719c3-168">**Standard automatique :** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="719c3-168">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="719c3-169">**File d’attente** d’appels : 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="719c3-169">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="719c3-170">Si vous souhaitez que les utilisateurs d’Skype Entreprise Server 2019 recherchent la file d’attente ou le serveur automatique d’appels, vous devez créer vos comptes de ressources sur Skype Entreprise Server 2019, car les comptes de ressources en ligne ne sont pas synchronisés avec Active Directory.</span><span class="sxs-lookup"><span data-stu-id="719c3-170">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="719c3-171">Lorsque les enregistrements SRV DNS pour sipfederationtls sont résolus jusqu’à Skype Entreprise Server 2019, les comptes de ressources doivent être **créés** sur Skype For Business Server 2019 à l’aide de L’shell de gestion SfB et synchronisés avec Azure AD.</span><span class="sxs-lookup"><span data-stu-id="719c3-171">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to Azure AD.</span></span>

<span data-ttu-id="719c3-172">Pour les implémentations hybrides avec Skype Entreprise Server :</span><span class="sxs-lookup"><span data-stu-id="719c3-172">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="719c3-173">Planifier les standards automatiques cloud</span><span class="sxs-lookup"><span data-stu-id="719c3-173">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="719c3-174">Planifier les files d’attente d’appels cloud</span><span class="sxs-lookup"><span data-stu-id="719c3-174">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="719c3-175">Configurer des comptes de ressources on-prem</span><span class="sxs-lookup"><span data-stu-id="719c3-175">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a><span data-ttu-id="719c3-176">Supprimer un compte de ressource</span><span class="sxs-lookup"><span data-stu-id="719c3-176">Delete a resource account</span></span>

<span data-ttu-id="719c3-177">Assurez-vous de dissocier le numéro de téléphone du compte de ressource avant de le supprimer, afin d’éviter que votre numéro de service reste bloqué en mode En attente.</span><span class="sxs-lookup"><span data-stu-id="719c3-177">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span>

<span data-ttu-id="719c3-178">Vous pouvez ensuite supprimer le compte de ressource dans le centre d Microsoft 365 d’administration, sous l’onglet Utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="719c3-178">After you do that, you can delete the resource account in the Microsoft 365 admin center, under the Users tab.</span></span>

<span data-ttu-id="719c3-179">Pour dissocier un numéro de téléphone de routage direct du compte de ressource, utilisez l’cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="719c3-179">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```
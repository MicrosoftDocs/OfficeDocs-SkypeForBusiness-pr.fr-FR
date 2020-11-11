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
ms.openlocfilehash: 7ccc7a26c83357d68147381101ef8a97184f03f4
ms.sourcegitcommit: 247b2587a60b1609947310ec82d51f47cf829703
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993496"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="12ed5-103">Gérer les comptes de ressources dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="12ed5-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="12ed5-104">Un compte de ressource est un objet utilisateur désactivé dans Azure AD et peut être utilisé pour représenter des ressources en général.</span><span class="sxs-lookup"><span data-stu-id="12ed5-104">A resource account is a disabled user object in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="12ed5-105">Par exemple, un compte de ressource peut être utilisé dans Exchange pour représenter des salles de conférence et leur permettre d’avoir un numéro de téléphone et un calendrier.</span><span class="sxs-lookup"><span data-stu-id="12ed5-105">For example, a resource account may be used in Exchange to represent conference rooms and allow them to have a phone number and calendar.</span></span> <span data-ttu-id="12ed5-106">Un compte de ressource peut être hébergé dans Microsoft 365 ou sur site à l’aide de Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="12ed5-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="12ed5-107">Dans Microsoft Teams, un compte de ressource est requis pour chaque standard automatique ou file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="12ed5-107">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="12ed5-108">Des numéros de téléphone de service pourront également être attribués aux comptes de ressources.</span><span class="sxs-lookup"><span data-stu-id="12ed5-108">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="12ed5-109">C’est ainsi que vous attribuez des numéros de téléphone aux standards automatiques et aux files d’attente d’appels permettant aux appelants d’équipes externes de joindre le standard automatique ou la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="12ed5-109">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

<span data-ttu-id="12ed5-110">Cet article décrit la création de comptes de ressources et leur disponibilité pour une utilisation avec des standards automatiques et des files d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="12ed5-110">This article covers how to create resource accounts and ready them for use with auto attendants and call queues.</span></span>

<span data-ttu-id="12ed5-111">Avant de commencer les procédures décrites dans cet article, assurez-vous que vous avez terminé les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="12ed5-111">Before you start the procedures in this article, ensure you've done the following:</span></span>

- [<span data-ttu-id="12ed5-112">Obtenir des licences utilisateur virtuelles</span><span class="sxs-lookup"><span data-stu-id="12ed5-112">Obtain virtual user licenses</span></span>](#obtain-virtual-user-licenses)
- [<span data-ttu-id="12ed5-113">Obtention des numéros de service</span><span class="sxs-lookup"><span data-stu-id="12ed5-113">Obtain service numbers</span></span>](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="12ed5-114">Obtenir des licences utilisateur virtuelles</span><span class="sxs-lookup"><span data-stu-id="12ed5-114">Obtain virtual user licenses</span></span>

<span data-ttu-id="12ed5-115">Pour pouvoir utiliser les standards automatiques et les files d’attente, les comptes de ressources doivent disposer d’une licence.</span><span class="sxs-lookup"><span data-stu-id="12ed5-115">Each resource account requires a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="12ed5-116">Vous pouvez utiliser un *système téléphonique Microsoft 365 gratuit-licence utilisateur virtuel* .</span><span class="sxs-lookup"><span data-stu-id="12ed5-116">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span> <span data-ttu-id="12ed5-117">Pour obtenir ces licences, voir [licence utilisateur virtuel](teams-add-on-licensing/virtual-user.md).</span><span class="sxs-lookup"><span data-stu-id="12ed5-117">To obtain these licenses, see [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="12ed5-118">Nous vous décrivons comment attribuer la licence à un compte de ressources plus loin dans cet article.</span><span class="sxs-lookup"><span data-stu-id="12ed5-118">We cover how to assign the license to a resource account later in this article.</span></span>

<span data-ttu-id="12ed5-119">Pour obtenir la licence de l’utilisateur virtuel, dans le centre d’administration 365 de **Billing** Microsoft, accédez à  >  la section abonnements au composant additionnel **services d’achat**  >  **de** facturation *Phone System - Virtual User* et faites défiler jusqu’à la fin.</span><span class="sxs-lookup"><span data-stu-id="12ed5-119">To get the Virtual User license, in the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see *Phone System - Virtual User* license.</span></span> <span data-ttu-id="12ed5-120">Sélectionnez **acheter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="12ed5-120">Select **Buy now**.</span></span> <span data-ttu-id="12ed5-121">Il y a un coût zéro, mais vous devez toujours suivre ces étapes pour acquérir la licence.</span><span class="sxs-lookup"><span data-stu-id="12ed5-121">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>

### <a name="obtain-service-numbers"></a><span data-ttu-id="12ed5-122">Obtention des numéros de service</span><span class="sxs-lookup"><span data-stu-id="12ed5-122">Obtain service numbers</span></span>

<span data-ttu-id="12ed5-123">Les numéros de service sont facultatifs pour les standards automatiques et les files d’attente d’appels, mais vous devez disposer d’au moins un numéro de service pour permettre aux appelants de joindre le standard automatique et la configuration de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="12ed5-123">Service numbers are optional for auto attendants and call queues, however you will need at least one service number in order for callers to reach your auto attendant and call queue configuration.</span></span> <span data-ttu-id="12ed5-124">Pour tout standard automatique ou file d’attente d’appels que vous souhaitez joindre directement par un numéro de service, vous devez disposer d’un compte de ressources avec un numéro de service associé.</span><span class="sxs-lookup"><span data-stu-id="12ed5-124">For any auto attendant or call queue that you want to be reachable directly by a service number, you must have a resource account with an associated service number.</span></span>

<span data-ttu-id="12ed5-125">Les comptes de ressources peuvent utiliser des numéros de service gratuits ou payants.</span><span class="sxs-lookup"><span data-stu-id="12ed5-125">Resource accounts can use either toll or toll-free service numbers.</span></span> <span data-ttu-id="12ed5-126">Vous pouvez demander de nouveaux numéros ou transférer des numéros existants à partir d’un autre opérateur.</span><span class="sxs-lookup"><span data-stu-id="12ed5-126">You can request new numbers or port existing numbers from another carrier.</span></span>

<span data-ttu-id="12ed5-127">Pour obtenir de nouveaux numéros de service, consultez la rubrique [obtention de numéros de téléphone de service](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="12ed5-127">To get new service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="12ed5-128">Pour porter un numéro à partir d’un autre opérateur, voir [transférer des numéros de téléphone vers teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="12ed5-128">To port a number from another carrier, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="12ed5-129">Créer un compte de ressources</span><span class="sxs-lookup"><span data-stu-id="12ed5-129">Create a resource account</span></span>

<span data-ttu-id="12ed5-130">Vous pouvez créer un compte de ressources dans le centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="12ed5-130">You can create a resource account in the Teams admin center.</span></span>

![Capture d’écran de l’interface utilisateur Ajouter un compte de ressources](media/resource-account-add.png)

1. <span data-ttu-id="12ed5-132">Dans le centre d’administration Teams, développez **paramètres à l’échelle** de l’organisation, puis cliquez sur **comptes de ressources**.</span><span class="sxs-lookup"><span data-stu-id="12ed5-132">In the Teams admin center, expand **Org-wide settings** , and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="12ed5-133">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="12ed5-133">Click **Add**.</span></span>

3. <span data-ttu-id="12ed5-134">Dans le **volet ajouter un compte de ressources** , spécifiez le nom d' **affichage** , le nom **d’utilisateur** et le **type de compte de ressource**.</span><span class="sxs-lookup"><span data-stu-id="12ed5-134">In the **Add resource account** pane, fill out **Display name** , **Username** , and the **Resource account type**.</span></span> <span data-ttu-id="12ed5-135">Le type de compte de ressource peut être de type **standard automatique** ou **file d’attente d’appels** , selon la manière dont vous envisagez d’utiliser ce compte de ressources.</span><span class="sxs-lookup"><span data-stu-id="12ed5-135">The resource account type can be either **Auto attendant** or **Call queue** , depending how you intend to use this resource account.</span></span>

4. <span data-ttu-id="12ed5-136">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="12ed5-136">Click **Save**.</span></span>

![Capture d’écran d’une liste de comptes de ressources](media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="12ed5-138">Attribuer une licence</span><span class="sxs-lookup"><span data-stu-id="12ed5-138">Assign a license</span></span>

<span data-ttu-id="12ed5-139">Pour chaque compte de ressource, vous devez attribuer un *système téléphonique Microsoft 365* ou une licence de *système téléphonique* .</span><span class="sxs-lookup"><span data-stu-id="12ed5-139">For each resource account, you must assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Capture d’écran de l’interface utilisateur affecter des licences dans le centre d’administration Microsoft 365](media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="12ed5-141">Dans le centre d’administration Microsoft 365, cliquez sur le compte de ressources auquel vous souhaitez attribuer une licence.</span><span class="sxs-lookup"><span data-stu-id="12ed5-141">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="12ed5-142">Dans l’onglet **licences et applications** , sous **licences** , sélectionnez **système téléphonique Microsoft 365-utilisateur virtuel**.</span><span class="sxs-lookup"><span data-stu-id="12ed5-142">On the **Licenses and Apps** tab, under **Licenses** , select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="12ed5-143">Cliquez sur **enregistrer les modifications**.</span><span class="sxs-lookup"><span data-stu-id="12ed5-143">Click **Save changes**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="12ed5-144">Affectation d’un numéro de service</span><span class="sxs-lookup"><span data-stu-id="12ed5-144">Assign a service number</span></span>

<span data-ttu-id="12ed5-145">Si vous envisagez d’utiliser le compte de ressources avec un standard automatique ou une file d’attente d’appels qui nécessite un numéro de service, attribuez un numéro au compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="12ed5-145">If you're planning to use the resource account with an auto attendant or call queue that requires a service number, assign a number to the resource account.</span></span>

![Capture d’écran de l’interface utilisateur affecter des numéros de service](media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="12ed5-147">Dans le centre d’administration Teams, dans la page **comptes de ressources** , sélectionnez le compte de ressources auquel vous souhaitez attribuer un numéro de service, puis cliquez sur **affecter/** retirer.</span><span class="sxs-lookup"><span data-stu-id="12ed5-147">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="12ed5-148">Dans la liste déroulante **type de numéro de téléphone** , choisissez le type de numéro que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="12ed5-148">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="12ed5-149">Dans la zone **numéro de téléphone attribué** , recherchez le numéro que vous voulez utiliser, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="12ed5-149">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

4. <span data-ttu-id="12ed5-150">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="12ed5-150">Click **Save**.</span></span>


<span data-ttu-id="12ed5-151">Pour affecter un routage direct ou un numéro hybride à un compte de ressources, vous devez utiliser PowerShell :</span><span class="sxs-lookup"><span data-stu-id="12ed5-151">To assign a direct routing or hybrid number to a resource account you need to use PowerShell:</span></span>

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a><span data-ttu-id="12ed5-152">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="12ed5-152">Next steps</span></span>

<span data-ttu-id="12ed5-153">Lorsque vous avez terminé la configuration du compte de ressources et que vous affectez un numéro de service le cas échéant, vous pouvez utiliser le compte de ressources avec un standard automatique ou une file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="12ed5-153">Once you've completed the resource account setup and assigning a service number if needed, you're ready to use the resource account with an auto attendant or call queue.</span></span>

<span data-ttu-id="12ed5-154">Voir les références suivantes :</span><span class="sxs-lookup"><span data-stu-id="12ed5-154">See the following references:</span></span>

 - [<span data-ttu-id="12ed5-155">Standard automatique Cloud</span><span class="sxs-lookup"><span data-stu-id="12ed5-155">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

 - [<span data-ttu-id="12ed5-156">File d’attente d’appels Cloud</span><span class="sxs-lookup"><span data-stu-id="12ed5-156">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)

<span data-ttu-id="12ed5-157">Vous pouvez modifier le nom d' **affichage** du compte de ressources et le type de **compte de ressources** en utilisant l’option **modifier** .</span><span class="sxs-lookup"><span data-stu-id="12ed5-157">You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="12ed5-158">Lorsque vous avez fin, cliquez sur **Enregistrer** .</span><span class="sxs-lookup"><span data-stu-id="12ed5-158">Click **Save** when you are done.</span></span>

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="12ed5-159">Modifier un compte de ressource existant pour utiliser une licence utilisateur virtuel</span><span class="sxs-lookup"><span data-stu-id="12ed5-159">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="12ed5-160">Si vous décidez de basculer entre les licences sur votre compte de ressources existant d’une licence de **système téléphonique** vers une licence utilisateur virtuel, vous devez acquérir la licence utilisateur virtuel gratuite, puis suivre les étapes du centre d’administration 365 Microsoft pour [déplacer des utilisateurs vers un autre abonnement](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span><span class="sxs-lookup"><span data-stu-id="12ed5-160">If you decide to switch the licenses on your existing resource account from a **Phone System** license to a Virtual User license, you'll need to acquire the free Virtual User license, and then follow the steps in the Microsoft 365 admin center to [Move users to a different subscription](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span></span>

> [!WARNING]
> <span data-ttu-id="12ed5-161">Supprimez toujours une licence de système téléphonique complet et attribuez-la à la licence utilisateur virtuel dans la même activité de licence.</span><span class="sxs-lookup"><span data-stu-id="12ed5-161">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="12ed5-162">Si vous supprimez l’ancienne licence, enregistrez les modifications du compte, ajoutez la nouvelle licence, puis enregistrez de nouveau les paramètres du compte, le compte de ressources risque de ne plus fonctionner comme prévu.</span><span class="sxs-lookup"><span data-stu-id="12ed5-162">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="12ed5-163">Si tel est le cas, nous vous recommandons de créer un compte de ressources pour la licence d’utilisateur virtuel et de supprimer le compte de ressource endommagé.</span><span class="sxs-lookup"><span data-stu-id="12ed5-163">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span>

## <a name="skype-for-business-server-2019"></a><span data-ttu-id="12ed5-164">Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="12ed5-164">Skype For Business Server 2019</span></span>

<span data-ttu-id="12ed5-165">Pour les comptes de ressources hébergés sur Skype entreprise Server 2019 qui peuvent être utilisés avec les files d’attente d’appels Cloud et les standards automatiques Cloud, voir [planifier des files d’attente d’appels Cloud](/SkypeforBusiness/hybrid/plan-call-queue) ou [planifier des standards automatiques Cloud](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span><span class="sxs-lookup"><span data-stu-id="12ed5-165">For resource accounts homed on Skype For Business Server 2019 that can be used with cloud call queues and cloud auto attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="12ed5-166">Les implémentations hybrides (numéros d’hébergement sur le routage direct) sont configurées à l’aide de l’applet de nouvelle applet de [CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) sur un serveur Skype entreprise Server 2019 local.</span><span class="sxs-lookup"><span data-stu-id="12ed5-166">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="12ed5-167">Les ID d’application que vous devez utiliser lors de la création des instances d’application sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="12ed5-167">The application IDs that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="12ed5-168">**Standard automatique :** ce933385-9390-45D1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="12ed5-168">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="12ed5-169">**File d’attente des appels :** 11cd3e2e-FCCB-42AD-AD00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="12ed5-169">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="12ed5-170">Si vous souhaitez que la file d’attente d’appels ou le standard automatique puissent être recherchés par les utilisateurs de Skype entreprise Server 2019, vous devez créer vos comptes de ressources dans Skype entreprise Server 2019, car les comptes de ressources en ligne ne sont pas synchronisés avec Active Directory.</span><span class="sxs-lookup"><span data-stu-id="12ed5-170">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="12ed5-171">Lorsque les enregistrements DNS SRV pour sipfederationtls sont résolus vers Skype entreprise Server 2019, les comptes de ressources **doivent** être créés dans Skype entreprise Server 2019 à l’aide de marketing Management Shell et synchronisés avec Azure ad.</span><span class="sxs-lookup"><span data-stu-id="12ed5-171">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to Azure AD.</span></span>

<span data-ttu-id="12ed5-172">Pour les implémentations hybrides avec Skype entreprise Server, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="12ed5-172">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="12ed5-173">Planifier les standards automatiques cloud</span><span class="sxs-lookup"><span data-stu-id="12ed5-173">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="12ed5-174">Planifier les files d’attente d’appels cloud</span><span class="sxs-lookup"><span data-stu-id="12ed5-174">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="12ed5-175">Configurer les comptes de ressources locaux</span><span class="sxs-lookup"><span data-stu-id="12ed5-175">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a><span data-ttu-id="12ed5-176">Supprimer un compte de ressource</span><span class="sxs-lookup"><span data-stu-id="12ed5-176">Delete a resource account</span></span>

<span data-ttu-id="12ed5-177">Vérifiez que vous avez dissocié le numéro de téléphone du compte de ressources avant de le supprimer, afin d’éviter de rester bloqué dans le mode en attente.</span><span class="sxs-lookup"><span data-stu-id="12ed5-177">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span>

<span data-ttu-id="12ed5-178">Après quoi, vous pouvez supprimer le compte de ressources dans le centre d’administration 365 Microsoft, sous l’onglet utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="12ed5-178">After you do that, you can delete the resource account in the Microsoft 365 admin center, under the Users tab.</span></span>

<span data-ttu-id="12ed5-179">Pour dissocier un numéro de téléphone de routage direct du compte de ressources, utilisez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="12ed5-179">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

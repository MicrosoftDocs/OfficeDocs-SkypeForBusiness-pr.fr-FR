---
title: Configurer les crédits de communication pour votre organisation
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: d5e246b42a2e90bf0808a574ed27ee76a4b60280
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/20/2019
ms.locfileid: "30120915"
---
# <a name="set-up-communications-credits-for-your-organization"></a><span data-ttu-id="712e1-103">Configurer les crédits de communication pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="712e1-103">Set up Communications Credits for your organization</span></span>

<span data-ttu-id="712e1-104">Vous devez configurer les crédits de communications si vous souhaitez utiliser des numéros gratuits avec Skype pour Business et Teams Microsoft.</span><span class="sxs-lookup"><span data-stu-id="712e1-104">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams.</span></span> <span data-ttu-id="712e1-105">En outre, nous vous recommandons de configurer les Communications crédits pour votre appel Plans (national ou International) et de conférence des utilisateurs qui ont besoin de la possibilité d’effectuer des appels sortants vers **une destination**.</span><span class="sxs-lookup"><span data-stu-id="712e1-105">Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**.</span></span> <span data-ttu-id="712e1-106">Plusieurs pays/régions sont incluses, mais certaines destinations ne peuvent pas être incluses dans vos abonnements planifier l’appel ou de conférence Audio.</span><span class="sxs-lookup"><span data-stu-id="712e1-106">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> <span data-ttu-id="712e1-107">Si vous ne pas configurer les Communications crédits facturation et attribuez une licence de **Communications crédits** à vos utilisateurs et que vous exécutez minutes pour votre organisation (en fonction de votre plan Plan d’appel ou de conférence Audio dans votre pays/région), ces utilisateurs sera en mesure d’effectuer des appels ou effectuer des appels sortants à partir des réunions de conférence Audio.</span><span class="sxs-lookup"><span data-stu-id="712e1-107">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="712e1-108">Vous pouvez obtenir plus d’informations, y compris recommandé de financement montants, en lisant l’article [Quelles sont les Communications crédits ?](what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="712e1-108">You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="712e1-109">Pour connaitre le coût, [voir les tarifs ici](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span><span class="sxs-lookup"><span data-stu-id="712e1-109">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span> 
  
## <a name="step-1-assign-an-audio-conferencing-and-calling-plan-license-to-your-users"></a><span data-ttu-id="712e1-110">Étape 1 : Attribuer une licence de conférence Audio et planifier l’appel à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="712e1-110">Step 1: Assign an Audio Conferencing and Calling Plan license to your users</span></span>

<span data-ttu-id="712e1-111">Lorsque vous vous inscrivez, vous obtenez un certain nombre de minutes en fonction de votre pays/région.</span><span class="sxs-lookup"><span data-stu-id="712e1-111">When you sign up, you get a certain number of minutes depending on your country/region.</span></span> <span data-ttu-id="712e1-112">Vous pouvez voir le nombre de minutes que vous obtenez la recherche pour le pays ou la région [ici](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="712e1-112">You can see the number of minutes you will get search for the country or region [here](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> <span data-ttu-id="712e1-113">Une fois que vous utilisez les minutes, les appels seront déconnectés.</span><span class="sxs-lookup"><span data-stu-id="712e1-113">After you use those minutes, calls will be disconnected.</span></span> <span data-ttu-id="712e1-114">Pour éviter cette situation, vous devez configurer les crédits de Communications.</span><span class="sxs-lookup"><span data-stu-id="712e1-114">To prevent this from happening, you need to set up Communications Credits.</span></span>
  
<span data-ttu-id="712e1-115">Pour cela, **vous devez affecter une conférence Audio ou une licence de système téléphonique** à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="712e1-115">To do so, **you need to assign an Audio Conferencing or Phone System license** to your users.</span></span>
  
- <span data-ttu-id="712e1-116">Attribuer une licence de **Conférence Audio** à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="712e1-116">Assign an **Audio Conferencing** license to your users.</span></span> <span data-ttu-id="712e1-117">Consultez les [licences d’affecter des équipes Microsoft](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="712e1-117">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>
    
    <span data-ttu-id="712e1-118">Une fois que vous affectez cette licence, vous devez configurer les services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="712e1-118">After you assign this license, you will need to set up audio conferencing.</span></span> <span data-ttu-id="712e1-119">Pour obtenir des instructions détaillées, voir [essayer ou acheter conférence dans Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span><span class="sxs-lookup"><span data-stu-id="712e1-119">For step-by-step instructions, see [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span></span>
    
- <span data-ttu-id="712e1-120">Affecter le **Système téléphonique** et une licence de planifier l’appel interne ou nationale et internationale à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="712e1-120">Assign **Phone System** and a domestic or domestic and international Calling Plan license to your users.</span></span> <span data-ttu-id="712e1-121">Consultez les [licences d’affecter des équipes Microsoft](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="712e1-121">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="712e1-122">Bien qu’il ne soit pas obligatoire pour les Communications générique, vous devez également affecter un **Intérieur appelant planifier** ou une licence **national et International appelant planifier** .</span><span class="sxs-lookup"><span data-stu-id="712e1-122">Although it's not required for Communications Credits, you still need to also assign a **Domestic Calling Plan** or an **Domestic and International Calling Plan** license.</span></span>
  
    <span data-ttu-id="712e1-123">Après avoir affecté ces licences, vous devrez également obtenir les numéros de téléphone pour votre organisation, puis les affecter aux utilisateurs dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="712e1-123">After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="712e1-124">Pour obtenir des instructions pas à pas, consultez [configurer des Plans de l’appel](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="712e1-124">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>
    
<span data-ttu-id="712e1-125">Pour plus d’informations, voir [Gestion des licences de module complémentaire Microsoft équipes](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="712e1-125">For more information, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="712e1-126">Étape 2 : Configurer les crédits de Communications pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="712e1-126">Step 2: Set up Communications Credits for your organization</span></span>

1. <span data-ttu-id="712e1-127">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="712e1-127">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="712e1-128">Dans la navigation de gauche du centre d’administration Office 365, accédez à la **facturation** > **abonnements** > **abonnements ajouter**.</span><span class="sxs-lookup"><span data-stu-id="712e1-128">In the left navigation of the Office 365 admin center, go to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>

3. <span data-ttu-id="712e1-129">Développez les **abonnements au module complémentaire**et choisissez **Crédits Communications** > **Acheter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="712e1-129">Expand **Add-on subscriptions**, and then choose **Communications Credits** > **Buy now**.</span></span>
    
4. <span data-ttu-id="712e1-130">Dans la page d’abonnement **Communications crédits** , renseignez vos informations, puis cliquez sur **suivant**:</span><span class="sxs-lookup"><span data-stu-id="712e1-130">On the **Communications Credits** subscription page, fill in your information, and then click **Next**:</span></span>
    
   - <span data-ttu-id="712e1-131">**Ajouter fonds** Entrez le montant que vous souhaitez ajouter à votre compte.</span><span class="sxs-lookup"><span data-stu-id="712e1-131">**Add funds** Enter the amount that you want to add to your account.</span></span> <span data-ttu-id="712e1-132">Si vous n’activez pas auto-recharge, une fois ces fonds épuisement, l’appel de fonctionnalités qui sont activées à l’aide de Communications crédits est interrompue (tel que service gratuit entrant).</span><span class="sxs-lookup"><span data-stu-id="712e1-132">If you don't enable auto-recharge, once these funds are depleted, calling capabilities that are enabled using Communications Credits will be disrupted (such as inbound toll-free service).</span></span> <span data-ttu-id="712e1-133">Pour éviter de réapprovisionnement manuellement votre compte Communications crédits chaque fois que votre compte atteint la valeur 0 (zéro), nous vous recommandons de que vous activez la fonctionnalité auto-recharge.</span><span class="sxs-lookup"><span data-stu-id="712e1-133">To avoid having to manually replenish your Communications Credits balance each time your balance reaches 0 (zero), we recommend you enable the auto-recharge feature.</span></span>
    
   - <span data-ttu-id="712e1-134">**Recharge automatique** Activer la recharge automatique permet de recharger automatiquement votre compte lorsque son solde passe en dessous d'un seuil que vous avez défini.</span><span class="sxs-lookup"><span data-stu-id="712e1-134">**Auto-recharge** Enabling auto-recharge will automatically refill your account when the balance falls below the threshold that you set.</span></span>
    
     <span data-ttu-id="712e1-135">Il est recommandé d’utiliser le paramètre **recharge automatique** pour éviter toute perturbation du service de votre compte Communications crédits doit parvenir à 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="712e1-135">It's recommended that you use the **Auto-recharge** setting to avoid any disruption of service should your Communications Credits balance reach 0 (zero).</span></span> <span data-ttu-id="712e1-136">Vous recevrez un message électronique lors de transactions recharge réussissent, lorsque les transactions recharge échouent (par exemple, une carte de crédit arrivés à expiration) et lorsque votre compte Communications crédits atteint 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="712e1-136">You will be sent an email when recharge transactions succeed, when recharge transactions fail (such as an expired credit card), and when your Communications Credits balance reaches 0 (zero).</span></span>
    
   - <span data-ttu-id="712e1-137">**Rechargez le montant** Entrez le montant dans la zone **Recharger avec** que vous souhaitez ajouter à votre compte une fois qu’elle atteint la quantité de déclencheur ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="712e1-137">**Recharge amount** Enter the amount in the **Recharge with** box that you want added to your account once it reaches the trigger amount below.</span></span>
    
   - <span data-ttu-id="712e1-138">**Quantité de déclencheur** Entrez le montant dans la zone **lorsque l’équilibre tombe en dessous** qui sera utilisé pour ' *déclencheur* ' le rechargement de standard automatique.</span><span class="sxs-lookup"><span data-stu-id="712e1-138">**Trigger amount** Enter the amount in **When the balance falls below** box that will be used to ' *trigger*  ' the auto-recharge.</span></span> <span data-ttu-id="712e1-139">Une fois que votre compte est inférieur à ce montant, le montant recharge sera automatiquement ajouté à votre compte.</span><span class="sxs-lookup"><span data-stu-id="712e1-139">Once your balance falls below this amount, the recharge amount will be added automatically to your account.</span></span>

      > [!NOTE]
     > <span data-ttu-id="712e1-140">Fonds seront appliquées uniquement aux Communications crédits chez Microsoft publié taux lorsque les services sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="712e1-140">Funds will be applied only to Communications Credits at Microsoft published rates when the services are used.</span></span> <span data-ttu-id="712e1-141">Tout fond non utilisé dans les 12 mois suivant la date d'achat expire et est perdu.</span><span class="sxs-lookup"><span data-stu-id="712e1-141">Any funds not used within 12 months of the purchase date will expire and be forfeited.</span></span> 
    
5. <span data-ttu-id="712e1-142">Entrez vos informations de paiement, cliquez sur **passer la commande**.</span><span class="sxs-lookup"><span data-stu-id="712e1-142">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="712e1-143">Si vous êtes un client de gestion des licences en volume, vous pouvez choisir votre numéro de contrat entreprise pour le paiement.</span><span class="sxs-lookup"><span data-stu-id="712e1-143">If you are a volume licensing customer, you may choose your enterprise agreement number for payment.</span></span> <span data-ttu-id="712e1-144">Si vous avez plusieurs numéros d’accord entreprise, vous serez en mesure de sélectionner l’accord entreprise que vous souhaitez utiliser pour le paiement.</span><span class="sxs-lookup"><span data-stu-id="712e1-144">If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment.</span></span> <span data-ttu-id="712e1-145">Vous aurez également une possibilité de spécifier un numéro de commande fournisseur à associer avec le numéro d’accord entreprise (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="712e1-145">You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="712e1-146">Chaque organisation dispose d’une utilisation différents de volume de l’appel de planifier et taux à prendre en compte.</span><span class="sxs-lookup"><span data-stu-id="712e1-146">Each organization will have a different usage of Calling Plan volume and rates to consider.</span></span> <span data-ttu-id="712e1-147">You will need to get this type of usage data from your current service provider.</span><span class="sxs-lookup"><span data-stu-id="712e1-147">You will need to get this type of usage data from your current service provider.</span></span> <span data-ttu-id="712e1-148">Organisations utilisant déjà Skype pour Business Online déjà comme leur fournisseur de services peuvent obtenir des données d’utilisation consulté dans le **Skype pour le centre d’administration de Business** > **rapports** > rapport de**détails d’utilisation PSTN** .</span><span class="sxs-lookup"><span data-stu-id="712e1-148">Organizations already using Skype for Business Online already as their service provider can get usage data by reviewing it in the **Skype for Business admin center** > **Reports** > **PSTN usage details** report.</span></span>
  
<span data-ttu-id="712e1-149">Lorsque vous configurez Communications générique, vous devez examiner l’utilisation des appels pour votre organisation déterminer les montants que vous devrez mettre dans.</span><span class="sxs-lookup"><span data-stu-id="712e1-149">When you are setting up Communications Credits, you will need to investigate call usage for your organization to determine the amounts that you will need to put in.</span></span> <span data-ttu-id="712e1-150">Ces informations sont disponibles dans le rapport **Détails de l'utilisation RTC**.</span><span class="sxs-lookup"><span data-stu-id="712e1-150">You can get call usage information by reviewing the **PSTN usage details** report.</span></span> <span data-ttu-id="712e1-151">Ce rapport permet d’exporter les enregistrements de données d’appel vers Excel si vous souhaitez exporter les données pour le stockage ou créer des rapports personnalisés.</span><span class="sxs-lookup"><span data-stu-id="712e1-151">This report lets you export the call data records to Excel if you want to export the data for storage or create custom reports.</span></span> <span data-ttu-id="712e1-152">Pour l’utilisation, consultez [Skype pour le rapport d’utilisation PSTN Business](/SkypeForBusiness/skype-for-business-online-reporting/pstn-usage-report)</span><span class="sxs-lookup"><span data-stu-id="712e1-152">To see usage, see [Skype for Business PSTN usage report](/SkypeForBusiness/skype-for-business-online-reporting/pstn-usage-report)</span></span>
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a><span data-ttu-id="712e1-153">Étape 3 : Attribuer une licence crédits Communications aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="712e1-153">Step 3: Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="712e1-154">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="712e1-154">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="712e1-155">Dans la navigation de gauche du centre d’administration Office 365, accédez aux **utilisateurs** > **utilisateurs actifs**, puis sélectionnez un ou plusieurs utilisateurs dans la liste.</span><span class="sxs-lookup"><span data-stu-id="712e1-155">In the left navigation of the Office 365 admin center, go to **Users** > **Active users**, and then select a user or users from the list.</span></span>
    
3. <span data-ttu-id="712e1-156">Dans le volet Action, sous **Licences de produit**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="712e1-156">In the Action pane under **Product licenses**, click **Edit**.</span></span>
    
4. <span data-ttu-id="712e1-157">Dans la page **licences de produits** , activer/désactiver les **Communications crédits** **sur** pour affecter cette licence, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="712e1-157">On the **Product licenses** page, toggle **Communications Credits** to **On** to assign this license, and then click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="712e1-158">Même si vous avez des utilisateurs auxquels une licence **Enterprise E5** , il est conseillé de faire.</span><span class="sxs-lookup"><span data-stu-id="712e1-158">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>
  
## <a name="want-to-know-about-plans-and-pricing"></a><span data-ttu-id="712e1-159">Vous souhaitez en savoir plus sur les offres et les tarifs ?</span><span class="sxs-lookup"><span data-stu-id="712e1-159">Want to know about plans and pricing?</span></span>

<span data-ttu-id="712e1-160">Vous pouvez voir les plans et les prix à partir d’un des liens suivants :</span><span class="sxs-lookup"><span data-stu-id="712e1-160">You can see the plans and pricing by visiting one of the following links:</span></span>
  
- [<span data-ttu-id="712e1-161">Offres d'appels</span><span class="sxs-lookup"><span data-stu-id="712e1-161">Calling Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [<span data-ttu-id="712e1-162">Plans de services d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="712e1-162">Audio Conferencing Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [<span data-ttu-id="712e1-163">Plans de système téléphonique</span><span class="sxs-lookup"><span data-stu-id="712e1-163">Phone System Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799763)
    
<span data-ttu-id="712e1-164">Vous pouvez également voir des informations en [vous connectant au centre d’administration Office 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) et **facturation** > **abonnements** > **abonnements ajouter**.</span><span class="sxs-lookup"><span data-stu-id="712e1-164">You can also see information by [signing in to the Office 365 admin center](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) and going to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>
  
<span data-ttu-id="712e1-165">Pour obtenir un tableau avec la licence ou les licences que vous aurez besoin pour chaque fonctionnalité, voir [Gestion des licences de module complémentaire équipes Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="712e1-165">To see a table with the license or licenses you will need for each feature, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="712e1-166">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="712e1-166">Related topics</span></span>

- [<span data-ttu-id="712e1-167">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="712e1-167">Set up Skype for Business Online</span></span>](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [<span data-ttu-id="712e1-168">Configurer la messagerie vocale du système téléphonique - Aide pour l'administrateur</span><span class="sxs-lookup"><span data-stu-id="712e1-168">Set up Phone System voicemail - Admin help</span></span>](set-up-phone-system-voicemail.md)
    
- <span data-ttu-id="712e1-169">[Configurer des Forfaits d’appels](set-up-calling-plans.md) et [Forfaits d’appels pour Office 365](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="712e1-169">[Set up Calling Plans](set-up-calling-plans.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md)</span></span>
    
- [<span data-ttu-id="712e1-170">Ajouter des fonds et gérer les Crédits de Communications</span><span class="sxs-lookup"><span data-stu-id="712e1-170">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
    
  
 
---
title: Configurer un attendant automatique pour Microsoft Teams - Didacticiel pour les petites entreprises
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Découvrez comment configurer et tester les attendants automatiques pour Microsoft 365 Business Voice.
ms.openlocfilehash: b3b291a91c96d75acdc8d4fe77f78790d2137914
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909616"
---
# <a name="set-up-an-auto-attendant---small-business-tutorial"></a><span data-ttu-id="3b44c-103">Configurer un attendant automatique - Didacticiel pour les petites entreprises</span><span class="sxs-lookup"><span data-stu-id="3b44c-103">Set up an auto attendant - small business tutorial</span></span>

<span data-ttu-id="3b44c-104">Les employés automatiques peuvent appeler votre organisation et parcourir un système de menus pour parler au service, à la file d’attente d’appels, à une personne ou à un opérateur.</span><span class="sxs-lookup"><span data-stu-id="3b44c-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="3b44c-105">Vous pouvez créer des attendants automatiques pour votre organisation avec le Centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3b44c-105">You can create auto attendants for your organization with the Microsoft Teams admin center.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="3b44c-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="3b44c-106">Before you begin</span></span>

<span data-ttu-id="3b44c-107">Obtenez les numéros de service dont vous avez besoin pour les travailleurs automatiques que vous souhaitez rendre accessibles en composant un numéro direct depuis l’extérieur de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3b44c-107">Get the service numbers that you need for the auto attendants that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="3b44c-108">Cela peut inclure [le transfert de numéros d’un autre fournisseur](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) ou la demande de nouveaux numéros de [service.](../getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="3b44c-108">This might include [transferring numbers from another provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](../getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="3b44c-109">Obtenir un [système téléphonique - Licence Utilisateur virtuel](../teams-add-on-licensing/virtual-user.md) pour chaque employé automatique que vous prévoyez de créer.</span><span class="sxs-lookup"><span data-stu-id="3b44c-109">Get a [Phone System - Virtual User license](../teams-add-on-licensing/virtual-user.md) for each auto attendant that you plan to create.</span></span> <span data-ttu-id="3b44c-110">Ces licences sont gratuites. Nous vous suggérons donc d’en obtenir quelques supplémentaires si vous décidez de modifier votre installation ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="3b44c-110">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="3b44c-111">Si vous souhaitez utiliser un itinéraire des appels [](../set-up-holidays-in-teams.md) différent pour les jours fériés, créez les jours fériés que vous voulez utiliser avant de créer le attendant automatique.</span><span class="sxs-lookup"><span data-stu-id="3b44c-111">If you want to have your auto attendant route calls differently on holidays, then [create the holidays that you want to use](../set-up-holidays-in-teams.md) before you create the auto attendant.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a><span data-ttu-id="3b44c-112">Pour configurer votre attendant automatique, suivez les étapes ci-après</span><span class="sxs-lookup"><span data-stu-id="3b44c-112">Follow these steps to set up your auto attendant</span></span>

# <a name="step-1brphone-number"></a>[<span data-ttu-id="3b44c-113">Étape 1 <br> Numéro de téléphone</span><span class="sxs-lookup"><span data-stu-id="3b44c-113">Step 1<br>Phone number</span></span>](#tab/phone-number)

<span data-ttu-id="3b44c-114">Chaque employé automatique que vous créez nécessite un compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="3b44c-114">Each auto attendant that you create requires a resource account.</span></span> <span data-ttu-id="3b44c-115">Ce compte est similaire à un compte d’utilisateur, sauf qu’il est associé à un moyen de service automatique ou à une file d’attente d’appels au lieu d’une personne.</span><span class="sxs-lookup"><span data-stu-id="3b44c-115">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="3b44c-116">Dans cette étape, nous allons créer le compte, lui attribuer une licence *Microsoft 365 Phone System - Utilisateur* virtuel, puis attribuer un numéro de service.</span><span class="sxs-lookup"><span data-stu-id="3b44c-116">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then assign a service number.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="3b44c-117">Créer un compte de ressource</span><span class="sxs-lookup"><span data-stu-id="3b44c-117">Create a resource account</span></span>

<span data-ttu-id="3b44c-118">Vous pouvez créer un compte de ressource dans le Centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="3b44c-118">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="3b44c-119">Dans le Centre d’administration Teams, développez **les paramètres** à l’échelle de l’organisation, puis cliquez **sur Comptes de ressources.**</span><span class="sxs-lookup"><span data-stu-id="3b44c-119">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="3b44c-120">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="3b44c-120">Click **Add**.</span></span>

3. <span data-ttu-id="3b44c-121">Dans le **volet Ajouter un compte** de ressource, tapez Nom **d’affichage,** Nom d’utilisateur et sélectionnez Le attendant **automatique** pour le type de compte **de ressource** </span><span class="sxs-lookup"><span data-stu-id="3b44c-121">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Auto attendant** for the **Resource account type**</span></span>

    ![Capture d’écran de l’interface utilisateur Ajouter un compte de ressource](../media/resource-account-add.png)

4. <span data-ttu-id="3b44c-123">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3b44c-123">Click **Save**.</span></span>

<span data-ttu-id="3b44c-124">Le nouveau compte apparaît dans la liste des comptes.</span><span class="sxs-lookup"><span data-stu-id="3b44c-124">The new account will appear in the list of accounts.</span></span>

![Capture d’écran d’une liste des comptes de ressources](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="3b44c-126">Attribuer une licence</span><span class="sxs-lookup"><span data-stu-id="3b44c-126">Assign a license</span></span>

<span data-ttu-id="3b44c-127">Vous devez attribuer une *licence Microsoft 365 Phone System - Utilisateur* virtuel au compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="3b44c-127">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="3b44c-128">Dans le Centre d’administration Microsoft 365, cliquez sur le compte de ressource auquel vous voulez attribuer une licence.</span><span class="sxs-lookup"><span data-stu-id="3b44c-128">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="3b44c-129">Sous **l’onglet Licences et** applications, sous **Licences,** sélectionnez **Microsoft 365 Phone System - Utilisateur virtuel.**</span><span class="sxs-lookup"><span data-stu-id="3b44c-129">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="3b44c-130">Cliquez **sur Enregistrer les modifications.**</span><span class="sxs-lookup"><span data-stu-id="3b44c-130">Click **Save changes**.</span></span>

    ![Capture d’écran de l’interface utilisateur d’attribution de licences dans le Centre d’administration Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a><span data-ttu-id="3b44c-132">Affecter un numéro de service</span><span class="sxs-lookup"><span data-stu-id="3b44c-132">Assign a service number</span></span>

<span data-ttu-id="3b44c-133">Si vous avez besoin que ce moyen de service automatique soit accessible à l’aide d’un numéro de téléphone, affectez ce numéro au compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="3b44c-133">If you need this auto attendant to be reachable by a phone number, then assign that number to the resource account.</span></span>

1. <span data-ttu-id="3b44c-134">Dans le Centre d’administration Teams, sur la **page** Comptes de ressources, sélectionnez le compte de ressource auquel vous voulez affecter un numéro de service, puis cliquez sur **Affecter/Désaffecter.**</span><span class="sxs-lookup"><span data-stu-id="3b44c-134">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="3b44c-135">Dans le **type de numéro de** téléphone, sélectionnez le type de numéro que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="3b44c-135">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="3b44c-136">Dans la **zone Numéro de téléphone** affecté, recherchez le numéro à utiliser, puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="3b44c-136">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

    ![Capture d’écran de l’interface utilisateur affecter un numéro de service](../media/resource-account-assign-phone-number.png)

4. <span data-ttu-id="3b44c-138">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3b44c-138">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3b44c-139">Étape 2 : le attendant automatique - Informations générales sur ></span><span class="sxs-lookup"><span data-stu-id="3b44c-139">Step 2 - Auto attendant general info ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[<span data-ttu-id="3b44c-140">Étape 2 : <br> Attendant - Informations générales</span><span class="sxs-lookup"><span data-stu-id="3b44c-140">Step 2<br>Attendant general info</span></span>](#tab/general-info)

<span data-ttu-id="3b44c-141">Pour configurer un attendant automatique</span><span class="sxs-lookup"><span data-stu-id="3b44c-141">To set up an auto attendant</span></span>

1. <span data-ttu-id="3b44c-142">Dans le Centre d’administration Teams, **développez Voix,** cliquez sur **Auto attendants,** puis sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="3b44c-142">In the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

2. <span data-ttu-id="3b44c-143">Tapez un nom pour le attendant automatique dans la zone en haut.</span><span class="sxs-lookup"><span data-stu-id="3b44c-143">Type a name for the auto attendant in the box at the top.</span></span>

3. <span data-ttu-id="3b44c-144">Si vous voulez désigner un opérateur, spécifiez la destination des appels vers cet opérateur.</span><span class="sxs-lookup"><span data-stu-id="3b44c-144">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="3b44c-145">Cette option est facultative (mais recommandée).</span><span class="sxs-lookup"><span data-stu-id="3b44c-145">This is optional (but recommended).</span></span> <span data-ttu-id="3b44c-146">Vous pouvez définir l’option **Opérateur** pour permettre aux appelants de sortir des menus et de parler à une personne désignée.</span><span class="sxs-lookup"><span data-stu-id="3b44c-146">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

4. <span data-ttu-id="3b44c-147">Spécifiez le fuseau horaire de ce attendant automatique.</span><span class="sxs-lookup"><span data-stu-id="3b44c-147">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="3b44c-148">Le fuseau horaire est utilisé pour calculer les heures d’ouverture si vous créez un flux d’appels distinct pour les heures de travail en de suite.</span><span class="sxs-lookup"><span data-stu-id="3b44c-148">The time zone is used for calculating business hours if you create a separate call flow for after hours.</span></span>

5. <span data-ttu-id="3b44c-149">Spécifiez une langue pour ce attendant automatique.</span><span class="sxs-lookup"><span data-stu-id="3b44c-149">Specify a language for this auto attendant.</span></span> <span data-ttu-id="3b44c-150">Il s’agir de la langue qui sera utilisée pour les invites vocales générées par le système.</span><span class="sxs-lookup"><span data-stu-id="3b44c-150">This the language that will be used for system-generated voice prompts.</span></span>

6. <span data-ttu-id="3b44c-151">Choisissez si vous voulez activer les entrées vocales.</span><span class="sxs-lookup"><span data-stu-id="3b44c-151">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="3b44c-152">Lorsqu’elle est activée, le nom de chaque option de menu devient un mot clé de reconnaissance vocale.</span><span class="sxs-lookup"><span data-stu-id="3b44c-152">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="3b44c-153">Par exemple, les appelants peuvent dire « Un » pour sélectionner l’option de menu mappée vers la touche 1, ou dire « Ventes » pour sélectionner l’option de menu appelée « Ventes ».</span><span class="sxs-lookup"><span data-stu-id="3b44c-153">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

    ![Capture d’écran des paramètres de attendant automatique pour les entrées de nom, d’opérateur, de fuseau horaire, de langue et de voix](../media/auto-attendant-general-info-page-new.png)

7. <span data-ttu-id="3b44c-155">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="3b44c-155">Click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3b44c-156">Étape 3 : flux d’appels ></span><span class="sxs-lookup"><span data-stu-id="3b44c-156">Step 3 - Call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[<span data-ttu-id="3b44c-157">Flux d’appels <br> d’étape 3</span><span class="sxs-lookup"><span data-stu-id="3b44c-157">Step 3<br>Call flow</span></span>](#tab/call-flow)

<span data-ttu-id="3b44c-158">Choisir vos options de flux d’appels</span><span class="sxs-lookup"><span data-stu-id="3b44c-158">Choose your call flow options</span></span>

1. <span data-ttu-id="3b44c-159">Choisissez si vous souhaitez lire un message d’accueil lorsque le attendant automatique répond à un appel.</span><span class="sxs-lookup"><span data-stu-id="3b44c-159">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

    <span data-ttu-id="3b44c-160">Si vous **sélectionnez Lire un fichier audio,** vous pouvez utiliser le bouton Télécharger un fichier pour télécharger un message d’accueil enregistré en tant qu’audio dans .  WAV, . MP3 ou . Format WMA.</span><span class="sxs-lookup"><span data-stu-id="3b44c-160">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="3b44c-161">L’enregistrement ne peut pas avoir une taille supérieure à 5 Mo.</span><span class="sxs-lookup"><span data-stu-id="3b44c-161">The recording can be no larger than 5 MB.</span></span>

    <span data-ttu-id="3b44c-162">Si vous sélectionnez Taper un **message** de salutation, le système lit le texte que vous tapez (jusqu’à 1 000 caractères) lorsque le attendant automatique répond à un appel.</span><span class="sxs-lookup"><span data-stu-id="3b44c-162">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

    ![Capture d’écran des paramètres du message d’accueil](../media/auto-attendant-call-flow-greeting-message.png)

2. <span data-ttu-id="3b44c-164">Choisissez la façon dont vous voulez router l’appel.</span><span class="sxs-lookup"><span data-stu-id="3b44c-164">Choose how you want to route the call.</span></span>

    <span data-ttu-id="3b44c-165">Si vous sélectionnez **Déconnecter,** le attendant automatique raccrochera.</span><span class="sxs-lookup"><span data-stu-id="3b44c-165">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

    <span data-ttu-id="3b44c-166">Si vous sélectionnez **Rediriger l’appel,** vous pouvez choisir l’une des destinations de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="3b44c-166">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

    <span data-ttu-id="3b44c-167">Si vous sélectionnez **les options du menu** Lecture, vous pouvez choisir de lire un fichier **audio** ou de taper un **message** d’accueil, puis de choisir entre les options de menu et la recherche dans l’annuaire.</span><span class="sxs-lookup"><span data-stu-id="3b44c-167">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

    ![Capture d’écran des paramètres de routage des appels](../media/auto-attendant-call-flow-route-call-message.png)

3. <span data-ttu-id="3b44c-169">Si vous souhaitez que les appelants utilisent les touches de numérotation pour naviguer, sous Définir les options du **menu,** choisissez ce que vous voulez faire lorsque les appelants appuient sur une touche de numérotation.</span><span class="sxs-lookup"><span data-stu-id="3b44c-169">If you want callers to use dial keys to navigate, then under **Set menu options**, choose what you want to happen when callers press a dial key.</span></span> <span data-ttu-id="3b44c-170">(Si vous créez ce attendant automatique en tant qu’annuaire de l’entreprise, laissez les options de touches de numérotation vides.)</span><span class="sxs-lookup"><span data-stu-id="3b44c-170">(If you're creating this auto attendant as a company directory, leave the dial key options blank.)</span></span>

    <span data-ttu-id="3b44c-171">Vous pouvez définir n’importe quelle touche de numérotation sur les destinations suivantes :</span><span class="sxs-lookup"><span data-stu-id="3b44c-171">You can set any of the dial keys to the following destinations:</span></span>

    - <span data-ttu-id="3b44c-172">**Une personne de l’organisation,** une personne de votre organisation qui peut recevoir des appels vocux.</span><span class="sxs-lookup"><span data-stu-id="3b44c-172">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span>
    - <span data-ttu-id="3b44c-173">**Application vocale :** un autre attendant automatique ou une file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="3b44c-173">**Voice app** - another auto attendant or a call queue.</span></span>
    - <span data-ttu-id="3b44c-174">**Numéro de téléphone externe -** n’importe quel numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="3b44c-174">**External phone number** - any phone number.</span></span> <span data-ttu-id="3b44c-175">Utilisez ce format : +[code pays][code de zone][numéro de téléphone]</span><span class="sxs-lookup"><span data-stu-id="3b44c-175">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="3b44c-176">**Messagerie vocale** : boîte vocale associée à un groupe Microsoft 365 que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="3b44c-176">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
    - <span data-ttu-id="3b44c-177">**Opérateur** (opérateur défini pour le transport automatique).</span><span class="sxs-lookup"><span data-stu-id="3b44c-177">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="3b44c-178">La définition d’un opérateur est facultative.</span><span class="sxs-lookup"><span data-stu-id="3b44c-178">Defining an operator is optional.</span></span> <span data-ttu-id="3b44c-179">L’opérateur peut être défini comme n’importe quelle autre destination dans cette liste.</span><span class="sxs-lookup"><span data-stu-id="3b44c-179">The operator can be defined as any of the other destinations in this list.</span></span>

    <span data-ttu-id="3b44c-180">Nous vous recommandons de définir 0 touche sur l’opérateur.</span><span class="sxs-lookup"><span data-stu-id="3b44c-180">We recommend setting 0 key to the operator.</span></span>

    <span data-ttu-id="3b44c-181">Pour chaque option de menu, spécifiez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="3b44c-181">For each menu option, specify the following:</span></span>

    - <span data-ttu-id="3b44c-182">**Touche de numérotation** (clé du clavier téléphonique pour accéder à cette option).</span><span class="sxs-lookup"><span data-stu-id="3b44c-182">**Dial key** - the key on the telephone keypad to access this option.</span></span>

    - <span data-ttu-id="3b44c-183">**Commande vocale** : définit la commande vocale qu’un appelant peut lui donner pour accéder à cette option, si les entrées vocales sont activées.</span><span class="sxs-lookup"><span data-stu-id="3b44c-183">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="3b44c-184">Il peut contenir plusieurs mots tels que « Service clientèle » ou « Activités et activités ».</span><span class="sxs-lookup"><span data-stu-id="3b44c-184">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> 

    - <span data-ttu-id="3b44c-185">**Rediriger** vers l’endroit où vous souhaitez que l’appel soit reçu lorsque les appelants choisissent cette option.</span><span class="sxs-lookup"><span data-stu-id="3b44c-185">**Redirect to** - where you want the call to go when callers choose this option.</span></span> <span data-ttu-id="3b44c-186">Si vous redirigez vers un service de service automatique ou une file d’attente d’appels, sélectionnez le compte de ressource qui lui est associé.</span><span class="sxs-lookup"><span data-stu-id="3b44c-186">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

    ![Capture d’écran des options de touches de numérotation](../media/auto-attendant-call-flow-menu-options-complete.png)

4. <span data-ttu-id="3b44c-188">Si vous souhaitez utiliser ce attendant automatique comme annuaire de l’entreprise, sous Recherche dans l’annuaire, **sélectionnez Composer par nom.**</span><span class="sxs-lookup"><span data-stu-id="3b44c-188">If you want to use this auto attendant as a company directory, then under **Directory search**, select **Dial by name**.</span></span> <span data-ttu-id="3b44c-189">Lorsque vous activez cette option, les appelants peuvent dire le nom de l’utilisateur ou le taper sur le clavier du téléphone.</span><span class="sxs-lookup"><span data-stu-id="3b44c-189">When you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="3b44c-190">Tout utilisateur en ligne titulaire d’une licence Phone System est un utilisateur éligible et peut être trouvé avec la numérotation par nom.</span><span class="sxs-lookup"><span data-stu-id="3b44c-190">Any online user with a Phone System license is an eligible user and can be found with Dial by name.</span></span> 

    <span data-ttu-id="3b44c-191">(Vous pouvez choisir **Numérotation par extension,** toutefois l’extension doit être configurée dans Azure Active Directory.)</span><span class="sxs-lookup"><span data-stu-id="3b44c-191">(You can choose **Dial by extension**, however the extension must be configured in Azure Active Directory.)</span></span>

5. <span data-ttu-id="3b44c-192">Une fois que vous avez sélectionné une option **de recherche dans l’annuaire,** cliquez sur **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="3b44c-192">Once you have selected a **Directory search** option, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3b44c-193">Étape 4 : flux d’appels en de suite après ></span><span class="sxs-lookup"><span data-stu-id="3b44c-193">Step 4 - After hours call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[<span data-ttu-id="3b44c-194">Étape 4 Après <br> les heures de travail</span><span class="sxs-lookup"><span data-stu-id="3b44c-194">Step 4<br>After hours</span></span>](#tab/after-hours)

<span data-ttu-id="3b44c-195">Les heures d’ouverture peuvent être définies pour chaque attendant automatique.</span><span class="sxs-lookup"><span data-stu-id="3b44c-195">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="3b44c-196">Si ce n'est pas le cas, tous les jours et toutes les heures de la semaine seront considérés comme heures d'ouverture, car une planification 24/24 est définie par défaut.</span><span class="sxs-lookup"><span data-stu-id="3b44c-196">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="3b44c-197">Les heures d’ouverture peuvent être définies avec des pauses au cours de la journée et toutes les heures non définies comme heures d’ouverture sont considérées comme des heures d’ouverture en de suite.</span><span class="sxs-lookup"><span data-stu-id="3b44c-197">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="3b44c-198">Vous pouvez définir différentes options de traitement des appels entrants et des messages d’accueil pour les heures de travail en de suite.</span><span class="sxs-lookup"><span data-stu-id="3b44c-198">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="3b44c-199">Selon la configuration de vos files d’attente automatiques et de vos files d’attente, il se peut que vous devrez uniquement spécifier le routage des appels en de après-heures pour les travailleurs automatiques avec des numéros de téléphone directs.</span><span class="sxs-lookup"><span data-stu-id="3b44c-199">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="3b44c-200">Si vous souhaitez un routage d’appel distinct pour les appelants en de suite, spécifiez vos heures d’ouverture pour chaque jour.</span><span class="sxs-lookup"><span data-stu-id="3b44c-200">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="3b44c-201">Cliquez **sur Ajouter un nouvel horaire** pour spécifier plusieurs ensembles d’heures pour un jour donné, par exemple, pour spécifier une pause déjeuner.</span><span class="sxs-lookup"><span data-stu-id="3b44c-201">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

![Capture d’écran des paramètres de jour et d’heure de fin](../media/auto-attendant-business-hours.png)

<span data-ttu-id="3b44c-203">Une fois que vous avez spécifié vos heures d’ouverture, sélectionnez vos options de routage des appels pour les heures de fermeture.</span><span class="sxs-lookup"><span data-stu-id="3b44c-203">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="3b44c-204">Les mêmes options sont disponibles que pour le routage des appels pendant les heures d’ouverture que vous avez spécifié à l’étape **3 (Flux d’appels).**</span><span class="sxs-lookup"><span data-stu-id="3b44c-204">The same options are available as for the business hours call routing that you specified in **Step 3 - Call flow**.</span></span>

<span data-ttu-id="3b44c-205">Cliquez **sur Suivant** lorsque vous avez terminé.</span><span class="sxs-lookup"><span data-stu-id="3b44c-205">Click **Next** when you're done.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3b44c-206">Étape 5 : flux d’appels pour les ></span><span class="sxs-lookup"><span data-stu-id="3b44c-206">Step 5 - Holiday call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=holidays#steps)

# <a name="step-5brholidays"></a>[<span data-ttu-id="3b44c-207">Étape 5 <br> Jours fériés</span><span class="sxs-lookup"><span data-stu-id="3b44c-207">Step 5<br>Holidays</span></span>](#tab/holidays)

<span data-ttu-id="3b44c-208">Vous pouvez faire router les appels vers votre service de service automatique différemment les jours fériés et les autres jours.</span><span class="sxs-lookup"><span data-stu-id="3b44c-208">You can have calls to your auto attendant routed differently on holidays than on other days.</span></span> <span data-ttu-id="3b44c-209">(Si vous ne voulez pas avoir un flux d’appels différent pour les jours fériés, vous pouvez ignorer cette étape.)</span><span class="sxs-lookup"><span data-stu-id="3b44c-209">(If you don't want to have a different call flow for holidays, you can skip this step.)</span></span>



<span data-ttu-id="3b44c-210">Votre employé automatique peut avoir un flux d’appels pour chaque jour férié que vous avez installé.</span><span class="sxs-lookup"><span data-stu-id="3b44c-210">Your auto attendant can have a call flow for each holiday you've set up.</span></span> <span data-ttu-id="3b44c-211">Vous pouvez ajouter jusqu'à 20 congés planifiés pour chaque standard automatique.</span><span class="sxs-lookup"><span data-stu-id="3b44c-211">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="3b44c-212">Dans la page Paramètres d’appel pour les fêtes, cliquez **sur Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="3b44c-212">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="3b44c-213">Tapez un nom pour ce paramètre de congés.</span><span class="sxs-lookup"><span data-stu-id="3b44c-213">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="3b44c-214">Dans la **dropdown** Jours fériés, choisissez les jours fériés que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="3b44c-214">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="3b44c-215">Choisissez le type de message d’accueil que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="3b44c-215">Choose the type of greeting that you want to use.</span></span>

    ![Capture d’écran des paramètres de vœux pour les fêtes de fin d’année](../media/auto-attendant-holiday-greeting.png)

5. <span data-ttu-id="3b44c-217">Choisissez si vous voulez **déconnecter ou** **rediriger** l’appel.</span><span class="sxs-lookup"><span data-stu-id="3b44c-217">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="3b44c-218">Si vous choisissez de rediriger l’appel, choisissez sa destination de routage.</span><span class="sxs-lookup"><span data-stu-id="3b44c-218">If you chose to redirect, choose the call routing destination for the call.</span></span>

    ![Capture d’écran des paramètres d’action d’appel des fêtes de fin d’année](../media/auto-attendant-holiday-actions.png)

7. <span data-ttu-id="3b44c-220">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3b44c-220">Click **Save**.</span></span>

<span data-ttu-id="3b44c-221">Répétez la procédure si nécessaire pour chaque jour férié supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="3b44c-221">Repeat the procedure as needed for each additional holiday.</span></span>

![Capture d’écran des paramètres de congés avec jours fériés répertoriés](../media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="3b44c-223">Une fois que vous avez ajouté tous vos jours fériés, cliquez sur **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="3b44c-223">When you've added all your holidays, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3b44c-224">Étape 6 : choisir les personnes qui font partir de l'></span><span class="sxs-lookup"><span data-stu-id="3b44c-224">Step 6 - Choose who's in the directory ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[<span data-ttu-id="3b44c-225">Étape 6 <br> Membres du répertoire</span><span class="sxs-lookup"><span data-stu-id="3b44c-225">Step 6<br>Directory members</span></span>](#tab/dial-scope)

<span data-ttu-id="3b44c-226">*L’étendue de* la numérotation définit les utilisateurs disponibles dans l’annuaire lorsqu’un appelant utilise la numérotation par nom ou la numérotation par extension.</span><span class="sxs-lookup"><span data-stu-id="3b44c-226">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="3b44c-227">La valeur par défaut de **Tous les utilisateurs en** ligne inclut tous les utilisateurs de votre organisation qui sont des utilisateurs en ligne titulaires d’une licence De système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="3b44c-227">The default of **All online users** includes all users in your organization that are Online users with a Phone System license.</span></span>

<span data-ttu-id="3b44c-228">Vous pouvez inclure ou exclure  des utilisateurs  spécifiques en sélectionnant Groupe d’utilisateurs personnalisés sous Inclure ou Exclure, puis en choisissant un ou plusieurs groupes, listes de distribution ou groupes de sécurité Microsoft 365. </span><span class="sxs-lookup"><span data-stu-id="3b44c-228">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="3b44c-229">Par exemple, vous pouvez exclure des cadres de votre organisation de l’annuaire d’appels.</span><span class="sxs-lookup"><span data-stu-id="3b44c-229">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="3b44c-230">(Si un utilisateur se trouve dans les deux listes, il sera exclu de l’annuaire.)</span><span class="sxs-lookup"><span data-stu-id="3b44c-230">(If a user is in both lists, they will be excluded from the directory.)</span></span>

![Capture d’écran de l’étendue de la numérotation : inclure et exclure des options](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> <span data-ttu-id="3b44c-232">Jusqu’à 36 heures peuvent être nécessaire pour que le nom d’un nouvel utilisateur soit répertorié dans l’annuaire.</span><span class="sxs-lookup"><span data-stu-id="3b44c-232">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="3b44c-233">Lorsque vous avez terminé de définir la portée de la numérotation, cliquez sur **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="3b44c-233">When you're done setting the dial scope, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3b44c-234">Étape 7 : affecter un compte de ressource ></span><span class="sxs-lookup"><span data-stu-id="3b44c-234">Step 7 - Assign a resource account ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[<span data-ttu-id="3b44c-235">Étape 7 <br> : comptes de ressources</span><span class="sxs-lookup"><span data-stu-id="3b44c-235">Step 7<br>Resource accounts</span></span>](#tab/resource-accounts)

<span data-ttu-id="3b44c-236">Tous les attendants automatiques doivent avoir un compte de ressource associé.</span><span class="sxs-lookup"><span data-stu-id="3b44c-236">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="3b44c-237">Les travailleurs automatiques de premier niveau auront besoin d’au moins un compte de ressource associé à un numéro de service.</span><span class="sxs-lookup"><span data-stu-id="3b44c-237">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="3b44c-238">Si vous le souhaitez, vous pouvez affecter plusieurs comptes de ressources à un fournisseur de services automatique, chacun avec un numéro de service distinct.</span><span class="sxs-lookup"><span data-stu-id="3b44c-238">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="3b44c-239">Pour ajouter un compte de ressource</span><span class="sxs-lookup"><span data-stu-id="3b44c-239">To add a resource account</span></span>

1. <span data-ttu-id="3b44c-240">Cliquez **sur Ajouter un** compte et recherchez le compte à ajouter.</span><span class="sxs-lookup"><span data-stu-id="3b44c-240">Click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="3b44c-241">Cliquez **sur Ajouter,** puis sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="3b44c-241">Click **Add**, and then click **Add**.</span></span>

    ![Capture d’écran du panneau Ajouter des comptes du compte de ressources](../media/auto-attendant-add-resource-account.png)

2. <span data-ttu-id="3b44c-243">Lorsque vous avez terminé d’ajouter des comptes de service, cliquez sur **Envoyer.**</span><span class="sxs-lookup"><span data-stu-id="3b44c-243">When you have finished adding service accounts, click **Submit**.</span></span>

    ![Capture d’écran d’une liste de comptes de ressources affichant le compte de ressource avec le numéro de service affecté](../media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="3b44c-245">La configuration du attendant automatique est terminée.</span><span class="sxs-lookup"><span data-stu-id="3b44c-245">This completes the auto attendant configuration.</span></span>

---



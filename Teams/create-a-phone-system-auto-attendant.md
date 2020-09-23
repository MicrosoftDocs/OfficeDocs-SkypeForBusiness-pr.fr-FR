---
title: Configurer un standard automatique pour Microsoft teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Apprenez à configurer et tester des standards automatiques pour Microsoft Teams.
ms.openlocfilehash: 2cb796db37f40025dc7a78123da729fd5812bbbb
ms.sourcegitcommit: 22e2f51abf879b34701064839d0e410758b6a3dd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48220187"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="0da03-103">Configurer un standard automatique</span><span class="sxs-lookup"><span data-stu-id="0da03-103">Set up an auto attendant</span></span>

<span data-ttu-id="0da03-104">Les standards automatiques permettent aux personnes d’appeler votre organisation et de naviguer dans un système de menus pour parler au service approprié, à la file d’attente des appels, à la personne ou à un opérateur.</span><span class="sxs-lookup"><span data-stu-id="0da03-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="0da03-105">Vous pouvez créer des standards automatiques pour votre organisation à l’aide du centre d’administration Microsoft teams ou avec PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0da03-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span> 

<span data-ttu-id="0da03-106">Vérifiez que vous disposez [d’un plan de lecture pour les standards automatiques d’équipe et les files d’attente d’appels](plan-auto-attendant-call-queue.md) , puis suivez les [étapes de mise](plan-auto-attendant-call-queue.md#getting-started) en route avant de suivre les procédures décrites dans cet article.</span><span class="sxs-lookup"><span data-stu-id="0da03-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="0da03-107">Les standards automatiques peuvent diriger les appels, en fonction de l’entrée des appelants, vers l’une des destinations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0da03-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations:</span></span>

- <span data-ttu-id="0da03-108">**Personne de votre organisation** : une personne de votre organisation qui peut recevoir des appels vocaux.</span><span class="sxs-lookup"><span data-stu-id="0da03-108">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="0da03-109">Il peut s’agir d’un utilisateur en ligne ou hébergé sur site utilisant Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="0da03-109">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="0da03-110">**Application vocale** -autre standard automatique ou file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="0da03-110">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="0da03-111">(Sélectionnez le compte de ressources associé au standard automatique ou à la file d’attente d’appels lors du choix de cette destination.)</span><span class="sxs-lookup"><span data-stu-id="0da03-111">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="0da03-112">**Numéro de téléphone externe** -n’importe quel numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="0da03-112">**External phone number** - any phone number.</span></span> <span data-ttu-id="0da03-113">(Voir les [Détails techniques sur les transferts externes](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span><span class="sxs-lookup"><span data-stu-id="0da03-113">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="0da03-114">Boîte **vocale** -la boîte aux lettres vocale associée à un groupe Microsoft 365 que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="0da03-114">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="0da03-115">**Opérateur** -l’opérateur défini pour le standard automatique.</span><span class="sxs-lookup"><span data-stu-id="0da03-115">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="0da03-116">La définition d’un opérateur est facultative.</span><span class="sxs-lookup"><span data-stu-id="0da03-116">Defining an operator is optional.</span></span> <span data-ttu-id="0da03-117">L’opérateur peut être défini comme n’importe quelle autre destination dans cette liste.</span><span class="sxs-lookup"><span data-stu-id="0da03-117">The operator can be defined as any of the other destinations in this list.</span></span>

<span data-ttu-id="0da03-118">Vous êtes invité à choisir l’une de ces options à différentes étapes Lorsque vous configurez un standard automatique.</span><span class="sxs-lookup"><span data-stu-id="0da03-118">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="0da03-119">Pour configurer un standard automatique, dans le centre d’administration Teams, développez **voix**, cliquez sur **standards automatiques**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="0da03-119">To set up an auto attendant, in the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="0da03-120">Informations générales</span><span class="sxs-lookup"><span data-stu-id="0da03-120">General info</span></span>

![](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="0da03-121">Tapez un nom pour le standard automatique dans la zone située dans la partie supérieure.</span><span class="sxs-lookup"><span data-stu-id="0da03-121">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="0da03-122">Si vous souhaitez désigner un opérateur, spécifiez la destination des appels à l’opérateur.</span><span class="sxs-lookup"><span data-stu-id="0da03-122">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="0da03-123">Facultatif (mais recommandé).</span><span class="sxs-lookup"><span data-stu-id="0da03-123">This is optional (but recommended).</span></span> <span data-ttu-id="0da03-124">Vous pouvez définir l’option d' **opérateur** permettant aux appelants de sortir des menus et de parler à une personne désignée.</span><span class="sxs-lookup"><span data-stu-id="0da03-124">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="0da03-125">Spécifiez le fuseau horaire pour ce standard automatique.</span><span class="sxs-lookup"><span data-stu-id="0da03-125">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="0da03-126">Le fuseau horaire est utilisé pour calculer les heures d’ouverture, si vous [créez un flux d’appels distinct pendant les heures qui suivent](#call-flow-for-after-hours).</span><span class="sxs-lookup"><span data-stu-id="0da03-126">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="0da03-127">Spécifiez une langue pour ce standard automatique.</span><span class="sxs-lookup"><span data-stu-id="0da03-127">Specify a language for this auto attendant.</span></span> <span data-ttu-id="0da03-128">Il s’agit de la langue qui sera utilisée pour les invites vocales générées par le système.</span><span class="sxs-lookup"><span data-stu-id="0da03-128">This the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="0da03-129">Indiquez si vous voulez activer les entrées vocales.</span><span class="sxs-lookup"><span data-stu-id="0da03-129">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="0da03-130">Lorsque cette option est activée, le nom de chaque option de menu devient un mot clé de reconnaissance vocale.</span><span class="sxs-lookup"><span data-stu-id="0da03-130">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="0da03-131">Par exemple, les appelants peuvent prononcer « un » pour sélectionner l’option de menu mappée à la clé 1, ou dire « ventes » pour sélectionner l’option de menu « ventes ».</span><span class="sxs-lookup"><span data-stu-id="0da03-131">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

6. <span data-ttu-id="0da03-132">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="0da03-132">Click **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="0da03-133">Flux d’appels</span><span class="sxs-lookup"><span data-stu-id="0da03-133">Call flow</span></span>

![](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="0da03-134">Indiquez si vous voulez lire un message d’accueil lorsque le standard automatique répond à un appel.</span><span class="sxs-lookup"><span data-stu-id="0da03-134">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="0da03-135">Si vous sélectionnez **lire un fichier audio** , vous pouvez utiliser le bouton **Télécharger un fichier** pour télécharger un message d’accueil enregistré en tant que fichier audio. WAV,. MP3 ou. Format WMA.</span><span class="sxs-lookup"><span data-stu-id="0da03-135">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="0da03-136">Le nombre d’enregistrements ne peut pas dépasser 5 Mo.</span><span class="sxs-lookup"><span data-stu-id="0da03-136">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="0da03-137">Si vous sélectionnez l’option **taper un message d’accueil** le système lira le texte que vous tapez (jusqu’à 1000 caractères) lorsque le standard automatique répond à un appel.</span><span class="sxs-lookup"><span data-stu-id="0da03-137">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="0da03-138">Choisissez le mode de routage de l’appel.</span><span class="sxs-lookup"><span data-stu-id="0da03-138">Choose how you want to route the call.</span></span>

<span data-ttu-id="0da03-139">Si vous sélectionnez **déconnecter**, le standard automatique raccrochera l’appel.</span><span class="sxs-lookup"><span data-stu-id="0da03-139">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="0da03-140">Si vous sélectionnez **rediriger l’appel**, vous pouvez choisir l’une des destinations de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="0da03-140">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="0da03-141">Si vous sélectionnez les **options de menu lire**, vous pouvez choisir de **lire un fichier audio** ou **de taper un message d’accueil** , puis de choisir entre les options de menu et la recherche dans l’annuaire.</span><span class="sxs-lookup"><span data-stu-id="0da03-141">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="0da03-142">Options de menu</span><span class="sxs-lookup"><span data-stu-id="0da03-142">Menu options</span></span>

![](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="0da03-143">Pour les options de numérotation, vous pouvez affecter les touches 0-9 du clavier du téléphone à l’une des destinations de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="0da03-143">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="0da03-144">(Les clés \* (REPEAT) et \# (retour) sont réservés par le système et ne peuvent pas être réaffectés.)</span><span class="sxs-lookup"><span data-stu-id="0da03-144">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="0da03-145">Les mappages de clés ne doivent pas nécessairement être continus.</span><span class="sxs-lookup"><span data-stu-id="0da03-145">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="0da03-146">Par exemple, il est possible de créer un menu avec les clés 0, 1 et 3 mappées à des options, tandis que la touche 2 n’est pas utilisée.</span><span class="sxs-lookup"><span data-stu-id="0da03-146">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the 2 key isn't used.</span></span>

<span data-ttu-id="0da03-147">Nous vous recommandons de mapper la touche 0 à l’opérateur si vous en avez configuré un.</span><span class="sxs-lookup"><span data-stu-id="0da03-147">We recommend mapping the 0 key to the operator if you have configured one.</span></span> <span data-ttu-id="0da03-148">Si l’opérateur n’est pas défini sur une touche, la commande vocale « opérateur » est également désactivée.</span><span class="sxs-lookup"><span data-stu-id="0da03-148">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span> 

<span data-ttu-id="0da03-149">Pour chaque option de menu, spécifiez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="0da03-149">For each menu option, specify the following:</span></span>

- <span data-ttu-id="0da03-150">**Clé de numérotation** -touche du clavier du téléphone pour accéder à cette option.</span><span class="sxs-lookup"><span data-stu-id="0da03-150">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="0da03-151">Si les entrées vocales sont disponibles, les appelants peuvent également prononcer ce numéro pour accéder à l’option.</span><span class="sxs-lookup"><span data-stu-id="0da03-151">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="0da03-152">**Commande vocale** : définit la commande vocale que l’appelant peut donner pour accéder à cette option, si les entrées vocales sont activées.</span><span class="sxs-lookup"><span data-stu-id="0da03-152">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="0da03-153">Elle peut contenir plusieurs mots tels que « service clientèle » ou « opérations et raisons ».</span><span class="sxs-lookup"><span data-stu-id="0da03-153">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="0da03-154">Par exemple, l’appelant peut appuyer sur 2, prononcer « deux » ou dire « ventes » pour sélectionner l’option associée à la clé 2.</span><span class="sxs-lookup"><span data-stu-id="0da03-154">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the 2 key.</span></span> <span data-ttu-id="0da03-155">Ce texte est également affiché par synthèse vocale pour l’invite de confirmation du service (par exemple, « transfert de votre appel vers les ventes »).</span><span class="sxs-lookup"><span data-stu-id="0da03-155">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="0da03-156">**Rediriger vers** -la destination du routage des appels utilisée lorsque les appelants choisissent cette option.</span><span class="sxs-lookup"><span data-stu-id="0da03-156">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="0da03-157">Si vous redirigez vers une file d’attente d’appels ou de standard automatique, sélectionnez le compte de ressources associé.</span><span class="sxs-lookup"><span data-stu-id="0da03-157">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="0da03-158">Recherche dans l’annuaire</span><span class="sxs-lookup"><span data-stu-id="0da03-158">Directory search</span></span>

<span data-ttu-id="0da03-159">Si vous affectez des clés de numérotation aux destinations, nous vous recommandons de choisir **aucune** pour la recherche dans l' **Annuaire**.</span><span class="sxs-lookup"><span data-stu-id="0da03-159">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="0da03-160">Si un appelant tente de composer un nom ou une extension à l’aide de clés affectées à des destinations spécifiques, il est possible qu’il soit routé de manière inattendue vers une destination avant d’avoir fini d’entrer le nom ou l’extension.</span><span class="sxs-lookup"><span data-stu-id="0da03-160">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="0da03-161">Nous vous recommandons de créer un standard automatique distinct pour la recherche dans l’annuaire et de définir le lien principal de votre standard automatique à l’aide d’une clé de numérotation.</span><span class="sxs-lookup"><span data-stu-id="0da03-161">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="0da03-162">Si vous n’avez pas affecté de touches de numérotation, sélectionnez une option pour la recherche dans l' **Annuaire**.</span><span class="sxs-lookup"><span data-stu-id="0da03-162">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="0da03-163">**Composer par nom** : Si vous activez cette option, les appelants peuvent prononcer le nom de l’utilisateur ou le taper sur le clavier du téléphone.</span><span class="sxs-lookup"><span data-stu-id="0da03-163">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="0da03-164">Tout utilisateur en ligne disposant d’une licence de système téléphonique ou d’un utilisateur hébergé sur site utilisant Skype entreprise Server est éligible et est disponible avec la numérotation par nom.</span><span class="sxs-lookup"><span data-stu-id="0da03-164">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="0da03-165">(Vous pouvez définir qui est et qui n’est pas inclus dans le répertoire de la page de [portée de numérotation](#dial-scope) ).</span><span class="sxs-lookup"><span data-stu-id="0da03-165">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="0da03-166">**Composer par poste** : Si vous activez cette option, les appelants peuvent se connecter aux utilisateurs de votre organisation en composant leur numéro de poste.</span><span class="sxs-lookup"><span data-stu-id="0da03-166">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="0da03-167">Tout utilisateur en ligne disposant d’une licence de système téléphonique ou d’un utilisateur hébergé sur site utilisant Skype entreprise Server est éligible et peut être trouvé avec la **numérotation par poste**.</span><span class="sxs-lookup"><span data-stu-id="0da03-167">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="0da03-168">(Vous pouvez définir qui est et qui n’est pas inclus dans le répertoire de la page de [portée de numérotation](#dial-scope) ).</span><span class="sxs-lookup"><span data-stu-id="0da03-168">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="0da03-169">Les utilisateurs que vous souhaitez rendre disponibles pour composer par poste doivent avoir une extension spécifiée dans le cadre de l’un des attributs de téléphone suivants définis dans Active Directory ou Azure Active Directory (voir [Ajouter des utilisateurs individuellement ou en bloc](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) pour plus d’informations).</span><span class="sxs-lookup"><span data-stu-id="0da03-169">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phone attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="0da03-170">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="0da03-170">OfficePhone</span></span>
- <span data-ttu-id="0da03-171">HomePhone</span><span class="sxs-lookup"><span data-stu-id="0da03-171">HomePhone</span></span>
- <span data-ttu-id="0da03-172">Mobile/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="0da03-172">Mobile/MobilePhone</span></span>
- <span data-ttu-id="0da03-173">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="0da03-173">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="0da03-174">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="0da03-174">OtherTelephone</span></span>

<span data-ttu-id="0da03-175">Le format requis pour entrer une extension dans le champ numéro de téléphone de l’utilisateur est \* + <phone number> ext = <extension> \* ou \* + <phone number> x <extension> \*.</span><span class="sxs-lookup"><span data-stu-id="0da03-175">The required format to enter the extension in the user phone number field is either *+<phone number>ext=<extension>* or *+<phone number>x<extension>*.</span></span>

<span data-ttu-id="0da03-176">Vous pouvez définir l’extension dans le [Centre d’administration Microsoft 365](https://admin.microsoft.com/) ou dans le [Centre d’administration Azure Active Directory](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="0da03-176">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="0da03-177">Il faut parfois jusqu’à 12 heures pour que les modifications soient disponibles aux standards automatiques et aux files d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="0da03-177">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="0da03-178">Si vous voulez utiliser les fonctions **numérotation par nom** et **numéro de poste par numéro** , vous pouvez affecter une touche de numérotation à votre standard automatique principal pour atteindre un standard automatique activé pour la **numérotation par nom**.</span><span class="sxs-lookup"><span data-stu-id="0da03-178">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="0da03-179">Dans ce standard automatique, vous pouvez affecter la touche 1 (qui ne comporte pas de lettres) pour atteindre le standard automatique de **composition par extension** .</span><span class="sxs-lookup"><span data-stu-id="0da03-179">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="0da03-180">Lorsque vous avez sélectionné une option de recherche dans l' **Annuaire** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="0da03-180">Once you have selected a **Directory search** option, click **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="0da03-181">Flux d’appels pour après heures</span><span class="sxs-lookup"><span data-stu-id="0da03-181">Call flow for after hours</span></span>

![](media/auto-attendant-business-hours.png)

<span data-ttu-id="0da03-182">Les heures d’activité peuvent être définies pour chaque standard automatique.</span><span class="sxs-lookup"><span data-stu-id="0da03-182">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="0da03-183">Si ce n'est pas le cas, tous les jours et toutes les heures de la semaine seront considérés comme heures d'ouverture, car une planification 24/24 est définie par défaut.</span><span class="sxs-lookup"><span data-stu-id="0da03-183">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="0da03-184">Les heures d’ouverture peuvent être définies à l’aide de pauses pendant la journée, et toutes les heures qui ne sont pas définies comme heures d’ouverture.</span><span class="sxs-lookup"><span data-stu-id="0da03-184">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="0da03-185">Vous pouvez définir des options de traitement des appels entrantes différentes et des salutations pour une durée de l’heure.</span><span class="sxs-lookup"><span data-stu-id="0da03-185">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="0da03-186">Selon la manière dont vous avez configuré vos standards automatiques et les files d’attente d’appels, il est possible que vous deviez spécifier le routage des appels après-heures pour les standards automatiques avec des numéros de téléphone directs.</span><span class="sxs-lookup"><span data-stu-id="0da03-186">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="0da03-187">Si vous souhaitez un routage des appels distinct pour les appelants après l’heure, spécifiez les heures d’activité pour chaque jour.</span><span class="sxs-lookup"><span data-stu-id="0da03-187">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="0da03-188">Cliquez sur **Ajouter un nouvel horaire** pour spécifier plusieurs jeux d’heures pour un jour donné, par exemple pour spécifier une pause déjeuner.</span><span class="sxs-lookup"><span data-stu-id="0da03-188">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="0da03-189">Une fois que vous avez spécifié les heures d’appel, sélectionnez vos options de routage des appels pour après heures.</span><span class="sxs-lookup"><span data-stu-id="0da03-189">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="0da03-190">Les mêmes options sont disponibles que pour le routage des appels d’heures d’activités que vous avez spécifié ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="0da03-190">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="0da03-191">Lorsque vous avez terminé, cliquez sur **suivant** .</span><span class="sxs-lookup"><span data-stu-id="0da03-191">Click **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="0da03-192">Flux d’appels pendant les vacances</span><span class="sxs-lookup"><span data-stu-id="0da03-192">Call flows during holidays</span></span>

![](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="0da03-193">Le standard automatique peut avoir un flux d’appels pour chaque [jour férié que vous avez configuré](set-up-holidays-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="0da03-193">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="0da03-194">Vous pouvez ajouter jusqu'à 20 congés planifiés pour chaque standard automatique.</span><span class="sxs-lookup"><span data-stu-id="0da03-194">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="0da03-195">Dans la page Paramètres des appels de vacances, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="0da03-195">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="0da03-196">Tapez un nom pour ce paramètre de vacances.</span><span class="sxs-lookup"><span data-stu-id="0da03-196">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="0da03-197">Dans la liste déroulante **jour férié** , choisissez le jour férié que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="0da03-197">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="0da03-198">Choisissez le type d’message d’accueil que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="0da03-198">Choose the type of greeting that you want to use.</span></span>

    ![](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="0da03-199">Choisissez si vous souhaitez vous **déconnecter** ou **Rediriger** l’appel.</span><span class="sxs-lookup"><span data-stu-id="0da03-199">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="0da03-200">Si vous avez choisi de rediriger l’appel, sélectionnez la destination de routage des appels pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="0da03-200">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="0da03-201">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="0da03-201">Click **Save**.</span></span>

![](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="0da03-202">Répétez la procédure selon vos besoins pour chaque jour férié supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="0da03-202">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="0da03-203">Lorsque vous avez ajouté tous vos jours fériés, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="0da03-203">When you've added all your holidays, click **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="0da03-204">Étendue de numérotation</span><span class="sxs-lookup"><span data-stu-id="0da03-204">Dial scope</span></span>

![](media/auto-attendant-dial-scope.png)

<span data-ttu-id="0da03-205">L' *étendue de numérotation* définit les utilisateurs disponibles dans l’annuaire quand un appelant utilise la numérotation par nom ou par numéro de poste par extension.</span><span class="sxs-lookup"><span data-stu-id="0da03-205">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="0da03-206">La valeur par défaut de **tous les utilisateurs en ligne** inclut tous les utilisateurs de votre organisation qui sont des utilisateurs en ligne disposant d’une licence de système téléphonique ou hébergés en local à l’aide de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="0da03-206">The default of **All online users** includes all users in your organization that are Online users with a Phone System license or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="0da03-207">Vous pouvez inclure ou exclure des utilisateurs spécifiques en sélectionnant **groupe d’utilisateurs personnalisé** sous **inclure** ou **exclure** et en choisissant un ou plusieurs groupes Microsoft 365, listes de distribution ou groupes de sécurité.</span><span class="sxs-lookup"><span data-stu-id="0da03-207">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="0da03-208">Par exemple, vous souhaiterez peut-être exclure les dirigeants de votre organisation du répertoire de numérotation.</span><span class="sxs-lookup"><span data-stu-id="0da03-208">For example, you might want to exclude executives in your organization from the dialing directory.</span></span>

> [!NOTE]
> <span data-ttu-id="0da03-209">Le nom d’un nouvel utilisateur peut nécessiter un maximum de 36 heures.</span><span class="sxs-lookup"><span data-stu-id="0da03-209">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="0da03-210">Lorsque vous avez terminé de définir l’étendue de numérotation, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="0da03-210">When you're done setting the dial scope, click **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="0da03-211">Comptes de ressources</span><span class="sxs-lookup"><span data-stu-id="0da03-211">Resource accounts</span></span>

<span data-ttu-id="0da03-212">Tous les standards automatiques doivent disposer d’un compte de ressources associé.</span><span class="sxs-lookup"><span data-stu-id="0da03-212">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="0da03-213">Les standards automatiques de premier niveau ont besoin d’au moins un compte de ressources associé à un numéro de service.</span><span class="sxs-lookup"><span data-stu-id="0da03-213">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="0da03-214">Si vous le souhaitez, vous pouvez affecter plusieurs comptes de ressources à un standard automatique, chacun avec un numéro de service distinct.</span><span class="sxs-lookup"><span data-stu-id="0da03-214">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="0da03-215">Pour ajouter un compte de ressource, cliquez sur **Ajouter un compte** et recherchez le compte que vous voulez ajouter.</span><span class="sxs-lookup"><span data-stu-id="0da03-215">To add a resource account, click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="0da03-216">Cliquez sur **Ajouter**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="0da03-216">Click **Add**, and then click **Add**.</span></span>

![](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="0da03-217">Lorsque vous avez terminé d’ajouter des comptes de service, cliquez sur **valider**.</span><span class="sxs-lookup"><span data-stu-id="0da03-217">When you have finished adding service accounts, click **Submit**.</span></span> <span data-ttu-id="0da03-218">Cela termine la configuration de standard automatique.</span><span class="sxs-lookup"><span data-stu-id="0da03-218">This completes the auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="0da03-219">Transferts de numéros de téléphone externes-détails techniques</span><span class="sxs-lookup"><span data-stu-id="0da03-219">External phone number transfers - technical details</span></span>

<span data-ttu-id="0da03-220">Lorsque vous transférez des appels vers un numéro de téléphone externe, le compte de ressources associé au standard automatique ou à la file d’attente d’appels doit être doté d’un numéro de téléphone et d’un système téléphonique Microsoft 365-licence utilisateur virtuelles.</span><span class="sxs-lookup"><span data-stu-id="0da03-220">When transferring calls to an external phone number, the resource account associated with the auto attendant or call queue must have a phone number and a Microsoft 365 Phone System - Virtual User license.</span></span> <span data-ttu-id="0da03-221">En outre</span><span class="sxs-lookup"><span data-stu-id="0da03-221">Additionally:</span></span>

- <span data-ttu-id="0da03-222">Dans le cas d’un compte de ressources avec un numéro de plan d’appels, attribuez une licence de [plan d’appel](calling-plans-for-office-365.md) .</span><span class="sxs-lookup"><span data-stu-id="0da03-222">For a resource account with a Calling Plan number, assign a [Calling Plan](calling-plans-for-office-365.md) license.</span></span>
- <span data-ttu-id="0da03-223">Dans le cas d’un compte de ressources avec un numéro de routage direct, attribuez une [stratégie de routage vocal en ligne](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0da03-223">For a resource account with a Direct Routing number, assign an [online voice routing policy](manage-voice-routing-policies.md).</span></span>

<span data-ttu-id="0da03-224">Le numéro de téléphone sortant affiché est déterminé comme suit :</span><span class="sxs-lookup"><span data-stu-id="0da03-224">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="0da03-225">Pour les numéros de plan d’appels, le numéro de téléphone de l’appelant initial est affiché.</span><span class="sxs-lookup"><span data-stu-id="0da03-225">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="0da03-226">Pour les numéros de routage directs, le numéro envoyé est basé sur le paramètre P-assertion-Identity (PAI) sur l’SBC, comme suit :</span><span class="sxs-lookup"><span data-stu-id="0da03-226">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="0da03-227">S’il est défini sur Disabled, le numéro de téléphone de l’appelant initial est affiché.</span><span class="sxs-lookup"><span data-stu-id="0da03-227">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="0da03-228">Il s’agit du paramètre par défaut et recommandé.</span><span class="sxs-lookup"><span data-stu-id="0da03-228">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="0da03-229">Si cette option est activée, le numéro de téléphone de votre compte de ressources est affiché.</span><span class="sxs-lookup"><span data-stu-id="0da03-229">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="0da03-230">Les transferts entre les Trunks de plans d’appel et les Trunks de routage direct ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="0da03-230">Transfers between Calling Plan trunks and Direct Routing trunks aren't supported.</span></span>

<span data-ttu-id="0da03-231">Dans un environnement hybride, pour transférer un appel de standard automatique vers le RTC via l’intégration RTC Skype entreprise, créez un nouvel utilisateur local avec le renvoi d’appel défini sur le numéro RTC.</span><span class="sxs-lookup"><span data-stu-id="0da03-231">In a hybrid environment, to transfer an auto attendant call to the PSTN via Skype for Business PSTN integration, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="0da03-232">L’utilisateur doit être activé pour voix entreprise et avoir reçu une stratégie vocale.</span><span class="sxs-lookup"><span data-stu-id="0da03-232">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="0da03-233">Pour en savoir plus, voir [transfert d’appel standard automatique vers PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span><span class="sxs-lookup"><span data-stu-id="0da03-233">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="0da03-234">Créer un standard automatique avec PowerShell</span><span class="sxs-lookup"><span data-stu-id="0da03-234">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="0da03-235">Vous pouvez également utiliser PowerShell pour créer et configurer des standards automatiques.</span><span class="sxs-lookup"><span data-stu-id="0da03-235">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="0da03-236">Voici les applets de passe dont vous avez besoin pour gérer un standard automatique :</span><span class="sxs-lookup"><span data-stu-id="0da03-236">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="0da03-237">Nouveau-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="0da03-237">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="0da03-238">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="0da03-238">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [<span data-ttu-id="0da03-239">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="0da03-239">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant?view=skype-ps)
- [<span data-ttu-id="0da03-240">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="0da03-240">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="0da03-241">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="0da03-241">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [<span data-ttu-id="0da03-242">Nouveau-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="0da03-242">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [<span data-ttu-id="0da03-243">Nouveau-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="0da03-243">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [<span data-ttu-id="0da03-244">Nouveau-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="0da03-244">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [<span data-ttu-id="0da03-245">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="0da03-245">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="0da03-246">Nouvelle CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="0da03-246">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [<span data-ttu-id="0da03-247">Nouvelle CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="0da03-247">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [<span data-ttu-id="0da03-248">Nouvelle CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="0da03-248">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [<span data-ttu-id="0da03-249">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="0da03-249">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="0da03-250">Nouveau-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="0da03-250">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="0da03-251">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="0da03-251">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="0da03-252">Importation-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="0da03-252">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="0da03-253">Nouveau-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="0da03-253">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)


## <a name="related-topics"></a><span data-ttu-id="0da03-254">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="0da03-254">Related topics</span></span>

[<span data-ttu-id="0da03-255">Voici les avantages du système téléphonique</span><span class="sxs-lookup"><span data-stu-id="0da03-255">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="0da03-256">Obtention de numéros de téléphone de service</span><span class="sxs-lookup"><span data-stu-id="0da03-256">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="0da03-257">Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays</span><span class="sxs-lookup"><span data-stu-id="0da03-257">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="0da03-258">Exemple petite entreprise : configurer un standard automatique</span><span class="sxs-lookup"><span data-stu-id="0da03-258">Small business example — Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa) 

[<span data-ttu-id="0da03-259">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="0da03-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

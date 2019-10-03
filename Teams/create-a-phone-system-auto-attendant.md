---
title: Configurer un standard automatique dans le cloud
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Découvrez comment configurer et tester les standards automatiques Cloud de Microsoft Teams.
ms.openlocfilehash: 0cac6b1bb7d19e91e4042bcb0673f6c677e77d2e
ms.sourcegitcommit: 2d31209aae9e0171693389db97b0b5c974864673
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2019
ms.locfileid: "37375708"
---
# <a name="set-up-a-cloud-auto-attendant"></a><span data-ttu-id="26c9a-103">Configurer un standard automatique dans le cloud</span><span class="sxs-lookup"><span data-stu-id="26c9a-103">Set up a Cloud auto attendant</span></span>

<span data-ttu-id="26c9a-104">Les standards automatiques permettent aux personnes qui rejoignent votre organisation d’appeler votre organisation et de naviguer dans un système de menu pour les faire passer au service approprié, à la file d’attente des appels, à la personne ou à l’opérateur.</span><span class="sxs-lookup"><span data-stu-id="26c9a-104">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="26c9a-105">Vous pouvez créer un standard automatique pour votre organisation à l’aide du centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="26c9a-105">You can create an auto attendant for your organization by using the Microsoft Teams admin center.</span></span> <span data-ttu-id="26c9a-106">Pour créer un standard automatique, dans la barre de navigation gauche, sélectionnez **voix** , puis cliquez sur **standards** > automatiques**Ajouter nouveau**.</span><span class="sxs-lookup"><span data-stu-id="26c9a-106">To create a new auto attendant, go to **Voice** in the left navigation, and then select **Auto attendants** > **Add new**.</span></span>

<span data-ttu-id="26c9a-107">Pour en savoir plus sur les standards automatiques, reportez-vous à la rubrique [qu’est-ce que les standards automatiques Cloud ?](/microsoftteams/what-are-phone-system-auto-attendants)</span><span class="sxs-lookup"><span data-stu-id="26c9a-107">If you want to learn more about auto attendants, see [What are Cloud auto attendants?](/microsoftteams/what-are-phone-system-auto-attendants)</span></span>

> [!NOTE]
> <span data-ttu-id="26c9a-108">Cet article s’applique à Microsoft teams et à Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="26c9a-108">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="26c9a-109">Étape 1 : prendre en main</span><span class="sxs-lookup"><span data-stu-id="26c9a-109">Step 1 — Get started</span></span>

- <span data-ttu-id="26c9a-110">Un standard automatique est requis pour disposer d’un compte de ressources associé.</span><span class="sxs-lookup"><span data-stu-id="26c9a-110">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="26c9a-111">Pour plus d’informations sur les comptes de ressources et toutes les licences requises, voir [gérer les comptes de ressources dans teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="26c9a-111">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts and all licenses required.</span></span>

> [!TIP]
> <span data-ttu-id="26c9a-112">Pour rediriger les appels vers un opérateur ou une option de menu qui est un utilisateur en ligne disposant d’une licence de **système téléphonique** , vous devez l’activer pour Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="26c9a-112">To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice.</span></span> <span data-ttu-id="26c9a-113">Consultez la rubrique [affectation de licences Skype entreprise](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) ou [affectation de licences Microsoft teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="26c9a-113">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="26c9a-114">Vous pouvez aussi utiliser Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26c9a-114">You can also use Windows PowerShell.</span></span> <span data-ttu-id="26c9a-115">Par exemple, exécutez :`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="26c9a-115">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

## <a name="step-2--create-a-new-auto-attendant"></a><span data-ttu-id="26c9a-116">Étape 2 : créer un standard automatique</span><span class="sxs-lookup"><span data-stu-id="26c9a-116">Step 2 — Create a new auto attendant</span></span>

> [!IMPORTANT]
> <span data-ttu-id="26c9a-117">Chaque standard automatique doit disposer d’un compte de [ressources](manage-resource-accounts.md)associé.</span><span class="sxs-lookup"><span data-stu-id="26c9a-117">Every auto attendant is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="26c9a-118">Vous devez d’abord créer le compte de ressources, puis vous pouvez l’associer au standard automatique.</span><span class="sxs-lookup"><span data-stu-id="26c9a-118">You must create the resource account first, then you can associate it to the auto attendant.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="26c9a-119">Utilisation du centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="26c9a-119">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="26c9a-120">Dans le **Centre d’administration de Microsoft teams**, cliquez sur**standards automatiques** **vocaux** > , puis sur **+ nouveau**:</span><span class="sxs-lookup"><span data-stu-id="26c9a-120">In the **Microsoft Teams admin center**, click   **Voice** > **Auto attendants**, then click **+ New**:</span></span>

#### <a name="general-info-page"></a><span data-ttu-id="26c9a-121">Page informations générales</span><span class="sxs-lookup"><span data-stu-id="26c9a-121">General info page</span></span>

![Capture d’écran de la page mon standard automatique](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![Icône du numéro 1 qui référence une légende dans la capture d’écran précédente](media/sfbcallout1.png)

<span data-ttu-id="26c9a-124">**Nom** Entrez un nom descriptif pour le standard automatique.</span><span class="sxs-lookup"><span data-stu-id="26c9a-124">**Name** Enter a descriptive display name for your auto attendant.</span></span> <span data-ttu-id="26c9a-125">Le nom est obligatoire et peut contenir jusqu'à 64 caractères, espaces compris.</span><span class="sxs-lookup"><span data-stu-id="26c9a-125">The name is required and can contain up to 64 characters, including spaces.</span></span> <span data-ttu-id="26c9a-126">Elle apparaît dans la colonne **nom** de l’onglet **standards automatiques** .</span><span class="sxs-lookup"><span data-stu-id="26c9a-126">It is listed in the **Name** column on the **Auto attendants** tab.</span></span>

* * *

![Icône du numéro 2 qui référence une légende dans la capture d’écran précédente](media/sfbcallout2.png)

<span data-ttu-id="26c9a-128"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="26c9a-128"></span></span>

<span data-ttu-id="26c9a-129">**Compte de ressources** Cliquez sur ce bouton pour sélectionner un ou plusieurs comptes de ressources pour vous connecter à votre nouveau standard automatique.</span><span class="sxs-lookup"><span data-stu-id="26c9a-129">**Resource account** Click this button to select one or more resource accounts to connect to your new auto attendant.</span></span> <span data-ttu-id="26c9a-130">Tous les standards automatiques doivent disposer d’un compte de ressources associé.</span><span class="sxs-lookup"><span data-stu-id="26c9a-130">All auto attendants are required to have an associated resource account.</span></span> <span data-ttu-id="26c9a-131">Un compte de ressource peut avoir un numéro de téléphone associé au compte, mais aucun numéro de téléphone n’est requis.</span><span class="sxs-lookup"><span data-stu-id="26c9a-131">A resource account can have a phone number associated to the account, but a phone number isn't a requirement.</span></span> <span data-ttu-id="26c9a-132">En règle générale, un standard automatique de niveau supérieur dispose d’un compte de ressources avec un numéro de téléphone, mais il est possible que le standard automatique qui se connecte au premier niveau ne dispose pas d’un numéro de téléphone attribué à son compte de ressources.</span><span class="sxs-lookup"><span data-stu-id="26c9a-132">A top-level auto attendant usually has a resource account with an assigned phone number, but nested auto attendant (used as a level 2 menu that the first-level auto attendant connects to) might not have a phone number assigned to its resource account.</span></span>

* * *

<span data-ttu-id="26c9a-133">![Icône du numéro 3 qui référence une légende dans la capture d’écran](media/sfbcallout3.png)
 <a name="timezone"> </a> précédente</span><span class="sxs-lookup"><span data-stu-id="26c9a-133">![Icon of the number 3, referencing a callout in the previous screenshot](media/sfbcallout3.png)
<a name="timezone"> </a></span></span>

<span data-ttu-id="26c9a-134">**Fuseau horaire** Vous devez définir le fuseau horaire pour votre standard automatique, mais il ne doit pas nécessairement correspondre à celui de l'adresse principale de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="26c9a-134">**Time zone** You must set the time zone for your auto attendant, but it doesn't need to correspond to the time zone of the main address listed for your organization.</span></span> <span data-ttu-id="26c9a-135">Chaque standard automatique peut avoir un fuseau horaire différent et les heures d’ouverture définies pour le standard automatique sont définies en fonction du fuseau horaire que vous sélectionnez ici.</span><span class="sxs-lookup"><span data-stu-id="26c9a-135">Each auto attendant can have a different time zone, and the business hours set for the auto attendant are set based on the time zone that you select here.</span></span>

* * *

![Icône du numéro 4, référençant une légende dans la capture d’écran précédente](media/sfbcallout4.png)

<span data-ttu-id="26c9a-137"><a name="language"> </a></span><span class="sxs-lookup"><span data-stu-id="26c9a-137"></span></span>

<span data-ttu-id="26c9a-138">**Langue** Sélectionnez la langue que vous souhaitez utiliser pour votre standard automatique parmi les langues disponibles répertoriées.</span><span class="sxs-lookup"><span data-stu-id="26c9a-138">**Language** Select the language that you want to use for your auto attendant from any of the available languages listed.</span></span> <span data-ttu-id="26c9a-139">La langue que vous définissez ici correspond à la langue utilisée par le standard automatique pour interagir avec les personnes qui rejoignent le standard automatique et toutes les invites système sont exécutées dans cette langue.</span><span class="sxs-lookup"><span data-stu-id="26c9a-139">The language you set here is the language that the auto attendant uses to interact with people that call in to this auto attendant, and all the system prompts are played in this language.</span></span>

* * *

![Icône du numéro 5 qui référence une légende dans la capture d’écran précédente](media/sfbcallout5.png)

<span data-ttu-id="26c9a-141"><a name="operator"> </a></span><span class="sxs-lookup"><span data-stu-id="26c9a-141"></span></span>

<span data-ttu-id="26c9a-142">**Opérateur** Facultatif, mais vous pouvez définir l’option d' **opérateur** permettant aux appelants de sortir des menus et de parler à une personne.</span><span class="sxs-lookup"><span data-stu-id="26c9a-142">**Operator** This is optional, but you can set the **Operator** option to allow callers to break out of the menus and speak to a person.</span></span>

<span data-ttu-id="26c9a-143">La touche 0 est affectée à l’opérateur par défaut.</span><span class="sxs-lookup"><span data-stu-id="26c9a-143">The 0 key is assigned to Operator by default.</span></span>

<span data-ttu-id="26c9a-144">Si vous définissez un opérateur, vous devez également indiquer aux personnes qui vous appellent à propos de l’option dans les **Options du menu Édition** de la page **gestion des appels d’heures d’entreprise** .</span><span class="sxs-lookup"><span data-stu-id="26c9a-144">If you set an Operator, you will also need to tell people who call about the option in the **Edit menu options** on the **Business hours call handling** page.</span></span> <span data-ttu-id="26c9a-145">Si vous définissez un opérateur sur votre standard automatique, vous devez entrer le texte d’invite correspondant dans la zone les **appelants entendent** ou changer votre fichier audio pour inclure cette option.</span><span class="sxs-lookup"><span data-stu-id="26c9a-145">If you set an operator on your auto attendant, you need to enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option.</span></span> <span data-ttu-id="26c9a-146">Par exemple, « pour l’opérateur, appuyez sur zéro. »</span><span class="sxs-lookup"><span data-stu-id="26c9a-146">For example, "For the Operator, press zero."</span></span>

<span data-ttu-id="26c9a-147">Vous pouvez définir l’opérateur de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="26c9a-147">You have several ways to set the Operator:</span></span>

- <span data-ttu-id="26c9a-148">**Personne de votre société** avec une licence de **Système téléphonique** qui est activée pour Enterprise Voice ou affectée Plans de l’appel dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="26c9a-148">**Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span>

     > [!Note]
     > <span data-ttu-id="26c9a-149">**Une Personne dans votre entreprise** peut être un utilisateur en ligne ou un utilisateur hébergé sur site à l’aide de Skype Professionnel Server 2015 ou Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="26c9a-149">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

- <span data-ttu-id="26c9a-150">**Application vocale** Sélectionnez le nom d’un compte de ressources associé à une file d’attente d’appels ou à un standard automatique que vous avez déjà créé.</span><span class="sxs-lookup"><span data-stu-id="26c9a-150">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>
- <span data-ttu-id="26c9a-151">Vous pouvez la configurer de manière à ce que la personne qui appelle envoie la boîte vocale.</span><span class="sxs-lookup"><span data-stu-id="26c9a-151">You can set it up so the person calling is sent to voicemail.</span></span> <span data-ttu-id="26c9a-152">Pour cela, sélectionnez une **personne au sein de votre entreprise** et configurez les appels de cette personne pour qu’elle soit transférée directement vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="26c9a-152">To do this, select **Person in your company** and set this person's calls to be forwarded directly to voicemail.</span></span>

* * *

![Icône du numéro 6 qui référence une légende dans la capture d’écran précédente](media/sfbcallout6.png)

<span data-ttu-id="26c9a-154">**Activer les entrées vocales** La reconnaissance vocale est disponible si cette option est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="26c9a-154">**Enable voice inputs** Speech recognition is available if this option is selected.</span></span> <span data-ttu-id="26c9a-155">Les personnes qui appellent dans peuvent utiliser la saisie vocale dans la [langue que vous avez définie](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="26c9a-155">People that call in can use voice input in the  [language you set](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span> <span data-ttu-id="26c9a-156">Si vous souhaitez uniquement permettre aux utilisateurs d’utiliser leur clavier téléphonique, vous pouvez désactiver la reconnaissance vocale en le définissant sur désactivé.</span><span class="sxs-lookup"><span data-stu-id="26c9a-156">If you want to only let people use their phone keypad, you can disable speech recognition by setting it to off.</span></span>

* * *

<span data-ttu-id="26c9a-157">Lorsque vous avez terminé vos sélections, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="26c9a-157">When you are finished with your selections, click **Next**.</span></span>

#### <a name="business-hours-page"></a><span data-ttu-id="26c9a-158">Page heures de bureau</span><span class="sxs-lookup"><span data-stu-id="26c9a-158">Business hours page</span></span>

<span data-ttu-id="26c9a-159">Par défaut, les heures d’activité sont définies sur 9:00 AM à 5:00 PM, du lundi au vendredi.</span><span class="sxs-lookup"><span data-stu-id="26c9a-159">By default, business hours are set to 9:00 am to 5:00 pm, Monday through Friday.</span></span> <span data-ttu-id="26c9a-160">Toutes les heures qui ne sont pas incluses dans les heures d’activité sont prises en compte après les heures d’activité.</span><span class="sxs-lookup"><span data-stu-id="26c9a-160">All hours that aren't included in business hours are considered after business hours.</span></span> <span data-ttu-id="26c9a-161">Vous pouvez cliquer sur **sélectionner 24/7** pour passer toutes les heures d’activité.</span><span class="sxs-lookup"><span data-stu-id="26c9a-161">You can click **Select 24/7** to make all hours business hours.</span></span> <span data-ttu-id="26c9a-162">Si vous ne sélectionnez pas l’option **Sélectionner une 24/7** , la page des **paramètres d’appel après heures** est utilisée pour configurer les règles de gestion des appels à partir de heures d’utilisation normales pour le standard automatique.</span><span class="sxs-lookup"><span data-stu-id="26c9a-162">Unless you select the **Select 24/7** option, the **After hours call settings** page will be used to configure the call handling rules for after business hours for the auto attendant.</span></span>

![Capture d’écran de la page des heures de bureau](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![Icône du numéro 1 qui référence une légende dans la capture d’écran précédente](media/sfbcallout1.png)

<span data-ttu-id="26c9a-165">Par défaut, les heures d’activité sont définies comme du lundi au vendredi, 9:00 AM-5:00 pm.</span><span class="sxs-lookup"><span data-stu-id="26c9a-165">By default, business hours are set to Monday to Friday, 9:00 am-5:00 pm.</span></span> <span data-ttu-id="26c9a-166">Sélectionnez l’option **effacer toutes les heures** pour désélectionner toutes les heures dans le planning.</span><span class="sxs-lookup"><span data-stu-id="26c9a-166">Select **Clear all hours** option to unselect all hours in the schedule.</span></span> <span data-ttu-id="26c9a-167">Lorsque vous sélectionnez **rétablir les valeurs par défaut**, les heures d’ouverture sont réinitialisées du lundi au vendredi, 9:00 am-5:00 pm.</span><span class="sxs-lookup"><span data-stu-id="26c9a-167">When you select **Reset to default**, business hours are reset to Monday to Friday, 9:00 am-5:00 pm.</span></span>

* * *

![Icône du numéro 2 qui référence une légende dans la capture d’écran précédente](media/sfbcallout2.png)

<span data-ttu-id="26c9a-169">Pour modifier les heures d’activité, sélectionnez les heures d’activité que vous voulez définir dans le calendrier.</span><span class="sxs-lookup"><span data-stu-id="26c9a-169">To change business hours, highlight the business hours you want to set in the calendar.</span></span> <span data-ttu-id="26c9a-170">Le calendrier vous permet de sélectionner des heures d’ouverture par intervalle de 30 minutes, et les heures d’ouverture de votre choix sont basées sur le fuseau horaire que vous avez défini dans la page **informations générales** .</span><span class="sxs-lookup"><span data-stu-id="26c9a-170">The calendar allows you to select business hours in 30-minute intervals, and the business hours you select here are based on the time zone that you set on the **General info** page.</span></span> <span data-ttu-id="26c9a-171">Pour configurer une coupure (pour le déjeuner, par exemple), désélectionnez ou faites glisser pour désélectionner l'heure dans le calendrier.</span><span class="sxs-lookup"><span data-stu-id="26c9a-171">To set up a break (a lunch break, for example), deselect or drag to deselect the time on the calendar.</span></span> <span data-ttu-id="26c9a-172">Vous pouvez définir plusieurs sauts dans les heures de bureau.</span><span class="sxs-lookup"><span data-stu-id="26c9a-172">You can set multiple breaks within business hours.</span></span>

* * *

<span data-ttu-id="26c9a-173">Lorsque vous avez terminé vos sélections, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="26c9a-173">When you are finished with your selections, click **Next**.</span></span>

#### <a name="business-hours-call-settings"></a><span data-ttu-id="26c9a-174">Paramètres d’appel d’heures d’activité</span><span class="sxs-lookup"><span data-stu-id="26c9a-174">Business hours call settings</span></span>

> [!TIP]
> <span data-ttu-id="26c9a-175">Si vous utilisez un planning personnalisé d’heures de travail, vous devez également configurer le suivi des appels après les heures d’activité à l’aide de la page de **traitement des appels après** les heures d’appel, qui vous offre les mêmes options que les **paramètres d’appel d’heures de travail**.</span><span class="sxs-lookup"><span data-stu-id="26c9a-175">If you use a custom business hours schedule, you will also need to set up call handing for after business hours using the **After hours call handling** page, which will give you the same options as **Business hours call settings**.</span></span>

<span data-ttu-id="26c9a-176">Vous pouvez configurer des messages d’accueil, des messages d’accueil et des menus que les utilisateurs entendent lors de leur appel au numéro de téléphone lié au standard automatique de votre organisation pendant les heures d’ouverture.</span><span class="sxs-lookup"><span data-stu-id="26c9a-176">You can set up greetings, prompts, and menus that people hear when they call to the phone number linked to your organization's auto attendant during business hours.</span></span>

<span data-ttu-id="26c9a-177">![Capture d’écran de la section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![d’accueil de la page de gestion des appels en heures d’activité](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span><span class="sxs-lookup"><span data-stu-id="26c9a-177">![Screenshot of the Business hours call handling page Greeting section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![Screenshot of the Business hours call handling page Actions section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span></span>

* * *

![Icône du numéro 1 qui référence une légende dans la capture d’écran précédente](media/sfbcallout1.png)

<span data-ttu-id="26c9a-179"><a name="greetingsandrouting"> </a></span><span class="sxs-lookup"><span data-stu-id="26c9a-179"></span></span>

<span data-ttu-id="26c9a-180">**Message d’accueil** Un message d’accueil d’heures d’entreprise est facultatif et **ne peut pas**être défini pour le message d’accueil.</span><span class="sxs-lookup"><span data-stu-id="26c9a-180">**Greeting** A business hours greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="26c9a-181">Dans ce cas, l’appelant n’entend aucun message ni message d’accueil avant que l’appel ne soit géré par l’une des actions que vous sélectionnez.</span><span class="sxs-lookup"><span data-stu-id="26c9a-181">In this case, the caller won't hear a message or greeting before the call is handled by one of the actions you select.</span></span> <span data-ttu-id="26c9a-182">Vous pouvez également charger un fichier audio (au format .wav, mp3 ou .wma), ou créer un messager d'accueil personnalisé à l'aide de la synthèse vocale.</span><span class="sxs-lookup"><span data-stu-id="26c9a-182">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>
- <span data-ttu-id="26c9a-183">**Télécharger un fichier audio** Si vous choisissez cette fonction, enregistrez le message d’accueil, puis téléchargez votre fichier audio (au format. wav,. mp3 ou. WMA).</span><span class="sxs-lookup"><span data-stu-id="26c9a-183">**Upload an audio file** If you choose this, record the greeting and then upload your audio file (in a .wav, .mp3 or .wma format).</span></span>
- <span data-ttu-id="26c9a-184">**Taper un message d’accueil** Si vous choisissez cette option, entrez le texte que le système doit lire (jusqu’à 1000 caractères).</span><span class="sxs-lookup"><span data-stu-id="26c9a-184">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="26c9a-185">Par exemple, vous pouvez entrer «Bienvenue dans contoso.</span><span class="sxs-lookup"><span data-stu-id="26c9a-185">For example, you might enter "Welcome to Contoso.</span></span> <span data-ttu-id="26c9a-186">Votre appel est important pour nous.</span><span class="sxs-lookup"><span data-stu-id="26c9a-186">Your call is important to us."</span></span> <span data-ttu-id="26c9a-187">dans la zone les **appelants entendent** .</span><span class="sxs-lookup"><span data-stu-id="26c9a-187">in the **Callers will hear** box.</span></span>

* * *

![Icône du numéro 2 qui référence une légende dans la capture d’écran précédente](media/sfbcallout2.png)

<span data-ttu-id="26c9a-189">Vous pouvez sélectionner ce qu’il advient des appels en temps réel.</span><span class="sxs-lookup"><span data-stu-id="26c9a-189">You can select what happens to calls that arrive during business hours.</span></span> <span data-ttu-id="26c9a-190">Vous pouvez choisir l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="26c9a-190">You can chose from the following actions:</span></span>

<span data-ttu-id="26c9a-191"><a name="redirectcalls"> </a></span><span class="sxs-lookup"><span data-stu-id="26c9a-191"></span></span>

- <span data-ttu-id="26c9a-192">Se **déconnecter** Si vous sélectionnez cette option, l’appelant sera déconnecté après avoir écouté un message d’accueil d’heures d’affaires.</span><span class="sxs-lookup"><span data-stu-id="26c9a-192">**Disconnect** If you select it, the person calling in will be disconnected after hearing a business hours greeting.</span></span>
- <span data-ttu-id="26c9a-193">**Rediriger un appel** Cela peut servir à envoyer automatiquement l’appel vers :</span><span class="sxs-lookup"><span data-stu-id="26c9a-193">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="26c9a-194">**Personne de la société** disposant d’une licence de **système téléphonique** activée pour les offres d’appels voix entreprise ou affectées dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="26c9a-194">**Person in company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="26c9a-195">Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="26c9a-195">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="26c9a-196">Pour cela, sélectionnez une **personne dans la société** et configurez cette personne de sorte que les appels soient transférés directement à la boîte vocale.</span><span class="sxs-lookup"><span data-stu-id="26c9a-196">To do this, select **Person in company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="26c9a-197">Une **personne de la société** peut être un utilisateur en ligne ou un utilisateur hébergé sur site utilisant Skype entreprise Server 2015 ou Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="26c9a-197">**Person in company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="26c9a-198">Un autre **standard automatique**</span><span class="sxs-lookup"><span data-stu-id="26c9a-198">Another **Auto attendant**</span></span>

   <span data-ttu-id="26c9a-199">Vous pouvez utiliser un standard automatique existant pour créer un deuxième niveau d’options de menu contenant un sous-menu.</span><span class="sxs-lookup"><span data-stu-id="26c9a-199">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="26c9a-200">Il s’agit des standards automatiques imbriqués.</span><span class="sxs-lookup"><span data-stu-id="26c9a-200">These are called nested auto attendants.</span></span> <span data-ttu-id="26c9a-201">Pour envoyer l’appel à un standard automatique imbriqué, sélectionnez une **personne dans la société** et attribuez un compte de ressource, qui est déjà associé à un standard automatique ou que vous voulez associer à un standard automatique une fois que vous avez créé ce standard automatique.</span><span class="sxs-lookup"><span data-stu-id="26c9a-201">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

- <span data-ttu-id="26c9a-202">Vous pouvez également utiliser les **options de menu lire** pour vous permettre de configurer une invite à lire.</span><span class="sxs-lookup"><span data-stu-id="26c9a-202">**Play menu options** can also be used to let you set up a prompt you want played.</span></span>

* * *

![Icône du numéro 3 qui référence une légende dans la capture d’écran précédente](media/sfbcallout3.png)

<span data-ttu-id="26c9a-204">**Invite de menu** Pour créer une invite de menu principale, vous pouvez utiliser la synthèse vocale ou charger un fichier audio (.wav, .mp3 ou .wma).</span><span class="sxs-lookup"><span data-stu-id="26c9a-204">**Menu prompt** To create main menu prompt, you can either use Text-to-Speech or upload an audio file (.wav, .mp3 or .wma).</span></span> <span data-ttu-id="26c9a-205">Vous pouvez taper l’invite dans la zone **Définissez votre navigation pour les appelants** ou enregistrez un fichier audio et dites, par exemple : «pour les ventes, Say ou appuyer sur 1.</span><span class="sxs-lookup"><span data-stu-id="26c9a-205">You can type the prompt in the **Set your menu navigation for callers** box or record an audio file and say, for example: "For Sales, say or press or say 1.</span></span> <span data-ttu-id="26c9a-206">Pour contacter le département des Services, dites 2 ou appuyez sur 2.</span><span class="sxs-lookup"><span data-stu-id="26c9a-206">For Services, press or say 2.</span></span> <span data-ttu-id="26c9a-207">Pour contacter le service clientèle, dites 3 ou appuyez sur 3.</span><span class="sxs-lookup"><span data-stu-id="26c9a-207">For Customer Support, press or say 3.</span></span> <span data-ttu-id="26c9a-208">Pour contacter l'opérateur, dites 0 ou appuyez sur 0.</span><span class="sxs-lookup"><span data-stu-id="26c9a-208">For the operator, press or say 0.</span></span> <span data-ttu-id="26c9a-209">Pour réécouter ce menu, appuyez sur étoile ou dites répéter.</span><span class="sxs-lookup"><span data-stu-id="26c9a-209">To hear this menu again, press the star key or say repeat."</span></span> <span data-ttu-id="26c9a-210">**Taper un message d’accueil** Si vous avez choisi cette méthode, vous devez entrer le texte que le système devra lire (jusqu’à 1000 caractères).</span><span class="sxs-lookup"><span data-stu-id="26c9a-210">**Type a greeting message** If you chose this, you should enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="26c9a-211">**Charger un fichier audio** Si vous choisissez cette option, vous devrez enregistrer le message d'accueil puis charger votre fichier audio (au format .wav, .mp3 ou .wma).</span><span class="sxs-lookup"><span data-stu-id="26c9a-211">**Upload an audio file** If you chose this, you will need to record the greeting and then upload your audio file (in a .wav, mp3 or .wma format).</span></span>

* * *

![Icône du numéro 4, référençant une légende dans la capture d’écran précédente](media/sfbcallout4.png)

<span data-ttu-id="26c9a-213">**Configuration des options de menu** Il est possible d’ajouter ou de supprimer des options de menu à l’aide de boutons clés sur le clavier.</span><span class="sxs-lookup"><span data-stu-id="26c9a-213">**Menu options setup** Menu options using key buttons on the keypad can be added or removed.</span></span> <span data-ttu-id="26c9a-214">Pour ajouter une option de menu, appuyez sur **+ affecter une touche de numérotation**.</span><span class="sxs-lookup"><span data-stu-id="26c9a-214">To add a menu option, press **+ Assign a dial key**.</span></span> <span data-ttu-id="26c9a-215">Une ligne d’options correspondante apparaît en dessous.</span><span class="sxs-lookup"><span data-stu-id="26c9a-215">A corresponding row of options will appear below.</span></span> <span data-ttu-id="26c9a-216">Pour supprimer une option de menu, il vous suffit de cliquer à gauche de la touche correspondante dans le contrôle clavier et de cliquer sur l’icône de suppression située au-dessus.</span><span class="sxs-lookup"><span data-stu-id="26c9a-216">To delete a menu option, simply click to the left of the corresponding key on the keypad control and click on the delete icon above.</span></span> <span data-ttu-id="26c9a-217">La ligne de mappage clé sera supprimée.</span><span class="sxs-lookup"><span data-stu-id="26c9a-217">The key mapping row will be removed.</span></span>

> [!TIP]
> <span data-ttu-id="26c9a-218">Vous devrez mettre à jour le texte des invites de menus ou réenregistrer l’audio séparément lors de l’ajout à la suppression d’options, car il n’est pas exécuté automatiquement pour l’invite de menu existante.</span><span class="sxs-lookup"><span data-stu-id="26c9a-218">You will have to update menu prompts text or re-record the audio separately when adding to removing options because it won't be automatically done for the existing menu prompt.</span></span>  
>
><span data-ttu-id="26c9a-219">Toutes les options de menu peuvent être ajoutées et supprimées dans n’importe quel ordre, et les mappages de clés ne doivent pas nécessairement être continus.</span><span class="sxs-lookup"><span data-stu-id="26c9a-219">Any menu option can be added and removed in any order, and the key mappings don't have to be continuous.</span></span> <span data-ttu-id="26c9a-220">Par exemple, il est possible de créer un menu avec les clés 0, 1 et 3 mappées à des options, tandis que la clé 2 n’est pas utilisée.</span><span class="sxs-lookup"><span data-stu-id="26c9a-220">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="26c9a-221">Les clés \* (répétition) et \# (retour) sont réservées par le système et ne peuvent pas être réaffectées.</span><span class="sxs-lookup"><span data-stu-id="26c9a-221">The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.</span></span> <span data-ttu-id="26c9a-222">Si la reconnaissance vocale est activée, le fait d’appuyer sur \* correspond à « répéter » et # correspond aux commandes vocales « retour ».</span><span class="sxs-lookup"><span data-stu-id="26c9a-222">If speech recognition is enabled, pressing \* will correspond with "Repeat" and # will correspond with the "Back" voice commands.</span></span>

<span data-ttu-id="26c9a-223">Pour configurer vos options de menu, après avoir sélectionné la ou les touches de numérotation, vous devrez :</span><span class="sxs-lookup"><span data-stu-id="26c9a-223">To set up your menu options, after you select the dial key(s), you will need to:</span></span>

- <span data-ttu-id="26c9a-224">Entrez la **commande vocale** de l’option.</span><span class="sxs-lookup"><span data-stu-id="26c9a-224">Enter the **Voice command**  of the option.</span></span> <span data-ttu-id="26c9a-225">Il peut y avoir un maximum de 64 caractères et contenir plusieurs mots tels que « service clientèle » ou « opérations et raisons ».</span><span class="sxs-lookup"><span data-stu-id="26c9a-225">This can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="26c9a-226">Si la reconnaissance vocale est activée, le nom sera automatiquement reconnu et la personne qui appelle pourra soit appuyez sur 3, par exemple « 3 », ou dire « Service clientèle » pour sélectionner l’option mappée à la clé 3.</span><span class="sxs-lookup"><span data-stu-id="26c9a-226">If speech recognition is enabled, the name will automatically be recognized, and the person calling in will be able to either press 3, say "three," or say "Customer Service" to select the option mapped to key 3.</span></span>
- <span data-ttu-id="26c9a-227">Sélectionner l’endroit où l’appel doit être envoyé si la touche correspondante est enfoncée ou si l’option est sélectionnée à l’aide de la reconnaissance vocale.</span><span class="sxs-lookup"><span data-stu-id="26c9a-227">Select where the call is to be sent if the corresponding key is pressed, or the option is selected using speech recognition.</span></span> <span data-ttu-id="26c9a-228">L’appel peut être envoyé à :</span><span class="sxs-lookup"><span data-stu-id="26c9a-228">The call can be sent to:</span></span>

  - <span data-ttu-id="26c9a-229">**Opérateur** Si l’opérateur a déjà été configuré, il est automatiquement mappé à la clé de 0, mais il peut également être supprimé ou réaffecté à une autre clé.</span><span class="sxs-lookup"><span data-stu-id="26c9a-229">**Operator** If operator is already set up, it is automatically mapped to key 0, but it can also be deleted or reassigned to a different key.</span></span> <span data-ttu-id="26c9a-230">Si l’opérateur n’est pas défini sur n’importe quelle touche, alors la commande vocale « Opérateur » sera désactivée aussi.</span><span class="sxs-lookup"><span data-stu-id="26c9a-230">If operator isn't set to any key, then the voice command "Operator" will be disabled too.</span></span>
  - <span data-ttu-id="26c9a-231">**Une Personne de votre société** avec une licence de **Système téléphonique** qui est activée pour Voix de l'Entreprise ou affectée à un Plan d’appel dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="26c9a-231">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned an Calling Plan in Office 365.</span></span> <span data-ttu-id="26c9a-232">Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="26c9a-232">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="26c9a-233">Pour cela, sélectionnez une **personne au sein de votre entreprise** et configurez cette personne pour que les appels soient transférés directement à la boîte vocale.</span><span class="sxs-lookup"><span data-stu-id="26c9a-233">To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="26c9a-234">Une **personne de votre entreprise** peut être un utilisateur en ligne ou un utilisateur hébergé sur site utilisant Skype entreprise Server ou Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="26c9a-234">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server or Lync Server 2013.</span></span>

  - <span data-ttu-id="26c9a-235">Un autre **standard automatique**</span><span class="sxs-lookup"><span data-stu-id="26c9a-235">Another **Auto attendant**</span></span>

       <span data-ttu-id="26c9a-236">Vous pouvez utiliser un standard automatique existant pour créer un deuxième niveau d’options de menu contenant un sous-menu.</span><span class="sxs-lookup"><span data-stu-id="26c9a-236">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="26c9a-237">Il s’agit des standards automatiques imbriqués.</span><span class="sxs-lookup"><span data-stu-id="26c9a-237">These are called nested auto attendants.</span></span> <span data-ttu-id="26c9a-238">Pour envoyer l’appel à un standard automatique imbriqué, sélectionnez une **personne dans la société** et attribuez un compte de ressource, qui est déjà associé à un standard automatique ou que vous voulez associer à un standard automatique une fois que vous avez créé ce standard automatique.</span><span class="sxs-lookup"><span data-stu-id="26c9a-238">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

        > [!Note]
        > The **Business Hours** of nested (or second-level) auto attendants will also be used, including for the calls sent from other auto attendants that have been set up.

    - <span data-ttu-id="26c9a-239">**Application vocale** Sélectionnez le nom d’un compte de ressources associé à une file d’attente d’appels ou à un standard automatique que vous avez déjà créé.</span><span class="sxs-lookup"><span data-stu-id="26c9a-239">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

![Icône du numéro 5 qui référence une légende dans la capture d’écran précédente](media/sfbcallout5.png)

<span data-ttu-id="26c9a-241">**Numérotation par nom** Si vous choisissez cette option, les utilisateurs qui se connectent pour rechercher des personnes dans votre organisation doivent effectuer une recherche dans l’annuaire.</span><span class="sxs-lookup"><span data-stu-id="26c9a-241">**Dial by name** If you choose this option, this will enable people who call in to search for people in your organization using Directory Search.</span></span> <span data-ttu-id="26c9a-242">Vous pouvez sélectionner les personnes qui seront répertoriées comme disponibles ou non disponibles pour la Numérotation par nom en configurant ces options dans la page de **portée de la numérotation**.</span><span class="sxs-lookup"><span data-stu-id="26c9a-242">You can select which people will be listed as available or not available for Dial by Name by setting up those options on the **Dial scope** page.</span></span> <span data-ttu-id="26c9a-243">Tout utilisateur en ligne disposant d’une licence de **système téléphonique** ou de tout utilisateur hébergé sur site utilisant Skype entreprise Server ou Lync Server 2013 est disponible avec la numérotation par nom.</span><span class="sxs-lookup"><span data-stu-id="26c9a-243">Any online user with a **Phone System** license, or any user hosted on-premises using Skype for Business Server or Lync Server 2013, can be found with Dial by Name.</span></span>

* * *

<span data-ttu-id="26c9a-244">Lorsque vous avez terminé vos sélections, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="26c9a-244">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="holiday-call-settings"></a><span data-ttu-id="26c9a-245">Paramètres des appels de vacances</span><span class="sxs-lookup"><span data-stu-id="26c9a-245">Holiday call settings</span></span>

<span data-ttu-id="26c9a-246"><a name="holidaygreetings"> </a></span><span class="sxs-lookup"><span data-stu-id="26c9a-246"></span></span>

<span data-ttu-id="26c9a-247">Vous pouvez ajouter jusqu'à 20 congés planifiés pour chaque standard automatique.</span><span class="sxs-lookup"><span data-stu-id="26c9a-247">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

> [!TIP]
> <span data-ttu-id="26c9a-248">Vous pouvez accéder à l’écran des \*\*\*\* > **jours fériés** de votre organisation pour créer des jours fériés ou vous pouvez les créer dans le cadre de la création d’un nouveau gestionnaire d’appels.</span><span class="sxs-lookup"><span data-stu-id="26c9a-248">You can go the the screen at **Org-wide settings** > **Holidays** to create Holidays, or you can create them as part of creating a new call handler.</span></span>

![Capture d’écran de la page des paramètres des appels de vacances](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![Icône du numéro 1 qui référence une légende dans la capture d’écran précédente](media/sfbcallout1.png)

<span data-ttu-id="26c9a-251">Si vous avez déjà créé d’autres standards automatiques, vous verrez peut-être une option que vous pouvez utiliser ou modifier dans ce que vous avez besoin de cette liste.</span><span class="sxs-lookup"><span data-stu-id="26c9a-251">If you've already created other auto attendants, you might see an option you can use or edit into what you need on this list.</span></span> <span data-ttu-id="26c9a-252">Si ce n’est pas le cas, vous devez créer un nouveau gestionnaire d’appels.</span><span class="sxs-lookup"><span data-stu-id="26c9a-252">If not, you'll need to create a new call handler.</span></span>

<span data-ttu-id="26c9a-253">Pour ajouter un nouveau gestionnaire d’appels, cliquez sur **+ nouveau gestionnaire d’appels**.</span><span class="sxs-lookup"><span data-stu-id="26c9a-253">To add a new call handler, click on **+ New call handler**.</span></span>

* * *

![Capture d’écran montrant l’ajout d’un nouveau gestionnaire d’appels](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![Icône du numéro 1 qui référence une légende dans la capture d’écran précédente](media/sfbcallout1.png)

<span data-ttu-id="26c9a-256">Dans la nouvelle fenêtre, entrez un nom pour votre nouveau gestionnaire d’appels dans la partie supérieure de l’écran.</span><span class="sxs-lookup"><span data-stu-id="26c9a-256">In the new window, enter a name for your new Call  handler at the top of the screen.</span></span>

![Icône du numéro 2 qui référence une légende dans la capture d’écran précédente](media/sfbcallout2.png)

<span data-ttu-id="26c9a-258">Si le nom de votre vacances existe déjà dans la liste déroulante **vacances** , vous pouvez l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="26c9a-258">If the name of your holiday already exists in the **Holiday** pull-down list, you can use it.</span></span> <span data-ttu-id="26c9a-259">Si vous n’avez pas encore le nom du jour férié dont vous avez besoin, sélectionnez **créer un jour férié** dans la liste déroulante et attribuez un nom et une date pour le nouveau jour férié dans l’écran nouveau qui s’affiche.</span><span class="sxs-lookup"><span data-stu-id="26c9a-259">If the holiday name you need does not already exist, select **Create new holiday** in the pull-down list and assign a name and a date for the new holiday in the new screen that appears.</span></span> <span data-ttu-id="26c9a-260">Cliquez sur **Enregistrer** lorsque vous êtes prêt.</span><span class="sxs-lookup"><span data-stu-id="26c9a-260">Click on **Save** when ready.</span></span>

<span data-ttu-id="26c9a-261">Noms des jours fériés peuvent contenir jusqu'à 64 caractères et doivent être unique pour le même standard automatique.</span><span class="sxs-lookup"><span data-stu-id="26c9a-261">Holiday names may consist of up to 64 characters and must be unique for the same auto attendant.</span></span> <span data-ttu-id="26c9a-262">Par exemple, vous ne pouvez pas de jours fériés nommés « Actiondegrâce » dans le même standard automatique.</span><span class="sxs-lookup"><span data-stu-id="26c9a-262">For example, you cannot have two holidays named "Thanksgiving" in the same auto attendant.</span></span>

![Icône du numéro 3 qui référence une légende dans la capture d’écran précédente](media/sfbcallout3.png)

<span data-ttu-id="26c9a-264">**Message d’accueil** Le message d’accueil est facultatif et ne peut **pas**être défini pour le message d’accueil.</span><span class="sxs-lookup"><span data-stu-id="26c9a-264">**Greeting** The greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="26c9a-265">Dans ce cas, l'appelant n'entendra aucun message ou salutation avant le traitement de son appel par l'une des options sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="26c9a-265">In this case, the caller will hear no message or greeting before the call is handled by one of the options you select.</span></span> <span data-ttu-id="26c9a-266">Vous pouvez également charger un fichier audio (au format .wav, mp3 ou .wma), ou créer un messager d'accueil personnalisé à l'aide de la synthèse vocale.</span><span class="sxs-lookup"><span data-stu-id="26c9a-266">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="26c9a-267">**Aucun message d’accueil** Aucun message d’accueil ne sera lu lorsque les personnes appellent le numéro de téléphone du standard automatique.</span><span class="sxs-lookup"><span data-stu-id="26c9a-267">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="26c9a-268">**Télécharger un fichier audio** Si vous choisissez cette fonction, enregistrez le message d’accueil du jour férié, puis chargez votre fichier audio (au format. wav,. mp3 ou. WMA).</span><span class="sxs-lookup"><span data-stu-id="26c9a-268">**Upload an audio file** If you choose this, record the holiday greeting and then upload your audio file (in a .wav, .mp3 or .wma format)</span></span>
- <span data-ttu-id="26c9a-269">**Taper un message d’accueil** Si vous choisissez cette option, entrez le texte que le système doit lire (jusqu’à 1000 caractères).</span><span class="sxs-lookup"><span data-stu-id="26c9a-269">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="26c9a-270">Par exemple, vous pouvez entrer « bonne année !</span><span class="sxs-lookup"><span data-stu-id="26c9a-270">For example, you might enter "Happy New Year!</span></span> <span data-ttu-id="26c9a-271">Nos bureaux sont actuellement fermés.</span><span class="sxs-lookup"><span data-stu-id="26c9a-271">Our offices are currently closed."</span></span> <span data-ttu-id="26c9a-272">dans la boîte de dialogue **taper un message d’accueil** .</span><span class="sxs-lookup"><span data-stu-id="26c9a-272">in the **Type a greeting message** box.</span></span>

![Icône du numéro 4, référençant une légende dans la capture d’écran précédente](media/sfbcallout4.png)

<span data-ttu-id="26c9a-274">**Actions** Vous pouvez sélectionner ce qu’il advient des appels à ce jour.</span><span class="sxs-lookup"><span data-stu-id="26c9a-274">**Actions** You can select what happens to the calls that arrive during this holiday.</span></span> <span data-ttu-id="26c9a-275">Vous pouvez choisir parmi les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="26c9a-275">You can chose from the following options:</span></span>

- <span data-ttu-id="26c9a-276">**Se déconnecter** La personne qui appel sera déconnectée après avoir entendu le message d’accueil du congé.</span><span class="sxs-lookup"><span data-stu-id="26c9a-276">**Disconnect** The person calling in will be disconnected after hearing the holiday greeting.</span></span>
- <span data-ttu-id="26c9a-277">**Rediriger un appel** Cela peut servir à envoyer automatiquement l’appel vers :</span><span class="sxs-lookup"><span data-stu-id="26c9a-277">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="26c9a-278">Une\*\*  Personne de votre société\*\*  disposant  d'une licence de \*\* Système téléphonique\*\*  qui est activée pour Voix de l'Enterprise ou de plans d'appels associés dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="26c9a-278">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="26c9a-279">Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="26c9a-279">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="26c9a-280">Pour cela, sélectionnez une **personne au sein de votre entreprise**et configurez cette personne pour que les appels soient transférés directement à la boîte vocale.</span><span class="sxs-lookup"><span data-stu-id="26c9a-280">To do this, select **Person in your company**, and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="26c9a-281">**Une Personne dans votre entreprise** peut être un utilisateur en ligne ou un utilisateur hébergé sur site à l’aide de Skype Professionnel Server 2015 ou Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="26c9a-281">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="26c9a-282">**Application vocale** Sélectionnez le nom d’un compte de ressources associé à une file d’attente d’appels ou à un standard automatique que vous avez déjà créé.</span><span class="sxs-lookup"><span data-stu-id="26c9a-282">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

    > [!Note]
    > <span data-ttu-id="26c9a-283">Par défaut, tous les appels arrivant pendant une période de congé sont définies pour déconnecter la session après le message d’accueil (le cas échéant), vous devez spécifier une redirection si vous souhaitez un comportement différent.</span><span class="sxs-lookup"><span data-stu-id="26c9a-283">By default, all calls arriving during a holiday period are set to disconnect after the greeting (if any), so you must specify a redirect if a different behavior is desired.</span></span>

<a name="dialscope"></a>
#### <a name="select-dial-scope-page"></a><span data-ttu-id="26c9a-284">Page de sélection de la portée de la numérotation</span><span class="sxs-lookup"><span data-stu-id="26c9a-284">Select dial scope page</span></span>

<span data-ttu-id="26c9a-285">Dans cette page, vous pouvez configurer les utilisateurs de votre organisation qui seront répertoriés dans votre annuaire et disponibles pour le numérotation par nom lorsqu’une personne appelle votre organisation.</span><span class="sxs-lookup"><span data-stu-id="26c9a-285">On this page, you can set up which users in your organization will be listed in your directory and available for Dial by Name when a person that calls in to your organization.</span></span>

![Capture d’écran montrant la page de portée de numérotation](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

<span data-ttu-id="26c9a-287">![Icône du numéro 1, qui référence une légende dans la capture d'](media/sfbcallout1.png) écran précédente à l’aide de l’option **inclure** , vous avez deux options :</span><span class="sxs-lookup"><span data-stu-id="26c9a-287">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png) Using the **Include** option, you have two options:</span></span>

- <span data-ttu-id="26c9a-288">**Tous les utilisateurs en ligne** Cette option permet d'inclure toutes les personnes de votre organisation dans la recherche dans l'annuaire.</span><span class="sxs-lookup"><span data-stu-id="26c9a-288">**All Online users** Using this option allows all of the people in your organization to be included in directory search.</span></span> <span data-ttu-id="26c9a-289">Tous les utilisateurs en ligne disposant d’une licence de **système téléphonique** , ainsi que les utilisateurs hébergés sur site utilisant Skype entreprise Server ou Lync Server 2013 qui dispose d’offres d’appels dans Office 365, seront répertoriés.</span><span class="sxs-lookup"><span data-stu-id="26c9a-289">All Online users with a **Phone System** license, as well as users hosted on-premises using Skype for Business Server or Lync Server 2013 who have Calling Plans in Office 365, will be listed.</span></span>
- <span data-ttu-id="26c9a-290">**Groupe d’utilisateurs personnalisés** Si vous utilisez cette option, vous pouvez rechercher un groupe Office 365, une liste de distribution ou un groupe de sécurité qui a été créé au sein de votre organisation et les personnes ajoutées à ce groupe Office 365, liste de distribution ou groupe de sécurité qui sont des **utilisateurs en ligne avec un Licence du système téléphonique** ou hébergé sur site avec Skype entreprise Server 2015 ou Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="26c9a-290">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and the people added to this Office 365 Group, distribution list, or security group who are either **Online users with a Phone System license** or hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="26c9a-291">Vous pouvez ajouter plusieurs groupes 365 Office, des listes de distribution et des groupes de sécurité.</span><span class="sxs-lookup"><span data-stu-id="26c9a-291">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

* * *

![Icône du numéro 2 qui référence une légende dans la capture d’écran précédente](media/sfbcallout2.png)

<span data-ttu-id="26c9a-293">L’option **exclure** présente deux choix :</span><span class="sxs-lookup"><span data-stu-id="26c9a-293">Using the **Exclude** option, you have two options:</span></span>

- <span data-ttu-id="26c9a-294">**Aucun** Cette option indiquera qu'aucun utilisateur en ligne ne sera exclu de la recherche dans l'annuaire.</span><span class="sxs-lookup"><span data-stu-id="26c9a-294">**None** Using this option will indicate that no Online users will be excluded from directory search.</span></span>
- <span data-ttu-id="26c9a-295">**Groupe d’utilisateurs personnalisés** Si vous utilisez cette option, vous pouvez rechercher un groupe, une liste de distribution ou un groupe de sécurité Office 365 qui a été créé au sein de votre organisation, et tous les participants ajoutés à ce groupe Office 365, liste de distribution ou groupes de sécurité seront exclus de la recherche dans l’annuaire.</span><span class="sxs-lookup"><span data-stu-id="26c9a-295">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and all people added to this Office 365 Group, distribution list, or security groups will be excluded from directory search.</span></span> <span data-ttu-id="26c9a-296">Vous pouvez ajouter plusieurs groupes 365 Office, des listes de distribution et des groupes de sécurité.</span><span class="sxs-lookup"><span data-stu-id="26c9a-296">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

> [!NOTE]
> <span data-ttu-id="26c9a-297">L’utilisation de la numérotation par nom avec la reconnaissance vocale peut prendre jusqu’à 36 heures pour qu’un nouveau utilisateur puisse avoir accès à son nom dans l’annuaire lorsque quelqu’un utilise la numérotation par nom.</span><span class="sxs-lookup"><span data-stu-id="26c9a-297">It might take up to 36 hours for a new user to have their name listed in the directory when someone uses Dial by Name with speech recognition.</span></span>

<span data-ttu-id="26c9a-298">Après avoir entré tous les champs requis et configuré l’ensemble des menus et options de traitement des appels, cliquez sur **valider**.</span><span class="sxs-lookup"><span data-stu-id="26c9a-298">After you enter all the required fields and set up call handling menus and options, click **Submit**.</span></span>

## <a name="editing-and-testing-auto-attendants"></a><span data-ttu-id="26c9a-299">Modification et test de standards automatiques</span><span class="sxs-lookup"><span data-stu-id="26c9a-299">Editing and testing auto attendants</span></span>

<span data-ttu-id="26c9a-300">Après avoir enregistré votre standard automatique, il sera répertorié dans la page des **standards automatiques**.</span><span class="sxs-lookup"><span data-stu-id="26c9a-300">After you have saved your auto attendant, it will be listed on the **Auto attendants** page.</span></span> <span data-ttu-id="26c9a-301">Vous pourrez ainsi voir rapidement certaines des options que vous avez configurées, y compris le nom, le numéro de téléphone, la langue et le statut.</span><span class="sxs-lookup"><span data-stu-id="26c9a-301">This will allow you to quickly see some of the options that you have set up, including the name, phone number, language, and status.</span></span>

<span data-ttu-id="26c9a-302">Si vous voulez apporter des modifications à un standard automatique, sélectionnez le standard automatique, puis dans le volet action, cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="26c9a-302">If you want to make changes to an auto attendant, select the auto attendant, and then in the Action pane click **Edit**.</span></span>

<span data-ttu-id="26c9a-303">Vous pouvez également effectuer un test rapide de votre standard automatique à l’aide du bouton **test** dans le volet action.</span><span class="sxs-lookup"><span data-stu-id="26c9a-303">You can also quickly place a test call to your auto attendant by using the **Test** button in the Action pane.</span></span>

## <a name="auto-attendant-cmdlets"></a><span data-ttu-id="26c9a-304">Applets de commande de standard automatique</span><span class="sxs-lookup"><span data-stu-id="26c9a-304">Auto attendant cmdlets</span></span>

<span data-ttu-id="26c9a-305">Vous pouvez également utiliser PowerShell Windows pour créer et configurer des standards automatiques.</span><span class="sxs-lookup"><span data-stu-id="26c9a-305">You can also use Windows PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="26c9a-306">Voici les applets de passe dont vous avez besoin pour gérer un standard automatique :</span><span class="sxs-lookup"><span data-stu-id="26c9a-306">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="26c9a-307">Nouveau-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="26c9a-307">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="26c9a-308">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="26c9a-308">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [<span data-ttu-id="26c9a-309">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="26c9a-309">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)
- [<span data-ttu-id="26c9a-310">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="26c9a-310">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="26c9a-311">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="26c9a-311">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [<span data-ttu-id="26c9a-312">Nouveau-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="26c9a-312">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [<span data-ttu-id="26c9a-313">Nouveau-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="26c9a-313">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [<span data-ttu-id="26c9a-314">Nouveau-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="26c9a-314">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [<span data-ttu-id="26c9a-315">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="26c9a-315">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="26c9a-316">Nouvelle CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="26c9a-316">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [<span data-ttu-id="26c9a-317">Nouvelle CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="26c9a-317">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [<span data-ttu-id="26c9a-318">Nouvelle CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="26c9a-318">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [<span data-ttu-id="26c9a-319">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="26c9a-319">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="26c9a-320">Nouveau-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="26c9a-320">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="26c9a-321">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="26c9a-321">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="26c9a-322">Importation-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="26c9a-322">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="26c9a-323">Nouveau-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="26c9a-323">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="26c9a-324">Informations supplémentaires sur PowerShell Windows</span><span class="sxs-lookup"><span data-stu-id="26c9a-324">More about Windows PowerShell</span></span>

- <span data-ttu-id="26c9a-325">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="26c9a-325">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="26c9a-326">Windows PowerShell vous permet de gérer Office 365 et Microsoft teams à l’aide d’un point d’administration unique qui peut vous simplifier le travail quotidien lorsque vous avez plusieurs tâches à effectuer.</span><span class="sxs-lookup"><span data-stu-id="26c9a-326">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="26c9a-327">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="26c9a-327">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="26c9a-328">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="26c9a-328">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="26c9a-329">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="26c9a-329">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="26c9a-330">Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="26c9a-330">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="26c9a-331">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="26c9a-331">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="26c9a-332">Gérer Office 365 avec Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="26c9a-332">Manage Office 365 with Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="26c9a-333">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="26c9a-333">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="26c9a-334">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="26c9a-334">Related topics</span></span>

[<span data-ttu-id="26c9a-335">Voici les avantages du système téléphonique dans Office 365</span><span class="sxs-lookup"><span data-stu-id="26c9a-335">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="26c9a-336">Obtention de numéros de téléphone de service</span><span class="sxs-lookup"><span data-stu-id="26c9a-336">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="26c9a-337">Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays</span><span class="sxs-lookup"><span data-stu-id="26c9a-337">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="26c9a-338">Nouvelle CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="26c9a-338">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[<span data-ttu-id="26c9a-339">Un standard Cloud automatique, qu’est-ce que c’est ?</span><span class="sxs-lookup"><span data-stu-id="26c9a-339">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="26c9a-340">Exemple de petite entreprise : configurer un standard automatique</span><span class="sxs-lookup"><span data-stu-id="26c9a-340">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)  

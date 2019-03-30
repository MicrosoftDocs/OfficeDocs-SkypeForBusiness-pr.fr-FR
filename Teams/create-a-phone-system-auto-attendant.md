---
title: Configurer les standards automatiques du système téléphonique
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Découvrez comment configurer et tester les standards automatiques de système téléphonique (PBX nuage) pour efficace gestion des appels pour votre organisation.
ms.openlocfilehash: 8bf33e911e11ab7561cc09e0cd18f4cfaf314d98
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013094"
---
# <a name="set-up-a-phone-system-auto-attendant"></a><span data-ttu-id="d35fc-103">Configurer les standards automatiques du système téléphonique</span><span class="sxs-lookup"><span data-stu-id="d35fc-103">Set up a Phone System auto attendant</span></span>

<span data-ttu-id="d35fc-104">Standards automatiques permettent aux personnes qui appellent votre organisation et accédez à les atteindre le bon service, appelez la file d’attente, la personne ou l’opérateur un système de menus.</span><span class="sxs-lookup"><span data-stu-id="d35fc-104">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="d35fc-105">Vous pouvez créer un standard automatique pour votre organisation à l’aide du centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d35fc-105">You can create an auto attendant for your organization by using the Microsoft Teams admin center.</span></span> <span data-ttu-id="d35fc-106">Pour créer un nouveau standard automatique, accédez à la **voix** dans le volet de navigation gauche et sélectionnez **standards automatiques** > **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d35fc-106">To create a new auto attendant, go to **Voice** in the left navigation, and then select **Auto attendants** > **Add new**.</span></span>

<span data-ttu-id="d35fc-107">Si vous souhaitez en savoir plus sur les standards automatiques, voir [Quelles sont les standards automatiques de système téléphonique ?](/microsoftteams/what-are-phone-system-auto-attendants)</span><span class="sxs-lookup"><span data-stu-id="d35fc-107">If you want to learn more about auto attendants, see [What are Phone System auto attendants?](/microsoftteams/what-are-phone-system-auto-attendants)</span></span>

> [!NOTE]
> <span data-ttu-id="d35fc-108">Cet article s’applique à Microsoft Teams et Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="d35fc-108">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>



## <a name="step-1---get-started"></a><span data-ttu-id="d35fc-109">Étape 1 : mise en route</span><span class="sxs-lookup"><span data-stu-id="d35fc-109">Step 1 - Get started</span></span>

- <span data-ttu-id="d35fc-110">Un standard automatique est nécessaire d’avoir un compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="d35fc-110">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="d35fc-111">Pour plus d’informations sur les comptes de ressources, voir [Gérer les comptes de ressources dans les équipes](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="d35fc-111">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="d35fc-112">Si vous souhaitez affecter un numéro de routage Direct, vous devez acquérir et affecter les licences suivantes aux comptes ressource \(Office 365 entreprise E1, E3 ou E5, avec le module complémentaire système téléphonique\).</span><span class="sxs-lookup"><span data-stu-id="d35fc-112">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="d35fc-113">Si vous affectez un numéro de service Microsoft au lieu de cela, vous devez acquérir et affecter les licences suivantes à votre compte de ressource \(Office 365 entreprise E1, E3 ou E5, avec le module complémentaire système téléphonique et un Plan d’appel de\).</span><span class="sxs-lookup"><span data-stu-id="d35fc-113">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>

> [!NOTE] 
> <span data-ttu-id="d35fc-114">Microsoft fonctionne sur un modèle de licence approprié pour les applications telles que les standards automatiques de nuage et les files d’attente des appels, maintenant vous devez utiliser le modèle de gestion des licences utilisateur pour.</span><span class="sxs-lookup"><span data-stu-id="d35fc-114">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>

> [!CAUTION]
> <span data-ttu-id="d35fc-115">Pour obtenir et utiliser les numéros de téléphone, vous devez configurer les crédits de Communications.</span><span class="sxs-lookup"><span data-stu-id="d35fc-115">To get and use toll-free phone numbers, you need to set up Communications Credits.</span></span> <span data-ttu-id="d35fc-116">Pour faire cela, consultez [Quelles sont les Communications crédits ?](what-are-communications-credits.md) et [configurer les Communications crédits pour votre organisation](set-up-communications-credits-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="d35fc-116">To do this see [What are Communications Credits?](what-are-communications-credits.md) and [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>

> [!TIP]
> <span data-ttu-id="d35fc-117">Pour rediriger les appels vers un opérateur ou une option de menu qui est un utilisateur en ligne avec une licence de **Système téléphonique** , vous devez les activer pour Enterprise Voice ou de leur attribuer des Plans de l’appel dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="d35fc-117">To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice or assign Calling Plans in Office 365 to them.</span></span> <span data-ttu-id="d35fc-118">Voir [Assigner de Skype pour les licences d’entreprise](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) ou [licences attribuer les équipes Microsoft](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="d35fc-118">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="d35fc-119">Vous pouvez aussi utiliser Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d35fc-119">You can also use Windows PowerShell.</span></span> <span data-ttu-id="d35fc-120">Par exemple, exécutez :`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="d35fc-120">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

## <a name="step-2---create-a-new-auto-attendant"></a><span data-ttu-id="d35fc-121">Étape 2 : création d'un standard automatique</span><span class="sxs-lookup"><span data-stu-id="d35fc-121">Step 2 - Create a new auto attendant</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d35fc-122">Chaque file d’attente de l’appel doit posséder un [compte de ressource](manage-resource-accounts.md)associé.</span><span class="sxs-lookup"><span data-stu-id="d35fc-122">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="d35fc-123">Vous devez d’abord créer le compte de ressources, puis vous pouvez l’associer au standard automatique.</span><span class="sxs-lookup"><span data-stu-id="d35fc-123">You must create the resource account first, then you can associate it to the auto attendant.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="d35fc-124">À l’aide du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d35fc-124">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="d35fc-125">Dans le **Centre d’administration équipes Microsoft**, cliquez sur **voix** > **standards automatiques**, puis cliquez sur **+ Nouveau**:</span><span class="sxs-lookup"><span data-stu-id="d35fc-125">In the **Microsoft Teams admin center**, click   **Voice** > **Auto attendants**, then click **+ New**:</span></span>

#### <a name="general-info-page"></a><span data-ttu-id="d35fc-126">Page Infos générales</span><span class="sxs-lookup"><span data-stu-id="d35fc-126">General info page</span></span>

![New auto attendant page 1.](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![Numéro 1](media/sfbcallout1.png)

<span data-ttu-id="d35fc-129">**Nom** Entrez un nom d’affichage de la description pour le standard automatique.</span><span class="sxs-lookup"><span data-stu-id="d35fc-129">**Name** Enter a descriptive display name for your auto attendant.</span></span> <span data-ttu-id="d35fc-130">Le nom est obligatoire et peut contenir jusqu'à 64 caractères, espaces compris.</span><span class="sxs-lookup"><span data-stu-id="d35fc-130">The name is required and can contain up to 64 characters, including spaces.</span></span> <span data-ttu-id="d35fc-131">Il sera répertorié dans la colonne **Nom** de l'onglet **Standards automatiques**.</span><span class="sxs-lookup"><span data-stu-id="d35fc-131">It will be listed in the **Name** column on the **Auto attendants** tab.</span></span>

* * *

![Numéro 2](media/sfbcallout2.png)

<span data-ttu-id="d35fc-133">**Compte de ressource** Cliquez sur ce bouton pour sélectionner un ou plusieurs comptes de ressources pour vous connecter à votre nouveau standard automatique.</span><span class="sxs-lookup"><span data-stu-id="d35fc-133">**Resource account** Click this button to select one or more resource accounts to connect to your new auto attendant.</span></span> <span data-ttu-id="d35fc-134">Tous les standards automatiques doit être un compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="d35fc-134">All auto attendants are required to have an associated resource account.</span></span> <span data-ttu-id="d35fc-135">Un compte de ressource peut avoir un numéro de téléphone associé au compte, mais il risque de ne pas.</span><span class="sxs-lookup"><span data-stu-id="d35fc-135">A resource account can have a phone number associated to the account, but it might not.</span></span> <span data-ttu-id="d35fc-136">Un standard automatique de niveau supérieur serait certainement aurait un compte de ressource avec un numéro de téléphone attribuée, mais un standard automatique secondaire (utilisé comme un menu de niveau 2 le standard automatique de niveau premier se connecte à) facilement peut-être pas affecté à un numéro de téléphone son compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="d35fc-136">A top-level auto attendant would almost certainly would have a resource account with an assigned phone number, but a secondary auto attendant (used as a level 2 menu that the first level auto attendant connects to) might easily not have a phone number assigned to its resource account.</span></span>

* * *

![Nombre 3](media/sfbcallout3.png)

<span data-ttu-id="d35fc-p108">**Fuseau horaire** Vous devez définir le fuseau horaire pour votre standard automatique, mais il ne doit pas nécessairement correspondre à celui de l'adresse principale de votre organisation. Vous pouvez définir un fuseau horaire différent pour chaque standard automatique et les horaires d'ouverture du standard automatique seront définies en fonction du fuseau horaire sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d35fc-p108">**Time zone** You must set the time zone for your auto attendant, but it doesn't need to correspond to the time zone of the main address listed for your organization. Each auto attendant can have a different time zone, and the business hours set for the auto attendant will be set based on the time zone that you select here.</span></span>

* * *

![Numéro 4](media/sfbcallout4.png)

<span data-ttu-id="d35fc-141">**Langue** Sélectionnez la langue que vous souhaitez utiliser pour votre standard automatique parmi les langues disponibles répertoriées.</span><span class="sxs-lookup"><span data-stu-id="d35fc-141">**Language** Select the language that you want to use for your auto attendant from any of the available languages listed.</span></span> <span data-ttu-id="d35fc-142">La langue que vous définissez ici est la langue que le standard automatique utilisera pour interagir avec des personnes qui appellent ce standard automatique et toutes les invites système seront énoncées dans cette langue.</span><span class="sxs-lookup"><span data-stu-id="d35fc-142">The language you set here is the language that the auto attendant will use to interact with people that call in to this auto attendant, and all the system prompts will be played in this language.</span></span>

* * *

!["Nombre 5"](media/sfbcallout5.png)

<span data-ttu-id="d35fc-144">**Opérateur** Cette option est facultative ne doit pas nécessairement être définie pour le standard automatique.</span><span class="sxs-lookup"><span data-stu-id="d35fc-144">**Operator** This is optional and doesn't need to be set for the auto attendant.</span></span> <span data-ttu-id="d35fc-145">Toutefois, vous pouvez définir l’option **opérateur** des personnes appellent pour sortir les menus de parler à une personne pour leur permettre de pouvoir.</span><span class="sxs-lookup"><span data-stu-id="d35fc-145">However, you can set the **Operator** option for people that call in to be able to break out of the menus to speak to a person to help them.</span></span>

<span data-ttu-id="d35fc-146">La touche 0 est automatiquement affectée à l'option Opérateur.</span><span class="sxs-lookup"><span data-stu-id="d35fc-146">The key 0 is automatically assigned to Operator.</span></span>

<span data-ttu-id="d35fc-147">Si vous configurer ce paramètre, vous devez également indiquer aux personnes qui appellent que ceci est une option disponible dans le **menu options d’édition** dans la page **Gestion des appels en heures** .</span><span class="sxs-lookup"><span data-stu-id="d35fc-147">If you set this up, you will also need to tell people who call in that this is an available option in the **Edit menu options** on the **Business hours call handling** page.</span></span> <span data-ttu-id="d35fc-148">Si vous définissez un opérateur pour le standard automatique, vous devrez entrer le texte du message correspondant dans la zone **appelants entendront** ou modifier votre fichier audio pour inclure cette option.</span><span class="sxs-lookup"><span data-stu-id="d35fc-148">If you set an operator on your auto attendant, you will need to enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option.</span></span> <span data-ttu-id="d35fc-149">Par exemple, « pour l’opérateur, appuyez sur zéro. »</span><span class="sxs-lookup"><span data-stu-id="d35fc-149">For example, "For the Operator, press zero."</span></span>

<span data-ttu-id="d35fc-150">L'opérateur peut être défini comme suit :</span><span class="sxs-lookup"><span data-stu-id="d35fc-150">You can set one of the following as Operator:</span></span>

- <span data-ttu-id="d35fc-151">**Personne de votre société** avec une licence de **Système téléphonique** qui est activée pour Enterprise Voice ou affectée Plans de l’appel dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="d35fc-151">**Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span>

     > [!Note]
     > <span data-ttu-id="d35fc-152">**Une Personne dans votre entreprise** peut être un utilisateur en ligne ou un utilisateur hébergé sur site à l’aide de Skype Professionnel Server 2015 ou Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d35fc-152">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

- <span data-ttu-id="d35fc-153">Un **appel de file d’attente** que vous avez configurées.</span><span class="sxs-lookup"><span data-stu-id="d35fc-153">A **call queue** that you have set up.</span></span>
- <span data-ttu-id="d35fc-154">Vous pouvez la configurer de manière qu'une personne appelant soit renvoyée sur la messagerie.</span><span class="sxs-lookup"><span data-stu-id="d35fc-154">You can set it up so the person calling will be sent to voicemail.</span></span> <span data-ttu-id="d35fc-155">Pour ce faire, sélectionnez la **personne de votre société** et définir les appels de cette personne à transférer directement vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="d35fc-155">To do this, select **Person in your company** and set this person's calls to be forwarded directly to voicemail.</span></span>

* * *

![Numéro 6](media/sfbcallout6.png)

<span data-ttu-id="d35fc-157">**Activer les entrées vocales** La reconnaissance vocale est disponible si cette option est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d35fc-157">**Enable voice inputs** Speech recognition is available if this option is selected.</span></span> <span data-ttu-id="d35fc-158">Personnes qui appellent dans peuvent utiliser entrée vocale dans la [langue définie](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="d35fc-158">People that call in can use voice input in the  [language you set](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span> <span data-ttu-id="d35fc-159">Vous pouvez désactiver la reconnaissance vocale en définissant la désactiver si vous souhaitez uniquement permettent aux utilisateurs à utiliser leur clavier du téléphone.</span><span class="sxs-lookup"><span data-stu-id="d35fc-159">You can disable speech recognition by setting it to off if you want to only let people use their phone keypad.</span></span>

* * *

<span data-ttu-id="d35fc-160">Lorsque vous avez terminé vos sélections, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="d35fc-160">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="business-hours-page"></a><span data-ttu-id="d35fc-161">Page heures</span><span class="sxs-lookup"><span data-stu-id="d35fc-161">Business hours page</span></span>

<span data-ttu-id="d35fc-162">Par défaut, les heures ouvrées sont définies à 9 h 00 à 17 h 00, du lundi au vendredi.</span><span class="sxs-lookup"><span data-stu-id="d35fc-162">By default, business hours are set to 9am to 5pm, Monday through Friday.</span></span>  <span data-ttu-id="d35fc-163">Toutes les heures exclues des heures d'ouverture sont considérées comme des heures de fermeture.</span><span class="sxs-lookup"><span data-stu-id="d35fc-163">All of the hours that aren't included in business hours are considered after business hours.</span></span> <span data-ttu-id="d35fc-164">Vous pouvez cliquer sur **Sélectionner 24 x 7** pour toutes les heures d’heures.</span><span class="sxs-lookup"><span data-stu-id="d35fc-164">You can click on **Select 24/7** to make all hours business hours.</span></span> <span data-ttu-id="d35fc-165">Sauf si vous sélectionnez l’option **Sélectionner 24 x 7** , la page **d’après les paramètres des appels heures** sera utilisée pour configurer la gestion des appels pour après les heures d’ouverture pour le standard automatique.</span><span class="sxs-lookup"><span data-stu-id="d35fc-165">Unless you select the **Select 24/7** option, the **After hours call settings** page will be used to configure the call handling for after business hours for the auto attendant.</span></span>

![New auto attendant Hours of operation.](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![Numéro 1](media/sfbcallout1.png)

<span data-ttu-id="d35fc-168">Par défaut, les heures ouvrées sont définies à lundi au vendredi, de 9 h 00-17 h 00.</span><span class="sxs-lookup"><span data-stu-id="d35fc-168">By default, business hours are set to Monday to Friday, 9:00 am-5:00 pm.</span></span> <span data-ttu-id="d35fc-169">L’option **désactiver toutes les heures** pour désélectionner toutes les heures d’heures de la planification.</span><span class="sxs-lookup"><span data-stu-id="d35fc-169">Select **Clear all hours** option to unselect all hours hours in the schedule.</span></span> <span data-ttu-id="d35fc-170">Lorsque vous sélectionnez **Rétablir par défaut**, les heures de bureau seront réinitialisées à lundi au vendredi, de 9 h 00-17 h 00.</span><span class="sxs-lookup"><span data-stu-id="d35fc-170">When you select **Reset to default**, business hours will be reset to Monday to Friday, 9:00 am-5:00 pm.</span></span>

* * *

![Numéro 2](media/sfbcallout2.png)

<span data-ttu-id="d35fc-172">Pour modifier les heures d'ouverture, mettez en surbrillance les heures d'ouverture que vous voulez définir à l'aide du calendrier.</span><span class="sxs-lookup"><span data-stu-id="d35fc-172">To change business hours, highlight the business hours you want to set using the calendar.</span></span> <span data-ttu-id="d35fc-173">Le calendrier permet de sélectionner les heures d’ouverture de 30 minutes, et les heures ouvrées que vous sélectionnez ici sera définies en fonction du fuseau horaire que vous avez définie dans la page **informations générales** .</span><span class="sxs-lookup"><span data-stu-id="d35fc-173">The calendar allows you to select business hours in 30-minute intervals, and the business hours you select here will be set based on the time zone that you set on the **General info** page.</span></span> <span data-ttu-id="d35fc-174">Pour configurer une coupure (pour le déjeuner, par exemple), désélectionnez ou faites glisser pour désélectionner l'heure dans le calendrier.</span><span class="sxs-lookup"><span data-stu-id="d35fc-174">To set up a break (a lunch break, for example), deselect or drag to deselect the time on the calendar.</span></span> <span data-ttu-id="d35fc-175">Vous pouvez définir plusieurs sauts dans les heures de bureau.</span><span class="sxs-lookup"><span data-stu-id="d35fc-175">You can set multiple breaks within business hours.</span></span>

* * *

<span data-ttu-id="d35fc-176">Lorsque vous avez terminé vos sélections, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="d35fc-176">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="business-hours-call-settings"></a><span data-ttu-id="d35fc-177">Paramètres des heures d’appels</span><span class="sxs-lookup"><span data-stu-id="d35fc-177">Business hours call settings</span></span>

> [!TIP]
> <span data-ttu-id="d35fc-178">Si vous utilisez un calendrier des heures de travail personnalisées, vous devez également configurer un traitement après les heures de bureau à l’aide de la page **après que les heures de gestion des appels** , qui vous donne les mêmes options que les **Paramètres des heures d’appels**pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="d35fc-178">If you use a custom business hours schedule, you will also need to set up call handing for after business hours using the **After hours call handling** page, which will give you the same options as **Business hours call settings**.</span></span>

<span data-ttu-id="d35fc-179">Vous pouvez configurer le message d’accueil et invites menus que les personnes appel de numéro de téléphone du standard automatique de votre organisation entendra pendant les heures ouvrées.</span><span class="sxs-lookup"><span data-stu-id="d35fc-179">You can set up greetings, prompts, and menus that people who call in to your organization's auto attendant phone number will hear during the business hours.</span></span>

<span data-ttu-id="d35fc-180">![Les heures de bureau de gestion des appels. ](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
 ![Heures suite des appels.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span><span class="sxs-lookup"><span data-stu-id="d35fc-180">![Business hours call handling.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![Business hours call handling continued.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span></span>

* * *

![Numéro 1](media/sfbcallout1.png)

<span data-ttu-id="d35fc-182">**Message d’accueil** Un accueil pendant les heures est facultatif et peut être définie sur **aucun message d’accueil**.</span><span class="sxs-lookup"><span data-stu-id="d35fc-182">**Greeting** A business hours greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="d35fc-183">Dans ce cas, l’appelant n’entendra aucun message ou un message d’accueil avant l’appel est traité par l’une des actions que vous sélectionnez.</span><span class="sxs-lookup"><span data-stu-id="d35fc-183">In this case, the caller will hear no message or greeting before the call is handled by one of the actions you select.</span></span> <span data-ttu-id="d35fc-184">Vous pouvez également charger un fichier audio (au format .wav, mp3 ou .wma), ou créer un messager d'accueil personnalisé à l'aide de la synthèse vocale.</span><span class="sxs-lookup"><span data-stu-id="d35fc-184">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="d35fc-185">**Aucun message d’accueil** Aucun message d’accueil ne sera lu quand personnes appellent au numéro de téléphone du standard automatique.</span><span class="sxs-lookup"><span data-stu-id="d35fc-185">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="d35fc-186">**Télécharger un fichier audio** Si vous choisissez cette option, enregistrer le message d’accueil et puis téléchargez votre fichier audio (au format .wav, .mp3 ou .wma).</span><span class="sxs-lookup"><span data-stu-id="d35fc-186">**Upload an audio file** If you choose this, record the greeting and then upload your audio file (in a .wav, .mp3 or .wma format).</span></span>
- <span data-ttu-id="d35fc-187">**Type d’un message de bienvenue** Si vous choisissez cette option, entrez le texte que vous souhaitez que le système pour lire (1000 caractères maximum).</span><span class="sxs-lookup"><span data-stu-id="d35fc-187">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="d35fc-188">Par exemple, vous pouvez entrer « Bienvenue dans Contoso.</span><span class="sxs-lookup"><span data-stu-id="d35fc-188">For example, you might enter "Welcome to Contoso.</span></span> <span data-ttu-id="d35fc-189">Votre appel est important pour nous.</span><span class="sxs-lookup"><span data-stu-id="d35fc-189">Your call is important to us."</span></span> <span data-ttu-id="d35fc-190">dans la zone **appelants** .</span><span class="sxs-lookup"><span data-stu-id="d35fc-190">in the **Callers will hear** box.</span></span>

* * *

![Numéro 2](media/sfbcallout2.png)

<span data-ttu-id="d35fc-192">Vous pouvez sélectionner que se passe-t-il pour les appels qui arrivent pendant les heures ouvrées.</span><span class="sxs-lookup"><span data-stu-id="d35fc-192">You can select what happens to calls that arrive during business hours.</span></span> <span data-ttu-id="d35fc-193">Vous pouvez choisir parmi les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="d35fc-193">You can chose from the following actions:</span></span>

- <span data-ttu-id="d35fc-194">**Se déconnecter** Si vous l’activez, la personne l’appel sera déconnectée après audition un accueil pendant les heures.</span><span class="sxs-lookup"><span data-stu-id="d35fc-194">**Disconnect** If you select it, the person calling in will be disconnected after hearing a business hours greeting.</span></span>
- <span data-ttu-id="d35fc-195">**Rediriger un appel** Cela peut servir à envoyer automatiquement l’appel vers :</span><span class="sxs-lookup"><span data-stu-id="d35fc-195">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="d35fc-196">**Personne dans la société** avec une licence de **Système téléphonique** qui est activée pour Enterprise Voice ou affectée des Plans de l’appel dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="d35fc-196">**Person in company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="d35fc-197">Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="d35fc-197">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="d35fc-198">Pour ce faire, sélectionnez la **personne dans la société** et définir cette personne pour que leurs appels transférés directement vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="d35fc-198">To do this, select **Person in company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="d35fc-199">**Personne dans la société** peut être un utilisateur en ligne ou un utilisateur hébergé sur site à l’aide de Skype pour Business Server 2015 ou Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d35fc-199">**Person in company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="d35fc-200">Un autre **standard automatique**</span><span class="sxs-lookup"><span data-stu-id="d35fc-200">Another **Auto attendant**</span></span>

   <span data-ttu-id="d35fc-201">Vous pouvez utiliser un standard automatique existant pour créer un second niveau d’options de menu qui contient un sous-menu.</span><span class="sxs-lookup"><span data-stu-id="d35fc-201">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="d35fc-202">Il s’agit des standards automatiques imbriqués.</span><span class="sxs-lookup"><span data-stu-id="d35fc-202">These are called nested auto attendants.</span></span> <span data-ttu-id="d35fc-203">Pour envoyer l’appel vers un standard automatique imbriquées, sélectionnez la **personne dans la société** et affecter un compte de ressource, une ayant déjà un standard automatique associée ou que vous associez à un standard automatique une fois que vous avez terminé la création de ce standard automatique.</span><span class="sxs-lookup"><span data-stu-id="d35fc-203">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

- <span data-ttu-id="d35fc-204">**Lire les options de menu** peut également servir à vous permettent de définir une invite désiré.</span><span class="sxs-lookup"><span data-stu-id="d35fc-204">**Play menu options** can also be used to let you set up a prompt you want played.</span></span>

* * *

![Nombre 3](media/sfbcallout3.png)

<span data-ttu-id="d35fc-206">**Invite de menu** Pour créer une invite de menu principale, vous pouvez utiliser la synthèse vocale ou charger un fichier audio (.wav, .mp3 ou .wma).</span><span class="sxs-lookup"><span data-stu-id="d35fc-206">**Menu prompt** To create main menu prompt, you can either use Text-to-Speech or upload an audio file (.wav, .mp3 or .wma).</span></span> <span data-ttu-id="d35fc-207">Vous pouvez taper l’invite dans la zone **définir votre navigation de menu pour les appelants** ou enregistrer un fichier audio et le dites, par exemple : « pour les ventes, dites ou appuyez sur ou dites 1.</span><span class="sxs-lookup"><span data-stu-id="d35fc-207">You can type the prompt in the **Set your menu navigation for callers** box or record an audio file and say, for example: "For Sales, say or press or say 1.</span></span> <span data-ttu-id="d35fc-208">Pour contacter le département des Services, dites 2 ou appuyez sur 2.</span><span class="sxs-lookup"><span data-stu-id="d35fc-208">For Services, press or say 2.</span></span> <span data-ttu-id="d35fc-209">Pour contacter le service clientèle, dites 3 ou appuyez sur 3.</span><span class="sxs-lookup"><span data-stu-id="d35fc-209">For Customer Support, press or say 3.</span></span> <span data-ttu-id="d35fc-210">Pour contacter l'opérateur, dites 0 ou appuyez sur 0.</span><span class="sxs-lookup"><span data-stu-id="d35fc-210">For the operator, press or say 0.</span></span> <span data-ttu-id="d35fc-211">Pour réécouter ce menu, appuyez sur étoile ou dites répéter.</span><span class="sxs-lookup"><span data-stu-id="d35fc-211">To hear this menu again, press the star key or say repeat."</span></span> <span data-ttu-id="d35fc-212">**Type d’un message de bienvenue** Si vous choisissez cette option, vous devez entrer le texte que vous souhaitez que le système pour lire (1000 caractères maximum).</span><span class="sxs-lookup"><span data-stu-id="d35fc-212">**Type a greeting message** If you chose this, you should enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="d35fc-213">**Charger un fichier audio** Si vous choisissez cette option, vous devrez enregistrer le message d'accueil puis charger votre fichier audio (au format .wav, .mp3 ou .wma).</span><span class="sxs-lookup"><span data-stu-id="d35fc-213">**Upload an audio file** If you chose this, you will need to record the greeting and then upload your audio file (in a .wav, mp3 or .wma format).</span></span>

* * *

![Numéro 4](media/sfbcallout4.png)

<span data-ttu-id="d35fc-215">**Configuration des options de menu** Options de menu à l’aide de boutons clés du pavé numérique peuvent être ajoutées ou supprimées.</span><span class="sxs-lookup"><span data-stu-id="d35fc-215">**Menu options setup** Menu options using key buttons on the keypad can be added or removed.</span></span> <span data-ttu-id="d35fc-216">Pour ajouter une option de menu, appuyez sur la touche **+ affecter une touche d’accès à distance**.</span><span class="sxs-lookup"><span data-stu-id="d35fc-216">To add a menu option, press **+ Assign a dial key**.</span></span> <span data-ttu-id="d35fc-217">Une ligne des options s’affiche ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="d35fc-217">A corresponding row of options will appear below.</span></span> <span data-ttu-id="d35fc-218">Pour supprimer une option de menu, cliquez à gauche de la clé correspondante sur le contrôle pavé numérique simplement et cliquez sur l’icône de suppression ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="d35fc-218">To delete a menu option, simply click to the left of the corresponding key on the keypad control and click on the delete icon above.</span></span> <span data-ttu-id="d35fc-219">La ligne de mappage clé sera supprimée.</span><span class="sxs-lookup"><span data-stu-id="d35fc-219">The key mapping row will be removed.</span></span>

> [!TIP]
> <span data-ttu-id="d35fc-220">Vous devrez mettre à jour le texte des invites de menu ou réenregistrer l’audio séparément lors de l’ajout à la suppression des options, car elle ne s’effectue automatiquement de l’invite de menu existants.</span><span class="sxs-lookup"><span data-stu-id="d35fc-220">You will have to update menu prompts text or re-record the audio separately when adding to removing options because it won't be automatically done for the existing menu prompt.</span></span>  
>
><span data-ttu-id="d35fc-221">Une option de menu peut être ajoutée et supprimée dans n’importe quel ordre, et les mappages de clés ne doivent pas être continue.</span><span class="sxs-lookup"><span data-stu-id="d35fc-221">Any menu option can be added and removed in any order, and the key mappings don't have to be continuous.</span></span> <span data-ttu-id="d35fc-222">Il est possible, par exemple, pour créer un menu avec les touches 0, 1 et 3 mappés aux options, tandis que la touche 2 n’est pas utilisée.</span><span class="sxs-lookup"><span data-stu-id="d35fc-222">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="d35fc-223">Les clés de \* (répétition) et \# (retour) sont réservées par le système et ne peut pas être réaffectés.</span><span class="sxs-lookup"><span data-stu-id="d35fc-223">The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.</span></span> <span data-ttu-id="d35fc-224">Si la reconnaissance vocale est activée, en appuyant sur \* correspond à « Répéter » et # correspond avec les commandes vocales « Nouveau ».</span><span class="sxs-lookup"><span data-stu-id="d35fc-224">If speech recognition is enabled, pressing \* will correspond with "Repeat" and # will correspond with the "Back" voice commands.</span></span>

<span data-ttu-id="d35fc-225">Pour configurer vos options de menu, une fois que vous sélectionnez les touches de numérotation, vous devez :</span><span class="sxs-lookup"><span data-stu-id="d35fc-225">To set up your menu options, after you select the dial key(s), you will need to:</span></span>

- <span data-ttu-id="d35fc-226">Entrez la **commande vocale** de l’option.</span><span class="sxs-lookup"><span data-stu-id="d35fc-226">Enter the **Voice command**  of the option.</span></span> <span data-ttu-id="d35fc-227">Il peut contenir jusqu'à 64 caractères et peut contenir plusieurs mots comme « Service clientèle » ou « opérations et motifs ».</span><span class="sxs-lookup"><span data-stu-id="d35fc-227">This can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="d35fc-228">Si la reconnaissance vocale est activée, le nom sera automatiquement reconnu et la personne qui appelle pourra soit appuyez sur 3, par exemple « 3 », ou dire « Service clientèle » pour sélectionner l’option mappée à la clé 3.</span><span class="sxs-lookup"><span data-stu-id="d35fc-228">If speech recognition is enabled, the name will automatically be recognized, and the person calling in will be able to either press 3, say "three," or say "Customer Service" to select the option mapped to key 3.</span></span>
- <span data-ttu-id="d35fc-229">Sélectionnez où l’appel doit être envoyé si la clé correspondante est activée, ou l’option est sélectionnée à l’aide de la reconnaissance vocale.</span><span class="sxs-lookup"><span data-stu-id="d35fc-229">Select where the call is to be sent if the corresponding key is pressed, or the option is selected using speech recognition.</span></span> <span data-ttu-id="d35fc-230">L’appel peut être envoyé à :</span><span class="sxs-lookup"><span data-stu-id="d35fc-230">The call can be sent to:</span></span>

  - <span data-ttu-id="d35fc-231">**Opérateur** Si l’opérateur a déjà été configuré, il est automatiquement mappé à la clé de 0, mais il peut également être supprimé ou réaffecté à une autre clé.</span><span class="sxs-lookup"><span data-stu-id="d35fc-231">**Operator** If operator is already set up, it is automatically mapped to key 0, but it can also be deleted or reassigned to a different key.</span></span> <span data-ttu-id="d35fc-232">Si l’opérateur n’est pas défini sur n’importe quelle touche, alors la commande vocale « Opérateur » sera désactivée aussi.</span><span class="sxs-lookup"><span data-stu-id="d35fc-232">If operator isn't set to any key, then the voice command "Operator" will be disabled too.</span></span>
  - <span data-ttu-id="d35fc-233">**Une Personne de votre société** avec une licence de **Système téléphonique** qui est activée pour Voix de l'Entreprise ou affectée à un Plan d’appel dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="d35fc-233">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned an Calling Plan in Office 365.</span></span> <span data-ttu-id="d35fc-234">Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="d35fc-234">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="d35fc-235">Pour ce faire, sélectionnez la **personne de votre société** et définissez cette personne pour que leurs appels transférés directement vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="d35fc-235">To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="d35fc-236">**Une Personne dans votre entreprise** peut être un utilisateur en ligne ou un utilisateur hébergé sur site à l’aide de Skype Professionnel Server 2015 ou Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d35fc-236">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="d35fc-237">Lync Server 2010 n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="d35fc-237">Lync Server 2010 is not supported.</span></span>
    - <span data-ttu-id="d35fc-238">Un autre **standard automatique**</span><span class="sxs-lookup"><span data-stu-id="d35fc-238">Another **Auto attendant**</span></span>

       <span data-ttu-id="d35fc-239">Vous pouvez utiliser un standard automatique existant pour créer un second niveau d’options de menu qui contient un sous-menu.</span><span class="sxs-lookup"><span data-stu-id="d35fc-239">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="d35fc-240">Il s’agit des standards automatiques imbriqués.</span><span class="sxs-lookup"><span data-stu-id="d35fc-240">These are called nested auto attendants.</span></span> <span data-ttu-id="d35fc-241">Pour envoyer l’appel vers un standard automatique imbriquées, sélectionnez la **personne dans la société** et affecter un compte de ressource, une ayant déjà un standard automatique associée ou que vous associez à un standard automatique une fois que vous avez terminé la création de ce standard automatique.</span><span class="sxs-lookup"><span data-stu-id="d35fc-241">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

        > [!Note]
        > <span data-ttu-id="d35fc-242">Les **heures d’ouverture** de standards automatiques imbriqués (ou de second niveau) seront également utilisé, y compris pour les appels envoyés à partir d’autres standards automatiques qui ont été définis.</span><span class="sxs-lookup"><span data-stu-id="d35fc-242">The **Business Hours** of nested (or second-level) auto attendants will also be used, including for the calls sent from other auto attendants that have been set up.</span></span>

<!--    - **call queue** Using a call queue option allows the call to be transferred to an existing call queue that you have set up. -->

* * *

!["Nombre 5"](media/sfbcallout5.png)

<span data-ttu-id="d35fc-244">**Numérotation par nom** Si vous choisissez cette option, vous activez des personnes appellent pour rechercher des personnes dans votre organisation à l’aide de la recherche dans l’annuaire.</span><span class="sxs-lookup"><span data-stu-id="d35fc-244">**Dial by name** If you choose this option, this will enable people who call in to search for people in your organization using Directory Search.</span></span> <span data-ttu-id="d35fc-245">Vous pouvez sélectionner les personnes qui seront répertoriées comme disponibles ou non disponibles pour la Numérotation par nom en configurant ces options dans la page de **portée de la numérotation**.</span><span class="sxs-lookup"><span data-stu-id="d35fc-245">You can select which people will be listed as available or not available for Dial by Name by setting up those options on the **Dial scope** page.</span></span> <span data-ttu-id="d35fc-246">Tout utilisateur en ligne disposant d'une licence \*\*   Phone System\*\*  ou de tout utilisateur hébergé sur site à l'aide de Skype Professionnel Server 2015 ou Lync Server 2013 peut être trouvé avec Composer par Nom.</span><span class="sxs-lookup"><span data-stu-id="d35fc-246">Any online user with a **Phone System** license, or any user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013, can be found with Dial by Name.</span></span>

> [!WARNING]
> <span data-ttu-id="d35fc-247">Les utilisateurs hébergés sur site à l’aide de Lync 2010 **ne sont pas joignables** avec numérotation par nom.</span><span class="sxs-lookup"><span data-stu-id="d35fc-247">Users hosted on-premises using Lync 2010 **can't be reached** with Dial by Name.</span></span>

* * *

<span data-ttu-id="d35fc-248">Lorsque vous avez terminé vos sélections, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="d35fc-248">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="holiday-call-settings"></a><span data-ttu-id="d35fc-249">Paramètres d’appel de congé</span><span class="sxs-lookup"><span data-stu-id="d35fc-249">Holiday call settings</span></span>

<span data-ttu-id="d35fc-250">Vous pouvez ajouter jusqu'à 20 congés planifiés pour chaque standard automatique.</span><span class="sxs-lookup"><span data-stu-id="d35fc-250">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

> [!TIP]
> <span data-ttu-id="d35fc-251">Vous pouvez passer le l’écran **paramètres à l’échelle de la société** > **congés** pour créer des congés, ou vous pouvez les créer dans le cadre de la création d’un nouveau gestionnaire d’appel.</span><span class="sxs-lookup"><span data-stu-id="d35fc-251">You can go the the screen at **Org-wide settings** > **Holidays** to create Holidays, or you can create them as part of creating a new call handler.</span></span>

![Définition des congés dans le standard automatique](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![Numéro 1](media/sfbcallout1.png)

<span data-ttu-id="d35fc-254">Si vous avez déjà créé les standards automatiques, vous pouvez voir une option, vous pouvez utiliser ou modifier dans ce que vous devez sur cette liste.</span><span class="sxs-lookup"><span data-stu-id="d35fc-254">If you've already created other auto attendants, you might see an option you can use or edit into what you need on this list.</span></span> <span data-ttu-id="d35fc-255">Si ce n’est pas le cas, vous devez créer un nouveau gestionnaire d’appel.</span><span class="sxs-lookup"><span data-stu-id="d35fc-255">If not, you'll need to create a new call handler.</span></span>

<span data-ttu-id="d35fc-256">Pour ajouter un nouveau gestionnaire d’appel, cliquez sur **+ nouveau gestionnaire d’appel**.</span><span class="sxs-lookup"><span data-stu-id="d35fc-256">To add a new call handler, click on **+ New call handler**.</span></span>

* * *

![Configuration de congés dans le standard automatique (suite)](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![Numéro 1](media/sfbcallout1.png)

<span data-ttu-id="d35fc-259">Dans la nouvelle fenêtre, entrez un nom pour votre nouveau gestionnaire d’appel dans la partie supérieure de l’écran.</span><span class="sxs-lookup"><span data-stu-id="d35fc-259">In the new window, enter a name for your new Call  handler at the top of the screen.</span></span>

![Numéro 2](media/sfbcallout2.png)

<span data-ttu-id="d35fc-261">Si le nom de votre groupe de congés déjà existe dans la liste déroulante **période de congé** , vous pouvez l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="d35fc-261">If the name of your holiday already exists in the **Holiday** pull-down list, you can use it.</span></span> <span data-ttu-id="d35fc-262">Si le nom du congé n’existe pas déjà, sélectionnez **Créer nouveau congé** dans la liste déroulante et attribuer un nom et une date pour le nouveau congé dans le nouvel écran qui s’affiche.</span><span class="sxs-lookup"><span data-stu-id="d35fc-262">If the holiday name you need does not already exist, select **Create new holiday** in the pull-down list and assign a name and a date for the new holiday in the new screen that appears.</span></span> <span data-ttu-id="d35fc-263">Cliquez sur **Enregistrer** lorsque vous êtes prêt.</span><span class="sxs-lookup"><span data-stu-id="d35fc-263">Click on **Save** when ready.</span></span>

<span data-ttu-id="d35fc-264">Noms des jours fériés peuvent contenir jusqu'à 64 caractères et doivent être unique pour le même standard automatique.</span><span class="sxs-lookup"><span data-stu-id="d35fc-264">Holiday names may consist of up to 64 characters and must be unique for the same auto attendant.</span></span> <span data-ttu-id="d35fc-265">Par exemple, vous ne pouvez pas de jours fériés nommés « Actiondegrâce » dans le même standard automatique.</span><span class="sxs-lookup"><span data-stu-id="d35fc-265">For example, you cannot have two holidays named "Thanksgiving" in the same auto attendant.</span></span>

![Nombre 3](media/sfbcallout3.png)

<span data-ttu-id="d35fc-267">**Message d’accueil** Le message d’accueil est facultatif et peut être définie sur **aucun message d’accueil**.</span><span class="sxs-lookup"><span data-stu-id="d35fc-267">**Greeting** The greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="d35fc-268">Dans ce cas, l'appelant n'entendra aucun message ou salutation avant le traitement de son appel par l'une des options sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="d35fc-268">In this case, the caller will hear no message or greeting before the call is handled by one of the options you select.</span></span> <span data-ttu-id="d35fc-269">Vous pouvez également charger un fichier audio (au format .wav, mp3 ou .wma), ou créer un messager d'accueil personnalisé à l'aide de la synthèse vocale.</span><span class="sxs-lookup"><span data-stu-id="d35fc-269">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="d35fc-270">**Aucun message d’accueil** Aucun message d’accueil ne sera lu quand personnes appellent au numéro de téléphone du standard automatique.</span><span class="sxs-lookup"><span data-stu-id="d35fc-270">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="d35fc-271">**Télécharger un fichier audio** Si vous choisissez cette option, enregistrer le message d’accueil de congé et télécharger le fichier audio (au format .wav, .mp3 ou .wma)</span><span class="sxs-lookup"><span data-stu-id="d35fc-271">**Upload an audio file** If you choose this, record the holiday greeting and then upload your audio file (in a .wav, .mp3 or .wma format)</span></span>
- <span data-ttu-id="d35fc-272">**Type d’un message de bienvenue** Si vous choisissez cette option, entrez le texte que vous souhaitez que le système pour lire (1000 caractères maximum).</span><span class="sxs-lookup"><span data-stu-id="d35fc-272">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="d35fc-273">Par exemple, vous pouvez entrer « bonne année !</span><span class="sxs-lookup"><span data-stu-id="d35fc-273">For example, you might enter "Happy New Year!</span></span> <span data-ttu-id="d35fc-274">Nos bureaux sont actuellement fermés.</span><span class="sxs-lookup"><span data-stu-id="d35fc-274">Our offices are currently closed."</span></span> <span data-ttu-id="d35fc-275">dans la zone **Tapez un message de bienvenue** .</span><span class="sxs-lookup"><span data-stu-id="d35fc-275">in the **Type a greeting message** box.</span></span>

![Numéro 4](media/sfbcallout4.png)

<span data-ttu-id="d35fc-277">**Actions** Vous pouvez sélectionner que se passe-t-il pour les appels qui arrivent pendant cette période de congé.</span><span class="sxs-lookup"><span data-stu-id="d35fc-277">**Actions** You can select what happens to the calls that arrive during this holiday.</span></span> <span data-ttu-id="d35fc-278">Vous pouvez choisir parmi les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="d35fc-278">You can chose from the following options:</span></span>

- <span data-ttu-id="d35fc-279">**Se déconnecter** La personne qui appel sera déconnectée après avoir entendu le message d’accueil du congé.</span><span class="sxs-lookup"><span data-stu-id="d35fc-279">**Disconnect** The person calling in will be disconnected after hearing the holiday greeting.</span></span>
- <span data-ttu-id="d35fc-280">**Rediriger un appel** Cela peut servir à envoyer automatiquement l’appel vers :</span><span class="sxs-lookup"><span data-stu-id="d35fc-280">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="d35fc-281">Une\*\*  Personne de votre société\*\*  disposant  d'une licence de \*\* Système téléphonique\*\*  qui est activée pour Voix de l'Enterprise ou de plans d'appels associés dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="d35fc-281">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="d35fc-282">Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="d35fc-282">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="d35fc-283">Pour ce faire, sélectionnez la **personne de votre société**et définir cette personne pour que leurs appels transférés directement vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="d35fc-283">To do this, select **Person in your company**, and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="d35fc-284">**Une Personne dans votre entreprise** peut être un utilisateur en ligne ou un utilisateur hébergé sur site à l’aide de Skype Professionnel Server 2015 ou Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d35fc-284">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="d35fc-285">Lync Server 2010 n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="d35fc-285">Lync Server 2010 is not supported.</span></span>

  - <span data-ttu-id="d35fc-286">Une **file d’attente d’appel** pour transférer l’appel vers une file d’attente appel existant que vous avez configurées.</span><span class="sxs-lookup"><span data-stu-id="d35fc-286">A **call queue** to transfer the call to an existing call queue that you have set up.</span></span>
  - <span data-ttu-id="d35fc-287">Un autre **standard automatique**, pour créer un second niveau d’options de menu qui contient un sous-menu.</span><span class="sxs-lookup"><span data-stu-id="d35fc-287">Another **Auto attendant**, to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="d35fc-288">Il s’agit des standards automatiques imbriqués.</span><span class="sxs-lookup"><span data-stu-id="d35fc-288">These are called nested auto attendants.</span></span>

    > [!Note]
    > <span data-ttu-id="d35fc-289">Par défaut, tous les appels arrivant pendant une période de congé sont définies pour déconnecter la session après le message d’accueil (le cas échéant), vous devez spécifier une redirection si vous souhaitez un comportement différent.</span><span class="sxs-lookup"><span data-stu-id="d35fc-289">By default, all calls arriving during a holiday period are set to disconnect after the greeting (if any), so you must specify a redirect if a different behavior is desired.</span></span>

#### <a name="select-dial-scope-page"></a><span data-ttu-id="d35fc-290">Page de sélection de la portée de la numérotation</span><span class="sxs-lookup"><span data-stu-id="d35fc-290">Select dial scope page</span></span>

<span data-ttu-id="d35fc-291">Dans cette page, vous pouvez configurer les utilisateurs de votre organisation seront répertoriés dans le répertoire et disponibles pour la numérotation par nom lorsqu’une personne qui appelle votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d35fc-291">On this page, you can set up which users in your organization will be listed in your directory and available for Dial by Name when a person that calls in to your organization.</span></span>

![Dial scope for searching with dial by name.](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

<span data-ttu-id="d35fc-293">![N ° 1](media/sfbcallout1.png) à l’aide de l’option **inclure** , vous disposez de deux options :</span><span class="sxs-lookup"><span data-stu-id="d35fc-293">![Number 1](media/sfbcallout1.png) Using the **Include** option, you have two options:</span></span>

- <span data-ttu-id="d35fc-294">**Tous les utilisateurs en ligne** Cette option permet d'inclure toutes les personnes de votre organisation dans la recherche dans l'annuaire.</span><span class="sxs-lookup"><span data-stu-id="d35fc-294">**All Online users** Using this option allows all of the people in your organization to be included in directory search.</span></span> <span data-ttu-id="d35fc-295">Tous les utilisateurs en ligne avec une licence de **Système téléphonique** , ainsi que les utilisateurs hébergés sur site à l’aide de Skype Professionnel Server 2015 ou Lync Server 2013 qui ont des Plans d’appel dans Office 365, apparaîtront.</span><span class="sxs-lookup"><span data-stu-id="d35fc-295">All Online users with a **Phone System** license, as well as users hosted on-premises using Skype for Business Server 2015 or Lync Server 2013 who have Calling Plans in Office 365, will be listed.</span></span>
- <span data-ttu-id="d35fc-296">**Groupe d’utilisateurs personnalisé** Si vous utilisez cette option, vous pouvez rechercher un groupe dans Office 365, liste de distribution ou un groupe de sécurité qui a été créé dans votre organisation et les personnes ajouté à ce groupe dans Office 365, liste de distribution ou groupe de sécurité qui sont soit **utilisateurs en ligne avec un Licence de système téléphonique** ou hébergée sur site à l’aide de Skype pour Business Server 2015 ou Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d35fc-296">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and the people added to this Office 365 Group, distribution list, or security group who are either **Online users with a Phone System license** or hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="d35fc-297">Vous pouvez ajouter plusieurs groupes d’Office 365, les listes de distribution et les groupes de sécurité.</span><span class="sxs-lookup"><span data-stu-id="d35fc-297">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

  > [!Caution]
  > <span data-ttu-id="d35fc-298">Les utilisateurs locaux des déploiements de Lync Server 2010 ne s’affichera lorsqu’un utilisateur recherche l’annuaire à l’aide de la numérotation par nom.</span><span class="sxs-lookup"><span data-stu-id="d35fc-298">On-premises users from deployments of Lync Server 2010 won't be listed when someone searches the directory using Dial by Name.</span></span>

* * *

![Numéro 2](media/sfbcallout2.png)

<span data-ttu-id="d35fc-300">À l’aide de l’option **Exclure** , vous disposez de deux options :</span><span class="sxs-lookup"><span data-stu-id="d35fc-300">Using the **Exclude** option, you have two options:</span></span>

- <span data-ttu-id="d35fc-301">**Aucun** Cette option indiquera qu'aucun utilisateur en ligne ne sera exclu de la recherche dans l'annuaire.</span><span class="sxs-lookup"><span data-stu-id="d35fc-301">**None** Using this option will indicate that no Online users will be excluded from directory search.</span></span>
- <span data-ttu-id="d35fc-302">**Groupe d’utilisateurs personnalisé** Si vous utilisez cette option, vous pouvez rechercher un groupe dans Office 365, liste de distribution ou un groupe de sécurité qui a été créé dans votre organisation, et tous les utilisateurs ajoutés à ce groupe d’Office 365, liste de distribution, ou groupes de sécurité seront exclus de la recherche dans l’annuaire.</span><span class="sxs-lookup"><span data-stu-id="d35fc-302">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and all people added to this Office 365 Group, distribution list, or security groups will be excluded from directory search.</span></span> <span data-ttu-id="d35fc-303">Vous pouvez ajouter plusieurs groupes d’Office 365, les listes de distribution et les groupes de sécurité.</span><span class="sxs-lookup"><span data-stu-id="d35fc-303">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

  > [!Caution]
  > <span data-ttu-id="d35fc-304">Les utilisateurs locaux des déploiements de Lync Server 2010 ne s’affichera lorsqu’un utilisateur recherche l’annuaire à l’aide de la numérotation par nom.</span><span class="sxs-lookup"><span data-stu-id="d35fc-304">On-premises users from deployments of Lync Server 2010 won't be listed when someone searches the directory using Dial by Name.</span></span>

> [!NOTE]
> <span data-ttu-id="d35fc-305">Cela peut prendre jusqu'à 36 heures pour un nouvel utilisateur à leur nom apparaît dans le répertoire lorsqu’une personne utilise la numérotation par un nom pour la reconnaissance vocale.</span><span class="sxs-lookup"><span data-stu-id="d35fc-305">It might take up to 36 hours for a new user to have their name listed in the directory when someone uses Dial by Name with speech recognition.</span></span>

<span data-ttu-id="d35fc-306">Une fois que vous entrez tous les champs obligatoires et que vous définissez des menus et les options de gestion des appels, cliquez sur **Envoyer**.</span><span class="sxs-lookup"><span data-stu-id="d35fc-306">After you enter all the required fields and set up call handling menus and options, click **Submit**.</span></span>

## <a name="editing-and-testing-auto-attendants"></a><span data-ttu-id="d35fc-307">Modification et le test des standards automatiques</span><span class="sxs-lookup"><span data-stu-id="d35fc-307">Editing and testing auto attendants</span></span>

<span data-ttu-id="d35fc-308">Après avoir enregistré votre standard automatique, il sera répertorié dans la page des **standards automatiques**.</span><span class="sxs-lookup"><span data-stu-id="d35fc-308">After you have saved your auto attendant, it will be listed on the **Auto attendants** page.</span></span> <span data-ttu-id="d35fc-309">Cela vous permettra de voir rapidement les options que vous avez configuré, notamment le nom, numéro de téléphone, langue et le statut.</span><span class="sxs-lookup"><span data-stu-id="d35fc-309">This will allow you to quickly see some of the options that you have set up, including the name, phone number, language, and status.</span></span>

<span data-ttu-id="d35fc-310">Si vous souhaitez apporter des modifications à un standard automatique, sélectionnez le standard automatique, puis cliquez sur **Modifier**dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="d35fc-310">If you want to make changes to an auto attendant, select the auto attendant, and then in the Action pane click **Edit**.</span></span>

<span data-ttu-id="d35fc-311">Vous pouvez également rapidement placer un test d’appel pour le standard automatique en utilisant le bouton de **Test** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="d35fc-311">You can also quickly place a test call to your auto attendant by using the **Test** button in the Action pane.</span></span>

## <a name="want-to-know-more"></a><span data-ttu-id="d35fc-312">Vous souhaitez en savoir plus ?</span><span class="sxs-lookup"><span data-stu-id="d35fc-312">Want to know more?</span></span>

<span data-ttu-id="d35fc-313">Vous pouvez également utiliser PowerShell Windows pour créer et configurer des standards automatiques.</span><span class="sxs-lookup"><span data-stu-id="d35fc-313">You can also use Windows PowerShell to create and set up auto attendants.</span></span>

### <a name="auto-attendant-cmdlets"></a><span data-ttu-id="d35fc-314">Applets de commande de standard automatique</span><span class="sxs-lookup"><span data-stu-id="d35fc-314">Auto attendant cmdlets</span></span>

<span data-ttu-id="d35fc-315">Voici les applets de commande requis pour gérer un standard automatique.</span><span class="sxs-lookup"><span data-stu-id="d35fc-315">Here are the cmdlets that you need to manage an auto attendant.</span></span>

 
- [<span data-ttu-id="d35fc-316">Nouvelle CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="d35fc-316">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="d35fc-317">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="d35fc-317">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps) 
- [<span data-ttu-id="d35fc-318">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="d35fc-318">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant?view=skype-ps) 
- [<span data-ttu-id="d35fc-319">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="d35fc-319">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps) 
- [<span data-ttu-id="d35fc-320">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="d35fc-320">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps) 
- [<span data-ttu-id="d35fc-321">Nouvelle CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="d35fc-321">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps) 
- [<span data-ttu-id="d35fc-322">Nouvelle CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="d35fc-322">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps) 
- [<span data-ttu-id="d35fc-323">Nouvelle CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="d35fc-323">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps) 
- [<span data-ttu-id="d35fc-324">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="d35fc-324">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-Export-CsAutoAttendantHolidays?view=skype-ps) 
- [<span data-ttu-id="d35fc-325">Nouvelle CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="d35fc-325">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-New-CsOnlineTimeRange?view=skype-ps) 
- [<span data-ttu-id="d35fc-326">Nouvelle CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="d35fc-326">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps) 
- [<span data-ttu-id="d35fc-327">Nouvelle CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="d35fc-327">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps) 
- [<span data-ttu-id="d35fc-328">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="d35fc-328">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps) 
- [<span data-ttu-id="d35fc-329">Nouvelle CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="d35fc-329">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps) 
- [<span data-ttu-id="d35fc-330">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="d35fc-330">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps) 
- [<span data-ttu-id="d35fc-331">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="d35fc-331">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps) 
- [<span data-ttu-id="d35fc-332">Nouvelle CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="d35fc-332">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps) 

### <a name="more-about-windows-powershell"></a><span data-ttu-id="d35fc-333">Informations supplémentaires sur PowerShell Windows</span><span class="sxs-lookup"><span data-stu-id="d35fc-333">More about Windows PowerShell</span></span>

- <span data-ttu-id="d35fc-334">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="d35fc-334">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="d35fc-335">Avec Windows PowerShell, vous pouvez gérer Office 365 et Teams Microsoft à l’aide d’un point unique d’administration qui peut simplifier votre travail quotidien, lorsque vous avez plusieurs tâches.</span><span class="sxs-lookup"><span data-stu-id="d35fc-335">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="d35fc-336">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="d35fc-336">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="d35fc-337">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="d35fc-337">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="d35fc-338">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="d35fc-338">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="d35fc-p147">Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="d35fc-p147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="d35fc-341">Gérer Office 365 avec Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d35fc-341">Manage Office 365 with Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="d35fc-342">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="d35fc-342">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="d35fc-343">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="d35fc-343">Related topics</span></span>

[<span data-ttu-id="d35fc-344">Voici les avantages du système téléphonique dans Office 365</span><span class="sxs-lookup"><span data-stu-id="d35fc-344">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="d35fc-345">Obtention de numéros de téléphone de service</span><span class="sxs-lookup"><span data-stu-id="d35fc-345">Getting service phone numbers</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[<span data-ttu-id="d35fc-346">Disponibilité des forfaits d'appels et de l’audioconférence selon les régions et les pays</span><span class="sxs-lookup"><span data-stu-id="d35fc-346">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="d35fc-347">Nouvelle CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="d35fc-347">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[<span data-ttu-id="d35fc-348">Quels sont les standards automatiques du système téléphonique?</span><span class="sxs-lookup"><span data-stu-id="d35fc-348">What are Phone System auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="d35fc-349">Exemple de petite entreprise : configurer un standard automatique</span><span class="sxs-lookup"><span data-stu-id="d35fc-349">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/skypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)  

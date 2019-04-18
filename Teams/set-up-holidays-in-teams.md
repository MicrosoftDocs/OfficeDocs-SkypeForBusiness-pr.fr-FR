---
title: Configurer des jours fériés dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
description: Découvrez comment configurer les jours fériés dans Microsoft Teams et les connecter à votre standard automatique.
ms.openlocfilehash: afec7fc3f1bbe47c907b823711db3b8b8ef3aded
ms.sourcegitcommit: 6949c957224949ccc6f5958d3c84294d382ee405
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2019
ms.locfileid: "31914577"
---
# <a name="set-up-holidays-in-microsoft-teams"></a><span data-ttu-id="ee865-103">Configurer des jours fériés dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ee865-103">Set up holidays in Microsoft Teams</span></span>

<span data-ttu-id="ee865-104">Vous pouvez utiliser la fonctionnalité de congés des équipes Microsoft pour planifier les dates spécifiques et de lorsque les personnes de votre organisation seront être prenez des congés à partir de travail n’est pas disponible pendant les heures ouvrables.</span><span class="sxs-lookup"><span data-stu-id="ee865-104">You can use the Microsoft Teams Holidays feature to schedule specific dates and times when people in your organization will be taking time off from work and won’t be available during regular business hours.</span></span> 

<span data-ttu-id="ee865-105">Vous pouvez lier les congés à standards automatiques que vous créez au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="ee865-105">You can link the holidays to auto attendants that you create within your organization.</span></span> <span data-ttu-id="ee865-106">Standards automatiques de permettent aux appelants de naviguer d’un système de menus pour atteindre le bon service ou d’obtenir les informations dont ils ont besoin.</span><span class="sxs-lookup"><span data-stu-id="ee865-106">Auto attendants let callers navigate a menu system to get to the right department or get to information that they need.</span></span> <span data-ttu-id="ee865-107">Lorsque vous configurez les paramètres d’appel congé pour un standard automatique, vous pouvez sélectionnez le jour férié à partir d’une liste, ajouter un message d’accueil et spécifier que faire avec l’appel lorsque celui-ci est reçu par le standard automatique au cours de la période de congé.</span><span class="sxs-lookup"><span data-stu-id="ee865-107">When you configure holiday call settings for an auto attendant, you can select the holiday from a list, add a greeting, and specify what to do with the call when it’s answered by the auto attendant during the holiday.</span></span>

<span data-ttu-id="ee865-108">Un bon exemple consiste à créer un congé pour Noël pour lorsque beaucoup de vos employés ne sont pas au bureau.</span><span class="sxs-lookup"><span data-stu-id="ee865-108">A good example is creating a holiday for Christmas for when many of your employees aren’t at work.</span></span> <span data-ttu-id="ee865-109">Après avoir créer la période de congé et définir les heures, puis vous devez ajouter le congé à votre principale standard automatique afin que lors de l’appellent de personnes, elles seront entendre un message audio que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="ee865-109">After you create the holiday and set times, then you would add the holiday to your main auto attendant so when people call in, they will hear an audio message you created.</span></span> <span data-ttu-id="ee865-110">Quelque chose comme, « nous effectuons fermés de Noël de 22 décembre via 27 décembre.</span><span class="sxs-lookup"><span data-stu-id="ee865-110">Something like, “We are closed for Christmas from December 22nd through December 27th.</span></span> <span data-ttu-id="ee865-111">Laissez nous un message vocal afin que nous pouvons renvoyer votre appel lorsque nous sommes du bureau. »</span><span class="sxs-lookup"><span data-stu-id="ee865-111">Please leave us a voice message so we can return your call when we are back in the office.”</span></span>

<span data-ttu-id="ee865-112">Pour plus d’informations sur les standards automatiques, voir [Quelles sont les standards automatiques de nuage](what-are-phone-system-auto-attendants.md)?</span><span class="sxs-lookup"><span data-stu-id="ee865-112">For more information about auto attendants, see [What are Cloud auto attendants](what-are-phone-system-auto-attendants.md)?</span></span>  

## <a name="create-a-holiday"></a><span data-ttu-id="ee865-113">Créer une période de congé</span><span class="sxs-lookup"><span data-stu-id="ee865-113">Create a holiday</span></span>

1. <span data-ttu-id="ee865-114">Dans le centre d’administration Microsoft Teams, accédez à **paramètres à l’échelle de l’organisation** > **jours fériés**.</span><span class="sxs-lookup"><span data-stu-id="ee865-114">In the Microsoft Teams admin center, go to **Org-wide settings** > **Holidays**.</span></span>

2. <span data-ttu-id="ee865-115">Sélectionnez **Nouveau congé**.</span><span class="sxs-lookup"><span data-stu-id="ee865-115">Select **New holiday**.</span></span>

3. <span data-ttu-id="ee865-116">Entrez un nom pour la période de congé.</span><span class="sxs-lookup"><span data-stu-id="ee865-116">Enter a name for the holiday.</span></span>

4. <span data-ttu-id="ee865-117">Sélectionnez **Ajouter nouvelle date**.</span><span class="sxs-lookup"><span data-stu-id="ee865-117">Select **Add new date**.</span></span>

5. <span data-ttu-id="ee865-118">Sous **heure de début**, sélectionnez l’icône du calendrier, sélectionnez la date lorsque vous souhaitez que le congé pour commencer.</span><span class="sxs-lookup"><span data-stu-id="ee865-118">Under **Start time**, select the calendar icon and choose the date when you’d like the holiday to begin.</span></span>

6. <span data-ttu-id="ee865-119">Utilisez la liste déroulante pour sélectionner une heure de début pour la période de congé.</span><span class="sxs-lookup"><span data-stu-id="ee865-119">Use the drop-down list to select a start time for the holiday.</span></span>

7. <span data-ttu-id="ee865-120">Sous **heure de fin**, sélectionnez l’icône du calendrier, sélectionnez la date lorsque vous souhaitez que le congé à la fin.</span><span class="sxs-lookup"><span data-stu-id="ee865-120">Under **End time**, select the calendar icon and choose the date when you’d like the holiday to end.</span></span> <span data-ttu-id="ee865-121">Si le congé n’est qu’un jour, il doit s’agir de la même date que celui que vous avez choisi sous **heure de début**.</span><span class="sxs-lookup"><span data-stu-id="ee865-121">If the holiday is one day only, this should be the same date as the one you chose under **Start time**.</span></span>

8. <span data-ttu-id="ee865-122">Utilisez la liste déroulante pour sélectionner une heure de fin pour la période de congé.</span><span class="sxs-lookup"><span data-stu-id="ee865-122">Use the drop-down list to select an end time for the holiday.</span></span>

9. <span data-ttu-id="ee865-123">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ee865-123">Select **Save**.</span></span>

## <a name="change-a-holiday"></a><span data-ttu-id="ee865-124">Modifier une période de congé</span><span class="sxs-lookup"><span data-stu-id="ee865-124">Change a holiday</span></span>

1. <span data-ttu-id="ee865-125">Dans le centre d’administration Microsoft Teams, accédez à **paramètres à l’échelle de l’organisation** > **jours fériés**.</span><span class="sxs-lookup"><span data-stu-id="ee865-125">In the Microsoft Teams admin center, go to **Org-wide settings** > **Holidays**.</span></span>

2. <span data-ttu-id="ee865-126">Dans la liste, sélectionnez la période de congé.</span><span class="sxs-lookup"><span data-stu-id="ee865-126">Select the holiday from the list.</span></span>

3. <span data-ttu-id="ee865-127">Sous **heure de début**, sélectionnez l’icône du calendrier, sélectionnez la date lorsque vous souhaitez que le congé pour commencer.</span><span class="sxs-lookup"><span data-stu-id="ee865-127">Under **Start time**, select the calendar icon and choose the date when you’d like the holiday to begin.</span></span>

4. <span data-ttu-id="ee865-128">Utilisez la liste déroulante pour sélectionner une heure de début pour la période de congé.</span><span class="sxs-lookup"><span data-stu-id="ee865-128">Use the drop-down list to select a start time for the holiday.</span></span>

5. <span data-ttu-id="ee865-129">Sous **heure de fin**, sélectionnez l’icône du calendrier, sélectionnez la date lorsque vous souhaitez que le congé à la fin.</span><span class="sxs-lookup"><span data-stu-id="ee865-129">Under **End time**, select the calendar icon and choose the date when you’d like the holiday to end.</span></span> 

6. <span data-ttu-id="ee865-130">Utilisez la liste déroulante pour sélectionner une heure de fin pour la période de congé.</span><span class="sxs-lookup"><span data-stu-id="ee865-130">Use the drop-down list to select an end time for the holiday.</span></span>

7. <span data-ttu-id="ee865-131">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ee865-131">Select **Save**.</span></span>

## <a name="connect-a-holiday-to-an-auto-attendant"></a><span data-ttu-id="ee865-132">Connecter un congé à un standard automatique</span><span class="sxs-lookup"><span data-stu-id="ee865-132">Connect a holiday to an auto attendant</span></span>

1. <span data-ttu-id="ee865-133">Dans le centre d’administration Microsoft Teams, accédez à la **voix** > **standards automatiques**.</span><span class="sxs-lookup"><span data-stu-id="ee865-133">In the Microsoft Teams admin center, go to **Voice** > **Auto attendants**.</span></span>
2. <span data-ttu-id="ee865-134">Sélectionnez un compte de ressource dans la liste.</span><span class="sxs-lookup"><span data-stu-id="ee865-134">Select a resource account from the list.</span></span>
3. <span data-ttu-id="ee865-135">Dans le volet gauche, sélectionnez **Paramètres des appels de congé**.</span><span class="sxs-lookup"><span data-stu-id="ee865-135">In the left pane, select **Holiday call settings**.</span></span>
4. <span data-ttu-id="ee865-136">Sélectionnez **Nouveau congé**.</span><span class="sxs-lookup"><span data-stu-id="ee865-136">Select **New holiday**.</span></span>
5. <span data-ttu-id="ee865-137">Dans la liste déroulante, sélectionnez la période de congé.</span><span class="sxs-lookup"><span data-stu-id="ee865-137">Select the holiday from the drop-down list.</span></span>
6. <span data-ttu-id="ee865-138">Vous pouvez ajouter un message d’accueil facultatif :</span><span class="sxs-lookup"><span data-stu-id="ee865-138">You can add an optional greeting:</span></span>
    - <span data-ttu-id="ee865-139">Pour lire un message d’accueil enregistré, sélectionnez **lire un fichier audio**, puis sélectionnez **Télécharger le fichier**.</span><span class="sxs-lookup"><span data-stu-id="ee865-139">To play a recorded greeting, select **Play an audio file**, and then select **Upload file**.</span></span> <span data-ttu-id="ee865-140">Accédez à l’emplacement du fichier audio, sélectionnez le fichier, puis sélectionnez **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="ee865-140">Browse to the location of the audio file, select the file, and then select **Open**.</span></span>
    - <span data-ttu-id="ee865-141">Pour créer un message d’accueil, sélectionnez le **Type d’un message de bienvenue**, puis tapez votre message.</span><span class="sxs-lookup"><span data-stu-id="ee865-141">To create a greeting, select **Type a greeting message**, and then type your message.</span></span> <span data-ttu-id="ee865-142">Les appelants entendent ce message si vous n’avez pas fourni d’un fichier audio.</span><span class="sxs-lookup"><span data-stu-id="ee865-142">Callers will hear this message if you haven’t provided an audio file.</span></span>
7. <span data-ttu-id="ee865-143">Pour mettre fin à l’appel après le message d’accueil, sous **Actions**, sélectionnez **se déconnecter**.</span><span class="sxs-lookup"><span data-stu-id="ee865-143">To end the call after the greeting, under **Actions**, select **Disconnect**.</span></span> 

    <span data-ttu-id="ee865-144">Pour rediriger l’appel, sélectionnez **rediriger l’appel**, puis sélectionnez la personne qui recevra l’appel redirigé à partir de la liste déroulante ou de la recherche pour la personne par nom complet.</span><span class="sxs-lookup"><span data-stu-id="ee865-144">To redirect the call, select **Redirect call**, and then select the person who will receive the redirected call from the drop-down list or search for the person by display name.</span></span>
8. <span data-ttu-id="ee865-145">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ee865-145">Select **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ee865-146">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="ee865-146">Related topics</span></span>

<span data-ttu-id="ee865-147">[Quelles sont les standards automatiques de nuage](what-are-phone-system-auto-attendants.md)?</span><span class="sxs-lookup"><span data-stu-id="ee865-147">[What are Cloud auto attendants](what-are-phone-system-auto-attendants.md)?</span></span>
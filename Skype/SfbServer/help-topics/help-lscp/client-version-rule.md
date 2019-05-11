---
title: Règle de version du client
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: Une stratégie de version de client est composée d’un ensemble de règles de version de client. Ces règles définissent les actions qui doivent être effectuées lorsque les utilisateurs tentent de se connecter avec des clients et des versions de client spécifiques.
ms.openlocfilehash: 2b78d665e608a9ac81baaaaee5812957a2eaf5e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920379"
---
# <a name="client-version-rule"></a><span data-ttu-id="6fb2c-104">Règle de version du client</span><span class="sxs-lookup"><span data-stu-id="6fb2c-104">Client Version Rule</span></span>

<span data-ttu-id="6fb2c-p102">Une stratégie de version de client est composée d’un ensemble de règles de version de client. Ces règles définissent les actions qui doivent être effectuées lorsque les utilisateurs tentent de se connecter avec des clients et des versions de client spécifiques.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="6fb2c-107">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="6fb2c-107">Tasks you can perform</span></span>

<span data-ttu-id="6fb2c-108">Dans la page **Nouvelle configuration de version du client** ou **Modifier la configuration de version du client**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="6fb2c-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="6fb2c-109">Ajout de nouvelles règles à une stratégie de version de client</span><span class="sxs-lookup"><span data-stu-id="6fb2c-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="6fb2c-110">Modification des règles composant une stratégie de version de client existante</span><span class="sxs-lookup"><span data-stu-id="6fb2c-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="6fb2c-111">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="6fb2c-111">UI Reference</span></span>

<span data-ttu-id="6fb2c-112">Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="6fb2c-113">**Agent utilisateur** Vous pouvez sélectionner un type de client à partir de la liste.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="6fb2c-114">Le tableau suivant définit les codes d’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-114">The following table defines user agent codes.</span></span>

|<span data-ttu-id="6fb2c-115">**Nom du client**</span><span class="sxs-lookup"><span data-stu-id="6fb2c-115">**Client Name**</span></span>|<span data-ttu-id="6fb2c-116">**Agent utilisateur**</span><span class="sxs-lookup"><span data-stu-id="6fb2c-116">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6fb2c-117">Lync 2013, Lync 2010, Office Communicator</span><span class="sxs-lookup"><span data-stu-id="6fb2c-117">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="6fb2c-118">OC</span><span class="sxs-lookup"><span data-stu-id="6fb2c-118">OC</span></span>  <br/> |
|<span data-ttu-id="6fb2c-119">Lync Web App, Office Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="6fb2c-119">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="6fb2c-120">CWA</span><span class="sxs-lookup"><span data-stu-id="6fb2c-120">CWA</span></span>  <br/> |
|<span data-ttu-id="6fb2c-121">Lync Phone Edition, Office Communicator Phone</span><span class="sxs-lookup"><span data-stu-id="6fb2c-121">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="6fb2c-122">OCPhone</span><span class="sxs-lookup"><span data-stu-id="6fb2c-122">OCPhone</span></span>  <br/> |
|<span data-ttu-id="6fb2c-123">Communicator Phone Edition Platform</span><span class="sxs-lookup"><span data-stu-id="6fb2c-123">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="6fb2c-124">CPE</span><span class="sxs-lookup"><span data-stu-id="6fb2c-124">CPE</span></span>  <br/> |
|<span data-ttu-id="6fb2c-125">Unified Communications Platform</span><span class="sxs-lookup"><span data-stu-id="6fb2c-125">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="6fb2c-126">UCCP</span><span class="sxs-lookup"><span data-stu-id="6fb2c-126">UCCP</span></span>  <br/> |
|<span data-ttu-id="6fb2c-127">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="6fb2c-127">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="6fb2c-128">AOC</span><span class="sxs-lookup"><span data-stu-id="6fb2c-128">AOC</span></span>  <br/> |
|<span data-ttu-id="6fb2c-129">Complément Live Meeting</span><span class="sxs-lookup"><span data-stu-id="6fb2c-129">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="6fb2c-130">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="6fb2c-130">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="6fb2c-131">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="6fb2c-131">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="6fb2c-132">LMC</span><span class="sxs-lookup"><span data-stu-id="6fb2c-132">LMC</span></span>  <br/> |
|<span data-ttu-id="6fb2c-133">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="6fb2c-133">Windows Messenger</span></span>  <br/> |<span data-ttu-id="6fb2c-134">WM</span><span class="sxs-lookup"><span data-stu-id="6fb2c-134">WM</span></span>  <br/> |
|<span data-ttu-id="6fb2c-135">Client Real-time Communications</span><span class="sxs-lookup"><span data-stu-id="6fb2c-135">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="6fb2c-136">RTC</span><span class="sxs-lookup"><span data-stu-id="6fb2c-136">RTC</span></span>  <br/> |
|<span data-ttu-id="6fb2c-137">Lync 2010 pour iPad</span><span class="sxs-lookup"><span data-stu-id="6fb2c-137">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="6fb2c-138">iPadLync</span><span class="sxs-lookup"><span data-stu-id="6fb2c-138">iPadLync</span></span>  <br/> |
|<span data-ttu-id="6fb2c-139">Lync 2010 pour iPhone</span><span class="sxs-lookup"><span data-stu-id="6fb2c-139">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="6fb2c-140">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="6fb2c-140">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="6fb2c-141">Lync 2010 pour Windows Phone</span><span class="sxs-lookup"><span data-stu-id="6fb2c-141">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="6fb2c-142">WPLync</span><span class="sxs-lookup"><span data-stu-id="6fb2c-142">WPLync</span></span>  <br/> |
|<span data-ttu-id="6fb2c-143">Lync 2010 pour Nokia</span><span class="sxs-lookup"><span data-stu-id="6fb2c-143">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="6fb2c-144">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="6fb2c-144">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="6fb2c-145">Lync 2010 pour Android</span><span class="sxs-lookup"><span data-stu-id="6fb2c-145">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="6fb2c-146">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="6fb2c-146">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="6fb2c-147">Mobility Service</span><span class="sxs-lookup"><span data-stu-id="6fb2c-147">Mobility service</span></span>  <br/> |<span data-ttu-id="6fb2c-148">McxService</span><span class="sxs-lookup"><span data-stu-id="6fb2c-148">McxService</span></span>  <br/> |

- <span data-ttu-id="6fb2c-149">**Numéro de version** Vous pouvez spécifier les numéros de version pour les champs suivants, ou utiliser des caractères génériques pour indiquer le numéro de version du client.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-149">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="6fb2c-150">**Version principale** Spécifie le numéro qui correspond à la version principale du client.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-150">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="6fb2c-151">**Version secondaire** Spécifie le numéro qui correspond à la version mineure du client.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-151">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="6fb2c-152">**Créer** Spécifie le numéro de version correspondant à la version principale et secondaire du client.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-152">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="6fb2c-153">**Mise à jour** Spécifie le numéro qui correspond à la version mise à jour du client.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-153">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="6fb2c-154">**Opération de comparaison** Vous pouvez spécifier l’opération de correspondance pour la version de client que vous avez spécifié dans les étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-154">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="6fb2c-155">Les opérations suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="6fb2c-155">The following operations are available:</span></span>

  - <span data-ttu-id="6fb2c-156">**Identique à**</span><span class="sxs-lookup"><span data-stu-id="6fb2c-156">**Same as**</span></span>

  - <span data-ttu-id="6fb2c-157">**Différent de**</span><span class="sxs-lookup"><span data-stu-id="6fb2c-157">**Is not**</span></span>

  - <span data-ttu-id="6fb2c-158">**Antérieur à**</span><span class="sxs-lookup"><span data-stu-id="6fb2c-158">**Newer than**</span></span>

  - <span data-ttu-id="6fb2c-159">**Antérieur ou simultané**</span><span class="sxs-lookup"><span data-stu-id="6fb2c-159">**Newer than or same as**</span></span>

  - <span data-ttu-id="6fb2c-160">**Postérieur à**</span><span class="sxs-lookup"><span data-stu-id="6fb2c-160">**Older than**</span></span>

  - <span data-ttu-id="6fb2c-161">**Postérieur ou simultané**</span><span class="sxs-lookup"><span data-stu-id="6fb2c-161">**Older than or same as**</span></span>

- <span data-ttu-id="6fb2c-162">**Action** Vous pouvez spécifier l’action à effectuer lorsque les critères ci-dessus sont remplies.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-162">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="6fb2c-163">Les actions suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="6fb2c-163">The following actions are available:</span></span>

  - <span data-ttu-id="6fb2c-164">**Autoriser** Autorise le client à se connecter.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-164">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="6fb2c-165">**Autoriser et mettre à niveau** Autorise le client à se connecter et de recevoir des mises à jour de Service de mise à jour de Windows Server ou Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-165">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="6fb2c-166">Cette action est disponible uniquement lorsque l’agent utilisateur **OC** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-166">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6fb2c-167">Sélectionnez cette action entraîne une notification à afficher les prochaine fois que les utilisateurs se connectent à Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-167">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="6fb2c-168">La notification indique qu’une mise à jour est disponible, même si les mises à jour n’ont pas encore été publiées pour le Service de mise à jour de Windows Server ou Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-168">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="6fb2c-169">Pour éviter toute confusion, vous devez choisir cette action uniquement une fois que les mises à jour sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-169">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="6fb2c-170">**Autoriser avec une URL** Autorise le client à se connecter et affiche un message sur l’emplacement de téléchargement d’une autre version du client.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-170">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="6fb2c-171">Vous devez spécifier l’URL dans le champ **URL**.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-171">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="6fb2c-172">**Bloc** Empêche le client de se connecter.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-172">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="6fb2c-173">**Blocage et mise à niveau** Empêche le client de se connecter et autorise le client à recevoir des mises à jour de Service de mise à jour de Windows Server ou Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-173">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="6fb2c-174">Cette action est disponible uniquement lorsque l’agent utilisateur **OC** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-174">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="6fb2c-p110">**Bloquer avec une URL** : empêche le client de se connecter et affiche un message à l’emplacement de téléchargement d’une autre version du client. Vous devez spécifier l’URL dans le champ **URL**.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="6fb2c-p111">Pour plus d’informations sur l’interopérabilité entre les clients et les versions des clients, reportez-vous à la rubrique [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) de la documentation de planification. Pour plus d’informations sur l’utilisation des configurations de version du client, reportez-vous à la rubrique [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) de la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="6fb2c-p111">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>


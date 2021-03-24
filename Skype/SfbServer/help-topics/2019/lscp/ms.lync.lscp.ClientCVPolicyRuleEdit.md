---
title: Règle de version du client
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: Une stratégie de version du client est composé d’un ensemble de règles de version des clients. Ces règles définissent les actions à prendre lorsque les utilisateurs tentent de se connecter avec des clients et des versions de clients spécifiques.
ms.openlocfilehash: a461dad500f0c7d3095ef56483a6b592cec6c20d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109620"
---
# <a name="client-version-rule"></a><span data-ttu-id="45172-104">Règle de version du client</span><span class="sxs-lookup"><span data-stu-id="45172-104">Client Version Rule</span></span>

<span data-ttu-id="45172-105">Une stratégie de version du client est composé d’un ensemble de règles de version des clients.</span><span class="sxs-lookup"><span data-stu-id="45172-105">A client version policy is made up of a set of client version rules.</span></span> <span data-ttu-id="45172-106">Ces règles définissent les actions à prendre lorsque les utilisateurs tentent de se connecter avec des clients et des versions de clients spécifiques.</span><span class="sxs-lookup"><span data-stu-id="45172-106">These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="45172-107">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="45172-107">Tasks you can perform</span></span>

<span data-ttu-id="45172-108">Vous pouvez effectuer les tâches suivantes dans la page **Nouvelle configuration de version du client** ou **Modifier la configuration de version du client** :</span><span class="sxs-lookup"><span data-stu-id="45172-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="45172-109">Ajoutez de nouvelles règles à une stratégie de version du client.</span><span class="sxs-lookup"><span data-stu-id="45172-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="45172-110">Modifier les règles qui font une stratégie de version du client existante</span><span class="sxs-lookup"><span data-stu-id="45172-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="45172-111">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="45172-111">UI Reference</span></span>

<span data-ttu-id="45172-112">Les listes suivantes décrivent les menus, commandes, champs et propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="45172-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="45172-113">**Agent utilisateur** Vous pouvez sélectionner un type de client dans la liste.</span><span class="sxs-lookup"><span data-stu-id="45172-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="45172-114">Le tableau suivant définit les codes d’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="45172-114">The following table defines user agent codes.</span></span> <span data-ttu-id="45172-115">Cette liste inclut les types de clients hérités, dont certains ne sont plus pris en charge.</span><span class="sxs-lookup"><span data-stu-id="45172-115">This list includes legacy client types, some of which are no longer supported.</span></span>

|<span data-ttu-id="45172-116">**Nom du client**</span><span class="sxs-lookup"><span data-stu-id="45172-116">**Client Name**</span></span>|<span data-ttu-id="45172-117">**Agent utilisateur**</span><span class="sxs-lookup"><span data-stu-id="45172-117">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="45172-118">Lync 2013, Lync 2010, Office Communicator</span><span class="sxs-lookup"><span data-stu-id="45172-118">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="45172-119">OC</span><span class="sxs-lookup"><span data-stu-id="45172-119">OC</span></span>  <br/> |
|<span data-ttu-id="45172-120">Lync Web App, Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="45172-120">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="45172-121">CWA</span><span class="sxs-lookup"><span data-stu-id="45172-121">CWA</span></span>  <br/> |
|<span data-ttu-id="45172-122">Lync Phone Edition, Office Communicator Phone</span><span class="sxs-lookup"><span data-stu-id="45172-122">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="45172-123">OCPhone</span><span class="sxs-lookup"><span data-stu-id="45172-123">OCPhone</span></span>  <br/> |
|<span data-ttu-id="45172-124">Communicator Phone Edition Platform</span><span class="sxs-lookup"><span data-stu-id="45172-124">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="45172-125">CPE</span><span class="sxs-lookup"><span data-stu-id="45172-125">CPE</span></span>  <br/> |
|<span data-ttu-id="45172-126">Plateforme de communications unifiées</span><span class="sxs-lookup"><span data-stu-id="45172-126">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="45172-127">UCCP</span><span class="sxs-lookup"><span data-stu-id="45172-127">UCCP</span></span>  <br/> |
|<span data-ttu-id="45172-128">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="45172-128">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="45172-129">AOC</span><span class="sxs-lookup"><span data-stu-id="45172-129">AOC</span></span>  <br/> |
|<span data-ttu-id="45172-130">Live Meeting Add-In</span><span class="sxs-lookup"><span data-stu-id="45172-130">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="45172-131">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="45172-131">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="45172-132">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="45172-132">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="45172-133">LMC</span><span class="sxs-lookup"><span data-stu-id="45172-133">LMC</span></span>  <br/> |
|<span data-ttu-id="45172-134">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="45172-134">Windows Messenger</span></span>  <br/> |<span data-ttu-id="45172-135">WM</span><span class="sxs-lookup"><span data-stu-id="45172-135">WM</span></span>  <br/> |
|<span data-ttu-id="45172-136">Client communications en temps réel</span><span class="sxs-lookup"><span data-stu-id="45172-136">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="45172-137">RTC</span><span class="sxs-lookup"><span data-stu-id="45172-137">RTC</span></span>  <br/> |
|<span data-ttu-id="45172-138">Lync 2010 pour iPad</span><span class="sxs-lookup"><span data-stu-id="45172-138">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="45172-139">iPadLync</span><span class="sxs-lookup"><span data-stu-id="45172-139">iPadLync</span></span>  <br/> |
|<span data-ttu-id="45172-140">Lync 2010 pour iPhone</span><span class="sxs-lookup"><span data-stu-id="45172-140">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="45172-141">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="45172-141">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="45172-142">Lync 2010 pour Windows Phone</span><span class="sxs-lookup"><span data-stu-id="45172-142">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="45172-143">WPLync</span><span class="sxs-lookup"><span data-stu-id="45172-143">WPLync</span></span>  <br/> |
|<span data-ttu-id="45172-144">Lync 2010 pour Nokia</span><span class="sxs-lookup"><span data-stu-id="45172-144">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="45172-145">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="45172-145">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="45172-146">Lync 2010 pour Android</span><span class="sxs-lookup"><span data-stu-id="45172-146">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="45172-147">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="45172-147">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="45172-148">Service de mobilité</span><span class="sxs-lookup"><span data-stu-id="45172-148">Mobility service</span></span>  <br/> |<span data-ttu-id="45172-149">McxService</span><span class="sxs-lookup"><span data-stu-id="45172-149">McxService</span></span>  <br/> |

- <span data-ttu-id="45172-150">**Numéro de version** Vous pouvez spécifier les numéros de version pour les champs suivants ou utiliser des caractères génériques pour indiquer le numéro de version du client.</span><span class="sxs-lookup"><span data-stu-id="45172-150">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="45172-151">**Version principale** Spécifie le nombre qui correspond à la version majeure du client.</span><span class="sxs-lookup"><span data-stu-id="45172-151">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="45172-152">**Version mineure** Spécifie le nombre qui correspond à la version mineure du client.</span><span class="sxs-lookup"><span data-stu-id="45172-152">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="45172-153">**Build** Spécifie le numéro de build qui correspond à la version principale et mineure du client.</span><span class="sxs-lookup"><span data-stu-id="45172-153">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="45172-154">**Mettre à jour** Spécifie le numéro qui correspond à la version mise à jour du client.</span><span class="sxs-lookup"><span data-stu-id="45172-154">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="45172-155">**Opération de comparaison** Vous pouvez spécifier l’opération de correspondance pour la version du client que vous avez spécifiée dans les étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="45172-155">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="45172-156">Les opérations suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="45172-156">The following operations are available:</span></span>

  - <span data-ttu-id="45172-157">**Identique à**</span><span class="sxs-lookup"><span data-stu-id="45172-157">**Same as**</span></span>

  - <span data-ttu-id="45172-158">**N’est pas**</span><span class="sxs-lookup"><span data-stu-id="45172-158">**Is not**</span></span>

  - <span data-ttu-id="45172-159">**Plus récent que**</span><span class="sxs-lookup"><span data-stu-id="45172-159">**Newer than**</span></span>

  - <span data-ttu-id="45172-160">**Plus récent ou identique**</span><span class="sxs-lookup"><span data-stu-id="45172-160">**Newer than or same as**</span></span>

  - <span data-ttu-id="45172-161">**Plus ancien que**</span><span class="sxs-lookup"><span data-stu-id="45172-161">**Older than**</span></span>

  - <span data-ttu-id="45172-162">**Plus ancien ou identique**</span><span class="sxs-lookup"><span data-stu-id="45172-162">**Older than or same as**</span></span>

- <span data-ttu-id="45172-163">**Action** Vous pouvez spécifier l’action à effectuer lorsque les critères des étapes précédentes sont satisfaits.</span><span class="sxs-lookup"><span data-stu-id="45172-163">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="45172-164">Les actions suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="45172-164">The following actions are available:</span></span>

  - <span data-ttu-id="45172-165">**Autoriser** Permet au client de se connecter.</span><span class="sxs-lookup"><span data-stu-id="45172-165">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="45172-166">**Autoriser et mettre à niveau** Permet au client de se connecter et de recevoir des mises à jour à partir de Windows Server Update Service ou De Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="45172-166">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="45172-167">Cette action est uniquement disponible lorsque l’agent utilisateur **OC** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="45172-167">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="45172-168">La sélection de cette action entraîne l’affichage d’une notification la prochaine fois que les utilisateurs se connectent à Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="45172-168">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="45172-169">La notification indique qu’une mise à jour est disponible, même si les mises à jour n’ont pas encore été publiées sur Windows Server Update Service ou Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="45172-169">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="45172-170">Pour éviter toute confusion, vous avez tout intérêt à choisir cette action après que des mises à jour ont été mises à disposition uniquement.</span><span class="sxs-lookup"><span data-stu-id="45172-170">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="45172-171">**Autoriser avec une URL** Permet au client de se connecter et affiche un message sur l’endroit où télécharger une autre version du client.</span><span class="sxs-lookup"><span data-stu-id="45172-171">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="45172-172">Vous spécifiez l’URL dans le **champ URL.**</span><span class="sxs-lookup"><span data-stu-id="45172-172">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="45172-173">**Bloquer** Empêche le client de se connecter.</span><span class="sxs-lookup"><span data-stu-id="45172-173">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="45172-174">**Bloquer et mettre à niveau** Empêche le client de se connecter et permet au client de recevoir des mises à jour à partir de Windows Server Update Service ou de Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="45172-174">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="45172-175">Cette action est uniquement disponible lorsque l’agent utilisateur **OC** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="45172-175">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="45172-176">**Bloquer avec une URL** empêche le client de se connecter et affiche un message sur l’endroit où télécharger une autre version du client.</span><span class="sxs-lookup"><span data-stu-id="45172-176">**Block with URL** prevents the client from logging on and displays a message about where to download another client version.</span></span> <span data-ttu-id="45172-177">Vous spécifiez l’URL dans le **champ URL.**</span><span class="sxs-lookup"><span data-stu-id="45172-177">You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="45172-178">Pour plus d’informations sur l’interopérabilité entre les clients et les versions des clients, voir [Interopérabilité](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) du client dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="45172-178">For details about interoperability among clients and client versions, see [Client Interoperability](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="45172-179">Pour plus d’informations sur l’utilisation des configurations de version du client, voir [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="45172-179">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) in the Operations documentation.</span></span>
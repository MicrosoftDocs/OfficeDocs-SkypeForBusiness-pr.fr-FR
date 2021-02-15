---
title: Règle de version du client
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: Une stratégie de version des clients est composé d’un ensemble de règles de version des clients. Ces règles définissent les actions à prendre lorsque les utilisateurs tentent de se connecter avec des clients et des versions de clients spécifiques.
ms.openlocfilehash: 14e9c0d14ce988ec89d8bb13410272c4734ae882
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829494"
---
# <a name="client-version-rule"></a><span data-ttu-id="18e7a-104">Règle de version du client</span><span class="sxs-lookup"><span data-stu-id="18e7a-104">Client Version Rule</span></span>

<span data-ttu-id="18e7a-105">Une stratégie de version des clients est composé d’un ensemble de règles de version des clients.</span><span class="sxs-lookup"><span data-stu-id="18e7a-105">A client version policy is made up of a set of client version rules.</span></span> <span data-ttu-id="18e7a-106">Ces règles définissent les actions à prendre lorsque les utilisateurs tentent de se connecter avec des clients et des versions de clients spécifiques.</span><span class="sxs-lookup"><span data-stu-id="18e7a-106">These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="18e7a-107">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="18e7a-107">Tasks you can perform</span></span>

<span data-ttu-id="18e7a-108">Vous pouvez effectuer les tâches suivantes dans la page **Nouvelle configuration de version du client** ou **Modifier la configuration de version du client** :</span><span class="sxs-lookup"><span data-stu-id="18e7a-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="18e7a-109">Ajoutez de nouvelles règles à une stratégie de version du client.</span><span class="sxs-lookup"><span data-stu-id="18e7a-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="18e7a-110">Modifier les règles qui font une stratégie de version du client existante</span><span class="sxs-lookup"><span data-stu-id="18e7a-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="18e7a-111">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="18e7a-111">UI Reference</span></span>

<span data-ttu-id="18e7a-112">Les listes suivantes décrivent les menus, commandes, champs et propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="18e7a-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="18e7a-113">**Agent utilisateur** Vous pouvez sélectionner un type de client dans la liste.</span><span class="sxs-lookup"><span data-stu-id="18e7a-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="18e7a-114">Le tableau suivant définit les codes d’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="18e7a-114">The following table defines user agent codes.</span></span>

|<span data-ttu-id="18e7a-115">**Nom du client**</span><span class="sxs-lookup"><span data-stu-id="18e7a-115">**Client Name**</span></span>|<span data-ttu-id="18e7a-116">**Agent utilisateur**</span><span class="sxs-lookup"><span data-stu-id="18e7a-116">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="18e7a-117">Lync 2013, Lync 2010, Office Communicator</span><span class="sxs-lookup"><span data-stu-id="18e7a-117">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="18e7a-118">OC</span><span class="sxs-lookup"><span data-stu-id="18e7a-118">OC</span></span>  <br/> |
|<span data-ttu-id="18e7a-119">Lync Web App, Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="18e7a-119">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="18e7a-120">CWA</span><span class="sxs-lookup"><span data-stu-id="18e7a-120">CWA</span></span>  <br/> |
|<span data-ttu-id="18e7a-121">Lync Phone Edition, Office Communicator Phone</span><span class="sxs-lookup"><span data-stu-id="18e7a-121">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="18e7a-122">OCPhone</span><span class="sxs-lookup"><span data-stu-id="18e7a-122">OCPhone</span></span>  <br/> |
|<span data-ttu-id="18e7a-123">Communicator Phone Edition Platform</span><span class="sxs-lookup"><span data-stu-id="18e7a-123">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="18e7a-124">CPE</span><span class="sxs-lookup"><span data-stu-id="18e7a-124">CPE</span></span>  <br/> |
|<span data-ttu-id="18e7a-125">Plateforme de communications unifiées</span><span class="sxs-lookup"><span data-stu-id="18e7a-125">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="18e7a-126">UCCP</span><span class="sxs-lookup"><span data-stu-id="18e7a-126">UCCP</span></span>  <br/> |
|<span data-ttu-id="18e7a-127">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="18e7a-127">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="18e7a-128">AOC</span><span class="sxs-lookup"><span data-stu-id="18e7a-128">AOC</span></span>  <br/> |
|<span data-ttu-id="18e7a-129">Live Meeting Add-In</span><span class="sxs-lookup"><span data-stu-id="18e7a-129">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="18e7a-130">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="18e7a-130">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="18e7a-131">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="18e7a-131">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="18e7a-132">LMC</span><span class="sxs-lookup"><span data-stu-id="18e7a-132">LMC</span></span>  <br/> |
|<span data-ttu-id="18e7a-133">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="18e7a-133">Windows Messenger</span></span>  <br/> |<span data-ttu-id="18e7a-134">WM</span><span class="sxs-lookup"><span data-stu-id="18e7a-134">WM</span></span>  <br/> |
|<span data-ttu-id="18e7a-135">Client communications en temps réel</span><span class="sxs-lookup"><span data-stu-id="18e7a-135">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="18e7a-136">RTC</span><span class="sxs-lookup"><span data-stu-id="18e7a-136">RTC</span></span>  <br/> |
|<span data-ttu-id="18e7a-137">Lync 2010 pour iPad</span><span class="sxs-lookup"><span data-stu-id="18e7a-137">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="18e7a-138">iPadLync</span><span class="sxs-lookup"><span data-stu-id="18e7a-138">iPadLync</span></span>  <br/> |
|<span data-ttu-id="18e7a-139">Lync 2010 pour iPhone</span><span class="sxs-lookup"><span data-stu-id="18e7a-139">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="18e7a-140">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="18e7a-140">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="18e7a-141">Lync 2010 pour Windows Phone</span><span class="sxs-lookup"><span data-stu-id="18e7a-141">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="18e7a-142">WPLync</span><span class="sxs-lookup"><span data-stu-id="18e7a-142">WPLync</span></span>  <br/> |
|<span data-ttu-id="18e7a-143">Lync 2010 pour Nokia</span><span class="sxs-lookup"><span data-stu-id="18e7a-143">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="18e7a-144">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="18e7a-144">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="18e7a-145">Lync 2010 pour Android</span><span class="sxs-lookup"><span data-stu-id="18e7a-145">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="18e7a-146">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="18e7a-146">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="18e7a-147">Service de mobilité</span><span class="sxs-lookup"><span data-stu-id="18e7a-147">Mobility service</span></span>  <br/> |<span data-ttu-id="18e7a-148">McxService</span><span class="sxs-lookup"><span data-stu-id="18e7a-148">McxService</span></span>  <br/> |

- <span data-ttu-id="18e7a-149">**Numéro de version** Vous pouvez spécifier les numéros de version pour les champs suivants ou utiliser des caractères génériques pour indiquer le numéro de version du client.</span><span class="sxs-lookup"><span data-stu-id="18e7a-149">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="18e7a-150">**Version principale** Spécifie le nombre qui correspond à la version majeure du client.</span><span class="sxs-lookup"><span data-stu-id="18e7a-150">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="18e7a-151">**Version mineure** Spécifie le nombre qui correspond à la version mineure du client.</span><span class="sxs-lookup"><span data-stu-id="18e7a-151">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="18e7a-152">**Build** Spécifie le numéro de build qui correspond à la version principale et mineure du client.</span><span class="sxs-lookup"><span data-stu-id="18e7a-152">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="18e7a-153">**Mettre à jour** Spécifie le numéro qui correspond à la version mise à jour du client.</span><span class="sxs-lookup"><span data-stu-id="18e7a-153">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="18e7a-154">**Opération de comparaison** Vous pouvez spécifier l’opération de correspondance pour la version du client que vous avez spécifiée dans les étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="18e7a-154">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="18e7a-155">Les opérations suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="18e7a-155">The following operations are available:</span></span>

  - <span data-ttu-id="18e7a-156">**Identique à**</span><span class="sxs-lookup"><span data-stu-id="18e7a-156">**Same as**</span></span>

  - <span data-ttu-id="18e7a-157">**N’est pas**</span><span class="sxs-lookup"><span data-stu-id="18e7a-157">**Is not**</span></span>

  - <span data-ttu-id="18e7a-158">**Plus récent que**</span><span class="sxs-lookup"><span data-stu-id="18e7a-158">**Newer than**</span></span>

  - <span data-ttu-id="18e7a-159">**Plus récent ou identique**</span><span class="sxs-lookup"><span data-stu-id="18e7a-159">**Newer than or same as**</span></span>

  - <span data-ttu-id="18e7a-160">**Plus ancien que**</span><span class="sxs-lookup"><span data-stu-id="18e7a-160">**Older than**</span></span>

  - <span data-ttu-id="18e7a-161">**Plus ancien ou identique**</span><span class="sxs-lookup"><span data-stu-id="18e7a-161">**Older than or same as**</span></span>

- <span data-ttu-id="18e7a-162">**Action** Vous pouvez spécifier l’action à effectuer lorsque les critères des étapes précédentes sont satisfaits.</span><span class="sxs-lookup"><span data-stu-id="18e7a-162">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="18e7a-163">Les actions suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="18e7a-163">The following actions are available:</span></span>

  - <span data-ttu-id="18e7a-164">**Autoriser** Permet au client de se connecter.</span><span class="sxs-lookup"><span data-stu-id="18e7a-164">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="18e7a-165">**Autoriser et mettre à niveau** Permet au client de se connecter et de recevoir des mises à jour à partir de Windows Server Update Service ou De Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="18e7a-165">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="18e7a-166">Cette action est uniquement disponible lorsque l’agent utilisateur **OC** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="18e7a-166">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="18e7a-167">La sélection de cette action entraîne l’affichage d’une notification la prochaine fois que les utilisateurs se connectent à Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="18e7a-167">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="18e7a-168">La notification indique qu’une mise à jour est disponible, même si les mises à jour n’ont pas encore été publiées sur Windows Server Update Service ou Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="18e7a-168">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="18e7a-169">Pour éviter toute confusion, vous avez tout intérêt à choisir cette action après que des mises à jour ont été mises à disposition uniquement.</span><span class="sxs-lookup"><span data-stu-id="18e7a-169">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="18e7a-170">**Autoriser avec une URL** Permet au client de se connecter et affiche un message sur l’endroit où télécharger une autre version du client.</span><span class="sxs-lookup"><span data-stu-id="18e7a-170">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="18e7a-171">Vous spécifiez l’URL dans le **champ URL.**</span><span class="sxs-lookup"><span data-stu-id="18e7a-171">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="18e7a-172">**Bloquer** Empêche le client de se connecter.</span><span class="sxs-lookup"><span data-stu-id="18e7a-172">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="18e7a-173">**Bloquer et mettre à niveau** Empêche le client de se connecter et permet au client de recevoir des mises à jour à partir de Windows Server Update Service ou de Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="18e7a-173">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="18e7a-174">Cette action est uniquement disponible lorsque l’agent utilisateur **OC** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="18e7a-174">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="18e7a-175">**Bloquer avec une URL** empêche le client de se connecter et affiche un message sur l’endroit où télécharger une autre version du client.</span><span class="sxs-lookup"><span data-stu-id="18e7a-175">**Block with URL** prevents the client from logging on and displays a message about where to download another client version.</span></span> <span data-ttu-id="18e7a-176">Vous spécifiez l’URL dans le **champ URL.**</span><span class="sxs-lookup"><span data-stu-id="18e7a-176">You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="18e7a-177">Pour plus d’informations sur l’interopérabilité entre les clients et les versions des clients, voir [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="18e7a-177">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="18e7a-178">Pour plus d’informations sur l’utilisation des configurations de version du client, voir [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="18e7a-178">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>


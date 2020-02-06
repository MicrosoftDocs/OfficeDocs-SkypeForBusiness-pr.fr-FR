---
title: Règle de version du client
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Une stratégie de version de client est composée d’un ensemble de règles de version de client. Ces règles définissent les actions qui doivent être effectuées lorsque les utilisateurs tentent de se connecter avec des clients et des versions de client spécifiques.
ms.openlocfilehash: a4d8cb38f30e8c332a9cec0ea90e27c012187d47
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794593"
---
# <a name="client-version-rule"></a><span data-ttu-id="13a08-104">Règle de version du client</span><span class="sxs-lookup"><span data-stu-id="13a08-104">Client Version Rule</span></span>

<span data-ttu-id="13a08-p102">Une stratégie de version de client est composée d’un ensemble de règles de version de client. Ces règles définissent les actions qui doivent être effectuées lorsque les utilisateurs tentent de se connecter avec des clients et des versions de client spécifiques.</span><span class="sxs-lookup"><span data-stu-id="13a08-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="13a08-107">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="13a08-107">Tasks you can perform</span></span>

<span data-ttu-id="13a08-108">Dans la page **Nouvelle configuration de version du client** ou **Modifier la configuration de version du client**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="13a08-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="13a08-109">Ajout de nouvelles règles à une stratégie de version de client</span><span class="sxs-lookup"><span data-stu-id="13a08-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="13a08-110">Modification des règles composant une stratégie de version de client existante</span><span class="sxs-lookup"><span data-stu-id="13a08-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="13a08-111">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="13a08-111">UI Reference</span></span>

<span data-ttu-id="13a08-112">Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="13a08-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="13a08-113">**Agent utilisateur** Vous pouvez sélectionner un type de client dans la liste.</span><span class="sxs-lookup"><span data-stu-id="13a08-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="13a08-114">Le tableau suivant définit les codes des agents utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="13a08-114">The following table defines user agent codes.</span></span> <span data-ttu-id="13a08-115">Cette liste comprend les types de clients hérités, qui ne sont plus pris en charge.</span><span class="sxs-lookup"><span data-stu-id="13a08-115">This list includes legacy client types, some of which are no longer supported.</span></span>

|<span data-ttu-id="13a08-116">**Nom du client**</span><span class="sxs-lookup"><span data-stu-id="13a08-116">**Client Name**</span></span>|<span data-ttu-id="13a08-117">**Agent utilisateur**</span><span class="sxs-lookup"><span data-stu-id="13a08-117">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="13a08-118">Lync 2013, Lync 2010, Office Communicator</span><span class="sxs-lookup"><span data-stu-id="13a08-118">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="13a08-119">OC</span><span class="sxs-lookup"><span data-stu-id="13a08-119">OC</span></span>  <br/> |
|<span data-ttu-id="13a08-120">Lync Web App, Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="13a08-120">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="13a08-121">CWA</span><span class="sxs-lookup"><span data-stu-id="13a08-121">CWA</span></span>  <br/> |
|<span data-ttu-id="13a08-122">Lync Phone Edition, téléphone Office Communicator</span><span class="sxs-lookup"><span data-stu-id="13a08-122">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="13a08-123">OCPhone</span><span class="sxs-lookup"><span data-stu-id="13a08-123">OCPhone</span></span>  <br/> |
|<span data-ttu-id="13a08-124">Communicator Phone Edition Platform</span><span class="sxs-lookup"><span data-stu-id="13a08-124">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="13a08-125">CPE</span><span class="sxs-lookup"><span data-stu-id="13a08-125">CPE</span></span>  <br/> |
|<span data-ttu-id="13a08-126">Unified Communications Platform</span><span class="sxs-lookup"><span data-stu-id="13a08-126">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="13a08-127">UCCP</span><span class="sxs-lookup"><span data-stu-id="13a08-127">UCCP</span></span>  <br/> |
|<span data-ttu-id="13a08-128">Lync 2010 participant</span><span class="sxs-lookup"><span data-stu-id="13a08-128">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="13a08-129">AOC</span><span class="sxs-lookup"><span data-stu-id="13a08-129">AOC</span></span>  <br/> |
|<span data-ttu-id="13a08-130">Complément Live Meeting</span><span class="sxs-lookup"><span data-stu-id="13a08-130">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="13a08-131">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="13a08-131">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="13a08-132">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="13a08-132">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="13a08-133">LMC</span><span class="sxs-lookup"><span data-stu-id="13a08-133">LMC</span></span>  <br/> |
|<span data-ttu-id="13a08-134">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="13a08-134">Windows Messenger</span></span>  <br/> |<span data-ttu-id="13a08-135">WM</span><span class="sxs-lookup"><span data-stu-id="13a08-135">WM</span></span>  <br/> |
|<span data-ttu-id="13a08-136">Client Real-time Communications</span><span class="sxs-lookup"><span data-stu-id="13a08-136">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="13a08-137">RTC</span><span class="sxs-lookup"><span data-stu-id="13a08-137">RTC</span></span>  <br/> |
|<span data-ttu-id="13a08-138">Lync 2010 pour iPad</span><span class="sxs-lookup"><span data-stu-id="13a08-138">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="13a08-139">iPadLync</span><span class="sxs-lookup"><span data-stu-id="13a08-139">iPadLync</span></span>  <br/> |
|<span data-ttu-id="13a08-140">Lync 2010 pour iPhone</span><span class="sxs-lookup"><span data-stu-id="13a08-140">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="13a08-141">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="13a08-141">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="13a08-142">Lync 2010 pour Windows Phone</span><span class="sxs-lookup"><span data-stu-id="13a08-142">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="13a08-143">WPLync</span><span class="sxs-lookup"><span data-stu-id="13a08-143">WPLync</span></span>  <br/> |
|<span data-ttu-id="13a08-144">Lync 2010 pour Nokia</span><span class="sxs-lookup"><span data-stu-id="13a08-144">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="13a08-145">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="13a08-145">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="13a08-146">Lync 2010 pour Android</span><span class="sxs-lookup"><span data-stu-id="13a08-146">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="13a08-147">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="13a08-147">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="13a08-148">Mobility Service</span><span class="sxs-lookup"><span data-stu-id="13a08-148">Mobility service</span></span>  <br/> |<span data-ttu-id="13a08-149">McxService</span><span class="sxs-lookup"><span data-stu-id="13a08-149">McxService</span></span>  <br/> |

- <span data-ttu-id="13a08-150">**Numéro de version** Vous pouvez spécifier les numéros de version pour les champs suivants ou utiliser des caractères génériques pour indiquer le numéro de version du client.</span><span class="sxs-lookup"><span data-stu-id="13a08-150">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="13a08-151">**Version principale** Spécifie le numéro qui correspond à la version majeure du client.</span><span class="sxs-lookup"><span data-stu-id="13a08-151">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="13a08-152">**Version mineure** Spécifie le numéro qui correspond à la version mineure du client.</span><span class="sxs-lookup"><span data-stu-id="13a08-152">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="13a08-153">**Créer** Spécifie le numéro de build qui correspond à la version majeure et mineure du client.</span><span class="sxs-lookup"><span data-stu-id="13a08-153">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="13a08-154">**Mise à jour** Spécifie le numéro qui correspond à la version mise à jour du client.</span><span class="sxs-lookup"><span data-stu-id="13a08-154">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="13a08-155">**Opération de comparaison** Vous pouvez spécifier l’opération correspondante pour la version du client spécifiée dans les étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="13a08-155">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="13a08-156">Les opérations suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="13a08-156">The following operations are available:</span></span>

  - <span data-ttu-id="13a08-157">**Identique à**</span><span class="sxs-lookup"><span data-stu-id="13a08-157">**Same as**</span></span>

  - <span data-ttu-id="13a08-158">**Différent de**</span><span class="sxs-lookup"><span data-stu-id="13a08-158">**Is not**</span></span>

  - <span data-ttu-id="13a08-159">**Antérieur à**</span><span class="sxs-lookup"><span data-stu-id="13a08-159">**Newer than**</span></span>

  - <span data-ttu-id="13a08-160">**Antérieur ou simultané**</span><span class="sxs-lookup"><span data-stu-id="13a08-160">**Newer than or same as**</span></span>

  - <span data-ttu-id="13a08-161">**Postérieur à**</span><span class="sxs-lookup"><span data-stu-id="13a08-161">**Older than**</span></span>

  - <span data-ttu-id="13a08-162">**Postérieur ou simultané**</span><span class="sxs-lookup"><span data-stu-id="13a08-162">**Older than or same as**</span></span>

- <span data-ttu-id="13a08-163">**Action** Vous pouvez spécifier l’action à exécuter lorsque les critères spécifiés dans les étapes précédentes sont remplis.</span><span class="sxs-lookup"><span data-stu-id="13a08-163">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="13a08-164">Les actions suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="13a08-164">The following actions are available:</span></span>

  - <span data-ttu-id="13a08-165">**Autoriser** Permet au client de se connecter.</span><span class="sxs-lookup"><span data-stu-id="13a08-165">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="13a08-166">**Autoriser et mettre à niveau** Permet au client de se connecter et de recevoir des mises à jour de Windows Server Update service ou de Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="13a08-166">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="13a08-167">Cette action est disponible uniquement en cas de sélection de l’agent utilisateur **OC** .</span><span class="sxs-lookup"><span data-stu-id="13a08-167">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="13a08-168">La sélection de cette action entraîne l’affichage d’une notification lors de la prochaine connexion de l’utilisateur à Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="13a08-168">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="13a08-169">La notification indique qu’une mise à jour est disponible, même si des mises à jour n’ont pas encore été publiées dans Windows Server Update service ou Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="13a08-169">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="13a08-170">Pour éviter toute confusion, ne sélectionnez cette action qu’après que les mises à jour sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="13a08-170">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="13a08-171">**Allow with URL** Permet au client de se connecter et d’afficher un message permettant de télécharger une autre version du client.</span><span class="sxs-lookup"><span data-stu-id="13a08-171">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="13a08-172">Vous devez spécifier l’URL dans le champ **URL**.</span><span class="sxs-lookup"><span data-stu-id="13a08-172">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="13a08-173">**Bloquer** Empêche le client de se connecter.</span><span class="sxs-lookup"><span data-stu-id="13a08-173">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="13a08-174">**Bloquer et mettre à niveau** Empêche le client de se connecter et permet au client de recevoir des mises à jour de Windows Server Update service ou de Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="13a08-174">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="13a08-175">Cette action est disponible uniquement en cas de sélection de l’agent utilisateur **OC** .</span><span class="sxs-lookup"><span data-stu-id="13a08-175">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="13a08-p110">**Bloquer avec une URL** : empêche le client de se connecter et affiche un message à l’emplacement de téléchargement d’une autre version du client. Vous devez spécifier l’URL dans le champ **URL**.</span><span class="sxs-lookup"><span data-stu-id="13a08-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="13a08-178">Pour plus d’informations sur l’interopérabilité entre les clients et les versions de client, voir [interopérabilité client](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="13a08-178">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="13a08-179">Pour plus d’informations sur l’utilisation des configurations de version du client, reportez-vous à la rubrique [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) de la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="13a08-179">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>


---
title: Règle de version du client
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Une stratégie de version de client est composée d’un ensemble de règles de version de client. Ces règles définissent les actions qui doivent être effectuées lorsque les utilisateurs tentent de se connecter avec des clients et des versions de client spécifiques.
ms.openlocfilehash: 870f0d46ff50b4fabab9b4f098cb569ae2c9ee82
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823057"
---
# <a name="client-version-rule"></a><span data-ttu-id="d951b-104">Règle de version du client</span><span class="sxs-lookup"><span data-stu-id="d951b-104">Client Version Rule</span></span>

<span data-ttu-id="d951b-p102">Une stratégie de version de client est composée d’un ensemble de règles de version de client. Ces règles définissent les actions qui doivent être effectuées lorsque les utilisateurs tentent de se connecter avec des clients et des versions de client spécifiques.</span><span class="sxs-lookup"><span data-stu-id="d951b-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="d951b-107">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="d951b-107">Tasks you can perform</span></span>

<span data-ttu-id="d951b-108">Dans la page **Nouvelle configuration de version du client** ou **Modifier la configuration de version du client**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="d951b-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="d951b-109">Ajout de nouvelles règles à une stratégie de version de client</span><span class="sxs-lookup"><span data-stu-id="d951b-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="d951b-110">Modification des règles composant une stratégie de version de client existante</span><span class="sxs-lookup"><span data-stu-id="d951b-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="d951b-111">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="d951b-111">UI Reference</span></span>

<span data-ttu-id="d951b-112">Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="d951b-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="d951b-113">**Agent utilisateur** Vous pouvez sélectionner un type de client dans la liste.</span><span class="sxs-lookup"><span data-stu-id="d951b-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="d951b-114">Le tableau suivant définit les codes des agents utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d951b-114">The following table defines user agent codes.</span></span>

|<span data-ttu-id="d951b-115">**Nom du client**</span><span class="sxs-lookup"><span data-stu-id="d951b-115">**Client Name**</span></span>|<span data-ttu-id="d951b-116">**Agent utilisateur**</span><span class="sxs-lookup"><span data-stu-id="d951b-116">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d951b-117">Lync 2013, Lync 2010, Office Communicator</span><span class="sxs-lookup"><span data-stu-id="d951b-117">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="d951b-118">OC</span><span class="sxs-lookup"><span data-stu-id="d951b-118">OC</span></span>  <br/> |
|<span data-ttu-id="d951b-119">Lync Web App, Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="d951b-119">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="d951b-120">CWA</span><span class="sxs-lookup"><span data-stu-id="d951b-120">CWA</span></span>  <br/> |
|<span data-ttu-id="d951b-121">Lync Phone Edition, téléphone Office Communicator</span><span class="sxs-lookup"><span data-stu-id="d951b-121">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="d951b-122">OCPhone</span><span class="sxs-lookup"><span data-stu-id="d951b-122">OCPhone</span></span>  <br/> |
|<span data-ttu-id="d951b-123">Communicator Phone Edition Platform</span><span class="sxs-lookup"><span data-stu-id="d951b-123">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="d951b-124">CPE</span><span class="sxs-lookup"><span data-stu-id="d951b-124">CPE</span></span>  <br/> |
|<span data-ttu-id="d951b-125">Unified Communications Platform</span><span class="sxs-lookup"><span data-stu-id="d951b-125">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="d951b-126">UCCP</span><span class="sxs-lookup"><span data-stu-id="d951b-126">UCCP</span></span>  <br/> |
|<span data-ttu-id="d951b-127">Lync 2010 participant</span><span class="sxs-lookup"><span data-stu-id="d951b-127">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="d951b-128">AOC</span><span class="sxs-lookup"><span data-stu-id="d951b-128">AOC</span></span>  <br/> |
|<span data-ttu-id="d951b-129">Complément Live Meeting</span><span class="sxs-lookup"><span data-stu-id="d951b-129">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="d951b-130">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="d951b-130">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="d951b-131">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="d951b-131">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="d951b-132">LMC</span><span class="sxs-lookup"><span data-stu-id="d951b-132">LMC</span></span>  <br/> |
|<span data-ttu-id="d951b-133">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="d951b-133">Windows Messenger</span></span>  <br/> |<span data-ttu-id="d951b-134">WM</span><span class="sxs-lookup"><span data-stu-id="d951b-134">WM</span></span>  <br/> |
|<span data-ttu-id="d951b-135">Client Real-time Communications</span><span class="sxs-lookup"><span data-stu-id="d951b-135">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="d951b-136">RTC</span><span class="sxs-lookup"><span data-stu-id="d951b-136">RTC</span></span>  <br/> |
|<span data-ttu-id="d951b-137">Lync 2010 pour iPad</span><span class="sxs-lookup"><span data-stu-id="d951b-137">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="d951b-138">iPadLync</span><span class="sxs-lookup"><span data-stu-id="d951b-138">iPadLync</span></span>  <br/> |
|<span data-ttu-id="d951b-139">Lync 2010 pour iPhone</span><span class="sxs-lookup"><span data-stu-id="d951b-139">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="d951b-140">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="d951b-140">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="d951b-141">Lync 2010 pour Windows Phone</span><span class="sxs-lookup"><span data-stu-id="d951b-141">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="d951b-142">WPLync</span><span class="sxs-lookup"><span data-stu-id="d951b-142">WPLync</span></span>  <br/> |
|<span data-ttu-id="d951b-143">Lync 2010 pour Nokia</span><span class="sxs-lookup"><span data-stu-id="d951b-143">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="d951b-144">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="d951b-144">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="d951b-145">Lync 2010 pour Android</span><span class="sxs-lookup"><span data-stu-id="d951b-145">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="d951b-146">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="d951b-146">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="d951b-147">Mobility Service</span><span class="sxs-lookup"><span data-stu-id="d951b-147">Mobility service</span></span>  <br/> |<span data-ttu-id="d951b-148">McxService</span><span class="sxs-lookup"><span data-stu-id="d951b-148">McxService</span></span>  <br/> |

- <span data-ttu-id="d951b-149">**Numéro de version** Vous pouvez spécifier les numéros de version pour les champs suivants ou utiliser des caractères génériques pour indiquer le numéro de version du client.</span><span class="sxs-lookup"><span data-stu-id="d951b-149">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="d951b-150">**Version principale** Spécifie le numéro qui correspond à la version majeure du client.</span><span class="sxs-lookup"><span data-stu-id="d951b-150">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="d951b-151">**Version mineure** Spécifie le numéro qui correspond à la version mineure du client.</span><span class="sxs-lookup"><span data-stu-id="d951b-151">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="d951b-152">**Créer** Spécifie le numéro de build qui correspond à la version majeure et mineure du client.</span><span class="sxs-lookup"><span data-stu-id="d951b-152">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="d951b-153">**Mise à jour** Spécifie le numéro qui correspond à la version mise à jour du client.</span><span class="sxs-lookup"><span data-stu-id="d951b-153">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="d951b-154">**Opération de comparaison** Vous pouvez spécifier l’opération correspondante pour la version du client spécifiée dans les étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="d951b-154">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="d951b-155">Les opérations suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="d951b-155">The following operations are available:</span></span>

  - <span data-ttu-id="d951b-156">**Identique à**</span><span class="sxs-lookup"><span data-stu-id="d951b-156">**Same as**</span></span>

  - <span data-ttu-id="d951b-157">**Différent de**</span><span class="sxs-lookup"><span data-stu-id="d951b-157">**Is not**</span></span>

  - <span data-ttu-id="d951b-158">**Antérieur à**</span><span class="sxs-lookup"><span data-stu-id="d951b-158">**Newer than**</span></span>

  - <span data-ttu-id="d951b-159">**Antérieur ou simultané**</span><span class="sxs-lookup"><span data-stu-id="d951b-159">**Newer than or same as**</span></span>

  - <span data-ttu-id="d951b-160">**Postérieur à**</span><span class="sxs-lookup"><span data-stu-id="d951b-160">**Older than**</span></span>

  - <span data-ttu-id="d951b-161">**Postérieur ou simultané**</span><span class="sxs-lookup"><span data-stu-id="d951b-161">**Older than or same as**</span></span>

- <span data-ttu-id="d951b-162">**Action** Vous pouvez spécifier l’action à exécuter lorsque les critères spécifiés dans les étapes précédentes sont remplis.</span><span class="sxs-lookup"><span data-stu-id="d951b-162">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="d951b-163">Les actions suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="d951b-163">The following actions are available:</span></span>

  - <span data-ttu-id="d951b-164">**Autoriser** Permet au client de se connecter.</span><span class="sxs-lookup"><span data-stu-id="d951b-164">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="d951b-165">**Autoriser et mettre à niveau** Permet au client de se connecter et de recevoir des mises à jour de Windows Server Update service ou de Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="d951b-165">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="d951b-166">Cette action est disponible uniquement en cas de sélection de l’agent utilisateur **OC** .</span><span class="sxs-lookup"><span data-stu-id="d951b-166">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d951b-167">La sélection de cette action entraîne l’affichage d’une notification lors de la prochaine connexion de l’utilisateur à Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="d951b-167">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="d951b-168">La notification indique qu’une mise à jour est disponible, même si des mises à jour n’ont pas encore été publiées dans Windows Server Update service ou Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="d951b-168">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="d951b-169">Pour éviter toute confusion, ne sélectionnez cette action qu’après que les mises à jour sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="d951b-169">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="d951b-170">**Allow with URL** Permet au client de se connecter et d’afficher un message permettant de télécharger une autre version du client.</span><span class="sxs-lookup"><span data-stu-id="d951b-170">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="d951b-171">Vous devez spécifier l’URL dans le champ **URL**.</span><span class="sxs-lookup"><span data-stu-id="d951b-171">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="d951b-172">**Bloquer** Empêche le client de se connecter.</span><span class="sxs-lookup"><span data-stu-id="d951b-172">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="d951b-173">**Bloquer et mettre à niveau** Empêche le client de se connecter et permet au client de recevoir des mises à jour de Windows Server Update service ou de Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="d951b-173">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="d951b-174">Cette action est disponible uniquement en cas de sélection de l’agent utilisateur **OC** .</span><span class="sxs-lookup"><span data-stu-id="d951b-174">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="d951b-p110">**Bloquer avec une URL** : empêche le client de se connecter et affiche un message à l’emplacement de téléchargement d’une autre version du client. Vous devez spécifier l’URL dans le champ **URL**.</span><span class="sxs-lookup"><span data-stu-id="d951b-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="d951b-p111">Pour plus d’informations sur l’interopérabilité entre les clients et les versions des clients, reportez-vous à la rubrique [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) de la documentation de planification. Pour plus d’informations sur l’utilisation des configurations de version du client, reportez-vous à la rubrique [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) de la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="d951b-p111">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>


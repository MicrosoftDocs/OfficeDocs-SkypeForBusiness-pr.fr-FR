---
title: 'Configuration de version du client : création d’une version ou modification d’une version existante'
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
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
description: Les paramètres de configuration de version du client sont utilisés pour activer ou désactiver le contrôle de version du client. La configuration de la version globale du client s’installe avec Skype Entreprise Server et est utilisée pour activer ou désactiver le contrôle de version du client pour l’ensemble du déploiement du serveur. Lorsque la configuration globale est activée, toutes les stratégies de version du client qui sont en place prendront effet lorsque les utilisateurs tenteront de se connecter. Vous pouvez désactiver la configuration globale de version du client si vous voulez qu’aucun contrôle de la version du client ne se produise.
ms.openlocfilehash: 5567a4de26d29413c049126b90c907383916d71c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800504"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a><span data-ttu-id="5e446-106">Configuration de version du client : création d’une nouvelle ou modification d’une configuration existante</span><span class="sxs-lookup"><span data-stu-id="5e446-106">Client Version Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="5e446-107">Les paramètres de configuration de version du client sont utilisés pour activer ou désactiver le contrôle de version du client.</span><span class="sxs-lookup"><span data-stu-id="5e446-107">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="5e446-108">La configuration de la version globale du client s’installe avec Skype Entreprise Server et est utilisée pour activer ou désactiver le contrôle de version du client pour l’ensemble du déploiement du serveur.</span><span class="sxs-lookup"><span data-stu-id="5e446-108">The Global client version configuration installs with Skype for Business Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="5e446-109">Lorsque la configuration globale est activée, toutes les stratégies de version du client qui sont en place prendront effet lorsque les utilisateurs tenteront de se connecter.</span><span class="sxs-lookup"><span data-stu-id="5e446-109">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="5e446-110">Vous pouvez désactiver la configuration globale de version du client si vous voulez qu’aucun contrôle de la version du client ne se produise.</span><span class="sxs-lookup"><span data-stu-id="5e446-110">You can disable the Global client version configuration if you do not want any client version control to occur.</span></span>

<span data-ttu-id="5e446-p103">Vous pouvez également créer des configurations de version du client spécifiques au site, ce qui vous permet d’activer ou de désactiver le contrôle de la version du client site par site. Les configurations spécifiques au site auront priorité sur la configuration globale.</span><span class="sxs-lookup"><span data-stu-id="5e446-p103">You can also create site-specific client version configurations, allowing you to enable or disable client version control by site. Site-specific configurations take precedence over the Global configuration.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="5e446-113">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="5e446-113">Tasks you can perform</span></span>

<span data-ttu-id="5e446-114">Vous pouvez effectuer les tâches suivantes dans la page **Nouvelle configuration de version du client** ou **Modifier la configuration de version du client** :</span><span class="sxs-lookup"><span data-stu-id="5e446-114">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="5e446-115">Ajouter ou modifier le nom de la configuration de version du client.</span><span class="sxs-lookup"><span data-stu-id="5e446-115">Add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="5e446-116">Activer ou désactiver le contrôle de version du client globalement ou pour le site spécifique.</span><span class="sxs-lookup"><span data-stu-id="5e446-116">Enable or disable client version control globally or for the specific site.</span></span>

- <span data-ttu-id="5e446-117">Ajouter ou modifier l’action par défaut pour la configuration de version du client.</span><span class="sxs-lookup"><span data-stu-id="5e446-117">Add or modify the default action for the client version configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="5e446-118">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="5e446-118">UI Reference</span></span>

<span data-ttu-id="5e446-119">Les listes suivantes décrivent les menus, commandes, champs et propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="5e446-119">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="5e446-120">**Étendue** Identifie l’étendue (globale ou site) de la configuration de version du client.</span><span class="sxs-lookup"><span data-stu-id="5e446-120">**Scope** Identifies the scope (Global or Site) of the client version configuration.</span></span>

- <span data-ttu-id="5e446-121">**Nom** Vous pouvez ajouter ou modifier le nom de la configuration de version du client.</span><span class="sxs-lookup"><span data-stu-id="5e446-121">**Name** You can add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="5e446-122">**Activer le contrôle de version** Vous pouvez activer ou désactiver le contrôle de version du client globalement ou pour le site, en fonction de l’étendue de la configuration.</span><span class="sxs-lookup"><span data-stu-id="5e446-122">**Enable version control** You can enable or disable client version control globally or for the site, depending on the scope of the configuration.</span></span>

- <span data-ttu-id="5e446-123">**Action par défaut** Vous pouvez sélectionner l’action par défaut qui sera appliquée lorsqu’un utilisateur tente de se connecter à l’aide d’une application cliente pour laquelle il n’existe aucune stratégie de version du client spécifique.</span><span class="sxs-lookup"><span data-stu-id="5e446-123">**Default action** You can select the default action that will be applied when a user attempts to log on using a client application for which there is no specific client version policy.</span></span> <span data-ttu-id="5e446-124">Vous avez le choix parmi les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="5e446-124">You have the following options:</span></span>

  - <span data-ttu-id="5e446-125">**Autoriser** Permet au client de se connecter si la version du client ne correspond à aucun filtre dans la liste des stratégies de version du client.</span><span class="sxs-lookup"><span data-stu-id="5e446-125">**Allow** Allows the client to log on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="5e446-126">**Bloquer** Empêche le client de se connecter si la version du client ne correspond à aucun filtre dans la liste des stratégies de version du client.</span><span class="sxs-lookup"><span data-stu-id="5e446-126">**Block** Prevents the client from logging on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="5e446-127">**Bloquer avec une URL** Empêche le client de se connecter si la version du client ne correspond à aucun filtre dans la liste des stratégies de version du client et inclut un message d’erreur contenant une URL dans laquelle un client plus récente peut être téléchargé.</span><span class="sxs-lookup"><span data-stu-id="5e446-127">**Block with URL** Prevents the client from logging on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="5e446-128">**Autoriser avec une URL** Permet au client de se connecter si la version du client ne correspond à aucun filtre dans la liste des stratégies de version du client et inclut un message d’erreur contenant une URL dans laquelle un client plus récente peut être téléchargé.</span><span class="sxs-lookup"><span data-stu-id="5e446-128">**Allow with URL** Allows the client to log on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="5e446-129">**URL** Si vous avez sélectionné **Bloquer avec une URL** ou Autoriser avec une **URL,** vous pouvez spécifier l’URL de téléchargement du client à inclure dans le message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="5e446-129">**URL** If you selected **Block with URL** or **Allow with URL**, you can specify the client download URL to include in the error message.</span></span>

<span data-ttu-id="5e446-130">Pour plus d’informations sur l’interopérabilité entre les clients et les versions des clients, voir [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="5e446-130">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="5e446-131">Pour plus d’informations sur l’utilisation des configurations de version du client, voir [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="5e446-131">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>


---
title: Configuration de la version du client création d’un nouveau ou modification existante
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
ROBOTS: NOINDEX, NOFOLLOW
description: Les paramètres de configuration de version du client sont utilisés pour activer ou désactiver le contrôle de version du client. La configuration de la version du client global s’installe avec Skype entreprise Server et est utilisée pour activer ou désactiver le contrôle de version du client pour le déploiement complet du serveur. Lorsque la configuration globale est activée, toutes les stratégies de version du client en place prendront effet lorsque les utilisateurs tenteront de se connecter. Vous pouvez désactiver la configuration globale de version du client si vous voulez que la version du client ne soit pas contrôlée.
ms.openlocfilehash: c0225947f3346e129768fc6e61dc9484e916be75
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794573"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a><span data-ttu-id="1a274-106">Configuration de version du client : création d’une version ou modification d’une version existante</span><span class="sxs-lookup"><span data-stu-id="1a274-106">Client Version Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="1a274-107">Les paramètres de configuration de version du client sont utilisés pour activer ou désactiver le contrôle de version du client.</span><span class="sxs-lookup"><span data-stu-id="1a274-107">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="1a274-108">La configuration de la version du client global s’installe avec Skype entreprise Server et est utilisée pour activer ou désactiver le contrôle de version du client pour le déploiement complet du serveur.</span><span class="sxs-lookup"><span data-stu-id="1a274-108">The Global client version configuration installs with Skype for Business Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="1a274-109">Lorsque la configuration globale est activée, toutes les stratégies de version du client en place prendront effet lorsque les utilisateurs tenteront de se connecter.</span><span class="sxs-lookup"><span data-stu-id="1a274-109">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="1a274-110">Vous pouvez désactiver la configuration globale de version du client si vous voulez que la version du client ne soit pas contrôlée.</span><span class="sxs-lookup"><span data-stu-id="1a274-110">You can disable the Global client version configuration if you do not want any client version control to occur.</span></span>

<span data-ttu-id="1a274-p103">Vous pouvez également créer des configurations de version du client spécifiques au site, ce qui vous permet d’activer ou de désactiver le contrôle de la version du client site par site. Les configurations spécifiques au site seront prioritaires sur la configuration globale.</span><span class="sxs-lookup"><span data-stu-id="1a274-p103">You can also create site-specific client version configurations, allowing you to enable or disable client version control by site. Site-specific configurations take precedence over the Global configuration.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="1a274-113">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="1a274-113">Tasks you can perform</span></span>

<span data-ttu-id="1a274-114">Dans la page **Nouvelle configuration de version du client** ou **Modifier la configuration de version du client**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="1a274-114">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="1a274-115">Ajout ou modification du nom de la configuration de version du client</span><span class="sxs-lookup"><span data-stu-id="1a274-115">Add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="1a274-116">Activation ou désactivation du contrôle de version du client au niveau global ou pour le site spécifique</span><span class="sxs-lookup"><span data-stu-id="1a274-116">Enable or disable client version control globally or for the specific site.</span></span>

- <span data-ttu-id="1a274-117">Ajout ou modification de l’action par défaut pour la configuration de version du client</span><span class="sxs-lookup"><span data-stu-id="1a274-117">Add or modify the default action for the client version configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="1a274-118">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="1a274-118">UI Reference</span></span>

<span data-ttu-id="1a274-119">Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="1a274-119">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="1a274-120">**Scope** Identifie l’étendue (globale ou site) de la configuration de la version du client.</span><span class="sxs-lookup"><span data-stu-id="1a274-120">**Scope** Identifies the scope (Global or Site) of the client version configuration.</span></span>

- <span data-ttu-id="1a274-121">**Nom** Vous pouvez ajouter ou modifier le nom de la configuration de la version du client.</span><span class="sxs-lookup"><span data-stu-id="1a274-121">**Name** You can add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="1a274-122">**Activer le contrôle de version** Vous pouvez activer ou désactiver le contrôle de version du client globalement ou pour le site, en fonction de l’étendue de la configuration.</span><span class="sxs-lookup"><span data-stu-id="1a274-122">**Enable version control** You can enable or disable client version control globally or for the site, depending on the scope of the configuration.</span></span>

- <span data-ttu-id="1a274-123">**Action par défaut** Vous pouvez sélectionner l’action par défaut qui sera appliquée lorsqu’un utilisateur tente de se connecter à l’aide d’une application cliente pour laquelle il n’existe aucune stratégie de version de client spécifique.</span><span class="sxs-lookup"><span data-stu-id="1a274-123">**Default action** You can select the default action that will be applied when a user attempts to log on using a client application for which there is no specific client version policy.</span></span> <span data-ttu-id="1a274-124">Les options suivantes s’offrent à vous :</span><span class="sxs-lookup"><span data-stu-id="1a274-124">You have the following options:</span></span>

  - <span data-ttu-id="1a274-125">**Autoriser** Permet au client de se connecter si la version du client ne correspond à aucun filtre dans la liste des stratégies de la version du client.</span><span class="sxs-lookup"><span data-stu-id="1a274-125">**Allow** Allows the client to log on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="1a274-126">**Bloquer** Empêche le client de se connecter si la version du client ne correspond à aucun filtre dans la liste des stratégies de la version du client.</span><span class="sxs-lookup"><span data-stu-id="1a274-126">**Block** Prevents the client from logging on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="1a274-127">**Bloquer avec l’URL** Empêche le client de se connecter si la version du client ne correspond à aucun filtre dans la liste des stratégies de la version du client, et qu’il inclut un message d’erreur contenant une URL dans laquelle un client plus récent peut être téléchargé.</span><span class="sxs-lookup"><span data-stu-id="1a274-127">**Block with URL** Prevents the client from logging on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="1a274-128">**Allow with URL** Permet au client de se connecter si la version du client ne correspond à aucun filtre dans la liste des stratégies de la version du client, et qu’il inclut un message d’erreur contenant une URL dans laquelle un client plus récent peut être téléchargé.</span><span class="sxs-lookup"><span data-stu-id="1a274-128">**Allow with URL** Allows the client to log on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="1a274-129">**URL (URL** ) Si vous avez sélectionné **bloquer avec une URL** ou **autoriser avec l’URL**, vous pouvez spécifier l’URL de téléchargement du client à inclure dans le message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="1a274-129">**URL** If you selected **Block with URL** or **Allow with URL**, you can specify the client download URL to include in the error message.</span></span>

<span data-ttu-id="1a274-130">Pour plus d’informations sur l’interopérabilité entre les clients et les versions de client, voir [interopérabilité client](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="1a274-130">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="1a274-131">Pour plus d’informations sur l’utilisation des configurations de version du client, reportez-vous à la rubrique [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) de la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="1a274-131">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>


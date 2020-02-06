---
title: Configuration de version du client
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
ROBOTS: NOINDEX, NOFOLLOW
description: En plus de spécifier la version de clients que vous voulez prendre en charge dans votre environnement, vous pouvez également spécifier une action par défaut pour les clients qui n’ont pas encore de stratégie de version définie. Cela vous permet de limiter les versions de client utilisées dans votre environnement, qui peuvent vous aider à contrôler les coûts associés à la prise en charge de plusieurs versions de client.
ms.openlocfilehash: e5675a2b3cab2309a78c2d8dc88041beee8cc619
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794563"
---
# <a name="client-version-configuration"></a><span data-ttu-id="5f2e0-104">Configuration de version du client</span><span class="sxs-lookup"><span data-stu-id="5f2e0-104">Client Version Configuration</span></span>

<span data-ttu-id="5f2e0-105">En plus de spécifier la version de clients que vous voulez prendre en charge dans votre environnement, vous pouvez également spécifier une action par défaut pour les clients qui n’ont pas encore de stratégie de version définie.</span><span class="sxs-lookup"><span data-stu-id="5f2e0-105">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="5f2e0-106">Cela vous permet de limiter les versions de client utilisées dans votre environnement, qui peuvent vous aider à contrôler les coûts associés à la prise en charge de plusieurs versions de client.</span><span class="sxs-lookup"><span data-stu-id="5f2e0-106">This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="5f2e0-107">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="5f2e0-107">Tasks you can perform</span></span>

<span data-ttu-id="5f2e0-108">Vous pouvez effectuer les tâches suivantes sur la page de configuration de la **version du client** :</span><span class="sxs-lookup"><span data-stu-id="5f2e0-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>

- <span data-ttu-id="5f2e0-109">Modifiez la configuration de la version du client par défaut ( **Global**).</span><span class="sxs-lookup"><span data-stu-id="5f2e0-109">Edit the default ( **Global**) client version configuration.</span></span>

- <span data-ttu-id="5f2e0-110">Créer une configuration de version de client pour un site particulier.</span><span class="sxs-lookup"><span data-stu-id="5f2e0-110">Create client version configuration for a particular site.</span></span>

- <span data-ttu-id="5f2e0-111">Activez et désactivez les configurations de version de client existantes.</span><span class="sxs-lookup"><span data-stu-id="5f2e0-111">Enable and disable existing client version configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="5f2e0-112">Étant donné que les utilisateurs anonymes ne sont pas associés à un site, les utilisateurs anonymes sont affectés par les stratégies de niveau global uniquement.</span><span class="sxs-lookup"><span data-stu-id="5f2e0-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="5f2e0-113">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="5f2e0-113">UI Reference</span></span>

<span data-ttu-id="5f2e0-114">Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="5f2e0-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="5f2e0-115">**Nouvelle** Vous pouvez créer une configuration de version de client pour un site particulier.</span><span class="sxs-lookup"><span data-stu-id="5f2e0-115">**New** You can create a client version configuration for a particular site.</span></span>

- <span data-ttu-id="5f2e0-116">**Modifier** Vous pouvez modifier les options de n’importe quelle stratégie de version du client.</span><span class="sxs-lookup"><span data-stu-id="5f2e0-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="5f2e0-117">Cette option vous permet d’effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5f2e0-117">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="5f2e0-118">**Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options de configuration d’une version de client.</span><span class="sxs-lookup"><span data-stu-id="5f2e0-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>

  - <span data-ttu-id="5f2e0-119">**Tout sélectionner** Cette option sélectionne toutes les configurations de version de client dans la liste.</span><span class="sxs-lookup"><span data-stu-id="5f2e0-119">**Select All** This option selects all client version configurations in the list.</span></span>

  - <span data-ttu-id="5f2e0-120">**Supprimer** Cette option supprime toutes les configurations de version de client sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="5f2e0-120">**Delete** This option deletes all selected client version configurations.</span></span>

- <span data-ttu-id="5f2e0-121">**Actualiser** Vous pouvez actualiser la liste de configuration de la version du client pour vérifier l’état des options de toutes les configurations de version du client.</span><span class="sxs-lookup"><span data-stu-id="5f2e0-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>

<span data-ttu-id="5f2e0-122">Pour plus d’informations sur l’interopérabilité entre les clients et les versions de client, voir [interopérabilité client](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="5f2e0-122">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="5f2e0-123">Pour plus d’informations sur l’utilisation des configurations de version du client, reportez-vous à la rubrique [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) de la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="5f2e0-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>


---
title: Stratégie de version du client
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
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
description: Vous pouvez spécifier la version des clients pris en charge dans votre environnement. Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités accessibles à l’un des clients peuvent être limitées par les capacités de l’autre client. Pour utiliser au mieux les fonctionnalités incluses dans Skype Entreprise Server 2015 et améliorer l’expérience utilisateur globale, vous pouvez utiliser le filtre de version du client pour limiter les versions des clients utilisées dans votre environnement. Le filtre de version du client vous permet également de réduire les coûts associés à la prise en charge de plusieurs versions du client.
ms.openlocfilehash: 0af11ac26a73452412c653c04233df7b932f2b49
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118643"
---
# <a name="client-version-policy"></a><span data-ttu-id="0e0d3-106">Stratégie de version du client</span><span class="sxs-lookup"><span data-stu-id="0e0d3-106">Client Version Policy</span></span>

<span data-ttu-id="0e0d3-107">Vous pouvez spécifier la version des clients pris en charge dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="0e0d3-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="0e0d3-108">Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités accessibles à l’un des clients peuvent être limitées par les capacités de l’autre client.</span><span class="sxs-lookup"><span data-stu-id="0e0d3-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="0e0d3-109">Pour utiliser au mieux les fonctionnalités incluses dans Skype Entreprise Server 2015 et améliorer l’expérience utilisateur globale, vous pouvez utiliser le filtre de version du client pour limiter les versions des clients utilisées dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="0e0d3-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="0e0d3-110">Le filtre de version du client vous permet également de réduire les coûts associés à la prise en charge de plusieurs versions du client.</span><span class="sxs-lookup"><span data-stu-id="0e0d3-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="0e0d3-111">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="0e0d3-111">Tasks you can perform</span></span>

<span data-ttu-id="0e0d3-112">Vous pouvez effectuer les tâches suivantes dans la page **Stratégie de version du client** :</span><span class="sxs-lookup"><span data-stu-id="0e0d3-112">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="0e0d3-113">Modifiez la **stratégie** de version du client par défaut ( globale).</span><span class="sxs-lookup"><span data-stu-id="0e0d3-113">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="0e0d3-114">Créer des stratégies de version du client pour un site ou un pool particulier.</span><span class="sxs-lookup"><span data-stu-id="0e0d3-114">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="0e0d3-115">Créer des stratégies de version du client qui peuvent être attribuées à des utilisateurs individuels.</span><span class="sxs-lookup"><span data-stu-id="0e0d3-115">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="0e0d3-116">Comme ils ne sont pas associés à un utilisateur, un site ou un service spécifique, les utilisateurs anonymes sont uniquement affectés par les stratégies globales.</span><span class="sxs-lookup"><span data-stu-id="0e0d3-116">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="0e0d3-117">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="0e0d3-117">UI Reference</span></span>

<span data-ttu-id="0e0d3-118">Les listes suivantes décrivent les menus, commandes, champs et propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="0e0d3-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="0e0d3-119">**Nouveau** Vous pouvez créer une ou plusieurs des stratégies de version des clients suivantes :</span><span class="sxs-lookup"><span data-stu-id="0e0d3-119">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="0e0d3-120">Stratégie de site</span><span class="sxs-lookup"><span data-stu-id="0e0d3-120">Site policy</span></span>

  - <span data-ttu-id="0e0d3-121">Stratégie de pool</span><span class="sxs-lookup"><span data-stu-id="0e0d3-121">Pool policy</span></span>

  - <span data-ttu-id="0e0d3-122">Stratégie de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="0e0d3-122">User policy</span></span>

- <span data-ttu-id="0e0d3-123">**Modifier** Vous pouvez modifier les options de n’importe quelle stratégie de version du client.</span><span class="sxs-lookup"><span data-stu-id="0e0d3-123">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="0e0d3-124">À l’aide de cette option, vous pouvez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0e0d3-124">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="0e0d3-125">**Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options d’une stratégie de version du client.</span><span class="sxs-lookup"><span data-stu-id="0e0d3-125">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="0e0d3-126">**Sélectionner tout** Cette option sélectionne toutes les stratégies de version des clients dans la liste.</span><span class="sxs-lookup"><span data-stu-id="0e0d3-126">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="0e0d3-127">**Supprimer** Cette option supprime toutes les stratégies de version des clients sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="0e0d3-127">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="0e0d3-128">**Actualiser** Vous pouvez actualiser la liste des stratégies de version des clients pour vérifier l’état des options de toutes les stratégies de version des clients.</span><span class="sxs-lookup"><span data-stu-id="0e0d3-128">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="0e0d3-129">Pour plus d’informations sur l’interopérabilité entre les clients et les versions des clients, voir [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="0e0d3-129">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="0e0d3-130">Pour plus d’informations sur l’utilisation des stratégies de version du client, voir [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="0e0d3-130">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) in the Operations documentation.</span></span>
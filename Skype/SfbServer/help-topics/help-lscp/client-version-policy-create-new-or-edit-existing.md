---
title: 'Stratégie de version du client : création d’une stratégie ou modification d’une stratégie existante'
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
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: Vous pouvez spécifier la version des clients pris en charge dans votre environnement. Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités accessibles à l’un des clients peuvent être limitées par les capacités de l’autre client. Pour utiliser au mieux les fonctionnalités incluses dans Skype Entreprise Server 2015 et améliorer l’expérience utilisateur globale, vous pouvez utiliser le filtre de version du client pour limiter les versions des clients utilisées dans votre environnement. Le filtre de version du client vous permet également de réduire les coûts associés à la prise en charge de plusieurs versions du client.
ms.openlocfilehash: db463896426d8919776ba21532bbac04415c526d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829514"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="a4a65-106">Stratégie de version du client : création d’une nouvelle ou modification d’une stratégie existante</span><span class="sxs-lookup"><span data-stu-id="a4a65-106">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="a4a65-107">Vous pouvez spécifier la version des clients pris en charge dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="a4a65-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="a4a65-108">Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités accessibles à l’un des clients peuvent être limitées par les capacités de l’autre client.</span><span class="sxs-lookup"><span data-stu-id="a4a65-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="a4a65-109">Pour utiliser au mieux les fonctionnalités incluses dans Skype Entreprise Server 2015 et améliorer l’expérience utilisateur globale, vous pouvez utiliser le filtre de version du client pour limiter les versions des clients utilisées dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="a4a65-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="a4a65-110">Le filtre de version du client vous permet également de réduire les coûts associés à la prise en charge de plusieurs versions du client.</span><span class="sxs-lookup"><span data-stu-id="a4a65-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4a65-p103">Les filtres sont répertoriés par ordre de priorité. Par exemple, si un premier filtre autorise les clients exécutant la version 1.5 à se connecter et qu’un second filtre bloque les clients exécutant une version antérieure à la version 2.0, le premier filtre est prioritaire : les clients exécutant la version 1.5 peuvent donc se connecter.</span><span class="sxs-lookup"><span data-stu-id="a4a65-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="a4a65-113">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="a4a65-113">Tasks you can perform</span></span>

<span data-ttu-id="a4a65-114">Vous pouvez effectuer les tâches suivantes dans la page **Nouvelle stratégie de version du client** ou **Modifier la stratégie de version du client** :</span><span class="sxs-lookup"><span data-stu-id="a4a65-114">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="a4a65-115">Ajouter ou modifier le nom ou la description de la stratégie de version du client</span><span class="sxs-lookup"><span data-stu-id="a4a65-115">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="a4a65-116">Ajouter ou modifier des règles de version de client pour la stratégie de version du client</span><span class="sxs-lookup"><span data-stu-id="a4a65-116">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="a4a65-117">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="a4a65-117">UI Reference</span></span>

<span data-ttu-id="a4a65-118">Les listes suivantes décrivent les menus, commandes, champs et propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="a4a65-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="a4a65-119">**Étendue** Identifie l’étendue (site, pool ou utilisateur) de la stratégie de version du client.</span><span class="sxs-lookup"><span data-stu-id="a4a65-119">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="a4a65-120">**Nom** Vous pouvez ajouter ou modifier le nom de la stratégie de version du client.</span><span class="sxs-lookup"><span data-stu-id="a4a65-120">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="a4a65-121">**Description** Vous pouvez ajouter une description pour vous aider à identifier la stratégie dans la liste de la page Stratégie de version du client.</span><span class="sxs-lookup"><span data-stu-id="a4a65-121">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="a4a65-122">**Nouveau** Vous pouvez ajouter une nouvelle règle de version du client à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="a4a65-122">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="a4a65-123">**Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options d’une règle de version du client.</span><span class="sxs-lookup"><span data-stu-id="a4a65-123">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="a4a65-124">**Supprimer** Cette option supprime la règle de version du client sélectionnée de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="a4a65-124">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="a4a65-125">**Flèches haut et bas** Cette option déplace la règle de version du client sélectionnée vers le haut ou vers le bas en priorité.</span><span class="sxs-lookup"><span data-stu-id="a4a65-125">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="a4a65-126">Les règles sont traitées dans l’ordre répertorié.</span><span class="sxs-lookup"><span data-stu-id="a4a65-126">Rules are processed in the order listed.</span></span>

<span data-ttu-id="a4a65-127">Pour plus d’informations sur l’interopérabilité entre les clients et les versions des clients, voir [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="a4a65-127">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="a4a65-128">Pour plus d’informations sur l’utilisation des stratégies de version du client, voir [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="a4a65-128">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>


---
title: Stratégie de Version du client créer ou modifier une existant
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
ROBOTS: NOINDEX, NOFOLLOW
description: Vous pouvez spécifier la version des clients pris en charge dans votre environnement. Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités disponibles pour l’un des clients peuvent être restreintes par les fonctions de l’autre client.
ms.openlocfilehash: 5648d96e69869171d78a3a28634bdb2b0221a234
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216402"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="17309-104">Stratégie de version du client : création d’une stratégie ou modification d’une stratégie existante</span><span class="sxs-lookup"><span data-stu-id="17309-104">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="17309-105">Vous pouvez spécifier la version des clients pris en charge dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="17309-105">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="17309-106">Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités disponibles pour l’un des clients peuvent être restreintes par les fonctions de l’autre client.</span><span class="sxs-lookup"><span data-stu-id="17309-106">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="17309-107">Pour rendre l’utilisation des fonctionnalités incluses dans Skype pour Business Server plus grande et pour améliorer l’expérience utilisateur globale, vous pouvez utiliser le filtre de version du client pour limiter les versions du client qui sont utilisées dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="17309-107">To make the greatest use of features included in Skype for Business Server and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="17309-108">Le filtre de version du client vous permet également de réduire les coûts associés à la prise en charge de différentes versions du client.</span><span class="sxs-lookup"><span data-stu-id="17309-108">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="17309-p103">Les filtres sont répertoriés par ordre de priorité. Par exemple, si un premier filtre autorise les clients exécutant la version 1.5 à se connecter et qu’un second filtre bloque les clients exécutant une version antérieure à la version 2.0, le premier filtre est prioritaire : les clients exécutant la version 1.5 peuvent donc se connecter.</span><span class="sxs-lookup"><span data-stu-id="17309-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="17309-111">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="17309-111">Tasks you can perform</span></span>

<span data-ttu-id="17309-112">Dans la page **Nouvelle stratégie de version du client** ou **Modifier la stratégie de version du client**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="17309-112">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="17309-113">Ajout ou modification du nom ou de la description de la stratégie de version du client</span><span class="sxs-lookup"><span data-stu-id="17309-113">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="17309-114">Ajout ou modification des règles de version de client pour la stratégie de version du client</span><span class="sxs-lookup"><span data-stu-id="17309-114">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="17309-115">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="17309-115">UI Reference</span></span>

<span data-ttu-id="17309-116">Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="17309-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="17309-117">**Étendue** Identifie l’étendue (Pool, Site ou utilisateur) de la stratégie de version du client.</span><span class="sxs-lookup"><span data-stu-id="17309-117">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="17309-118">**Nom** Vous pouvez ajouter ou modifier le nom de la stratégie de version du client.</span><span class="sxs-lookup"><span data-stu-id="17309-118">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="17309-119">**Description** Vous pouvez ajouter une description pour aider à identifier la stratégie dans la liste dans la page Stratégie de Version du Client.</span><span class="sxs-lookup"><span data-stu-id="17309-119">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="17309-120">**Nouveau** Vous pouvez ajouter une nouvelle règle de version de client à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="17309-120">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="17309-121">**Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options pour une règle de version du client.</span><span class="sxs-lookup"><span data-stu-id="17309-121">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="17309-122">**Supprimer** Cette option supprime la règle de version de client sélectionnée de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="17309-122">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="17309-123">**Flèches haut et bas** Cette option déplace la règle de version de client sélectionnée monter ou Descendre dans la priorité.</span><span class="sxs-lookup"><span data-stu-id="17309-123">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="17309-124">Les règles sont traitées dans l’ordre indiqué.</span><span class="sxs-lookup"><span data-stu-id="17309-124">Rules are processed in the order listed.</span></span>

<span data-ttu-id="17309-125">Pour plus d’informations sur l’interopérabilité entre les clients et les versions du client, voir [Interopérabilité des clients](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx).</span><span class="sxs-lookup"><span data-stu-id="17309-125">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx).</span></span> <span data-ttu-id="17309-126">Pour plus d’informations sur l’utilisation des stratégies de version du client, reportez-vous à la rubrique[Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) de la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="17309-126">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>


---
title: Stratégie de version du client
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
ROBOTS: NOINDEX, NOFOLLOW
description: Vous pouvez spécifier la version des clients pris en charge dans votre environnement. Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités accessibles à l’un des clients peuvent être limitées par les capacités de l’autre client.
ms.openlocfilehash: c52921df4e68b8273a4e87af0cfe54105e8a10ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812394"
---
# <a name="client-version-policy"></a><span data-ttu-id="a9448-104">Stratégie de version du client</span><span class="sxs-lookup"><span data-stu-id="a9448-104">Client Version Policy</span></span>

<span data-ttu-id="a9448-105">Vous pouvez spécifier la version des clients pris en charge dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="a9448-105">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="a9448-106">Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités accessibles à l’un des clients peuvent être limitées par les capacités de l’autre client.</span><span class="sxs-lookup"><span data-stu-id="a9448-106">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="a9448-107">Pour utiliser au mieux les fonctionnalités incluses dans Skype Entreprise Server et améliorer l’expérience utilisateur globale, vous pouvez utiliser le filtre de version du client pour limiter les versions des clients utilisées dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="a9448-107">To make the greatest use of features included in Skype for Business Server and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="a9448-108">Le filtre de version du client vous permet également de réduire les coûts associés à la prise en charge de plusieurs versions du client.</span><span class="sxs-lookup"><span data-stu-id="a9448-108">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="a9448-109">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="a9448-109">Tasks you can perform</span></span>

<span data-ttu-id="a9448-110">Vous pouvez effectuer les tâches suivantes dans la page **Stratégie de version du client** :</span><span class="sxs-lookup"><span data-stu-id="a9448-110">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="a9448-111">Modifiez la **stratégie** de version du client par défaut ( globale).</span><span class="sxs-lookup"><span data-stu-id="a9448-111">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="a9448-112">Créer des stratégies de version du client pour un site ou un pool particulier.</span><span class="sxs-lookup"><span data-stu-id="a9448-112">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="a9448-113">Créer des stratégies de version du client qui peuvent être attribuées à des utilisateurs individuels.</span><span class="sxs-lookup"><span data-stu-id="a9448-113">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="a9448-114">Comme ils ne sont pas associés à un utilisateur, un site ou un service spécifique, les utilisateurs anonymes sont uniquement affectés par les stratégies globales.</span><span class="sxs-lookup"><span data-stu-id="a9448-114">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="a9448-115">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="a9448-115">UI Reference</span></span>

<span data-ttu-id="a9448-116">Les listes suivantes décrivent les menus, commandes, champs et propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="a9448-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="a9448-117">**Nouveau** Vous pouvez créer une ou plusieurs des stratégies de version des clients suivantes :</span><span class="sxs-lookup"><span data-stu-id="a9448-117">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="a9448-118">Stratégie de site</span><span class="sxs-lookup"><span data-stu-id="a9448-118">Site policy</span></span>

  - <span data-ttu-id="a9448-119">Stratégie de pool</span><span class="sxs-lookup"><span data-stu-id="a9448-119">Pool policy</span></span>

  - <span data-ttu-id="a9448-120">Stratégie de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="a9448-120">User policy</span></span>

- <span data-ttu-id="a9448-121">**Modifier** Vous pouvez modifier les options de n’importe quelle stratégie de version du client.</span><span class="sxs-lookup"><span data-stu-id="a9448-121">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="a9448-122">À l’aide de cette option, vous pouvez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a9448-122">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="a9448-123">**Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options d’une stratégie de version du client.</span><span class="sxs-lookup"><span data-stu-id="a9448-123">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="a9448-124">**Sélectionner tout** Cette option sélectionne toutes les stratégies de version des clients dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a9448-124">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="a9448-125">**Supprimer** Cette option supprime toutes les stratégies de version des clients sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="a9448-125">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="a9448-126">**Actualiser** Vous pouvez actualiser la liste des stratégies de version des clients pour vérifier l’état des options de toutes les stratégies de version des clients.</span><span class="sxs-lookup"><span data-stu-id="a9448-126">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="a9448-127">Pour plus d’informations sur l’interopérabilité entre les clients et les versions des clients, voir [Interopérabilité](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) du client dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="a9448-127">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="a9448-128">Pour plus d’informations sur l’utilisation des stratégies de version du client, voir [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="a9448-128">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>


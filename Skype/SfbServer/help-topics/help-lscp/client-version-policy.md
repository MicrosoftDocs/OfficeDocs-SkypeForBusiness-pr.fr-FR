---
title: Stratégie de version du client
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
description: Vous pouvez spécifier la version des clients pris en charge dans votre environnement. Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités disponibles pour l’un des clients peuvent être restreintes par les fonctions de l’autre client. Pour utiliser plus de fonctionnalités incluses dans Skype pour Business Server 2015 et pour améliorer l’expérience utilisateur globale, vous pouvez utiliser le filtre de version du client pour limiter les versions du client qui sont utilisées dans votre environnement. Le filtre de version du client vous permet également de réduire les coûts associés à la prise en charge de différentes versions du client.
ms.openlocfilehash: 67524a0f00a4251db3a16667340c959ca3628547
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23247016"
---
# <a name="client-version-policy"></a><span data-ttu-id="d61a8-106">Stratégie de version du client</span><span class="sxs-lookup"><span data-stu-id="d61a8-106">Client Version Policy</span></span>

<span data-ttu-id="d61a8-107">Vous pouvez spécifier la version des clients pris en charge dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="d61a8-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="d61a8-108">Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités disponibles pour l’un des clients peuvent être restreintes par les fonctions de l’autre client.</span><span class="sxs-lookup"><span data-stu-id="d61a8-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="d61a8-109">Pour utiliser plus de fonctionnalités incluses dans Skype pour Business Server 2015 et pour améliorer l’expérience utilisateur globale, vous pouvez utiliser le filtre de version du client pour limiter les versions du client qui sont utilisées dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="d61a8-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="d61a8-110">Le filtre de version du client vous permet également de réduire les coûts associés à la prise en charge de différentes versions du client.</span><span class="sxs-lookup"><span data-stu-id="d61a8-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="d61a8-111">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="d61a8-111">Tasks you can perform</span></span>

<span data-ttu-id="d61a8-112">Dans la page **Stratégie de version du client**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="d61a8-112">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="d61a8-113">Modifier la stratégie de version du client par défaut ( **Global**).</span><span class="sxs-lookup"><span data-stu-id="d61a8-113">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="d61a8-114">Création des stratégies de version du client pour un site ou un pool particulier</span><span class="sxs-lookup"><span data-stu-id="d61a8-114">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="d61a8-115">Création des stratégies de version du client qui peuvent être affectées à des utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="d61a8-115">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="d61a8-116">Comme ils ne sont pas associés à un utilisateur, un site ou un service spécifiques, les utilisateurs anonymes ne sont affectés que par les stratégies globales.</span><span class="sxs-lookup"><span data-stu-id="d61a8-116">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="d61a8-117">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="d61a8-117">UI Reference</span></span>

<span data-ttu-id="d61a8-118">Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="d61a8-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="d61a8-119">**Nouveau** Vous pouvez créer une ou plusieurs des stratégies de version des clients suivants :</span><span class="sxs-lookup"><span data-stu-id="d61a8-119">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="d61a8-120">Stratégie de site</span><span class="sxs-lookup"><span data-stu-id="d61a8-120">Site policy</span></span>

  - <span data-ttu-id="d61a8-121">Stratégie de pool</span><span class="sxs-lookup"><span data-stu-id="d61a8-121">Pool policy</span></span>

  - <span data-ttu-id="d61a8-122">Stratégie utilisateur</span><span class="sxs-lookup"><span data-stu-id="d61a8-122">User policy</span></span>

- <span data-ttu-id="d61a8-123">**Modifier** Vous pouvez modifier les options d’une des stratégies de version des clients.</span><span class="sxs-lookup"><span data-stu-id="d61a8-123">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="d61a8-124">Utilisez cette option, vous pouvez procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d61a8-124">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="d61a8-125">**Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options pour une stratégie de version du client.</span><span class="sxs-lookup"><span data-stu-id="d61a8-125">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="d61a8-126">**Sélectionner tout** Cette option sélectionne toutes les stratégies de version de client dans la liste.</span><span class="sxs-lookup"><span data-stu-id="d61a8-126">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="d61a8-127">**Supprimer** Cette option supprime toutes les stratégies de version de client sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d61a8-127">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="d61a8-128">**Actualiser** Vous pouvez actualiser la liste de stratégie de version de client pour vérifier le statut des options de toutes les stratégies de version du client.</span><span class="sxs-lookup"><span data-stu-id="d61a8-128">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="d61a8-129">Pour plus d’informations sur l’interopérabilité entre les clients et les versions du client, voir [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="d61a8-129">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="d61a8-130">Pour plus d’informations sur l’utilisation des stratégies de version du client, voir [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="d61a8-130">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>


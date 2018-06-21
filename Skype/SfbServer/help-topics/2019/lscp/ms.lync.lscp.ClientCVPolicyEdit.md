---
title: Stratégie de Version du client créer ou modifier une existant
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
description: Vous pouvez spécifier la version des clients pris en charge dans votre environnement. Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités disponibles pour l’un des clients peuvent être restreintes par les fonctions de l’autre client. Pour rendre l’utilisation des fonctionnalités incluses dans Skype pour Business Server plus grande et pour améliorer l’expérience utilisateur globale, vous pouvez utiliser le filtre de version du client pour limiter les versions du client qui sont utilisées dans votre environnement. Le filtre de version du client vous permet également de réduire les coûts associés à la prise en charge de différentes versions du client.
ms.openlocfilehash: bf1e521a5c847bff8968364556d51b82d0f934e2
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/20/2018
ms.locfileid: "19969595"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="45161-106">Stratégie de version du client : création d’une stratégie ou modification d’une stratégie existante</span><span class="sxs-lookup"><span data-stu-id="45161-106">Client Version Policy: Create New or Edit Existing</span></span>
 
<span data-ttu-id="45161-107">Vous pouvez spécifier la version des clients pris en charge dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="45161-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="45161-108">Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités disponibles pour l’un des clients peuvent être restreintes par les fonctions de l’autre client.</span><span class="sxs-lookup"><span data-stu-id="45161-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="45161-109">Pour rendre l’utilisation des fonctionnalités incluses dans Skype pour Business Server plus grande et pour améliorer l’expérience utilisateur globale, vous pouvez utiliser le filtre de version du client pour limiter les versions du client qui sont utilisées dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="45161-109">To make the greatest use of features included in Skype for Business Server and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="45161-110">Le filtre de version du client vous permet également de réduire les coûts associés à la prise en charge de différentes versions du client.</span><span class="sxs-lookup"><span data-stu-id="45161-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="45161-p103">Les filtres sont répertoriés par ordre de priorité. Par exemple, si un premier filtre autorise les clients exécutant la version 1.5 à se connecter et qu’un second filtre bloque les clients exécutant une version antérieure à la version 2.0, le premier filtre est prioritaire : les clients exécutant la version 1.5 peuvent donc se connecter.</span><span class="sxs-lookup"><span data-stu-id="45161-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="45161-113">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="45161-113">Tasks you can perform</span></span>

<span data-ttu-id="45161-114">Dans la page **Nouvelle stratégie de version du client** ou **Modifier la stratégie de version du client**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="45161-114">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>
  
- <span data-ttu-id="45161-115">Ajout ou modification du nom ou de la description de la stratégie de version du client</span><span class="sxs-lookup"><span data-stu-id="45161-115">Add or modify the name or description of the client version policy.</span></span>
    
- <span data-ttu-id="45161-116">Ajout ou modification des règles de version de client pour la stratégie de version du client</span><span class="sxs-lookup"><span data-stu-id="45161-116">Add or modify client version rules for the client version policy.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="45161-117">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="45161-117">UI Reference</span></span>

<span data-ttu-id="45161-118">Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="45161-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="45161-119">**Étendue** Identifie l’étendue (Pool, Site ou utilisateur) de la stratégie de version du client.</span><span class="sxs-lookup"><span data-stu-id="45161-119">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>
    
- <span data-ttu-id="45161-120">**Nom** Vous pouvez ajouter ou modifier le nom de la stratégie de version du client.</span><span class="sxs-lookup"><span data-stu-id="45161-120">**Name** You can add or modify the name of the client version policy.</span></span>
    
- <span data-ttu-id="45161-121">**Description** Vous pouvez ajouter une description pour aider à identifier la stratégie dans la liste dans la page Stratégie de Version du Client.</span><span class="sxs-lookup"><span data-stu-id="45161-121">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>
    
- <span data-ttu-id="45161-122">**Nouveau** Vous pouvez ajouter une nouvelle règle de version de client à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="45161-122">**New** You can add a new client version rule to the policy.</span></span>
    
- <span data-ttu-id="45161-123">**Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options pour une règle de version du client.</span><span class="sxs-lookup"><span data-stu-id="45161-123">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>
    
- <span data-ttu-id="45161-124">**Supprimer** Cette option supprime la règle de version de client sélectionnée de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="45161-124">**Remove** This option removes the selected client version rule from the policy.</span></span>
    
- <span data-ttu-id="45161-125">**Flèches haut et bas** Cette option déplace la règle de version de client sélectionnée monter ou Descendre dans la priorité.</span><span class="sxs-lookup"><span data-stu-id="45161-125">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="45161-126">Les règles sont traitées dans l’ordre indiqué.</span><span class="sxs-lookup"><span data-stu-id="45161-126">Rules are processed in the order listed.</span></span>
    
<span data-ttu-id="45161-127">Pour plus d’informations sur l’interopérabilité entre les clients et les versions du client, voir [Interopérabilité des clients](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="45161-127">For details about interoperability among clients and client versions, see [Client Interoperability](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="45161-128">Pour plus d’informations sur l’utilisation des stratégies de version du client, voir [Specify the Client Versions Supported in Your Organization](http://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="45161-128">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](http://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>


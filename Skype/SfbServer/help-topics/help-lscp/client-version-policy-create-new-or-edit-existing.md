---
title: Stratégie de Version de client, créer ou modifier une existante
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: Vous pouvez spécifier la version des clients pris en charge dans votre environnement. Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités disponibles pour l’un des clients peuvent être restreintes par les fonctions de l’autre client. Pour rendre l’utilisation de plus de fonctionnalités incluses dans Skype pour Business Server 2015 et d’améliorer l’expérience utilisateur globale, vous pouvez utiliser le filtre de la version client pour restreindre les versions de client qui sont utilisées dans votre environnement. Le filtre de version du client vous permet également de réduire les coûts associés à la prise en charge de différentes versions du client.
ms.openlocfilehash: 6c1e895dc03d094013f41a34cb21a12a24928172
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="605b1-106">Stratégie de version du client : création d’une stratégie ou modification d’une stratégie existante</span><span class="sxs-lookup"><span data-stu-id="605b1-106">Client Version Policy: Create New or Edit Existing</span></span>
 
<span data-ttu-id="605b1-107">Vous pouvez spécifier la version des clients pris en charge dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="605b1-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="605b1-108">Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités disponibles pour l’un des clients peuvent être restreintes par les fonctions de l’autre client.</span><span class="sxs-lookup"><span data-stu-id="605b1-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="605b1-109">Pour rendre l’utilisation de plus de fonctionnalités incluses dans Skype pour Business Server 2015 et d’améliorer l’expérience utilisateur globale, vous pouvez utiliser le filtre de la version client pour restreindre les versions de client qui sont utilisées dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="605b1-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="605b1-110">Le filtre de version du client vous permet également de réduire les coûts associés à la prise en charge de différentes versions du client.</span><span class="sxs-lookup"><span data-stu-id="605b1-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="605b1-p103">Les filtres sont répertoriés par ordre de priorité. Par exemple, si un premier filtre autorise les clients exécutant la version 1.5 à se connecter et qu’un second filtre bloque les clients exécutant une version antérieure à la version 2.0, le premier filtre est prioritaire : les clients exécutant la version 1.5 peuvent donc se connecter.</span><span class="sxs-lookup"><span data-stu-id="605b1-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="605b1-113">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="605b1-113">Tasks you can perform</span></span>

<span data-ttu-id="605b1-114">Dans la page **Nouvelle stratégie de version du client** ou **Modifier la stratégie de version du client**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="605b1-114">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>
  
- <span data-ttu-id="605b1-115">Ajout ou modification du nom ou de la description de la stratégie de version du client</span><span class="sxs-lookup"><span data-stu-id="605b1-115">Add or modify the name or description of the client version policy.</span></span>
    
- <span data-ttu-id="605b1-116">Ajout ou modification des règles de version de client pour la stratégie de version du client</span><span class="sxs-lookup"><span data-stu-id="605b1-116">Add or modify client version rules for the client version policy.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="605b1-117">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="605b1-117">UI Reference</span></span>

<span data-ttu-id="605b1-118">Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="605b1-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="605b1-119">**Champ d’application** Identifie l’étendue (Site, liste ou utilisateur) de la stratégie de version de client.</span><span class="sxs-lookup"><span data-stu-id="605b1-119">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>
    
- <span data-ttu-id="605b1-120">**Nom** Vous pouvez ajouter ou modifier le nom de la stratégie de version de client.</span><span class="sxs-lookup"><span data-stu-id="605b1-120">**Name** You can add or modify the name of the client version policy.</span></span>
    
- <span data-ttu-id="605b1-121">**Description** Vous pouvez ajouter une description pour aider à identifier la stratégie dans la liste sur la page Stratégie de Version de Client.</span><span class="sxs-lookup"><span data-stu-id="605b1-121">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>
    
- <span data-ttu-id="605b1-122">**Nouveau** Vous pouvez ajouter une nouvelle règle de la version client de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="605b1-122">**New** You can add a new client version rule to the policy.</span></span>
    
- <span data-ttu-id="605b1-123">**Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options pour une règle de la version client.</span><span class="sxs-lookup"><span data-stu-id="605b1-123">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>
    
- <span data-ttu-id="605b1-124">**Supprimer** Cette option supprime la règle de la version client sélectionné à partir de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="605b1-124">**Remove** This option removes the selected client version rule from the policy.</span></span>
    
- <span data-ttu-id="605b1-125">**Flèches haut et bas** Cette option déplace la règle de la version client sélectionné vers le haut ou vers le bas dans la zone priorité.</span><span class="sxs-lookup"><span data-stu-id="605b1-125">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="605b1-126">Les règles sont traitées dans l’ordre indiqué.</span><span class="sxs-lookup"><span data-stu-id="605b1-126">Rules are processed in the order listed.</span></span>
    
<span data-ttu-id="605b1-127">Pour plus d’informations sur l’interopérabilité entre les clients et les versions de client, consultez [Interopérabilité du Client dans Microsoft Lync 2013 Preview](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="605b1-127">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="605b1-128">Pour plus d’informations sur l’utilisation des stratégies de version de client, reportez-vous à la section [spécifier le Client Versions prises en charge dans votre organisation](http://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) dans la documentation sur les opérations.</span><span class="sxs-lookup"><span data-stu-id="605b1-128">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](http://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>


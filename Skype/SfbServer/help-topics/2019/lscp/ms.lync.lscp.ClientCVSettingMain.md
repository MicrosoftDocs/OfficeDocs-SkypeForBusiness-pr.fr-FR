---
title: Configuration de Version du client
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
description: Outre la spécification de la version des clients que vous souhaitez prendre en charge dans votre environnement, vous pouvez également spécifier une action par défaut pour les clients qui n’ont pas encore définie une stratégie de version. Cela permet de limiter les versions du client sont utilisées dans votre environnement, qui peut vous aider à contrôler les coûts associés à la prise en charge de plusieurs versions du client.
ms.openlocfilehash: f40a95956b2cee855dbdde0d9646afc44e187958
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/21/2018
ms.locfileid: "19990729"
---
# <a name="client-version-configuration"></a><span data-ttu-id="4aa64-104">Configuration de Version du client</span><span class="sxs-lookup"><span data-stu-id="4aa64-104">Client Version Configuration</span></span>
 
<span data-ttu-id="4aa64-105">Outre la spécification de la version des clients que vous souhaitez prendre en charge dans votre environnement, vous pouvez également spécifier une action par défaut pour les clients qui n’ont pas encore définie une stratégie de version.</span><span class="sxs-lookup"><span data-stu-id="4aa64-105">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="4aa64-106">Cela permet de limiter les versions du client sont utilisées dans votre environnement, qui peut vous aider à contrôler les coûts associés à la prise en charge de plusieurs versions du client.</span><span class="sxs-lookup"><span data-stu-id="4aa64-106">This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="4aa64-107">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="4aa64-107">Tasks you can perform</span></span>

<span data-ttu-id="4aa64-108">Vous pouvez effectuer les tâches suivantes dans la page **Configuration de Version du Client** :</span><span class="sxs-lookup"><span data-stu-id="4aa64-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>
  
- <span data-ttu-id="4aa64-109">Modifier la configuration de version du client par défaut ( **Global**).</span><span class="sxs-lookup"><span data-stu-id="4aa64-109">Edit the default ( **Global**) client version configuration.</span></span>
    
- <span data-ttu-id="4aa64-110">Créer la configuration de version du client pour un site particulier.</span><span class="sxs-lookup"><span data-stu-id="4aa64-110">Create client version configuration for a particular site.</span></span>
    
- <span data-ttu-id="4aa64-111">Activer et désactiver des configurations de version du client existant.</span><span class="sxs-lookup"><span data-stu-id="4aa64-111">Enable and disable existing client version configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4aa64-112">Étant donné que les utilisateurs anonymes ne sont pas associés à un site, les utilisateurs anonymes sont affectés par les stratégies au niveau global uniquement.</span><span class="sxs-lookup"><span data-stu-id="4aa64-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span> 
  
## <a name="ui-reference"></a><span data-ttu-id="4aa64-113">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="4aa64-113">UI Reference</span></span>

<span data-ttu-id="4aa64-114">Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="4aa64-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="4aa64-115">**Nouveau** Vous pouvez créer une configuration de version du client pour un site particulier.</span><span class="sxs-lookup"><span data-stu-id="4aa64-115">**New** You can create a client version configuration for a particular site.</span></span>
    
- <span data-ttu-id="4aa64-116">**Modifier** Vous pouvez modifier les options d’une des stratégies de version des clients.</span><span class="sxs-lookup"><span data-stu-id="4aa64-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="4aa64-117">Utilisez cette option, vous pouvez procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4aa64-117">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="4aa64-118">**Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options pour une configuration de version du client.</span><span class="sxs-lookup"><span data-stu-id="4aa64-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>
    
  - <span data-ttu-id="4aa64-119">**Sélectionner tout** Cette option sélectionne toutes les configurations de version du client dans la liste.</span><span class="sxs-lookup"><span data-stu-id="4aa64-119">**Select All** This option selects all client version configurations in the list.</span></span>
    
  - <span data-ttu-id="4aa64-120">**Supprimer** Cette option supprime toutes les configurations de version du client sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="4aa64-120">**Delete** This option deletes all selected client version configurations.</span></span>
    
- <span data-ttu-id="4aa64-121">**Actualiser** Vous pouvez actualiser la liste de configuration de version de client pour vérifier le statut des options de toutes les configurations de version du client.</span><span class="sxs-lookup"><span data-stu-id="4aa64-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>
    
<span data-ttu-id="4aa64-122">Pour plus d’informations sur l’interopérabilité entre les clients et les versions du client, voir [Interopérabilité des clients](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="4aa64-122">For details about interoperability among clients and client versions, see [Client Interoperability](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="4aa64-123">Pour plus d’informations sur l’utilisation des configurations de version du client, voir [Modifier l’Action par défaut pour les Clients pas explicitement pris en charge ou restreints](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="4aa64-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>


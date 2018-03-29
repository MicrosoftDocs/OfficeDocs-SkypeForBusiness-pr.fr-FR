---
title: Version de Configuration du client
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
description: En plus de spécifier la version de clients que vous souhaitez prendre en charge dans votre environnement, vous pouvez également spécifier une action par défaut pour les clients qui n’ont pas déjà d’une stratégie de version définie. Cela vous permet de limiter les versions de client sont utilisées dans votre environnement, ce qui peut vous aider à contrôler les coûts associés à la prise en charge de plusieurs versions du client.
ms.openlocfilehash: 4b5f76d17c92d0dd478aa9a1a3fe902ccbf35c48
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="client-version-configuration"></a><span data-ttu-id="ef377-104">Version de Configuration du client</span><span class="sxs-lookup"><span data-stu-id="ef377-104">Client Version Configuration</span></span>
 
<span data-ttu-id="ef377-105">En plus de spécifier la version de clients que vous souhaitez prendre en charge dans votre environnement, vous pouvez également spécifier une action par défaut pour les clients qui n’ont pas déjà d’une stratégie de version définie.</span><span class="sxs-lookup"><span data-stu-id="ef377-105">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="ef377-106">Cela vous permet de limiter les versions de client sont utilisées dans votre environnement, ce qui peut vous aider à contrôler les coûts associés à la prise en charge de plusieurs versions du client.</span><span class="sxs-lookup"><span data-stu-id="ef377-106">This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="ef377-107">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="ef377-107">Tasks you can perform</span></span>

<span data-ttu-id="ef377-108">Vous pouvez effectuer les tâches suivantes dans la page **Configuration de Version de Client** :</span><span class="sxs-lookup"><span data-stu-id="ef377-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>
  
- <span data-ttu-id="ef377-109">Modifier la configuration de version de client par défaut ( **Global**).</span><span class="sxs-lookup"><span data-stu-id="ef377-109">Edit the default ( **Global**) client version configuration.</span></span>
    
- <span data-ttu-id="ef377-110">Créer la configuration de version de client pour un site particulier.</span><span class="sxs-lookup"><span data-stu-id="ef377-110">Create client version configuration for a particular site.</span></span>
    
- <span data-ttu-id="ef377-111">Activer et désactiver les configurations de la version client existant.</span><span class="sxs-lookup"><span data-stu-id="ef377-111">Enable and disable existing client version configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ef377-112">Étant donné que les utilisateurs anonymes ne sont pas associés à un site, les utilisateurs anonymes sont affectées par uniquement les stratégies au niveau global.</span><span class="sxs-lookup"><span data-stu-id="ef377-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span> 
  
## <a name="ui-reference"></a><span data-ttu-id="ef377-113">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="ef377-113">UI Reference</span></span>

<span data-ttu-id="ef377-114">Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="ef377-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="ef377-115">**Nouveau** Vous pouvez créer une configuration de version de client pour un site particulier.</span><span class="sxs-lookup"><span data-stu-id="ef377-115">**New** You can create a client version configuration for a particular site.</span></span>
    
- <span data-ttu-id="ef377-116">**Modifier** Vous pouvez modifier les options de toutes les stratégies de version de client.</span><span class="sxs-lookup"><span data-stu-id="ef377-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="ef377-117">À l’aide de cette option, vous pouvez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ef377-117">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="ef377-118">**Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options de configuration de version d’un client.</span><span class="sxs-lookup"><span data-stu-id="ef377-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>
    
  - <span data-ttu-id="ef377-119">**Sélectionner tout** Cette option permet de sélectionner toutes les configurations de la version client dans la liste.</span><span class="sxs-lookup"><span data-stu-id="ef377-119">**Select All** This option selects all client version configurations in the list.</span></span>
    
  - <span data-ttu-id="ef377-120">**Supprimer** Cette option supprime toutes les configurations de version du client sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ef377-120">**Delete** This option deletes all selected client version configurations.</span></span>
    
- <span data-ttu-id="ef377-121">**Actualiser** Vous pouvez actualiser la liste de configuration client version pour vérifier l’état des options de toutes les configurations de la version client.</span><span class="sxs-lookup"><span data-stu-id="ef377-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>
    
<span data-ttu-id="ef377-122">Pour plus d’informations sur l’interopérabilité entre les clients et les versions de client, consultez [Interopérabilité du Client dans Microsoft Lync 2013 Preview](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="ef377-122">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="ef377-123">Pour plus d’informations sur l’utilisation des configurations de la version client, reportez-vous à la section [Modifier l’Action par défaut pour les Clients pas explicitement prises en charge ou restreint](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) dans la documentation sur les opérations.</span><span class="sxs-lookup"><span data-stu-id="ef377-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>


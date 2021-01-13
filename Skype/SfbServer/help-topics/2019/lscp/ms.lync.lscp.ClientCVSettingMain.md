---
title: Configuration de version du client
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: En plus de spécifier la version des clients que vous souhaitez prendre en charge dans votre environnement, vous pouvez également affecter une action par défaut aux clients pour lesquels aucune stratégie de version n’a encore été définie. Cela vous permet de restreindre les versions des clients utilisées dans votre environnement, ce qui peut vous aider à contrôler les coûts associés à la prise en charge de plusieurs versions de clients.
ms.openlocfilehash: d2d2a18928a31d136b52a90852836db93c01ffc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812314"
---
# <a name="client-version-configuration"></a><span data-ttu-id="5ec11-104">Configuration de version du client</span><span class="sxs-lookup"><span data-stu-id="5ec11-104">Client Version Configuration</span></span>

<span data-ttu-id="5ec11-p102">En plus de spécifier la version des clients que vous souhaitez prendre en charge dans votre environnement, vous pouvez également affecter une action par défaut aux clients pour lesquels aucune stratégie de version n’a encore été définie. Cela vous permet de restreindre les versions des clients utilisées dans votre environnement, ce qui peut vous aider à contrôler les coûts associés à la prise en charge de plusieurs versions de clients.</span><span class="sxs-lookup"><span data-stu-id="5ec11-p102">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined. This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="5ec11-107">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="5ec11-107">Tasks you can perform</span></span>

<span data-ttu-id="5ec11-108">Vous pouvez effectuer les tâches suivantes dans la page **Configuration de la version du client** :</span><span class="sxs-lookup"><span data-stu-id="5ec11-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>

- <span data-ttu-id="5ec11-109">Modifiez la configuration **de** version du client par défaut ( globale).</span><span class="sxs-lookup"><span data-stu-id="5ec11-109">Edit the default ( **Global**) client version configuration.</span></span>

- <span data-ttu-id="5ec11-110">Créer une configuration de version du client pour un site particulier</span><span class="sxs-lookup"><span data-stu-id="5ec11-110">Create client version configuration for a particular site.</span></span>

- <span data-ttu-id="5ec11-111">Activer et désactiver des configurations de version du client existantes</span><span class="sxs-lookup"><span data-stu-id="5ec11-111">Enable and disable existing client version configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="5ec11-112">Comme ils ne sont pas associés à un site, les utilisateurs anonymes sont uniquement affectés par les stratégies globales.</span><span class="sxs-lookup"><span data-stu-id="5ec11-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="5ec11-113">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="5ec11-113">UI Reference</span></span>

<span data-ttu-id="5ec11-114">Les listes suivantes décrivent les menus, commandes, champs et propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="5ec11-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="5ec11-115">**Nouveau** Vous pouvez créer une configuration de version du client pour un site particulier.</span><span class="sxs-lookup"><span data-stu-id="5ec11-115">**New** You can create a client version configuration for a particular site.</span></span>

- <span data-ttu-id="5ec11-116">**Modifier** Vous pouvez modifier les options de n’importe quelle stratégie de version du client.</span><span class="sxs-lookup"><span data-stu-id="5ec11-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="5ec11-117">À l’aide de cette option, vous pouvez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5ec11-117">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="5ec11-118">**Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options d’une configuration de version du client.</span><span class="sxs-lookup"><span data-stu-id="5ec11-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>

  - <span data-ttu-id="5ec11-119">**Sélectionner tout** Cette option sélectionne toutes les configurations de version des clients dans la liste.</span><span class="sxs-lookup"><span data-stu-id="5ec11-119">**Select All** This option selects all client version configurations in the list.</span></span>

  - <span data-ttu-id="5ec11-120">**Supprimer** Cette option supprime toutes les configurations de version du client sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="5ec11-120">**Delete** This option deletes all selected client version configurations.</span></span>

- <span data-ttu-id="5ec11-121">**Actualiser** Vous pouvez actualiser la liste de configuration des versions des clients pour vérifier l’état des options de toutes les configurations de version des clients.</span><span class="sxs-lookup"><span data-stu-id="5ec11-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>

<span data-ttu-id="5ec11-122">Pour plus d’informations sur l’interopérabilité entre les clients et les versions des clients, voir [Interopérabilité](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) du client dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="5ec11-122">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="5ec11-123">Pour plus d’informations sur l’utilisation des configurations de version du client, voir [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="5ec11-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>


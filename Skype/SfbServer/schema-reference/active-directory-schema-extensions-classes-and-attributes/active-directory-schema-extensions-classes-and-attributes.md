---
title: Attributs, classes et extensions des schémas Active Directory
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 'Cette section de référence inclut les informations suivantes :'
ms.openlocfilehash: 37dee1a029a0d8872452082aebb9b8f0fcf2f072
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888835"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="171cd-103">Attributs, classes et extensions des schémas Active Directory</span><span class="sxs-lookup"><span data-stu-id="171cd-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="171cd-104">Cette section de référence inclut les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="171cd-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="171cd-105">Extensions de schéma Active Directory qui sont nouvelles ou modifiées pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="171cd-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="171cd-106">Le schéma Active Directory contient des définitions formelles de chaque classe d’objet pouvant être créés dans une forêt Active Directory.</span><span class="sxs-lookup"><span data-stu-id="171cd-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="171cd-107">Le schéma contient également des définitions formelles de chaque attribut pouvant exister dans un objet Active Directory.</span><span class="sxs-lookup"><span data-stu-id="171cd-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="171cd-108">Le catalogue global Active Directory contient les réplicas de tous les objets de la forêt, ainsi qu’un sous-ensemble d’attributs pour chaque objet.</span><span class="sxs-lookup"><span data-stu-id="171cd-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="171cd-109">Cette section décrit les classes et les attributs qui sont nouvelles ou modifiées dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="171cd-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="171cd-110">Toutes les classes utilisées par Skype pour Business Server, avec une description de chacun d’eux</span><span class="sxs-lookup"><span data-stu-id="171cd-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="171cd-111">Tous les attributs utilisés par Skype pour Business Server, avec une description de chacun d’eux</span><span class="sxs-lookup"><span data-stu-id="171cd-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="171cd-112">Une liste des classes utilisées par Skype pour Business Server, avec les attributs peut contenir</span><span class="sxs-lookup"><span data-stu-id="171cd-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="171cd-113">Les paramètres globaux et objets, outre les groupes universels de service et d’administration qui sont créés pendant la préparation de la forêt</span><span class="sxs-lookup"><span data-stu-id="171cd-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="171cd-114">Entrées de contrôle d’accès (ACE) qui sont créées sur les domaine racine et les conteneurs intégrés pendant la préparation du domaine</span><span class="sxs-lookup"><span data-stu-id="171cd-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="171cd-115">Modifications effectuées dans une unité d’organisation (OU) Active Directory par l’applet de commande Grant_CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="171cd-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="171cd-116">Modifications effectuées dans une unité d’organisation Active Directory par l’applet de commande Grant_CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="171cd-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="171cd-117">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="171cd-117">In This Section</span></span>

- [<span data-ttu-id="171cd-118">Modifications de schéma dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="171cd-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="171cd-119">Classes de schéma et les descriptions de Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="171cd-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="171cd-120">Attributs de schéma et les descriptions de Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="171cd-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="171cd-121">Attributs de schéma par classe dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="171cd-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="171cd-122">Modifications apportées par la préparation de la forêt dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="171cd-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="171cd-123">Modifications apportées par la préparation du domaine dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="171cd-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="171cd-124">Modifications apportées par Grant-CsSetupPermission dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="171cd-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="171cd-125">Modifications apportées par Grant-CsOUPermission dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="171cd-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    


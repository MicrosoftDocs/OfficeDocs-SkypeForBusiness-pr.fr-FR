---
title: Les extensions de schéma active Directory, les classes et les attributs
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 'Cette section de référence consacrée les informations suivantes :'
ms.openlocfilehash: f185a11bdc5d3700839be2f1306e266d9ab6af26
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="9c0fe-103">Les extensions de schéma active Directory, les classes et les attributs</span><span class="sxs-lookup"><span data-stu-id="9c0fe-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="9c0fe-104">Cette section de référence consacrée les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9c0fe-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="9c0fe-105">Extensions de schéma Active Directory qui sont nouvelles ou modifiées pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="9c0fe-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="9c0fe-106">Le schéma Active Directory contient des définitions formelles de chaque classe d’objet qui peut être créé dans une forêt Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9c0fe-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="9c0fe-107">Le schéma contient également des définitions formelles de chaque attribut qui peuvent exister sur un objet Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9c0fe-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="9c0fe-108">Le catalogue global Active Directory contient les réplicas de tous les objets de la forêt, ainsi que d’un sous-ensemble d’attributs pour chaque objet.</span><span class="sxs-lookup"><span data-stu-id="9c0fe-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="9c0fe-109">Cette section décrit les classes et les attributs qui sont nouvelles ou modifiées dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="9c0fe-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="9c0fe-110">Toutes les classes utilisées par Skype pour le serveur de l’entreprise, avec une description de chaque</span><span class="sxs-lookup"><span data-stu-id="9c0fe-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="9c0fe-111">Tous les attributs utilisés par Skype pour le serveur de l’entreprise, avec une description de chaque</span><span class="sxs-lookup"><span data-stu-id="9c0fe-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="9c0fe-112">Une liste des classes utilisées par Skype pour le serveur de l’entreprise, avec les attributs peut-être contenir des</span><span class="sxs-lookup"><span data-stu-id="9c0fe-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="9c0fe-113">Paramètres globaux et les objets, les groupes universels de service et d’administration qui sont créés au cours de la préparation de la forêt</span><span class="sxs-lookup"><span data-stu-id="9c0fe-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="9c0fe-114">Entrées de contrôle d’accès (ACE) qui sont créées sur les conteneurs de domaine racine et intégré au cours de la préparation du domaine</span><span class="sxs-lookup"><span data-stu-id="9c0fe-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="9c0fe-115">Modifications effectuées sur une unité d’organisation (UO) d’Active Directory par l’applet de commande Grant_CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="9c0fe-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="9c0fe-116">Modifications effectuées sur une unité d’organisation du répertoire actif par l’applet de commande Grant_CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="9c0fe-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="9c0fe-117">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="9c0fe-117">In This Section</span></span>

- [<span data-ttu-id="9c0fe-118">Modifications de schéma dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="9c0fe-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="9c0fe-119">Classes de schéma et de descriptions dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="9c0fe-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="9c0fe-120">Les attributs de schéma et de descriptions dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="9c0fe-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="9c0fe-121">Attributs de schéma par classe dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="9c0fe-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="9c0fe-122">Modifications apportées par la préparation de la forêt dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="9c0fe-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="9c0fe-123">Modifications apportées par la préparation du domaine dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="9c0fe-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="9c0fe-124">Modifications apportées par la subvention-CsSetupPermission dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="9c0fe-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="9c0fe-125">Modifications apportées par la subvention-CsOUPermission dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="9c0fe-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    


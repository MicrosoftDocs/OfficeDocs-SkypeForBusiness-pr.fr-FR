---
title: Attributs, classes et extensions des schémas Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 'Cette section de référence contient les informations suivantes:'
ms.openlocfilehash: 5934c9ffab8055de86cdaf3bcf507fa9c806f245
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296741"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="697b4-103">Attributs, classes et extensions des schémas Active Directory</span><span class="sxs-lookup"><span data-stu-id="697b4-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="697b4-104">Cette section de référence contient les informations suivantes:</span><span class="sxs-lookup"><span data-stu-id="697b4-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="697b4-105">Extensions de schéma Active Directory nouvelles ou modifiées pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="697b4-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="697b4-106">Le schéma Active Directory contient des définitions formels de toutes les classes d’objets qui peuvent être créées dans une forêt Active Directory.</span><span class="sxs-lookup"><span data-stu-id="697b4-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="697b4-107">Le schéma contient également des définitions formels de chaque attribut qui peut exister sur un objet Active Directory.</span><span class="sxs-lookup"><span data-stu-id="697b4-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="697b4-108">Le catalogue global Active Directory contient des réplicas de tous les objets pour la forêt, ainsi qu’un sous-ensemble des attributs de chaque objet.</span><span class="sxs-lookup"><span data-stu-id="697b4-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="697b4-109">Cette section décrit les classes et attributs qui sont nouveaux ou modifiés dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="697b4-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="697b4-110">Toutes les classes utilisées par Skype entreprise Server, avec une description de chaque</span><span class="sxs-lookup"><span data-stu-id="697b4-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="697b4-111">Tous les attributs utilisés par Skype entreprise Server, avec une description de chaque</span><span class="sxs-lookup"><span data-stu-id="697b4-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="697b4-112">Une liste des classes utilisées par Skype entreprise Server, avec les attributs qu’il contient</span><span class="sxs-lookup"><span data-stu-id="697b4-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="697b4-113">Paramètres globaux et objets, en plus du service universel et des groupes d’administration créés lors de la préparation de la forêt</span><span class="sxs-lookup"><span data-stu-id="697b4-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="697b4-114">Entrées de contrôle d’accès (ACE) créées sur la racine de domaine et les conteneurs intégrés lors de la préparation du domaine</span><span class="sxs-lookup"><span data-stu-id="697b4-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="697b4-115">Modifications effectuées sur une unité d’organisation Active Directory par l’applet de contrôle Grant_CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="697b4-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="697b4-116">Les modifications apportées sur une unité d’organisation Active Directory par l’applet de contrôle Grant_CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="697b4-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="697b4-117">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="697b4-117">In This Section</span></span>

- [<span data-ttu-id="697b4-118">Modifications de schéma dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="697b4-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="697b4-119">Classes et descriptions de schéma dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="697b4-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="697b4-120">Attributs et descriptions de schéma dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="697b4-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="697b4-121">Attributs de schéma par classe dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="697b4-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="697b4-122">Modifications apportées par la préparation de la forêt dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="697b4-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="697b4-123">Modifications apportées par la préparation du domaine dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="697b4-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="697b4-124">Modifications apportées par Grant-CsSetupPermission dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="697b4-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="697b4-125">Modifications apportées par Grant-CsOUPermission dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="697b4-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    


---
title: Attributs, classes et extensions des schémas Active Directory
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 'Cette section de référence inclut les informations suivantes :'
ms.openlocfilehash: 5c8a1ceb6b623466219cbd3df46ff2b39ccceb2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831934"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="dbac6-103">Attributs, classes et extensions des schémas Active Directory</span><span class="sxs-lookup"><span data-stu-id="dbac6-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="dbac6-104">Cette section de référence inclut les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="dbac6-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="dbac6-105">Extensions de schéma Active Directory nouvelles ou modifiées pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="dbac6-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="dbac6-106">Le schéma Active Directory contient des définitions formelles de chaque classe d’objet pouvant être créée dans une forêt Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dbac6-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="dbac6-107">Il contient également des définitions formelles de chaque attribut pouvant exister dans un objet Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dbac6-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="dbac6-108">Le catalogue global Active Directory contient les réplicas de tous les objets de la forêt, ainsi qu’un sous-ensemble d’attributs pour chaque objet.</span><span class="sxs-lookup"><span data-stu-id="dbac6-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="dbac6-109">Cette section décrit les classes et attributs nouveaux ou modifiés dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="dbac6-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="dbac6-110">Toutes les classes utilisées par Skype Entreprise Server, avec une description de chacune</span><span class="sxs-lookup"><span data-stu-id="dbac6-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="dbac6-111">Tous les attributs utilisés par Skype Entreprise Server, avec une description de chacun</span><span class="sxs-lookup"><span data-stu-id="dbac6-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="dbac6-112">Liste des classes utilisées par Skype Entreprise Server, avec les attributs que chacune peut contenir</span><span class="sxs-lookup"><span data-stu-id="dbac6-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="dbac6-113">Objets et paramètres globaux, ainsi que groupes de services universels et d’administration, qui sont créés pendant la préparation de la forêt</span><span class="sxs-lookup"><span data-stu-id="dbac6-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="dbac6-114">Entrées de contrôle d’accès (ACE) créées à la racine du domaine et conteneurs intégrés pendant la préparation du domaine</span><span class="sxs-lookup"><span data-stu-id="dbac6-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="dbac6-115">Modifications effectuées dans une unité d’organisation (OU) Active Directory par l’applet de commande Grant_CsSetupPermission</span><span class="sxs-lookup"><span data-stu-id="dbac6-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="dbac6-116">Modifications effectuées dans une unité d’organisation (OU) Active Directory par l’applet de commande Grant_CsOUPermission</span><span class="sxs-lookup"><span data-stu-id="dbac6-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="dbac6-117">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="dbac6-117">In This Section</span></span>

- [<span data-ttu-id="dbac6-118">Modifications apportées au schéma dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="dbac6-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="dbac6-119">Classes de schéma et descriptions dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="dbac6-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="dbac6-120">Attributs et descriptions de schéma dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="dbac6-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="dbac6-121">Attributs de schéma par classe dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="dbac6-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="dbac6-122">Modifications apportées par la préparation de la forêt dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="dbac6-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="dbac6-123">Modifications apportées par la préparation du domaine dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="dbac6-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="dbac6-124">Modifications apportées par Grant-CsSetupPermission dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="dbac6-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="dbac6-125">Modifications apportées par Grant-CsOUPermission dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="dbac6-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    


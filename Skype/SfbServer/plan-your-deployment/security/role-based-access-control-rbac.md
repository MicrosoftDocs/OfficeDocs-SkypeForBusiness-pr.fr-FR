---
title: Contrôle d’accès basé sur les rôles (RBAC) pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype entreprise Server inclut des groupes de contrôle d’accès basés sur les rôles (RBAC) pour vous permettre de déléguer des tâches administratives tout en préservant la sécurité. Ces groupes sont créés durant la préparation de la forêt. Pour plus d’informations sur la préparation de la forêt, voir services de domaine Active Directory pour Skype entreprise Server. Pour plus d’informations sur les groupes spécifiques créés par la préparation de la forêt, voir modifications apportées par la préparation de la forêt dans Skype entreprise Server dans la documentation de déploiement.
ms.openlocfilehash: d5f31d7c53c743e4b2d001b00abec7ec93ef8d91
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/17/2019
ms.locfileid: "35759014"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a><span data-ttu-id="4ec2b-106">Contrôle d’accès basé sur les rôles (RBAC) pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="4ec2b-106">Role-based access control (RBAC) for Skype for Business Server</span></span>
 
<span data-ttu-id="4ec2b-107">Skype entreprise Server inclut des groupes de contrôle d’accès basés sur les rôles (RBAC) pour vous permettre de déléguer des tâches administratives tout en préservant la sécurité.</span><span class="sxs-lookup"><span data-stu-id="4ec2b-107">Skype for Business Server includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="4ec2b-108">Ces groupes sont créés durant la préparation de la forêt.</span><span class="sxs-lookup"><span data-stu-id="4ec2b-108">These groups are created during forest preparation.</span></span> <span data-ttu-id="4ec2b-109">Pour plus d’informations sur la préparation de la forêt, voir [services de domaine Active Directory pour Skype entreprise Server](active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="4ec2b-109">For details about forest preparation, see [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md).</span></span> <span data-ttu-id="4ec2b-110">Pour plus d’informations sur les groupes spécifiques créés par la préparation de la forêt, voir [modifications apportées par la préparation de la forêt dans Skype entreprise Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="4ec2b-110">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="4ec2b-111">Dans ce cadre, le privilège administratif est accordé en affectant les utilisateurs à des rôles d’administration prédéfinis, incluant les 11 rôles prédéfinis qui couvrent de nombreuses tâches d’administration courantes.</span><span class="sxs-lookup"><span data-stu-id="4ec2b-111">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="4ec2b-112">Chaque rôle est associé à une liste d’applets de cmdlet Skype entreprise Server Management Shell que les utilisateurs de ce rôle peuvent exécuter.</span><span class="sxs-lookup"><span data-stu-id="4ec2b-112">Each role is associated with a specific list of Skype for Business Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="4ec2b-113">Vous pouvez utiliser le contrôle d’accès basé sur un rôle pour suivre le principe du « privilège minimum » qui limite les droits d’administration octroyés aux utilisateurs à ceux nécessaires à leur travail.</span><span class="sxs-lookup"><span data-stu-id="4ec2b-113">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> 
  
<span data-ttu-id="4ec2b-114">Vous trouverez des informations supplémentaires sur les rôles RBAC dans [planification pour le contrôle d’accès basé sur un rôle](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control).</span><span class="sxs-lookup"><span data-stu-id="4ec2b-114">More details on RBAC roles can be found at [Planning for role-based access control](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control).</span></span>

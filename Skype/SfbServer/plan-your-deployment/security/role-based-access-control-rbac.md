---
title: Contrôle d’accès basé sur un rôle (RBAC) pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype Entreprise Server inclut des groupes Role-Based contrôle d’accès (RBAC) pour vous permettre de déléguer des tâches administratives tout en maintenant des normes élevées en matière de sécurité. Ces groupes sont créés pendant la phase de préparation de la forêt. Pour plus d’informations sur la préparation de la forêt, voir Services de domaine Active Directory pour Skype Entreprise Server. Pour plus d’informations sur les groupes spécifiques créés par la préparation de la forêt, voir Modifications apportées par la préparation de la forêt dans Skype Entreprise Server dans la documentation de déploiement.
ms.openlocfilehash: 9d3c453d4e7c3057c03f99cf2ff31b5fe17ae0bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832104"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a><span data-ttu-id="1b207-106">Contrôle d’accès basé sur un rôle (RBAC) pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1b207-106">Role-based access control (RBAC) for Skype for Business Server</span></span>
 
<span data-ttu-id="1b207-107">Skype Entreprise Server inclut des groupes Role-Based contrôle d’accès (RBAC) pour vous permettre de déléguer des tâches administratives tout en maintenant des normes élevées en matière de sécurité.</span><span class="sxs-lookup"><span data-stu-id="1b207-107">Skype for Business Server includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="1b207-108">Ces groupes sont créés pendant la phase de préparation de la forêt.</span><span class="sxs-lookup"><span data-stu-id="1b207-108">These groups are created during forest preparation.</span></span> <span data-ttu-id="1b207-109">Pour plus d’informations sur la préparation de la forêt, voir Services de domaine [Active Directory pour Skype Entreprise Server.](active-directory-domain-services.md)</span><span class="sxs-lookup"><span data-stu-id="1b207-109">For details about forest preparation, see [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md).</span></span> <span data-ttu-id="1b207-110">Pour plus d’informations sur les groupes spécifiques créés par la préparation de la forêt, voir Modifications apportées par la préparation de la forêt [dans Skype](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) Entreprise Server dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="1b207-110">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="1b207-111">Avec le contrôle d’accès en fonction du rôle, le privilège administratif est accordé en attribuant aux utilisateurs des rôles d’administration prédéfin définis, y compris les 11 rôles prédéfin définis qui couvrent de nombreuses tâches administratives courantes.</span><span class="sxs-lookup"><span data-stu-id="1b207-111">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="1b207-112">Chaque rôle est associé à une liste spécifique de cmdlets Skype Entreprise Server Management Shell que les utilisateurs de ce rôle sont autorisés à exécuter.</span><span class="sxs-lookup"><span data-stu-id="1b207-112">Each role is associated with a specific list of Skype for Business Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="1b207-113">Vous pouvez utiliser RBAC pour suivre le principe du « privilège minimum », dans lequel les utilisateurs ne sont attribués qu’aux capacités administratives dont leur travail a besoin.</span><span class="sxs-lookup"><span data-stu-id="1b207-113">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> 
  
<span data-ttu-id="1b207-114">Pour plus d’informations sur les rôles RBAC, voir [Planning for role-based access control](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control).</span><span class="sxs-lookup"><span data-stu-id="1b207-114">More details on RBAC roles can be found at [Planning for role-based access control](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control).</span></span>

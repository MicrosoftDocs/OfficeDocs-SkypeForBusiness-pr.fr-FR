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
ms.openlocfilehash: 493af102ae42658d51cfcb5d65fde6c26596d82d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296839"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a><span data-ttu-id="5d72e-106">Contrôle d’accès basé sur les rôles (RBAC) pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="5d72e-106">Role-based access control (RBAC) for Skype for Business Server</span></span>
 
<span data-ttu-id="5d72e-107">Skype entreprise Server inclut des groupes de contrôle d’accès basés sur les rôles (RBAC) pour vous permettre de déléguer des tâches administratives tout en préservant la sécurité.</span><span class="sxs-lookup"><span data-stu-id="5d72e-107">Skype for Business Server includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="5d72e-108">Ces groupes sont créés durant la préparation de la forêt.</span><span class="sxs-lookup"><span data-stu-id="5d72e-108">These groups are created during forest preparation.</span></span> <span data-ttu-id="5d72e-109">Pour plus d’informations sur la préparation de la forêt, voir [services de domaine Active Directory pour Skype entreprise Server](active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="5d72e-109">For details about forest preparation, see [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md).</span></span> <span data-ttu-id="5d72e-110">Pour plus d’informations sur les groupes spécifiques créés par la préparation de la forêt, voir [modifications apportées par la préparation de la forêt dans Skype entreprise Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="5d72e-110">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="5d72e-111">Dans ce cadre, le privilège administratif est accordé en affectant les utilisateurs à des rôles d’administration prédéfinis, incluant les 11 rôles prédéfinis qui couvrent de nombreuses tâches d’administration courantes.</span><span class="sxs-lookup"><span data-stu-id="5d72e-111">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="5d72e-112">Chaque rôle est associé à une liste spécifique de cmdlets Lync Server Management Shell que les utilisateurs de ce rôle peuvent exécuter.</span><span class="sxs-lookup"><span data-stu-id="5d72e-112">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="5d72e-113">Vous pouvez utiliser le contrôle d’accès basé sur un rôle pour suivre le principe du « privilège minimum » qui limite les droits d’administration octroyés aux utilisateurs à ceux nécessaires à leur travail.</span><span class="sxs-lookup"><span data-stu-id="5d72e-113">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> 
  
<span data-ttu-id="5d72e-114">Vous trouverez des informations supplémentaires sur les rôles RBAC à l’adresse suivante:https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx</span><span class="sxs-lookup"><span data-stu-id="5d72e-114">More details on RBAC roles can be found at: https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx</span></span>

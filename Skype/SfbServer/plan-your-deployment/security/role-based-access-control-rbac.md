---
title: Contrôle d’accès basé sur un rôle (RBAC) pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype Entreprise Server inclut Role-Based groupes de contrôle d’accès (RBAC) pour vous permettre de déléguer des tâches administratives tout en maintenant des normes élevées en matière de sécurité. Ces groupes sont créés pendant la phase de préparation de la forêt. Pour plus d’informations sur la préparation de la forêt, voir Services de domaine Active Directory pour Skype Entreprise Server. Pour plus d’informations sur les groupes spécifiques créés par la préparation de la forêt, voir Modifications apportées par la préparation de la forêt Skype Entreprise Server dans la documentation de déploiement.
ms.openlocfilehash: 8b4f96764487ba20e2699ea8f22e1b065e109e8b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858951"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Contrôle d’accès basé sur un rôle (RBAC) pour Skype Entreprise Server
 
Skype Entreprise Server inclut Role-Based groupes de contrôle d’accès (RBAC) pour vous permettre de déléguer des tâches administratives tout en maintenant des normes élevées en matière de sécurité. Ces groupes sont créés pendant la phase de préparation de la forêt. Pour plus d’informations sur la préparation de la forêt, voir Services de domaine [Active Directory pour Skype Entreprise Server](active-directory-domain-services.md). Pour plus d’informations sur les groupes spécifiques créés par la préparation de la forêt, voir Modifications apportées par la préparation de la forêt [Skype Entreprise Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) dans la documentation de déploiement.
  
Avec le contrôle d’accès en fonction du rôle, le privilège administratif est accordé en attribuant aux utilisateurs des rôles d’administration prédéfin définis, y compris les 11 rôles prédéfin définis qui couvrent de nombreuses tâches administratives courantes. Chaque rôle est associé à une liste spécifique de cmdlets Skype Entreprise Server Management Shell que les utilisateurs de ce rôle sont autorisés à exécuter. Vous pouvez utiliser RBAC pour suivre le principe du « privilège minimum », dans lequel les utilisateurs ne sont attribués qu’aux capacités administratives dont leur travail a besoin. 
  
Pour plus d’informations sur les rôles RBAC, voir [Planning for role-based access control](/lyncserver/lync-server-2013-planning-for-role-based-access-control).
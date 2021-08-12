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
description: Skype Entreprise Server inclut Role-Based groupes de contrôle d’accès (RBAC) pour vous permettre de déléguer des tâches administratives tout en maintenant des normes élevées en matière de sécurité. Ces groupes sont créés pendant la phase de préparation de la forêt. Pour plus d’informations sur la préparation de la forêt, voir Services de domaine Active Directory pour Skype Entreprise Server. Pour plus d’informations sur les groupes spécifiques créés par la préparation de la forêt, voir Modifications apportées par la préparation de la forêt Skype Entreprise Server dans la documentation de déploiement.
ms.openlocfilehash: 8b4dbfc85a92063bff7e5c57ee18ccc9b80bb4e08b0716fd1cac0666f1862fb0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337722"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Contrôle d’accès basé sur un rôle (RBAC) pour Skype Entreprise Server
 
Skype Entreprise Server inclut Role-Based groupes de contrôle d’accès (RBAC) pour vous permettre de déléguer des tâches administratives tout en maintenant des normes élevées en matière de sécurité. Ces groupes sont créés pendant la phase de préparation de la forêt. Pour plus d’informations sur la préparation de la forêt, voir Services de domaine [Active Directory pour Skype Entreprise Server](active-directory-domain-services.md). Pour plus d’informations sur les groupes spécifiques créés par la préparation de la forêt, voir Modifications apportées par la préparation de la forêt [Skype Entreprise Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) dans la documentation de déploiement.
  
Avec le contrôle d’accès en fonction du rôle, le privilège administratif est accordé en attribuant aux utilisateurs des rôles d’administration prédéfin définis, y compris les 11 rôles prédéfin définis qui couvrent de nombreuses tâches administratives courantes. Chaque rôle est associé à une liste spécifique de cmdlets Skype Entreprise Server Management Shell que les utilisateurs de ce rôle sont autorisés à exécuter. Vous pouvez utiliser RBAC pour suivre le principe du « privilège minimum », dans lequel les utilisateurs ne sont attribués qu’aux capacités administratives dont leur travail a besoin. 
  
Pour plus d’informations sur les rôles RBAC, voir [Planning for role-based access control](/lyncserver/lync-server-2013-planning-for-role-based-access-control).
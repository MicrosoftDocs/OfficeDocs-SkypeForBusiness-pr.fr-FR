---
title: Contrôle d’accès basé sur les rôles (RBAC) pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype entreprise Server inclut des groupes de contrôle d’accès basés sur les rôles (RBAC) pour vous permettre de déléguer des tâches administratives tout en préservant la sécurité. Ces groupes sont créés durant la préparation de la forêt. Pour plus d’informations sur la préparation de la forêt, voir services de domaine Active Directory pour Skype entreprise Server. Pour plus d’informations sur les groupes spécifiques créés par la préparation de la forêt, voir modifications apportées par la préparation de la forêt dans Skype entreprise Server dans la documentation de déploiement.
ms.openlocfilehash: 41efad45b442d9c7fca82d090afa0d1aa23e7d63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815622"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Contrôle d’accès basé sur les rôles (RBAC) pour Skype entreprise Server
 
Skype entreprise Server inclut des groupes de contrôle d’accès basés sur les rôles (RBAC) pour vous permettre de déléguer des tâches administratives tout en préservant la sécurité. Ces groupes sont créés durant la préparation de la forêt. Pour plus d’informations sur la préparation de la forêt, voir [services de domaine Active Directory pour Skype entreprise Server](active-directory-domain-services.md). Pour plus d’informations sur les groupes spécifiques créés par la préparation de la forêt, voir [modifications apportées par la préparation de la forêt dans Skype entreprise Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) dans la documentation de déploiement.
  
Dans ce cadre, le privilège administratif est accordé en affectant les utilisateurs à des rôles d’administration prédéfinis, incluant les 11 rôles prédéfinis qui couvrent de nombreuses tâches d’administration courantes. Chaque rôle est associé à une liste d’applets de cmdlet Skype entreprise Server Management Shell que les utilisateurs de ce rôle peuvent exécuter. Vous pouvez utiliser le contrôle d’accès basé sur un rôle pour suivre le principe du « privilège minimum » qui limite les droits d’administration octroyés aux utilisateurs à ceux nécessaires à leur travail. 
  
Vous trouverez des informations supplémentaires sur les rôles RBAC dans [planification pour le contrôle d’accès basé sur un rôle](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control).

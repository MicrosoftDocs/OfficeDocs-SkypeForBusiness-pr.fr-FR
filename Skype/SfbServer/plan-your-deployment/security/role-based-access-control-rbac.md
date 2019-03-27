---
title: Contrôle d’accès basé sur un rôle (RBAC) pour Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype pour Business Server propose des groupes de contrôle d’accès basé sur un rôle (RBAC) vous permet de déléguer des tâches administratives tout en conservant les normes de sécurité strictes. Ces groupes sont créés durant la préparation de la forêt. Pour plus d’informations sur la préparation de la forêt, voir Services de domaine Active Directory pour Skype pour Business Server. Pour plus d’informations sur les groupes spécifiques créés par la préparation de forêt, consultez modifications effectuées par la préparation de la forêt dans Skype pour Business Server dans la documentation de déploiement.
ms.openlocfilehash: 461fa82809b16ccf6db1ac02e7c8d0e6698e2b61
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894272"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Contrôle d’accès basé sur un rôle (RBAC) pour Skype pour Business Server
 
Skype pour Business Server propose des groupes de contrôle d’accès basé sur un rôle (RBAC) vous permet de déléguer des tâches administratives tout en conservant les normes de sécurité strictes. Ces groupes sont créés durant la préparation de la forêt. Pour plus d’informations sur la préparation de la forêt, voir [Services de domaine Active Directory pour Skype pour Business Server](active-directory-domain-services.md). Pour plus d’informations sur les groupes spécifiques créés par la préparation de forêt, consultez [modifications effectuées par la préparation de la forêt dans Skype pour Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) dans la documentation de déploiement.
  
Dans ce cadre, le privilège administratif est accordé en affectant les utilisateurs à des rôles d’administration prédéfinis, incluant les 11 rôles prédéfinis qui couvrent de nombreuses tâches d’administration courantes. Chaque rôle est associé à une liste spécifique de cmdlets Lync Server Management Shell que les utilisateurs de ce rôle sont autorisés à exécuter. Vous pouvez utiliser le contrôle d’accès basé sur un rôle pour suivre le principe du « privilège minimum » qui limite les droits d’administration octroyés aux utilisateurs à ceux nécessaires à leur travail. 
  
Vous trouverez plus d’informations sur les rôles RBAC à :https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx

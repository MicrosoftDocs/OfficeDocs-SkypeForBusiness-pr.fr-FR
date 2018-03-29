---
title: Contrôle d’accès en fonction du rôle (RBAC) pour Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype pour Business Server 2015 comprend des groupes de contrôle d’accès basée sur les rôles (RBAC) vous permet de déléguer des tâches administratives tout en conservant un niveau élevé de sécurité. Ces groupes sont créés durant la préparation de la forêt. Pour plus d’informations sur la préparation de la forêt, voir Services de domaine Active Directory pour Skype pour Business Server 2015. Pour plus d’informations sur les groupes spécifiques, créés en préparation de la forêt, voir modifications apportées par la préparation de la forêt dans Skype pour Business Server dans la documentation de déploiement.
ms.openlocfilehash: f637ef752bb122cb73220d66fd8aa19c16fb358e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server-2015"></a>Contrôle d’accès en fonction du rôle (RBAC) pour Skype Entreprise Server 2015
 
Skype pour Business Server 2015 comprend des groupes de contrôle d’accès basée sur les rôles (RBAC) vous permet de déléguer des tâches administratives tout en conservant un niveau élevé de sécurité. Ces groupes sont créés durant la préparation de la forêt. Pour plus d’informations sur la préparation de la forêt, voir [Services de domaine Active Directory pour Skype pour Business Server 2015](active-directory-domain-services.md). Pour plus d’informations sur les groupes spécifiques, créés en préparation de la forêt, reportez-vous à la section [modifications apportées par la préparation de la forêt dans Skype pour Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) dans la documentation de déploiement.
  
Dans ce cadre, le privilège administratif est accordé en affectant les utilisateurs à des rôles d’administration prédéfinis, incluant les 11 rôles prédéfinis qui couvrent de nombreuses tâches d’administration courantes. Chaque rôle est associé à une liste spécifique d’applets de commande de Communications Server Management Shell que les utilisateurs dans ce rôle sont autorisés à s’exécuter. Vous pouvez utiliser le contrôle d’accès basé sur un rôle pour suivre le principe du « privilège minimum » qui limite les droits d’administration octroyés aux utilisateurs à ceux nécessaires à leur travail. 
  


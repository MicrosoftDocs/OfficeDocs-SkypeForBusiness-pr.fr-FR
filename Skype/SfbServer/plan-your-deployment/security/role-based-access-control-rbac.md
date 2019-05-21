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
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Contrôle d’accès basé sur les rôles (RBAC) pour Skype entreprise Server
 
Skype entreprise Server inclut des groupes de contrôle d’accès basés sur les rôles (RBAC) pour vous permettre de déléguer des tâches administratives tout en préservant la sécurité. Ces groupes sont créés durant la préparation de la forêt. Pour plus d’informations sur la préparation de la forêt, voir [services de domaine Active Directory pour Skype entreprise Server](active-directory-domain-services.md). Pour plus d’informations sur les groupes spécifiques créés par la préparation de la forêt, voir [modifications apportées par la préparation de la forêt dans Skype entreprise Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) dans la documentation de déploiement.
  
Dans ce cadre, le privilège administratif est accordé en affectant les utilisateurs à des rôles d’administration prédéfinis, incluant les 11 rôles prédéfinis qui couvrent de nombreuses tâches d’administration courantes. Chaque rôle est associé à une liste spécifique de cmdlets Lync Server Management Shell que les utilisateurs de ce rôle peuvent exécuter. Vous pouvez utiliser le contrôle d’accès basé sur un rôle pour suivre le principe du « privilège minimum » qui limite les droits d’administration octroyés aux utilisateurs à ceux nécessaires à leur travail. 
  
Vous trouverez des informations supplémentaires sur les rôles RBAC à l’adresse suivante:https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx

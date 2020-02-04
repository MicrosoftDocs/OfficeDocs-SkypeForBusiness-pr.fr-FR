---
title: Liste de vérification de première exécution pour le panneau de configuration de Skype Entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
ROBOTS: NOINDEX, NOFOLLOW
description: Bienvenue dans le panneau de configuration Skype entreprise Server, interface utilisateur basée sur le Web pour l’administration et la gestion de Skype entreprise Server. Vous pouvez utiliser le panneau de configuration pour effectuer des types de tâche administrative effectuées en utilisant la console d’administration Microsoft.
ms.openlocfilehash: 9fe3c04746d15e67cc37a8039b3b43db869b1835
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691279"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Liste de vérification de première exécution pour le panneau de configuration de Skype Entreprise Server

Bienvenue dans le panneau de configuration Skype entreprise Server, interface utilisateur basée sur le Web pour l’administration et la gestion de Skype entreprise Server. Vous pouvez utiliser le panneau de configuration pour effectuer des types de tâche administrative effectuées en utilisant la console d’administration Microsoft.

Il existe un certain nombre de tâches importantes que nous vous recommandons vivement d’effectuer après le déploiement de Skype entreprise Server. Certaines de ces tâches sont des étapes de configuration initiales que vous avez peut-être déjà effectuées lors du déploiement, tandis que d’autres améliorent ou modifient des paramètres configurés lors du déploiement ou sont des paramètres par défaut. D’autres tâches décrites dans cette rubrique valident les configurations effectuées lors de la procédure de déploiement.

> [!NOTE]
> Avant d’effectuer les tâches dans le tableau ci-dessous, veillez à vous connecter en utilisant les droits d’utilisateur, les autorisations et le rôle appropriés conformément à la description de la section « Rôles et étendue » de la rubrique [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx).

## <a name="first-run-checklist"></a>Liste de vérification de première exécution

Nous vous conseillons vivement de passer en revue les tâches décrites dans cette rubrique, puis d’effectuer les procédures appropriées de déploiement au sein de votre organisation.

|**Task**|**Groupe du panneau de configuration**|**Documentation**|
|:-----|:-----|:-----|
|Vérifiez que les services installés dans votre topologie sont exécutés de la façon escomptée.  <br/> |**Topologie** <br/> |[View Details About a Service](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|Activez les utilisateurs de Skype entreprise Server. Si vous migrez à partir d’une version précédente, vous pouvez également déplacer des utilisateurs vers Skype entreprise Server.  <br/> |**Utilisateurs** <br/> |[Managing Users](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|Si vous avez déployé ou si voulez déployer Voix Entreprise, configurez une connexion de jonction SIP pour activer la connectivité au réseau téléphonique commuté public (RTC).  <br/> |**Routage des communications vocales** <br/> |[Configuring Trunks and Translation Rules](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|Si vous avez déployé Voix Entreprise, vérifiez les paramètres de routage Voix Entreprise.  <br/> |**Routage des communications vocales** <br/> |[Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|Si vous avez déployé le serveur d’archivage, vérifiez que les stratégies et les paramètres d’archivage répondent aux besoins de votre organisation.  <br/> |**Surveillance et archivage** <br/> |[Managing Archiving](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|Si vous avez déployé le serveur de surveillance, affichez les rapports du serveur de surveillance pour afficher les informations d’utilisation et de diagnostic.  <br/> |**Accueil** <br/> |[Gestion de l’intégrité et de la surveillance dans Skype entreprise Server](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |



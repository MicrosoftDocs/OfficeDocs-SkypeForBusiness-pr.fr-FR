---
title: Liste de vérification de première exécution pour le panneau de configuration de Skype Entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
ROBOTS: NOINDEX, NOFOLLOW
description: Bienvenue dans le Skype pour Business Server le panneau de configuration, l’interface utilisateur web pour l’administration et la gestion de Skype pour Business Server. Vous pouvez utiliser le panneau de configuration pour effectuer des types de tâche administrative effectuées en utilisant la console d’administration Microsoft.
ms.openlocfilehash: e7538c82098abbd7a199cb699c0eeed6cee901aa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891487"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Liste de vérification de première exécution pour le panneau de configuration de Skype Entreprise Server

Bienvenue dans le Skype pour Business Server le panneau de configuration, l’interface utilisateur web pour l’administration et la gestion de Skype pour Business Server. Vous pouvez utiliser le panneau de configuration pour effectuer des types de tâche administrative effectuées en utilisant la console d’administration Microsoft.

Il existe un nombre de tâches importantes qu’il est vivement recommandé de qu'effectuer une fois que vous avez déployé Skype pour Business Server. Certaines de ces tâches sont des étapes de configuration initiales que vous avez peut-être déjà effectuées lors du déploiement, tandis que d’autres améliorent ou modifient des paramètres configurés lors du déploiement ou sont des paramètres par défaut. D’autres tâches décrites dans cette rubrique valident les configurations effectuées lors de la procédure de déploiement.

> [!NOTE]
> Avant d’effectuer les tâches dans le tableau ci-dessous, veillez à vous connecter en utilisant les droits d’utilisateur, les autorisations et le rôle appropriés conformément à la description de la section « Rôles et étendue » de la rubrique [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx).

## <a name="first-run-checklist"></a>Liste de vérification de première exécution

Nous vous recommandons fortement que vous passez en revue les tâches mentionnées dans cette rubrique, puis effectuez les procédures appropriées pour le déploiement dans votre organisation.

|**Task**|**Groupe du panneau de configuration**|**Documentation**|
|:-----|:-----|:-----|
|Vérifiez que les services installés dans votre topologie sont exécutés de la façon escomptée.  <br/> |**Topologie** <br/> |[View Details About a Service](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|Permettre aux utilisateurs de Skype pour Business Server. Si vous le souhaitez et, si une migration depuis une version précédente, déplacer des utilisateurs vers Skype pour Business Server.  <br/> |**Utilisateurs** <br/> |[Managing Users](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|Si vous avez déployé ou si voulez déployer Voix Entreprise, configurez une connexion de jonction SIP pour activer la connectivité au réseau téléphonique commuté public (RTC).  <br/> |**Routage des communications vocales** <br/> |[Configuring Trunks and Translation Rules](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|Si vous avez déployé Voix Entreprise, vérifiez les paramètres de routage Voix Entreprise.  <br/> |**Routage des communications vocales** <br/> |[Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|Si vous avez déployé le serveur d’archivage, vérifiez que les stratégies et les paramètres d’archivage répondent aux besoins de votre organisation.  <br/> |**Surveillance et archivage** <br/> |[Managing Archiving](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|Si vous avez déployé le serveur de surveillance, affichez les rapports du serveur de surveillance pour afficher les informations d’utilisation et de diagnostic.  <br/> |**Accueil** <br/> |[Gérer l’intégrité et surveillance dans Skype pour Business Server](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |



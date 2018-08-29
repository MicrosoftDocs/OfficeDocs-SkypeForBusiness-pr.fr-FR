---
title: Liste de vérification de première exécution pour le panneau de configuration de Skype Entreprise Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
description: Bienvenue dans le Skype pour Business Server le panneau de configuration, l’interface utilisateur web pour l’administration et la gestion de Skype pour Business Server. Vous pouvez utiliser le panneau de configuration pour effectuer des types de tâche administrative effectuées en utilisant la console d’administration Microsoft.
ms.openlocfilehash: 56f3b330861b70042d1e30aba76ac33659a6675d
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23255115"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Liste de vérification de première exécution pour le panneau de configuration de Skype Entreprise Server

Bienvenue dans le Skype pour Business Server le panneau de configuration, l’interface utilisateur web pour l’administration et la gestion de Skype pour Business Server. Vous pouvez utiliser le panneau de configuration pour effectuer des types de tâche administrative effectuées en utilisant la console d’administration Microsoft.

Il existe un nombre de tâches importantes qu’il est vivement recommandé de qu'effectuer une fois que vous avez déployé Skype pour Business Server. Certaines de ces tâches sont des étapes de configuration initiales que vous avez peut-être déjà effectuées lors du déploiement, tandis que d’autres améliorent ou modifient des paramètres configurés lors du déploiement ou sont des paramètres par défaut. D’autres tâches décrites dans cette rubrique valident les configurations effectuées lors de la procédure de déploiement.

> [!NOTE]
> Avant d’effectuer les tâches dans le tableau suivant, assurez-vous que vous ouvrez une session à l’aide de droits d’utilisateur sont correctes, les autorisations et les rôles comme décrit dans la section « Rôles et étendue » de la rubrique [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) .

## <a name="first-run-checklist"></a>Liste de vérification de première exécution

Nous vous recommandons fortement que vous passez en revue les tâches mentionnées dans cette rubrique, puis effectuez les procédures appropriées pour le déploiement de Lync Server dans votre organisation.

|**Tâche**|**Groupe du panneau de configuration**|**Documentation**|
|:-----|:-----|:-----|
|Vérifiez que les services installés dans votre topologie sont exécutés de la façon escomptée.  <br/> |**Topologie** <br/> |[Afficher les détails d’un Service](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|Permettre aux utilisateurs de Skype pour Business Server. Si vous le souhaitez et, si une migration depuis une version précédente, déplacer des utilisateurs vers Skype pour Business Server.  <br/> |**Utilisateurs ** <br/> |[La gestion des utilisateurs](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|Si vous avez déployé ou si voulez déployer Voix Entreprise, configurez une connexion de jonction SIP pour activer la connectivité au réseau téléphonique commuté public (RTC).  <br/> |**Routage des communications vocales** <br/> |[Configuration de jonctions et des règles de traduction](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|Si vous avez déployé Voix Entreprise, vérifiez les paramètres de routage Voix Entreprise.  <br/> |**Routage des communications vocales** <br/> |[Tester le routage des communications vocales](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|Si vous avez déployé le serveur d’archivage, vérifiez que les stratégies et les paramètres d’archivage répondent aux besoins de votre organisation.  <br/> |**Surveillance et archivage** <br/> |[Gestion de l’archivage](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|Si vous avez déployé le serveur de surveillance, affichez les rapports du serveur de surveillance pour afficher les informations d’utilisation et de diagnostic.  <br/> |**Accueil** <br/> |[Gestion de l’intégrité et de la surveillance dans Skype Entreprise Server 2015](../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |



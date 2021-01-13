---
title: Liste de vérification de première exécution pour le panneau de configuration de Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
ROBOTS: NOINDEX, NOFOLLOW
description: Bienvenue dans le Panneau de contrôle Skype Entreprise Server, l’interface utilisateur web pour l’administration et la gestion de Skype Entreprise Server. Vous pouvez utiliser le panneau de contrôle pour effectuer les types de tâches administratives qui ont été effectuées à l’aide de la console de gestion Microsoft dans les versions précédentes.
ms.openlocfilehash: fdd6aeefb6c4914dec54673f426c95c4028388ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836624"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Liste de vérification de première exécution pour le panneau de configuration de Skype Entreprise Server

Bienvenue dans le Panneau de contrôle Skype Entreprise Server, l’interface utilisateur web pour l’administration et la gestion de Skype Entreprise Server. Vous pouvez utiliser le panneau de contrôle pour effectuer les types de tâches administratives qui ont été effectuées à l’aide de la console de gestion Microsoft dans les versions précédentes.

Il existe un certain nombre de tâches importantes que nous vous recommandons vivement d’effectuer après avoir déployé Skype Entreprise Server. Certaines de ces tâches sont des étapes de configuration initiales que vous avez peut-être déjà effectuées pendant le déploiement, tandis que d’autres sont des perfectionnements ou des modifications de paramètres que vous avez configurés pendant le déploiement ou de paramètres par défaut. D’autres tâches décrites dans cette rubrique valident les configurations que vous avez effectuées pendant le processus de déploiement.

> [!NOTE]
> Avant d’effectuer les tâches du tableau suivant, veillez à vous connecter à l’aide des droits d’utilisateur, autorisations et rôles corrects, comme décrit dans la section « Rôles et étendue » de la rubrique Contrôle d’accès basé sur un rôle. [](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)

## <a name="first-run-checklist"></a>Liste de vérification de première exécution

Nous vous recommandons vivement de passer en revue les tâches mentionnées dans cette rubrique, puis d’effectuer les procédures appropriées pour le déploiement dans votre organisation.

|**Tâche**|**Groupe Panneau de contrôle**|**Documentation**|
|:-----|:-----|:-----|
|Vérifiez que les services que vous avez installés dans votre topologie sont exécutés comme prévu.  <br/> |**Topologie** <br/> |[Afficher les détails d’un service](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|Activez les utilisateurs pour Skype Entreprise Server. Facultatif et, si vous migrez à partir d’une version précédente, déplacez les utilisateurs vers Skype Entreprise Server.  <br/> |**Utilisateurs** <br/> |[Gestion des utilisateurs](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|Si vous avez déployé ou voulez déployer Voix Entreprise, configurez une connexion de jonction SIP pour activer la connectivité au réseau téléphonique commuté public (PSTN).  <br/> |**Routage des communications vocales** <br/> |[Configuration des trunks et des règles de traduction](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|Si vous avez déployé Voix Entreprise, vérifiez les paramètres de routage Voix Entreprise.  <br/> |**Routage des communications vocales** <br/> |[Tester le routage des communications vocales](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|Si vous avez déployé le serveur d’archivage, vérifiez que les stratégies et les paramètres d’archivage répondent aux besoins de votre organisation.  <br/> |**Surveillance et archivage** <br/> |[Gestion de l’archivage](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|Si vous avez déployé le serveur de surveillance, affichez les rapports du serveur de surveillance pour afficher les informations d’utilisation et de diagnostic.  <br/> |**Accueil** <br/> |[Gérer l’état d’santé et la surveillance dans Skype Entreprise Server](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |



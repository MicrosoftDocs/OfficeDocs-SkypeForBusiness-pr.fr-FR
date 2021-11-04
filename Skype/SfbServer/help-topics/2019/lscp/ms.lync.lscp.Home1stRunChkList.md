---
title: Liste de vérification de première exécution pour le panneau de configuration de Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
ROBOTS: NOINDEX, NOFOLLOW
description: Bienvenue dans le Panneau de Skype Entreprise Server, l’interface utilisateur web pour l’administration et la gestion des Skype Entreprise Server. Vous pouvez utiliser le panneau de contrôle pour effectuer les types de tâches administratives qui ont été effectuées à l’aide de la console de gestion Microsoft dans les versions précédentes.
ms.openlocfilehash: 21f4f2f3add2ba287357243463967e93d3ebe7b4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60742760"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Liste de vérification de première exécution pour le panneau de configuration de Skype Entreprise Server

Bienvenue dans le Panneau de Skype Entreprise Server, l’interface utilisateur web pour l’administration et la gestion des Skype Entreprise Server. Vous pouvez utiliser le panneau de contrôle pour effectuer les types de tâches administratives qui ont été effectuées à l’aide de la console de gestion Microsoft dans les versions précédentes.

Il existe un certain nombre de tâches importantes que nous vous recommandons vivement d’effectuer une fois que vous avez déployé Skype Entreprise Server. Certaines de ces tâches sont des étapes de configuration initiales que vous avez peut-être déjà effectuées pendant le déploiement, tandis que d’autres sont des perfectionnements ou des modifications de paramètres que vous avez configurés pendant le déploiement ou de paramètres par défaut. D’autres tâches décrites dans cette rubrique valident les configurations que vous avez effectuées pendant le processus de déploiement.

> [!NOTE]
> Avant d’effectuer les tâches du tableau suivant, veillez à vous connecter à l’aide des droits d’utilisateur, autorisations et rôles corrects, comme décrit dans la section « Rôles et étendue » de la rubrique Contrôle d’accès basé sur un rôle. [](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control)

## <a name="first-run-checklist"></a>Liste de vérification de première exécution

Nous vous recommandons vivement de passer en revue les tâches mentionnées dans cette rubrique, puis d’effectuer les procédures appropriées pour le déploiement dans votre organisation.

|**Tâche**|**Groupe Panneau de contrôle**|**Documentation**|
|:-----|:-----|:-----|
|Vérifiez que les services que vous avez installés dans votre topologie sont exécutés comme prévu.  <br/> |**Topologie** <br/> |[Afficher les détails d’un service](/previous-versions/office/lync-server-2013/lync-server-2013-view-details-about-a-service) <br/> |
|Activez les utilisateurs pour Skype Entreprise Server. Éventuellement et, si vous migrez à partir d’une version précédente, déplacez les utilisateurs vers Skype Entreprise Server.  <br/> |**Utilisateurs** <br/> |[Gestion des utilisateurs](/previous-versions/office/lync-server-2013/lync-server-2013-user-accounts-enabled-for-lync-server) <br/> |
|Si vous avez déployé ou voulez déployer Voix Entreprise, configurez une connexion de jonction SIP pour activer la connectivité au réseau téléphonique commuté public (PSTN).  <br/> |**Routage des communications vocales** <br/> |[Configuration des trunks et des règles de traduction](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-trunks) <br/> |
|Si vous avez déployé Voix Entreprise, vérifiez les paramètres de routage Voix Entreprise.  <br/> |**Routage des communications vocales** <br/> |[Tester le routage des communications vocales](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing) <br/> |
|Si vous avez déployé le serveur d’archivage, vérifiez que les stratégies et les paramètres d’archivage répondent aux besoins de votre organisation.  <br/> |**Surveillance et archivage** <br/> |[Gestion de l’archivage](/previous-versions/office/lync-server-2013/lync-server-2013-managing-archiving) <br/> |
|Si vous avez déployé le serveur de surveillance, affichez les rapports du serveur de surveillance pour afficher les informations d’utilisation et de diagnostic.  <br/> |**Accueil** <br/> |[Gérer l’état d’Skype Entreprise Server](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |
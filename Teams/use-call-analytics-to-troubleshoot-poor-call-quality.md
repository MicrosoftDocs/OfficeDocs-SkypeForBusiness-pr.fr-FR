---
title: Utiliser les données d’analyse des appels pour résoudre les problèmes de qualité des appels
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: Utilisez des informations d’analyse des appels par utilisateur sur les appareils, les réseaux et la connectivité pour résoudre les problèmes des utilisateurs en rapport avec les Microsoft Teams et les réunions.
ms.openlocfilehash: 4732cf68624b824a452455fc779b22ae7eb32d56
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760559"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Utiliser les données d’analyse des appels pour résoudre les problèmes de qualité des appels

Cet article explique comment utiliser l’analyse des appels pour résoudre des problèmes de qualité d’appel ou de réunion Microsoft Teams pour des utilisateurs individuels si vous êtes un administrateur de Teams ou un ingénieur ou spécialiste en support des communications Teams.

## <a name="call-analytics-permissions"></a>Autorisations d’analyse des appels

Cet article part du principe que vous avez déjà installé l’analyse des appels. Si ce n’est pas le cas, lisez [Configurer l’analyse](set-up-call-analytics.md)des appels pour Teams.

## <a name="introduction-to-call-analytics"></a>Présentation de l’analyse des appels

L’analyse des appels affiche des informations détaillées sur les Teams et les réunions pour chaque utilisateur de Office 365 compte. Il inclut des informations sur les périphériques, les réseaux, la connectivité et la qualité des appels (l’un de ces facteurs peut être un facteur de mauvaise qualité de l’appel ou de la réunion). Si vous chargez des informations sur le bâtiment, le site et le client, ces informations sont également affichées pour chaque appel et réunion. Utilisez les données d’analyse des appels pour comprendre en quoi l’expérience d’appel ou de réunion d’un utilisateur est médiocre.

L’analyse des appels vous montre chaque partie d’un appel ou d’une réunion (par exemple, d’un participant à un deuxième participant). En analysant ces détails, un Teams peut isoler les zones problématiques et identifier la cause première d’une mauvaise qualité.

En tant qu Teams administrateur de services, vous accédez à l’ensemble des données d’analyse des appels pour chaque utilisateur. De plus, vous pouvez attribuer des rôles Azure Active Directory au personnel de support technique. Pour en savoir plus sur ces rôles, lisez [Accorder l’autorisation](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)au support technique et aider le personnel. Ne manquez pas ce [que font Teams rôle de support technique ? ci-dessous.](#what-does-each-teams-support-role-do)

## <a name="where-to-find-per-user-call-analytics"></a>Où trouver les données d’analyse des appels par utilisateur

Pour voir toutes les informations et données d’appel d’un utilisateur, rendez-vous dans le [Teams d’administration.](https://admin.teams.microsoft.com) Sous **Utilisateurs,** sélectionnez un utilisateur, puis ouvrez l’onglet **& Appels** sur la page de profil de l’utilisateur. Vous y trouverez tous les appels et les réunions de cet utilisateur au cours des 30 derniers jours.

![Capture d’écran de toutes les données d’analyse des utilisateurs](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

Pour obtenir des informations supplémentaires sur une session donnée, y compris des statistiques détaillées sur les médias et la mise en réseau, cliquez sur une session pour en voir les détails.

![Capture d’écran des données de session de l’utilisateur d’analyse des appels](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

## <a name="what-does-each-teams-support-role-do"></a>Que peut faire Teams de support technique ?

Le **spécialiste Teams du support aux communications** (support de niveau 1) gère les problèmes de qualité des appels de base. Ils n’examinent pas les problèmes de réunions. Au lieu de cela, ils collectent des informations connexes, puis les font parler à un ingénieur du support des communications.

La **Teams du support** des communications (support de niveau 2) voit des informations dans des journaux d’appels détaillés qui sont masqués par le spécialiste Teams support aux communications. Le tableau ci-dessous répertorie les informations disponibles pour Teams rôle de support de la communication.

Le tableau suivant vous indique quelles informations par utilisateur sont disponibles pour chaque rôle de support technique pour les communications.

|Activité|Information|Quels sont les communications<br>spécialiste *du* support technique|Quels sont les communications<br>*l’ingénieur support* voit|
|---|---|---|---|
|**Appels**|Nom de l’appelant|Seul le nom de l’utilisateur pour lequel l’agent a recherché.|Nom d’utilisateur.|
||Nom du destinataire|Affiche en tant qu’utilisateur interne ou utilisateur externe.|Nom du destinataire.|
||Numéro de téléphone de l'appelant|Les numéros de téléphone entiers, à l’exception des trois derniers chiffres, sont masqués par des symboles astérisques. Par exemple, 15552823. \* \* \*|Les numéros de téléphone entiers, à l’exception des trois derniers chiffres, sont masqués par des symboles astérisques. Par exemple, 15552823. \* \* \*|
||Numéro de téléphone du destinataire|Les numéros de téléphone entiers, à l’exception des trois derniers chiffres, sont masqués par des symboles astérisques. Par exemple, 15552823. \* \* \*|Les numéros de téléphone entiers, à l’exception des trois derniers chiffres, sont masqués par des symboles astérisques. Par exemple, 15552823. \* \* \*|
||**Détails de l’appel** \> **Onglet** Avancé|Informations non affichées.|Tous les détails affichés, tels que le nom des appareils, l’adresse IP, le mappage de sous-réseau, etc.|
||**Détails de l’appel** \> **Avancé** \> **Onglet Débogage**|Informations non affichées.|Tous les détails affichés, tels que le suffixe DNS et SSID.|
|**Réunions**|Noms des participants|Seul le nom de l’utilisateur pour lequel l’agent a recherché. Autres participants identifiés comme utilisateur interne ou utilisateur externe.|Tous les noms affichés.|
||Nombre de participants|Nombre de participants.|Nombre de participants.|
||Détails de la session|Détails de la session affichés avec des exceptions. Seul le nom de l’utilisateur pour lequel l’agent a recherché s’affiche. Autres participants identifiés comme utilisateur interne ou utilisateur externe. Les trois derniers chiffres d’un numéro de téléphone entre deux symboles astérisques.|Détails de la session affichés. Noms d’utilisateur et détails de session affichés. Les trois derniers chiffres d’un numéro de téléphone entre deux symboles astérisques.|
||||

## <a name="troubleshoot-user-call-quality-problems"></a>Résoudre les problèmes de qualité des appels des utilisateurs

1. Ouvrez le Teams d’administration de l’entreprise () et connectez-vous à l’aide Teams du support des communications ou Teams <https://admin.teams.microsoft.com> informations d’identification d’administrateur.

2. Dans Le tableau de **bord,** dans la recherche d’utilisateurs, commencez à taper le  nom ou l’adresse SIP de l’utilisateur dont vous souhaitez résoudre les problèmes, ou sélectionnez Afficher les utilisateurs pour afficher la liste des utilisateurs.

3. Sélectionnez l’utilisateur dans la liste.

4. Sélectionnez **l’historique** des appels, puis l’appel ou la réunion à résoudre.

5. Sélectionnez **l’onglet** Avancé, puis recherchez les éléments jaunes et rouges qui indiquent une mauvaise qualité d’appel ou des problèmes de connexion.

   Dans les détails de la session pour chaque appel ou réunion, les problèmes mineurs apparaissent en jaune. Si un point est jaune, il ne se trouve pas dans une plage normale et contribue peut-être au problème, mais il est peu probable qu’il s’agit de la cause principale du problème. Si un problème est de couleur rouge, il s’agit d’un problème significatif, qui est probablement la cause principale de la mauvaise qualité des appels pour cette session.

Dans de rares cas, les données de qualité de l’expérience ne sont pas reçues pour les sessions audio. Cette situation est souvent due à l’abandon d’un appel ou à la fin de la connexion au client. Dans ce cas, l’évaluation de la session **est indisponible.**

Pour les sessions audio qui ont des données de qualité de l’expérience (QoE), le tableau suivant décrit les principaux problèmes qui qualifier une session comme **médiocre.**

|Problème|Domaine|Description|
|---|---|---|
|Configuration des appels|Session|Le code d’erreur Ms-diag 20-29 indique que la configuration de l’appel a échoué. L’utilisateur n’a pas pu participer à l’appel ou à la réunion.|
|Réseau audio classé comme médiocre|Session|Des problèmes de qualité réseau (tels que la perte de paquets, la gigue, la dégradation NMOS, la rtT ou les proportions d’enveloppe) se sont produits.|
|L’appareil ne fonctionne pas|Device|Un appareil ne fonctionne pas correctement. Les proportions des appareils non fonctionnels sont les autres : <p> DeviceRenderNotFunctioningEventRatio >= 0,005 <br>  DeviceCaptureNotFunctioningEventRatio >= 0,005|
||||

## <a name="related-topics"></a>Sujets associés

[Configurer l’analyse des appels par utilisateur](set-up-call-analytics.md)

---
title: Salles Microsoft Teams’entreprise
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Fournir une vue d’état de vos salles de réunion.
f1keywords: ''
ms.openlocfilehash: db8f6125bda335dfab2f9208fcfd8ab0f192e4e7
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767526"
---
# <a name="microsoft-managed-meeting-rooms-portal"></a>Portail Salles de réunion gérées par Microsoft

## <a name="overview"></a>Présentation

Le portail Salles de réunion gérées (« Portail Salles ») fournit une vue d’état de vos salles de réunion. Un affichage client de ce portail est pour votre visibilité et vos commentaires, et pour faciliter vos outils/pratiques d’analyse existants.

L’étendue de la surveillance est

- Affichage des incidents
  - Principaux problèmes affectant vos salles
  - Actions requises pour rétablir l’état d’santé des salles
  - Problèmes en cours d’investigation par Microsoft
- Affichage des appareils Microsoft Teams salle
  - Instantané de l’état au Salles Microsoft Teams de l’appareil (MTR)
  - Historique et détails de base pour chaque appareil

**Affichage des appareils Microsoft Teams salle**

- Instantané de l’état au Salles Microsoft Teams de l’appareil (MTR)
- Historique et détails de base pour chaque appareil

> [!Important]
> Examinez [**attribuer aux utilisateurs le**](enrolling-mtrp-managed-service.md#assign-users-to-the-managed-service-administrator-role) rôle Administrateur de services gérés et assurez-vous que l’accès au portail est limité en fonction des besoins de votre entreprise.

## <a name="terminology"></a>Terminologie

Voici les termes fréquemment utilisés dans le portail.

|Terme |Signification |
| :- | :- |
|**Logiciel de surveillance** |Agent de surveillance déployé sur chacun des appareils de Microsoft Teams salle. |
|**Application** |Microsoft Teams’application Room System (qu’elle utilise Skype Entreprise ou Microsoft Teams comme service de collaboration. |
|**Salle/Appareil** |Le périphérique certifié Microsoft Teams room system. |
|**Non contrôlé** | Les logiciels de surveillance Microsoft déployés dans le cadre des services gérés ne peuvent pas se connecter aux services cloud. Nous ne recevons pas de télémétrie sur l’appareil. |
|<p>**Saine /** </p><p>**Défectueux** </p>|(s) dans l’appareil/périphérique. |
|**Supprimé** |Si un périphérique est connu pour être en maintenance et que ses alertes doivent être ignorées, l’appareil peut être supprimé délibérément. |
|**Intégration** |L’état d’un appareil de salle pendant sa configuration est ajouté, mais n’est pas prêt comme une salle régulièrement prise en charge. |
|**Incident** |Problème affectant les expériences de réunion des utilisateurs finaux qui ont besoin d’une action. |
|**Configuration mal configurée** |La configuration détectée n’est pas correcte / souvent utilisée. |
|**Support Ticket** |Identificateur de suivi Microsoft interne qui suit toutes les communications/actions relatives à un incident. |

## <a name="incidents-view"></a>Affichage Incidents

Cet affichage est une vue d’ensemble de l’onglet Incidents dans le portail Salles gérées. Cette page est la page d’accueil par défaut du portail.

### <a name="top-level-summary"></a>Résumé de niveau supérieur 
Le résumé de niveau supérieur présente en un coup d’œil les problèmes qui affectent vos salles, ce que vous devez faire et ce que Microsoft fait à leur sujet :

![Capture d’écran montrant un résumé des problèmes de niveau supérieur](../media/rooms-monitor-001new.png)

|# |Explication |
| :- | :- |
|1 |Types d’incidents affectant vos salles |
|2 |**ACTION DE LA NÉCESSITÉ**: éléments nécessitant votre intervention à résoudre. |
|3 |**AFFECTÉ À MICROSOFT**: Éléments pour l’instant examinés par le personnel de Microsoft. |
|4 |**EXAMEN EN ATTENTE**: Éléments dans la file d’attente à examiner par le personnel microsoft. |

Les incidents devraient se trouver dans l’un des trois états :

- **Action du besoin**: vous est attribué pour action
- **Affecté à Microsoft**: Affecté à Microsoft pour l’action suivante
- **Examen en attente**: examen en cours pour les étapes suivantes

### <a name="reviewing-incidents"></a>Révision des incidents

L’image suivante répertorie tous les incidents actuellement actifs dans vos salles. Ceux qui vous sont  attribués sont dans la partie supérieure : voici ce que vous devez examiner pour les étapes suivantes. En outre, ceux affectés à Microsoft ou à l’examen en attente ont des détails que vous pouvez utiliser pour intervenir.

Le fait de cliquer sur un des éléments dont l’état est «**Action** des besoins » affiche des détails supplémentaires sur l’incident.

## <a name="types-of-incidents"></a>Types d’incidents

Les incidents sont classés avec deux types de gravité générale :

- **Important**: les incidents susceptibles de causer des problèmes dans les réunions et qui doivent être prioritaires.
- **Avertissement :** incidents qui sont des notifications pour planifier des actions de maintenance. Si ces salles ne sont pas prises en charge, il est probable qu’elles soient plus susceptibles d’être prises en charge. Les avertissements vous donnent le temps de planifier et de soutenir l’assistance.

Un avertissement peut passer à «**Important**» s’il n’est pas participé à un certain temps.

## <a name="health-status-of-device-and-incidents"></a>État d’état du périphérique et incidents

Les incidents classés comme **« Important** » dans la gravité affectent l’état d’état d’un appareil. Si au moins un incident de gravité **= « Important »** est associé à un appareil, il est considéré comme **_un_** appareil défectueux.

Les incidents classés **comme étant de gravité de l’avertissement** n’affectent pas l’état d’état signalé sur un appareil. Toutefois, si un appareil est associé à des incidents de niveau d’avertissement, il s’affiche avec l’état d’état de l’appareil comme suit.

![Capture d’écran montrant l’état d’état d’une salle](../media/rooms-monitor-004.jpg)

Voici quelques-uns des types d’incidents que vous pouvez voir et les explications de chaque type. Pour chaque type, l’action associée à l’incident sera plus spécifique en fonction du problème.

**Tableau 1 : incidents avec une gravité « Importante »**

|Type |Explication |
| :- | :- |
|**Affichage** |L’affichage connecté à l’appareil ne semble pas être sain.|
|**Microphone de conférence, haut-parleur de conférence** |Les périphériques audio (micro/haut-parleur) semblent mal configurés. |
|**Appareil photo** |L’appareil photo connecté à l’appareil ne semble pas être en bon état. |
|**HDMI Ingest** |HDMI Ingest n’est pas sain. |
|**Sign-in** (Exchange) |Microsoft Teams l’application Room accède aux informations de calendrier de Exchange et les problèmes de réussite de la signature sont signalés en cas d’incident de inscription. |
|**Se connectez** (Teams) |Microsoft Teams’application Room se connecte à l’appareil et l’échec de la se connecte sera signalé avec cet incident (si le client utilise Teams). |
|**Se connectez** (Skype Entreprise) |Microsoft Teams’application Room se connecte à l’appareil, et l’échec de la connecté est signalé avec cet incident (si le client utilise Skype Entreprise) |
|**Capteur de proximité** |Microsoft Teams’application Salle invite les participants à participer à une réunion s’ils sont à proximité. Les échecs de cette fonctionnalité seront signalés dans le cadre de cet incident. |

**Tableau 2 : Incidents avec gravité de l’avertissement**

|Type |Explication |
| :- | :- |
|**Version de l’application** |La version de l’Microsoft Teams Room s’exécutant sur l’appareil n’est pas à jour. Les versions obsolètes sont les causes connues des problèmes connus des utilisateurs. |
|**Version du système d’exploitation** |La version de votre Windows d’exploitation s’exécutant dans la salle de réunion n’est plus recommandée. |
|**Réseau** |Ce type d’avertissement sera supprimé à l’avenir en raison d’un travail supplémentaire requis après l’évaluation. |

## <a name="responding-to-incidents"></a>Réponse aux incidents

Les incidents sont de trois catégories : Action des besoins, Examen en attente ou Affecté à Microsoft.

### <a name="needs-action-incidents"></a>Incidents de « nécessite une action »

Les incidents dont l’état est « Action nécessaire **»** vous sont attribués pour qu’une action corrective soit entreprise.

Chaque incident de ce type aura un champ d’action avec une action recommandée par Microsoft comme suit :

![Capture d’écran montrant l’action d’incident recommandée](../media/rooms-monitor-005.jpg)

- Si vous avez pris cette action, vous pouvez répondre à l’incident en insérez vos notes dans la zone Répondre, puis sélectionner « Attribuer à Microsoft » avant de publier.
- Il est également possible que la notification soit incorrecte sur la base de votre avis. Dans ce cas, faites part de vos commentaires et attribuez-le à Microsoft.
- Enfin, si vous souhaitez ajouter un commentaire afin de fournir davantage de contexte pour votre propre équipe ou pour l’équipe Microsoft, publiez le message sans avoir à mettre en place l’attribution à Microsoft.

>[!NOTE]
>Votre action corrective peut résoudre le problème et l’analyse des salles gérées effacera cet incident de votre liste. Dans le cas ci-dessus, vous n’avez peut-être pas la possibilité de résoudre le problème et de le ré-attribuer à Microsoft. Ce problème sera résolu dans une prochaine version.

### <a name="pending-investigation-incidents"></a>Incidents de « Examen en attente »

Pour les incidents en cours d’investigation, le champ de description contient des informations sur l’incident, les causes classiques et les résolutions qui peuvent être utiles pour résoudre certains problèmes afin que vous pouvez agir sans délai.

### <a name="assigned-to-microsoft-incidents"></a>Incidents « Affectés à Microsoft »

Pour les incidents attribués à Microsoft, le champ « Action » contiendra de brefs détails sur les étapes correctives planifiées ou progressions. Ces étapes peuvent avoir besoin d’une collaboration avec votre équipe, et une collaboration étendue sera effectuée par e-mail/appels au besoin. Une fois ces problèmes résolus, ils disparaîtront du portail et, à l’avenir, ils seront suivis et résolus dans l’historique.

![Capture d’écran montrant les étapes correctives MS](../media/rooms-monitor-006.jpg)

## <a name="rooms-view"></a>Vue Salles

Chaque appareil est un proxy pour une salle et ses périphériques connectés. Un appareil sain représente une salle saine, et un appareil défectueux représente une salle qui peut être à l’origine de problèmes pendant les réunions. Outre l’affichage Incidents, le portail Salles gérées fournit également une vue d’ensemble de l’état de la salle et vous aide à dépanner les détails des appareils et à comprendre les échecs répétés dans l’historique des incidents.

![Capture d’écran montrant la vue d’ensemble de l’état d’une salle](../media/rooms-monitor-007.jpg)

**Sain, défectueux, déconnecté** Le panneau supérieur de l’affichage Salles fournit un instantané rapide du bon état de nombre de vos appareils (« En bonne santé »), du nombre affectés par des problèmes (« Défectueux »), du nombre de personnes qui ne fournissent pas de données de télémétrie (« Déconnecté ») et du nombre d’appareils supprimés de l’alerte (en tant que remplacement). Les salles sont surveillées pour leur santé à l’aide de critères évolutifs et de critères heuristiques. L’objectif est de refléter la réalité de l’expérience utilisateur dans la salle le plus précisément possible et de la rendre actionnable.

**Salles saines/non saines**:

Les appareils/périphériques qui n’ont aucun incident de gravité « Important » sont ceux qui sont marqués comme sains. Toutefois, cela n’implique pas qu’il y a une panne de place pour tous les appareils défectueux dans le portail. La partie description et action de l’incident contient des détails plus spécifiques sur le problème et l’impact potentiel sur l’expérience utilisateur.

**Appareil déconnecté :**

L’agent de surveillance Microsoft déployé dans le cadre du pilote Salles gérées est déconnecté des services cloud des salles gérées. Nous ne recevons pas de télémétrie sur la salle et n’avons pas le statut le plus récent. Cela peut se produire en raison de problèmes réseau, de modifications de la stratégie de pare-feu ou de modifications apportées à l’image de l’appareil.

## <a name="room-detail-status-and-changes"></a>Détails de la salle : État et modifications

**Détails de la salle : État** *L’onglet* État du périphérique fournit une vue consolidée de l’état d’un appareil, de tous les problèmes actifs pour l’appareil, des actions nécessaires pour les résoudre ou qui sont en cours. L’onglet État présente également la répartition des différents composants d’état d’état de l’appareil sous *l’onglet Incidents.* Si un appareil est déconnecté, les détails de l’état ne sont pas disponibles.

![Capture d’écran montrant l’affichage état consolidé](../media/rooms-monitor-008.png)

**Afficher tous les signaux :** Pour afficher tous les signaux d’une catégorie de signaux, activez le bouton bascule Afficher tous les signaux. Des flèches d’extension apparaissent en regard des titres de catégorie sur lesquels vous pouvez cliquer pour développer la vue d’accordion.

![Capture d’écran montrant des signaux au sein d’une catégorie](../media/rooms-monitor-009.png)

**Supprimer/désapresser le ticket** Lorsqu’une salle est inscrite, vous indiquez que vous souhaitez recevoir des notifications pour les modifications apportées à la télémétrie de salle. Il peut se produire qu’un appareil ou un périphérique particulier se trouve dans un état connu où vous ne souhaitez pas que des tickets ou notifications soient générés. L’utilisation de la fonctionnalité Supprimer le ticket supprimera toute notification concernant ce signal particulier. Lorsque vous êtes prêt à ce que le service surveille et vous informe à propos de ce signal, il vous suffit de les compresser individuellement.

![Capture d’écran montrant les tickets supprimés d’une salle](../media/rooms-monitor-010.png)

**Extension de la catégorie de ticket actif** Sous chaque catégorie de ticket, un ticket actif ou le dernier ticket résolu s’affiche avec la gravité et la date de la dernière mise à jour du ticket. En cliquant sur la flèche d’extension, tous les tickets s’affichent avec un lien actif vers les informations sur les tickets.

Extension de la catégorie de ticket actif : sous chaque catégorie de ticket, un ticket actif ou le dernier ticket résolu s’affiche avec la gravité et la date de la dernière mise à jour du ticket. En cliquant sur la flèche d’extension, tous les tickets s’affichent avec un lien actif vers les informations sur les tickets.

![Capture d’écran montrant la catégorie de ticket résolue](../media/rooms-monitor-011.png)

## <a name="active-ticket-overview"></a>Ticket actif : Vue d’ensemble

Chaque incident créé identifie le problème détecté et l’action corrective à mettre en place pour rétablir l’état de la salle. Le ticket généré véhicule une vue d’ensemble des incidents avec tous les messages générés par l’IA des services gérés, ainsi que l’équipe d’ingénierie du service Microsoft qui enquête sur le problème. Toutes les pièces jointes collectées pour la résolution des problèmes d’incident sont répertoriées. L’onglet Historique contient les dates à qui des problèmes ont été identifiés.

![Capture d’écran montrant une vue d’ensemble des tickets actifs](../media/rooms-monitor-012.png)

Ticket actif : Messages L’interface utilisateur des messages est le principal outil de communication pour interagir avec les ingénieurs du service Microsoft afin de corriger le problème identifié. Il est important de prendre réception des communications de Microsoft afin de vous assurer que nous vous fournissons le meilleur service possible. Si vous avez pris les mesures recommandées, répondez à cet incident en insliquant sur vos notes dans la zone Répondre et attribuez-les à Microsoft en cliquant sur Attribuer à Microsoft avant de publier.
Il est également possible que la notification soit incorrecte sur la base de votre avis. Dans ce cas, faites part de vos commentaires et attribuez-le à Microsoft.
Enfin, si vous souhaitez ajouter un commentaire afin de fournir davantage de contexte pour votre propre équipe ou pour Microsoft, publiez simplement le message sans avoir à mettre en place l’erreur « Affecter à Microsoft .

![Capture d’écran montrant les messages de ticket actif](../media/rooms-monitor-013.png)


Ticket actif : Pièces jointes Dans certains cas, les ingénieurs du service Microsoft ont besoin d’informations supplémentaires pour améliorer leur examen du problème. L’onglet Pièce jointe vous permet de télécharger des images, des vidéos ou des journaux qui sont demandés.

![Capture d’écran montrant des attachmments de ticket actifs](../media/rooms-monitor-014.png)

Ticket actif : Historique Chaque signal de salle est affecté à un seul numéro de ticket. Un périphérique ou un appareil de salle est persistant dans une salle et peut-être en problème au fil du temps. En conservant ces informations sous un ID de ticket unique spécifique, toutes les informations historiques sont conservées et peuvent être analysées pour des modèles de comportement. L’interface utilisateur Historique affiche toutes les actions de tickets créées et résolues pour ce signal.

![Capture d’écran montrant l’historique des tickets actifs](../media/rooms-monitor-015.png)

Faq Comment les tickets dynamiques affectent-ils moi et les opérations de mes salles ?  
Les clients voient la création de tickets et de corrections plus intelligents qui se développent au-delà d’un simple ticket de signal binaire. Par exemple, un Salle de réunion peut afficher jusqu’à trois écrans (Affichage 1, Affichage 2 &'affichage du panneau tactile MTR). Toutefois, seul un (un) signal d’affichage est saine ou défectueux. Grâce aux nouveaux tickets dynamiques, nous pouvons désormais générer des tickets propres à chaque signal d’affichage.

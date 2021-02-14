---
title: Assistant Stratégies de Teams pour l’Éducation pour appliquer facilement des stratégies pour un apprentissage sécurisé
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: shajohri, angch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser l’Assistant Stratégie de Teams pour l’Éducation afin d’appliquer facilement des stratégies pour les étudiants et les enseignants afin de préserver la sécurité de votre environnement d’apprentissage.
f1keywords: ''
ms.openlocfilehash: 1ea7fb684bce3d59063f1a258d0db37fb75a4681
ms.sourcegitcommit: 95b85926d67cbf3159f58d9083d5813cc29074f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790418"
---
# <a name="use-the-teams-for-education-policy-wizard-to-easily-apply-policies-for-a-safe-learning-environment"></a>Utiliser l’Assistant Stratégie de Teams pour l’Éducation pour appliquer facilement des stratégies à un environnement d’apprentissage sécurisé

## <a name="overview"></a>Présentation

L’Assistant Stratégie de Microsoft Teams pour l’Éducation simplifie la gestion des stratégies pour vos étudiants et enseignants. Utilisez-la pour appliquer facilement et rapidement l’ensemble le plus important de stratégies pertinentes pour créer une expérience d’apprentissage sécurisée et productive.

Les stratégies dans Teams vous offrent la manière dont Teams se comporte dans votre environnement et les fonctionnalités disponibles pour les utilisateurs. Par exemple, il existe des stratégies d’appel, des stratégies de réunion et des stratégies de messagerie, entre autres, et chaque zone de stratégie peut être personnalisée pour répondre aux besoins de votre organisation.

Pour maintenir un environnement d’apprentissage sécurisé et concentré, il est important de définir des stratégies pour contrôler ce que les étudiants peuvent faire dans Teams. Par exemple, vous pouvez utiliser des stratégies pour contrôler qui peut utiliser la conversation privée et les appels privés, qui peut planifier des réunions et quels types de contenu peuvent être partagés. Vous pouvez également utiliser des stratégies pour activer les fonctionnalités de Teams qui enrichissent l’expérience d’apprentissage.

Les stratégies doivent être ajustées pour les étudiants et les enseignants afin de préserver la sécurité de l’expérience d’apprentissage. Les stratégies pour les étudiants doivent être plus restrictives afin de réduire leur risque de recevoir des niveaux d’accès inappropriés. Les enseignants et le personnel ont besoin d’un ensemble distinct de stratégies qui peuvent être plus permissives pour leur réussite. Par exemple, autorisez les enseignants à planifier des réunions et empêchez les étudiants de le faire.

:::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Capture d’écran de l’Assistant":::

Cet article vous explique comment exécuter l’Assistant.

> [!IMPORTANT]
> Les stratégies appliquées par l’Assistant répondront aux besoins de la majorité des clients Teams pour l’éducation. L’Assistant ajuste la définition globale (à l’échelle de l’organisation par défaut) d’un ensemble principal de stratégies avec des paramètres que nous recommandons pour la sécurité des étudiants et les applique aux étudiants. L’Assistant crée et affecte également un ensemble de stratégies personnalisées aux enseignants et aux membres du personnel. La plupart des clients Teams pour l’éducation n’auront pas besoin d’utiliser d’autres méthodes d’affectation de stratégie après avoir utilisé cet Assistant. Utilisez d’autres méthodes *d’affectation* de stratégies uniquement si vous voulez créer et gérer manuellement des stratégies pour vos étudiants, enseignants et membres du personnel.

## <a name="teams-for-education-policy-wizard"></a>Assistant Stratégie de Teams pour l’Éducation

<a name="polwiz_intro"> </a>

L’Assistant applique un ensemble de définitions de stratégie principale aux étudiants et un ensemble distinct de définitions de stratégies principales aux enseignants et au personnel, avec des paramètres appropriés pour chacune d’elles. Voici ce qui se produit lorsque vous exécutez l’Assistant.

L’Assistant définit les stratégies en fonction du type d’établissement d’enseignement (enseignement primaire **ou** **secondaire ou supérieur).** Vous sélectionnez le type de votre établissement, et l’Assistant doit :

- **Étudiants**: L’Assistant ajuste la définition de stratégie globale (à l’échelle de l’organisation par défaut) de chaque zone de stratégie couverte par l’Assistant avec de nouveaux paramètres par défaut appropriés pour protéger vos étudiants. Cela garantit que vos étudiants actuels et tous les nouveaux étudiants obtiennent le jeu de stratégies le plus restrictif.
- **Enseignants et membres** du personnel : L’Assistant crée un ensemble de définitions de stratégie personnalisées pour chaque zone de stratégie couverte par l’Assistant, avec des paramètres adaptés aux besoins des enseignants et du personnel. Il affecte ensuite les définitions de stratégie au groupe d’enseignants et de membres du personnel que vous choisissez. Ainsi, vos enseignants et membres du personnel obtiennent un ensemble de stratégies plus permissif pour leur réussite.

Il vous suffit d’exécuter l’Assistant une seule fois. Les définitions de stratégie Globale (à l’échelle de l’organisation par défaut) sont automatiquement appliquées par l’Assistant et les nouveaux membres du personnel que vous ajoutez au groupe que vous avez sélectionné se voit automatiquement attribuer les stratégies personnalisées.

> [!NOTE]
> Pour [obtenir la liste](#policies-applied-by-the-wizard) détaillée des définitions de stratégie appliquées par l’Assistant, voir Stratégies appliquées par l’Assistant.

Commençons dès à présent !

## <a name="run-the-wizard"></a>Exécuter l’Assistant

<a name="polwiz_run"> </a>

Suivez ces étapes pour exécuter l’Assistant.

1. Si vous débutez sur Teams, l’Assistant démarre automatiquement. Sinon, vous pouvez démarrer l’Assistant à tout moment à partir du tableau de bord. Dans le panneau de navigation gauche du Centre d’administration  Microsoft Teams, sélectionnez Tableau de **bord,** puis dans la vignette Stratégie facile pour un environnement d’apprentissage sécurisé, sélectionnez **Configuration rapide.**

    :::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="Capture d’écran de l’Assistant dans le tableau de bord":::

2. Sélectionnez le type de votre établissement d’enseignement **(secondaire** ou **supérieur),** puis **Suivant.**

    :::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Capture d’écran de la page dans l’Assistant pour sélectionner le type d’établissement":::

3. Recherchez et sélectionnez un groupe contenant vos enseignants et membres du personnel, puis sélectionnez **Suivant.** Si aucun groupe n’est encore créé pour vos enseignants et membres du [personnel,](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)créez un groupe, puis ré-exécutez l’Assistant. <br/><br/>Pour l’instant, vous ne pouvez sélectionner qu’un seul groupe. Les enseignants et les membres du groupe que vous sélectionnez se voit attribuer un [ensemble de](#policies-applied-by-the-wizard) stratégies personnalisées adaptées à leurs besoins. N’oubliez pas que cet ensemble de stratégies est distinct des stratégies appliquées aux étudiants.

    :::image type="content" source="media/easy-policy-setup-group.png" alt-text="Capture d’écran de la page dans l’Assistant de sélection d’un enseignant et d’un groupe de membres du personnel":::

4. Examinez vos sélections.

    :::image type="content" source="media/easy-policy-setup-review-selections.png" alt-text="Capture d’écran de la page dans l’Assistant pour passer en revue les sélections":::

5. Sélectionnez **Appliquer** pour appliquer vos modifications. Cela peut prendre quelques minutes.<br/><br/>Les définitions de stratégie globale (à l’échelle de l’organisation par défaut) sont appliquées immédiatement aux étudiants. Pour vos enseignants et membres du personnel, l’attribuée aux stratégies personnalisées à chaque membre du groupe que vous avez sélectionné peut prendre quelques heures, selon la taille du groupe. Cela se produit en arrière-plan, une fois que vous avez réussi cette étape.
6. Vous êtes en route, mais ce n’est pas encore fait ! D’autres éléments sont à prendre en considération. Consultez ensuite la procédure de la section Procédure [à suivre](#what-to-do-after-running-the-wizard) après avoir exécute la section Assistant de cet article.

    :::image type="content" source="media/easy-policy-setup-on-way.png" alt-text="Capture d’écran de la page de l’Assistant pour les étapes suivantes":::

## <a name="what-to-do-after-running-the-wizard"></a>Que faire après avoir exécutez l’Assistant

<a name="polwiz_remove"> </a>

### <a name="step-1-remove-existing-policy-assignments-that-conflict-with-policies-applied-by-the-wizard"></a>Étape 1 : supprimer les affectations de stratégie existantes qui entrent en conflit avec les stratégies appliquées par l’Assistant

> [!IMPORTANT]
> **N’effectuer cette étape que si des stratégies  existantes** sont affectées aux étudiants ou aux enseignants et au personnel avant d’avoir dirigé l’Assistant. Si vous débutez dans Teams et que vous n’avez aucune stratégie autre que celles créées par l’Assistant, ignorez cette étape et passez à l’étape 2.

Dans Teams, pour un domaine de stratégie donné, une stratégie peut être appliquée à un utilisateur des façons suivantes :

- Affectation directe à l’utilisateur
- Affectation à un groupe dont l’utilisateur est membre
- Si l’utilisateur n’est pas directement affecté à une stratégie ou n’est pas membre d’un groupe à qui une stratégie a été attribuée, l’utilisateur reçoit automatiquement la stratégie globale (à l’échelle de l’organisation par défaut)

Si plusieurs de ces affectations de stratégie existent pour un utilisateur, Teams utilise l’ordre suivant pour déterminer l’affectation de stratégie qui prend effet. Pour plus d’informations, voir [quelle stratégie est prioritaire ?](assign-policies.md#which-policy-takes-precedence) et règles de [priorité.](assign-policies.md#precedence-rules)

|Affectations de stratégies d’un utilisateur|Stratégie qui prend effet |
|---------|---------|
|Stratégie attribuée au groupe : Non<br/>Stratégie attribuée directement à l’utilisateur : Non    |Stratégie par défaut globale (à l’échelle de l’organisation)      |
|Stratégie attribuée au groupe : Non<br/>Stratégie attribuée directement à l’utilisateur : Oui    |Stratégie attribuée directement à l’utilisateur         |
|Stratégie attribuée au groupe : Oui<br/>Stratégie attribuée directement à l’utilisateur : Oui     |Stratégie attribuée directement à l’utilisateur         |
|Stratégie attribuée au groupe : Oui<br/>Stratégie attribuée directement à l’utilisateur : Non     |Stratégie attribuée au groupe<br/><br/>Si l’utilisateur est membre de plusieurs groupes et qu’une stratégie de la même zone de stratégie est affectée à chaque groupe, la stratégie qui présente le classement d’affectation de groupe le plus élevé [prend](assign-policies.md#group-assignment-ranking) effet.       |

Étant donné cet ordre, les stratégies créées par l’Assistant ne prennent pas effet si un utilisateur possède déjà des affectations directes ou des affectations de groupe. Cela signifie que vous devez supprimer les affectations de stratégie existantes de l’utilisateur pour que la stratégie appliquée par l’Assistant prenne effet.

Pour chaque [zone de stratégie appliquée par l’Assistant,](#policies-applied-by-the-wizard)vous pouvez :

- Supprimez tous les devoirs directs et les affectations de groupe existants de vos étudiants afin que la définition de stratégie globale (à l’échelle de l’organisation par défaut) appliquée par l’Assistant prenne effet.
- Supprimez les affectations directes conflictuelles pour vos enseignants et membres du personnel afin que la définition de stratégie personnalisée créée par l’Assistant prenne effet. Utilisez le tableau ci-dessus pour déterminer les scénarios qui s’appliquent à vous. <br/><br/>Gardez à l’esprit que l’Assistant attribue des [](assign-policies.md#group-assignment-ranking) stratégies à vos enseignants et à votre groupe de membres du personnel à l’aide d’un classement d’affectations de groupe de 1, qui est le plus élevé. Si une stratégie du même domaine de stratégie est attribuée à vos enseignants et groupe de membres du personnel, cette stratégie existante est déplacée vers un classement inférieur et la stratégie attribuée par l’Assistant prend effet.

[Découvrez comment](batch-group-policy-assignment-edu.md#remove-a-policy-that-was-directly-assigned-to-users) supprimer des stratégies qui sont directement affectées aux utilisateurs.

Par exemple, vous avez attribué une stratégie de réunion directement aux enseignants et vos étudiants ont la stratégie de réunion globale (à l’échelle de l’organisation par défaut). Dans ce scénario, supprimez la stratégie de réunion que vous avez directement attribuée aux enseignants afin que la définition de stratégie personnalisée pour la stratégie de réunion créée par l’Assistant prenne effet. Vous n’avez rien à faire avec la stratégie de réunion globale existante (à l’échelle de l’organisation) pour les étudiants, car aucune autre stratégie de réunion n’entre en conflit avec elle.

<a name="polwiz_addmeasures"> </a>

### <a name="step-2-check-for-additional-measures-that-you-can-take-for-student-safety"></a>Étape 2 : vérifier les mesures supplémentaires que vous pouvez prendre pour la sécurité des étudiants

L’Assistant ajuste et applique automatiquement [ces stratégies.](#policies-applied-by-the-wizard) Il existe quelques mesures supplémentaires que vous voudrez peut-être prendre en fonction des besoins de votre établissement en sécurité.

Voir [Maintenir la sécurité des étudiants lors de l’utilisation de Teams pour l’apprentissage à distance](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8#ID0EBBAAA) pour obtenir des recommandations supplémentaires en matière de sécurité.

<a name="polwiz_mc"> </a>

### <a name="step-3-check-message-center-for-policy-updates"></a>Étape 3 : vérifier les mises à jour de stratégie dans le Centre de messages

Pour l’instant, l’Assistant applique les stratégies recommandées lorsque vous l’exécutez. Il est important de savoir qu’à mesure que de nouvelles stratégies deviennent disponibles dans Teams, les paramètres globaux (à l’échelle de l’organisation par défaut) pour la sécurité des étudiants ne sont pas automatiquement ajoutés par l’Assistant. Cette fonctionnalité sera disponible dans une prochaine version.

Jusqu’à ce que cette fonctionnalité soit disponible, consultez régulièrement le Centre de messages [(dans](https://admin.microsoft.com/AdminPortal/Home?#/MessageCenter) le Centre d’administration Microsoft 365) pour rester à jour sur les nouvelles stratégies et paramètres de stratégie dans Teams. À mesure que de nouvelles fonctionnalités deviennent disponibles, il se peut que vous de eussiez à mettre à jour manuellement vos stratégies pour préserver la sécurité de votre environnement d’apprentissage.

## <a name="make-changes-in-the-wizard"></a>Apporter des modifications dans l’Assistant

<a name="polwiz_change"> </a>

Si vous devez apporter des modifications après avoir exécuté l’Assistant, vous pouvez le ré-exécuter et modifier vos sélections.

1. Dans le panneau de navigation gauche du Centre d’administration  Microsoft Teams, sélectionnez Tableau de **bord,** puis dans la vignette Stratégie facile pour un environnement d’apprentissage sécurisé, **sélectionnez Modifier.**
2. À partir de là, continuez à travers chaque page de l’Assistant pour apporter vos modifications. Vous pouvez modifier le type de votre établissement, le groupe d’enseignants et de membres du personnel auquel vous voulez attribuer des stratégies, ou les deux.

Le tableau suivant récapitule ce qui se produit lorsque vous a modifiez l’Assistant.

|Type de modification  |Comportement des stratégies  |
|---------|---------|
|Modifier à la fois le type d’établissement d’enseignement et le groupe d’enseignants et de membres du personnel    |<ul><li>**Étudiants**: les définitions de stratégie globales (à l’échelle de l’organisation par défaut) basées sur le nouveau type d’établissement d’enseignement sont appliquées aux étudiants.</li><li>**Enseignants et membres du personnel**: un ensemble de définitions de stratégies personnalisées basées sur le nouveau type d’établissement d’enseignement est créé et attribué au nouvel enseignant et au groupe de membres du personnel. Les définitions de stratégie personnalisée précédentes sont supprimées des enseignants et des groupes de membres du personnel précédents.</li></ul>    |
|Modifier uniquement le type d’établissement d’enseignement    |<ul><li>**Étudiants**: les définitions de stratégie globales (à l’échelle de l’organisation par défaut) basées sur le nouveau type d’établissement d’enseignement sont appliquées aux étudiants.</li><li>**Enseignants et membres du personnel**: un ensemble de définitions de stratégies personnalisées basées sur le nouveau type d’établissement d’enseignement est créé et attribué aux enseignants et au groupe de membres du personnel. Les définitions de stratégie personnalisées créées pour le type d’établissement d’enseignement précédent sont supprimées des enseignants et du groupe de membres du personnel.</li></ul>         |
|Modifier uniquement les enseignants et le groupe de membres du personnel   |<ul><li>**Étudiants**: Aucune modification des définitions de stratégie globale (à l’échelle de l’organisation par défaut) appliquées aux étudiants.</li><li>**Enseignants et membres du personnel**: les définitions de stratégie personnalisée sont affectées aux nouveaux enseignants et au groupe de membres du personnel, et supprimées des précédents enseignants et des groupes de membres du personnel.</li></ul>         |

## <a name="policies-applied-by-the-wizard"></a>Stratégies appliquées par l’Assistant

<a name="polwiz_policies"> </a>

### <a name="policy-areas"></a>Zones de stratégie

Voici les zones de stratégie et les noms de stratégie correspondants couverts par l’Assistant. Pour rechercher ces stratégies, allez au Centre d’administration Microsoft Teams, puis dans le panneau de navigation de gauche, sur chaque page de la zone de stratégie.

#### <a name="students"></a>[**Étudiants**](#tab/students/)

|Zone De stratégie  |Nom de la stratégie principale ou secondaire |Nom de la stratégie de l’enseignement supérieur  |
|---------|---------|---------|
|Stratégie Teams    |Global (par défaut à l’échelle de l’organisation)         |Global (par défaut à l’échelle de l’organisation)           |
|Stratégie de réunion    |Global (par défaut à l’échelle de l’organisation)           |Global (par défaut à l’échelle de l’organisation)           |
|Stratégie d’événements en direct     |Global (par défaut à l’échelle de l’organisation)          |  Global (par défaut à l’échelle de l’organisation)          |
|Stratégie de configuration de l’application     |Global (par défaut à l’échelle de l’organisation)           |Global (par défaut à l’échelle de l’organisation)           |
|Stratégie d’autorisation d’application    |Global (par défaut à l’échelle de l’organisation)           |Global (par défaut à l’échelle de l’organisation)           |
|Stratégie de messagerie     |Global (par défaut à l’échelle de l’organisation)           |Global (par défaut à l’échelle de l’organisation)           |
|Stratégie d’Appel    |Global (par défaut à l’échelle de l’organisation)           |Global (par défaut à l’échelle de l’organisation)           |

#### <a name="educators-and-staff"></a>[**Enseignants et personnel**](#tab/educators/)

|Zone De stratégie  |Nom de la stratégie principale ou secondaire |Nom de la stratégie de l’enseignement supérieur |
|---------|---------|---------|
|Stratégie Teams   |Enseignants primaires ou secondaires et membres du personnel enseignant - Teams         |Enseignants et membres du personnel de l’enseignement supérieur - Teams         |
|Stratégie de réunion    |Enseignants et membres du personnel primaires ou secondaires - Réunion         |Enseignants et membres du personnel de l’enseignement supérieur - Réunion         |
|Stratégie d’événements en direct   | Enseignants principaux ou secondaires et membres du personnel - Événements en direct         |Enseignants et membres du personnel de l’enseignement supérieur - Événements en direct         |
|Stratégie de messagerie    |Enseignants et membres du personnel principaux ou secondaires - Messagerie         | Enseignants et membres du personnel de l’enseignement supérieur - Messagerie         |
|Stratégie d’Appel    |Enseignants principaux ou secondaires et membres du personnel enseignant - Appel         |Enseignants et membres du personnel de l’enseignement supérieur - Appels         |

* * *

### <a name="policy-settings"></a>Paramètres de stratégie

Voici un résumé des paramètres appliqués par l’Assistant pour chaque zone de stratégie.

#### <a name="students"></a>[**Étudiants**](#tab/student-settings/)

Voici une liste des définitions de stratégie globales (à l’échelle de l’organisation par défaut) ajustées par l’Assistant et appliquées aux étudiants.

|Zone De stratégie |Sous-zone  |Paramètre de stratégie  |Principale ou secondaire |Enseignement supérieur |
|---------|---------|---------|---------|---------|
|Stratégie Teams   |         |Créer des canaux privés         |Désactivé       |Activé|
|Stratégie de réunions    |Général         |Autoriser la conférence maintenant dans les canaux         |Désactivé      |Activé|
|  |        |Autoriser le complément Outlook         |Désactivé       |Activé|
|  |        |Autoriser la planification des réunions pour les canaux        |Désactivé      |Activé|
|  |        |Autoriser la planification des réunions privées       |Désactivé      |Activé|
|  |Audio & vidéo        |Autoriser la transcription        |Activé       |Activé|
|  |        |Autoriser l’enregistrement dans le Cloud         |Désactivé      |Activé|
|  |        |Mode pour l’audio sur IP       |Audio sortant et entrant activé        |Audio sortant et entrant activé|
|  |        |Mode pour la vidéo sur IP         |Vidéo sortante et entrante activée     |Vidéo sortante et entrante activée|
|  |       |Autoriser la vidéo sur IP         |Activé         |Activé|
|  |       |Autoriser la diffusion de NDI         |Désactivé         |Désactivé|
|  |       |Vitesse de transmission du média (Ko)         |50 000         |50 000|
|  |Partage de contenu       |Mode de partage d’écran         |Écran entier         |Écran entier|
|  |       |Autoriser un participant à donner ou demander le contrôle         |Activé         |Activé|
|  |       |Autoriser un participant externe à donner ou demander le contrôle         |Activé         |Activé|
|  |       |Autoriser le partage de PowerPoint        |Activé         |Activé|
|  |       |Autoriser le tableau blanc         |Activé         |Activé|
|  |       |Autoriser les notes partagées         |Activé        |Activé|
|  |Participants et & invités       |Autoriser les personnes anonymes à démarrer une réunion       |Désactivé         |Activé|
|  |       |Rôles qui ont des droits de présentateur dans les réunions        |EveryoneUserOverride         |EveryoneUserOverride|
|  |       |Admettre les personnes automatiquement        |EveryoneInCompany|EveryoneInCompany|
|  |       |Autoriser les utilisateurs entrants à éviter la salle d’attente        |Désactivé         |Désactivé|
|  |       |Autoriser la Conférence maintenant dans les réunions privées        |Désactivé         |Activé|
|  |       |Activer les légendes dynamiques       |Désactivé mais l’utilisateur peut remplacer         |Désactivé mais l’utilisateur peut remplacer|
|  |       |Autoriser la conversation en réunion         |Activé         |Activé|
|Stratégie d’événements en direct  |       |Autoriser la planification         |Désactivé         |Désactivé|
|  |       |Autoriser la transcription pour les participants          |Activé       |Activé|
|  |       |Qui peut participer aux événements en direct planifiés        |Tous les membres de l’organisation        |Tous les membres de l’organisation|
|  |       |Qui peut enregistrer un événement         |Toujours         |Toujours|
|Stratégie de messagerie  |       |Les propriétaires peuvent supprimer les messages envoyés         |Désactivé|Activé|
|  |       |Supprimer des messages envoyés         |Désactivé         |Activé|
|  |       |Modifier des messages envoyés         |Désactivé         |Activé|
|  |       |Read receipts         |Utilisateur contrôlé         |Utilisateur contrôlé|
|  |       |Conversation         |Désactivé         |Activé|
|  |       |Utiliser des Giphys dans les conversations         |Désactivé         |Activé|
|  |       |Évaluation du contenu Giphy         |Strict        |Strict|
|  |       |Utiliser des mèmes dans les conversations         |Activé         |Activé|
|  |       |Utiliser des autocollants dans les conversations         |Activé         |Activé|
|  |       |Autoriser les aperçus d’URL        |Activé         |Activé|
|  |       |Traduire des messages         |Activé         |Activé|
|  |       |Autoriser le lecteur immersif à afficher les messages        |Activé      |Activé|
|  |       |Envoyer des messages urgents à l’aide de notifications de priorité  |Désactivé         |Activé|
|  |       |Créer des messages vocaux         |Autorisé dans les conversations et les canaux         |Autorisé dans les conversations et les canaux|
|  |       |Sur les appareils mobiles, afficher les canaux favoris au-dessus des conversations récentes     |Activé         |Activé|
|  |       |Supprimer des utilisateurs des conversations de groupe         |Désactivé         |Activé|
|Stratégie d’autorisation d’application  |       |Applications Microsoft         |Bloquer des applications spécifiques et autoriser tous les autres utilisateurs à > Le Talkie-walkie est bloqué         |Autoriser toutes les applications|
|  |       |Applications tierces         |Autoriser toutes les applications         |Autoriser toutes les applications|
|  |       |Applications personnalisées         |Autoriser toutes les applications         |Autoriser toutes les applications|
|Stratégie de configuration de l’application  |           |Télécharger des applications personnalisées           |Désactivé         |Désactivé|
|  |       |Autoriser l’épinglage utilisateur |Activé         |Activé|
|  |       |Applications installées         |Aucun         |Aucun|
|  |       |Applications épinglées         |Activité, Calendrier, Teams         |Activité, Conversations, Équipes, Calendrier, Appels, Fichier
|Stratégie d’Appel  |       |Passer des appels privés         |Désactivé        |Activé|
|  |       |Call forwarding and simultaneous ringing to people in your organization         |Désactivé         |Activé|
|  |       |Call forwarding and simultaneous ringing to external phone numbers         |Désactivé         |Activé|
|  |       |La messagerie vocale est disponible pour les appels entrants de routage         |Utilisateur contrôlé         |Utilisateur contrôlé|
|  |       |Les appels entrants peuvent être acheminés vers des groupes d’appels         |Désactivé        |Activé|
|  |       |Autoriser la délégation pour les appels entrants et sortants         |Désactivé         |Activé|
|  |       |Empêcher la dérivation et l’envoi d’appels via le PSTN        |Désactivé         |Désactivé|
|  |       |Occupé(elle) est disponible lors d’un appel         |Désactivé         |Désactivé|
|  |       |Autoriser les appels PSTN Web         |Désactivé         |Activé|

#### <a name="educators-and-staff"></a>[**Enseignants et personnel**](#tab/educator-settings/)

Voici une liste des définitions de stratégie personnalisées assignées aux enseignants et au groupe de membres du personnel que vous choisissez dans l’Assistant.  

|Zone de stratégie |Sous-zone  |Paramètre de stratégie  |Principale ou secondaire |Enseignement supérieur |
|---------|---------|---------|---------|---------|
|Stratégie Teams   |         |Créer des canaux privés         |Activé       |Activé|
|Stratégie de réunions    |Général         |Autoriser la conférence maintenant dans les canaux         |Activé      |Activé|
|  |        |Autoriser le complément Outlook         |Activé       |Activé|
|  |        |Autoriser la planification des réunions pour les canaux        |Activé      |Activé|
|  |        |Autoriser la planification des réunions privées       |Activé      |Activé|
|  |Audio & vidéo        |Autoriser la transcription        |Activé       |Activé|
|  |        |Autoriser l’enregistrement dans le Cloud         |Activé      |Activé|
|  |        |Mode pour l’audio sur IP       |Audio sortant et entrant activé        |Audio sortant et entrant activé|
|  |        |Mode pour la vidéo sur IP         |Vidéo sortante et entrante activée     |Vidéo sortante et entrante activée|
|  |       |Autoriser la vidéo sur IP         |Activé         |Activé|
|  |       |Autoriser la diffusion de NDI         |Désactivé         |Désactivé|
|  |       |Vitesse de transmission du média (Ko)         |50 000         |50 000|
|  |Partage de contenu       |Mode de partage d’écran         |Écran entier         |Écran entier|
|  |       |Autoriser un participant à donner ou demander le contrôle         |Activé         |Activé|
|  |       |Autoriser un participant externe à donner ou demander le contrôle         |Activé         |Activé|
|  |       |Autoriser le partage de PowerPoint        |Activé         |Activé|
|  |       |Autoriser le tableau blanc         |Activé         |Activé|
|  |       |Autoriser les notes partagées         |Activé        |Activé|
|  |Participants et & invités       |Autoriser les personnes anonymes à démarrer une réunion       |Activé        |Activé|
|  |       |Rôles qui ont des droits de présentateur dans les réunions        |OrganizerOnlyUserOverride         |OrganizerOnlyUserOverride|
|  |       |Admettre les personnes automatiquement        |OrganisateurOnly|OrganisateurOnly|
|  |       |Autoriser les utilisateurs entrants à éviter la salle d’attente        |Désactivé         |Désactivé|
|  |       |Autoriser la Conférence maintenant dans les réunions privées        |Activé         |Activé|
|  |       |Activer les légendes dynamiques       |Désactivé mais l’utilisateur peut remplacer         |Désactivé mais l’utilisateur peut remplacer|
|  |       |Autoriser la conversation en réunion         |Activé         |Activé|
|Stratégie d’événements en direct  |       |Autoriser la planification         |Activé         |Activé|
|  |       |Autoriser la transcription pour les participants          |Activé       |Activé|
|  |       |Qui peut participer aux événements en direct planifiés        |Tous les membres de l’organisation        |Tous les membres de l’organisation|
|  |       |Qui peut enregistrer un événement         |Toujours enregistrer         |Toujours enregistrer|
|Stratégie de messagerie  |       |Les propriétaires peuvent supprimer les messages envoyés         |Activé|Activé|
|  |       |Supprimer des messages envoyés         |Activé         |Activé|
|  |       |Modifier des messages envoyés         |Activé         |Activé|
|  |       |Read receipts         |Utilisateur contrôlé         |Utilisateur contrôlé|
|  |       |Conversation         |Activé         |Activé
|  |       |Utiliser des Giphys dans les conversations         |Activé        |Activé|
|  |       |Évaluation du contenu Giphy         |Strict        |Strict|
|  |       |Utiliser des mèmes dans les conversations         |Activé         |Activé|
|  |       |Utiliser des autocollants dans les conversations         |Activé         |Activé|
|  |       |Autoriser les aperçus d’URL        |Activé         |Activé|
|  |       |Traduire des messages         |Activé         |Activé|
|  |       |Autoriser le lecteur immersif à afficher les messages        |Activé      |Activé|
|  |       |Envoyer des messages urgents à l’aide de notifications de priorité  |Activé         |Activé|
|  |       |Créer des messages vocaux         |Autorisé dans les conversations et les canaux         |Autorisé dans les conversations et les canaux|
|  |       |Sur les appareils mobiles, afficher les canaux favoris au-dessus des conversations récentes     |Activé         |Activé|
|  |       |Supprimer des utilisateurs des conversations de groupe         |Activé        |Activé|
|Stratégie d’Appel  |       |Passer des appels privés         |Activé       |Activé|
|  |       |Call forwarding and simultaneous ringing to people in your organization         |Activé        |Activé|
|  |       |Call forwarding and simultaneous ringing to external phone numbers         |Activé        |Activé|
|  |       |La messagerie vocale est disponible pour les appels entrants de routage         |Utilisateur contrôlé         |Utilisateur contrôlé|
|  |       |Les appels entrants peuvent être acheminés vers des groupes d’appels         |Activé        |Activé|
|  |       |Autoriser la délégation pour les appels entrants et sortants         |Activé         |Activé|
|  |       |Empêcher la dérivation et l’envoi d’appels via le PSTN        |Désactivé         |Désactivé|
|  |       |Occupé(elle) est disponible lors d’un appel         |Désactivé         |Désactivé|
|  |       |Autoriser les appels PSTN Web         |Activé      |Activé|

* * *

## <a name="related-topics"></a>Sujets associés

- [Stratégies et packages de stratégie Teams pour l’éducation](policy-packages-edu.md)
- [Attribuer des stratégies à un grand nombre d’utilisateurs dans votre établissement scolaire](batch-group-policy-assignment-edu.md)
- [Assurer la sécurité des étudiants lors de l’utilisation de Teams pour l’apprentissage à distance](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)

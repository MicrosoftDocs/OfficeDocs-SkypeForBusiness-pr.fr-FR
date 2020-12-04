---
title: Assistant politique de Microsoft teams pour l’éducation permettant d’appliquer facilement des politiques pour une formation sécurisée
author: lanachin
ms.author: v-lanac
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
description: Découvrez comment utiliser l’Assistant politique de Microsoft teams pour l’éducation pour appliquer facilement des stratégies aux étudiants et aux enseignants afin de préserver la sécurité de votre environnement d’apprentissage.
f1keywords: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: d72ef20a8ae56fba67534944d229d01468531207
ms.sourcegitcommit: 80c1ec1d5a43b9259a4da6db3e462f6d4257bfa7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/03/2020
ms.locfileid: "49564253"
---
# <a name="use-the-teams-for-education-policy-wizard-to-easily-apply-policies-for-a-safe-learning-environment"></a>Utiliser l’Assistant politique de Microsoft teams pour l’éducation pour appliquer facilement des stratégies pour un environnement d’apprentissage sûr

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>Vue d’ensemble

L’Assistant politique de Microsoft teams pour l’éducation simplifie la gestion des stratégies destinées aux étudiants et aux enseignants. Ce service vous permet d’appliquer facilement et rapidement le jeu de stratégies le plus important en matière de création d’une interface de formation sécurisée et productive.

Les stratégies dans teams vous permettent de contrôler la manière dont teams se comporte dans votre environnement et quelles sont les fonctionnalités disponibles pour les utilisateurs. Par exemple, il existe des stratégies d’appel, des stratégies de réunion et des stratégies de messagerie, pour n’en nommer qu’une pour les besoins de votre organisation.

Pour conserver un environnement d’apprentissage sécurisé et ciblé, il est important de définir des stratégies pour contrôler ce que les étudiants peuvent faire dans Teams. Par exemple, vous pouvez utiliser des stratégies pour contrôler qui peut utiliser des discussions privées et des appels privés, qui peut planifier des réunions et quels types de contenus peuvent être partagés. Vous pouvez également utiliser des stratégies pour activer les fonctionnalités d’équipe qui enrichissent l’apprentissage.

Les politiques doivent être ajustées pour permettre aux étudiants et aux enseignants de garantir la sécurité des connaissances. Les politiques destinées aux étudiants doivent être plus restrictives pour réduire le risque de recevoir des niveaux d’accès inappropriés. Les enseignants et les membres du personnel ont besoin d’un ensemble de stratégies distinctes qui peuvent être plus permissif pour réussir. Par exemple, permettez aux enseignants de planifier des réunions et de restreindre leurs élèves.

:::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Capture d’écran de l’Assistant":::

Cet article vous guide dans l’exécution de l’Assistant.

> [!IMPORTANT]
> Les stratégies appliquées par l’Assistant répondront aux besoins de la majorité des équipes destinées aux clients universitaires. L’Assistant ajuste la définition globale (par défaut de l’organisation) d’un ensemble de stratégies de base à l’aide de paramètres que nous recommandons pour la sécurité des étudiants et l’applique aux étudiants. L’Assistant crée et attribue également un ensemble de stratégies personnalisées aux enseignants et aux membres du personnel. La plupart des équipes destinées aux clients éducation n’ont pas besoin d’utiliser d’autres méthodes d’attribution de stratégie après l’exécution de cet Assistant. Utiliser d’autres méthodes d’attribution de stratégie *uniquement* si vous souhaitez créer et gérer des stratégies manuellement pour vos étudiants, enseignants et membres du personnel.

## <a name="teams-for-education-policy-wizard"></a>Assistant politique de Microsoft teams éducation

<a name="polwiz_intro"> </a>

L’Assistant applique un ensemble de définitions de stratégies principales aux étudiants, ainsi qu’un ensemble de définitions de stratégies principales aux enseignants et au personnel, avec des paramètres appropriés pour chacun d’eux. Voici ce qui se produit lorsque vous exécutez l’Assistant.

L’Assistant définit les stratégies en fonction du type d’établissement scolaire (**principal ou secondaire** ou **supérieur**). Vous sélectionnez votre type d’établissement et l’Assistant effectue les actions suivantes :

- **Étudiants**: l’Assistant ajuste la définition de stratégie globale (par défaut de l’organisation) de chaque zone de stratégie couverte par l’Assistant grâce aux nouveaux paramètres par défaut qui sont appropriés pour garantir la sécurité de vos étudiants. Cela permet à vos étudiants actuels et à tous les nouveaux étudiants de bénéficier du jeu de stratégies le plus restrictif.
- **Enseignants et membres du personnel enseignant**: l’Assistant crée un ensemble de définitions de stratégie personnalisées pour chaque zone de stratégie couverte par l’Assistant, avec des paramètres adaptés aux besoins des enseignants et du personnel. Ensuite, il attribue les définitions de la stratégie au groupe d’enseignants et de membres du personnel de votre choix. De cette manière, vos enseignants et le personnel disposent d’un ensemble de stratégies plus permissif pour garantir leur réussite.

Il vous suffit d’exécuter l’Assistant une seule fois. Les nouveaux étudiants obtiennent automatiquement les définitions de stratégies globales par défaut (organisation par défaut) appliquées par l’Assistant, et les nouveaux membres du personnel que vous ajoutez au groupe que vous avez sélectionné reçoivent automatiquement les stratégies personnalisées.

> [!NOTE]
> Pour obtenir la liste détaillée des définitions de stratégie appliquées par l’Assistant, voir [stratégies appliquées par l’Assistant](#policies-applied-by-the-wizard) .

Commençons.

## <a name="run-the-wizard"></a>Exécution de l’Assistant

<a name="polwiz_run"> </a>

Pour exécuter l’Assistant, procédez comme suit. 

1. S’il s’agit de nouvelles équipes, l’Assistant démarre automatiquement. Dans le cas contraire, vous pouvez démarrer l’Assistant à tout moment à partir du tableau de bord. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez au **tableau de bord**, puis dans la fenêtre **configuration de la stratégie simplifiée d’un environnement d’apprentissage sûr** , sélectionnez **Configuration rapide**.

    :::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="Capture d’écran de l’Assistant dans le tableau de bord":::

2. Sélectionnez votre type d’établissement scolaire (**principal ou secondaire** ou **supérieur**), puis cliquez sur **suivant**.

    :::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Capture d’écran de la page de l’Assistant pour sélectionner un type d’établissement":::

3. Recherchez et sélectionnez un groupe qui contient vos enseignants et membres du personnel, puis cliquez sur **suivant**. Si vous n’avez pas encore configuré de groupes pour les enseignants et le personnel, [créez un groupe](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups), puis réexécutez l’Assistant. <br/><br/>Pour l’instant, vous ne pouvez sélectionner qu’un seul groupe. Les enseignants et le personnel dans le groupe que vous sélectionnez disposeront [d’un ensemble de stratégies personnalisées](#policies-applied-by-the-wizard) adaptées à leurs besoins. N’oubliez pas que ce jeu de stratégies est différent des politiques appliquées aux étudiants.

    :::image type="content" source="media/easy-policy-setup-group.png" alt-text="Capture d’écran de la page de l’Assistant pour sélectionner les enseignants et les membres du personnel enseignant":::

4. Passez en revue vos sélections.

    :::image type="content" source="media/easy-policy-setup-review-selections.png" alt-text="Capture d’écran de la page de l’Assistant pour vérifier les sélections":::

5. Sélectionnez **appliquer** pour appliquer vos modifications. Cette opération risque de nécessiter quelques minutes.<br/><br/>Les définitions de stratégies globales par défaut de l’organisation sont immédiatement appliquées aux étudiants. Pour les enseignants et les membres du personnel, il peut s’écouler jusqu’à 48 heures pour que les stratégies personnalisées soient affectées à chaque membre du groupe sélectionné, en fonction de la taille du groupe. Cela se produit en arrière-plan, une fois que vous avez terminé cette étape.
6. Vous n’avez pas encore terminé votre travail. Plusieurs éléments sont à prendre en compte. Suivez ensuite les étapes décrites dans la section [que faire après avoir exécuté l’Assistant](#what-to-do-after-running-the-wizard) de cet article.

    :::image type="content" source="media/easy-policy-setup-on-way.png" alt-text="Capture d’écran de la page de l’Assistant pour les étapes suivantes":::

## <a name="what-to-do-after-running-the-wizard"></a>Procédure à suivre après l’exécution de l’Assistant

<a name="polwiz_remove"> </a>

### <a name="step-1-remove-existing-policy-assignments-that-conflict-with-policies-applied-by-the-wizard"></a>Étape 1 : supprimer les affectations de stratégie existantes qui entrent en conflit avec celles appliquées par l’Assistant

> [!IMPORTANT]
> **Ne complétez cette étape que si vous disposez de stratégies existantes attribuées aux étudiants, aux enseignants et au personnel *avant* d’exécuter l’Assistant**. Si vous débutez dans teams et que vous ne disposez pas de stratégies qui ne sont pas les mêmes que celles créées par l’Assistant, passez à l’étape 2.

Dans Microsoft Teams, pour une zone de stratégie donnée, une stratégie peut être appliquée à un utilisateur de l’une des façons suivantes :

- Attribution directe à l’utilisateur
- Attribution à un groupe dont l’utilisateur est membre
- Si l’utilisateur n’est pas directement affecté à une stratégie ou n’est pas membre de tout groupe auquel une stratégie est affectée, l’utilisateur obtient automatiquement la stratégie globale de l’organisation.

S’il existe plusieurs de ces affectations de stratégie pour un utilisateur, teams utilise l’ordre suivant pour déterminer la façon dont l’affectation de stratégie est appliquée. Pour plus d’informations, voir [quelle est la stratégie prioritaire ?](assign-policies.md#which-policy-takes-precedence) et [règles de précédence](assign-policies.md#precedence-rules).

|Attributions de stratégie à un utilisateur|Politique qui est appliquée |
|---------|---------|
|Stratégie attribuée au groupe : non<br/>Stratégie attribuée directement à l’utilisateur : non    |Stratégie par défaut globale (au sein de l’organisation)      |
|Stratégie attribuée au groupe : non<br/>Stratégie attribuée directement à l’utilisateur : Oui    |Stratégie attribuée directement à l’utilisateur         |
|Stratégie attribuée au groupe : Oui<br/>Stratégie attribuée directement à l’utilisateur : Oui     |Stratégie attribuée directement à l’utilisateur         |
|Stratégie attribuée au groupe : Oui<br/>Stratégie attribuée directement à l’utilisateur : non     |Stratégie affectée à un groupe<br/><br/>Si l’utilisateur est membre de plusieurs groupes et chaque groupe est affecté d’une stratégie de la même zone de stratégie, la stratégie qui dispose du [classement d’attribution de groupe](assign-policies.md#group-assignment-ranking) le plus élevé est appliquée.       |

Pour cette raison, les stratégies créées par l’Assistant ne s’appliquent pas si un utilisateur a des affectations directes ou des affectations de groupe existantes. Cela signifie que vous devez supprimer les affectations de stratégie existantes de l’utilisateur afin que la stratégie appliquée par l’Assistant prenne effet.

Pour chaque [zone de stratégie appliquée par l’Assistant](#policies-applied-by-the-wizard), procédez comme suit :

- Supprimez l’ensemble des affectations directes et des affectations de groupe de vos étudiants de sorte que la définition de stratégie globale (par défaut de l’organisation) appliquée par l’Assistant prenne effet.
- Supprimez toute affectation directe en conflit pour les enseignants et le personnel de sorte que la définition de stratégie personnalisée créée par l’Assistant prenne effet. Utilisez le tableau ci-dessus pour déterminer les scénarios qui vous concernent. <br/><br/>Gardez à l’esprit que l’Assistant affecte des stratégies aux enseignants et aux groupes de personnel en utilisant un [classement d’affectation de groupe](assign-policies.md#group-assignment-ranking) de 1, qui est le classement le plus élevé. Si votre enseignant et votre groupe personnel dispose d’une stratégie de la même zone de stratégie qui lui est affectée, la stratégie existante est déplacée vers un classement inférieur et la stratégie attribuée par l’Assistant est appliquée.

[En savoir plus](batch-group-policy-assignment-edu.md#remove-a-policy-that-was-directly-assigned-to-users) sur la suppression de stratégies directement affectées aux utilisateurs.

Par exemple, vous avez affecté une stratégie de réunion directement aux enseignants et vos étudiants disposent de la stratégie de réunion globale (par défaut de l’organisation). Dans ce scénario, supprimez la stratégie de réunion que vous avez affectée directement aux enseignants pour que la définition de stratégie personnalisée de la stratégie de réunion créée par l’Assistant soit appliquée. Vous n’avez rien à faire de la stratégie de réunion globale existante (par défaut de l’organisation) pour les étudiants, car aucune autre stratégie de réunion n’est en conflit.

<a name="polwiz_addmeasures"> </a>

### <a name="step-2-check-for-additional-measures-that-you-can-take-for-student-safety"></a>Étape 2 : recherchez d’autres mesures que vous pouvez appliquer pour la sécurité des étudiants

L’Assistant ajuste et applique automatiquement [ces stratégies](#policies-applied-by-the-wizard). Il existe quelques mesures supplémentaires que vous voudrez peut-être prendre en fonction de vos besoins en matière de sécurité.

Apprenez à [maintenir la sécurité des étudiants lors de l’utilisation d’équipes pour une formation à distance](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8#ID0EBBAAA) pour des recommandations supplémentaires en matière de sécurité.

<a name="polwiz_mc"> </a>

### <a name="step-3-check-message-center-for-policy-updates"></a>Étape 3 : vérifier le centre de messages pour les mises à jour de la stratégie

Pour l’instant, l’Assistant applique les stratégies recommandées lors de son exécution. Il est important de savoir que de nouvelles stratégies deviennent disponibles dans Teams, les paramètres généraux (par défaut de l’organisation par défaut) pour la sécurité des étudiants ne sont pas automatiquement ajoutés par l’Assistant. Cette fonctionnalité sera disponible dans une version ultérieure.

Tant que cette fonctionnalité n’est pas disponible, vérifiez fréquemment le [Centre de messages](https://admin.microsoft.com/AdminPortal/Home?#/MessageCenter) (dans le centre d’administration 365 Microsoft) pour rester à jour sur les nouvelles stratégies et les nouveaux paramètres de stratégie dans Teams. À mesure que de nouvelles fonctionnalités sont disponibles, vous devrez peut-être mettre à jour manuellement vos stratégies pour garantir la sécurité de votre environnement d’apprentissage.

## <a name="make-changes-in-the-wizard"></a>Apporter des modifications à l’Assistant

<a name="polwiz_change"> </a>

Si vous avez besoin d’apporter des modifications après avoir exécuté l’Assistant, vous pouvez le réexécuter et modifier vos sélections.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **tableau de bord**, puis dans la fenêtre **configuration de la stratégie simplifiée d’un environnement d’apprentissage sûr** , sélectionnez **modifier**.
2. À partir de cet emplacement, passez en revue toutes les pages de l’Assistant pour apporter vos modifications. Vous pouvez modifier le type de votre établissement d’encadrement, le groupe d’enseignants et les deux.

Le tableau suivant résume ce qui se produit lorsque vous effectuez une modification dans l’Assistant.

|Type de modification  |Comportement de la stratégie  |
|---------|---------|
|Changer le type de l’établissement scolaire et les enseignants et les membres du personnel enseignant    |<ul><li>**Étudiants**: les définitions de stratégie globales (par défaut de l’organisation) basées sur le nouveau type d’établissement d’enseignement sont appliquées aux étudiants.</li><li>**Enseignants et membres du personnel enseignant**: un ensemble de définitions de stratégie personnalisées basées sur le nouveau type d’établissement d’enseignement est créé et attribué aux nouveaux enseignants et groupes du personnel enseignant. Les définitions de stratégie personnalisées précédentes sont supprimées des enseignants et du groupe de personnel.</li></ul>    |
|Changer uniquement le type de l’établissement scolaire    |<ul><li>**Étudiants**: les définitions de stratégie globales (par défaut de l’organisation) basées sur le nouveau type d’établissement d’enseignement sont appliquées aux étudiants.</li><li>**Enseignants et membres du personnel enseignant**: un ensemble de définitions de stratégie personnalisées basées sur le nouveau type d’établissement d’enseignement est créé et attribué aux enseignants et au groupe personnel. Les définitions de stratégie personnalisées créées pour le type d’établissement d’enseignement précédent sont supprimées des enseignants et du personnel enseignant.</li></ul>         |
|Changer uniquement les enseignants et les membres du personnel enseignant   |<ul><li>**Étudiants**: il n’est pas possible de modifier les définitions de stratégie globales par défaut appliquées aux étudiants.</li><li>**Enseignants et membres du personnel enseignant**: les définitions de politiques personnalisées sont attribuées aux nouveaux enseignants et au groupe de personnel enseignant et supprimées des enseignants et du groupe de personnel.</li></ul>         |

## <a name="policies-applied-by-the-wizard"></a>Stratégies appliquées par l’Assistant

<a name="polwiz_policies"> </a>

### <a name="policy-areas"></a>Zones de stratégie

Voici les zones de stratégie et les noms de stratégie correspondants couverts par l’Assistant. Pour rechercher ces stratégies, accédez au centre d’administration de Microsoft Teams, puis, dans le volet de navigation de gauche, accédez à chaque page de la zone de stratégie.

#### <a name="students"></a>[**Étudiants**](#tab/students/)

|Zone de stratégie  |Nom de la stratégie principale ou secondaire |Nom de la stratégie d’éducation supérieure  |
|---------|---------|---------|
|Stratégie Teams    |Global (par défaut de l’organisation)         |Global (par défaut de l’organisation)           |
|Stratégie de réunion    |Global (par défaut de l’organisation)           |Global (par défaut de l’organisation)           |
|Stratégie d’événements en direct     |Global (par défaut de l’organisation)          |  Global (par défaut de l’organisation)          |
|Politique de configuration des applications     |Global (par défaut de l’organisation)           |Global (par défaut de l’organisation)           |
|Stratégie d’autorisation d’application    |Global (par défaut de l’organisation)           |Global (par défaut de l’organisation)           |
|Stratégie de messagerie     |Global (par défaut de l’organisation)           |Global (par défaut de l’organisation)           |
|Stratégie d’Appel    |Global (par défaut de l’organisation)           |Global (par défaut de l’organisation)           |

#### <a name="educators-and-staff"></a>[**Enseignants et personnel**](#tab/educators/)

|Zone de stratégie  |Nom de la stratégie principale ou secondaire |Nom de la stratégie d’éducation supérieure |
|---------|---------|---------|
|Stratégie Teams   |Enseignants principaux ou secondaires et équipe         |Enseignants et équipes de grande éducation         |
|Stratégie de réunion    |Enseignants principaux ou secondaires et réunion du personnel enseignant         |Enseignants et membres du personnel enseignant         |
|Stratégie d’événements en direct   | Enseignants principaux ou secondaires et événements en direct du personnel enseignant         |Enseignants et événements en direct         |
|Stratégie de messagerie    |Enseignants principaux ou secondaires et messagerie du personnel enseignant         | Enseignants et service de messagerie de niveau supérieur         |
|Stratégie d’Appel    |Enseignants principaux ou secondaires et appels personnels         |Enseignants et appels d’équipe supérieurs         |

* * *

### <a name="policy-settings"></a>Paramètres de stratégie

Voici un résumé des paramètres appliqués par l’Assistant pour chaque zone de stratégie.

#### <a name="students"></a>[**Étudiants**](#tab/student-settings/)

Vous trouverez ci-dessous une liste des définitions de stratégies globales (par défaut de l’organisation) ajustées par l’Assistant et appliquées aux étudiants.

|Zone de stratégie |Sous-zone  |Paramètre de stratégie  |Principal ou secondaire |Enseignement supérieur |
|---------|---------|---------|---------|---------|
|Stratégie Teams   |         |Créer des canaux privés         |Désactivé       |Activé|
|Stratégie de réunion    |Général         |Autoriser la Conférence maintenant dans les canaux         |Désactivé      |Activé|
|  |        |Autoriser le complément Outlook         |Désactivé       |Activé|
|  |        |Autoriser la planification des réunions de canal        |Désactivé      |Activé|
|  |        |Autoriser la planification de réunions privées       |Désactivé      |Activé|
|  |Audio & vidéo        |Autoriser la transcription        |Activé       |Activé|
|  |        |Autoriser l’enregistrement Cloud         |Désactivé      |Activé|
|  |        |Mode pour le son IP       |Audio entrant et sortant activé        |Audio entrant et sortant activé|
|  |        |Mode pour la vidéo IP         |Vidéo sortante et entrante activée     |Vidéo sortante et entrante activée|
|  |       |Autoriser la vidéo sur IP         |Activé         |Activé|
|  |       |Autoriser NDI streaming         |Désactivé         |Désactivé|
|  |       |Taux d’échantillonnage du support (Ko)         |50 000         |50 000|
|  |Partage de contenu       |Mode de partage d’écran         |Tout l’écran         |Tout l’écran|
|  |       |Autoriser un participant à céder ou demander le contrôle         |Activé         |Activé|
|  |       |Autoriser un participant externe à céder ou demander le contrôle         |Activé         |Activé|
|  |       |Autoriser le partage PowerPoint        |Activé         |Activé|
|  |       |Autoriser le tableau blanc         |Activé         |Activé|
|  |       |Autoriser les notes partagées         |Activé        |Activé|
|  |Participants & invités       |Permettre aux utilisateurs anonymes de démarrer une réunion       |Désactivé         |Activé|
|  |       |Rôles possédant des droits de présentateur pour les réunions        |EveryoneUserOverride         |EveryoneUserOverride|
|  |       |Admettre automatiquement des personnes        |EveryoneInCompany|EveryoneInCompany|
|  |       |Autoriser les utilisateurs rendez-vous à ignorer la salle d’attente        |Désactivé         |Désactivé|
|  |       |Autoriser la Conférence maintenant dans les réunions privées        |Désactivé         |Activé|
|  |       |Activer les légendes dynamiques       |Désactivé mais peut être substitué         |Désactivé mais peut être substitué|
|  |       |Autoriser la discussion dans les réunions         |Activé         |Activé|
|  |Mode de filtres vidéo       |VideoFiltersMode         |BlurandDefaultBackgrounds|AllFilters|
|  |Rapport présence sur une réunion       |AllowEngagementReport         |Désactivé         |Activé|
|Stratégie d’événements en direct  |       |Autoriser la planification         |Désactivé         |Désactivé|
|  |       |Autoriser la transcription pour les participants          |Activé       |Activé|
|  |       |Qui peut participer aux événements en direct planifiés        |Tout le monde au sein de l’Organisation        |Tout le monde au sein de l’Organisation|
|  |       |Qui peut enregistrer un événement         |Toujours         |Toujours|
|Stratégie de messagerie  |       |Les propriétaires peuvent supprimer des messages envoyés         |Désactivé|Activé|
|  |       |Supprimer des messages envoyés         |Désactivé         |Activé|
|  |       |Modifier des messages envoyés         |Désactivé         |Activé|
|  |       |Confirmations de lecture         |Contrôle utilisateur         |Contrôle utilisateur|
|  |       |Conversation         |Désactivé         |Activé|
|  |       |Utiliser Giphys dans les conversations         |Désactivé         |Activé|
|  |       |Évaluation du contenu Giphy         |Strict        |Strict|
|  |       |Utiliser mèmes dans les conversations         |Activé         |Activé|
|  |       |Utiliser les autocollants dans les conversations         |Activé         |Activé|
|  |       |Autoriser les aperçus d’URL        |Activé         |Activé|
|  |       |Traduire des messages         |Activé         |Activé|
|  |       |Autoriser le lecteur immersif à afficher les messages        |Activé      |Activé|
|  |       |Envoyer des messages urgents à l’aide de notifications de priorité  |Désactivé         |Activé|
|  |       |Créer des messages vocaux         |Autorisé dans les conversations et les canaux         |Autorisé dans les conversations et les canaux|
|  |       |Sur les appareils mobiles, afficher les canaux préférés au-dessus des discussions récentes     |Activé         |Activé|
|  |       |Supprimer des utilisateurs d’une discussion de groupe         |Désactivé         |Activé|
|  |       |Suggestions de réponses         |Activé         |Activé|
|Stratégie d’autorisation d’application  |       |Applications Microsoft         |Bloquer des applications spécifiques et permettre à tous les autres > de dialoguer sur le blocage         |Autoriser toutes les applications|
|  |       |Applications tierces         |Autoriser toutes les applications         |Autoriser toutes les applications|
|  |       |Applications personnalisées         |Autoriser toutes les applications         |Autoriser toutes les applications|
|Politique de configuration des applications  |           |Télécharger des applications personnalisées           |Désactivé         |Désactivé|
|  |       |Autoriser l’épinglage de l’utilisateur |Activé         |Activé|
|  |       |Applications installées         |Aucun         |Aucun|
|  |       |Applications épinglées         |Activité, calendrier, équipes         |Activité, discussions, équipes, calendrier, appels, fichiers
|Stratégie d’Appel  |       |Passer des appels privés         |Désactivé        |Activé|
|  |       |Transfert d’appel et sonnerie simultanée pour les membres de votre organisation         |Désactivé         |Activé|
|  |       |Transfert d’appel et sonnerie simultanée sur les numéros de téléphone externes         |Désactivé         |Activé|
|  |       |La boîte vocale est disponible pour le routage des appels entrants         |Contrôle utilisateur         |Contrôle utilisateur|
|  |       |Les appels entrants peuvent être routés vers des groupes d’appels         |Désactivé        |Activé|
|  |       |Autoriser la délégation pour les appels entrants et sortants         |Désactivé         |Activé|
|  |       |Empêcher le contournement payant et envoyer les appels via PSTN        |Désactivé         |Désactivé|
|  |       |Le niveau occupé est disponible en cas d’appel         |Désactivé         |Désactivé|
|  |       |Autoriser les appels RTC Web         |Désactivé         |Activé|

#### <a name="educators-and-staff"></a>[**Enseignants et personnel**](#tab/educator-settings/)

Vous trouverez ci-dessous la liste des définitions de stratégie personnalisées attribuées aux enseignants et aux groupes de personnel que vous choisissez dans l’Assistant.  

|Zone de stratégie |Sous-zone  |Paramètre de stratégie  |Principal ou secondaire |Enseignement supérieur |
|---------|---------|---------|---------|---------|
|Stratégie Teams   |         |Créer des canaux privés         |Activé       |Activé|
|Stratégie de réunion    |Général         |Autoriser la Conférence maintenant dans les canaux         |Activé      |Activé|
|  |        |Autoriser le complément Outlook         |Activé       |Activé|
|  |        |Autoriser la planification des réunions de canal        |Activé      |Activé|
|  |        |Autoriser la planification de réunions privées       |Activé      |Activé|
|  |Audio & vidéo        |Autoriser la transcription        |Activé       |Activé|
|  |        |Autoriser l’enregistrement Cloud         |Activé      |Activé|
|  |        |Mode pour le son IP       |Audio entrant et sortant activé        |Audio entrant et sortant activé|
|  |        |Mode pour la vidéo IP         |Vidéo sortante et entrante activée     |Vidéo sortante et entrante activée|
|  |       |Autoriser la vidéo sur IP         |Activé         |Activé|
|  |       |Autoriser NDI streaming         |Désactivé         |Désactivé|
|  |       |Taux d’échantillonnage du support (Ko)         |50 000         |50 000|
|  |Partage de contenu       |Mode de partage d’écran         |Tout l’écran         |Tout l’écran|
|  |       |Autoriser un participant à céder ou demander le contrôle         |Activé         |Activé|
|  |       |Autoriser un participant externe à céder ou demander le contrôle         |Activé         |Activé|
|  |       |Autoriser le partage PowerPoint        |Activé         |Activé|
|  |       |Autoriser le tableau blanc         |Activé         |Activé|
|  |       |Autoriser les notes partagées         |Activé        |Activé|
|  |Participants & invités       |Permettre aux utilisateurs anonymes de démarrer une réunion       |Activé        |Activé|
|  |       |Rôles possédant des droits de présentateur pour les réunions        |OrganizerOnlyUserOverride         |OrganizerOnlyUserOverride|
|  |       |Admettre automatiquement des personnes        |Organisateur : seule|Organisateur : seule|
|  |       |Autoriser les utilisateurs rendez-vous à ignorer la salle d’attente        |Désactivé         |Désactivé|
|  |       |Autoriser la Conférence maintenant dans les réunions privées        |Activé         |Activé|
|  |       |Activer les légendes dynamiques       |Désactivé mais peut être substitué         |Désactivé mais peut être substitué|
|  |       |Autoriser la discussion dans les réunions         |Activé         |Activé|
|  |Mode de filtres vidéo       |VideoFiltersMode         |AllFilters|AllFilters|
|  |Rapport présence sur une réunion       |AllowEngagementReport         |Activé         |Activé|
|Stratégie d’événements en direct  |       |Autoriser la planification         |Activé         |Activé|
|  |       |Autoriser la transcription pour les participants          |Activé       |Activé|
|  |       |Qui peut participer aux événements en direct planifiés        |Tout le monde au sein de l’Organisation        |Tout le monde au sein de l’Organisation|
|  |       |Qui peut enregistrer un événement         |Toujours enregistrer         |Toujours enregistrer|
|Stratégie de messagerie  |       |Les propriétaires peuvent supprimer des messages envoyés         |Activé|Activé|
|  |       |Supprimer des messages envoyés         |Activé         |Activé|
|  |       |Modifier des messages envoyés         |Activé         |Activé|
|  |       |Confirmations de lecture         |Contrôle utilisateur         |Contrôle utilisateur|
|  |       |Conversation         |Activé         |Activé
|  |       |Utiliser Giphys dans les conversations         |Activé        |Activé|
|  |       |Évaluation du contenu Giphy         |Strict        |Strict|
|  |       |Utiliser mèmes dans les conversations         |Activé         |Activé|
|  |       |Utiliser les autocollants dans les conversations         |Activé         |Activé|
|  |       |Autoriser les aperçus d’URL        |Activé         |Activé|
|  |       |Traduire des messages         |Activé         |Activé|
|  |       |Autoriser le lecteur immersif à afficher les messages        |Activé      |Activé|
|  |       |Envoyer des messages urgents à l’aide de notifications de priorité  |Activé         |Activé|
|  |       |Créer des messages vocaux         |Autorisé dans les conversations et les canaux         |Autorisé dans les conversations et les canaux|
|  |       |Sur les appareils mobiles, afficher les canaux préférés au-dessus des discussions récentes     |Activé         |Activé|
|  |       |Supprimer des utilisateurs d’une discussion de groupe         |Activé        |Activé|
|  |       |Suggestions de réponses         |Activé         |Activé|
|Stratégie d’Appel  |       |Passer des appels privés         |Activé       |Activé|
|  |       |Transfert d’appel et sonnerie simultanée pour les membres de votre organisation         |Activé        |Activé|
|  |       |Transfert d’appel et sonnerie simultanée sur les numéros de téléphone externes         |Activé        |Activé|
|  |       |La boîte vocale est disponible pour le routage des appels entrants         |Contrôle utilisateur         |Contrôle utilisateur|
|  |       |Les appels entrants peuvent être routés vers des groupes d’appels         |Activé        |Activé|
|  |       |Autoriser la délégation pour les appels entrants et sortants         |Activé         |Activé|
|  |       |Empêcher le contournement payant et envoyer les appels via PSTN        |Désactivé         |Désactivé|
|  |       |Le niveau occupé est disponible en cas d’appel         |Désactivé         |Désactivé|
|  |       |Autoriser les appels RTC Web         |Activé      |Activé|

* * *

## <a name="related-topics"></a>Voir aussi

- [Stratégies d’équipe et packages de stratégie pour l’éducation](policy-packages-edu.md)
- [Attribution de stratégies à de grands ensembles d’utilisateurs dans votre établissement scolaire](batch-group-policy-assignment-edu.md)
- [Garantir la sécurité des étudiants lors de l’utilisation d’équipes pour une formation à distance](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)

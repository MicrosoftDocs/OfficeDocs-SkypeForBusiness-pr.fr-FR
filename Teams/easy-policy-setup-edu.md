---
title: Teams pour l'éducation Assistant Stratégie pour appliquer facilement des stratégies pour l’apprentissage en toute sécurité
author: serdars
ms.author: serdars
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
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment utiliser l’Assistant Stratégie Teams pour l'éducation pour appliquer facilement des stratégies aux étudiants et aux enseignants afin de sécuriser votre environnement d’apprentissage.
f1keywords: ''
ms.openlocfilehash: 245739f06d86459f119d9f5d0a37e67ac4098953
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675916"
---
# <a name="use-the-teams-for-education-policy-wizard-to-easily-apply-policies-for-a-safe-learning-environment"></a>Utilisez l’Assistant Stratégie Teams pour l'éducation pour appliquer facilement des stratégies pour un environnement d’apprentissage sécurisé

## <a name="overview"></a>Présentation

L’Assistant Stratégie Microsoft Teams pour l'éducation simplifie la gestion des stratégies pour vos étudiants et enseignants. Utilisez-le pour appliquer facilement et rapidement l’ensemble le plus important de stratégies pertinentes à la création d’une expérience d’apprentissage sûre et productive.

Les stratégies de Teams vous permettent de contrôler le comportement de Teams dans votre environnement et les fonctionnalités disponibles pour les utilisateurs. Par exemple, il existe des stratégies d’appel, des stratégies de réunion et des stratégies de messagerie, pour n’en nommer que quelques-unes, et chaque zone de stratégie peut être personnalisée pour répondre aux besoins de votre organisation.

Pour maintenir un environnement d’apprentissage sûr et ciblé, il est important de définir des stratégies pour contrôler ce que les étudiants peuvent faire dans Teams. Par exemple, vous pouvez utiliser des stratégies pour contrôler qui peut utiliser une conversation privée et un appel privé, qui peut planifier des réunions et quels types de contenu peuvent être partagés. Vous pouvez également utiliser des stratégies pour activer Teams fonctionnalités qui enrichissent l’expérience d’apprentissage.

Les stratégies doivent être ajustées pour que les élèves et les enseignants puissent garder l’expérience d’apprentissage sécuritaire. Les politiques pour les étudiants doivent être plus restrictives afin de réduire le risque de recevoir des niveaux d’accès inappropriés. Les enseignants et le personnel ont besoin d’un ensemble distinct de politiques qui peuvent être plus permissives pour leur permettre de réussir. Par exemple, autorisez les enseignants à planifier des réunions et à empêcher les étudiants de le faire.

:::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Capture d’écran de l’Assistant.":::

Cet article vous guide tout au long de l’exécution de l’Assistant.

> [!IMPORTANT]
> Les stratégies appliquées par l’Assistant répondent aux besoins de la majorité des clients Teams pour l'éducation. L’Assistant ajuste la définition globale (par défaut à l’échelle de l’organisation) d’un ensemble de stratégies de base avec des paramètres que nous recommandons pour la sécurité des étudiants et l’applique aux étudiants. L’Assistant crée et affecte également un ensemble de stratégies personnalisées aux enseignants et au personnel enseignant. La plupart des Teams pour l'éducation clients n’ont pas besoin d’utiliser d’autres méthodes d’attribution de stratégie après l’exécution de cet Assistant. Utilisez d’autres méthodes d’affectation de stratégie *uniquement* si vous souhaitez créer et gérer manuellement des stratégies pour vos étudiants, enseignants et membres du personnel.

## <a name="teams-for-education-policy-wizard"></a>Assistant Stratégie Teams pour l'éducation

<a name="polwiz_intro"> </a>

L’Assistant applique un ensemble de définitions de stratégie de base aux étudiants et un ensemble distinct de définitions de stratégie de base aux enseignants et au personnel enseignant, avec des paramètres appropriés pour chacun d’eux. Voici ce qui se passe lorsque vous exécutez l’Assistant.

L’Assistant configure des stratégies basées sur le type d’établissement d’enseignement (**primaire, secondaire** ou **supérieur**). Vous sélectionnez votre type d’établissement et l’Assistant effectue les opérations suivantes :

- **Étudiants** : l’Assistant ajuste la définition de stratégie globale (par défaut à l’échelle de l’organisation) de chaque zone de stratégie couverte par l’Assistant avec les nouveaux paramètres par défaut qui sont appropriés pour assurer la sécurité de vos étudiants. Cela garantit que vos étudiants actuels et tous les nouveaux étudiants bénéficient de l’ensemble de politiques le plus restrictif.
- **Enseignants et membres du personnel** : l’Assistant crée un ensemble de définitions de stratégie personnalisées pour chaque zone de stratégie couverte par l’Assistant avec des paramètres adaptés aux besoins des enseignants et du personnel. Ensuite, il affecte les définitions de stratégie au groupe d’enseignants et de membres du personnel que vous choisissez. De cette façon, vos enseignants et votre personnel obtiennent un ensemble de politiques plus permissif pour leur permettre de réussir.

Vous n’avez besoin d’exécuter l’Assistant qu’une seule fois. Les nouveaux étudiants obtiennent automatiquement les définitions de stratégie globales (par défaut à l’échelle de l’organisation) appliquées par l’Assistant et les nouvelles équipes que vous ajoutez au groupe que vous avez sélectionné reçoivent automatiquement les stratégies personnalisées.

En outre, chaque fois qu’une nouvelle fonctionnalité est ajoutée à Teams, la valeur par défaut appropriée de la stratégie edu appropriée pour cette fonctionnalité est automatiquement ajoutée au global (valeur par défaut à l’échelle de l’organisation) sans aucune intervention de l’administrateur. Cela permet de s’assurer que les bonnes politiques sont en place pour assurer la sécurité et l’engagement des étudiants.

> [!NOTE]
> Consultez [Stratégies appliquées par l’Assistant](#policies-applied-by-the-wizard) pour obtenir une liste détaillée des définitions de stratégie appliquées par l’Assistant.

Maintenant, commençons !

## <a name="run-the-wizard"></a>Exécuter l’Assistant

<a name="polwiz_run"> </a>

Suivez ces étapes pour exécuter l’Assistant.

1. Si vous débutez avec Teams, l’Assistant démarre automatiquement. Sinon, vous pouvez démarrer l’Assistant à tout moment à partir du tableau de bord. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez à **Accueil**, puis, dans la vignette Configuration facile **d’un environnement d’apprentissage sécurisé**, sélectionnez **Configuration rapide**.

    :::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="Capture d’écran de l’Assistant dans le tableau de bord.":::

2. Sélectionnez votre type d’établissement d’enseignement (**primaire, secondaire** ou **supérieur**), puis **sélectionnez Suivant**.

    :::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Capture d’écran de la page de l’Assistant pour sélectionner le type d’établissement.":::

3. Recherchez et sélectionnez les groupes qui contiennent vos enseignants et votre personnel, puis sélectionnez **Suivant**. Si vous n’avez pas encore de groupes configurés pour vos enseignants et votre personnel enseignant, [créez un groupe](/microsoft-365/admin/create-groups/create-groups), puis réexélez l’Assistant. <br/><br/>Vous pouvez sélectionner jusqu’à trois groupes. Les enseignants et le personnel des groupes que vous sélectionnez se verront attribuer [un ensemble de stratégies personnalisées adaptées](#policies-applied-by-the-wizard) à leurs besoins. N’oubliez pas que cet ensemble de stratégies est distinct des stratégies appliquées aux étudiants.

    :::image type="content" source="media/edu-policy-wizard-add-3-groups.png" alt-text="Capture d’écran de la page de l’Assistant pour sélectionner des groupes d’enseignants et de membres du personnel.":::

4. Passez en revue vos sélections.

    :::image type="content" source="media/edu-policy-wizard-3-groups-review.png" alt-text="Capture d’écran de la page dans l’Assistant pour passer en revue les sélections.":::

5. Sélectionnez **Appliquer** pour appliquer vos modifications. Cette opération peut prendre quelques minutes.<br/><br/>Les définitions de stratégie globales (par défaut à l’échelle de l’organisation) sont immédiatement appliquées aux étudiants. Pour vos enseignants et votre personnel, l’affectation des stratégies personnalisées à chaque membre des groupes sélectionnés peut prendre quelques heures, en fonction de la taille des groupes. Cela se produit en arrière-plan, une fois cette étape terminée.
6. Vous êtes sur votre chemin, mais vous n’avez pas encore terminé! Il y a encore quelques points à prendre en compte. Ensuite, consultez les étapes décrites dans la section [Que faire après avoir exécuté la section Assistant](#what-to-do-after-running-the-wizard) de cet article.

    :::image type="content" source="media/easy-policy-setup-on-way.png" alt-text="Capture d’écran de la page dans l’Assistant pour les étapes suivantes.":::

## <a name="what-to-do-after-running-the-wizard"></a>Procédure à suivre après l’exécution de l’Assistant

<a name="polwiz_remove"> </a>

### <a name="step-1-remove-existing-policy-assignments-that-conflict-with-policies-applied-by-the-wizard"></a>Étape 1 : Supprimer les affectations de stratégie existantes en conflit avec les stratégies appliquées par l’Assistant

> [!IMPORTANT]
> **Effectuez cette étape uniquement si des stratégies existantes sont affectées aux étudiants, aux enseignants et au personnel *avant* d’exécuter l’Assistant**. Si vous débutez avec Teams et que vous n’avez pas d’autres stratégies que les stratégies créées par l’Assistant, ignorez-la et passez à l’étape 2.

Dans Teams, pour une zone de stratégie donnée, une stratégie peut être appliquée à un utilisateur des manières suivantes :

- Affectation directe à l’utilisateur
- Affectation à un groupe dont l’utilisateur est membre
- Si l’utilisateur ne reçoit pas directement une stratégie ou n’est pas membre d’un groupe auquel une stratégie est affectée, l’utilisateur obtient automatiquement la stratégie globale (par défaut à l’échelle de l’organisation).

Si plusieurs de ces affectations de stratégie existent pour un utilisateur, Teams utilise l’ordre suivant pour déterminer quelle affectation de stratégie prend effet. Pour plus d’informations, consultez [la stratégie qui a la priorité](policy-assignment-overview.md#which-policy-takes-precedence) ou [les règles de précédence pour les groupes](assign-policies-users-and-groups.md#precedence-rules).

|Affectations de stratégie d’un utilisateur|Stratégie qui prend effet|
|---|---|
|Stratégie affectée au groupe : Non <p> Stratégie affectée directement à l’utilisateur : Non|Stratégie par défaut globale (à l’échelle de l’organisation)|
|Stratégie affectée au groupe : Non <p> Stratégie affectée directement à l’utilisateur : Oui|Stratégie affectée directement à l’utilisateur|
|Stratégie affectée au groupe : Oui <p> Stratégie affectée directement à l’utilisateur : Oui|Stratégie affectée directement à l’utilisateur|
|Stratégie affectée au groupe : Oui <p> Stratégie affectée directement à l’utilisateur : Non|Stratégie affectée au groupe <p> Si l’utilisateur est membre de plusieurs groupes et que chaque groupe reçoit une stratégie de la même zone de stratégie, la stratégie qui a le [classement d’attribution de groupe](assign-policies-users-and-groups.md#group-assignment-ranking) le plus élevé prend effet.|

En raison de cet ordre, les stratégies créées par l’Assistant n’entrent pas en vigueur si un utilisateur a des affectations directes ou des affectations de groupe existantes. Cela signifie que vous devrez supprimer les affectations de stratégie existantes de l’utilisateur afin que la stratégie appliquée par l’Assistant prenne effet.

Pour chaque [zone de stratégie appliquée par l’Assistant](#policies-applied-by-the-wizard), procédez comme suit :

- Supprimez toutes les affectations directes et les affectations de groupe existantes de vos étudiants afin que la définition de stratégie globale (par défaut à l’échelle de l’organisation) appliquée par l’Assistant prenne effet.
- Supprimez les affectations directes en conflit pour vos enseignants et votre personnel afin que la définition de stratégie personnalisée créée par l’Assistant prenne effet. Utilisez le tableau ci-dessus pour déterminer les scénarios qui s’appliquent à vous. <p> N’oubliez pas que l’Assistant affecte des stratégies à vos enseignants et à votre groupe de membres du personnel à l’aide d’un [classement d’affectation de groupe](assign-policies-users-and-groups.md#group-assignment-ranking) de 1, qui est le classement le plus élevé. Si vos enseignants et votre groupe de membres du personnel disposent d’une stratégie existante de la même zone de stratégie qui lui est affectée, cette stratégie existante est déplacée vers un classement inférieur et la stratégie affectée par l’Assistant prend effet.

[En savoir plus](batch-group-policy-assignment-edu.md#remove-a-policy-that-was-directly-assigned-to-users) sur la suppression des stratégies qui sont directement affectées aux utilisateurs.

Par exemple, vous avez affecté une stratégie de réunion directement aux enseignants et vos étudiants disposent de la stratégie de réunion globale (par défaut à l’échelle de l’organisation). Dans ce scénario, supprimez la stratégie de réunion que vous avez directement affectée aux enseignants afin que la définition de stratégie personnalisée pour la stratégie de réunion créée par l’Assistant prenne effet. Vous n’avez rien à faire avec la stratégie de réunion globale (par défaut à l’échelle de l’organisation) existante pour les étudiants, car aucune autre stratégie de réunion n’est en conflit avec elle.

<a name="polwiz_addmeasures"> </a>

### <a name="step-2-check-for-additional-measures-that-you-can-take-for-student-safety"></a>Étape 2 : Vérifier les mesures supplémentaires que vous pouvez prendre pour la sécurité des étudiants

L’Assistant ajuste et applique automatiquement [ces stratégies](#policies-applied-by-the-wizard). Il existe peu de mesures supplémentaires, que vous souhaiterez peut-être prendre en fonction des besoins de votre établissement pour rester en sécurité.

Pour obtenir des recommandations supplémentaires en matière de sécurité, consultez [La sécurité des étudiants lors de l’utilisation de Teams pour l’apprentissage à distance](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8#ID0EBBAAA).

<a name="polwiz_mc"> </a>

### <a name="step-3-check-message-center-for-policy-updates"></a>Étape 3 : Rechercher les mises à jour de stratégie dans le Centre de messages

Actuellement, l’Assistant applique nos stratégies recommandées quand vous l’exécutez. Il est important de savoir qu’à mesure que de nouvelles stratégies deviennent disponibles dans Teams, les paramètres globaux (par défaut à l’échelle de l’organisation) pour la sécurité des étudiants sont automatiquement mis à jour par l’Assistant.

Toutefois, consultez fréquemment le [Centre](https://admin.microsoft.com/AdminPortal/Home?#/MessageCenter) de messages (dans le Centre d'administration Microsoft 365) pour rester à jour sur les nouvelles fonctionnalités et leurs stratégies et paramètres de stratégie dans Teams.

## <a name="make-changes-in-the-wizard"></a>Apporter des modifications dans l’Assistant

<a name="polwiz_change"> </a>

Si vous devez apporter des modifications après avoir exécuté l’Assistant, vous pouvez le réexécuter et modifier vos sélections.

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez à **Accueil**, puis, dans la configuration de stratégie **facile pour une vignette d’environnement d’apprentissage sécurisé**, **sélectionnez Modifier**.
2. À partir de là, passez à travers chaque page de l’Assistant pour apporter vos modifications. Vous pouvez modifier le type de votre établissement, les groupes d’enseignants et le personnel auquel vous souhaitez affecter des stratégies, ou les deux.

Le tableau suivant récapitule ce qui se passe lorsque vous apportez une modification dans l’Assistant.

|Type de modification|Comportement de la stratégie|
|---|---|
|Modifier à la fois le type d’établissement d’enseignement et les enseignants et les groupes de personnel|<ul><li>**Étudiants** : Les définitions de stratégie globales (par défaut à l’échelle de l’organisation) basées sur le nouveau type d’établissement d’enseignement sont appliquées aux étudiants.</li><li>**Enseignants et personnel** enseignant : un ensemble de définitions de stratégie personnalisées basées sur le nouveau type d’établissement d’enseignement est créé et affecté aux nouveaux groupes d’enseignants et de membres du personnel. Les définitions de stratégie personnalisées précédentes sont supprimées des enseignants et groupes de personnel précédents.</li></ul>|
|Modifier uniquement le type d’établissement d’enseignement|<ul><li>**Étudiants** : Les définitions de stratégie globales (par défaut à l’échelle de l’organisation) basées sur le nouveau type d’établissement d’enseignement sont appliquées aux étudiants.</li><li>**Enseignants et personnel** enseignant : un ensemble de définitions de stratégie personnalisées basées sur le nouveau type d’établissement d’enseignement est créé et affecté aux enseignants et aux groupes de personnel. Les définitions de stratégie personnalisées créées pour le type d’établissement d’enseignement précédent sont supprimées des enseignants et des groupes d’enseignants.</li></ul>|
|Modifier uniquement les enseignants et les groupes de personnel|<ul><li>**Étudiants** : Aucune modification n’a été apportée aux définitions de stratégie globales (par défaut à l’échelle de l’organisation) appliquées aux étudiants.</li><li>**Enseignants et membres du personnel** : les définitions de stratégie personnalisées sont attribuées aux nouveaux enseignants et groupes de personnel et supprimées des groupes d’enseignants et de personnel précédents.</li></ul>|

## <a name="policies-applied-by-the-wizard"></a>Stratégies appliquées par l’Assistant

<a name="polwiz_policies"> </a>

### <a name="policy-areas"></a>Domaines de stratégie

Voici les zones de stratégie et les noms de stratégie correspondants couverts par l’Assistant. Pour trouver ces stratégies, accédez au centre d’administration Microsoft Teams, puis, dans la navigation de gauche, accédez à chaque page de zone de stratégie.

#### <a name="students"></a>[**Étudiants**](#tab/students/)

|Zone de stratégie|Nom de la stratégie primaire ou secondaire|Nom de la politique de l’enseignement supérieur|
|---|---|---|
|Stratégie Teams|Global (par défaut à l’échelle de l’organisation)|Global (par défaut à l’échelle de l’organisation)|
|Stratégie de réunion|Global (par défaut à l’échelle de l’organisation)|Global (par défaut à l’échelle de l’organisation)|
|Stratégie d’événements en direct|Global (par défaut à l’échelle de l’organisation)|Global (par défaut à l’échelle de l’organisation)|
|Stratégie d’installation de l’application|Global (par défaut à l’échelle de l’organisation)|Global (par défaut à l’échelle de l’organisation)|
|Stratégie d’autorisation d’application|Global (par défaut à l’échelle de l’organisation)|Global (par défaut à l’échelle de l’organisation)|
|Stratégie de messagerie|Global (par défaut à l’échelle de l’organisation)|Global (par défaut à l’échelle de l’organisation)|
|Stratégie d’Appel|Global (par défaut à l’échelle de l’organisation)|Global (par défaut à l’échelle de l’organisation)|

#### <a name="educators-and-staff"></a>[**Enseignants et personnel**](#tab/educators/)

|Zone de stratégie|Nom de la stratégie primaire ou secondaire|Nom de la politique de l’enseignement supérieur|
|---|---|---|
|Stratégie Teams|Enseignants et membres du personnel principal ou secondaire - Teams|Enseignants et membres du personnel de l’enseignement supérieur - Teams|
|Stratégie de réunion|Enseignants et membres du personnel principal ou secondaire - Réunion|Enseignants et membres du personnel de l’enseignement supérieur - Réunion|
|Stratégie d’événements en direct|Enseignants et membres du personnel principal ou secondaire - Événements en direct|Enseignants et membres du personnel de l’enseignement supérieur - Événements en direct|
|Stratégie de messagerie|Enseignants et membres du personnel principal ou secondaire - Messagerie|Enseignants et membres du personnel de l’enseignement supérieur - Messagerie|
|Stratégie d’Appel|Enseignants et membres du personnel principal ou secondaire - Appel|Enseignants et personnel de l’enseignement supérieur - Appel|

### <a name="policy-settings"></a>Paramètres de stratégie

Voici un résumé des paramètres appliqués par l’Assistant pour chaque zone de stratégie.

> [!NOTE]
> Seuls les propriétaires d’équipe peuvent créer des canaux partagés.<br><br>Les canaux partagés avec d’autres organisations nécessitent la configuration de la [connexion directe Azure AD B2B](/azure/active-directory/external-identities/b2b-direct-connect-overview) , qui est désactivée par défaut. Pour activer cette fonctionnalité, consultez [Collaborer avec des participants externes dans un canal](/microsoft-365/solutions/collaborate-teams-direct-connect) .

#### <a name="students"></a>[**Étudiants**](#tab/student-settings/)

Voici une liste des définitions de stratégie globales (par défaut à l’échelle de l’organisation) ajustées par l’Assistant et appliquées aux étudiants.

|Zone de stratégie|Sous-zone|Paramètre de stratégie|Principal ou secondaire|Enseignement supérieur|
|---|---|---|---|---|
|Stratégie Teams||Créer des canaux privés|Désactivé|Activé|
|||Créer des canaux partagés|Activé|Activé|
|||Partager un canal avec des participants externes|Activé|Activé|
|||Participer à un canal partagé externe|Activé|Activé|
|Stratégie de réunions|Général|Autoriser la conférence maintenant dans les canaux|Désactivé|Activé|
|||Autoriser le complément Outlook|Désactivé|Activé|
|||Autoriser la planification des réunions pour les canaux|Désactivé|Activé|
|||Autoriser la planification des réunions privées|Désactivé|Activé|
|||Autoriser l’inscription à une réunion|Activé|Activé|
|||Qui peut s’inscrire|Tous les membres de l’organisation|Tous les membres de l’organisation|
||Vidéo de & audio|Transcription|Activé|Activé|
|||Enregistrement cloud|Désactivé|Activé|
|||Mode pour l’audio sur IP|Audio sortant et entrant activé|Audio sortant et entrant activé|
|||Mode pour la vidéo sur IP|Vidéo sortante et entrante activée|Vidéo sortante et entrante activée|
|||Vidéo IP|Activé|Activé|
|||Autoriser la diffusion en continu de NDI|Désactivé|Désactivé|
|||Vitesse de transmission du média (Ko)|50 000|50 000|
||Partage de contenu|Mode de partage d’écran|Écran entier|Écran entier|
|||Autoriser un participant à donner ou demander le contrôle|Activé|Activé|
|||Autoriser un participant externe à donner ou demander le contrôle|Activé|Activé|
|||partage PowerPoint|Activé|Activé|
|||Tableau blanc|Activé|Activé|
|||Notes partagées|Activé|Activé|
||Participants & invités|Autoriser les personnes anonymes à démarrer une réunion|Désactivé|Activé|
|||Rôles qui ont des droits de présentateur dans les réunions|EveryoneUserOverride|EveryoneUserOverride|
|||Admettre les personnes automatiquement|EveryoneInCompany|EveryoneInCompany|
|||Autoriser les utilisateurs entrants à éviter la salle d’attente|Désactivé|Désactivé|
|||Se réunir maintenant dans des réunions privées|Désactivé|Activé|
|||Légendes en direct|Désactivé, mais l’utilisateur peut remplacer|Désactivé, mais l’utilisateur peut remplacer|
|||Conversation dans les réunions|Activé|Activé|
|Stratégie d’événements en direct||Planification des événements en direct|Désactivé|Désactivé|
|||Transcription pour les participants|Activé|Activé|
|||Qui peut participer aux événements en direct planifiés|Tous les membres de l’organisation|Tous les membres de l’organisation|
|||Qui pouvez enregistrer un événement|Toujours|Toujours|
|Stratégie de messagerie||Les propriétaires peuvent supprimer les messages envoyés|Désactivé|Activé|
|||Supprimer des messages envoyés|Désactivé|Activé|
|||Modifier des messages envoyés|Désactivé|Activé|
|||Confirmations de lecture|Contrôlé par l’utilisateur|Contrôlé par l’utilisateur|
|||Conversation|Désactivé|Activé|
|||Giphys dans les conversations|Désactivé|Activé|
|||Évaluation du contenu Giphy|Stricte|Stricte|
|||Mèmes dans les conversations|Activé|Activé|
|||Autocollants dans les conversations|Activé|Activé|
|||Aperçus d’URL|Activé|Activé|
|||Traduire des messages|Activé|Activé|
|||Lecteur immersif pour les messages|Activé|Activé|
|||Envoyer des messages urgents à l’aide de notifications de priorité|Désactivé|Activé|
|||Créer des messages vocaux|Autorisé dans les conversations et les canaux|Autorisé dans les conversations et les canaux|
|||Sur les appareils mobiles, affichez les canaux favoris au-dessus des conversations récentes|Activé|Activé|
|||Supprimer des utilisateurs des conversations de groupe|Désactivé|Activé|
|Stratégie d’autorisation d’application||Applications Microsoft|Bloquer des applications spécifiques et autoriser tous les autres > Walkie Talkie bloqué|Autoriser toutes les applications|
|||Applications tierces|Autoriser toutes les applications|Autoriser toutes les applications|
|||Applications personnalisées|Autoriser toutes les applications|Autoriser toutes les applications|
|Stratégie d’installation de l’application||Télécharger applications personnalisées|Désactivé|Désactivé|
|||Épinglage d’utilisateur|Activé|Activé|
|||Applications installées|Aucun|Aucun|
|||Applications épinglées|Activité, Calendrier, Teams|Activité, conversations, Teams, calendrier, appel, fichier
|Stratégie d’Appel||Passer des appels privés|Désactivé|Activé|
|||Transfert d’appel et sonnerie simultanée aux membres de votre organisation|Désactivé|Activé|
|||Transfert d’appel et sonnerie simultanée vers des numéros de téléphone externes|Désactivé|Activé|
|||La messagerie vocale est disponible pour le routage des appels entrants|Contrôlé par l’utilisateur|Contrôlé par l’utilisateur|
|||Les appels entrants peuvent être routées vers des groupes d’appels|Désactivé|Activé|
|||Autoriser la délégation pour les appels entrants et sortants|Désactivé|Activé|
|||Empêcher le contournement des péages et envoyer des appels via le RTC|Désactivé|Désactivé|
|||Busy on busy est disponible lors d’un appel|Désactivé|Désactivé|
|||Autoriser les appels RTC web|Désactivé|Activé|

#### <a name="educators-and-staff"></a>[**Enseignants et personnel**](#tab/educator-settings/)

Voici une liste des définitions de stratégie personnalisées affectées aux enseignants et aux groupes de personnel que vous choisissez dans l’Assistant.  

|Zone de stratégie|Sous-zone|Paramètre de stratégie|Principal ou secondaire|Enseignement supérieur|
|---|---|---|---|---|
|Stratégie Teams||Créer des canaux privés|Activé|Activé|
|||Créer des canaux partagés|Activé|Activé|
|||Partager un canal avec des participants externes|Activé|Activé|
|||Participer à un canal partagé externe|Activé|Activé|
|Stratégie de réunions|Général|Autoriser la conférence maintenant dans les canaux|Activé|Activé|
|||Autoriser le complément Outlook|Activé|Activé|
|||Autoriser la planification des réunions pour les canaux|Activé|Activé|
|||Autoriser la planification des réunions privées|Activé|Activé|
|||Autoriser l’inscription à une réunion|Activé|Activé|
|||Qui peut s’inscrire|Tous les membres de l’organisation|Tous les membres de l’organisation|
||Vidéo de & audio|Transcription|Activé|Activé|
|||Enregistrement cloud|Activé|Activé|
|||Mode pour l’audio sur IP|Audio sortant et entrant activé|Audio sortant et entrant activé|
|||Mode pour la vidéo sur IP|Vidéo sortante et entrante activée|Vidéo sortante et entrante activée|
|||Vidéo IP|Activé|Activé|
|||Autoriser la diffusion en continu de NDI|Désactivé|Désactivé|
|||Vitesse de transmission du média (Ko)|50 000|50 000|
||Partage de contenu|Mode de partage d’écran|Écran entier|Écran entier|
|||Autoriser un participant à donner ou demander le contrôle|Activé|Activé|
|||Autoriser un participant externe à donner ou demander le contrôle|Activé|Activé|
|||partage PowerPoint|Activé|Activé|
|||Tableau blanc|Activé|Activé|
|||Notes partagées|Activé|Activé|
||Participants & invités|Autoriser les personnes anonymes à démarrer une réunion|Activé|Activé|
|||Rôles qui ont des droits de présentateur dans les réunions|OrganizerOnlyUserOverride|OrganizerOnlyUserOverride|
|||Admettre les personnes automatiquement|OrganizerOnly|OrganizerOnly|
|||Autoriser les utilisateurs entrants à éviter la salle d’attente|Désactivé|Désactivé|
|||Se réunir maintenant dans des réunions privées|Activé|Activé|
|||Légendes en direct|Désactivé, mais l’utilisateur peut remplacer|Désactivé, mais l’utilisateur peut remplacer|
|||Conversation dans les réunions|Activé|Activé|
|Stratégie d’événements en direct||Planification des événements en direct|Activé|Activé|
|||Transcription pour les participants|Activé|Activé|
|||Qui peut participer aux événements en direct planifiés|Tous les membres de l’organisation|Tous les membres de l’organisation|
|||Qui pouvez enregistrer un événement|Toujours enregistrer|Toujours enregistrer|
|Stratégie de messagerie||Les propriétaires peuvent supprimer les messages envoyés|Activé|Activé|
|||Supprimer des messages envoyés|Activé|Activé|
|||Modifier des messages envoyés|Activé|Activé|
|||Confirmations de lecture|Contrôlé par l’utilisateur|Contrôlé par l’utilisateur|
|||Conversation|Activé|Activé
|||Giphys dans les conversations|Activé|Activé|
|||Évaluation du contenu Giphy|Stricte|Stricte|
|||Mèmes dans les conversations|Activé|Activé|
|||Autocollants dans les conversations|Activé|Activé|
|||Aperçus d’URL|Activé|Activé|
|||Traduire des messages|Activé|Activé|
|||Lecteur immersif pour les messages|Activé|Activé|
|||Envoyer des messages urgents à l’aide de notifications de priorité|Activé|Activé|
|||Créer des messages vocaux|Autorisé dans les conversations et les canaux|Autorisé dans les conversations et les canaux|
|||Sur les appareils mobiles, affichez les canaux favoris au-dessus des conversations récentes|Activé|Activé|
|||Supprimer des utilisateurs des conversations de groupe|Activé|Activé|
|Stratégie d’Appel||Passer des appels privés|Activé|Activé|
|||Transfert d’appel et sonnerie simultanée aux membres de votre organisation|Activé|Activé|
|||Transfert d’appel et sonnerie simultanée vers des numéros de téléphone externes|Activé|Activé|
|||La messagerie vocale est disponible pour le routage des appels entrants|Contrôlé par l’utilisateur|Contrôlé par l’utilisateur|
|||Les appels entrants peuvent être routées vers des groupes d’appels|Activé|Activé|
|||Autoriser la délégation pour les appels entrants et sortants|Activé|Activé|
|||Empêcher le contournement des péages et envoyer des appels via le RTC|Désactivé|Désactivé|
|||Busy on busy est disponible lors d’un appel|Désactivé|Désactivé|
|||Autoriser les appels RTC web|Activé|Activé|

## <a name="related-topics"></a>Voir aussi

- [Stratégies et packages de stratégies Teams pour l’éducation](policy-packages-edu.md)
- [Affecter des stratégies à de grands ensembles d’utilisateurs dans votre établissement scolaire](batch-group-policy-assignment-edu.md)
- [Assurer la sécurité des étudiants lors de l’utilisation de Teams pour l’apprentissage à distance](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)

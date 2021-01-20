---
title: Gérer l’application Tâches pour votre organisation dans Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
audience: admin
description: Découvrez comment gérer l’application Tâches pour les utilisateurs de votre organisation.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2cc477b9589aeebb8dcd486e7f85ca04daf6ff4d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909398"
---
# <a name="manage-the-tasks-app-for-your-organization-in-microsoft-teams"></a>Gérer l’application Tâches pour votre organisation dans Microsoft Teams

## <a name="overview-of-tasks"></a>Vue d’ensemble des tâches

L’application Tâches apporte une expérience cohérente de gestion des tâches à Microsoft Teams, intégrant des tâches individuelles optimisées par [Microsoft To Do](https://todo.microsoft.com/tasks/) et des tâches d’équipe optimisées par le Planificateur à un seul endroit. Les utilisateurs peuvent accéder aux tâches en tant qu’application sur le côté gauche de Teams et en tant qu’onglet dans un canal au sein d’équipes individuelles. **Mes tâches et** **plans** partagés dans Tâches permet aux utilisateurs d’afficher et de gérer leurs tâches individuelles et d’équipe, et de hiérarchiser leur travail. Les tâches sont disponibles dans les clients de bureau, web et mobiles de Teams. 

> [!NOTE]
> Lorsque nous allons déployer l’expérience Tâches sur les clients de bureau Teams, le nom de l’application apparaîtra initialement **en** tant que Planificateur pour les utilisateurs. Le nom est alors temporairement remplacé par Tâches par Planificateur et À **faire.** Plus tard, il est renommé **Tâches.** Sur les clients mobiles Teams, les utilisateurs voient toujours le nom de l’application sous la forme **Tâches.** Une fois l’expérience de bureau disponible, la disponibilité de l’expérience mobile peut prendre un court délai.

   ![Capture d’écran de l’affichage de liste des tâches dans la liste Teams](media/manage-tasks-app-tasks.png)

Pour les organisations qui souhaitent simplifier la gestion des tâches pour les employés en avant-plan, les tâches incluent également des fonctionnalités qui vous permettent de cibler, de publier et de suivre les tâches à l’échelle de votre personnel en première ligne. Par exemple, les dirigeants d’entreprise et régionaux peuvent créer et publier des listes de tâches destinées à des emplacements appropriés, tels que des magasins de détail spécifiques, et suivre l’avancement à l’aide de rapports en temps réel. Les responsables peuvent affecter des tâches à leur personnel et diriger les activités au sein de leur emplacement. Les employés en contact direct avec leurs employés ont une liste hiérarchisées des tâches qui leur sont affectées sur les appareils mobiles ou les ordinateurs de bureau. Pour [activer](#task-publishing)la publication de tâches, vous devez d’abord configurer une hiérarchie de ciblage d’équipe pour votre organisation, qui définit la manière dont toutes les équipes dans la hiérarchie sont liées entre elles.

## <a name="what-you-need-to-know-about-tasks"></a>Ce que vous devez savoir sur les tâches

Les tâches sont disponibles sous la mesure d’une application et d’un onglet dans un canal. N’oubliez pas que l’application comprend à la fois des tâches individuelles de To Do et des tâches d’équipe du Planificateur, tandis que l’onglet affiche uniquement les tâches de l’équipe.

Grâce aux tâches, les utilisateurs peuvent obtenir une expérience de bureau, web et mobile. Si Tâches est installée sur le client de bureau Teams, les utilisateurs peuvent également la voir sur leurs clients Web et mobiles Teams. Les utilisateurs invités font exception. Il est important de savoir que les invités peuvent uniquement accéder aux tâches sous forme d’application à partir du client mobile Teams. Les invités voient les onglets Tâches sur les clients de bureau et web Teams.

**Mes tâches** indiquent les tâches individuelles d’un utilisateur. **Les plans partagés** montrent les tâches sur quoi travaille l’ensemble de l’équipe et incluent une liste des tâches ajoutée sous la la mesure d’un onglet Tâches à un canal. Notez ce qui suit :

- Les listes des tâches créées par un utilisateur dans l’application Tâches apparaissent également dans les clients Tâche pour cet utilisateur. De même, les listes des tâches créées par un utilisateur dans To Do apparaissent dans Mes **tâches** pour cet utilisateur. Il en va de même pour les tâches individuelles.

- Les onglets Tâches ajoutés à un canal apparaissent également dans les clients du Planificateur. Lorsqu’un utilisateur crée un plan dans le Planificateur, celui-ci n’est pas indiqué dans l’application Tâches ou Planificateur, sauf s’il est ajouté sous forme d’onglet à un canal. Lorsqu’un utilisateur ajoute un nouvel onglet Tâches, il peut créer une liste ou un plan, ou en choisir une existante.

## <a name="set-up-tasks"></a>Configurer les tâches

> [!IMPORTANT]
> Les paramètres et stratégies que vous avez configurés pour le Planificateur s’appliquent également aux tâches.

### <a name="enable-or-disable-tasks-in-your-organization"></a>Activer ou désactiver les tâches dans votre organisation

Les tâches sont activées par défaut pour tous les utilisateurs de Teams dans votre organisation. Vous pouvez désactiver ou activer l’application au niveau de l’organisation sur la page [Gérer les](manage-apps.md) applications du Centre d’administration Microsoft Teams.

1. Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez à **l’application Teams** Gérer  >  **les applications.**
2. Dans la liste des applications, faites l’une des choses suivantes :

    - Pour désactiver l’application Tâches pour votre organisation, recherchez l’application Tâches, sélectionnez-la, puis cliquez sur **Bloquer.**
    - Pour activer les tâches pour votre organisation, recherchez l’application Tâches, sélectionnez-la, puis cliquez sur **Autoriser.**

> [!NOTE]
> Si vous ne trouvez pas l’application Tâches, recherchez les noms dans la première note de cet article. L’application est peut-être en cours de modification du nom.

### <a name="enable-or-disable-tasks-for-specific-users-in-your-organization"></a>Activer ou désactiver les tâches pour des utilisateurs spécifiques de votre organisation

Pour autoriser ou empêcher des utilisateurs spécifiques de votre organisation d’utiliser les tâches, assurez-vous que la fonction Tâches est bien allumée pour votre organisation sur la [page](manage-apps.md) Gérer les applications, puis créez une stratégie d’autorisation d’application personnalisée et attribuez-la à ces utilisateurs. Pour en savoir plus, consultez [Gérer les stratégies d’autorisation d’application dans Teams.](teams-app-permission-policies.md)

### <a name="use-an-app-setup-policy-to-pin-tasks-to-teams"></a>Utiliser une stratégie de configuration d’application pour épingler les tâches à Teams

Les stratégies de configuration d’application vous permettent de personnaliser Teams pour mettre en évidence les applications les plus importantes pour les utilisateurs de votre organisation. Les applications que vous définissez dans une stratégie sont épinglées à la barre de l’application sur le côté du client de bureau Teams et en bas des clients mobiles Teams, où les utilisateurs peuvent y accéder rapidement et &mdash; &mdash; facilement.

Pour épingler l’application Tâches pour vos utilisateurs, vous pouvez modifier la stratégie globale (à l’échelle de l’organisation par défaut) ou créer et affecter une stratégie de configuration d’application personnalisée. Pour en savoir plus, consultez [Gérer les stratégies de configuration d’application dans Teams.](teams-app-setup-policies.md)

### <a name="a-users-my-tasks-is-visible-if-the-user-is-licensed-for-exchange-online"></a>Les tâches Mes tâches d’un utilisateur sont visibles si l’utilisateur est titulaire d’une licence Exchange Online

Si vous ne voulez pas qu’un utilisateur **voie** mes tâches, vous pouvez les masquer. Pour ce faire, [supprimez la licence Exchange Online de l’utilisateur.](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users) Il est important de savoir qu’après avoir supprimé une licence Exchange Online, l’utilisateur n’a plus accès à sa boîte aux lettres.  Les données de boîte aux lettres sont en attente pendant 30 jours, après quoi elles sont supprimées et ne peuvent pas être récupérées, sauf si la boîte aux lettres est placée en attente sur place ou en attente pour [litige.](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds)

Cette fonction n’est pas recommandée pour les travailleurs de l’information, mais il peut y avoir des cas où cela pourrait s’appliquer, par exemple, pour les employés en ligne qui ne dépendent pas de leur messagerie.

## <a name="task-publishing"></a>Publication de tâches

Grâce à la publication de tâches, votre organisation peut publier des listes des tâches ciblées à des emplacements spécifiques (équipes) au sein de votre organisation pour définir et partager un plan de travail à terminer à ces emplacements.

- Les membres de l’équipe de publication, comme les dirigeants d’entreprise ou régionaux, peuvent créer des listes de tâches et les publier dans des équipes spécifiques.<br>
    ![Capture d’écran de la publication de tâches](media/manage-tasks-app-publish.png)
- Les responsables des équipes de destinataires peuvent examiner les listes de tâches publiées et attribuer des tâches individuelles aux membres de l’équipe.<br>
    ![Capture d’écran de l’attribution d’une tâche](media/manage-tasks-app-assign.png)
- Les employés en ligne ont une expérience mobile simple pour voir les tâches qui leur sont affectées. Ils peuvent joindre des photos pour afficher leur travail le cas échéant et marquer leurs tâches comme terminées.
- Les éditeurs et responsables peuvent afficher les rapports pour afficher l’état d’affectation et d’achèvement des tâches à chaque niveau, y compris par emplacement (équipe), liste des tâches et tâche individuelle.<br>
    ![Capture d’écran des tâches affectées sur un appareil mobile](media/manage-tasks-app-reporting.png)

Les utilisateurs créent, gèrent et publient des listes des tâches sous l’onglet **Listes publiées** dans l’application Tâches. Cet onglet s’affiche uniquement pour un utilisateur si votre organisation [a](#set-up-your-team-targeting-hierarchy) mis en place une hiérarchie de ciblage d’équipe et que l’utilisateur fait partie d’une équipe incluse dans la hiérarchie. La hiérarchie détermine si l’utilisateur peut publier ou recevoir des listes de tâches et afficher les rapports pour les listes reçues.

### <a name="example-scenario"></a>Exemple de scénario

Voici un exemple du fonctionnement de la publication de tâches.

Contoso met en place une nouvelle promotion de livraison et de livraison de nourriture. Pour assurer une expérience de marque cohérente, ils doivent coordonner l’exécution cohérente du déploiement dans plus de 300 emplacements de magasin.

L’équipe marketing partage les détails de la promotion et la liste de tâches correspondante avec le Gestionnaire de communications commerciales. Le Gestionnaire de communications au détail, qui garde le contrôle des magasins, examine les informations, crée une liste de tâches pour la promotion, puis crée une tâche pour chaque unité de travail qui doit être effectuée par chacun des magasins concernés. Une fois la liste des tâches terminée, elle doit sélectionner les magasins qui doivent terminer le travail. Dans ce cas, la promotion s’applique uniquement aux magasins aux États-Unis qui ont un restaurant dans une boutique. Dans Tâches, elle filtre la liste du Store en fonction de l’attribut du restaurant dans le store, sélectionne les emplacements correspondants aux États-Unis dans la hiérarchie, puis publie la liste des tâches sur ces magasins.

Les responsables de magasin à chaque emplacement reçoivent une copie des tâches publiées et les affectent aux membres de leur équipe. Les responsables peuvent utiliser l’expérience tâches pour comprendre tout le travail requis dans leur magasin. Ils peuvent également utiliser les filtres disponibles pour se concentrer sur un ensemble de travail spécifique, par exemple le travail prévu aujourd’hui ou travailler dans un domaine particulier.

Les employés en ligne de chaque emplacement de magasin ont désormais une liste hiérarchisées de leur travail dans tâches sur leur appareil mobile. Lorsqu’ils terminent une tâche, ils la marquent comme terminée. Certains peuvent même choisir de charger et de joindre une photo à la tâche pour montrer leur travail.

Les sièges sociaux et les responsables intermédiaires de Contoso peuvent afficher les rapports pour afficher l’affectation et l’état d’achèvement des tâches dans chaque magasin et tous les magasins. Ils peuvent également descendre dans la détail à une tâche spécifique pour voir l’état au sein de différents magasins. À l’approche de la date de lancement, ils peuvent repérer les quelconques handicaps et faire le point avec leurs équipes selon les besoins. Cette visibilité permet à Contoso d’améliorer l’efficacité du déploiement et d’offrir une expérience plus cohérente sur leurs magasins.

### <a name="set-up-your-team-targeting-hierarchy"></a>Configurer la hiérarchie de ciblage d’équipe

Pour activer la publication de tâches dans votre organisation, vous devez d’abord configurer le schéma de ciblage d’équipe dans un . Fichier CSV. Le schéma définit comment toutes les équipes de votre hiérarchie sont liées entre elles et les attributs utilisés pour filtrer et sélectionner des équipes. Après avoir créé le schéma, téléchargez-le dans Teams pour l’appliquer à votre organisation. Les membres de l’équipe de publication, comme le Gestionnaire de communications au détail dans l’exemple de scénario, peuvent ensuite filtrer les équipes par hiérarchie, attributs ou combinaison des deux pour sélectionner les équipes concernées devant recevoir les listes de tâches, puis publier les listes de tâches dans ces équipes.

Pour savoir comment configurer la hiérarchie de ciblage d’équipe, voir Configurer la hiérarchie de [ciblage d’équipe.](set-up-your-team-hierarchy.md)

## <a name="power-automate-and-graph-api"></a>API Power Automate et Graph

Tâches prend en charge Power Automate pour To Do et les API Graph pour le Planificateur. Pour en savoir plus, reportez-vous à la rubrique :

- [Vue d’ensemble de l’API Tâches et plans du Planificateur](https://docs.microsoft.com/graph/planner-concept-overview)
- [Utilisation de Microsoft To Do avec Power Automate](https://support.office.com/article/using-microsoft-to-do-with-power-automate-526e8f75-217b-46e0-9e06-44780b72c295)

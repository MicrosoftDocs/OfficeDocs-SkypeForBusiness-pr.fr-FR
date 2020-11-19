---
title: Gérer l’application tâches pour votre organisation dans Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
audience: admin
description: Découvrez comment gérer l’application tâches pour les utilisateurs de votre organisation.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.openlocfilehash: 18af74a2a62f8282ee9b39c998db803235cc4ff0
ms.sourcegitcommit: 7966991c398cd80f6bd0bb21e57a6b2a97c09ea9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130495"
---
# <a name="manage-the-tasks-app-for-your-organization-in-microsoft-teams"></a>Gérer l’application tâches pour votre organisation dans Microsoft teams

## <a name="overview-of-tasks"></a>Vue d’ensemble des tâches

L’application tâches offre une interface de gestion des tâches cohésive à Microsoft Teams, intégrant les tâches individuelles mises en œuvre par [Microsoft pour](https://todo.microsoft.com/tasks/) les tâches effectuées par le planificateur au même endroit. Les utilisateurs peuvent accéder aux tâches en tant qu’application sur le côté gauche d’une équipe et en tant qu’onglet dans un canal au sein d’équipes individuelles. **Mes tâches** et **plans partagés** dans les tâches permettent aux utilisateurs d’afficher et de gérer toutes leurs tâches individuelles et d’équipe et de hiérarchiser leur travail. Le complément tâches est disponible dans les applications de bureau, Web et mobiles Teams. 

> [!NOTE]
> À mesure que nous déployons l’expérience de tâches sur les clients teams de bureau, le nom de l’application s’affichera initialement en tant que **planificateur** aux utilisateurs. Le nom sera alors provisoirement modifié **en tâches par Planner et à faire**, et par la suite, il sera renommé **tâches**. Pour les clients mobiles Teams, le nom de l’application s’affichera toujours en tant que **tâches**. La disponibilité de l’expérience mobile peut prendre un peu de temps après la disponibilité de l’expérience de bureau.

   ![Capture d’écran de l’affichage liste des tâches dans la liste d’équipes](media/manage-tasks-app-tasks.png)

Pour les organisations qui souhaitent rationaliser la gestion des tâches pour les travailleurs terrain, les tâches incluent également des fonctionnalités qui vous permettent de cibler, de publier et de suivre les tâches à la mise à l’échelle de votre personnel terrain. Par exemple, le leadership d’entreprise et régional peut créer et publier des listes de tâches ciblées sur des emplacements appropriés, par exemple des magasins de vente spécifiques, et effectuer le suivi de l’avancement par le biais de rapports en temps réel. Les responsables peuvent affecter des tâches à leur personnel et aux activités directes dans leurs lieux de travail, et les employés de terrain disposent d’une liste hiérarchisée des tâches qui leur sont affectées sur un appareil mobile ou de bureau. Pour activer la [publication de tâches](#task-publishing), vous devez commencer par définir une hiérarchie de ciblage d’équipe pour votre organisation, qui définit le rapport entre toutes les équipes de la hiérarchie.

## <a name="what-you-need-to-know-about-tasks"></a>Ce que vous devez savoir sur les tâches

Tâches est disponible en tant qu’application et en tant qu’onglet dans un canal. Gardez à l’esprit que l’application comprend des tâches individuelles de à faire et des tâches d’équipe du planificateur, alors que l’onglet n’affiche que les tâches d’équipe.

Avec les tâches, les utilisateurs bénéficient d’une expérience de bureau, Web ou mobile. Si les tâches sont installées sur le client de bureau Teams, les utilisateurs la verront également sur leurs clients de bureau et mobiles Teams. Exception : utilisateurs invités. Il est important de savoir que les invités peuvent uniquement accéder aux tâches en tant qu’application à partir du client mobile Teams. Les invités verront les onglets tâches sur le bureau et les clients Web Teams.

**Mes tâches** affiche les tâches individuelles d’un utilisateur. Les **plans partagés** indiquent les tâches sur lesquelles l’équipe entière travaille, ainsi que les listes de tâches ajoutées en tant qu’onglet tâches à un canal. Notez ce qui suit :

- Les listes de tâches créées par un utilisateur dans l’application tâches s’affichent également dans pour les clients de cet utilisateur. De la même façon, les listes de tâches qu’un utilisateur crée dans le **dossier** tâches s’affichent dans les tâches de l’utilisateur. Le même vrai pour chaque tâche.

- Tout onglet tâches qui est ajouté à un canal s’affichera également dans les clients Planner. Lorsqu’un utilisateur crée un plan dans Planner, le plan n’apparaît pas dans l’application tâches ou planificateur sauf s’il est ajouté en tant qu’onglet à un canal. Lorsqu’un utilisateur ajoute un nouvel onglet tâches, il peut créer une liste ou un plan ou en choisir un existant.

## <a name="set-up-tasks"></a>Configurer des tâches

> [!IMPORTANT]
> Les paramètres et les stratégies que vous avez configurés pour le planificateur s’appliquent également aux tâches.

### <a name="enable-or-disable-tasks-in-your-organization"></a>Activation ou désactivation de tâches au sein de votre organisation

L’option tâches est activée par défaut pour tous les utilisateurs d’équipes de votre organisation. Vous pouvez activer ou désactiver l’application au niveau de l’organisation sur la page [gérer les applications](manage-apps.md) dans le centre d’administration Microsoft Teams.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **teams**  >  **Manage** apps.
2. Dans la liste des applications, effectuez l’une des opérations suivantes :

    - Pour désactiver des tâches pour votre organisation, recherchez l’application tâches, sélectionnez-la, puis cliquez sur **bloquer**.
    - Pour activer les tâches pour votre organisation, recherchez l’application tâches, sélectionnez-la, puis cliquez sur **autoriser**.

> [!NOTE]
> Si vous ne trouvez pas l’application tâches, recherchez les noms dans la première note de cet article. Il est possible que l’application soit en cours de renommer.

### <a name="enable-or-disable-tasks-for-specific-users-in-your-organization"></a>Activation ou désactivation de tâches pour des utilisateurs spécifiques de votre organisation

Pour autoriser ou empêcher des utilisateurs spécifiques de votre organisation d’utiliser des tâches, assurez-vous que les tâches sont activées pour votre organisation dans la page [gérer les applications](manage-apps.md) , puis créez une stratégie d’autorisations d’application personnalisée et attribuez-la à ces utilisateurs. Pour en savoir plus, voir [gérer les stratégies d’autorisation d’applications dans Microsoft teams](teams-app-permission-policies.md).

### <a name="use-an-app-setup-policy-to-pin-tasks-to-teams"></a>Utiliser une stratégie de configuration d’application pour épingler des tâches à des équipes

Les stratégies de configuration des applications vous permettent de personnaliser teams afin de mettre en évidence les applications les plus importantes pour les utilisateurs de votre organisation. Les applications que vous définissez dans une stratégie sont épinglées à la barre de l’application &mdash; , qui se trouve sur le côté du client de bureau teams et dans la partie inférieure des clients mobiles Teams, &mdash; où les utilisateurs peuvent y accéder rapidement et facilement.

Pour épingler l’application tâches à vos utilisateurs, vous pouvez modifier la stratégie globale par défaut de l’organisation, ou créer et affecter une stratégie de configuration d’application personnalisée. Pour en savoir plus, voir [gérer les stratégies de configuration des applications dans Microsoft teams](teams-app-setup-policies.md).

### <a name="a-users-my-tasks-is-visible-if-the-user-is-licensed-for-exchange-online"></a>Les tâches d’un utilisateur s’affichent si l’utilisateur est titulaire d’une licence pour Exchange Online

Si vous ne voulez pas que l’utilisateur puisse voir **Mes tâches**, vous pouvez le masquer. Pour cela, [supprimez la licence Exchange Online de l’utilisateur](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users). Il est important de savoir qu’une fois que vous avez supprimé une licence Exchange Online, l’utilisateur n’a plus accès à la boîte aux lettres.  Les données de boîte aux lettres sont conservées pendant 30 jours, après quoi elles sont supprimées et ne peuvent pas être récupérées, sauf si la boîte aux lettres est placée [en conservation inaltérable ou en conservation pour litige](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds).

Nous déconseillons de le faire pour les travailleurs de l’information, mais dans certains cas, cela peut être le cas, par exemple pour les travailleurs terrain qui ne dépendent pas de la messagerie électronique.

## <a name="task-publishing"></a>Publication de tâches

La publication de tâches permet à votre organisation de publier des listes de tâches ciblées en fonction d’emplacements spécifiques (équipes) au sein de votre organisation afin de définir et de partager un plan de travail à utiliser à ces emplacements.

- Les membres de l’équipe de publication, tels que le leadership d’une entreprise ou d’une région, peuvent créer des listes de tâches et les publier dans des équipes spécifiques.<br>
    ![Capture d’écran de la publication de tâches](media/manage-tasks-app-publish.png)
- Les responsables des équipes du destinataire peuvent passer en revue les listes de tâches publiées et affecter des tâches individuelles aux membres de l’équipe.<br>
    ![Capture d’écran de l’affectation d’une tâche](media/manage-tasks-app-assign.png)
- Les travailleurs terrain ont une utilisation mobile simple pour afficher les tâches qui leur sont affectées. Ils peuvent joindre des photos pour montrer leur emploi le cas échéant et marquer leurs tâches comme terminées.
- Les éditeurs et responsables peuvent afficher des rapports permettant d’afficher le statut des affectations et de réussite des tâches à chaque niveau, y compris par emplacement (équipe), liste des tâches et tâche individuelle.<br>
    ![Capture d’écran de tâches attribuées sur un appareil mobile](media/manage-tasks-app-reporting.png)

Les utilisateurs peuvent créer, gérer et publier des listes de tâches dans l’onglet **listes publiées** de l’application tâches. Cet onglet ne s’affiche qu’aux utilisateurs si votre organisation a [configuré une hiérarchie de ciblage d’équipe](#set-up-your-team-targeting-hierarchy) et que l’utilisateur se trouve dans une équipe incluse dans la hiérarchie. La hiérarchie détermine si l’utilisateur peut publier ou recevoir des listes de tâches et afficher le rapport des listes reçues.

### <a name="example-scenario"></a>Exemple de scénario

Voici un exemple du fonctionnement de la publication de tâches.

Contoso est en déploiement d’une nouvelle promotion alimentaire takeout et de remise. Pour garantir une qualité de marque homogène, ils doivent coordonner l’exécution cohérente du déploiement sur plus de 300 emplacements de magasin.

L’équipe marketing partage les détails de la promotion et la liste des tâches correspondante avec le gestionnaire des communications commerciales. Le gestionnaire des communications commerciales, qui fait office de Gatekeeper pour les boutiques, examine les informations, crée une liste des tâches pour la promotion, puis crée une tâche pour chaque unité de travail à effectuer par chaque banque affectée. À la fin de la liste des tâches, elle doit sélectionner les magasins qui doivent terminer le travail. Dans le cas présent, la promotion s’applique uniquement aux magasins des États-Unis ayant un restaurant en magasin. Dans Tasks, elle filtre la liste du Windows Store en fonction de l’attribut de restaurant du magasin, sélectionne les emplacements des États-Unis dans la hiérarchie, puis publie la liste des tâches dans ces magasins.

Les responsables du magasin dans chaque emplacement reçoivent une copie des tâches publiées et attribuent celles-ci à leurs membres d’équipe. Les responsables peuvent utiliser l’interface de tâches pour comprendre tout le travail requis au sein de leur magasin. Ils peuvent également utiliser les filtres disponibles pour vous concentrer sur un ensemble spécifique de tâches, comme le fait de travailler à l’heure actuelle ou du travailler dans une zone spécifique.

Les employés de terrain à chaque emplacement du magasin disposent désormais d’une liste hiérarchisée de leur travail dans les tâches sur leur appareil mobile. Lorsque l’utilisateur termine une tâche, il la marque comme terminée. Certains pourront même choisir de télécharger et de joindre une photo à la tâche pour montrer leur travail.

Le siège social et les responsables intermédiaires de contoso peuvent afficher les rapports pour afficher l’état des affectations et de la réussite des tâches dans chaque banque et dans les magasins. Ils peuvent également descendre dans une tâche spécifique pour afficher l’État dans les différents magasins. Dans la mesure où la date de lancement est proche, les utilisateurs peuvent repérer les anomalies éventuelles et consulter leurs équipes selon leurs besoins. Cette visibilité permet à contoso d’améliorer l’efficacité du déploiement et d’offrir une plus grande homogénéité dans ses magasins.

### <a name="set-up-your-team-targeting-hierarchy"></a>Configurer la hiérarchie de ciblage de votre équipe

Pour activer la publication de tâches au sein de votre organisation, vous devez commencer par configurer le schéma de ciblage de votre équipe. Fichier. CSV. Le schéma définit le rapport entre toutes les équipes de votre hiérarchie et les attributs utilisés pour filtrer et sélectionner Teams. Après avoir créé le schéma, téléchargez-le dans teams pour l’appliquer à votre organisation. Les membres de l’équipe de publication, tels que le gestionnaire des communications commerciales dans l’exemple de scénario, peuvent filtrer les équipes par hiérarchie, attributs ou une combinaison des deux pour sélectionner les équipes appropriées qui recevront les listes des tâches, puis publier les listes de tâches dans ces équipes.

Pour connaître la procédure de configuration de votre hiérarchie de ciblage d’équipe, voir [configurer la hiérarchie de ciblage de votre équipe](set-up-your-team-hierarchy.md).

## <a name="power-automate-and-graph-api"></a>Automate et API graphique

Les tâches prennent en charge la mise à l’arrêt des API dans le planificateur. Pour en savoir plus, reportez-vous à la rubrique :

- [Présentation des API tâches et plans du planificateur](https://docs.microsoft.com/graph/planner-concept-overview)
- [Utiliser Microsoft pour effectuer des opérations d’automate](https://support.office.com/article/using-microsoft-to-do-with-power-automate-526e8f75-217b-46e0-9e06-44780b72c295)

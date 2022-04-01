---
title: Utiliser l’Assistant Connecteur Shifts pour connecter Shifts à Blue Yonder Workforce Management
author: lanachin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment utiliser l’Assistant Connecteur Shifts pour intégrer Shifts dans Teams blue Yonder Workforce Management.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4041b0909a3c5e8f1aa256fd2ec662030548343c
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593666"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-blue-yonder-workforce-management"></a>Utiliser l’Assistant Connecteur Shifts pour connecter Shifts à Blue Yonder Workforce Management

## <a name="overview"></a>Vue d’ensemble

L’Assistant Connecteur Shifts du Centre d'administration Microsoft 365 vous permet d’intégrer l’application Shifts dans Microsoft Teams à votre système de gestion du personnel (WFM). Une fois que vous avez établi une connexion, vos employés en contact direct peuvent consulter et gérer leurs plannings en toute transparence dans votre système WFM à partir de Shifts.

L’Assistant configure le connecteur Shifts, crée une connexion à votre système WFM et applique les paramètres de synchronisation et mappages d’équipe de votre choix. Les paramètres de synchronisation déterminent les informations de planification synchronisées entre votre système WFM et Shifts. Les mappages d’équipe définissent la relation de synchronisation entre vos sites WFM et vos équipes dans Teams. Vous pouvez faire une carte vers des équipes existantes et de nouvelles équipes.

Vous pouvez configurer plusieurs connexions, chacune avec des paramètres de synchronisation différents. Par exemple, si votre organisation possède plusieurs emplacements avec des exigences de planification différentes, créez une connexion avec des paramètres de synchronisation uniques pour chaque emplacement. N’oubliez pas qu’un site WFM ne peut être mappé qu’à une équipe à un moment donné. Si un site WFM est déjà mappé à une équipe, il ne peut pas être mappé vers une autre équipe.

Avec votre système WFM comme système de enregistrement, vos employés en ligne peuvent consulter et échanger des shifts, gérer leur disponibilité et demander un congé dans Shifts sur leurs appareils. Les responsables en ligne peuvent continuer à utiliser votre système WFM pour définir des plannings.

## <a name="integrate-shifts-with-blue-yonder-workforce-management"></a>Intégrer Shifts à Blue Yonder Workforce Management

Actuellement, l’Assistant prend en [charge le Microsoft Teams Shifts pour Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder). Ce connecteur vous permet d’intégrer Shifts à Blue Yonder Workforce Management (Blue Yonder WFM) pour gérer vos plannings et les tenir à jour. Dans cet article, nous vous explique comment exécuter l’Assistant pour configurer une connexion à Blue Yonder WFM via le connecteur.

> [!NOTE]
> Vous pouvez également utiliser PowerShell pour intégrer Shifts à Blue Yonder WFM. Pour en savoir plus, [voir Utiliser PowerShell pour connecter Shifts à Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md).

## <a name="before-you-begin"></a>Avant de commencer

Vous devez être un Microsoft 365 administrateur global pour exécuter l’Assistant.

### <a name="prerequisites"></a>Conditions préalables
<a name="prerequisites"> </a>
[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

- Les équipes que vous voulez ma carte n’ont aucun planning. Si une équipe dispose d’un [planning existant,](#remove-schedules-from-teams-you-want-to-map) supprimez-le avant de ma mapnder un site Blue Yonder WFM vers celui-ci. Dans le cas contraire, vous verrez des shifts en double.

## <a name="remove-schedules-from-teams-you-want-to-map"></a>Supprimer les plannings des équipes que vous souhaitez ma carte
<a name="remove_schedules"> </a>

> [!NOTE]
> Terminez cette étape si vous mappagez des sites Blue Yonder WFM avec des équipes existantes qui ont des plannings. Si vous mappage à des équipes qui n’ont aucun planning ou si vous créez des équipes vers qui établir le mappage, vous pouvez ignorer cette étape.

Utilisez PowerShell pour supprimer des plannings d’équipes.

1. Tout d’abord, vous devez installer les modules PowerShell et le configurer. Suivez les étapes de [configurer votre environnement](shifts-connector-powershell-manage.md#set-up-your-environment).
1. Exécutez la commande suivante :

    ```powershell
    Remove-CsTeamsShiftsScheduleRecord -TeamId <Teams team ID> -DateRangeStartDate <start time> -DateRangeEndDate <end time> -ClearSchedulingGroup:$false -EntityType <the scenario entities that you want to remove, the format is @(scenario1, scenario2, ...)> -DesignatedActorId <Teams team owner ID>
    ```

    Pour obtenir la liste des scénarios pour le `EntityType` paramètre, exécutez [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps). Les données de planification sont supprimées pour la plage de dates et d’heures que vous spécifiez.

Pour en savoir plus, [voir Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps).

## <a name="run-the-wizard"></a>Exécuter l’Assistant

### <a name="get-started"></a>Prise en main

1. Dans le volet de navigation gauche du [Centre d'administration Microsoft 365](https://admin.microsoft.com/), **sélectionnez Configuration**, puis allez à la section **Applications et courrier** électronique.
1. Sélectionnez **Connecter votre système de gestion du personnel**. Ici, vous pouvez en savoir plus sur les connecteurs Shifts, ainsi que l’expérience des employés et responsables en première ligne lorsque vous connectez Shifts à votre système WFM.
    :::image type="content" source="../../media/shifts-connector-wizard-get-started.png" alt-text="Capture d’écran de la page de détails de l’Assistant Connecteur Shifts du Centre d'administration Microsoft 365." lightbox="../../media/shifts-connector-wizard-get-started.png":::
1. Lorsque vous êtes prêt, sélectionnez **Démarrage**.
1. **Sélectionnez Suivant** pour créer une connexion Blue Yonder WFM.

### <a name="enter-connection-details"></a>Entrer les détails de la connexion
<a name="connection_details"> </a>

1. Dans la page Détails de la connexion, donnez un nom unique à votre connexion. Il ne peut pas faire plus de 128 caractères ou avoir des caractères spéciaux.
    :::image type="content" source="../../media/shifts-connector-wizard-connection-details.png" alt-text="Capture d’écran de la page Détails de la connexion de l’Assistant, affichant les paramètres de connexion." lightbox="../../media/shifts-connector-wizard-connection-details.png":::
1. Entrez le nom et le mot de passe de votre compte de service Blue Yonder WFM, ainsi que les URL de service.
1. Lorsque vous avez terminé, sélectionnez **Suivant** pour tester la connexion avec les paramètres que vous avez entrés.

### <a name="choose-sync-settings"></a>Choisir les paramètres de synchronisation
<a name="sync"> </a>

Dans la page Paramètres de synchronisation, vous choisissez les informations à synchroniser de Blue Yonder WFM à Shifts, la fréquence de synchronisation, et indiquez si les utilisateurs de Shifts peuvent apporter des modifications aux données.

1. Entrez votre Microsoft 365 système de sécurité.
    :::image type="content" source="../../media/shifts-connector-wizard-sync-settings.png" alt-text="Capture d’écran de la page Des paramètres de synchronisation de l’Assistant, affichant les paramètres de synchronisation." lightbox="../../media/shifts-connector-wizard-sync-settings.png":::
<a name="email"> </a>
1. Sous **Notification par courrier électronique, sélectionnez** les destinataires des notifications par courrier électronique concernant cette connexion. Vous pouvez ajouter des utilisateurs et groupes individuels. Les notifications par courrier électronique contiennent des informations sur l’état de configuration de la connexion et des problèmes ou erreurs qui peuvent se produire une fois la connexion configurée.
1. Choisissez vos paramètres de synchronisation :
    1. Sous **Planning et shifts**, sélectionnez les données Blue Yonder WFM que les utilisateurs Shifts peuvent voir ou modifier, puis définissez la fréquence de synchronisation.
    2. Sous **Demandes**, choisissez les types de demandes que les utilisateurs de Shifts peuvent voir et créer.

    > [!IMPORTANT]
    > Si vous avez choisi l’une des options suivantes pour désactiver les shifts ouverts, les demandes de shift ouvertes, les demandes d’échange ou les demandes de congé, il existe une autre étape que vous devez faire pour masquer la fonctionnalité dans Shifts.
    >
    > - Shifts ouverts : **Les utilisateurs de Shifts ne voient pas les données Blue Yonder WFM**
    > - Demandes d’échange **: La fonctionnalité est désactivée pour tous les utilisateurs**
    > - Demandes de congé : **La fonctionnalité est désactivée pour tous les utilisateurs**
    >
    > Après avoir exécuté l’Assistant, veillez à suivre les étapes de la section Désactiver les [shifts ouverts,](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) ouvrir les demandes de shift, les demandes d’échange et les demandes de congé plus loin dans cet article.
 
1. Une fois vos paramètres sélectionnés, sélectionnez **Créer une connexion**.

### <a name="map-blue-yonder-workforce-management-sites-to-teams"></a>Ma carte de sites blue Yonder Workforce Management vers des équipes
<a name="sites"> </a>

Choisissez les sites Blue Yonder WFM que vous voulez connecter à Shifts. Vous pouvez sélectionner jusqu’à 100 sites.

:::image type="content" source="../../media/shifts-connector-wizard-sites.png" alt-text="Capture d’écran de l’Assistant affichant la liste des sites Blue Yonder WFM" lightbox="../../media/shifts-connector-wizard-sites.png":::
<a name="mapping"> </a>
<a name="search_teams"> </a> Ensuite, mapmez chaque site Blue Yonder WFM que vous avez sélectionné à une équipe dans Teams. Vous pouvez ma carter un site à une équipe existante ou créer une équipe.
:::image type="content" source="../../media/shifts-connector-wizard-search-team.png" alt-text="Capture d’écran du volet montrant l’option d’équipe de recherche et créer une option d’équipe." lightbox="../../media/shifts-connector-wizard-search-team.png":::
#### <a name="to-map-a-site-to-an-existing-team"></a>Pour ma carter un site à une équipe existante

1. Sélectionnez le nom du site.
2. Dans le volet, recherchez l’équipe, puis sélectionnez-la. N’oubliez pas que les équipes déjà mappées sur un site dans cette connexion n’ont pas été présentes dans la recherche.
3. Choisissez le fuseau horaire et la ville la plus proche.
4. **Sélectionnez Enregistrer**, puis **Suivant**.

#### <a name="to-map-a-site-to-a-new-team"></a>Pour ma carte d’un site à une nouvelle équipe

1. Sélectionnez le nom du site.
2. Dans le volet, **sélectionnez Créer une équipe**. Vous serez alors placé dans un nouvel onglet dans votre navigateur, où vous pourrez créer une équipe dans le Centre d'administration Microsoft 365.
    1. Entrez un nom et une description facultative pour l’équipe.
    1. Ajoutez un ou plusieurs propriétaires d’équipe. Assurez-vous d’ajouter le Microsoft 365 système en tant que propriétaire.
    1. Ajoutez des membres d’équipe.
    1. Ajoutez une adresse e-mail d’équipe et choisissez un paramètre de confidentialité.
    1. Examinez vos paramètres, puis sélectionnez **Ajouter une équipe**. Une fois votre équipe créée, sélectionnez **Fermer**.
3. Retour l’Assistant, recherchez et sélectionnez la nouvelle équipe que vous avez créée.
4. Choisissez le fuseau horaire et la ville la plus proche.
5. **Sélectionnez Enregistrer**, puis **Suivant**.

### <a name="review-and-finish"></a>Révision et fin

Examinez vos paramètres. Si vous devez apporter des modifications à des mappages d’équipe, **sélectionnez Modifier** pour le faire. Lorsque vous êtes prêt, sélectionnez **Terminer**.

:::image type="content" source="../../media/shifts-connector-wizard-review.png" alt-text="Capture d’écran de la page Révision de l’Assistant, montrant des mappages." lightbox="../../media/shifts-connector-wizard-review.png":::

Vous verrez un message confirmant la réception de votre demande, ainsi qu’un ID d’opération. Notez l’ID d’opération. Vous en aurez besoin pour vérifier l’état de configuration de votre connexion.

:::image type="content" source="../../media/shifts-connector-wizard-operation-id.png" alt-text="Capture d’écran de la page de l’Assistant, affichant un message de confirmation et l’ID d’opération." lightbox="../../media/shifts-connector-wizard-operation-id.png":::

L’Assistant démarre le processus de configurer la connexion et de ma carte des sites aux équipes que vous avez sélectionnées. La finalisation de ce processus peut prendre un certain temps. Les destinataires que vous avez choisis recevront des notifications par courrier électronique sur l’état de configuration.

**Sélectionnez Terminé** pour quitter l’Assistant.

Vous êtes en route, mais ce n’est pas encore fait ! Assurez-vous de consulter votre courrier électronique. Vous recevrez une confirmation de réception de votre demande ainsi qu’un [](shifts-connector-powershell-manage.md#check-connection-setup-status) lien vers la vérification de l’état d’installation.

> [!NOTE]
> Si un problème ou une erreur se produit dans une connexion après qu’elle est définie, vous êtes averti par courrier électronique. Suivez les instructions dans l’e-mail pour résoudre le problème.

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Désactiver les shifts ouverts, les demandes de shift ouvertes, les demandes d’échange et les demandes de congé

> [!IMPORTANT]
> Suivez ces étapes uniquement si vous avez choisi l’une des options suivantes pour désactiver les shifts ouverts, les demandes de shift ouvertes, les demandes d’échange ou les demandes de congé dans l’Assistant. L’exécution de cette étape masque la fonctionnalité dans Shifts.
>
> - Shifts ouverts : **Les utilisateurs de Shifts ne voient pas les données Blue Yonder WFM**
> - Demandes d’échange **: La fonctionnalité est désactivée pour tous les utilisateurs**
> - Demandes de congé : **La fonctionnalité est désactivée pour tous les utilisateurs**
>
> Sans cette deuxième étape, les utilisateurs continueront de voir la fonctionnalité dans Shifts et un message d’erreur « Opération non pris en place » s’ils essaient de l’utiliser.

Pour masquer les shifts, demandes d’échange et de congé ouverts dans Shifts, utilisez le type de ressource API Graph [Schedule](/graph/api/resources/schedule?view=graph-rest-1.0) pour définir les paramètres suivants ```false``` pour chaque équipe mappée vers un site Blue Yonder WFM :

- Shifts ouverts : ```openShiftsEnabled```
- Demandes d’échange :  ```swapShiftsRequestsEnabled```
- Demandes de congé : ```timeOffRequestsEnabled```

Pour masquer les demandes de shifts ouverts dans Shifts,  Paramètres dans Shifts, puis désactiver le paramètre **Ouvrir les shifts**.

## <a name="if-you-need-to-make-changes-to-a-connection"></a>Si vous devez apporter des modifications à une connexion
<a name="update_connection"> </a>

Une fois qu’une connexion est définie, vous utilisez PowerShell pour y apporter des modifications. Par exemple, vous pouvez mettre à jour les paramètres de synchronisation, les mappages d’équipe et désactiver la synchronisation pour une connexion. Pour obtenir une aide étape par étape, voir Utiliser PowerShell pour gérer votre connexion [Shifts à Blue Yonder Workforce Management](shifts-connector-powershell-manage.md).

## <a name="related-articles"></a>Articles connexes

- [Connecteurs Shifts](shifts-connectors.md)
- [Utiliser PowerShell pour gérer votre connexion Shifts à Blue Yonder Workforce Management](shifts-connector-powershell-manage.md)
- [Gérer l’application Shifts dans Teams](manage-the-shifts-app-for-your-organization-in-teams.md)

---
title: Utilisez l’Assistant Connecteur Shifts pour connecter Shifts à Blue Yonder Workforce Management
author: lanachin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment utiliser l’Assistant Connecteur Shifts pour intégrer Shifts dans Teams à Blue Yonder Workforce Management.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: de511df118e1c5e6d62e0bed8cd076a7481b3407
ms.sourcegitcommit: 90f03a841f8ca33092dce65c543357c7c2f7b82a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2022
ms.locfileid: "66647808"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-blue-yonder-workforce-management"></a>Utilisez l’Assistant Connecteur Shifts pour connecter Shifts à Blue Yonder Workforce Management

## <a name="overview"></a>Présentation

L’Assistant Connecteur Shifts dans le Centre d'administration Microsoft 365 vous permet d’intégrer l’application Shifts dans Microsoft Teams à votre système de gestion du personnel (WFM). Après avoir configuré une connexion, vos employés de première ligne peuvent afficher et gérer en toute transparence leurs planifications dans votre système WFM à partir de Shifts.

L’Assistant configure le connecteur Shifts, crée une connexion à votre système WFM et applique les paramètres de synchronisation et les mappages d’équipe que vous choisissez. Les paramètres de synchronisation déterminent les informations de planification synchronisées entre votre système WFM et Shifts. Les mappages d’équipe définissent la relation de synchronisation entre vos instances WFM et les équipes dans Teams. Vous pouvez mapper aux équipes existantes et aux nouvelles équipes.

Vous pouvez configurer plusieurs connexions, chacune avec des paramètres de synchronisation différents. Par exemple, si votre organisation a plusieurs emplacements avec des exigences de planification différentes, créez une connexion avec des paramètres de synchronisation uniques pour chaque emplacement. N’oubliez pas qu’une instance de WFM ne peut être mappée qu’à une seule équipe à un moment donné. Si une instance WFM est déjà mappée à une équipe, elle ne peut pas être mappée à une autre équipe.

Avec votre système WFM comme système d’enregistrement, vos employés de première ligne peuvent voir et échanger des shifts, gérer leur disponibilité et demander des congés dans shifts sur leurs appareils. Les responsables de première ligne peuvent continuer à utiliser votre système WFM pour configurer des planifications.

## <a name="integrate-shifts-with-blue-yonder-workforce-management"></a>Intégrer Shifts à Blue Yonder Workforce Management

Actuellement, l’Assistant prend en charge le [connecteur Microsoft Teams Shifts pour Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder). Ce connecteur vous permet d’intégrer Shifts à Blue Yonder Workforce Management (Blue Yonder WFM) pour gérer vos planifications et les tenir à jour. Dans cet article, nous vous présentons comment exécuter l’Assistant pour configurer une connexion à Blue Yonder WFM via le connecteur.

> [!NOTE]
> Vous pouvez également utiliser PowerShell pour intégrer Shifts à Blue Yonder WFM. Pour plus d’informations, consultez [Utiliser PowerShell pour connecter Shifts à Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md).

## <a name="before-you-begin"></a>Avant de commencer

Vous devez être administrateur général de Microsoft 365 pour exécuter l’Assistant.

### <a name="prerequisites"></a>Conditions préalables
<a name="prerequisites"> </a>
[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

- Les équipes que vous souhaitez mapper n’ont pas de planification. Si une équipe a une planification existante, [supprimez-la de l’équipe](#remove-schedules-from-teams-you-want-to-map) avant d’y mapper une instance blue Yonder WFM. Sinon, vous verrez des décalages en double.

## <a name="remove-schedules-from-teams-you-want-to-map"></a>Supprimer les planifications des équipes que vous souhaitez mapper
<a name="remove_schedules"> </a>

> [!NOTE]
> Effectuez cette étape si vous mappez blue Yonder WFM instances aux équipes existantes qui ont des planifications. Si vous mappez à des équipes qui n’ont pas de planification ou si vous créez de nouvelles équipes à mapper, vous pouvez ignorer cette étape.

Utilisez PowerShell pour supprimer des planifications des équipes.

1. Tout d’abord, vous devez installer les modules PowerShell et être configuré. Suivez les étapes pour [configurer votre environnement](shifts-connector-powershell-manage.md#set-up-your-environment).
1. Exécutez la commande suivante :

    ```powershell
    Remove-CsTeamsShiftsScheduleRecord -TeamId <Teams team ID> -DateRangeStartDate <start time> -DateRangeEndDate <end time> -ClearSchedulingGroup:$false -EntityType <the scenario entities that you want to remove, the format is @(scenario1, scenario2, ...)> -DesignatedActorId <Teams team owner ID>
    ```

    Pour obtenir la liste des scénarios du `EntityType` paramètre, [exécutez Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector). Les données de planification seront supprimées pour l’intervalle de date et d’heure que vous spécifiez.

Pour plus d’informations, consultez [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord).

## <a name="run-the-wizard"></a>Exécuter l’Assistant

### <a name="get-started"></a>Prise en main

1. Dans le volet de navigation gauche de [l’Centre d'administration Microsoft 365](https://admin.microsoft.com/), choisissez **Configurer**, puis accédez à la section **Applications et e-mail**.
1. Sélectionnez **Connecter votre système de gestion des effectifs**. Ici, vous pouvez en savoir plus sur les connecteurs Shifts et l’expérience de travail et de gestionnaire de première ligne lorsque vous connectez Shifts à votre système WFM.
    :::image type="content" source="../../media/shifts-connector-wizard-get-started.png" alt-text="Capture d’écran de la page de détails de l’Assistant Connecteur Shifts dans le Centre d'administration Microsoft 365." lightbox="../../media/shifts-connector-wizard-get-started.png":::
1. Lorsque vous êtes prêt, **sélectionnez Prise en main**.
1. Sélectionnez **Suivant** pour créer une connexion blue Yonder WFM.

### <a name="enter-connection-details"></a>Entrer les détails de la connexion
<a name="connection_details"> </a>

1. Dans la page Détails de la connexion, donnez un nom unique à votre connexion. Il ne peut pas dépasser 128 caractères ou comporter des caractères spéciaux.
    :::image type="content" source="../../media/shifts-connector-wizard-connection-details.png" alt-text="Capture d’écran de la page Détails de la connexion de l’Assistant, montrant les paramètres de connexion." lightbox="../../media/shifts-connector-wizard-connection-details.png":::
1. Entrez le nom de votre compte de service blue Yonder WFM ainsi que le mot de passe et les URL de service.
1. Lorsque vous avez terminé, sélectionnez **Suivant** pour tester la connexion avec les paramètres que vous avez entrés.

### <a name="choose-sync-settings"></a>Choisir les paramètres de synchronisation
<a name="sync"> </a>

Dans la page Paramètres de synchronisation, vous choisissez les informations à synchroniser de Blue Yonder WFM à Shifts, la fréquence de synchronisation et indiquez si les utilisateurs de Shifts peuvent apporter des modifications aux données.

1. Entrez votre compte système Microsoft 365.
    :::image type="content" source="../../media/shifts-connector-wizard-sync-settings.png" alt-text="Capture d’écran de la page Paramètres de synchronisation de l’Assistant, montrant les paramètres de synchronisation." lightbox="../../media/shifts-connector-wizard-sync-settings.png":::
<a name="email"> </a>
1. Sous **Destinataires de notification par e-mail**, choisissez qui reçoit les notifications par e-mail concernant cette connexion. Vous pouvez ajouter des utilisateurs et des groupes individuels. Les notifications par e-mail contiennent des informations sur l’état de l’installation de la connexion et les éventuels problèmes ou erreurs qui peuvent se produire après la configuration de la connexion.
1. Choisissez vos paramètres de synchronisation :
    1. Sous **Planification et décalages**, choisissez les données blue Yonder WFM que les utilisateurs de Shifts peuvent voir ou modifier, puis définissez la fréquence de synchronisation.
    2. Sous **Demandes**, choisissez les types de demandes que les utilisateurs Shifts peuvent voir et créer.

    > [!IMPORTANT]
    > Si vous avez choisi l’une des options suivantes pour désactiver les décalages ouverts, les demandes de décalage ouvertes, les demandes d’échange ou les demandes de congé, vous devez effectuer une autre étape pour masquer la fonctionnalité dans Shifts.
    >
    > - Ouvrir les shifts : **les utilisateurs de shifts ne verront pas les données blue Yonder WFM**
    > - Demandes **d’échange : la fonctionnalité est désactivée pour tous les utilisateurs**
    > - Demandes de congé : **la fonctionnalité est désactivée pour tous les utilisateurs**
    >
    > Après avoir exécuté l’Assistant, veillez à suivre les [étapes décrites dans la section Désactiver les décalages ouverts, ouvrir les demandes de décalage, les demandes d’échange et les demandes de congé](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) plus loin dans cet article.
 
1. Lorsque vous avez terminé de choisir vos paramètres, sélectionnez **Créer une connexion**.

### <a name="map-blue-yonder-workforce-management-instances-to-teams"></a>Mapper des instances blue Yonder Workforce Management à des équipes
<a name="sites"> </a>

Choisissez les instances blue Yonder WFM que vous souhaitez connecter à Shifts, puis mappez chaque instance à une équipe dans Teams. Vous pouvez mapper jusqu’à 100 instances. Il existe deux façons de procéder :

- [Mapper manuellement des instances à des équipes](#manually-map-instances-to-teams)
- [Préparer et charger un fichier CSV qui définit vos mappages](#use-a-csv-file-to-map-instances-to-teams)

#### <a name="manually-map-instances-to-teams"></a>Mapper manuellement des instances à des équipes

Sélectionnez les instances que vous souhaitez mapper.

:::image type="content" source="../../media/shifts-connector-wizard-sites.png" alt-text="Capture d’écran de l’Assistant, montrant la liste des instances blue Yonder WFM." lightbox="../../media/shifts-connector-wizard-sites.png":::
<a name="mapping"> </a>
<a name="search_teams"> </a> Ensuite, mappez chaque instance à une équipe dans Teams. Vous pouvez mapper une instance à une équipe existante ou créer une équipe.
:::image type="content" source="../../media/shifts-connector-wizard-search-team.png" alt-text="Capture d’écran du volet montrant l’option d’équipe de recherche et créer une option d’équipe." lightbox="../../media/shifts-connector-wizard-search-team.png":::

##### <a name="to-map-an-instance-to-an-existing-team"></a>Pour mapper une instance à une équipe existante

1. Sélectionnez le nom de l’instance.
2. Dans le volet, recherchez l’équipe, puis sélectionnez-la. Gardez à l’esprit que les équipes qui sont déjà mappées à une instance de cette connexion ne s’affichent pas dans la recherche.
3. Choisissez le fuseau horaire et la ville la plus proche.
4. Sélectionnez **Enregistrer**, puis **Suivant**.

##### <a name="to-map-an-instance-to-a-new-team"></a>Pour mapper une instance à une nouvelle équipe

1. Sélectionnez le nom de l’instance.
2. Dans le volet, choisissez **Créer une équipe**. Vous accédez à un nouvel onglet dans votre navigateur, où vous pouvez créer une équipe dans le Centre d'administration Microsoft 365.
    1. Entrez un nom et une description facultative pour l’équipe.
    1. Ajoutez un ou plusieurs propriétaires d’équipe. Veillez à ajouter le compte système Microsoft 365 en tant que propriétaire.
    1. Ajoutez des membres de l’équipe.
    1. Ajoutez une adresse e-mail d’équipe et choisissez un paramètre de confidentialité.
    1. Passez en revue vos paramètres, puis **choisissez Ajouter une équipe**. Lorsque votre équipe est créée, choisissez **Fermer**.
3. Retour à l’Assistant, recherchez, puis sélectionnez la nouvelle équipe que vous avez créée.
4. Choisissez le fuseau horaire et la ville la plus proche.
5. Sélectionnez **Enregistrer**, puis **Suivant**.

#### <a name="use-a-csv-file-to-map-instances-to-teams"></a>Utiliser un fichier CSV pour mapper des instances à des équipes

1. Sélectionnez **passer en mode en bloc**.
1. Sélectionnez **télécharger un fichier de modèle** pour télécharger un modèle de mappage que vous pouvez utiliser pour définir vos mappages.

    :::image type="content" source="../../media/shifts-connector-wizard-mapping-file.png" alt-text="Capture d’écran de la page Charger le fichier de mappage de l’Assistant." lightbox="../../media/shifts-connector-wizard-mapping-file.png":::

1. Utilisez le modèle pour créer votre fichier de mappage. Il contient ces colonnes, dans l’ordre suivant, en commençant par la première colonne. Un astérisque (*) indique une colonne obligatoire.

    |Nom de colonne  |Description  |
    |---------|---------|
    |**ID d’instance Blue Yonder*** |ID d’instance blue Yonder WFM.|
    |**Nom de l’instance Blue Yonder**|Nom de l’instance blue Yonder WFM.|
    |**ID d’équipe*** |ID d’équipe.|
    |**Nom de l’équipe**|Nom de l’équipe.|
    |**Fuseau horaire*** |Fuseau horaire au format de base de données tz. Par exemple, Europe/Londres.|

    > [!NOTE]
    > Vous devez uniquement remplir les colonnes requises (ID d’instance Blue Yonder, ID d’équipe, fuseau horaire) pour mapper des instances à des équipes.

    Voici un exemple de ce à quoi ressemble un fichier de mappage.

    |ID d’instance Blue Yonder|Nom de l’instance Blue Yonder|ID d’équipe|Nom de l’équipe|Fuseau horaire|
    |---------|---------|---------|---------|---------|
    |2111|Contoso US Team|3a4d78a-2261|Équipe des États-Unis|Amérique/Los_Angeles|
    |3212|Contoso UK Team|2d1f6c2e-5272|Équipe du Royaume-Uni|Europe/Londres|
    |4865||bfa6o89e-1328||Amérique/Toronto|

1. Une fois que vous avez créé votre fichier de mappage, **sélectionnez Parcourir** pour le charger. L’Assistant valide votre fichier. S’il détecte des erreurs, vous verrez une liste des erreurs et un message vous demandant de les corriger. Sinon, vous verrez un message pour passer à l’étape suivante.  
1. Sélectionnez **Suivant**.

### <a name="review-and-finish"></a>Vérifier et terminer

Passez en revue vos paramètres. Si vous devez apporter des modifications aux mappages d’équipe, **choisissez Modifier** pour ce faire. Lorsque vous êtes prêt, sélectionnez **Terminer**.

:::image type="content" source="../../media/shifts-connector-wizard-review.png" alt-text="Capture d’écran de la page Révision de l’Assistant, montrant les mappages." lightbox="../../media/shifts-connector-wizard-review.png":::

Vous verrez un message pour confirmer que nous avons reçu votre demande ainsi qu’un ID d’opération. Notez l’ID d’opération. Vous en aurez besoin pour vérifier l’état d’installation de votre connexion.

:::image type="content" source="../../media/shifts-connector-wizard-operation-id.png" alt-text="Capture d’écran de la page de l’Assistant, montrant le message de confirmation et l’ID d’opération." lightbox="../../media/shifts-connector-wizard-operation-id.png":::

L’Assistant démarre le processus pour configurer la connexion et mapper les instances aux équipes que vous avez sélectionnées. Ce processus peut prendre un certain temps. Les destinataires que vous avez choisis recevront des notifications par e-mail sur l’état de l’installation.

Sélectionnez **Terminé** pour quitter l’Assistant.

Vous êtes sur votre chemin, mais vous n’avez pas encore terminé! Veillez à vérifier votre adresse e-mail. Vous recevrez une confirmation que nous avons reçu votre demande, ainsi qu’un [lien](shifts-connector-powershell-manage.md#check-connection-setup-status) vers la façon dont vous pouvez vérifier l’état de l’installation.

> [!NOTE]
> Si un problème ou une erreur se produit dans une connexion après sa configuration, vous êtes averti par e-mail. Suivez les instructions de l’e-mail pour résoudre le problème.

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Désactiver les décalages ouverts, les demandes de décalage ouvertes, les demandes d’échange et les demandes de congé

> [!IMPORTANT]
> Suivez ces étapes uniquement si vous avez choisi l’une des options suivantes pour désactiver les décalages ouverts, les demandes de décalage ouvertes, les demandes d’échange ou les demandes de congé dans l’Assistant. L’exécution de cette étape masque la fonctionnalité dans Shifts.
>
> - Ouvrir les shifts : **les utilisateurs de shifts ne verront pas les données blue Yonder WFM**
> - Demandes **d’échange : la fonctionnalité est désactivée pour tous les utilisateurs**
> - Demandes de congé : **la fonctionnalité est désactivée pour tous les utilisateurs**
>
> Sans cette deuxième étape, les utilisateurs verront toujours la fonctionnalité dans Shifts et recevront un message d’erreur « opération non prise en charge » s’ils essaient de l’utiliser.

Pour masquer les décalages ouverts, les demandes d’échange et les demandes de congé dans Shifts, utilisez le [type de ressource de planification](/graph/api/resources/schedule) API Graph pour définir les paramètres suivants ```false``` pour chaque équipe que vous avez mappée à une instance de WFM Blue Yonder :

- Ouvrir les décalages : ```openShiftsEnabled```
- Demandes d’échange :  ```swapShiftsRequestsEnabled```
- Demandes de congé : ```timeOffRequestsEnabled```

Pour masquer les demandes de décalages ouverts dans Shifts, accédez à **Paramètres** dans Shifts, puis désactivez le paramètre **Ouvrir les décalages** .

## <a name="if-you-need-to-make-changes-to-a-connection"></a>Si vous devez apporter des modifications à une connexion
<a name="update_connection"> </a>

Une fois qu’une connexion est configurée, vous utilisez PowerShell pour y apporter des modifications. Par exemple, vous pouvez mettre à jour les paramètres de synchronisation, les mappages d’équipe et désactiver la synchronisation pour une connexion. Pour obtenir des conseils pas à pas, consultez [Utiliser PowerShell pour gérer votre connexion Shifts à Blue Yonder Workforce Management](shifts-connector-powershell-manage.md).

## <a name="related-articles"></a>Articles connexes

- [Majs connecteurs](shifts-connectors.md)
- [Utilisez PowerShell pour gérer votre connexion Shifts à Blue Yonder Workforce Management](shifts-connector-powershell-manage.md)
- [Gérer l’application Shifts dans Teams](manage-the-shifts-app-for-your-organization-in-teams.md)

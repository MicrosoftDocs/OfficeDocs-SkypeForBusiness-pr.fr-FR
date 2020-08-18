---
title: Gérer les balises dans Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: acolonna, salu
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Apprenez à gérer l’utilisation des indicateurs au sein de votre organisation dans Microsoft Teams.
ms.openlocfilehash: b285cd4348894007d1e487a0788f82c9c8821d43
ms.sourcegitcommit: 27fb021e46d775652a99d862b19d94f3fc020594
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778076"
---
# <a name="manage-tags-in-microsoft-teams"></a>Gérer les balises dans Microsoft teams

> [!NOTE]
> L’une des fonctionnalités décrites dans cet article, **balisage par Shift**, n’a pas encore été publiée. Il a été annoncé et est bientôt disponible.Si vous êtes un administrateur, vous pouvez en savoir plus sur le lancement de cette fonctionnalité dans le centre de messagerie (dans le [Centre d’administration 365 Microsoft](https://portal.office.com/adminportal/home)). Pour rester au courant des nouvelles fonctionnalités de teams, consultez la [documentation Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).

## <a name="overview"></a>Vue d’ensemble

Dans Microsoft Teams, les indicateurs permettent aux utilisateurs de se connecter facilement et rapidement avec un sous-ensemble de personnes d’une équipe. Vous pouvez créer des balises personnalisées et les affecter pour classer des personnes en fonction d’attributs tels que le rôle, le projet, la qualification ou l’emplacement. Vous pouvez également attribuer automatiquement des indicateurs aux personnes en fonction de leur planning et des informations de décalage dans l' [application Shifts](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) (bientôt disponible). Dès lors que vous avez ajouté une balise à un ou plusieurs membres d’une équipe, vous pouvez l’utiliser dans @mentions par n’importe quel membre de l’équipe dans un billet de canal ou pour démarrer une conversation avec uniquement les personnes auxquelles cette balise est affectée.

Comme mentionné plus haut, il existe deux types de balises dans Teams.

- **Balises personnalisées**: les propriétaires d’équipe et les membres de l’équipe (si la fonctionnalité est activée pour eux) peuvent créer et attribuer manuellement des indicateurs aux personnes. Par exemple, une balise « Designer » ou « radiologist » permettra aux membres de l’équipe d’entrer leurs noms.
- **Balisage par Shift** (bientôt disponible) : cette fonctionnalité permet aux utilisateurs d’affecter automatiquement des balises correspondant au nom de leur planning et au groupe de décalage dans l' [application Shifts](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) dans Teams. Par exemple, la balise « EngineerOnCall » atteint toutes les équipes programmées dans des équipes pour fonctionner lors de l’utilisation de la balise dans une conversation ou un billet de canal. En fonction du balisage par Shift, teams n’accepte pas de savoir le nom du personnel en déplacement lorsque les utilisateurs ont besoin de transférer rapidement des informations. Le balisage par Shift peut également être sauvegardé par des systèmes de gestion de main-d’œuvre importants tels que JDA, Kronos et AMiON en les intégrant aux équipes. Pour en savoir plus sur la configuration de cette fonctionnalité, consultez la rubrique [configurer le balisage par Shift](#set-up-tagging-by-shift-coming-soon).

> [!NOTE]
> Les balises ne sont pas encore prises en charge dans les canaux privés. Les balises ne sont pas encore disponibles dans les organisations du secteur public américain de la communauté américaine (GCC), des États-Unis ou du ministère de la défense des États-Unis.

## <a name="how-tags-work"></a>Fonctionnement des indicateurs

Une balise peut être ajoutée manuellement ou attribuée automatiquement à une personne d’une équipe spécifique. Elle peut ensuite être utilisée dans @mentions sur la ligne **à** d’une discussion ou dans un billet sur n’importe quel canal standard de l’équipe. Voici quelques exemples de la manière dont les indicateurs peuvent être utilisés dans teams :

- Un responsable du Windows Store publie une annonce dans un canal pour avertir tous les caissiers.
- Un administrateur d’hôpital envoie un message à toutes les Radiologists dans un canal.
- Un responsable marketing commence une discussion de groupe avec tous les concepteurs.
- Une infirmier envoie un message à tous les appels cardiologists. (prochainement)
- Un ingénieur système publie une annonce dans un canal pour avertir tous les ingénieurs en déplacement. (prochainement)

Quand une balise n’est @mentioned dans une conversation de canal, les membres de l’équipe associés à la balise seront avertis, comme tout autre @mention.

## <a name="manage-custom-tags-for-your-organization"></a>Gérer les balises personnalisées pour votre organisation

En tant qu’administrateur, vous pouvez contrôler la façon dont les balises sont utilisées au sein de votre organisation dans le centre d’administration Microsoft Teams.

![Capture d’écran des paramètres de marquage dans le centre d’administration Microsoft teams](media/manage-tags-admin-settings.png)

Une équipe peut avoir jusqu’à 100 indicateurs, jusqu’à 100 membres de l’équipe peuvent être attribuées à une balise et 25 balises peuvent être affectées à un utilisateur unique. 

### <a name="set-who-can-add-custom-tags"></a>Définir qui peut ajouter des indicateurs personnalisés

Par défaut, les propriétaires d’équipe peuvent ajouter des balises personnalisées. Vous pouvez modifier ce paramètre pour autoriser les propriétaires d’équipe et les membres de l’équipe à ajouter des indicateurs ou à désactiver les indicateurs de votre organisation.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur paramètres des équipes des **paramètres à l’échelle de l’organisation**  >  **Teams settings**.
2. Sous **marquage**, en regard de l’option **étiquetage est activée pour**, sélectionnez l’une des options suivantes :

    - **Propriétaires et membres**d’une équipe : autoriser les propriétaires et les membres de l’équipe à ajouter des indicateurs.
    - **Propriétaires d’équipe**: autoriser les propriétaires d’équipe à ajouter des indicateurs.
    - **Désactivé**: désactiver les balises.

### <a name="configure-custom-tags-settings"></a>Configurer les paramètres de balises personnalisées

Vous pouvez configurer les paramètres de balises suivants pour contrôler l’utilisation des balises personnalisées au sein de votre organisation.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur paramètres des équipes des **paramètres à l’échelle de l’organisation**  >  **Teams settings**.
2. Sous **marquage**, définissez les éléments suivants selon les besoins de votre organisation.

    - Le propriétaire d’une **équipe peut remplacer les personnes qui peuvent appliquer des indicateurs**: lorsque cette fonction est activée, les propriétaires d’équipe peuvent autoriser ou interdire les membres à ajouter des indicateurs dans les paramètres d’équipe.
    - **Les membres peuvent ajouter des indicateurs supplémentaires**: Si vous autorisez les membres de l’équipe à ajouter des indicateurs, activez cette option pour permettre aux membres de l’équipe d’ajouter des balises autres que les balises par défaut suggérées. Si cette option est désactivée, les membres de l’équipe peuvent uniquement utiliser les balises par défaut.
    - **Balises par défaut suggérées**: utilisez cet indicateur pour ajouter un ensemble de balises par défaut. Vous pouvez ajouter jusqu’à 25 indicateurs et chaque balise peut contenir un maximum de 25 caractères. Les propriétaires d’équipe et les membres (si la fonctionnalité est activée pour eux) peuvent utiliser ces suggestions, y ajouter ou créer un ensemble de balises.

## <a name="manage-custom-tags-settings-for-a-team"></a>Gérer les paramètres de balises personnalisés pour une équipe

Si vous avez activé la case à coadresse le propriétaire de l' **équipe peut remplacer les utilisateurs qui peuvent appliquer des indicateurs** dans le centre d’administration Microsoft Teams, les propriétaires d’équipe peuvent définir si les membres peuvent ajouter des balises au niveau de l’équipe. Pour ce faire, dans l’onglet **paramètres** d’une équipe, accédez à **balises**, puis sélectionnez qui peut ajouter des indicateurs.

![Capture d’écran du paramètre balises au niveau de l’équipe](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>Utiliser des indicateurs

Pour ajouter des balises personnalisées et configurer le balisage par Shift (si vous utilisez l’application Shifts dans Teams), procédez comme suit. Pour en savoir plus, voir [utilisation de balises dans teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).

### <a name="create-and-assign-custom-tags"></a>Création et affectation de balises personnalisées

Pour créer et affecter des balises personnalisées, sélectionnez **équipes** dans la partie gauche de l’application, puis recherchez votre équipe dans la liste. Cliquez sur **autres options**, puis sélectionnez **gérer les indicateurs**. Ici, vous pouvez créer des balises et les affecter à des personnes de votre équipe.

![Capture d’écran de l’application de balises dans le client teams ](media/manage-tags-teams.png)

Pour supprimer un indicateur, supprimez tous les membres de l’équipe associés à la balise.

### <a name="set-up-tagging-by-shift-coming-soon"></a>Configurer le balisage par le biais du changement (bientôt disponible)

1. Dans Teams, accédez à l' [application Shifts](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop).
2. Créez des [groupes Shift](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) et nommez-les après un attribut tel qu’un rôle. Par exemple, EngineerOnCall. Le nom du groupe de décalage sera le nom de la balise.
3. [Remplissez un échéancier](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) en attribuant des Shifts aux membres de votre équipe. Lorsque vous avez terminé, dans le coin supérieur droit de l’application Shifts, sélectionnez **partager avec l’équipe**.
4. Attendez 15 minutes pour que les équipes planifiées remplissent le service de balisage.
5. Utilisez l’indicateur partout où vous utilisez des balises dans Teams.

Le marquage par Shift permet aux utilisateurs d’accéder aux personnes en déplacement en temps réel. Les notifications ne sont envoyées qu’aux personnes qui se trouvent sur la touche Maj au moment où une balise est utilisée pour démarrer une discussion ou dans un billet de canal.

## <a name="related-topics"></a>Voir aussi

[Utilisation de balises dans teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Gérer l’application Shifts pour votre organisation dans Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Documentation d’aide sur les Shifts](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)

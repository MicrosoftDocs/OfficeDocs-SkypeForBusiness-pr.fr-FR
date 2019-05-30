---
title: Ajouter des bots à des conversations et des canaux privés dans Microsoft Teams
author: LolaJacobsen, DamienDoumer
ms.author: lolaj, Damien
manager: serdars
ms.date: 12/05/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: lucarras
description: Découvrez comment ajouter des bots dans Microsoft Teams pour des conversations et des canaux privés, créer des bots personnalisés et charger une version test de votre propre bot pour une conversation privée.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6987c14973443e62f0be69f9872c4e248ddb026b
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548844"
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a>Ajouter des bots à des conversations et des canaux privés dans Microsoft Teams
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Les robots sont des programmes automatisés qui répondent aux requêtes ou fournissent des mises à jour et des notifications relatives aux détails que les utilisateurs trouvent intéressants ou veulent suivre. Les robots permettent aux utilisateurs d’interagir avec les services Cloud, par exemple, la gestion des tâches, la planification et l’interrogation, par le biais de conversations par messagerie instantanée dans Microsoft Teams. Les robots de Microsoft teams sont basés sur l' [infrastructure Microsoft bot](https://go.microsoft.com/fwlink/?linkid=854370). Les robots développés à l’aide de cette infrastructure peuvent être facilement activés pour Microsoft Teams. Pour plus d’informations[Gérer les paramètres de Microsoft Teams pour votre organisation](enable-features-office-365.md).

Actuellement, Microsoft Teams prend en charge les bots dans les conversations et canaux privés dans une équipe. Les administrateurs peuvent contrôler l'autorisation ou l'interdiction de l'utilisation de bots dans le client Office 365.<span id="_T-Bot" class="anchor"></span>

Les bots développés par la communauté peuvent être utilisés dans Microsoft Teams. La fonctionnalité et le chargement de version test de bot doivent être activés au niveau du client pour rendre les bots personnalisés fonctionnels. Les bots peuvent être utilisés dans les conversations et canaux privés. Dans le cas des canaux, les propriétaires ou membres d'équipe peuvent ajouter des bots.

Pour plus d'informations, reportez-vous à la section « Utilisation des bots » dans la rubrique [Applications et services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b). 

> [!IMPORTANT]
> L’ajout d’un bot par le biais d’un GUID, qui n’a pas d’effet de test, n’est pas recommandé. Cela limite sérieusement la fonctionnalité d’un bot. Les robots en production doivent être ajoutés aux équipes dans le cadre d’une application. Voir [créer un bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-create) et [tester et déboguer votre bot Microsoft teams](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-test)

<a name="create-custom-bots-for-microsoft-teams"></a>Création de bots personnalisés pour Microsoft Teams
--------------------------------------

Vous pouvez facilement créer un bot qui s'intègre à vos applications métier à l'aide de Bot Framework de Microsoft. Reportez-vous au guide [Creating and Testing a bot for Microsoft Teams (Création et test de bots pour Microsoft Teams)](https://go.microsoft.com/fwlink/?linkid=854371) pour connaître la procédure de développement et de publication de vos propres bots.

Lorsque vous créez un bot et l'enregistrez avec Bot Framework, vous pouvez décider de le publier. Si vous ne le publiez pas, il reste privé. Vous pouvez également demander à vos utilisateurs de se connecter avant d'utiliser le bot. De cette manière, vous serez certain que seuls les employés de votre organisation y accèdent, même si l'ID d'application du bot venait à être révélé. Reportez-vous à la page dédiée à [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) sur GitHub pour obtenir un exemple de code d'authentification des utilisateurs sur Azure Active Directory, au moyen de bots.

Les bots peuvent être testés à l'aide de l'[émulateur Bot Framework](https://go.microsoft.com/fwlink/?linkid=854373) avant de les déployer dans Teams.

<a name="side-load-your-own-bot-for-private-chat"></a>Chargement de version test de votre propre bot pour une conversation privée
---------------------------------------

1. Après avoir créé votre bot, accédez aux paramètres de l' **application** du robot que vous avez développé, puis sous paramètres de l' **application**, copiez la valeur du paramètre **MicrosoftAppId** . ![Capture d’écran de la page des paramètres d’application pour un bot](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)



2.  Dans le volet **Conversation** de Microsoft Teams, sélectionnez l'icône **Ajouter une conversation**. Dans **À**, collez l’**ID d’application Microsoft**. ![Capture d’écran d’un volet de conversation avec ID d’application Microsoft en surbrillance](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)



3.  L'ID d'application sera converti en **nom de bot** et vous pourrez démarrer une conversation avec ce bot.

<a name="side-load-your-bot-for-channels"></a>Chargement latéral de votre bot pour les canaux
-----------------------------------

Si vous voulez partager votre bot avec vos collègues, vous pouvez l’ajouter à des canaux d’équipes différentes en procédant comme suit:

1. Une fois que vous avez [créé un package d’application pour votre bot](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload), ouvrez teams et naviguez jusqu’à l’équipe dans laquelle vous allez charger le robot.
2. Ajoutez **[app Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, l’application à Microsoft Teams.
3. Dans App Studio, sélectionnez l’onglet **éditeur** de manifeste ![. capture d’écran de l’onglet Éditeur de manifeste.](media/Adding_Bot_To_Teams.png)
4. Pour ajouter votre bot, dans capacités, sélectionnez bot et choisissez d’ajouter un bot existant, vous avez la possibilité de choisir un robot existant à partir d’une goutte ou d’entrer l’ID de l’un de vos robots existants.
![Affiche la sélection du bot que vous avez déjà créé.](media/Select_Existing_Bot.png)
5. Naviguez jusqu’à l’emplacement de votre package d’application, sélectionnez-le, puis cliquez sur **ouvrir**.
6. Sélectionnez le nom de votre bot (n’oubliez pas de cocher la case "équipe" dans la section étendue)
7. Sélectionnez l’option tester et distribuer.
8. Dans la boîte de dialogue qui s’affiche, sélectionnez l’équipe dans laquelle vous voulez connecter votre bot.

Le robot sera alors disponible dans l’équipe de Microsoft Teams.

---
title: Ajouter des bots à des conversations et des canaux privés dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: lucarras, jakon
description: Découvrez comment ajouter des robots dans Microsoft teams pour les discussions personnelles, les discussions de groupe et les canaux, et télécharger vos propres robots pour les discussions personnelles, les conversations de groupes et les canaux.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7837fd3a832a1764cfde3968b73337069762dab3
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2019
ms.locfileid: "37516160"
---
<a name="add-bots-for-personal-chats-group-chats-and-channels-in-microsoft-teams"></a>Ajouter des robots pour les discussions personnelles, les discussions de groupe et les canaux dans Microsoft teams
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Les robots sont des programmes automatisés qui répondent aux requêtes ou fournissent des mises à jour et des notifications sur les détails que les utilisateurs trouvent intéressants ou souhaitent être informés. Les robots permettent aux utilisateurs d’interagir avec les services Cloud, par exemple, la gestion des tâches, la planification et l’interrogation, par le biais de conversations par messagerie instantanée dans Microsoft Teams. Les robots pour les équipes sont basés sur l' [infrastructure Microsoft bot](https://go.microsoft.com/fwlink/?linkid=854370). Les robots développés à l’aide de cette infrastructure peuvent être facilement activés pour les équipes. Pour plus d’informations, reportez-vous à [gérer les paramètres de Microsoft teams pour votre organisation](enable-features-office-365.md).

Actuellement, teams prend en charge les robots dans les discussions personnelles, les discussions de groupe et les canaux au sein d’une équipe. Les administrateurs peuvent contrôler si l’utilisation de robots est autorisée ou interdite dans le client Office 365.<span id="_T-Bot" class="anchor"></span>

Les robots développés par la Communauté peuvent être utilisés dans Teams. Les fonctionnalités du bot et la possibilité de télécharger des applications personnalisées (également appelées chargement indépendant) doivent être activées sur le niveau du client pour que les robots personnalisés soient opérationnels. Les robots peuvent être utilisés dans des discussions personnelles, des discussions de groupe et des canaux. Dans le cas des canaux, les propriétaires ou membres d'équipe peuvent ajouter des bots.

Pour plus d’informations, voir [applications et services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).

> [!IMPORTANT]
> L’ajout d’un bot par le biais d’un GUID, qui n’a pas d’effet de test, n’est pas recommandé. Cela limite sérieusement la fonctionnalité d’un bot. Les robots en production doivent être ajoutés aux équipes dans le cadre d’une application. Voir [créer un bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-create) et [tester et déboguer votre bot Microsoft teams](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-test)

<a name="create-custom-bots-for-microsoft-teams"></a>Création de bots personnalisés pour Microsoft Teams
--------------------------------------

Vous pouvez facilement créer un bot qui s’intègre à vos applications métier, à l’aide de l’infrastructure Microsoft bot. Pour plus d’informations sur le développement et la publication de robots, voir les recommandations en [matière de création et de test d’un bot pour Microsoft teams](https://go.microsoft.com/fwlink/?linkid=854371) .

Lorsque vous créez un bot et l'enregistrez avec Bot Framework, vous pouvez décider de le publier. Si vous ne le publiez pas, il reste privé. Vous pouvez également demander à vos utilisateurs de se connecter avant d'utiliser le bot. De cette manière, vous serez certain que seuls les employés de votre organisation y accèdent, même si l'ID d'application du bot venait à être révélé. Reportez-vous à la page dédiée à [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) sur GitHub pour obtenir un exemple de code d'authentification des utilisateurs sur Azure Active Directory, au moyen de bots.

Les bots peuvent être testés à l'aide de l'[émulateur Bot Framework](https://go.microsoft.com/fwlink/?linkid=854373) avant de les déployer dans Teams.

<a name="upload-your-bot-for-personal-chat"></a>Télécharger votre bot pour les discussions personnelles
---------------------------------------

1. Après avoir créé votre bot, accédez aux paramètres de l' **application** du robot que vous avez développé, puis sous paramètres de l' **application**, copiez la valeur du paramètre **MicrosoftAppId** . ![Capture d’écran de la page des paramètres d’application pour un bot](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)

2.  Dans Microsoft Teams, dans le volet de **conversation** , sélectionnez l' **icône Ajouter une conversation**. Dans **à**, collez l’ID de l' **application Microsoft**de votre bot. ![Capture d’écran d’un volet de conversation avec ID d’application Microsoft en surbrillance](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)

3. L’ID d’application sera résolu sur le nom de votre **bot,** puis vous pourrez commencer une conversation avec ce robot.

<a name="upload-your-bot-for-group-chats-or-channels"></a>Télécharger votre bot pour les discussions ou canaux de groupe
-----------------------------------

Si vous voulez partager votre bot avec vos collègues, vous pouvez l’ajouter à des discussions de groupe ou à des canaux d’équipes différentes en procédant comme suit :

1. Une fois que vous avez [créé un package d’application pour votre bot](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload), ouvrez teams et naviguez jusqu’à l’équipe dans laquelle vous téléchargez le bot.
2. Ajoutez **[app Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, application à Teams.
3. Dans App Studio, sélectionnez l’onglet **éditeur** de manifeste ![. capture d’écran de l’onglet Éditeur de manifeste.](media/Adding_Bot_To_Teams.png)
4. Pour ajouter votre bot, dans capacités, sélectionnez le robot, puis choisissez d’ajouter un bot existant. Sélectionnez ensuite une bot existante ou entrez l’ID d’un robot existant.
![Affiche la sélection du bot que vous avez déjà créé.](media/Select_Existing_Bot.png)
5. Naviguez jusqu’à l’emplacement de votre package d’application, sélectionnez-le, puis cliquez sur **ouvrir**.
6. Sélectionnez le nom de votre bot. (N’oubliez pas de sélectionner la case à cocher **discussion de groupe** ou **équipe** dans la section étendue).
7. Sélectionnez **tester et distribuer**.
8. Sélectionnez la discussion de groupe ou l’équipe dans laquelle vous voulez connecter votre bot.

    Votre bot sera disponible au sein de votre équipe ou de la discussion de groupe dans Teams.

---
title: Ajouter des bots à des conversations et des canaux privés dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: lucarras
description: Découvrez comment ajouter des bots dans Microsoft Teams pour des conversations et des canaux privés, créer des bots personnalisés et charger une version test de votre propre bot pour une conversation privée.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 84ddb68dd5251d943e1fe3b6cca1aae2cf8fcb45
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23867652"
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a>Ajouter des bots à des conversations et des canaux privés dans Microsoft Teams
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Robots sont des programmes automatisés qui répondent aux requêtes ou donnent des mises à jour et les notifications relatives aux utilisateurs de détails intéresser ou doit rester informés. Robots permettent aux utilisateurs d’interagir avec les services de cloud comme la gestion de la tâche, la planification et l’interrogation, par le biais des conversations dans Microsoft Teams. Robots pour Teams Microsoft reposent sur l' [Infrastructure de robot de Microsoft](https://go.microsoft.com/fwlink/?linkid=854370). Robots qui sont développées à l’aide de cette infrastructure peuvent être facilement activés pour Microsoft Teams. Pour plus d’informations, voir [fonctionnalités de gestion des équipes Microsoft dans votre organisation Office 365](enable-features-office-365.md).

Actuellement, Microsoft Teams prend en charge les bots dans les conversations et canaux privés dans une équipe. Les administrateurs peuvent contrôler l'autorisation ou l'interdiction de l'utilisation de bots dans le client Office 365.<span id="_T-Bot" class="anchor"></span>

Les bots développés par la communauté peuvent être utilisés dans Microsoft Teams. La fonctionnalité et le chargement de version test de bot doivent être activés au niveau du client pour rendre les bots personnalisés fonctionnels. Les bots peuvent être utilisés dans les conversations et canaux privés. Dans le cas des canaux, les propriétaires ou membres d'équipe peuvent ajouter des bots.

Pour plus d'informations, reportez-vous à la section « Utilisation des bots » dans la rubrique [Applications et services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b). 




<a name="create-custom-bots-for-microsoft-teams"></a>Création de bots personnalisés pour Microsoft Teams
--------------------------------------

Vous pouvez facilement créer un bot qui s'intègre à vos applications métier à l'aide de Bot Framework de Microsoft. Reportez-vous au guide [Creating and Testing a bot for Microsoft Teams (Création et test de bots pour Microsoft Teams)](https://go.microsoft.com/fwlink/?linkid=854371) pour connaître la procédure de développement et de publication de vos propres bots.

Lorsque vous créez un bot et l'enregistrez avec Bot Framework, vous pouvez décider de le publier. Si vous ne le publiez pas, il reste privé. Vous pouvez également demander à vos utilisateurs de se connecter avant d'utiliser le bot. De cette manière, vous serez certain que seuls les employés de votre organisation y accèdent, même si l'ID d'application du bot venait à être révélé. Reportez-vous à la page dédiée à [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) sur GitHub pour obtenir un exemple de code d'authentification des utilisateurs sur Azure Active Directory, au moyen de bots.

Les bots peuvent être testés à l'aide de l'[émulateur Bot Framework](https://go.microsoft.com/fwlink/?linkid=854373) avant de les déployer dans Teams.

<a name="side-load-your-own-bot-for-private-chat"></a>Chargement de version test de votre propre bot pour une conversation privée
---------------------------------------

1. Après avoir créé votre robot, les **Paramètres de l’Application** pour le composant WebBot que vous avez développé, puis sous **paramètres de l’application**, copiez la valeur du paramètre **MicrosoftAppId** . ![Page de paramètres de capture d’écran de l’Application pour un robot avec l’ID d’application de Microsoft en surbrillance.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)



2.  Dans le volet **Conversation** de Microsoft Teams, sélectionnez l'icône **Ajouter une conversation**. Dans **À**, collez l’**ID d’application Microsoft**. ![Capture d'écran d'un volet de discussion avec l'icône Ajouter une conversation et la ligne À de l'ID d'application Microsoft mis en évidence.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)



3.  L'ID d'application sera converti en **nom de bot** et vous pourrez démarrer une conversation avec ce bot.

---
title: Configuration de vos paramètres de coexistence et de mise à niveau
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: Cet article vous aideront à choisir le mode de coexistence et définir les autres paramètres de coexistence.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 55ed1396cd9c16b96e7d230429ccf25c1802473e
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460403"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a>Configuration de vos paramètres de coexistence et de mise à niveau

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Lorsque vous mettez à niveau votre Skype pour les utilisateurs d’utiliser des équipes, vous disposez de plusieurs options pour vous aider à faire un processus transparent pour vos utilisateurs. Vous avez la possibilité d’effectuer de coexistence et mise à niveau des paramètres pour tous les utilisateurs de votre organisation en une seule fois, ou vous pouvez modifier les paramètres pour un seul ou un ensemble d’utilisateurs dans votre organisation. Notez que les versions antérieures de Skype pour les clients d’entreprise ne pas appliquer ces paramètres. Pour plus d’informations sur Skype pour les versions de client d’entreprise, accédez à [Skype pour les entreprises télécharge et met à jour de la page](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates). 

Vous pouvez obtenir une meilleure compréhension des types de modes sont à votre disposition en lisant l’article [Skype pour l’interopérabilité et coexistence d’entreprise et comprendre les équipes Microsoft](teams-and-skypeforbusiness-coexistence-and-interoperability.md) ou la [Coexistence avec Skype pour les entreprises](coexistence-chat-calls-presence.md).  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Définir les options de mise à niveau pour tous les utilisateurs de votre organisation

![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**

1. Dans la navigation de gauche, accédez à **paramètres à l’échelle de la société** > **équipes de mise à niveau**. 

2. En haut de la page **mise à niveau des équipes** , apportez les modifications suivantes si elles ne fonctionnera pour vous.
    - Définir le mode de **Coexistence** .
        - **(Îles)** - Utilisez ce paramètre si vous souhaitez que les utilisateurs soient en mesure d’utiliser les deux Skype pour professionnels et les équipes simultanément.
        - **Skype pour les entreprises uniquement** - Utilisez ce paramètre si vous souhaitez que vos utilisateurs uniquement utiliser Skype pour les entreprises.
        - **Équipes uniquement** (dans l’aperçu pour certaines organisations) - Utilisez ce paramètre si vous souhaitez que vos utilisateurs d’utiliser uniquement les équipes. Notez que même si ce paramètre, les utilisateurs peuvent toujours participer aux réunions hébergées dans Skype pour les entreprises.
    - Définissez **Skype de notification pour les utilisateurs professionnels, équipes est disponible pour la mise à niveau**. Si vous activez ce, elle indique la Skype pour les utilisateurs professionnels qu’ils seront bientôt être mis à niveau à l’application d’équipes.
    - Définir l' **application par défaut pour les utilisateurs à participer à Skype pour les réunions d’entreprise**. Ce paramètre détermine l’application qui est utilisée pour participer à des Skype pour les réunions d’entreprise et est respecté, quelle que soit la valeur de mode de coexistence.
      - **Application de réunions Skype**
      - **Skype pour les entreprises avec des fonctionnalités limitées**
    - Définir s’il faut **Télécharger l’application d’équipes en arrière-plan pour Skype pour les utilisateurs professionnels**.  Ce paramètre télécharge en mode silencieux l’application équipes pour les utilisateurs Skype pour les entreprises en cours d’exécution sur un ordinateur Windows. Elle est respectée uniquement si le mode de coexistence pour l’utilisateur est uniquement les équipes ou si des notifications en attente de mise à niveau sont activées dans Skype pour les entreprises.
3. Une fois que vous apportez vos modifications, cliquez sur **Enregistrer** .

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Définir les options de mise à niveau pour un seul utilisateur dans votre organisation

![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**

1. Dans la navigation de gauche, accédez à des **utilisateurs**, puis sélectionnez l’utilisateur dans la liste. 
2. Sous l’onglet **compte** pour l’utilisateur, sous **mise à niveau des équipes**, cliquez sur **Modifier**.
3. Vous pouvez définir le **mode de Coexistence**. Choisissez parmi les options suivantes :
     - **Paramètres d’utilisation à l’échelle de l’organisation** - Utilisez ce paramètre si vous souhaitez que l’utilisateur à utiliser les paramètres dans les paramètres **au niveau de l’organisation** . 
     - **(Îles)** - Utilisez ce paramètre si vous souhaitez que l’utilisateur pour être en mesure d’utiliser les deux Skype pour professionnels et les équipes. 
     - **Skype pour les entreprises uniquement** - Utilisez ce paramètre si vous souhaitez que l’utilisateur d’utiliser Skype pour les entreprises. 
     - Les **équipes uniquement** - Utilisez ce paramètre si vous souhaitez que l’utilisateur à utiliser uniquement les équipes. L’utilisateur sera toujours en mesure de joindre Skype pour les réunions d’entreprise.
4. Si vous sélectionnez un **mode de Coexistence** autres que les **paramètres d’utilisation à l’échelle de l’organisation**, vous avez la possibilité d’activer les notifications de Skype l’utilisateur pour l’application de gestion de mise à niveau pour les équipes est bientôt disponible. Vous pouvez activer cette notification de l’utilisateur à activer l’option **notifier le Skype pour l’utilisateur d’entreprise** .
5. Une fois que vous apportez vos modifications, cliquez sur **Enregistrer** .

### <a name="related-topics"></a>Rubriques connexes
[Planifier le voyage](upgrade-plan-journey.md)

[Comprendre la coexistence et la mise à niveau de voyage pour Skype pour professionnels et les équipes](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md)

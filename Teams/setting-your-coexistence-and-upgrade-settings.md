---
title: Configuration de vos paramètres de coexistence et de mise à niveau
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: Découvrez comment définir les paramètres de coexistence et de mise à niveau pour tous les utilisateurs de votre organisation à la fois, ou pour un ou plusieurs membres de votre organisation.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a20e8c355df4103980dc9da460d003382c721800
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940604"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>Configuration de vos paramètres de coexistence et de mise à niveau


Lorsque vous mettre à niveau vos utilisateurs Skype Entreprise pour utiliser Teams, plusieurs options s’offrent à vous pour faciliter le processus pour vos utilisateurs. Vous avez la possibilité d’établir des paramètres de coexistence et de mise à niveau pour tous les utilisateurs de votre organisation à la fois, ou d’apporter des modifications aux paramètres d’un ou plusieurs utilisateurs de votre organisation. Notez que les versions antérieures des clients Skype Entreprise peuvent ne pas respecter ces paramètres. Pour plus d’informations sur les versions du client Skype Entreprise, voir la page des téléchargements et mises à jour [de Skype Entreprise.](https://docs.microsoft.com/skypeforbusiness/software-updates) 

Vous pouvez mieux comprendre les modes disponibles en lisant Comprendre Microsoft Teams et la coexistence et [l’interopérabilité](teams-and-skypeforbusiness-coexistence-and-interoperability.md) de Skype Entreprise avec [Skype Entreprise.](coexistence-chat-calls-presence.md)  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Définir les options de mise à niveau pour tous les utilisateurs de votre organisation

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

1. Dans le Centre [d’administration Microsoft Teams,](https://admin.teams.microsoft.com/)dans le panneau de navigation de gauche, allez à la mise à niveau de Teams à l’échelle **de**  >  **l’organisation.** 

2. En haut de la page de **mise à niveau de Teams,** modifiez les options suivantes comme vous le souhaitez.
    - Définissez le mode **Coexistence.**
        - **Îles** : utilisez ce paramètre si vous souhaitez que les utilisateurs puissent utiliser Skype Entreprise et Teams simultanément.
        - **Skype Entreprise uniquement** : utilisez ce paramètre si vous souhaitez que vos utilisateurs utilisent uniquement Skype Entreprise.
        - **Collaboration dans Skype Entreprise avec Teams** : utilisez ce paramètre si vous souhaitez que vos utilisateurs utilisent Skype Entreprise en plus de Teams pour la collaboration de groupe (canaux).
        - Skype Entreprise avec la collaboration et les réunions Teams - Utilisez ce paramètre si vous souhaitez que vos **utilisateurs** utilisent Skype Entreprise en plus d’utiliser Teams pour la collaboration de groupe (canaux) et les réunions Teams.
        - **Teams uniquement** - Utilisez ce paramètre si vous souhaitez que vos utilisateurs utilisent uniquement Teams. Notez que même avec ce paramètre, les utilisateurs peuvent toujours participer à des réunions hébergées dans Skype Entreprise.
        
    - Définissez Informer les utilisateurs de Skype Entreprise **que Teams est disponible pour la mise à niveau.** Si vous l’allumez, les utilisateurs de Skype Entreprise s’indiqueront qu’ils seront bientôt mis à niveau vers l’application Teams.
    - Définissez **l’application Préférée pour que les utilisateurs participent à des réunions Skype Entreprise.** Ce paramètre détermine l’application utilisée pour participer à des réunions Skype Entreprise et est honorée quelle que soit la valeur du mode de coexistence.
      - **Application Réunions Skype**
      - **Skype Entreprise avec des fonctionnalités limitées**
    - Définissez si vous **décidez de télécharger l’application Teams en arrière-plan pour les utilisateurs de Skype Entreprise.**  Ce paramètre télécharge en mode silencieux l’application Teams pour les utilisateurs exécutant Skype Entreprise sur Windows. Il est honoré uniquement si le mode coexistence de l’utilisateur est Teams uniquement ou si les notifications de mise à niveau en attente sont activées dans Skype Entreprise.
3. Cliquez **sur Enregistrer** après avoir apporté vos modifications.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Définir les options de mise à niveau pour un seul utilisateur dans votre organisation

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

1. Dans le navigateur de gauche, **sélectionnez Utilisateurs,** puis sélectionnez l’utilisateur dans la liste. 
2. Sous **l’onglet Compte** de l’utilisateur, sous **Mise à niveau de Teams,** cliquez **sur Modifier.**
3. Vous pouvez définir le **mode coexistence.** Choisissez l’une des options suivantes :
     - **Utiliser les paramètres** à l’échelle de l’organisation . Utilisez  ce paramètre si vous souhaitez que l’utilisateur utilise les paramètres à l’échelle de l’organisation. 
     - **Îles** : utilisez ce paramètre si vous souhaitez que l’utilisateur puisse utiliser Skype Entreprise et Teams. 
     - **Skype Entreprise uniquement** : utilisez ce paramètre si vous souhaitez que l’utilisateur utilise Skype Entreprise.
     - **Collaboration dans Skype** Entreprise avec Teams : utilisez ce paramètre si vous souhaitez que l’utilisateur utilise Skype Entreprise en plus de Teams pour la collaboration de groupe (canaux).
      - **Skype** Entreprise avec la collaboration et les réunions Teams - Utilisez ce paramètre si vous souhaitez que l’utilisateur utilise Skype Entreprise en plus d’utiliser Teams pour la collaboration de groupe (canaux) et les réunions Teams.
     - **Teams uniquement** - Utilisez ce paramètre si vous souhaitez que l’utilisateur utilise uniquement Teams. L’utilisateur pourra toujours participer à des réunions Skype Entreprise.
4. Si vous sélectionnez un mode de **coexistence** autre que Utiliser les **paramètres** à l’échelle de l’organisation, vous avez la possibilité d’activer les notifications dans l’application Skype Entreprise de l’utilisateur qui sera bientôt mise à niveau vers Teams. Vous pouvez activer cette notification pour l’utilisateur en enableant l’option Notifier l’utilisateur **Skype** Entreprise.
5. Cliquez **sur Enregistrer** après avoir apporté vos modifications.

### <a name="related-topics"></a>Sujets associés
[Mise à niveau de Skype Entreprise vers Teams pour les administrateurs informatiques](upgrade-to-teams-on-prem-overview.md)

[Planifiez votre voyage](upgrade-plan-journey.md)

[Comprendre le parcours de coexistence et de mise à niveau de Skype Entreprise et Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md)

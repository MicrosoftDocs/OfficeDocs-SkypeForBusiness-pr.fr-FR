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
description: Découvrez comment définir les paramètres de coexistence et de mise à niveau de tous les utilisateurs de votre organisation en une seule fois, ou pour un seul ou un ensemble d’utilisateurs de votre organisation.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 245e22c9a5deb518617ff547c4cc2f590d9ea1e6
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905556"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a>Configuration de vos paramètres de coexistence et de mise à niveau


Lorsque vous effectuez une mise à niveau de vos utilisateurs Skype entreprise de manière à utiliser Teams, plusieurs options s’offrent à vous pour faciliter le processus de gestion des utilisateurs. Vous avez la possibilité de définir les paramètres de coexistence et de mise à niveau de tous les utilisateurs de votre organisation en une seule fois, ou de modifier les paramètres d’un seul ou d’un ensemble d’utilisateurs de votre organisation. Notez que les versions plus anciennes de clients Skype entreprise ne respectent pas ces paramètres. Pour plus d’informations sur les versions de client Skype entreprise, consultez la [page téléchargements et mises à jour Skype entreprise](https://docs.microsoft.com/skypeforbusiness/software-updates). 

Vous pouvez vous familiariser avec les modes disponibles en lisant la rubrique comprendre les modes de [coexistence et d’interopérabilité de Microsoft Teams,](teams-and-skypeforbusiness-coexistence-and-interoperability.md) ainsi que l’interopérabilité ou la [coexistence de Skype entreprise](coexistence-chat-calls-presence.md).  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Définir les options de mise à niveau pour tous les utilisateurs de votre organisation

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

1. Dans le [Centre d’administration de Microsoft teams](https://admin.teams.microsoft.com/), dans le volet de navigation de gauche, accédez à**mise à niveau des équipes** **des paramètres** > à l’échelle de l’organisation. 

2. En haut de la page **mise à niveau de teams** , modifiez les options suivantes comme vous le souhaitez.
    - Définissez le mode de **coexistence** .
        - **Îles** -utilisez ce paramètre si vous souhaitez que les utilisateurs puissent utiliser simultanément Skype entreprise et Teams.
        - **Skype entreprise uniquement** : utilisez ce paramètre si vous souhaitez que vos utilisateurs utilisent uniquement Skype entreprise.
        - **Skype entreprise avec collaboration en équipe** : utilisez ce paramètre si vous souhaitez que vos utilisateurs utilisent Skype entreprise, en plus de l’utilisation d’équipes pour la collaboration de groupe (canaux).
        - **Skype entreprise avec collaboration et réunions en équipe** : utilisez ce paramètre si vous souhaitez que vos utilisateurs utilisent Skype entreprise, en plus de l’utilisation d’équipes pour la collaboration de groupe (canaux) et les réunions Teams.
        - **Équipes uniquement** : utilisez ce paramètre si vous souhaitez que vos utilisateurs utilisent uniquement Teams. Notez que, même avec ce paramètre, les utilisateurs peuvent quand même participer à des réunions hébergées dans Skype entreprise.
        
    - Définissez **des utilisateurs Skype entreprise que teams est disponible pour la mise à niveau**. Si vous activez cette option, les utilisateurs de Skype entreprise pourront bientôt procéder à la mise à niveau vers l’application Teams.
    - Définissez l' **application préférée pour permettre aux utilisateurs de participer à des réunions Skype entreprise**. Ce paramètre détermine quelle application est utilisée pour participer aux réunions Skype entreprise et est honorée indépendamment de la valeur du mode de coexistence.
      - **Application réunions Skype**
      - **Skype entreprise avec des fonctions limitées**
    - Indiquez si vous souhaitez **Télécharger l’application teams en arrière-plan pour les utilisateurs de Skype entreprise**.  Ce paramètre télécharge en silence l’application équipes pour les utilisateurs de Skype entreprise sur Windows. Le mode de coexistence est accepté uniquement si le mode de coexistence pour l’utilisateur est équipe uniquement ou si les notifications de mise à niveau en attente sont activées dans Skype entreprise.
3. Cliquez sur **Enregistrer** une fois que vous avez effectué vos modifications.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Définir les options de mise à niveau pour un utilisateur unique au sein de votre organisation

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

1. Dans le volet de navigation gauche, accédez à **utilisateurs**, puis sélectionnez l’utilisateur dans la liste. 
2. Dans l’onglet **compte** de l’utilisateur, sous **mise à niveau de Microsoft teams**, cliquez sur **modifier**.
3. Vous pouvez définir le **mode de coexistence**. Choisissez l’une des options suivantes :
     - **Utiliser les paramètres** à l’échelle de l’organisation-utilisez ce paramètre si vous souhaitez que l’utilisateur utilise les paramètres définis dans les paramètres à l’échelle de l' **organisation** . 
     - **Îles** -utilisez ce paramètre si vous souhaitez que l’utilisateur puisse utiliser Skype entreprise et Teams. 
     - **Skype entreprise uniquement** : utilisez ce paramètre si vous souhaitez que l’utilisateur utilise Skype entreprise.
     - **Skype entreprise avec collaboration en équipe** : utilisez ce paramètre si vous souhaitez que l’utilisateur utilise Skype entreprise en plus de l’utilisation d’équipes pour la collaboration de groupe (canaux).
      - **Skype entreprise avec collaboration et réunions en équipe** : utilisez ce paramètre si vous souhaitez que l’utilisateur utilise Skype entreprise, en plus de l’utilisation d’équipes pour la collaboration de groupe (canaux) et les réunions Teams.
     - **Équipes uniquement** : utilisez ce paramètre si vous souhaitez que l’utilisateur utilise uniquement Teams. L’utilisateur sera toujours en mesure de participer à des réunions Skype entreprise.
4. Si vous sélectionnez n’importe quel **mode de coexistence** autre que l’option **utiliser les paramètres**à l’échelle de l’organisation, vous avez la possibilité d’activer les notifications dans l’application Skype entreprise d’un utilisateur qui est bientôt mise à niveau vers Teams. Vous pouvez activer cette notification pour l’utilisateur en activant l’option **informer l’utilisateur de Skype entreprise** .
5. Cliquez sur **Enregistrer** une fois que vous avez effectué vos modifications.

### <a name="related-topics"></a>Sujets associés
[Mise à niveau de Skype entreprise vers équipes : pour les administrateurs informatiques](upgrade-to-teams-on-prem-overview.md)

[Planifier le voyage](upgrade-plan-journey.md)

[Comprendre le parcours de coexistence et de mise à niveau de Skype entreprise et équipes](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md)

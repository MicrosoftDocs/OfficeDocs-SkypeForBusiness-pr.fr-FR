---
title: Configuration de vos paramètres de coexistence et de mise à niveau
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: Découvrez comment définir des paramètres de coexistence et de mise à niveau pour tous les utilisateurs de votre organisation en même temps, ou pour un seul ou un ensemble d’utilisateurs de votre organisation.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 474c5fc55476e664ba03b9dd82608d8c244b7982
ms.sourcegitcommit: 9bee7cb9433bfc687387647a102f814dc52c8591
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2022
ms.locfileid: "64839185"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>Configuration de vos paramètres de coexistence et de mise à niveau


Lorsque vous mettez à niveau vos utilisateurs Skype Entreprise à utiliser Teams, vous disposez de plusieurs options pour vous aider à en faire un processus transparent pour vos utilisateurs. Vous avez la possibilité d’effectuer simultanément des paramètres de coexistence et de mise à niveau pour tous les utilisateurs de votre organisation, ou vous pouvez modifier les paramètres d’un seul ou d’un ensemble d’utilisateurs de votre organisation. Notez que les versions antérieures de Skype Entreprise clients peuvent ne pas respecter ces paramètres. Pour plus d’informations sur Skype Entreprise versions clientes, accédez à la [page Skype Entreprise téléchargements et mises à jour](/skypeforbusiness/software-updates). 

Vous pouvez mieux comprendre les modes disponibles en lisant [Comprendre Microsoft Teams et Skype Entreprise coexistence et interopérabilité](teams-and-skypeforbusiness-coexistence-and-interoperability.md) ou [coexistence avec Skype Entreprise](coexistence-chat-calls-presence.md).  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Définir les options de mise à niveau pour tous les utilisateurs de votre organisation

 **Utiliser le centre d’administration Microsoft Teams**

1. Dans le [centre d’administration Microsoft Teams](https://admin.teams.microsoft.com/), dans la navigation de gauche, accédez à **Teams** >  **Teams paramètres de mise à niveau**. 

2. En haut de la page **de mise à niveau Teams**, modifiez les options suivantes comme vous le souhaitez.

    - Définissez le mode **coexistence** .
        - **Îles** : utilisez ce paramètre si vous souhaitez que les utilisateurs puissent utiliser simultanément Skype Entreprise et Teams.
        - **Skype Entreprise uniquement** : utilisez ce paramètre si vous souhaitez que vos utilisateurs utilisent uniquement Skype Entreprise.
        - **Skype Entreprise avec Teams collaboration** : utilisez ce paramètre si vous souhaitez que vos utilisateurs utilisent Skype Entreprise en plus d’utiliser Teams pour la collaboration de groupe (canaux).
        - **Skype Entreprise avec Teams collaboration et réunions** : utilisez ce paramètre si vous souhaitez que vos utilisateurs utilisent Skype Entreprise en plus d’utiliser Teams pour la collaboration de groupe (canaux) et les réunions Teams.
        - **Teams uniquement** : utilisez ce paramètre si vous souhaitez que vos utilisateurs utilisent uniquement Teams. Notez que même avec ce paramètre, les utilisateurs peuvent toujours participer à des réunions hébergées dans Skype Entreprise.

          > [!IMPORTANT]
          > Vous ne pouvez affecter le mode TeamsOnly à l’ensemble du locataire qu’une fois les deux étapes suivantes terminées :
          >  - Tous les utilisateurs locaux ont été déplacés vers Teams uniquement à l’aide de Move-CsUser dans l’ensemble d’outils local Skype Entreprise Server.
          >  - Vous avez mis à jour tous les enregistrements DNS Skype Entreprise pour qu’ils pointent vers Microsoft 365. 
          >
          > Pour plus d’informations, consultez [Désactiver votre configuration hybride pour terminer la migration vers Teams uniquement](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).
        
    - Définissez **Avertir Skype Entreprise utilisateurs que Teams est disponible pour la mise à niveau**. Si vous activez cette option, elle indique aux utilisateurs Skype Entreprise qu’ils seront bientôt mis à niveau vers l’application Teams.

    - Définissez **l’application Préférée pour que les utilisateurs rejoignent Skype Entreprise réunions**. Ce paramètre détermine quelle application est utilisée pour rejoindre Skype Entreprise réunions et est honorée quelle que soit la valeur du mode de coexistence.
      - **application réunions Skype**
      - **Skype Entreprise avec des fonctionnalités limitées**

    - Indiquez **s’il faut télécharger l’application Teams en arrière-plan pour Skype Entreprise utilisateurs**. Ce paramètre télécharge silencieusement l’application Teams pour les utilisateurs exécutant Skype Entreprise sur Windows. Elle est honorée uniquement si le mode de coexistence de l’utilisateur est Teams uniquement ou si les notifications de mise à niveau en attente sont activées dans Skype Entreprise.

3. Cliquez sur **Enregistrer** après avoir apporté vos modifications.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Définir les options de mise à niveau pour un seul utilisateur de votre organisation

 **Utiliser le centre d’administration Microsoft Teams**

1. Dans le volet de navigation de gauche, accédez aux **utilisateurs UsersManage** > , puis sélectionnez l’utilisateur dans la liste. 
2. Sous l’onglet **Compte** de l’utilisateur, sous **Teams mise à niveau**, cliquez sur **Modifier**.
3. Vous pouvez définir le **mode coexistence**. Les modes autres que Teams ne peuvent être appliqués qu’aux utilisateurs hébergés dans Skype Entreprise Server localement, et inversement, seuls les utilisateurs hébergés dans le cloud peuvent avoir le mode TeamsOnly.  Choisissez parmi les options suivantes :
     - **Utiliser les paramètres à l’échelle** de l’organisation : utilisez ce paramètre si vous souhaitez que l’utilisateur utilise les paramètres dans les paramètres à **l’échelle de l’organisation** . 
     - **Îles** : utilisez ce paramètre si vous souhaitez que l’utilisateur puisse utiliser à la fois Skype Entreprise et Teams. 
     - **Skype Entreprise uniquement** : utilisez ce paramètre si vous souhaitez que l’utilisateur utilise Skype Entreprise.
     - **Skype Entreprise avec Teams collaboration** : utilisez ce paramètre si vous souhaitez que l’utilisateur utilise Skype Entreprise en plus d’utiliser Teams pour la collaboration de groupe (canaux).
      - **Skype Entreprise avec Teams collaboration et réunions** : utilisez ce paramètre si vous souhaitez que l’utilisateur utilise Skype Entreprise en plus d’utiliser Teams pour la collaboration de groupe (canaux) et les réunions Teams.
     - **Teams uniquement** : utilisez ce paramètre si vous souhaitez que l’utilisateur utilise uniquement Teams. L’utilisateur pourra toujours participer à Skype Entreprise réunions.
4. Si vous sélectionnez un **mode de coexistence** autre que **Utiliser les paramètres à l’échelle de l’organisation**, vous avez la possibilité d’activer les notifications dans l’application Skype Entreprise de l’utilisateur qui seront bientôt mises à niveau vers Teams. Vous pouvez activer cette notification pour l’utilisateur en activant l’option **Notifier l’utilisateur Skype Entreprise**.
5. Cliquez sur **Enregistrer** après avoir apporté vos modifications.

### <a name="related-topics"></a>Sujets associés
[Planifier le parcours](upgrade-plan-journey.md)

[Comprendre le parcours de coexistence et de mise à niveau pour Skype Entreprise et Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md)

[Désaffecter votre environnement Skype Entreprise local](/skypeforbusiness/hybrid/decommission-on-prem-overview)

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
description: Découvrez comment définir les paramètres de coexistence et de mise à niveau pour tous les utilisateurs de votre organisation à la fois, ou pour un ou plusieurs membres de votre organisation.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 489f5315df8c818fd674e30fdaef7c057e9a8ff3
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536495"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>Configuration de vos paramètres de coexistence et de mise à niveau


Lorsque vous mettre à niveau Skype Entreprise utilisateurs pour utiliser Teams, plusieurs options s’offrent à vous pour faciliter le processus pour vos utilisateurs. Vous avez la possibilité d’établir des paramètres de coexistence et de mise à niveau pour tous les utilisateurs de votre organisation à la fois, ou d’apporter des modifications aux paramètres d’un ou plusieurs utilisateurs de votre organisation. Notez que les versions antérieures Skype Entreprise clients peuvent ne pas respecter ces paramètres. Pour plus d’informations Skype Entreprise versions de client, voir la page Skype Entreprise téléchargements et [mises à jour.](/skypeforbusiness/software-updates) 

Vous pouvez mieux comprendre les modes disponibles en lisant « Comprendre les Microsoft Teams et [Skype Entreprise coexistence](teams-and-skypeforbusiness-coexistence-and-interoperability.md) et interopérabilité ou [coexistence](coexistence-chat-calls-presence.md)avec les Skype Entreprise ».  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Définir les options de mise à niveau pour tous les utilisateurs de votre organisation

 **Utiliser le centre d’administration Microsoft Teams**

1. Dans le [Microsoft Teams d’administration,](https://admin.teams.microsoft.com/)dans le panneau de navigation de gauche, allez dans les **paramètres** de l’Teams  >  **mise à niveau.** 

2. En haut de la page **Teams mise à niveau,** modifiez les options suivantes comme vous le souhaitez.

    - Définissez le mode **Coexistence.**
        - **Îles** : utilisez ce paramètre si vous voulez que les utilisateurs puissent utiliser simultanément Skype Entreprise et Teams.
        - **Skype Entreprise uniquement** - Utilisez ce paramètre si vous souhaitez que vos utilisateurs utilisent uniquement Skype Entreprise.
        - **Skype Entreprise** avec Teams collaboration de groupe - Utilisez ce paramètre si vous voulez que vos utilisateurs utilisent Skype Entreprise en plus d’utiliser des Teams pour la collaboration de groupe (canaux).
        - Skype Entreprise avec Teams collaboration et réunions : utilisez ce paramètre si vous souhaitez que vos **utilisateurs** utilisent Skype Entreprise en plus d’utiliser Teams pour la collaboration de groupe (canaux) et les Teams réunion.
        - **Teams uniquement** - Utilisez ce paramètre si vous souhaitez que vos utilisateurs utilisent uniquement Teams. Notez que même avec ce paramètre, les utilisateurs peuvent toujours participer à des réunions hébergées dans Skype Entreprise.

          > [!IMPORTANT]
          > Vous ne pouvez attribuer le mode TeamsOnly qu’à l’ensemble du client une fois que les deux étapes suivantes ont été effectuées :
          >  - Tous les utilisateurs locaux ont été déplacés vers le Teams à l’aide de Move-CsUser dans le Skype Entreprise Server d’outils local.
          >  - Vous avez mis à jour Skype Entreprise enregistrements DNS de façon à ce qu’ils pointent vers Microsoft 365. 
          >
          > Pour plus d’informations, voir Désactiver votre configuration hybride pour achever la [migration vers Teams uniquement.](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)
        
    - Définissez **Informer Skype Entreprise utilisateurs que des Teams sont disponibles pour la mise à niveau.** Si vous l’allumez, il indique Skype Entreprise utilisateurs qu’ils seront bientôt mis à niveau vers l’Teams appe.

    - Définissez **l’application Préférée pour que les utilisateurs participent Skype Entreprise réunions.** Ce paramètre détermine l’application utilisée pour participer Skype Entreprise réunions et est honorée quelle que soit la valeur du mode de coexistence.
      - **Skype Application Réunions**
      - **Skype Entreprise fonctionnalités limitées**

    - Définissez si vous **décidez de télécharger l Teams appappil en arrière-plan pour Skype Entreprise utilisateurs.**  Ce paramètre télécharge en mode silencieux l Teams appappil pour les utilisateurs exécutant Skype Entreprise sur Windows. Il est honoré uniquement si le mode de coexistence de l’utilisateur est Teams ou si les notifications de mise à niveau en attente sont activées dans Skype Entreprise.

3. Cliquez **sur Enregistrer** après avoir apporté vos modifications.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Définir les options de mise à niveau pour un seul utilisateur dans votre organisation

 **Utiliser le centre d’administration Microsoft Teams**

1. Dans le navigateur de gauche, **sélectionnez Utilisateurs,** puis sélectionnez l’utilisateur dans la liste. 
2. Sous **l’onglet** Compte de l’utilisateur, sous Teams mise à **niveau,** cliquez sur **Modifier.**
3. Vous pouvez définir le **mode coexistence.** Les modes autres que Teams Ne peuvent être appliqués qu’aux utilisateurs homed dans Skype Entreprise Server local, et à l’inverse, seuls les utilisateurs homed in the cloud peuvent utiliser le mode TeamsOnly.  Choisissez l’une des options suivantes :
     - **Utiliser les paramètres** à l’échelle de l’organisation . Utilisez  ce paramètre si vous souhaitez que l’utilisateur utilise les paramètres à l’échelle de l’organisation. 
     - **Îles** : utilisez ce paramètre si vous souhaitez que l’utilisateur puisse utiliser à la fois Skype Entreprise et Teams. 
     - **Skype Entreprise uniquement** : utilisez ce paramètre si vous souhaitez que l’utilisateur utilise Skype Entreprise.
     - **Skype Entreprise** avec Teams collaboration de groupe - Utilisez ce paramètre si vous souhaitez que l’utilisateur utilise Skype Entreprise en plus d’utiliser des Teams pour la collaboration de groupe (canaux).
      - **Skype Entreprise** avec Teams collaboration et réunions - Utilisez ce paramètre si vous souhaitez que l’utilisateur utilise Skype Entreprise en plus d’utiliser Teams pour la collaboration de groupe (canaux) et les réunions Teams.
     - **Teams uniquement** - Utilisez ce paramètre si vous souhaitez que l’utilisateur utilise uniquement Teams. L’utilisateur pourra toujours participer à Skype Entreprise réunions.
4. Si vous sélectionnez un mode de **coexistence** autre que Utiliser les **paramètres** à l’échelle de l’organisation, vous avez la possibilité d’activer les notifications dans l’application Skype Entreprise de l’utilisateur qui sont bientôt mises à niveau vers Teams. Vous pouvez activer cette notification pour l’utilisateur en activer l’option Skype Entreprise **l’utilisateur.**
5. Cliquez **sur Enregistrer** après avoir apporté vos modifications.

### <a name="related-topics"></a>Sujets associés
[Planifiez votre voyage](upgrade-plan-journey.md)

[Comprendre le voyage de coexistence et de mise à niveau pour Skype Entreprise et Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md)

[Désaffecter votre environnement Skype Entreprise local](/skypeforbusiness/hybrid/decommission-on-prem-overview)

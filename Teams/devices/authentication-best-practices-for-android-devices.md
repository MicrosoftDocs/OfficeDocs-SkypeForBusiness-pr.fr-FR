---
title: Meilleures pratiques d’authentification pour les appareils Android
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Guide de meilleures pratiques pour l’authentification Teams appareils Android.
ms.collection:
- M365-voice
- M365-collaboration
- skype-for-business-itpro
- skype-for-business-online
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8ffa30efd7f122b6d95c4545dd2d2517f3669472
ms.sourcegitcommit: 73d12d90fc20e3d943301f57ee434379d0b0e91b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2021
ms.locfileid: "61576164"
---
# <a name="authentication-best-practices-for-teams-android-devices"></a>Meilleures pratiques d’authentification pour Teams appareils Android

Cet article fournit des conseils généraux et des recommandations pour le déploiement de stratégies d’authentification pour Teams téléphones et appareils d’appel.

>[!NOTE]
>L’accès conditionnel nécessite Azure Active Directory (Azure AD) Premium abonnement.

>[!NOTE]
>Il se peut que les stratégies applicables aux appareils mobiles Android ne Teams’appliquent pas aux appareils Android.


## <a name="personal-and-shared-devices"></a>Appareils personnels et partagés

Les Teams, tels que les appareils de salle de réunion ou les téléphones de la zone commune, ne peuvent pas utiliser les mêmes exigences en matière d’inscription et de conformité que les appareils personnels. L’application d’exigences d’authentification des appareils personnels aux appareils partagés entraîne les problèmes de authentification suivants :

1.  **Les appareils sont connectés en raison de stratégies de mot de passe**

Les comptes utilisés sur Teams’appareils ont une stratégie d’expiration de mot de passe. Contrairement aux utilisateurs, les comptes utilisés avec des appareils partagés n’ont pas d’utilisateur désigné pour les mettre à jour et les restaurer à l’état valide à l’expiration de leur mot de passe. Si votre organisation exige l’expiration et la réinitialisation périodiques des mots de passe, ces comptes cesseront de fonctionner sur les appareils Teams jusqu’à ce qu’un administrateur Teams réinitialise le mot de passe et se réinitialise.

2.  **Les appareils ne parviennent pas à se connecter en raison de stratégies d’accès conditionnel**

Les appareils partagés ne peuvent pas se conformer à Azure AD d’accès conditionnel pour les comptes d’utilisateurs ou les appareils personnels. Si les appareils partagés sont regroupés avec des comptes d’utilisateurs ou des appareils personnels pour une stratégie d’accès conditionnel, la connectez-vous échoue.

Par exemple, si l’authentification multifacteur est requise pour accéder à Teams utilisateur, une intervention de l’utilisateur est nécessaire pour effectuer l’authentification. Les appareils partagés ne supportent pas l’authentification multifacteur. De même, si le compte est configuré de manière à se authentifier tous les X jours, un appareil partagé ne peut pas résoudre le problème sans intervention de l’utilisateur.

## <a name="best-practices-for-teams-shared-device-deployments"></a>Meilleures pratiques pour les déploiements Teams appareils partagés

Microsoft recommande les paramètres suivants lors du déploiement d Teams appareils dans votre organisation.

### <a name="password-policy"></a>**Stratégie de mot de passe**

Teams appareils partagés doivent utiliser un [Exchange de ressources.](/exchange/recipients-in-exchange-online/manage-resource-mailboxes) Ces comptes peuvent être synchronisés à partir d’Active Directory ou créés directement dans Azure AD. Les stratégies d’expiration des mots de passe pour les utilisateurs s’appliquent également aux comptes utilisés Teams appareils partagés.

Pour éviter les perturbations provoquées par les stratégies d’expiration des mots de passe, définissez la stratégie d’expiration des mots de passe pour les appareils partagés afin qu’elle n’expire jamais.

À partir de Teams les appareils CY21 [Update #1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) (Teams version 1449/1.0.94.2021022403 pour les téléphones Teams) et [CY2021](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) Mise à jour n°2 (Teams version 1449/1.0.96.2021051904 pour Salles Microsoft Teams sur Android), les administrateurs client peuvent se Teams appareils à distance. Ne partagez pas de mots de passe avec les techniciens pour configurer des appareils. Un administrateur utilise la connectez-vous à distance pour émettre des codes de vérification, puis connectez-vous à ces appareils à partir Teams centre d’administration.

Pour plus d’informations, voir Mise en service à distance et [se Teams appareils Android.](/MicrosoftTeams/devices/remote-provision-remote-login) 

### <a name="conditional-access-policies"></a>**Stratégies d’accès conditionnel**

Azure AD accès conditionnel définit les conditions requises supplémentaires pour que les appareils se connectent. Pour Teams appareils mobiles, voir les conseils suivants pour déterminer si vous avez rédigé les stratégies appropriées. Pour une vue d’ensemble de l’accès conditionnel, voir [Qu’est-ce que l’accès conditionnel](/azure/active-directory/conditional-access/overview).

### <a name="multi-factor-authentication"></a>Authentification multifacteur

Les comptes des appareils partagés sont liés à une salle ou à un espace physique, et non à un compte d’utilisateur. Les appareils partagés ne supportant pas l’authentification multifacteur, excluez les appareils partagés des stratégies d’authentification multifacteur.

>[!TIP]
>Utilisez un [emplacement nommé ou](/azure/active-directory/conditional-access/location-condition) un périphérique conforme [pour](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) sécuriser les appareils partagés.

### <a name="location-based-access-with-named-locations"></a>Accès basé sur l’emplacement avec des emplacements nommés

Si des appareils partagés sont configurés dans un emplacement bien défini et qu’ils peuvent être identifiés avec une plage d’adresses IP, vous pouvez configurer l’accès conditionnel à l’aide d’emplacements nommés [pour](/azure/active-directory/conditional-access/location-condition) ces appareils. Cette conditionnelle permet à ces appareils d’accéder aux ressources de votre entreprise uniquement lorsqu’elles se trouveront au sein de votre réseau.

### <a name="require-compliant-device"></a>Exiger un périphérique conforme

>[!NOTE]
>La conformité des appareils nécessite une licence Intune.

Si vous inscrivez des appareils partagés dans Intune, vous pouvez configurer la conformité des appareils en tant que contrôle dans l’accès conditionnel afin que seuls les périphériques conformes peuvent accéder aux ressources de votre entreprise. Teams appareils peuvent être configurés pour des stratégies d’accès conditionnel en fonction de la conformité de l’appareil. Pour plus d’informations, [voir Accès conditionnel : Exiger une](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)conformité ou un Azure AD un appareil joint.

Pour définir les paramètres de conformité pour vos appareils à l’aide d’Intune, voir Utiliser les stratégies de conformité pour définir des règles pour les appareils que vous gérez [avec Intune.](/intune/protect/device-compliance-get-started)

>[!NOTE]
> Les appareils partagés utilisés pour le « hotdesking » doivent être exclus des stratégies de conformité. Les polices de conformité empêchent les appareils de s’inscrire au compte d’utilisateur hot-desk. Utilisez plutôt des emplacements nommés pour sécuriser ces appareils.
> Pour renforcer la sécurité, vous pouvez également exiger l’authentification [multifacteur](/azure/active-directory/authentication/tutorial-enable-azure-mfa) pour les utilisateurs d’hot-desking en plus des stratégies d’emplacement nommé.

### <a name="sign-in-frequency"></a>Fréquence de se connecte

Dans l’accès conditionnel, vous [pouvez](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency) configurer la fréquence de inscription pour exiger que les utilisateurs se connectent à nouveau pour accéder à une ressource après une période spécifiée. Si la fréquence de sign-in est appliquée pour les comptes de salle, les appareils partagés se connectent jusqu’à ce qu’un administrateur les connecte à nouveau. Microsoft recommande d’exclure les appareils partagés des stratégies de fréquence de signature.

### <a name="filters-for-devices"></a>Filtres pour les appareils

[Les filtres pour les](/azure/active-directory/conditional-access/concept-condition-filters-for-devices) appareils sont une fonctionnalité de l’accès conditionnel qui vous permet de configurer des stratégies plus granulaires pour les appareils en fonction des propriétés de l’appareil disponibles dans Azure AD. Vous pouvez également utiliser vos propres valeurs personnalisées en fixant des attributs d’extension 1 à 15 sur l’objet de l’appareil, puis en utilisant ceux-ci.

Utilisez des filtres pour les appareils afin d’identifier vos appareils en zone commune et d’activer les stratégies dans deux scénarios clés :

1.  Exclusion des appareils partagés des stratégies appliquées pour les appareils personnels. Par exemple, le fait d’exiger la conformité des appareils n’est pas appliqué pour les appareils partagés utilisés pour la vérification d’écran, mais pour tous les autres appareils sur la base du numéro de modèle.

2.  application de stratégies spéciales sur les appareils partagés qui ne doivent pas être appliquées à des appareils personnels ; Par exemple, vous devez exiger des emplacements nommés comme stratégie uniquement pour les appareils en zone commune en fonction d’un attribut d’extension que vous définissez pour ces appareils (par exemple : « CommonAreaPhone »).

>[!NOTE] 
> Certains attributs, tels que **le modèle,** **le** fabricant et **operatingSystemVersion,** ne peuvent être définies que lorsque les appareils sont gérés par Intune. Si vos appareils ne sont pas gérés par Intune, utilisez des attributs d’extension.
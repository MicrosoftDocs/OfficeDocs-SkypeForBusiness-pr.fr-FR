---
title: Meilleures pratiques d’authentification pour Microsoft Teams gestion des appareils partagés des appareils Android.
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Meilleures pratiques en matière de gestion des appareils android partagés dans Teams. Cela comprend l’accès conditionnel, la stratégie de mot de passe, les conseils d’authentification multifacteur et bien plus encore.
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
ms.openlocfilehash: 070c662c09d8b8159dbce850501026f67dabb203
ms.sourcegitcommit: 909b0a709983d21fa6f2b547a78cc6a1222188df
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2022
ms.locfileid: "62279232"
---
# <a name="authentication-best-practices-for-teams-shared-device-management-on-android-devices"></a>Meilleures pratiques d’authentification pour Teams gestion des appareils partagés sur les appareils Android

Les objectifs des appareils utilisés Teams rendre différentes stratégies de gestion des appareils nécessaires. Par exemple, une tablette professionnelle personnelle utilisée par un vendeur a des besoins différents par rapport à un téléphone en appel partagé par de nombreux employés du service clientèle.

Les administrateurs de la sécurité et les équipes d’opérations doivent planifier les appareils qui peuvent être utilisés dans l’organisation. Ils doivent *implémenter des* mesures de sécurité adaptées à chaque objectif. Les recommandations de cet article facilitent certaines de ces décisions.

>[!NOTE]
>L’accès conditionnel nécessite Azure Active Directory (Azure AD) Premium abonnement.

>[!NOTE]
>Il se peut que les stratégies applicables aux appareils mobiles Android ne Teams’appliquent pas aux appareils Android.

## <a name="authentication-recommendations-are-different-for-personal-versus-shared-android-devices"></a>Les recommandations d’authentification sont différentes pour les appareils personnels et les appareils Android partagés

Les Teams appareils mobiles partagés ne peuvent pas utiliser les mêmes exigences d’inscription et de conformité que sur les appareils personnels. L’application d’exigences d’authentification des appareils personnels aux appareils partagés entraîne des problèmes de se connecte.

1.  **Les appareils sont connectés en raison de stratégies de mot de passe.**

Les comptes utilisés sur Teams’appareils ont une stratégie d’expiration de mot de passe. Les comptes utilisés avec des appareils partagés n’ont pas d’utilisateur spécifique pour les mettre à jour et les restaurer à l’expiration de leur mot de passe. Si votre organisation exige l’expiration et la réinitialisation occasionnelles des mots de passe, ces comptes cesseront de fonctionner sur les appareils Teams jusqu’à ce qu’un administrateur Teams réinitialise le mot de passe et se réinitialise.

**Défi :** en ce qui concerne l’accès. Teams d’un appareil, le compte d’une personne a une stratégie d’expiration de mot de passe. Lorsque le mot de passe va expirer, il suffit de le modifier. Toutefois, les comptes *utilisés sur des* appareils partagés (comptes de ressources) peuvent ne pas être connectés à une seule personne qui peut modifier un mot de passe si nécessaire. Cela signifie qu’un mot de passe peut expirer et laisser des travailleurs sur place, sans savoir comment reprendre leur travail.

Si votre organisation exige la réinitialisation ou l’expiration des mots de passe, assurez-vous qu’un administrateur Teams est prêt à réinitialiser le mot de passe pour que ces comptes partagés se connectent à nouveau.

2.  **Les appareils ne se connectent pas en raison de stratégies d’accès conditionnel.**

**Défi :** Les appareils partagés ne peuvent pas se conformer à Azure AD d’accès conditionnel pour les comptes d’utilisateurs ou les appareils personnels. Si les appareils partagés sont regroupés avec des comptes d’utilisateurs ou des appareils personnels pour une stratégie d’accès conditionnel, la *connectez-vous échoue*.

Par exemple, si une authentification multifacteur est requise pour accéder à Teams, l’entrée utilisateur d’un code est nécessaire pour effectuer cette authentification. En général, les appareils partagés n’ont pas un utilisateur unique qui peut configurer et effectuer une authentification multifacteur. De plus, si le compte doit être authentifier tous les X jours, un appareil partagé ne peut pas résoudre le problème sans l’intervention d’un utilisateur.

L’authentification multifacteur n’est pas prise en charge avec les appareils partagés. Les méthodes à utiliser sont décrites ci-dessous.

## <a name="best-practices-for-the-deployment-of-shared-android-devices-with-teams"></a>Meilleures pratiques pour le déploiement d’appareils android partagés avec Teams

Microsoft recommande les paramètres suivants lors du déploiement d Teams appareils dans votre organisation.

### <a name="use-a-resource-account-and-curtail-its-password-expiration"></a>**Utiliser un compte ressource et expiration de son mot de passe**

Teams les appareils partagés doivent utiliser une boîte [aux lettres Exchange ressources partagées](/exchange/recipients-in-exchange-online/manage-resource-mailboxes). La création de ces boîtes aux lettres génère un compte automatiquement. Ces comptes peuvent être synchronisés avec des utilisateurs Azure AD Active Directory ou créés directement dans Azure AD. Toute stratégie d’expiration des mots de passe pour les utilisateurs s’appliquera également aux comptes utilisés sur les appareils partagés d’Teams afin d’éviter les perturbations provoquées par les stratégies d’expiration des mots de passe, définissez la stratégie d’expiration du mot de passe pour les appareils partagés de façon à ne jamais expirer.

À partir de Teams les appareils CY21 [Update #1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) (Teams version 1449/1.0.94.2021022403 pour les téléphones Teams) et [CY2021 Mise à jour n°2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) (Teams version 1449/1.0.96.2021051904 pour Salles Microsoft Teams sur Android), les administrateurs client peuvent se connecter à Teams appareils à distance. Au lieu de partager des mots de passe avec des techniciens pour configurer des appareils, les administrateurs de client doivent utiliser la validation à distance pour émettre des codes de vérification. Vous pouvez vous connectez à ces appareils à partir du Centre d’Teams’administration.

Pour plus d’informations, [voir Mise en service à distance et se Teams appareils Android](/MicrosoftTeams/devices/remote-provision-remote-login). 

### <a name="review-these-conditional-access-policies"></a>**Passer en revue les stratégies d’accès conditionnel**

Azure AD accès conditionnel définit les conditions requises supplémentaires pour que les appareils se connectent. Pour Teams appareils, voir les conseils ci-dessous pour déterminer si vous avez rédigé les stratégies qui permettront aux utilisateurs d’appareils partagés de faire leur travail.

> [!TIP]
> Pour une vue d’ensemble de l’accès conditionnel, voir [Qu’est-ce que l’accès conditionnel](/azure/active-directory/conditional-access/overview) ?

### <a name="do-not-use-multi-factor-authentication-for-shared-devices"></a>N’utilisez pas l’authentification multifacteur pour les appareils partagés

Les comptes des appareils partagés sont liés à une salle ou à un espace physique, plutôt qu’à un compte d’utilisateur final. Les appareils partagés ne supportant pas l’authentification multifacteur, excluez les appareils partagés des stratégies d’authentification multifacteur.

>[!TIP]
>Utilisez un [emplacement nommé ou](/azure/active-directory/conditional-access/location-condition) [un périphérique conforme pour](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) sécuriser les appareils partagés.

### <a name="you-can-use-location-based-access-with-named-locations"></a>Vous pouvez utiliser l’accès basé sur l’emplacement avec des emplacements nommés

Si des appareils partagés sont configurés dans un emplacement bien défini et qu’ils peuvent être identifiés avec une plage d’adresses IP, vous pouvez configurer l’accès conditionnel à l’aide d’emplacements nommés [pour ces](/azure/active-directory/conditional-access/location-condition) appareils. Cette conditionnelle permet à ces appareils d’accéder aux ressources de votre entreprise uniquement lorsqu’elles se trouveront au sein de votre réseau.

### <a name="when-and-when-not-to-require-compliant-shared-devices"></a>Quand et quand ne pas exiger des appareils partagés conformes

>[!NOTE]
>La conformité des appareils nécessite une licence Intune.

Si vous inscrivez des appareils partagés dans Intune, vous pouvez configurer la conformité des appareils en tant que contrôle dans l’accès conditionnel afin que seuls les périphériques conformes peuvent accéder aux ressources de votre entreprise. Teams appareils peuvent être configurés pour des stratégies d’accès conditionnel en fonction de la conformité de l’appareil. Pour plus d’informations, voir [Accès conditionnel : Exiger une conformité ou un Azure AD un appareil joint](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device).

Pour définir les paramètres de conformité pour vos appareils à l’aide d’Intune, voir Utiliser les stratégies de conformité pour définir des règles pour les appareils que vous gérez [avec Intune](/intune/protect/device-compliance-get-started).

>[!NOTE]
> Les appareils partagés utilisés pour les procédures *d’utilisation d’hotking* doivent être exclus des stratégies de conformité. Les polices de conformité empêchent les appareils de s’inscrire au compte d’utilisateur hot desk. **Utilisez plutôt des emplacements nommés pour sécuriser ces appareils**.
> Pour renforcer la sécurité, vous pouvez également exiger l’authentification [multifacteur](/azure/active-directory/authentication/tutorial-enable-azure-mfa) pour les *utilisateurs et comptes d’utilisateurs hotking* en plus des stratégies d’emplacement nommées.

### <a name="exclude-shared-devices-from-sign-in-frequency-conditions"></a>Exclure les appareils partagés des conditions de fréquence de se connecte

Dans l’accès conditionnel, [vous pouvez configurer](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency) la fréquence de inscription pour exiger que les utilisateurs se connectent à nouveau pour accéder à une ressource après une période spécifiée. Si la fréquence de sign-in est appliquée pour les comptes de salle, les appareils partagés se connectent jusqu’à ce qu’un administrateur les connecte à nouveau. Microsoft recommande d’exclure les appareils partagés des stratégies de fréquence de signature.

### <a name="using-filters-for-devices"></a>Utilisation de filtres pour les appareils

[Les filtres pour les](/azure/active-directory/conditional-access/concept-condition-filters-for-devices) appareils sont une fonctionnalité de l’accès conditionnel qui vous permet de configurer des stratégies plus granulaires pour les appareils en fonction des propriétés de l’appareil disponibles dans Azure AD. Vous pouvez également utiliser vos propres valeurs personnalisées en fixant des attributs d’extension 1 à 15 sur l’objet de l’appareil, puis en utilisant ceux-ci.

Utilisez des filtres pour les appareils afin d’identifier vos appareils en zone commune et d’activer les stratégies dans deux scénarios clés :

1.  Exclusion des appareils partagés des stratégies appliquées pour les appareils personnels. Par exemple, le fait d’exiger la conformité des appareils n’est pas appliqué pour les appareils partagés  utilisés pour les utilisations de *l’utilisation de la fonction d’utilisation d’une* base de données hot-king, mais il est appliqué pour tous les autres appareils sur la base du numéro de modèle.

2.  application de stratégies spéciales sur les appareils partagés qui *ne doivent* pas être appliquées à des appareils personnels ; Par exemple, vous devez exiger des emplacements nommés comme stratégie uniquement pour les appareils en zone commune en fonction d’un attribut d’extension que vous définissez pour ces appareils (par exemple : « CommonAreaPhone »).

>[!NOTE] 
> Certains attributs tels que **modèle**, **fabricant** et **operatingSystemVersion** ne peuvent être définies que lorsque les appareils sont gérés par Intune. Si vos appareils ne sont pas gérés par Intune, utilisez des attributs d’extension.

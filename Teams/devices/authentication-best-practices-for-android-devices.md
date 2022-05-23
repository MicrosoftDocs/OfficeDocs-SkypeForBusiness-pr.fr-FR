---
title: Meilleures pratiques d’authentification pour Microsoft Teams la gestion des appareils partagés des appareils Android.
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Meilleures pratiques sur la gestion des appareils Android partagés dans Teams. Cela comprend l’accès conditionnel, la stratégie de mot de passe, les conseils d’authentification multifacteur et bien plus encore.
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
ms.openlocfilehash: 6eef76052f662b26f946bf80839a62186c287b68
ms.sourcegitcommit: d425748a50964ebc78e5d38fce564a444a449f43
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/23/2022
ms.locfileid: "65635461"
---
# <a name="authentication-best-practices-for-teams-shared-device-management-on-android-devices"></a>Meilleures pratiques d’authentification pour Teams la gestion des appareils partagés sur Android appareils

Les objectifs des appareils utilisés avec Teams rendre nécessaires différentes stratégies de gestion des appareils. Par exemple, une tablette d’entreprise personnelle utilisée par un seul vendeur a un ensemble de besoins différent d’un téléphone sur appel partagé par de nombreuses personnes du service clientèle.

Les administrateurs de sécurité et les équipes d’exploitation doivent planifier les appareils qui peuvent être utilisés dans l’organisation. Ils doivent implémenter des mesures *de sécurité* adaptées à chaque objectif. Les recommandations de cet article facilitent certaines de ces décisions.

>[!NOTE]
>L’accès conditionnel nécessite un abonnement Premium Azure Active Directory (Azure AD).

>[!NOTE]
>Les stratégies pour Android appareils mobiles peuvent ne pas s’appliquer aux appareils Teams Android.

## <a name="authentication-recommendations-are-different-for-personal-versus-shared-android-devices"></a>Les recommandations d’authentification sont différentes pour les appareils android personnels et partagés

Les appareils Teams partagés ne peuvent pas utiliser les mêmes exigences d’inscription et de conformité que sur les appareils personnels. L’application des exigences d’authentification des appareils personnels aux appareils partagés entraîne des problèmes de connexion.

1.  **Les appareils sont déconnectés en raison de stratégies de mot de passe.**

Les comptes utilisés sur Teams appareils ont une stratégie d’expiration de mot de passe. Les comptes utilisés avec des appareils partagés n’ont pas d’utilisateur spécifique pour les mettre à jour et les restaurer à un état de travail lorsque leurs mots de passe expirent. Si votre organisation exige l’expiration et la réinitialisation occasionnelles des mots de passe, ces comptes cesseront de fonctionner sur Teams appareils jusqu’à ce qu’un administrateur Teams réinitialise le mot de passe et se connecte.

**Défi** : Quand il s’agit d’accéder. Teams à partir d’un appareil, le compte d’une personne a une stratégie d’expiration de mot de passe. Lorsque le mot de passe va expirer, il suffit de le modifier. Toutefois, les comptes utilisés sur *des appareils partagés* (comptes de ressources) peuvent ne pas être connectés à une seule personne qui peut modifier un mot de passe en fonction des besoins. Cela signifie qu’un mot de passe peut expirer et laisser les travailleurs sur place, ne sachant pas comment reprendre leur travail.

Lorsque votre organisation a besoin d’une réinitialisation de mot de passe ou applique l’expiration du mot de passe, assurez-vous qu’un administrateur Teams est prêt à réinitialiser le mot de passe afin que ces comptes partagés puissent se connecter.

2.  **Les appareils ne parviennent pas à se connecter en raison de stratégies d’accès conditionnel.**

**Défi** : Les appareils partagés ne peuvent pas se conformer aux stratégies d’accès conditionnel Azure AD pour les comptes d’utilisateur ou les appareils personnels. Si les appareils partagés sont regroupés avec des comptes d’utilisateur ou des appareils personnels pour une stratégie d’accès conditionnel, la connexion *échoue*.

Par exemple, si l’authentification multifacteur est requise pour accéder à Teams, l’entrée utilisateur d’un code est nécessaire pour terminer cette authentification. Les appareils partagés n’ont généralement pas un seul utilisateur capable de configurer et de terminer l’authentification multifacteur. En outre, si le compte doit se réauthentifier tous les X jours, un appareil partagé ne peut pas résoudre le problème sans l’intervention d’un utilisateur.

L’authentification multifacteur n’est pas prise en charge avec les appareils partagés. Les méthodes à utiliser à la place sont décrites ci-dessous.

## <a name="best-practices-for-the-deployment-of-shared-android-devices-with-teams"></a>Meilleures pratiques pour le déploiement d’appareils Android partagés avec Teams

Microsoft recommande les paramètres suivants lors du déploiement d’appareils Teams dans votre organisation.

### <a name="use-a-resource-account-and-curtail-its-password-expiration"></a>**Utiliser un compte de ressource et limiter l’expiration de son mot de passe**

Teams appareils partagés doivent utiliser une [boîte aux lettres de ressources Exchange](/exchange/recipients-in-exchange-online/manage-resource-mailboxes). La création de ces boîtes aux lettres génère automatiquement un compte. Ces comptes peuvent être synchronisés avec Azure AD à partir d’Active Directory ou créés directement dans Azure AD. Toutes les stratégies d’expiration de mot de passe pour les utilisateurs s’appliquent également aux comptes utilisés sur Teams appareils partagés. Par conséquent, pour éviter les interruptions causées par les stratégies d’expiration de mot de passe, définissez la stratégie d’expiration du mot de passe pour les appareils partagés afin qu’elles n’expirent jamais.

À compter de Teams appareils CY21 [Update #1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) (Teams version 1449/1.0.94.2021022403 pour les téléphones Teams) et [CY20 21 Mise à jour 2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) (Teams version 1449/1.0.96.2021051904 pour Salles Microsoft Teams sur Android), les administrateurs clients peuvent se connecter à Teams  appareils à distance. Au lieu de partager des mots de passe avec des techniciens pour configurer des appareils, les administrateurs locataires doivent utiliser la connexion à distance pour émettre des codes de vérification. Vous pouvez vous connecter à ces appareils à partir du centre d’administration Teams.

Pour plus d’informations, consultez [l’approvisionnement à distance et la connexion pour Teams Android appareils](/MicrosoftTeams/devices/remote-provision-remote-login). 

### <a name="review-these-conditional-access-policies"></a>**Passer en revue ces stratégies d’accès conditionnel**

L’accès conditionnel Azure AD définit des exigences supplémentaires que les appareils doivent respecter pour se connecter. Pour Teams appareils, passez en revue les conseils qui suivent pour déterminer si vous avez créé les stratégies qui permettront aux utilisateurs d’appareils partagés d’effectuer leur travail.

> [!TIP]
> Pour obtenir une vue d’ensemble de l’accès conditionnel, consultez [Qu’est-ce que l’accès conditionnel](/azure/active-directory/conditional-access/overview) ?

### <a name="do-not-use-multi-factor-authentication-for-shared-devices"></a>N’utilisez pas l’authentification multifacteur pour les appareils partagés

Les comptes d’appareils partagés sont liés à une salle ou à un espace physique, plutôt qu’à un compte d’utilisateur final. Étant donné que les appareils partagés ne prennent pas en charge l’authentification multifacteur, excluez les appareils partagés des stratégies d’authentification multifacteur.

>[!TIP]
>Utilisez un [emplacement nommé](/azure/active-directory/conditional-access/location-condition) ou [exigez un appareil conforme](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) pour sécuriser les appareils partagés.

### <a name="you-can-use-location-based-access-with-named-locations"></a>Vous pouvez utiliser l’accès en fonction de l’emplacement avec des emplacements nommés

Si les appareils partagés sont approvisionnés dans un emplacement bien défini qui peut être identifié avec une plage d’adresses IP, vous pouvez configurer l’accès conditionnel à l’aide [d’emplacements nommés](/azure/active-directory/conditional-access/location-condition) pour ces appareils. Cette condition permet à ces appareils d’accéder à vos ressources d’entreprise uniquement lorsqu’ils se trouvent dans votre réseau.

### <a name="when-and-when-not-to-require-compliant-shared-devices"></a>Quand et quand ne pas exiger des appareils partagés conformes

>[!NOTE]
>La conformité des appareils nécessite une licence Intune.

Si vous inscrivez des appareils partagés dans Intune, vous pouvez configurer la conformité des appareils en tant que contrôle dans l’accès conditionnel afin que seuls les appareils conformes puissent accéder à vos ressources d’entreprise. Teams appareils peuvent être configurés pour les stratégies d’accès conditionnel en fonction de la conformité des appareils. Pour plus d’informations, consultez [Accès conditionnel : Exiger un appareil joint à Azure AD conforme ou hybride](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device).

Pour définir le paramètre de conformité de vos appareils à l’aide de Intune, consultez [Utiliser des stratégies de conformité pour définir des règles pour les appareils que vous gérez avec Intune](/intune/protect/device-compliance-get-started).

>[!NOTE]
> Les appareils partagés utilisés pour le *desking à chaud* doivent être exclus des stratégies de conformité. Les stratégies de conformité empêchent les appareils de s’inscrire au compte d’utilisateur hot desk. **Utilisez plutôt des emplacements nommés pour sécuriser ces appareils**.
> Pour renforcer la sécurité, vous pouvez également [exiger l’authentification multifacteur](/azure/active-directory/authentication/tutorial-enable-azure-mfa) pour les *utilisateurs/comptes d’utilisateurs à chaud* , en plus des stratégies d’emplacement nommées.

### <a name="exclude-shared-devices-from-sign-in-frequency-conditions"></a>Exclure les appareils partagés des conditions de fréquence de connexion

Dans l’accès conditionnel, vous pouvez [configurer la fréquence de connexion](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency) pour obliger les utilisateurs à se reconnecter pour accéder à une ressource après une période spécifiée. Si la fréquence de connexion est appliquée pour les comptes de salle, les appareils partagés se déconnectent jusqu’à ce qu’ils soient à nouveau connectés par un administrateur. Microsoft recommande d’exclure les appareils partagés des stratégies de fréquence de connexion.

### <a name="using-filters-for-devices"></a>Utilisation de filtres pour les appareils

[Les filtres pour les appareils](/azure/active-directory/conditional-access/concept-condition-filters-for-devices) sont une fonctionnalité de l’accès conditionnel qui vous permet de configurer des stratégies plus granulaires pour les appareils en fonction des propriétés d’appareil disponibles dans Azure AD. Vous pouvez également utiliser vos propres valeurs personnalisées en définissant les attributs d’extension 1 à 15 sur l’objet de l’appareil, puis en les utilisant.

Utilisez des filtres pour les appareils afin d’identifier vos appareils communs et d’activer les stratégies dans deux scénarios clés :

1.  Exclusion des appareils partagés des stratégies appliquées aux appareils personnels. Par exemple, l’exigence de conformité des appareils *n’est pas appliquée* pour les appareils partagés utilisés pour le desking à chaud, mais *elle est appliquée* pour tous les autres appareils, en fonction du numéro de modèle.

2.  Application de stratégies spéciales sur les appareils partagés qui *ne doivent pas* être appliquées à des appareils personnels. Par exemple, exiger des emplacements nommés comme stratégie uniquement pour les appareils de zone commune en fonction d’un attribut d’extension que vous avez défini pour ces appareils (par exemple : « CommonAreaPhone »).

>[!NOTE] 
> Certains attributs tels que **le modèle**, **le fabricant** et **operatingSystemVersion** ne peuvent être définis que lorsque les appareils sont gérés par Intune. Si vos appareils ne sont pas gérés par Intune, utilisez des attributs d’extension.

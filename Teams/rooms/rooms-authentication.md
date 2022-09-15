---
title: Authentification dans Salles Microsoft Teams sur Windows
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ''
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Découvrez comment configurer l’authentification moderne pour Salles Microsoft Teams sur Windows
ms.openlocfilehash: 23e08b48c5d161caf8091068abc4c9cda0061122
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706431"
---
# <a name="authentication-in-microsoft-teams-rooms-on-windows"></a>Authentification dans Salles Microsoft Teams sur Windows

La gestion des comptes pour Salles Microsoft Teams est gérée au niveau de l’application. L’application se connecte à Microsoft Teams, Skype Entreprise et Exchange pour obtenir des ressources pour le compte de ressource afin d’activer les expériences d’appel et de réunion. salles Teams utilise un compte de ressources dédié pour autoriser les fonctionnalités always on, les scénarios d’appel (pour les appareils configurés avec un plan d’appel) et les mécanismes de verrouillage personnalisés. Cela signifie que l’authentification pour salles Teams se produit d’une manière différente de celle des appareils de l’utilisateur final.  

L’authentification moderne est recommandée pour tous les clients utilisant Salles Microsoft Teams avec Microsoft 365 ou Office 365. Si vous disposez d’un déploiement local d’un serveur Exchange ou d’un serveur Skype Entreprise, configurez [l’authentification moderne hybride](/office365/enterprise/hybrid-modern-auth-overview) avec Azure Active Directory (Azure AD) pour l’activer à l’aide de l’authentification moderne.

L’authentification moderne est prise en charge sur Salles Microsoft Teams version 4.4.25.0 et ultérieure.

## <a name="modern-authentication"></a>Authentification moderne

Lorsque vous utilisez l’authentification moderne avec l’application Salles Microsoft Teams, la bibliothèque d’authentification Active Directory (ADAL) est utilisée pour vous connecter à Microsoft Teams, Exchange et Skype Entreprise. Le mécanisme d’authentification moderne utilise le type d’autorisation [des informations d’identification du mot de passe du propriétaire](/azure/active-directory/develop/v2-oauth-ropc) de la ressource dans OAuth 2.0, qui ne nécessite aucune intervention de l’utilisateur. Il s’agit de l’une des principales différences entre le fonctionnement de l’authentification moderne pour les comptes d’utilisateur et les comptes de ressources utilisés par Salles Microsoft Teams. Pour cette raison, Salles Microsoft Teams comptes de ressources ne doivent pas être configurés pour utiliser l’authentification multifacteur (MFA), l’authentification par carte à puce ou l’authentification basée sur un certificat client (qui sont tous disponibles pour les utilisateurs finaux).

L’autre différence clé entre le fonctionnement de l’authentification moderne sur Salles Microsoft Teams et les appareils de l’utilisateur final est que vous ne pouvez pas utiliser un compte de ressource pour appliquer des stratégies d’accès conditionnel au niveau de l’appareil dans Azure Active Directory et Endpoint Manager, car les informations sur l’appareil ne sont pas transmises lors de l’utilisation de ce type d’octroi. Au lieu de cela, vous pouvez inscrire un appareil dans Microsoft Endpoint Manager et appliquer des stratégies de conformité. Pour plus d’informations, consultez [l’accès conditionnel et la conformité Intune pour Salles Microsoft Teams](conditional-access-and-compliance-for-devices.md).

## <a name="enable-modern-authentication-on-microsoft-teams-rooms"></a>Activer l’authentification moderne sur Salles Microsoft Teams

Pour Salles Microsoft Teams utiliser l’authentification moderne avec Skype Entreprise et Exchange, activez le paramètre côté client pour l’authentification moderne sur Salles Microsoft Teams. Vous pouvez le faire dans les paramètres de l’appareil ou dans le fichier de configuration XML.

> [!NOTE]
> Avant d’activer le paramètre côté client pour l’authentification moderne, assurez-vous que votre environnement est correctement configuré pour utiliser l’authentification moderne.

### <a name="using-device-settings"></a>Utilisation des paramètres de l’appareil

1. Sur Salles Microsoft Teams, accédez à **Plus** (**...**).
    
2. Sélectionnez **Paramètres**, puis entrez le nom d’utilisateur et le mot de passe de l’administrateur de l’appareil.
3. Accédez à l’onglet **Compte** , activez **l’authentification moderne**, puis **sélectionnez Enregistrer et quitter**.

### <a name="using-the-xml-config-file"></a>Utilisation du fichier de configuration XML

Dans votre fichier SkypeSettings.xml, définissez l’élément XML d’authentification moderne sur **True**, comme suit.

```XML
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Pour appliquer le paramètre, consultez [Gérer les paramètres d’une console Salles Microsoft Teams à distance avec un fichier de configuration XML](xml-config-file.md).

## <a name="prepare-your-environment-for-modern-authentication"></a>Préparer votre environnement pour l’authentification moderne

Avant de commencer, veillez à bien comprendre les modèles d’identité à utiliser avec Office 365 et Azure AD. Vous trouverez plus d’informations sur [les modèles d’identité Office 365 et Azure Active Directory](/Office365/Enterprise/about-office-365-identity), ainsi que sur la [synchronisation d’identités et d’annuaires hybrides pour Microsoft 365 ou Office 365](/Office365/Enterprise/plan-for-directory-synchronization).

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Activer l’authentification moderne dans Microsoft 365 ou Office 365

Pour activer l’authentification moderne pour Exchange Online, consultez [Activer l’authentification moderne dans Exchange Online](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).

Nous vous recommandons de ne pas supprimer les stratégies d’authentification de base pour Exchange Online ou de désactiver l’authentification de base pour votre locataire tant que vous n’avez pas validé que Salles Microsoft Teams appareils peuvent se connecter avec Exchange Online et Teams.

Pour plus d’informations sur la désactivation de l’authentification de base dans Exchange Online, consultez [Désactiver l’authentification de base dans Exchange Online](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online).

## <a name="hybrid-modern-authentication"></a>Authentification moderne hybride

Pour garantir la réussite de l’authentification auprès de votre serveur Exchange local et/ou de votre serveur Skype Entreprise, vous devez vous assurer que le compte de ressource utilisé avec Salles Microsoft Teams est configuré pour obtenir l’autorisation d’Azure AD.

salles Teams flux d’authentification varient en fonction de votre configuration d’authentification. Pour les clients qui utilisent un domaine managé, salles Teams utilise les informations d’identification du [mot de passe du propriétaire de ressource OAuth 2.0](/azure/active-directory/develop/v2-oauth-ropc) avec Azure Active Directory. Toutefois, pour les clients qui utilisent un domaine fédéré, [OAuth 2.0 SAML Bearer Assertion Flow](/azure/active-directory/develop/v2-saml-bearer-assertion) est utilisé.

> [!NOTE]
> Votre fournisseur d’identité peut avoir besoin de configurations ou de paramètres spécifiques pour l’intégration à Azure Active Directory ou Office 365. Contactez votre fournisseur d’identité si vous avez besoin d’aide pour configurer l’authentification avec salles Teams.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Conditions préalables propres à Salles Microsoft Teams

Les conditions préalables à l’activation de l’authentification moderne dans votre topologie hybride sont [traitées dans la vue d’ensemble de l’authentification moderne hybride et les prérequis pour l’utiliser avec des serveurs Skype Entreprise locaux et Exchange](/office365/enterprise/hybrid-modern-auth-overview). Tous les prérequis décrits dans l’article s’appliquent.

Toutefois, étant donné que Salles Microsoft Teams utilise l’autorisation [des informations d’identification du mot de passe du propriétaire](https://tools.ietf.org/html/rfc6749#section-1.3.3) de la ressource et les API REST sous-jacentes pour l’authentification moderne, les différences importantes à connaître sont spécifiques à Salles Microsoft Teams.

- Vous devez avoir Exchange Server 2016 CU8 ou version ultérieure, ou Exchange Server 2019 CU1 ou version ultérieure.
- Vous devez avoir Skype Entreprise Server 2015 CU5 ou version ultérieure, ou Skype Entreprise Server 2019 ou version ultérieure.
- L’authentification multifacteur n’est pas prise en charge, quelle que soit la topologie dont vous disposez.
- Salles Microsoft Teams ne prend pas en charge l’incompatibilité SIP et UPN. Vous devez créer un compte Salles Microsoft Teams avec les mêmes UPN et SIP pour qu’il fonctionne.
- Si vous utilisez un fournisseur d’authentification tiers pris en charge par Azure AD, il doit prise en charge un flux d’authentification actif via WS-Trust.
- N’utilisez pas de stratégies d’accès conditionnel au niveau de l’appareil pour un compte de ressource configuré avec l’application. Cela entraîne des échecs de connexion. Au lieu de cela, inscrivez un appareil dans Microsoft Intune et appliquez des stratégies de conformité. Pour plus d’informations, consultez [l’accès conditionnel et la conformité Intune pour Salles Microsoft Teams](conditional-access-and-compliance-for-devices.md).

### <a name="configure-exchange-server"></a>Configurer Exchange Server

Pour activer l’authentification moderne hybride dans Exchange Server, consultez [Comment configurer Exchange Server localement pour utiliser l’authentification moderne hybride](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="configure-skype-for-business-server"></a>Configurer Skype Entreprise Server

Pour activer l’authentification moderne hybride avec Skype Entreprise Server, consultez [Comment configurer Skype Entreprise localement pour utiliser l’authentification moderne hybride](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Supprimer ou désactiver Skype Entreprise et Exchange

Si votre configuration n’autorise pas l’authentification moderne hybride ou si vous devez supprimer ou désactiver l’authentification moderne hybride pour Exchange ou Skype Entreprise, consultez [Suppression ou désactivation de l’authentification moderne hybride de Skype Entreprise et Exchange](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha).

### <a name="azure-ad-conditional-access"></a>Accès conditionnel Azure AD

Vous pouvez configurer un compte de ressource utilisé avec Salles Microsoft Teams pour l’accès IP/basé sur l’emplacement. Pour plus d’informations, consultez [Accès conditionnel : Bloquer l’accès par emplacement](/azure/active-directory/conditional-access/howto-conditional-access-policy-location).

Pour plus d’informations sur la conformité des appareils, consultez [Les stratégies d’accès conditionnel prises en charge et de conformité Intune pour Salles Microsoft Teams](supported-ca-and-compliance-policies.md).

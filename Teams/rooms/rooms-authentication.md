---
title: Authentification dans Salles Microsoft Teams
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
description: Découvrez comment configurer l’authentification moderne pour Salles Microsoft Teams
ms.openlocfilehash: d38bf63e0ed1dc9e5cb52445fab88e617fda6169
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015194"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Authentification dans Salles Microsoft Teams

La gestion des comptes Salles Microsoft Teams est gérée au niveau de l’application. L’application se connecte à Microsoft Teams, Skype Entreprise et Exchange ressources du compte de ressource pour activer les appels et les expériences de réunion. salles Teams utilise un compte de ressources dédié pour permettre des fonctionnalités toujours opérationnelles, des scénarios d’appel (pour les appareils configurés avec un plan d’appels) et des mécanismes de verrouillage personnalisés. Cela signifie que l’authentification salles Teams se produit d’une autre façon que pour les appareils des utilisateurs finaux.  

L’authentification moderne est recommandée pour tous les clients qui utilisent des Salles Microsoft Teams’Microsoft 365 ou Office 365. Si vous avez un déploiement local de Exchange Server ou Skype Entreprise Server, configurez l’authentification moderne hybride avec Azure Active Directory (Azure AD) pour l’activer à l’aide de l’authentification moderne. [](/office365/enterprise/hybrid-modern-auth-overview)

L’authentification moderne est prise Salles Microsoft Teams version 4.4.25.0 et ultérieures.

## <a name="modern-authentication"></a>Authentification moderne

Lorsque vous utilisez l’authentification moderne avec l’application Salles Microsoft Teams, la bibliothèque d’authentification Active Directory (ADAL) est utilisée pour se connecter à Microsoft Teams, Exchange et Skype Entreprise. Le mécanisme d’authentification moderne utilise le type d’autorisation d’autorisation de mot de passe de propriétaire de ressource dans OAuth 2.0, qui ne nécessite aucune intervention de l’utilisateur. [](/azure/active-directory/develop/v2-oauth-ropc) C’est l’une des principales différences entre le fonctionnement de l’authentification moderne pour les comptes d’utilisateurs et les comptes de ressources utilisés par Salles Microsoft Teams. C’est pourquoi les comptes de ressources Salles Microsoft Teams ne doivent pas être configurés pour utiliser l’authentification multifacteur (MFA), l’authentification par carte à puce ou l’authentification basée sur un certificat client (disponible pour les utilisateurs finaux).

L’autre différence essentielle entre le fonctionnement de l’authentification moderne sur les appareils Salles Microsoft Teams et les utilisateurs finaux est que vous ne pouvez pas utiliser un compte de ressource pour appliquer des stratégies d’accès conditionnel au niveau de l’appareil dans Azure Active Directory et Endpoint Manager, car les informations sur l’appareil ne sont pas transmises lors de l’utilisation de ce type d’octroi. Au lieu de cela, vous pouvez inscrire un appareil au Microsoft Endpoint Manager et appliquer des stratégies de conformité à l’aide des instructions fournies dans la gestion des salles de réunion Teams avec [Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

## <a name="enable-modern-authentication-on-microsoft-teams-rooms"></a>Activer l’authentification moderne sur Salles Microsoft Teams

Pour Salles Microsoft Teams’utiliser l’authentification moderne avec les Skype Entreprise et Exchange, activez le paramètre côté client pour l’authentification moderne sur Salles Microsoft Teams. Vous pouvez le faire dans les paramètres de l’appareil ou dans le fichier de configuration XML.

> [!NOTE]
> Avant d’activer le paramètre côté client pour l’authentification moderne, assurez-vous que votre environnement est correctement installé pour utiliser l’authentification moderne.

### <a name="using-device-settings"></a>Utilisation des paramètres de l’appareil

1. Sur Salles Microsoft Teams, allez à **Plus** **(...).**
    
2. Sélectionnez **Paramètres,** puis entrez le nom d’utilisateur et le mot de passe de l’administrateur de l’appareil.
3. Sous **l’onglet Compte,** activer **l’authentification moderne,** puis sélectionner **Enregistrer et quitter.**

### <a name="using-the-xml-config-file"></a>Utilisation du fichier de config XML

Dans votre SkypeSettings.xml, définissez l’élément XML d’authentification moderne sur **True,** comme suit.

```XML
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Pour appliquer le paramètre, voir Gérer une console Salles Microsoft Teams à distance avec [un fichier de configuration XML.](xml-config-file.md)

## <a name="prepare-your-environment-for-modern-authentication"></a>Préparer votre environnement pour l’authentification moderne

Avant de commencer, assurez-vous de comprendre les modèles d’identité à utiliser Office 365 et Azure AD. Vous pouvez trouver plus d’informations sur [Office 365](/Office365/Enterprise/about-office-365-identity) modèles d’identité et Azure Active Directory et sur la synchronisation d’annuaires et d’identité hybride pour Microsoft 365 ou [Office 365.](/Office365/Enterprise/plan-for-directory-synchronization)

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Activer l’authentification moderne dans Microsoft 365 ou Office 365

Pour activer l’authentification moderne pour Exchange Online, voir [Activer l’authentification moderne dans Exchange Online.](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)

Nous vous recommandons de ne pas supprimer les stratégies d’authentification de base pour Exchange Online ni de désactiver l’authentification de base pour votre client tant que vous n’avez pas validé que les appareils Salles Microsoft Teams peuvent se connecter avec Exchange Online et Teams.

Pour plus d’informations sur la désactivation de l’authentification de base dans Exchange Online, voir Désactiver [l’authentification](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)de base dans Exchange Online.

## <a name="hybrid-modern-authentication"></a>Authentification moderne hybride

Pour garantir la réussite de l’authentification pour votre serveur Exchange local et/ou Skype Entreprise server, vous devez vous assurer que le compte de ressource utilisé avec Salles Microsoft Teams est configuré pour obtenir l’autorisation d’Azure AD.

salles Teams flux d’authentification varient en fonction de votre configuration d’authentification. Pour les clients utilisant un domaine géré, salles Teams utilise des informations d’identification de mot de passe de propriétaire de ressources [OAuth 2.0](/azure/active-directory/develop/v2-oauth-ropc) avec Azure Active Directory. Toutefois, pour les clients utilisant un domaine fédéré, [OAuth 2.0 SAML Bearer Assertion Flow](/azure/active-directory/develop/v2-saml-bearer-assertion) est utilisé.

> [!NOTE]
> Votre fournisseur d’identité peut avoir besoin de configurations ou de paramètres spécifiques pour l’intégration avec Azure Active Directory ou Office 365. Contactez votre fournisseur d’identité si vous avez besoin d’aide pour configurer l’authentification auprès salles Teams.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Conditions préalables spécifiques aux Salles Microsoft Teams

Les conditions préalables à l’authentification moderne dans votre topologie hybride sont couvertes par la vue d’ensemble de l’authentification moderne hybride et les conditions préalables d’utilisation avec des serveurs Skype Entreprise et Exchange [locaux.](/office365/enterprise/hybrid-modern-auth-overview) Toutes les conditions préalables abordées dans cet article s’appliquent.

Toutefois, étant donné [](https://tools.ietf.org/html/rfc6749#section-1.3.3) que Salles Microsoft Teams utilise l’autorisation d’informations d’identification de propriétaire de ressources et les API REST sous-jacentes pour l’authentification moderne, il est important de connaître les différences suivantes qui sont propres à Salles Microsoft Teams.

- Vous devez avoir Exchange Server 2016 CU8 ou une Exchange Server 2019 CU1 ou ultérieure.
- Vous devez avoir Skype Entreprise Server 2015 CU5 ou une Skype Entreprise Server 2019 ou ultérieure.
- L’mf n’est pas prise en charge, quelle que soit la topologie que vous avez.
- Salles Microsoft Teams ne prend pas en charge l’inégalisation des sip et des upN. Vous devez créer un Salles Microsoft Teams utilisateur avec les mêmes nom d’utilisateur utilisateur (UPN) et SIP pour qu’il fonctionne.
- Si vous utilisez un fournisseur d’authentification tiers pris en charge par Azure AD, il doit prendre en charge un flux d’authentification active via WS-Trust.
- N’utilisez pas de stratégies d’accès conditionnel au niveau de l’appareil pour un compte de ressource configuré avec l’application. Cette faisant, vous entraînerez des échecs de inscription. Au lieu de cela, inscrivez un appareil dans Microsoft Intune et appliquez les stratégies de conformité à l’aide des recommandations publiées dans La gestion des salles de réunion Teams [avec Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

### <a name="configure-exchange-server"></a>Configurer les Exchange Server

Pour activer l’authentification moderne hybride dans Exchange Server, voir comment configurer Exchange Server local pour utiliser l’authentification [moderne hybride.](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="configure-skype-for-business-server"></a>Configurer les Skype Entreprise Server

Pour activer l’authentification moderne hybride avec Skype Entreprise Server, voir comment configurer Skype Entreprise local pour utiliser l’authentification [moderne hybride.](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Supprimer ou désactiver des Skype Entreprise et des Exchange

Si votre installation ne permet pas l’authentification moderne hybride ou si vous devez supprimer ou désactiver l’authentification moderne hybride pour Exchange ou Skype Entreprise, voir Supprimer ou désactiver l’authentification moderne hybride de [Skype Entreprise et Exchange.](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)

### <a name="azure-ad-conditional-access"></a>Azure AD’accès conditionnel

Vous pouvez configurer un compte de ressource utilisé avec Salles Microsoft Teams pour un accès IP/basé sur l’emplacement. Pour plus d’informations, [voir Accès conditionnel : bloquer l’accès par emplacement.](/azure/active-directory/conditional-access/howto-conditional-access-policy-location)

Aucune autre stratégie d’accès conditionnel n’est prise en charge. Pour plus d’informations sur la conformité des appareils, voir Gérer Teams salles de [réunion avec Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

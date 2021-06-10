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
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-collaboration
description: Découvrez comment configurer l’authentification moderne pour Salles Microsoft Teams
ms.openlocfilehash: 93577c74005c8ad266739da0991f31e384a57ba6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117482"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Authentification dans Salles Microsoft Teams

La gestion des comptes Salles Microsoft Teams appareils mobiles est gérée au niveau de l’application. L’application se connecte à Microsoft Teams, Skype Entreprise et Exchange pour obtenir des ressources pour le compte de salle afin d’activer les appels et les expériences de réunion. L’appareil est agnostique de façon à ce qu’il soit toujours possible d’utiliser des fonctionnalités, des scénarios d’appel (pour les appareils configurés avec un plan d’appels) et des mécanismes de verrouillage personnalisés implémentés sur ces appareils. Cela signifie que l’authentification de ces appareils est différente de celle des appareils des utilisateurs finaux.  

L’authentification moderne est recommandée pour tous les clients qui utilisent Salles Microsoft Teams appareils mobiles avec Microsoft 365 ou Office 365. Si vous avez un déploiement local de serveur Exchange ou de serveur [](/office365/enterprise/hybrid-modern-auth-overview) Skype Entreprise, configurez l’authentification moderne hybride avec Azure Active Directory (Azure AD) pour l’activer à l’aide de l’authentification moderne.

L’authentification moderne est prise Salles Microsoft Teams version 4.4.25.0 et ultérieures.

## <a name="modern-authentication"></a>Authentification moderne

Lorsque vous utilisez l’authentification moderne avec l’application Salles Microsoft Teams, la bibliothèque d’authentification Active Directory (ADAL) est utilisée pour se connecter à Microsoft Teams, Exchange et Skype Entreprise. Un Salles Microsoft Teams est un appareil partagé et effectue un redémarrage nocturne afin de garantir un fonctionnement fluide et de récupérer des mises à jour critiques du système d’exploitation, du pilote, du microprogramme ou des applications. Le mécanisme d’authentification moderne utilise le type d’autorisation d’autorisation de mot de passe de propriétaire de ressource dans OAuth 2.0, qui ne nécessite aucune intervention de l’utilisateur. [](/azure/active-directory/develop/v2-oauth-ropc) C’est l’une des principales différences entre le fonctionnement de l’authentification moderne pour les comptes d’utilisateurs et les comptes de ressources utilisés par l Salles Microsoft Teams application. C’est pourquoi les comptes de ressources Salles Microsoft Teams ne doivent pas être configurés pour utiliser l’authentification multifacteur (MFA), l’authentification par carte à puce ou l’authentification basée sur un certificat client (disponible pour les utilisateurs finaux).

L’autre différence essentielle entre le fonctionnement de l’authentification moderne sur les appareils Salles Microsoft Teams et les appareils des utilisateurs finaux est que vous ne pouvez pas utiliser un compte de ressource pour appliquer des stratégies d’accès conditionnel au niveau de l’appareil dans Azure Active Directory et Endpoint Manager, car les informations sur l’appareil ne sont pas transmises lors de l’utilisation de ce type d’octroi. Au lieu de cela, vous pouvez inscrire un appareil au Microsoft Endpoint Manager et appliquer des stratégies de conformité à l’aide des instructions fournies dans la gestion des salles de réunion Teams avec [Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>Activer l’authentification moderne sur un Salles Microsoft Teams appareil

Pour Salles Microsoft Teams’utiliser l’authentification moderne avec Skype Entreprise et Exchange, activez le paramètre côté client pour l’authentification moderne sur l Salles Microsoft Teams appareil. Vous pouvez le faire dans les paramètres de l’appareil ou dans le fichier de configuration XML.

> [!NOTE]
> Avant d’activer le paramètre côté client pour l’authentification moderne, assurez-vous que votre environnement est correctement installé pour utiliser l’authentification moderne.

### <a name="using-device-settings"></a>Utilisation des paramètres de l’appareil

1. Sur l’appareil Salles d’équipe Microsoft, allez **à Autres** (**...**).
    
2. Sélectionnez **Paramètres,** puis entrez le nom d’utilisateur et le mot de passe de l’administrateur de l’appareil.
3. Sous **l’onglet Compte,** activer **l’authentification moderne,** puis sélectionner **Enregistrer et quitter.**

### <a name="using-the-xml-config-file"></a>Utilisation du fichier de config XML

Dans votre SkypeSettings.xml, définissez l’élément XML d’authentification moderne sur **True,** comme suit.

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Pour appliquer le paramètre, voir Gérer une console Salles Microsoft Teams à distance avec [un fichier de configuration XML.](xml-config-file.md)

## <a name="prepare-your-environment-for-modern-authentication"></a>Préparer votre environnement pour l’authentification moderne

Avant de commencer, assurez-vous de comprendre les modèles d’identité à utiliser avec Office 365 et Azure AD. Vous pouvez trouver plus d’informations sur [Office 365](/Office365/Enterprise/about-office-365-identity) modèles d’identité et Azure Active Directory sur l’identité hybride et la synchronisation d’annuaires pour Microsoft 365 ou [Office 365.](/Office365/Enterprise/plan-for-directory-synchronization)

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Activer l’authentification moderne dans Microsoft 365 ou Office 365

Pour activer l’authentification moderne pour Exchange Online, voir [Activer l’authentification moderne dans Exchange Online.](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) Si vous utilisez Skype Entreprise Online, vous devez également vous assurer que l’authentification moderne est mise en Skype Entreprise Online. Pour en savoir plus, voir [Skype Entreprise Online : activer votre client pour l’authentification moderne.](https://aka.ms/SkypeModernAuth)

Nous vous recommandons de ne pas supprimer les stratégies d’authentification de base pour Exchange Online ni désactiver l’authentification de base pour votre client tant que vous n’avez pas validé que les appareils Salles Microsoft Teams peuvent se connecter avec Exchange Online, Teams et Skype Entreprise Online.

Pour plus d’informations sur la désactivation de l’authentification de base dans Exchange Online, voir Désactiver [l’authentification](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)de base dans Exchange Online.

## <a name="hybrid-modern-authentication"></a>Authentification moderne hybride

Pour garantir la réussite de l’authentification auprès de votre serveur Exchange local et/ou Skype Entreprise server, vous devez vous assurer que le compte de ressource utilisé avec Salles Microsoft Teams est configuré pour obtenir l’autorisation d’Azure AD. 

salles Teams flux d’authentification varient en fonction de votre configuration d’authentification. Pour les clients qui utilisent un domaine géré, salles Teams utilise les informations d’identification de mot de passe de propriétaire de ressources [OAuth 2.0](/azure/active-directory/develop/v2-oauth-ropc) avec Azure Active Directory. Toutefois, pour les clients utilisant un domaine fédéré, [OAuth 2.0 SAML Bearer Assertion Flow](/azure/active-directory/develop/v2-saml-bearer-assertion) est utilisé.

> [!NOTE]
> Votre fournisseur d’identité peut avoir besoin de configurations ou de paramètres spécifiques pour l’intégration avec Azure Active Directory ou Office 365. Contactez votre fournisseur d’identité si vous avez besoin d’aide pour configurer l’authentification auprès salles Teams.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Conditions préalables spécifiques aux Salles Microsoft Teams

Les conditions préalables à l’authentification moderne dans votre topologie hybride sont couvertes par la vue d’ensemble de l’authentification moderne hybride et les conditions préalables d’utilisation avec des serveurs Skype Entreprise et Exchange [locaux.](/office365/enterprise/hybrid-modern-auth-overview) Toutes les conditions préalables abordées dans cet article s’appliquent.

Toutefois, étant donné [](https://tools.ietf.org/html/rfc6749#section-1.3.3) que Salles Microsoft Teams utilise l’autorisation des informations d’identification de propriétaire de ressources et les API REST sous-jacentes pour l’authentification moderne, il est important de connaître les différences suivantes qui sont propres à Salles Microsoft Teams.

- Vous devez avoir Exchange Server 2016 CU8 ou une Exchange Server 2019 CU1 ou ultérieure.
- Vous devez avoir Skype Entreprise Server 2015 CU5 ou une Skype Entreprise Server 2019 ou ultérieure.
- L’mf n’est pas prise en charge, quelle que soit la topologie que vous avez.
- Salles Microsoft Teams ne prend pas en charge l’inégalisation de sip et d’UPN. Vous devez créer un Salles Microsoft Teams utilisateur avec les mêmes nom d’utilisateur utilisateur (UPN) et SIP pour qu’il fonctionne.
- Si vous utilisez un fournisseur d’authentification tiers pris en charge par Azure AD, il doit prendre en charge un flux d’authentification active via WS-Trust.
- N’utilisez pas de stratégies d’accès conditionnel au niveau de l’appareil pour un compte de ressource configuré avec l’application. Cette faisant, vous entraînerez des échecs de inscription. Au lieu de cela, inscrivez un appareil dans Microsoft Intune et appliquez les stratégies de conformité à l’aide des recommandations publiées dans La gestion des salles de réunion Teams [avec Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

### <a name="configure-exchange-server"></a>Configurer Exchange Server

Pour activer l’authentification moderne hybride dans Exchange Server, voir comment configurer Exchange Server local pour utiliser l’authentification [moderne hybride.](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="configure-skype-for-business-server"></a>Configurer Skype Entreprise Server

Pour activer l’authentification moderne hybride avec Skype Entreprise Server, voir comment configurer Skype Entreprise local pour utiliser l’authentification [moderne hybride.](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Supprimer ou désactiver des Skype Entreprise et des Exchange

Si votre installation ne permet pas l’authentification moderne hybride ou si vous devez supprimer ou désactiver l’authentification moderne hybride pour Exchange ou Skype Entreprise, voir Supprimer ou désactiver l’authentification moderne hybride de [Skype Entreprise et Exchange.](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)

### <a name="azure-ad-conditional-access"></a>Accès conditionnel Azure AD

Vous pouvez configurer un compte de ressource utilisé avec Salles Microsoft Teams pour un accès IP/basé sur l’emplacement. Pour plus d’informations, [voir Accès conditionnel : bloquer l’accès par emplacement.](/azure/active-directory/conditional-access/howto-conditional-access-policy-location)

Aucune autre stratégie d’accès conditionnel n’est prise en charge. Pour plus d’informations sur la conformité des [appareils, voir Gérer Teams salles de réunion avec Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)
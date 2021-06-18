---
title: Authentification dans les salles Microsoft Teams
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
description: Découvrir comment configurer l’authentification moderne pour les salles Microsoft Teams
ms.openlocfilehash: 93577c74005c8ad266739da0991f31e384a57ba6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117482"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Authentification dans les salles Microsoft Teams

La gestion des comptes pour les appareils Salle Microsoft Teams est gérée au niveau de l’application. L’application se connecte à Microsoft Teams, Skype Entreprise et Exchange pour obtenir des ressources pour le compte de salle afin d’activer les appels et les expériences de réunion. L’appareil est agnostique de façon à ce qu’il offre des fonctionnalités toujours opérationnelles, des scénarios d’appel (pour les appareils configurés avec un plan d’appels) et des mécanismes de verrouillage personnalisés implémentés sur ces appareils. Cela signifie que l’authentification pour ces appareils se produit d’une autre façon que pour les appareils des utilisateurs finaux.  

L’authentification moderne est recommandée pour tous les clients qui utilisent des appareils Salles Microsoft Teams avec Microsoft 365 ou Office 365. Si vous avez un déploiement local d’Exchange Server ou [](/office365/enterprise/hybrid-modern-auth-overview) de Skype Entreprise, configurez l’authentification moderne hybride avec Azure Active Directory (Azure AD) pour l’activer à l’aide de l’authentification moderne.

L’authentification moderne est prise en charge dans les salles Microsoft Teams version 4.4.25.0 et ultérieures.

## <a name="modern-authentication"></a>Authentification moderne

Lorsque vous utilisez l’authentification moderne avec l’application Salles Microsoft Teams, la bibliothèque d’authentification Active Directory (ADAL) est utilisée pour se connecter à Microsoft Teams, Exchange et Skype Entreprise. Un appareil Salles Microsoft Teams est un appareil partagé qui effectue un redémarrage nocturne afin de garantir un fonctionnement fluide et de mettre à jour le système d’exploitation, le pilote, le microprogramme ou l’application. Le mécanisme d’authentification moderne utilise le type d’autorisation d’autorisation de mot de passe de propriétaire de ressource dans OAuth 2.0, qui ne nécessite aucune intervention de l’utilisateur. [](/azure/active-directory/develop/v2-oauth-ropc) C’est l’une des principales différences entre le fonctionnement de l’authentification moderne pour les comptes d’utilisateurs et les comptes de ressources utilisés par l’application Salles Microsoft Teams. Pour cette raison, les comptes de ressources des salles Microsoft Teams ne doivent pas être configurés pour utiliser l’authentification multifacteur ( MFA), l’authentification par carte à puce ou l’authentification basée sur un certificat client (disponible pour les utilisateurs finaux).

L’autre différence essentielle entre le fonctionnement de l’authentification moderne sur les appareils Microsoft Teams Rooms et les appareils des utilisateurs finaux est que vous ne pouvez pas utiliser un compte de ressource pour appliquer des stratégies d’accès conditionnel au niveau de l’appareil dans Azure Active Directory et Endpoint Manager, car les informations sur l’appareil ne sont pas transmises lors de l’utilisation de ce type d’octroi. Au lieu de cela, vous pouvez inscrire un appareil dans Microsoft Endpoint Manager et appliquer des stratégies de conformité à l’aide des instructions fournies dans la gestion des salles de réunion Teams avec [Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>Activer l’authentification moderne sur un appareil Salles Microsoft Teams

Pour que les salles Microsoft Teams utilisent l’authentification moderne avec Skype Entreprise et Exchange, activez le paramètre côté client pour l’authentification moderne sur l’appareil Salles Microsoft Teams. Vous pouvez le faire dans les paramètres de l’appareil ou dans le fichier de configuration XML.

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

Pour appliquer le paramètre, consultez Gérer les paramètres d’une console de salles Microsoft Teams à distance [avec un fichier de configuration XML.](xml-config-file.md)

## <a name="prepare-your-environment-for-modern-authentication"></a>Préparer votre environnement pour l’authentification moderne

Avant de commencer, assurez-vous de comprendre les modèles d’identité à utiliser avec Office 365 et Azure AD. Vous trouverez davantage d’informations sur les modèles d’identité [Office 365 et Azure Active Directory,](/Office365/Enterprise/about-office-365-identity) ainsi que sur la synchronisation d’annuaires et d’identité hybride pour [Microsoft 365 ou Office 365.](/Office365/Enterprise/plan-for-directory-synchronization)

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Activer l’authentification moderne dans Microsoft 365 ou Office 365

Pour activer l’authentification moderne pour Exchange Online, voir [Activer l’authentification moderne dans Exchange Online.](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) Si vous utilisez Skype Entreprise Online, vous devez également vous assurer que l’authentification moderne est mise en place pour Skype Entreprise Online. Pour en savoir plus, [consultez Skype Entreprise Online : Activer votre client pour l’authentification moderne.](https://aka.ms/SkypeModernAuth)

Nous vous recommandons de ne pas supprimer les stratégies d’authentification de base pour Exchange Online, ni de désactiver l’authentification de base pour votre client tant que vous n’avez pas validé que les appareils salles Microsoft Teams peuvent se connecter avec Exchange Online, Teams et Skype Entreprise Online.

Pour plus d’informations sur la désactivation de l’authentification de base dans Exchange Online, voir Désactiver [l’authentification](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)de base dans Exchange Online.

## <a name="hybrid-modern-authentication"></a>Authentification moderne hybride

Pour garantir la réussite de l’authentification pour votre serveur Exchange local et/ou Skype Entreprise, vous devez vous assurer que le compte de ressource utilisé avec les salles Microsoft Teams est configuré pour obtenir l’autorisation d’Azure AD. 

Les flux d’authentification des salles Teams varient en fonction de votre configuration d’authentification. Pour les clients utilisant un domaine géré, les salles Teams utilisent les informations d’identification de mot de passe de propriétaire de ressources [OAuth 2.0](/azure/active-directory/develop/v2-oauth-ropc) avec Azure Active Directory. Toutefois, pour les clients utilisant un domaine fédéré, [OAuth 2.0 SAML Bearer Assertion Flow](/azure/active-directory/develop/v2-saml-bearer-assertion) est utilisé.

> [!NOTE]
> Votre fournisseur d’identité peut avoir besoin de configurations ou de paramètres spécifiques pour l’intégration avec Azure Active Directory ou Office 365. Contactez votre fournisseur d’identité si vous avez besoin d’aide pour configurer l’authentification avec salles Teams.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Conditions préalables spécifiques aux salles Microsoft Teams

Les conditions préalables à l’authentification moderne dans votre topologie hybride sont couvertes par la vue d’ensemble de l’authentification moderne hybride et les conditions préalables d’utilisation avec les serveurs Skype Entreprise et [Exchange locaux.](/office365/enterprise/hybrid-modern-auth-overview) Toutes les conditions préalables abordées dans cet article s’appliquent.

Toutefois, étant donné que les [salles](https://tools.ietf.org/html/rfc6749#section-1.3.3) Microsoft Teams utilisent l’autorisation d’identification de mot de passe de propriétaire de ressource et les API REST sous-jacentes pour l’authentification moderne, il est important de connaître les différences suivantes qui sont spécifiques aux salles Microsoft Teams.

- Vous devez avoir Exchange Server 2016 CU8 ou une Exchange Server 2019 CU1 ou ultérieure.
- Vous devez avoir Skype Entreprise Server 2015 CU5 ou une date ultérieure, ou Skype Entreprise Server 2019 ou une date ultérieure.
- L’mf n’est pas prise en charge, quelle que soit la topologie que vous avez.
- Les salles Microsoft Teams ne prend pas en charge l’inégalisation des systèmes d’exploitation SIP et UPN. Vous devez créer un compte Salles Microsoft Teams avec les mêmes nom d’utilisateur utilisateur et SIP pour qu’il fonctionne.
- Si vous utilisez un fournisseur d’authentification tiers pris en charge par Azure AD, il doit prendre en charge un flux d’authentification active via WS-Trust.
- N’utilisez pas de stratégies d’accès conditionnel au niveau de l’appareil pour un compte de ressource configuré avec l’application. Cette faisant, vous entraînerez des échecs de inscription. Instead, enroll a device in Microsoft Intune and apply compliance policies by using the guidance published in [Managing Teams Meeting Rooms with Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

### <a name="configure-exchange-server"></a>Configurer les Exchange Server

Pour activer l’authentification moderne hybride dans Exchange Server, voir Comment configurer Exchange Server local pour utiliser l’authentification [moderne hybride.](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="configure-skype-for-business-server"></a>Configurer Skype Entreprise Server

Pour activer l’authentification moderne hybride avec Skype Entreprise Server, découvrez comment configurer Skype Entreprise en local pour utiliser l’authentification [moderne hybride.](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Supprimer ou désactiver Skype Entreprise et Exchange

Si votre installation ne permet pas l’authentification moderne hybride ou si vous devez supprimer ou désactiver l’authentification moderne hybride pour Exchange ou Skype Entreprise, consultez La suppression ou la désactivation de l’authentification moderne hybride à partir de Skype Entreprise et [Exchange.](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)

### <a name="azure-ad-conditional-access"></a>Accès conditionnel Azure AD

Vous pouvez configurer un compte de ressource utilisé avec Salles Microsoft Teams pour un accès IP/basé sur l’emplacement. Pour plus d’informations, [voir Accès conditionnel : bloquer l’accès par emplacement.](/azure/active-directory/conditional-access/howto-conditional-access-policy-location)

Aucune autre stratégie d’accès conditionnel n’est prise en charge. Pour plus d’informations sur la conformité des appareils, voir [Gérer les salles de réunion Teams avec Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)
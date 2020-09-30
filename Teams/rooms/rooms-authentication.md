---
title: Authentification dans les salles de Microsoft teams
ms.author: v-lanac
author: lanachin
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
description: Découvrir comment configurer l’authentification moderne pour les salles Microsoft teams
ms.openlocfilehash: ba6259efac5d1e429bbcc33aeaef19759930e345
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308257"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Authentification dans les salles de Microsoft teams

La gestion des comptes pour les appareils Microsoft teams est gérée au niveau de l’application. L’application se connecte à Microsoft Teams, à Skype entreprise et à Exchange pour obtenir des ressources pour le compte de la salle afin d’activer les appels et les expériences de réunion. Le compte est maintenu de manière indépendante pour permettre des fonctionnalités toujours disponibles, des scénarios d’appel (pour les appareils configurés avec un plan d’appels) et des mécanismes de verrouillage personnalisés implémentés sur ces appareils. Cela signifie que l’authentification de ces périphériques se produit de manière différente de celle des appareils utilisateurs finaux.  

L’authentification moderne est recommandée pour tous les clients utilisant des appareils Microsoft teams en Microsoft 365 ou Office 365. Si vous avez un déploiement local d’Exchange Server ou de Skype entreprise Server, configurez [l’authentification moderne hybride](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview) avec Azure Active Directory (Azure AD) pour permettre l’utilisation de l’authentification moderne.

L’authentification moderne est prise en charge dans Microsoft Teams (version 4.4.25.0 et versions ultérieures).

## <a name="modern-authentication"></a>Authentification moderne

Lorsque vous utilisez l’authentification moderne avec l’application Microsoft teams Resources, la bibliothèque d’authentification Active Directory (ADAL) est utilisée pour se connecter à Microsoft Teams, Exchange et Skype entreprise. Un appareil de salle Microsoft teams est un appareil partagé et effectue un redémarrage nocturne pour garantir un fonctionnement fluide et obtenir des mises à jour de systèmes d’exploitation, de microprogrammes ou de microprogrammes importants. Le mécanisme d’authentification moderne utilise le type d’autorisation d’accès au [mot de passe du propriétaire de ressources](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth-ropc) dans OAuth 2,0, qui ne nécessite aucune intervention de l’utilisateur. Il s’agit de l’une des principales différences entre le fonctionnement de l’authentification moderne pour les comptes d’utilisateurs et les comptes de ressources qui sont utilisés par l’application Microsoft Teams. Pour cette raison, les comptes de ressources de Microsoft Teams ne doivent pas être configurés de manière à utiliser l’authentification multifacteur (MFA), l’authentification par carte à puce ou l’authentification par certificat client (qui sont disponibles pour les utilisateurs finaux).

La différence principale entre le fonctionnement de l’authentification moderne sur les appareils Microsoft teams et les appareils utilisateurs finaux réside dans le fait que vous ne pouvez pas utiliser un compte de ressource pour appliquer des stratégies d’accès conditionnel au niveau de l’appareil dans Azure Active Directory et le gestionnaire de points de terminaison car les informations d’appareil ne sont pas transmises lors de l’utilisation de ce type d’autorisation. Au lieu de cela, vous pouvez inscrire un appareil dans le gestionnaire de points de terminaison Microsoft et appliquer des stratégies de conformité à l’aide des recommandations fournies dans [gestion des salles de réunion d’équipes avec Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230).

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>Activer l’authentification moderne sur un appareil Microsoft teams

Pour que Microsoft teams se réutilise l’authentification moderne dans Skype entreprise et Exchange, activez le paramètre côté client pour l’authentification moderne sur le périphérique Microsoft Teams. Pour cela, vous pouvez utiliser les paramètres de l’appareil ou le fichier de configuration XML.

> [!NOTE]
> Avant d’activer le paramètre côté client pour l’authentification moderne, assurez-vous que votre environnement est correctement configuré pour utiliser l’authentification moderne.

### <a name="using-device-settings"></a>Utiliser les paramètres de l’appareil

1. Sur l’appareil Microsoft Teams, accédez à **plus** (**...**).
    
2. Sélectionnez **paramètres**, puis entrez le nom d’utilisateur et le mot de passe de l’administrateur de l’appareil.
3. Accédez à l’onglet **compte** , activez **l’authentification moderne**, puis sélectionnez **enregistrer et quitter**.

### <a name="using-the-xml-config-file"></a>Utilisation du fichier de configuration XML

Dans votre fichier SkypeSettings.xml, définissez l’élément XML d’authentification moderne sur **true**, comme suit.

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Pour appliquer le paramètre, voir [gérer les paramètres de la console Microsoft teams à distance à l’aide d’un fichier de configuration XML](xml-config-file.md).

## <a name="prepare-your-environment-for-modern-authentication"></a>Préparer votre environnement pour l’authentification moderne

Avant de commencer, assurez-vous de bien comprendre les modèles d’identité à utiliser avec Office 365 et Azure AD. Vous pouvez en savoir plus sur les [modèles d’identité Office 365 et Azure Active Directory](https://docs.microsoft.com/Office365/Enterprise/about-office-365-identity) et sur l' [identité hybride et la synchronisation d’annuaires pour Microsoft 365 ou Office 365](https://docs.microsoft.com/Office365/Enterprise/plan-for-directory-synchronization).

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Activer l’authentification moderne dans Microsoft 365 ou Office 365

Pour activer l’authentification moderne pour Exchange Online, voir [activer l’authentification moderne dans Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online). Si vous utilisez Skype entreprise Online, vous devez également vérifier que l’authentification moderne est activée pour Skype entreprise online. Pour en savoir plus, reportez-vous à [la rubrique Skype entreprise Online : activer votre client pour l’authentification moderne](https://aka.ms/SkypeModernAuth).

Nous vous conseillons de ne pas supprimer les stratégies d’authentification de base pour Exchange Online ou de désactiver l’authentification de base pour votre client tant que vous n’avez pas vérifié que les appareils de la salle Microsoft teams peuvent se connecter à l’aide d’Exchange Online, teams et de Skype entreprise online.

Pour plus d’informations sur la désactivation de l’authentification de base dans Exchange Online, voir [désactiver l’authentification de base dans Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online).

## <a name="hybrid-modern-authentication"></a>Authentification moderne hybride

Pour garantir une authentification réussie de votre serveur Exchange local et/ou de Skype entreprise Server, vous devez vous assurer que le compte de ressources utilisé avec les salles de Microsoft teams est configuré pour obtenir l’autorisation d’Azure AD. 

Les flux d’authentification par salle d’équipe varient en fonction de votre configuration d’authentification. Pour les clients qui utilisent un domaine géré, teams utilise [les informations d’identification du mot de passe du propriétaire de ressources 2,0 OAuth](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth-ropc) avec Azure Active Directory. Toutefois, pour les clients qui utilisent un domaine fédéré, le [flux d’assertion du porteur SAML 2,0](https://docs.microsoft.com/azure/active-directory/develop/v2-saml-bearer-assertion) est utilisé.

> [!NOTE]
> Votre fournisseur d’identité doit avoir besoin de configurations ou de paramètres spécifiques pour l’intégration avec Azure Active Directory ou Office 365. Contactez votre fournisseur d’identité si vous avez besoin d’aide pour configurer l’authentification auprès des salles d’équipe.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Éléments requis spécifiques aux salles de Microsoft teams

La configuration requise pour activer l’authentification moderne dans votre topologie hybride est abordée dans la [vue d’ensemble de l’authentification moderne hybride et les prérequis pour une utilisation avec des serveurs Skype entreprise et Exchange locaux](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview). Tous les éléments requis mentionnés dans l’article s’appliquent.

Toutefois, étant donné que Microsoft teams est compatible avec les [informations d’identification du mot de passe](https://tools.ietf.org/html/rfc6749#section-1.3.3) et les API REST sous-jacentes pour l’authentification moderne, il existe d’importantes différences qui sont spécifiques aux salles de Microsoft Teams.

- Vous devez disposer d’Exchange Server 2016 CU8 ou version ultérieure, ou d’Exchange Server 2019 CU1 ou version ultérieure.
- Vous devez disposer de Skype entreprise Server 2015 CU5 ou version ultérieure, ou de Skype entreprise Server 2019 ou version ultérieure.
- L’authentification multifacteur n’est pas prise en charge, quelle que soit la topologie que vous utilisez.
- Les salles de Microsoft Teams ne prennent pas en charge les incompatibilités SIP et UPN. Pour pouvoir fonctionner, vous devez créer un compte Microsoft teams avec les mêmes nom d’utilisateur principal et SIP.
- Si vous utilisez un fournisseur d’authentification tiers pris en charge par Azure AD, il doit prendre en charge un flux d’authentification actif via WS-Trust.
- N’utilisez pas de stratégies d’accès conditionnel au niveau de l’appareil pour un compte de ressources configuré avec l’application. Cela entraînera des échecs de connexion. Au lieu de cela, inscrivez un appareil dans Microsoft Intune et appliquez les stratégies de conformité à l’aide des instructions publiées dans [gestion des salles de réunion d’équipes avec Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230).

### <a name="configure-exchange-server"></a>Configurer Exchange Server

Pour activer l’authentification moderne hybride dans Exchange Server, reportez-vous [à la rubrique Configuration d’Exchange Server local pour utiliser l’authentification moderne hybride](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="configure-skype-for-business-server"></a>Configurer Skype entreprise Server

Pour activer l’authentification moderne hybride avec Skype entreprise Server, reportez-vous [à la configuration de Skype entreprise sur site pour utiliser l’authentification moderne hybride](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Suppression ou désactivation de Skype entreprise et Exchange

Si votre configuration n’autorise pas l’authentification moderne hybride ou si vous devez supprimer ou désactiver l’authentification moderne hybride pour Exchange ou Skype entreprise, reportez-vous à la rubrique [retrait ou désactivation de l’authentification moderne hybride de Skype entreprise et Exchange](https://docs.microsoft.com/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha).

### <a name="azure-ad-conditional-access"></a>Accès conditionnel Azure AD

Vous pouvez configurer un compte de ressources utilisé avec les salles de Microsoft teams pour l’accès par adresse IP/par emplacement. Pour en savoir plus, voir [accès conditionnel : bloquer l’accès par emplacement](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-location).

Aucune autre stratégie d’accès conditionnel n’est prise en charge. Pour plus d’informations sur la compatibilité des appareils, voir [gestion des salles de réunion teams avec Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230).  

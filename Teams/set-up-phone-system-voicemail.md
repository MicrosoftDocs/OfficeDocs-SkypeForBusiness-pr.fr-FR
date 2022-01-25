---
title: Configurer la Messagerie vocale cloud
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Découvrez comment configurer des Messagerie vocale infonuagique pour vos utilisateurs.
ms.openlocfilehash: cf4edb7043c3d9965f2f01710f1ed9e7fa7f96b8
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2022
ms.locfileid: "62191075"
---
# <a name="set-up-cloud-voicemail"></a>Configurer la Messagerie vocale cloud

Cet article s’adresse aux administrateurs Microsoft 365 administrateur Office 365, comme décrit dans la page À propos des rôles d’administrateur qui souhaite configurer la fonctionnalité Messagerie vocale infonuagique pour tous les utilisateurs de l’entreprise. [](/microsoft-365/admin/add-users/about-admin-roles) Messagerie vocale infonuagique nécessite Exchange boîtes aux lettres pour les utilisateurs dans lequel ils déposent les messages vocaux. Il ne prend pas en charge les systèmes de courrier tiers. Pour plus Exchange Online conditions de licence requises, voir [Exchange Online description du service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans)

## <a name="cloud-voicemail-for-teams-users"></a>Messagerie vocale infonuagique pour Teams utilisateurs

Pour Teams utilisateurs, Messagerie vocale infonuagique est automatiquement installé et mis en service. Une licence Microsoft Teams Téléphone licence de licence n’est pas nécessaire pour Messagerie vocale infonuagique.

## <a name="help-your-users-learn-teams-voicemail-features"></a>Aider vos utilisateurs à découvrir Teams fonctionnalités de messagerie vocale

Nous avons les informations suivantes pour vos utilisateurs sur l’utilisation et la gestion de la messagerie vocale dans Teams :

- [Consulter votre messagerie vocale dans Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [Gérer vos paramètres d’appel dans Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)

## <a name="setting-up-cloud-voicemail-to-work-with-on-premises-users"></a>Configuration d Messagerie vocale infonuagique de travail avec les utilisateurs locaux

Vous pouvez utiliser Messagerie vocale infonuagique pour fournir des fonctionnalités de messagerie vocale à vos utilisateurs qui ont des boîtes aux lettres sur vos serveurs Exchange, ou aux utilisateurs qui utilisent Skype Entreprise Server. Cette section fournit des informations pour ces scénarios. 

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurer des utilisateurs Messagerie vocale infonuagique boîtes aux Exchange Server

Les informations suivantes ont pour sujet la configuration Messagerie vocale infonuagique à travailler avec les Microsoft Teams Téléphone qui ont leur boîte aux lettres sur Exchange Server.

1. Les messages vocaux sont remis aux boîtes aux lettres des Exchange via SMTP acheminés via Exchange Online Protection. Pour permettre la remise de ces messages, assurez-vous que les connecteurs Exchange sont correctement configurés entre vos serveurs Exchange et vos Exchange Online Protection ; [Utiliser des connecteurs pour configurer le courrier Flow.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

2. Pour activer les fonctionnalités de messagerie vocale telles que la personnalisation des messages d’accueil et de la messagerie vocale visuelle dans les clients Skype Entreprise, une connexion de Microsoft 365 ou Office 365 à la boîte aux lettres de serveur Exchange via les services web Exchange est requise. Pour activer cette connectivité, vous devez configurer le nouveau protocole d’authentification Oauth Exchange décrit dans Configurer l’authentification [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)entre les organisations Exchange et Exchange Online ou exécuter l’Assistant Exchange Hybride à partir d’Exchange 2013 CU5 ou version supérieure. En outre, vous devez configurer l’intégration et Oauth entre Skype Entreprise Online et le serveur Exchange décrits dans Configurer l’intégration et [oAuth](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)entre Skype Entreprise Online et Exchange Server.

### <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Configurer des Messagerie vocale infonuagique pour Skype Entreprise Server utilisateurs

Pour configurer les utilisateurs Skype Entreprise serveur pour Messagerie vocale infonuagique, voir Planifier le service Messagerie vocale infonuagique pour les [utilisateurs locaux.](/skypeforbusiness/hybrid/plan-cloud-voicemail)

## <a name="enabling-protected-voicemail-in-your-organization"></a>Activation de la messagerie vocale protégée dans votre organisation

Lorsqu’un utilisateur laisse un message vocal pour un utilisateur de votre organisation, ce dernier est remis dans la boîte aux lettres de l’utilisateur sous la mesure d’une pièce jointe. En utilisant des règles de flux de courrier pour appliquer le chiffrement des messages, vous pouvez empêcher le courrier d’être transmis à d’autres destinataires. Lorsque vous activez des messages vocaux protégés, les utilisateurs peuvent écouter les messages vocaux protégés en appelant leur boîte aux lettres vocale ou en ouvrant le message dans Outlook, Outlook sur le web ou Outlook pour Android ou iOS. Les messages vocaux protégés ne peuvent pas être ouverts dans des Skype Entreprise ou Microsoft Teams.

Pour plus d’informations sur le chiffrement des messages, voir Définir les règles de [flux de courrier pour chiffrer les messages électroniques.](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)

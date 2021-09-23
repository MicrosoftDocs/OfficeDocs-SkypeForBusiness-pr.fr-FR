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
description: 'Découvrez comment configurer des Messagerie vocale infonuagique pour vos utilisateurs. '
ms.openlocfilehash: 37cf89d4c728cab491d0312762a2c845bb711dcd
ms.sourcegitcommit: 5f19df90443810e027085f8b38d22218e4123a16
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2021
ms.locfileid: "59482418"
---
# <a name="set-up-cloud-voicemail"></a>Configurer la Messagerie vocale cloud

Cet article s’adresse aux administrateurs Microsoft 365 administrateur Office 365, comme décrit dans la page À propos des rôles d’administrateur qui souhaite configurer la fonctionnalité Messagerie vocale infonuagique pour tous les utilisateurs de l’entreprise. [](/microsoft-365/admin/add-users/about-admin-roles)

> [!NOTE]
> Messagerie vocale infonuagique prend en charge le dépôt de messages vocaux uniquement dans une boîte aux lettres Exchange et ne prend pas en charge les systèmes de messagerie tiers. 

> [!NOTE]
> Lorsqu’un délégué répond à un appel au nom d’un délégant, les notifications ne sont pas disponibles dans Messagerie vocale infonuagique. Les utilisateurs peuvent recevoir des notifications pour les appels manqués.

## <a name="cloud-voicemail-for-teams-users"></a>Messagerie vocale infonuagique pour Teams utilisateurs

Pour Teams utilisateurs, Messagerie vocale infonuagique est automatiquement installé et mis en service. Notez qu’une licence Système téléphonique licence de licence n’est pas nécessaire pour Messagerie vocale infonuagique. 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurer des utilisateurs Messagerie vocale infonuagique boîtes aux Exchange Server

Les informations suivantes ont pour but de configurer des Messagerie vocale infonuagique de manière à ce qu’ils fonctionnent avec les utilisateurs qui utilisent une boîte aux lettres en ligne Système téléphonique dont la boîte aux lettres est Exchange Server. 
  
1. Les messages vocaux sont remis aux boîtes aux lettres des Exchange via SMTP acheminés via Exchange Online Protection. Pour permettre la remise de ces messages, assurez-vous que les connecteurs Exchange sont correctement configurés entre vos serveurs Exchange et vos Exchange Online Protection ; [Utiliser des connecteurs pour configurer l’Flow.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 

2. Pour activer les fonctionnalités de messagerie vocale, telles que la personnalisation des messages d’accueil et de la messagerie vocale visuelle dans les clients Skype Entreprise, une connectivité de Microsoft 365 ou Office 365 à la boîte aux lettres de serveur Exchange via les services web Exchange est requise. Pour activer cette connectivité, vous devez configurer le nouveau protocole d’authentification Oauth Exchange décrit dans configurer l’authentification [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)entre les organisations Exchange et Exchange Online, ou exécuter l’Assistant Exchange Hybride à partir d’Exchange 2013 CU5 ou version supérieure. De plus, vous devez configurer l’intégration et Oauth entre Skype Entreprise Online et le serveur Exchange décrits dans Configurer l’intégration et [oAuth](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)entre Skype Entreprise Online et Exchange Server. 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Configurer des Messagerie vocale infonuagique pour Skype Entreprise Server utilisateurs

Pour configurer les utilisateurs Skype Entreprise serveur pour Messagerie vocale infonuagique, consultez le service Messagerie vocale infonuagique de plan pour les [utilisateurs locaux.](/skypeforbusiness/hybrid/plan-cloud-voicemail)

## <a name="enabling-protected-voicemail-in-your-organization"></a>Activation de la messagerie vocale protégée dans votre organisation

Lorsqu’un utilisateur laisse un message vocal pour un utilisateur de votre organisation, ce dernier est remis dans sa boîte aux lettres sous la mesure où il est joint à un message électronique. En utilisant des règles de flux de courrier pour appliquer le chiffrement des messages, vous pouvez empêcher le courrier d’être transmis à d’autres destinataires. Lorsque vous activez des messages vocaux protégés, les utilisateurs peuvent écouter les messages vocaux protégés en appelant leur boîte aux lettres vocale ou en ouvrant le message dans Outlook, Outlook sur le web ou Outlook pour Android ou iOS. Les messages vocaux protégés ne peuvent pas être ouverts dans des Skype Entreprise ou Microsoft Teams.

Pour plus d’informations sur le chiffrement des messages, voir [Chiffrement des e-mails.](/microsoft-365/compliance/email-encryption?view=o365-worldwide)


Pour configurer une messagerie vocale protégée, vous pouvez :

1. Connectez-vous https://admin.microsoft.com à l’aide d’un compte avec des autorisations d’administrateur général.
2. Sélectionnez **Afficher tout,** puis allez dans centres **d’administration**  >  **Exchange.**
3. Dans le Centre Exchange d’administration, sélectionnez **Règles de flux de**  >  **courrier.**
4. Sélectionnez **+** **Ajouter,** puis sélectionnez Appliquer chiffrement de messages Office 365 protection des droits **et des droits aux messages.**
5. Donnent un nom à la nouvelle règle de flux de courrier, puis sous Appliquer cette règle si **,** sélectionnez les propriétés du **message** Inclure le type de  >  **message**  >  **Messagerie vocale.** Sélectionnez **OK.**
6. Sous **Faire ce qui suit,** sélectionnez Appliquer chiffrement de messages Office 365 protection des droits et droits au **message,** puis **sélectionnez-en un.** Sous **Modèle RMS,** sélectionnez **Ne pas avancer.** Sélectionnez **OK,** puis **Enregistrer.**
    > [!NOTE]
    > Si la **liste de modèles RMS** est vide, vous devez configurer le chiffrement des messages. Pour plus d’informations sur la configuration du chiffrement des messages, voir les articles suivants :
    > - [Configurer de nouvelles fonctionnalités de chiffrement de messages](/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [Configuration et gestion des modèles pour Azure Information Protection](/information-protection/deploy-use/configure-policy-templates)
    > - [Option Ne pas forwarder pour les e-mails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

    > [!NOTE]
    > Vous devez définir la clé de Registre suivante pour les utilisateurs, les entreprises et les organisations qui souhaitent que le formulaire de messagerie vocale apparaisse : [HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Outlook\Addins] « AllowVoicemailForm »=dword:00000001                           

## <a name="help-your-users-learn-teams-voicemail-features"></a>Aider vos utilisateurs à découvrir Teams fonctionnalités de messagerie vocale

Nous vous avons accès aux informations suivantes pour vos utilisateurs sur la gestion de leurs paramètres de messagerie vocale ainsi que sur les autres fonctionnalités d’appel Teams :

- [Gérez vos paramètres d’appel dans Teams.](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) Cet article explique comment gérer toutes les fonctionnalités d’appel Teams utilisateur final. 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Aider vos utilisateurs à découvrir les fonctionnalités de messagerie vocale de Skype Entreprise

Nous vous indions des informations de formation et des articles pour aider vos utilisateurs à se Skype Entreprise messagerie vocale. Orientez-les vers les articles suivants :

- Consultez Skype Entreprise messagerie vocale et vos [options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): cet article explique comment écouter vos messages vocaux dans Skype Entreprise, modifier votre message d’accueil vocal, modifier vos paramètres de messagerie vocale et écouter vos messages vocaux à des vitesses différentes.

- [Formation Skype Entreprise 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Voir aussi
[Configurer Skype entreprise Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Les avantages du système téléphonique](here-s-what-you-get-with-phone-system.md)

[Planifier la migration pour Skype Entreprise Server et Exchange Server](/SkypeForBusiness/hybrid/plan-um-migration)

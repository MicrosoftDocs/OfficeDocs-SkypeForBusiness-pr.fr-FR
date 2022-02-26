---
title: Configurer la Messagerie vocale cloud
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
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
ms.openlocfilehash: f1645ec9a14a5b201809cbe12219d7b1e437d355
ms.sourcegitcommit: edf68b7ac4f1861259a0990157ee6ae84f68ca42
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/26/2022
ms.locfileid: "62974471"
---
# <a name="set-up-cloud-voicemail"></a>Configurer la Messagerie vocale cloud

Cet article est Microsoft 365 administrateurs qui souhaitent configurer des Messagerie vocale infonuagique pour leurs utilisateurs. 

Messagerie vocale infonuagique dépose les messages vocaux dans la boîte aux lettres Exchange’un utilisateur. Messagerie vocale infonuagique ne prend pas en charge les systèmes de courrier tiers. Pour consulter Exchange Online de licences requises, voir [Exchange Online description du service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans). Pour plus d’informations sur les rôles d’administrateur, voir [À propos des rôles d’administrateur](/microsoft-365/admin/add-users/about-admin-roles).

## <a name="cloud-voicemail-provisioning"></a>Messagerie vocale infonuagique approvisionnement

Pour Teams utilisateurs, Messagerie vocale infonuagique est automatiquement installé et mis en service. *Une licence Microsoft Teams Téléphone licence de licence n’est pas nécessaire pour Messagerie vocale infonuagique.*

L’approvisionnement Teams utilisateurs est un service autre que pour Skype Entreprise Online. Pour Skype Entreprise Utilisateurs en ligne, Messagerie vocale infonuagique a été automatiquement installé et mis en service lorsque les utilisateurs ont été affectés à une licence Système téléphonique et Voix Entreprise activés par le système de mise en service.

Pour Skype Entreprise Server utilisateurs locaux, une Messagerie vocale infonuagique est automatiquement mise en service. Toutefois, vous devez configurer l’environnement Skype Entreprise Server pour router les appels vers Messagerie vocale infonuagique. Pour plus d’informations, [voir Planifier Messagerie vocale infonuagique service pour les utilisateurs locaux](/skypeforbusiness/hybrid/plan-cloud-voicemail.md). 

## <a name="cloud-voicemail-storage"></a>Messagerie vocale infonuagique stockage de données

Les messages vocaux générés par Messagerie vocale infonuagique sont remis et stockés dans la boîte aux lettres Exchange de l’utilisateur, soit dans Exchange Online, soit dans Exchange Server. Il n’existe pas de stockage spécifique ou supplémentaire pour la messagerie vocale. Les clients qui accèdent à la messagerie vocale (par exemple, Microsoft Outlook, Microsoft Teams ou Skype Entreprise) le font via la boîte aux lettres Exchange et les API fournies. 

Un message vocal contient un fichier audio joint avec les messages vocaux et la transcription des messages vocaux (si activé). 

La Exchange boîte aux lettres d’un utilisateur stocke les messages d’accueil enregistrés personnalisés. Ces messages d’accueil sont récupérés par les Messagerie vocale infonuagique besoin pendant un appel entrant. 

## <a name="cloud-voicemail-processing"></a>Messagerie vocale infonuagique traitement des données 

L’enregistrement et la transcription Messagerie vocale infonuagique débutent en Microsoft 365 à l’origine de l’appel acheminé vers Messagerie vocale infonuagique. Le message est ensuite remis dans la boîte aux lettres de l’Exchange’utilisateur. 

Par exemple, si un appel est reçu par un utilisateur de routage direct non disponible via un contrôleur de session border controller (SBC) en Europe, l’enregistrement et la transcription de la messagerie vocale sont effectués en Europe. Le message est ensuite remis dans la boîte aux lettres de l’Exchange’utilisateur. Par exemple, supposons qu’un Teams Amérique du Nord appelle un utilisateur non Teams en Europe. Dans ce cas, l’appel démarre en Amérique du Nord, le traitement se produit en Amérique du Nord, puis la messagerie vocale est remis dans la boîte aux lettres de l’Exchange en Europe. 

La remise d’un message vocal à une boîte aux lettres Exchange s’fait à l’aide du protocole SMTP (Simple Mail Transport Protocol) comme n’importe quel autre message électronique. 

## <a name="manage-cloud-voicemail-for-users"></a>Gérer les Messagerie vocale infonuagique utilisateurs 

Pour gérer les Messagerie vocale infonuagique de vos utilisateurs, utilisez le module PowerShell Teams la manière suivante. 

Pour gérer Messagerie vocale infonuagique fonctionnalités de messagerie pour des groupes d’utilisateurs, utilisez l’cmdlet [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy). Vous pouvez configurer et affecter des stratégies de messagerie vocale existantes ou nouvelles pour des fonctionnalités telles que les règles de répondeur automatique, la transcription de messages vocaux, le masquage de la transcription, la traduction et la langue d’invite système. Pour plus d’informations, [voir New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy).

Pour gérer les Messagerie vocale infonuagique utilisateurs individuels, utilisez l’cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings). Messagerie vocale infonuagique paramètres que vous pouvez appliquer aux utilisateurs individuels sont les règles de répondeurs, la langue d’invite, le texte par défaut de la parole et les vœux de vacances. Pour plus d’informations, [voir Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings).
(Notez que vos utilisateurs finaux peuvent également configurer ces paramètres dans le client  ->  Teams en vous Paramètres **CallsConfigure** ->  **Voicemail**.)

Vous pouvez également désactiver la Messagerie vocale infonuagique d’un utilisateur à l’aide de la cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) et en $false. Ce paramètre garantit que les Messagerie vocale infonuagique ne pourront plus enregistrer de message vocal pour l’utilisateur.



## <a name="control-routing-of-calls-to-cloud-voicemail"></a>Contrôler le routage des appels vers Messagerie vocale infonuagique 

Le paramètre par défaut pour tous les utilisateurs provisionés pour Messagerie vocale infonuagique est d’autoriser le routage des appels vers des Messagerie vocale infonuagique et de permettre aux utilisateurs de Messagerie vocale infonuagique. 

Vous pouvez contrôler si le routage des appels vers Messagerie vocale infonuagique est autorisé pour les utilisateurs de Teams à l’aide de l'Set-CsTeamsCallingPolicy de commande avec le paramètre AllowVoicemail. Pour plus d’informations,  [voirSet-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy.md). 

- Si vous définissez AllowVoicemail sur AlwaysDisabled, les appels ne seront jamais acheminés vers la messagerie vocale, quels que soient les paramètres de réponse ou de réponse d’un utilisateur. La messagerie vocale n’est pas disponible en tant que paramètre de forwardage d’appel ou sans réponse dans Teams.  

- Si vous définissez AllowVoicemail sur AlwaysEnabled, les appels sont toujours transmis à la messagerie vocale sans réponse après une sonnerie de 30 secondes, indépendamment du paramètre de forward d’appel sans réponse d’un utilisateur.  

- Si vous définissez AllowVoicemail sur UserOverride, les appels sont transmis à la messagerie vocale en fonction des paramètres de réponse et/ou de réponse d’un utilisateur. 



## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>Configurer des Messagerie vocale infonuagique pour travailler avec des utilisateurs locaux

Vous pouvez utiliser Messagerie vocale infonuagique pour fournir des fonctionnalités de messagerie vocale aux utilisateurs qui ont des boîtes aux lettres sur vos serveurs Exchange, ou aux utilisateurs qui utilisent Skype Entreprise Server. 

Cette section explique comment configurer des utilisateurs de boîtes Messagerie vocale infonuagique Exchange Server boîtes aux lettres. Pour plus d’informations sur la configuration de l Messagerie vocale infonuagique pour Skype Entreprise Server utilisateurs, consultez le [service Plan Messagerie vocale infonuagique pour les utilisateurs locaux](/skypeforbusiness/hybrid/plan-cloud-voicemail).

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurer des utilisateurs Messagerie vocale infonuagique boîte aux lettres Exchange Server’utilisateurs

Les informations suivantes ont pour sujet la configuration Messagerie vocale infonuagique à travailler avec les Teams qui ont leur boîte aux lettres sur Exchange Server.

1. Les messages vocaux sont remis à la boîte aux lettres d’un Exchange via SMTP acheminé via Exchange Online Protection. Pour permettre la remise de ces messages, assurez-vous que les connecteurs Exchange sont correctement configurés entre vos serveurs Exchange et vos Exchange Online Protection. Pour plus d’informations, [voir Utiliser des connecteurs pour configurer le courrier Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

2. Pour activer les fonctionnalités de messagerie vocale telles que la personnalisation des messages d’accueil et de la messagerie vocale visuelle dans les clients Teams, vous devez configurer la connectivité entre Microsoft 365 et la boîte Exchange Server messagerie. Pour activer cette connectivité, vous devez configurer le nouveau protocole d’authentification Oauth Exchange décrit dans Configurer l’authentification [OAuth entre les organisations Exchange et Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help) ou exécuter l’Assistant Exchange hybride à partir d’Exchange 2013 CU5 ou version supérieure. Vous devez également configurer l’intégration et Oauth entre les Teams et Exchange Server décrits dans Configurer l’intégration et [oAuth entre Teams et Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).


## <a name="enable-protected-voicemail-in-your-organization"></a>Activer la messagerie vocale protégée dans votre organisation

Lorsqu’un utilisateur laisse un message vocal pour un utilisateur de votre organisation, ce dernier est remis dans la boîte aux lettres de l’utilisateur sous la mesure d’une pièce jointe. En utilisant des règles de flux de courrier pour appliquer le chiffrement des messages, vous pouvez empêcher le courrier d’être transmis à d’autres destinataires. Lorsque vous activez des messages vocaux protégés, les utilisateurs peuvent écouter les messages vocaux protégés en appelant leur boîte aux lettres vocale ou en ouvrant le message dans Outlook, Outlook sur le web ou Outlook pour Android ou iOS. Les messages vocaux protégés ne peuvent pas être ouverts dans des Skype Entreprise ou Microsoft Teams.

Pour plus d’informations sur le chiffrement des messages, voir [Définir les règles de flux de courrier pour chiffrer les messages électroniques](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).



## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>Aider vos utilisateurs à en savoir plus sur Messagerie vocale infonuagique fonctionnalités

Pour aider vos utilisateurs à en savoir plus sur l’utilisation et la gestion Messagerie vocale infonuagique fonctionnalités de gestion des données, vous pouvez recommander les articles suivants : 

- [Consulter votre messagerie vocale dans Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [Gérer vos paramètres d’appel dans Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)

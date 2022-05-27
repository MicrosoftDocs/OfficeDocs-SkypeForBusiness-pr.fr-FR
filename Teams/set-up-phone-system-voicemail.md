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
description: Découvrez comment configurer Messagerie vocale infonuagique pour vos utilisateurs.
ms.openlocfilehash: 6a75856954da509677a1c9ccdb54e34055f171ed
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681405"
---
# <a name="set-up-cloud-voicemail"></a>Configurer la Messagerie vocale cloud

Cet article s’applique aux administrateurs Microsoft 365 qui souhaitent configurer Messagerie vocale infonuagique pour leurs utilisateurs.

Messagerie vocale infonuagique dépose des messages vocaux dans la boîte aux lettres Exchange d’un utilisateur. Messagerie vocale infonuagique ne prend pas en charge les systèmes de messagerie tiers. Pour Exchange Online exigences en matière de licences, consultez [Exchange Online description du service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans). Pour plus d’informations sur les rôles d’administrateur, consultez [À propos des rôles d’administrateur](/microsoft-365/admin/add-users/about-admin-roles).

## <a name="cloud-voicemail-provisioning"></a>approvisionnement Messagerie vocale infonuagique

Pour Teams utilisateurs, Messagerie vocale infonuagique est automatiquement configuré et configuré. *Une licence Téléphonie Microsoft Teams n’est pas requise pour Messagerie vocale infonuagique.*

L’approvisionnement pour Teams utilisateurs n’est pas le même que pour les utilisateurs Skype Entreprise Online. Pour les utilisateurs Skype Entreprise Online, Messagerie vocale infonuagique a été automatiquement configuré et configuré lorsque les utilisateurs ont reçu une licence Système téléphonique et ont été Voix Entreprise activés par le système d’approvisionnement.

Pour Skype Entreprise Server utilisateurs locaux, Messagerie vocale infonuagique est automatiquement configuré et configuré. Toutefois, vous devez configurer l’environnement Skype Entreprise Server pour router les appels vers Messagerie vocale infonuagique. Pour plus d’informations, consultez [Plan Messagerie vocale infonuagique service pour les utilisateurs locaux](/skypeforbusiness/hybrid/plan-cloud-voicemail).

## <a name="cloud-voicemail-storage"></a>stockage Messagerie vocale infonuagique

Les messages vocaux générés par Messagerie vocale infonuagique sont remis et stockés dans la boîte aux lettres Exchange de l’utilisateur, dans Exchange Online ou dans Exchange Server. Il n’existe aucun stockage spécifique ou supplémentaire pour la messagerie vocale. Les clients qui accèdent à la messagerie vocale (par exemple, Microsoft Outlook, Microsoft Teams ou Skype Entreprise) le font via la boîte aux lettres Exchange et les API fournies.

Un message vocal contient un fichier audio joint avec les messages vocaux et la transcription de la messagerie vocale (si activé).

La boîte aux lettres Exchange d’un utilisateur stocke les messages d’accueil enregistrés personnalisés. Ces salutations sont récupérées par Messagerie vocale infonuagique en fonction des besoins lors d’un appel entrant.

## <a name="cloud-voicemail-processing"></a>traitement Messagerie vocale infonuagique

L’enregistrement et la transcription de Messagerie vocale infonuagique commencent dans Microsoft 365 à l’origine de l’appel acheminé vers Messagerie vocale infonuagique. Le message est ensuite remis à la boîte aux lettres Exchange de l’utilisateur.

Par exemple, si un appel arrive à un utilisateur de routage direct indisponible via un contrôleur de frontière de session (SBC) en Europe, l’enregistrement et la transcription de la messagerie vocale sont effectués en Europe. Le message est ensuite remis à la boîte aux lettres Exchange de l’utilisateur. Par exemple, supposons qu’un utilisateur Teams dans Amérique du Nord appelle un utilisateur Teams non disponible en Europe. Dans ce cas, l’appel démarre dans Amérique du Nord, le traitement se produit dans Amérique du Nord, puis la messagerie vocale est remise à la boîte aux lettres Exchange de l’utilisateur en Europe.

La remise d’une messagerie vocale à une boîte aux lettres Exchange est effectuée à l’aide du protocole SMTP (Simple Mail Transport Protocol) comme n’importe quel autre e-mail.

## <a name="manage-cloud-voicemail-for-users"></a>Gérer Messagerie vocale infonuagique pour les utilisateurs

Pour gérer Messagerie vocale infonuagique fonctionnalités pour vos utilisateurs, utilisez le module PowerShell Teams comme suit.

Pour gérer Messagerie vocale infonuagique fonctionnalités pour les groupes d’utilisateurs, utilisez l’applet de commande [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy).
Vous pouvez configurer et affecter des stratégies de messagerie vocale existantes ou nouvelles pour des fonctionnalités telles que les règles de réponse aux appels, la transcription de la messagerie vocale, le masquage des vulgarités de transcription, la traduction de transcription et le langage d’invite système. Pour plus d’informations, consultez [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy).

Pour gérer Messagerie vocale infonuagique paramètres pour les utilisateurs individuels, utilisez l’applet de commande [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings). Messagerie vocale infonuagique paramètres que vous pouvez appliquer à des utilisateurs individuels incluent les règles de réponse aux appels, la langue d’invite, la reconnaissance vocale par défaut et les salutations de vacances. Pour plus d’informations, consultez [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings).
(Notez que vos utilisateurs finaux peuvent également configurer ces paramètres dans le client Teams en allant à **Paramètres** ->  **Calls** -> **Configure Voicemail**.)

Vous pouvez également désactiver Messagerie vocale infonuagique pour un utilisateur à l’aide de l’applet de commande [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) et en définissant le paramètre VoicemailEnabled sur $false. Ce paramètre garantit que Messagerie vocale infonuagique ne peut plus enregistrer de messagerie vocale pour l’utilisateur.

## <a name="control-routing-of-calls-to-cloud-voicemail"></a>Contrôler le routage des appels à Messagerie vocale infonuagique

Le paramètre par défaut pour tous les utilisateurs approvisionnés pour Messagerie vocale infonuagique est d’autoriser le routage des appels vers Messagerie vocale infonuagique et de permettre aux utilisateurs de transférer des appels à Messagerie vocale infonuagique.

Vous pouvez contrôler si le routage des appels à Messagerie vocale infonuagique est autorisé pour Teams utilisateurs à l’aide de l’applet de commande Set-CsTeamsCallingPolicy avec le paramètre AllowVoicemail. Pour plus d’informations, consultez [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

- Si vous définissez AllowVoicemail sur AlwaysDisabled, les appels ne sont jamais acheminés vers la messagerie vocale, quels que soient les paramètres de transfert d’appel ou sans réponse pour un utilisateur. La messagerie vocale n’est pas disponible en tant que transfert d’appel ou paramètre sans réponse dans Teams.

- Si vous définissez AllowVoicemail sur AlwaysEnabled, les appels sont toujours transférés vers la messagerie vocale sans réponse après avoir sonné pendant trente secondes, quel que soit le paramètre de transfert d’appel sans réponse pour un utilisateur.

- Si vous définissez AllowVoicemail sur UserOverride, les appels sont transférés vers la messagerie vocale en fonction du transfert d’appel et/ou des paramètres sans réponse d’un utilisateur.

## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>Configurer Messagerie vocale infonuagique pour travailler avec des utilisateurs locaux

Vous pouvez utiliser Messagerie vocale infonuagique pour fournir des fonctionnalités de messagerie vocale aux utilisateurs qui ont des boîtes aux lettres sur vos serveurs Exchange ou aux utilisateurs qui utilisent Skype Entreprise Server.

Cette section explique comment configurer Messagerie vocale infonuagique pour Exchange Server utilisateurs de boîte aux lettres. Pour plus d’informations sur la configuration de Messagerie vocale infonuagique pour les utilisateurs Skype Entreprise Server, consultez [Plan Messagerie vocale infonuagique service for on-premises users](/skypeforbusiness/hybrid/plan-cloud-voicemail).

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurer Messagerie vocale infonuagique pour les utilisateurs de boîte aux lettres Exchange Server

Les informations suivantes traitent de la configuration des Messagerie vocale infonuagique pour qu’ils fonctionnent avec Teams utilisateurs qui ont leur boîte aux lettres sur Exchange Server.

1. Les messages vocaux sont remis à la boîte aux lettres Exchange d’un utilisateur via SMTP routée via Exchange Online Protection. Pour permettre la remise de ces messages, assurez-vous que Exchange connecteurs sont correctement configurés entre vos serveurs Exchange et vos Exchange Online Protection. Pour plus d’informations, consultez [Utiliser des connecteurs pour configurer les Flow de messagerie](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

2. Pour activer les fonctionnalités de messagerie vocale, telles que la personnalisation des messages d’accueil et de la messagerie vocale visuelle dans Teams clients, vous devez configurer la connectivité entre Microsoft 365 et la boîte aux lettres Exchange Server. Pour activer cette connectivité, vous devez configurer le nouveau protocole d’authentification Oauth Exchange décrit dans [Configurer l’authentification OAuth entre les organisations Exchange et Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help), ou exécuter l’Assistant hybride Exchange à partir de Exchange 2013 CU5 ou version ultérieure. Vous devez également configurer l’intégration et Oauth entre Teams et Exchange Server décrits dans [Configurer l’intégration et OAuth entre Teams et Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).

## <a name="enable-protected-voicemail-in-your-organization"></a>Activer la messagerie vocale protégée dans votre organisation

Lorsqu’une personne laisse un message vocal pour un utilisateur de votre organisation, la messagerie vocale est remise à la boîte aux lettres de l’utilisateur sous forme de pièce jointe.

À l’aide de Protection des données Microsoft Purview, vous pouvez chiffrer les messages vocaux laissés par les appelants internes et externes. Vous pouvez également empêcher l’utilisateur de transférer ces messages. Cette fonctionnalité est prise en charge pour les utilisateurs disposant de boîtes aux lettres Exchange Online.

Pour chiffrer le message vocal, vous pouvez créer une étiquette de confidentialité. Avec la fonctionnalité d’étiquetage automatique, vous pouvez vous assurer que l’étiquette sera appliquée automatiquement aux messages vocaux entrants.

Lorsque vous activez la messagerie vocale protégée, les utilisateurs peuvent écouter les messages vocaux protégés en appelant dans leur boîte aux lettres de messagerie vocale ou en ouvrant le message dans Outlook, Outlook sur le web ou Outlook pour Android ou iOS. Les messages vocaux protégés ne peuvent pas être ouverts dans Microsoft Teams ou Skype Entreprise.

Pour créer une étiquette de confidentialité pour la messagerie vocale, consultez [Utiliser des étiquettes de confidentialité](/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions). Dans la section **Chiffrement** , choisissez **Autoriser les utilisateurs à attribuer des autorisations lorsqu’ils appliquent l’étiquette**. Sélectionnez **Dans Outlook, appliquez l’une des restrictions suivantes**, puis sélectionnez l’option **Ne pas transférer**.

Pour créer la stratégie d’étiquetage automatique afin d’appliquer une étiquette de confidentialité à la messagerie vocale, consultez [Comment configurer des stratégies d’étiquetage automatique](/microsoft-365/compliance/apply-sensitivity-label-automatically#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) et spécifiez les paramètres spécifiques suivants :

- Pour **choisir les informations auxquelles vous souhaitez appliquer cette étiquette**, sélectionnez **Stratégie personnalisée**.

- Pour **choisir les emplacements où vous souhaitez appliquer l’étiquette**, sélectionnez **Emplacements : Exchange pour tous les utilisateurs**.

- Pour  **configurer des règles courantes ou avancées**, sélectionnez **Règles avancées**.

- règles de Exchange :
  - Conditions:
    - **Modèle correspondant à l’en-tête** : Content-Class = Voice-CA
    - **L’adresse IP de l’expéditeur est** : 13.107.64.0/18, 52.112.0.0/14, 52.120.0.0/14, 52.238.119.141/32, 52.244.160.207/32

- Pour **choisir une étiquette à appliquer automatiquement**, sélectionnez l’étiquette de confidentialité que vous avez créée pour la messagerie vocale à l’étape ci-dessus.

- Pour **obtenir des paramètres supplémentaires pour l’e-mail**, **sélectionnez Appliquer le chiffrement aux e-mails reçus de l’extérieur de votre organisation**, puis spécifiez le propriétaire Rights Management.

Les plages IP V4 spécifiées dans l’adresse IP de l’expéditeur sont basées sur la liste de l’ID 12 dans [Office 365 URL et plages d’adresses IP](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

Pour plus d’informations sur le chiffrement des messages, consultez [Définir des règles de flux de courrier pour chiffrer les messages électroniques](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).

## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>Aider vos utilisateurs à découvrir Messagerie vocale infonuagique fonctionnalités

Pour aider vos utilisateurs à découvrir comment utiliser et gérer Messagerie vocale infonuagique fonctionnalités, vous pouvez recommander les articles suivants :

- [Vérifier votre messagerie vocale dans Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [Gérer vos paramètres d’appel dans Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)

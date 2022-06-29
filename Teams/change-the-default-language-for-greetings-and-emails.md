---
title: Modifier la langue par défaut des messages d'accueil et des courriers électroniques
author: crowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: Découvrez comment configurer Microsoft Teams et Skype Entreprise pour utiliser une autre langue pour le message d’accueil par défaut de votre organisation.
ms.openlocfilehash: 30e122c0d41c93326cdfa39de4c0ceb3a6d55cd2
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66241123"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a>Modifier la langue par défaut des messages d'accueil et des courriers électroniques

Messagerie vocale infonuagique utilise différents paramètres de langue pour lire des messages d’accueil, générer des traductions de transcription et générer des messages vocaux. Les paramètres de langue peuvent être spécifiés par défaut au niveau du locataire, par stratégie ou individuellement sur un utilisateur donné.

## <a name="greetings"></a>Salutations
Les salutations sont lues à l’appelant qui quitte la messagerie vocale et peuvent être les types suivants :

- Message d’accueil système
- Messages d’accueil personnalisés enregistrés par l’utilisateur appelé
- Message d’accueil de synthèse vocale personnalisé spécifié sur l’utilisateur appelé

La langue utilisée pour lire les messages d’accueil système est, dans l’ordre de priorité, la langue d’invite principale et secondaire spécifiée dans la stratégie de messagerie vocale en ligne affectée à l’utilisateur, la langue par défaut spécifiée pour l’utilisateur ou la langue de locataire par défaut.

Les messages d’accueil personnalisés et sortants du bureau sont enregistrés par l’utilisateur dans la langue choisie par l’utilisateur.

Si des messages d’accueil de synthèse vocale personnalisés sont spécifiés pour l’utilisateur par l’utilisateur ou l’administrateur du locataire, la langue utilisée pour générer la parole est l’InviteLanguage spécifié avec les messages d’accueil de synthèse vocale.

Les messages d’accueil de synthèse vocale personnalisés sont utilisés uniquement s’il n’existe aucun message d’accueil personnalisé enregistré pour l’utilisateur.

## <a name="transcription"></a>Transcription
Si elle est activée par la stratégie de messagerie vocale en ligne pour l’utilisateur appelé, Messagerie vocale infonuagique tente de transcrire la messagerie vocale laissée par l’appelant. Elle utilise la détection vocale pour comprendre la langue utilisée dans le contenu audio et, si possible, transcrire le contenu à l’aide de la langue détectée.

## <a name="transcription-translation"></a>Traduction de transcription
Si elle est activée par la stratégie de messagerie vocale en ligne pour l’utilisateur appelé, Messagerie vocale infonuagique traduit la messagerie vocale transcrite. Il se traduit de la langue détectée lors de la détection vocale en la langue par ordre de priorité spécifiée pour l’utilisateur ou la langue de locataire par défaut.

## <a name="voicemail-message-template"></a>Modèle de message vocal
Messagerie vocale infonuagique génère le message vocal à l’aide d’un modèle de langue basé sur, dans l’ordre de priorité, la langue par défaut spécifiée pour l’utilisateur ou la langue de locataire par défaut.

## <a name="setting-the-preferred-language-for-a-user"></a>Définition de la langue par défaut pour un utilisateur
Vous pouvez définir la langue par défaut d’un utilisateur à l’aide de PowerShell dans Azure Active Directory ou dans le Active Directory local. Pour plus d’informations, consultez [Comment définir les paramètres de langue et de région pour Microsoft 365 ou Office 365](/office365/troubleshoot/access-management/set-language-and-region).

Les utilisateurs peuvent modifier leur propre langue par le biais de leurs paramètres après s’être connectés. Pour plus d’informations, consultez [Modifier votre langue d’affichage et votre fuseau horaire dans Microsoft 365 Entreprise](https://support.office.com/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)

## <a name="change-the-system-language-for-everyone-in-your-organization"></a>Modifier la langue du système pour l'ensemble des utilisateurs de votre organisation

1. Connectez-vous avec votre compte [d’administrateur général](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) à l’adresse [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).

2. Dans le Centre d'administration Microsoft 365, choisissez Profil **d’organisation** **paramètres** > **de l’organisation des paramètres** >  de l’organisation.

3. Choisissez **les informations de l’organisation**.

4. Sélectionnez une langue dans la liste **Langue préférée** pour l'ensemble des utilisateurs de votre organisation.

5. Cliquez sur **Enregistrer**.

**Les langues disponibles sont déterminées par l'emplacement de votre organisation**. Par exemple, si votre organisation est située aux États-Unis, vous pouvez configurer la langue par défaut sur l'anglais ou l'espagnol. Si votre organisation est située au Canada, vous avez le choix entre l'anglais et le français.

## <a name="supported-languages-in-cloud-voicemail"></a>Langues prises en charge dans Messagerie vocale infonuagique
Pour obtenir la liste des langues prises en charge dans Messagerie vocale infonuagique pour Microsoft Teams et Skype Entreprise, consultez [Messagerie vocale infonuagique langues prises en charge](languages-for-voicemail-greetings-and-messages.md).
  

## <a name="custom-greeting-recorded-by-a-user"></a>Message d’accueil personnalisé enregistré par un utilisateur
Les utilisateurs peuvent enregistrer leur propre message d’accueil personnalisé et hors du bureau. Consultez [les paramètres du client de bureau Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) et [vérifiez Skype Entreprise la messagerie vocale et les options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).

## <a name="custom-text-to-speech-greeting-specified-for-a-user"></a>Message d’accueil de synthèse vocale personnalisé spécifié pour un utilisateur
L’administrateur client peut spécifier le message d’accueil de synthèse vocale personnalisé et la langue d’invite d’un utilisateur à l’aide de l’onglet Messagerie vocale de la page de détails de l’utilisateur dans le Centre d’administration Teams ou de l’applet de commande [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) .

## <a name="custom-text-to-speech-greeting-specified-by-a-user"></a>Message d’accueil de synthèse vocale personnalisé spécifié par un utilisateur
Les utilisateurs peuvent spécifier leurs propres messages d’accueil de synthèse vocale personnalisés et la langue utilisée pour les messages d’accueil. Pour Microsoft Teams - Les utilisateurs peuvent modifier leur message d’accueil de messagerie vocale à partir [des paramètres du client de bureau Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f). Pour Skype Entreprise, [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) choisissez une nouvelle langue sous **Langue d’invite**. 


## <a name="related-articles"></a>Articles connexes

[Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings)

[Get-CsOnlineVoicemailUserSettings](/powershell/module/skype/get-csonlinevoicemailusersettings)

[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

[Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)

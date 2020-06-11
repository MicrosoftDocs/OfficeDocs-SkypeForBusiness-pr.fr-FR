---
title: Activer les utilisateurs pour le routage direct
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Découvrez comment permettre aux utilisateurs du routage direct du système Microsoft Phone.
ms.openlocfilehash: 2ae485398cef1cef2444de07dcabc4bf3f949ad5
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691370"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>Permettre aux utilisateurs d’utiliser le routage direct, les appels vocaux et la messagerie vocale

Cet article explique comment permettre aux utilisateurs de routage direct du système téléphonique.  Vous trouverez ci-dessous l’étape 2 de la procédure de configuration du routage direct :

- Étape 1. [Connecter l’SBC avec un système Microsoft Phone et valider la connexion](direct-routing-connect-the-sbc.md) 
- **Étape 2. Permettre aux utilisateurs d’utiliser le routage direct, la voix et** la boîte vocale (cet article)
- Étape 3. [Configurer le routage de la voix](direct-routing-voice-routing.md)
- Étape 4. [Traduire des nombres dans un autre format](direct-routing-translate-numbers.md) 


Pour plus d’informations sur la procédure de configuration du routage direct, voir [configurer le routage direct](direct-routing-configure.md).

Lorsque vous êtes prêt à activer les utilisateurs pour le routage direct, procédez comme suit : 

1. Créez un utilisateur dans Microsoft 365 ou Office 365 et attribuez une licence de système téléphonique. 
2. Assurez-vous que l’utilisateur est bien immobilier dans Skype entreprise online. 
3. Configurez le numéro de téléphone et activez voix entreprise et boîte vocale. 
4. Affecter uniquement le mode équipe aux utilisateurs.

## <a name="create-a-user-and-assign-the-license"></a>Créer un utilisateur et lui attribuer une licence 

Deux options s’offrent à vous pour créer un utilisateur dans Microsoft 365 ou Office 365. Toutefois, Microsoft recommande à votre organisation de choisir une option pour éviter les problèmes de routage : 

- Créer l’utilisateur dans l’annuaire Active Directory local et synchroniser l’utilisateur avec le Cloud. Voir [intégrer vos annuaires locaux avec Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).
- Créez l’utilisateur directement dans le centre d’administration 365 Microsoft. Pour plus d' [informations, voir ajouter des utilisateurs individuellement ou en bloc à Microsoft 365 ou Office 365-aide de l’administrateur](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

Si votre déploiement de Skype entreprise Online existe avec Skype entreprise 2015 ou Lync 2010 ou 2013 sur site, la seule option prise en charge consiste à créer l’utilisateur dans l’annuaire Active Directory local et à synchroniser l’utilisateur dans le Cloud (option 1). 

Pour plus d’informations sur la gestion des licences, voir gestion des [licences et autres exigences](direct-routing-plan.md#licensing-and-other-requirements) dans [planifier le routage direct](direct-routing-plan.md).

## <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a>Vérifier que l’utilisateur est bien immobilier dans Skype entreprise Online 

Le routage direct nécessite que l’utilisateur soit hébergé dans Skype entreprise online. Vous pouvez vérifier en examinant le paramètre RegistrarPool, qui doit avoir une valeur dans le domaine infra.lync.com.

1. Connectez-vous à Remote PowerShell.
2. Émettez la commande suivante : 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
    ``` 

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Configuration du numéro de téléphone et activation de la voix et de la boîte vocale entreprise 

Une fois que vous avez créé l’utilisateur et attribué une licence, l’étape suivante consiste à configurer le numéro de téléphone de l’utilisateur et la boîte vocale. 

Pour ajouter le numéro de téléphone et l’activer pour la boîte vocale, procédez comme suit :
 
1. Se connecter à une session PowerShell distante. 
2. Entrez la commande suivante : 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```

    Par exemple, pour ajouter un numéro de téléphone pour l’utilisateur « Beaune Low », entrez ce qui suit : 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    Le numéro de téléphone utilisé doit être configuré en tant que numéro de téléphone avec l’indicatif du pays. 

      > [!NOTE]
      > Si le numéro de téléphone de l’utilisateur est géré en local, utilisez l’interpréteur de commandes ou le panneau de configuration Skype entreprise local pour configurer le numéro de téléphone de l’utilisateur. 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>Configurer l’envoi d’appels directement à la boîte vocale

Le routage direct vous permet de mettre fin à l’appel d’un utilisateur et de l’envoyer directement à la boîte vocale de l’utilisateur. Si vous voulez envoyer l’appel directement à la boîte vocale, attachez opaque = application : boîte vocale dans l’en-tête de la requête. Par exemple, « SIP : user@yourdomain. com ; opaque = application : boîte vocale ». Dans ce cas, l’utilisateur teams n’aura pas reçu la notification d’appel, l’appel sera connecté directement à la boîte vocale de l’utilisateur.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Attribuer le mode d’affectation uniquement aux utilisateurs pour s’assurer des appels terrestres dans Microsoft teams

Le routage direct exige que les utilisateurs soient en mode d’équipe uniquement pour s’assurer que les appels entrants sont présents dans le client Teams. Pour faire en sorte que les utilisateurs en mode équipes uniquement, attribuez-leur l’instance « UpgradeToTeams » de TeamsUpgradePolicy. Pour plus d’informations, consultez la rubrique [recommandations de mise à niveau pour les administrateurs informatiques](upgrade-to-teams-on-prem-overview.md). Si votre organisation utilise Skype entreprise Server ou Skype entreprise Online, reportez-vous à l’article suivant pour plus d’informations sur l’interopérabilité entre Skype et teams : [migration et interopérabilité avec Skype entreprise](migration-interop-guidance-for-teams-with-skype.md).

## <a name="see-also"></a>Voir aussi

[Planifier le routage direct](direct-routing-plan.md)

[Configurer le routage direct](direct-routing-configure.md)

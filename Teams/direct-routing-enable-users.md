---
title: Permettre aux utilisateurs d’obtenir un routage direct
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
description: Découvrez comment activer le routage direct de Microsoft Phone System.
ms.openlocfilehash: 972bd8d5e01a050a67978560b8de272439fda40d
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421309"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>Activer les utilisateurs pour le routage direct, la voix et la messagerie vocale

Cet article explique comment activer le routage direct du système téléphonique pour les utilisateurs.  Voici l’étape 2 de la procédure de configuration du routage direct :

- Étape 1. [Connecter le SBC à Microsoft Phone System et valider la connexion](direct-routing-connect-the-sbc.md) 
- **Étape 2. Activer les utilisateurs pour le routage direct, la voix et la messagerie vocale**   (cet article)
- Étape 3. [Configurer le routage vocal](direct-routing-voice-routing.md)
- Étape 4. [Traduire des nombres dans un autre format](direct-routing-translate-numbers.md) 


Pour plus d’informations sur les étapes requises pour configurer le routage direct, voir [Configurer le routage direct.](direct-routing-configure.md)

Lorsque vous êtes prêt à activer le routage direct pour les utilisateurs, suivez ces étapes : 

1. Créez un utilisateur dans Microsoft 365 ou Office 365 et attribuez une licence Phone System. 
2. Assurez-vous que l’utilisateur est bien domicile dans Skype Entreprise Online. 
3. Configurez le numéro de téléphone et activez la voix entreprise et la messagerie vocale. 
4. Attribuer le mode Teams uniquement aux utilisateurs.

## <a name="create-a-user-and-assign-the-license"></a>Créer un utilisateur et attribuer la licence 

Deux options s’offrent à vous pour créer un utilisateur dans Microsoft 365 ou Office 365. Toutefois, Microsoft recommande à votre organisation de choisir une option pour éviter les problèmes de routage : 

- Créez l’utilisateur dans Active Directory local et synchronisez l’utilisateur avec le cloud. Consultez [Intégrer vos annuaires locaux à Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)
- Créez l’utilisateur directement dans le Centre d’administration Microsoft 365. Voir [Ajouter des utilisateurs individuellement ou en bloc à Microsoft 365 ou Office 365 - Aide de l’administrateur.](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec) 

Si votre déploiement Skype Entreprise Online coexiste avec Skype Entreprise 2015 ou Lync 2010 ou 2013 en local, la seule option prise en charge consiste à créer l’utilisateur dans l’Active Directory local et à le synchroniser avec le cloud (option 1). 

Pour plus d’informations sur les conditions de licence, voir licences et [autres conditions requises](direct-routing-plan.md#licensing-and-other-requirements) dans [Planifier le routage direct.](direct-routing-plan.md)

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a>Assurez-vous que l’utilisateur est domicile en ligne et que le numéro de téléphone n’est pas synchronisé à partir de l’emplacement local (applicable à Skype Entreprise Server Voix Entreprise pour les utilisateurs activés pour la migration vers le routage direct de Teams)

Le routage direct nécessite que l’utilisateur soit domicile en ligne. Vous pouvez vérifier le paramètre RegistrarPool, qui doit avoir une valeur dans infra.lync.com domaine. Le paramètre OnPremLineUriManuallySet doit également être réglé sur True. Pour ce faire, configurez le numéro de téléphone et activez la voix entreprise et la messagerie vocale à l’aide de Skype Entreprise Online PowerShell.

1. Connectez une session PowerShell Skype Entreprise Online.

2. Émettre la commande : 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    Si OnPremLineUriManuallySet est configuré sur False et LineUri est rempli avec un> de numéro de téléphone <E.164, nettoyez les paramètres à l’aide de Skype Entreprise Management Shell sur site avant de configurer le numéro de téléphone à l’aide de Skype Entreprise Online PowerShell. 

1. Dans l’environnement de ligne de commande de Skype Entreprise Management Shell, vous pouvez émettre la commande : 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   Une fois les modifications synchronisées avec Office 365, la sortie attendue `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` de serait :

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Configurer le numéro de téléphone et activer la messagerie vocale et la messagerie vocale d’entreprise 

Après avoir créé l’utilisateur et attribué une licence, l’étape suivante consiste à configurer son numéro de téléphone et sa messagerie vocale. 

Pour ajouter le numéro de téléphone et activer la messagerie vocale :
 
1. Connectez une session PowerShell Skype Entreprise Online. 

2. Émettre la commande : 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    Par exemple, pour ajouter un numéro de téléphone pour l’utilisateur « Contrôle faible », entrez ce qui suit : 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    Si les utilisateurs « Sont petits » et « Qu’ils partagent le même numéro de base avec des extensions uniques », entrez les informations suivantes :
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    Il est recommandé, mais pas obligatoire, que le numéro de téléphone utilisé soit configuré comme numéro de téléphone E.164 complet avec l’code du pays. Il est pris en charge pour configurer des numéros de téléphone avec des extensions qui seront utilisés pour rechercher des utilisateurs lorsque la recherche par rapport au numéro de base renvoie plusieurs résultats. Cela permet aux entreprises de configurer des numéros de téléphone avec le même numéro de base et des extensions uniques. Pour que la recherche soit réussie, l’invitation doit inclure le numéro complet avec l’extension suivante :
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > Si le numéro de téléphone de l’utilisateur est géré en local, utilisez l’shell de gestion de Skype Entreprise local ou le Panneau de configuration pour configurer le numéro de téléphone de l’utilisateur. 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>Configuration de l’envoi d’appels directement sur la messagerie vocale

Le routage direct vous permet de mettre fin à l’appel à un utilisateur et de l’envoyer directement à la messagerie vocale de l’utilisateur. Si vous voulez envoyer l’appel directement sur la messagerie vocale, joignez opaque=application:voicemail à l’en-tête URI de demande. Par exemple, « sip:user@yourdomain.com;opaque=app:voicemail ». Dans ce cas, l’utilisateur de Teams ne recevra pas la notification d’appel, l’appel sera connecté à la messagerie vocale de l’utilisateur directement.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Attribuer le mode Teams uniquement aux utilisateurs pour garantir la qualité des appels dans Microsoft Teams

Le routage direct nécessite que les utilisateurs soient en mode Teams uniquement pour s’assurer que les appels entrants arrivent dans le client Teams. Pour placer les utilisateurs en mode Teams uniquement, affectez-leur l’instance « UpgradeToTeams » de TeamsUpgradePolicy. Pour plus d’informations, voir [Stratégies de mise à niveau pour les administrateurs informatiques.](upgrade-to-teams-on-prem-implement.md) Si votre organisation utilise Skype Entreprise Server ou Skype Entreprise Online, consultez l’article suivant pour plus d’informations sur l’interopérabilité entre Skype et Teams : migration et interopérabilité avec [Skype Entreprise.](migration-interop-guidance-for-teams-with-skype.md)

## <a name="see-also"></a>Voir aussi

[Planifier le routage direct](direct-routing-plan.md)

[Configurer le routage direct](direct-routing-configure.md)

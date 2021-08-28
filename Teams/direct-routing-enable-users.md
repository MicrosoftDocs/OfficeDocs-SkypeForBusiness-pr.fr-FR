---
title: Permettre aux utilisateurs d’obtenir un routage direct
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Découvrez comment permettre aux utilisateurs d Téléphone Microsoft routage direct du système.
ms.openlocfilehash: b6eb9bf0930b9b8f78d13deca95349afd78ec5af
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627586"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>Activer les utilisateurs pour le routage direct, la voix et la messagerie vocale

Cet article explique comment permettre aux utilisateurs d’obtenir Système téléphonique routage direct.  Voici l’étape 2 de la procédure de configuration du routage direct :

- Étape 1. [Connecter SBC avec votre système Téléphone Microsoft données et valider la connexion](direct-routing-connect-the-sbc.md) 
- **Étape 2. Activer les utilisateurs pour le routage direct, la voix et la messagerie vocale**   (cet article)
- Étape 3. [Configurer le routage vocal](direct-routing-voice-routing.md)
- Étape 4. [Traduire des nombres dans un autre format](direct-routing-translate-numbers.md) 


Pour plus d’informations sur les étapes requises pour configurer le routage direct, voir [Configurer le routage direct.](direct-routing-configure.md)

Lorsque vous êtes prêt à activer le routage direct pour les utilisateurs, suivez ces étapes : 

1. Créez un utilisateur dans Microsoft 365 ou Office 365 et attribuez une licence Système téléphonique utilisateur. 
2. Assurez-vous que l’utilisateur est bien familialement Skype Entreprise Online. 
3. Configurez le numéro de téléphone et activez la voix entreprise et la messagerie vocale. 
4. Affectez Teams mode uniquement aux utilisateurs.

## <a name="create-a-user-and-assign-the-license"></a>Créer un utilisateur et attribuer la licence

Deux options s’offrent à vous pour créer un utilisateur dans Microsoft 365 ou Office 365. Toutefois, Microsoft recommande à votre organisation de choisir une option pour éviter les problèmes de routage : 

- Créez l’utilisateur dans Active Directory local et synchronisez l’utilisateur avec le cloud. Consultez [Intégrer vos annuaires locaux à Azure Active Directory.](/azure/active-directory/connect/active-directory-aadconnect)
- Créez l’utilisateur directement dans le Centre d’administration Microsoft 365. Voir [Ajouter des utilisateurs individuellement ou en bloc Microsoft 365 ou Office 365 - Aide de l’administrateur.](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec) 

Si votre déploiement Skype Entreprise Online coexiste avec Skype Entreprise 2015 ou Lync 2010 ou 2013 en local, la seule option prise en charge consiste à créer l’utilisateur dans l’Active Directory local et à le synchroniser avec le cloud (option 1). 

Pour plus d’informations sur les conditions de licence, voir licences et [autres conditions requises](direct-routing-plan.md#licensing-and-other-requirements) dans [Planifier le routage direct.](direct-routing-plan.md)

## <a name="ensure-that-the-user-is-homed-online"></a>Vérifier que l’utilisateur est bien familialement en ligne 

Cette étape s’applique aux Skype Entreprise Server Voix Entreprise en cours de migration vers Teams routage direct.

Le routage direct nécessite que l’utilisateur soit domicile en ligne. Vous pouvez vérifier le paramètre RegistrarPool, qui doit avoir une valeur dans le domaine infra.lync.com bureau d’enregistrement. Il est également recommandé, mais pas obligatoire, de modifier la gestion de l’uri lineURI de l’offre en local vers le web lors de la migration des utilisateurs vers Teams routage direct. 

1. Connecter une session Skype Entreprise PowerShell online.

2. Émettre la commande : 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    Dans le cas où OnPremLineUriManuallySet est définie sur False et LineUri est remplie avec un> <numéro de téléphone E.164, le numéro de téléphone a été affecté sur site et synchronisé avec O365. Si vous voulez gérer le numéro de téléphone en ligne, nettoyez le paramètre à l’aide de Skype Entreprise Management Shell local et synchronisez-le avec O365, avant de configurer le numéro de téléphone à l’aide de Skype Entreprise Online PowerShell. 

1. À partir Skype Entreprise Management Shell, émettre la commande : 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null
    ``` 
 > [!NOTE]
 > Ne définissez pas EnterpriseVoiceEnabled sur False, car aucune obligation n’est requise et cela peut entraîner des problèmes de normalisation des plans de numérotation si des téléphones Skype Entreprise hérités sont utilisés et que la configuration hybride client est définie avec UseOnPremDialPlan $True. 
    
   Une fois les modifications synchronisées sur Office 365 la sortie `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` attendue serait :

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```
 > [!NOTE]
 > Tous les attributs de téléphone des utilisateurs doivent être gérés en ligne avant la mise hors service de votre environnement Skype Entreprise [local.](/skypeforbusiness/hybrid/decommission-on-prem-overview) 

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online"></a>Configurer le numéro de téléphone et activer la voix entreprise et la messagerie vocale en ligne 

Après avoir créé l’utilisateur et attribué une licence, l’étape suivante consiste à configurer ses paramètres de téléphone en ligne. 

 
1. Connecter une session Skype Entreprise PowerShell online. 

2. Si vous gérez le numéro de téléphone de l’utilisateur sur site, émettre la commande : 

    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
3. Si vous gérez le numéro de téléphone de l’utilisateur en ligne, émettre la commande : 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    Par exemple, pour ajouter un numéro de téléphone pour l’utilisateur « Contrôle faible », entrez ce qui suit : 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    Si les utilisateurs « Sont petits » et « Qu’ils partagent le même numéro de base avec des extensions uniques », entrez les informations suivantes :
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1001" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1002" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    Il est recommandé, mais pas obligatoire, que le numéro de téléphone utilisé soit configuré comme numéro de téléphone E.164 complet avec l’code du pays. Il est pris en charge pour configurer des numéros de téléphone avec des extensions qui seront utilisés pour rechercher des utilisateurs lorsque la recherche par rapport au numéro de base renvoie plusieurs résultats. Cela permet aux entreprises de configurer des numéros de téléphone avec le même numéro de base et des extensions uniques. Pour que la recherche soit réussie, l’invitation doit inclure le numéro complet avec l’extension suivante :
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > Si le numéro de téléphone de l’utilisateur est géré en local, utilisez l’shell de gestion Skype Entreprise local ou le Panneau de configuration pour configurer le numéro de téléphone de l’utilisateur. 


## <a name="configure-sending-calls-directly-to-voicemail"></a>Configurer l’envoi d’appels directement sur la messagerie vocale

Le routage direct vous permet de mettre fin à l’appel à un utilisateur et de l’envoyer directement à la messagerie vocale de l’utilisateur. Si vous voulez envoyer l’appel directement sur la messagerie vocale, joignez opaque=application:voicemail à l’en-tête URI de demande. Par exemple, « sip:user@yourdomain.com;opaque=app:voicemail ». Dans ce cas, l Teams de l’utilisateur ne reçoit pas la notification d’appel, l’appel est connecté directement à la messagerie vocale de l’utilisateur.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Affecter Teams mode uniquement aux utilisateurs pour s’assurer que les appels sont bien Microsoft Teams

Le routage direct nécessite que les utilisateurs soient en Teams uniquement pour s’assurer que les appels entrants arrivent dans Teams client. Pour mettre les utilisateurs en Teams mode Uniquement, affectez-leur l’instance « UpgradeToTeams » de TeamsUpgradePolicy. Pour plus d’informations, voir [Stratégies de mise à niveau pour les administrateurs informatiques.](upgrade-to-teams-on-prem-implement.md) Si votre organisation utilise Skype Entreprise Server ou Skype Entreprise Online, consultez l’article suivant pour plus d’informations sur l’interopérabilité entre Skype et Teams : [migration](migration-interop-guidance-for-teams-with-skype.md)et interopérabilité avec Skype Entreprise.

## <a name="see-also"></a>Voir aussi

[Planifier le routage direct](direct-routing-plan.md)

[Configurer le routage direct](direct-routing-configure.md)

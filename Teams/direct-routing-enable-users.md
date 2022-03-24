---
title: Permettre aux utilisateurs d’obtenir un routage direct
ms.reviewer: filippse
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
description: Découvrez comment activer l’accès des utilisateurs Microsoft Teams Téléphone routage direct.
ms.openlocfilehash: e82865abcc7bb37835009fb9ab7f93e11c423d66
ms.sourcegitcommit: b91d83739a078b175770c797c17d602eb5c83a4f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "63774093"
---
# <a name="enable-users-for-direct-routing"></a>Permettre aux utilisateurs d’obtenir un routage direct

Cet article explique comment permettre aux utilisateurs d’obtenir un routage direct. Voici l’étape 2 de la procédure de configuration du routage direct :

- Étape 1. [Connecter le SBC avec Système téléphonique et validez la connexion](direct-routing-connect-the-sbc.md) 
- **Étape 2. Activer le routage direct pour les utilisateurs**   (cet article)
- Étape 3. [Configurer le routage vocal](direct-routing-voice-routing.md)
- Étape 4. [Traduire des nombres dans un autre format](direct-routing-translate-numbers.md) 


Pour plus d’informations sur les étapes requises pour configurer le routage direct, voir [Configurer le routage direct](direct-routing-configure.md).

Lorsque vous êtes prêt à activer le routage direct pour les utilisateurs, suivez ces étapes : 

1. Créez un utilisateur dans Microsoft 365 et affectez une licence Système téléphonique utilisateur.  
2. Assurez-vous que l’utilisateur est bien homed online.
3. Configurez le numéro de téléphone et activez Voix Entreprise. 
4. Affectez Teams mode uniquement aux utilisateurs.

## <a name="create-a-user-and-assign-the-license"></a>Créer un utilisateur et attribuer la licence

Deux options s’offrent à vous pour créer un utilisateur dans Microsoft 365. Toutefois, Microsoft recommande à votre organisation de choisir une option pour éviter les problèmes de routage : 

- Créez l’utilisateur dans Active Directory local et synchronisez l’utilisateur avec le cloud. [Consultez Intégrer vos annuaires locaux à Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).
- Créez l’utilisateur directement dans le Centre d'administration Microsoft 365. Voir [Ajouter des utilisateurs individuellement ou en bloc Microsoft 365 ou Office 365 - Aide de l’administrateur](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

Si votre déploiement Skype Entreprise Online coexiste avec Skype Entreprise 2015 ou Lync 2010 ou 2013 en local, la seule option prise en charge consiste à créer l’utilisateur dans l’Active Directory local et à le synchroniser avec le cloud (option 1). 

Pour plus d’informations sur les conditions de licence, voir [licences et autres conditions requises](direct-routing-plan.md#licensing-and-other-requirements) dans [Planifier le routage direct](direct-routing-plan.md).

## <a name="ensure-that-the-user-is-homed-online"></a>Vérifier que l’utilisateur est bien homed online 

Cette étape s’applique Skype Entreprise Server Voix Entreprise utilisateurs en cours de migration vers Teams routage direct.

Le routage direct nécessite que l’utilisateur soit domicile en ligne. Vous pouvez vérifier le paramètre RegistrarPool, qui doit avoir une valeur dans le infra.lync.com domaine. Microsoft recommande, mais n’exige pas, de modifier l’uri lineURI de l’offre en local vers le web lors de la migration des utilisateurs vers Teams routage direct. 

1. Connecter une Microsoft Teams PowerShell.

2. Émettre la commande : 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUri,LineUri
    ``` 
    Si OnPremLineUri est rempli avec un> de numéro de téléphone <E.164, le numéro de téléphone a été affecté sur site et synchronisé avec Microsoft 365. Si vous voulez gérer le numéro de téléphone en ligne, nettoyez le paramètre à l’aide de Skype Entreprise Management Shell et synchronisez-le avec Microsoft 365 avant de configurer le numéro de téléphone à l’aide de Teams PowerShell. 

1. À partir Skype Entreprise Management Shell, émettre la commande : 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null
    ``` 
 > [!NOTE]
 > Ne définissez pas EnterpriseVoiceEnabled sur False, car aucune obligation n’est requise et cela peut entraîner des problèmes de normalisation des plans de numérotation si des téléphones Skype Entreprise hérités sont utilisés et que la configuration hybride client est définie avec UseOnPremDialPlan $True. 
    
   Une fois les modifications synchronisées sur Microsoft 365 la sortie attendue serait `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` :

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```
 > [!NOTE]
 > Tous les attributs de téléphone des utilisateurs doivent être gérés en ligne avant la mise hors service de votre environnement Skype Entreprise [local](/skypeforbusiness/hybrid/decommission-on-prem-overview). 

## <a name="configure-the-phone-number-and-enable-enterprise-voice"></a>Configurer le numéro de téléphone et activer Voix Entreprise 

Après avoir créé l’utilisateur et attribué une licence, vous devez configurer ses paramètres de téléphone en ligne. Notez que la configuration de Messagerie vocale infonuagique automatique pour l’utilisateur est automatique. Aucune configuration supplémentaire n’a besoin d’être effectuée.

Vous pouvez configurer le numéro de téléphone à l’aide du Centre Teams’administration ou de Teams PowerShell.

### <a name="use-teams-admin-center"></a>Utiliser le Teams d’administration de l’équipe

1. Allez à **UtilisateursManage** ->  **utilisateurs**.

2. Sélectionnez un utilisateur.

2. Sous **Informations générales** **sur le compte**, **sélectionnez Modifier**.

3. Sous **Affecter un numéro de téléphone**, dans **Téléphone menu déroulant Type** de numéro, sélectionnez **Routage direct**.

4. Entrez un numéro de téléphone affecté et une extension de numéro de téléphone si appicable.

5. **Sélectionnez Appliquer.**

Les informations générales du compte indiquent désormais le numéro de téléphone affecté et le routage direct comme type de numéro de téléphone.


### <a name="use-powershell"></a>Utiliser PowerShell

1. Connecter à une session Microsoft Teams PowerShell. 

2. Les étapes suivantes varient selon que vous gérez le numéro de téléphone de l’utilisateur sur site ou en ligne. Si vous gérez le numéro de téléphone en local, vous devez utiliser l’shell de gestion Skype Entreprise local, le Panneau de contrôle ou l’une des méthodes expliquées dans Décider comment gérer les [attributs après la désisionisation](/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes).

   - Si vous gérez le numéro de téléphone de l’utilisateur en local, vous devez vous assurer que l’utilisateur Voix Entreprise activé en ligne à l’aide de la commande suivante :

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -EnterpriseVoiceEnabled $true
       ```
       
   - Si vous gérez le numéro de téléphone de l’utilisateur en ligne, vous devez affecter ce numéro à l’utilisateur à l’aide de la commande suivante Teams PowerShell. L’utilisateur est automatiquement Voix Entreprise activé par la commande : 
 
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -PhoneNumber <phone number> -PhoneNumberType DirectRouting
       ```
    
       Par exemple, pour ajouter un numéro de téléphone pour l’utilisateur « Contrôle faible », entrez ce qui suit : 

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388797" -PhoneNumberType DirectRouting
       ```
       Si les utilisateurs « Sont petits » et «  Qu’ils partagent le même numéro de base avec des extensions uniques », entrez les informations suivantes :
    
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388701;ext=1001" -PhoneNumberType DirectRouting
       Set-CsPhoneNumberAssignment -Identity "stacy.quinn@contoso.com" -PhoneNumber "+14255388701;ext=1002" -PhoneNumberType DirectRouting
       ```

    Microsoft recommande, mais ne nécessite pas, que le numéro de téléphone soit configuré comme numéro de téléphone E.164 complet avec un code de pays. Vous pouvez configurer des numéros de téléphone avec des extensions. Ces extensions seront utilisées pour rechercher des utilisateurs lorsque la recherche par rapport au numéro de base renvoie plusieurs résultats. Cette fonctionnalité permet aux entreprises de configurer des numéros de téléphone avec le même numéro de base et des extensions uniques. Pour que la recherche soit réussie, l’invitation doit inclure le numéro complet avec l’extension suivante :
    
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```


## <a name="configure-sending-calls-directly-to-voicemail"></a>Configurer l’envoi d’appels directement sur la messagerie vocale

Le routage direct vous permet de mettre fin à l’appel à un utilisateur et de l’envoyer directement à sa messagerie vocale. Si vous voulez envoyer l’appel directement sur la messagerie vocale, joignez opaque=application:voicemail à l’en-tête URI de demande. Par exemple, « sip:user@yourdomain.com;opaque=app:voicemail ». Le Teams’utilisateur ne reçoit pas la notification d’appel, l’appel est connecté directement à la messagerie vocale de l’utilisateur.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Affecter Teams mode uniquement aux utilisateurs pour s’assurer que les appels sont bien Microsoft Teams

Le routage direct nécessite que les utilisateurs soient en Teams seul mode pour s’assurer que les appels entrants arrivent dans Teams client. Pour mettre les utilisateurs en Teams mode Uniquement, affectez-leur l’instance « UpgradeToTeams » de TeamsUpgradePolicy. Pour plus d’informations, voir [Stratégies de mise à niveau pour les administrateurs informatiques](upgrade-to-teams-on-prem-implement.md). Si votre organisation utilise Skype Entreprise Server, consultez l’article suivant pour plus d’informations sur l’interopérabilité entre les Skype et Teams : [Migration](migration-interop-guidance-for-teams-with-skype.md) et interopérabilité avec les Skype Entreprise.

## <a name="see-also"></a>Voir aussi

[Planifier le routage direct](direct-routing-plan.md)

[Configurer le routage direct](direct-routing-configure.md)

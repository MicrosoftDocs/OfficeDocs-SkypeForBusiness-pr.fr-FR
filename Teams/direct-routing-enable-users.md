---
title: Activer les utilisateurs pour le routage direct
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
description: Découvrez comment activer les utilisateurs pour Téléphonie Microsoft Teams le routage direct.
ms.openlocfilehash: edf02077bf5c15da56fe7894d1faec2a9b87b0d5
ms.sourcegitcommit: 9968ef7d58c526e35cb58174db3535fd6b2bd1db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/09/2022
ms.locfileid: "65284079"
---
# <a name="enable-users-for-direct-routing"></a>Activer les utilisateurs pour le routage direct

Cet article explique comment activer les utilisateurs pour le routage direct. Il s’agit de l’étape 2 des étapes suivantes pour configurer le routage direct :

- Étape 1. [Connecter le SBC avec Système téléphonique et valider la connexion](direct-routing-connect-the-sbc.md) 
- **Étape 2. Activer les utilisateurs pour le routage direct**   (cet article)
- Étape 3. [Configurer le routage vocal](direct-routing-voice-routing.md)
- Étape 4. [Traduire des nombres dans un autre format](direct-routing-translate-numbers.md) 


Pour plus d’informations sur toutes les étapes nécessaires à la configuration du routage direct, consultez [Configurer le routage direct](direct-routing-configure.md).

Lorsque vous êtes prêt à activer le routage direct des utilisateurs, procédez comme suit : 

1. Créez un utilisateur dans Microsoft 365 et attribuez une licence Système téléphonique.  
2. Assurez-vous que l’utilisateur est hébergé en ligne.
3. Configurez le numéro de téléphone et activez la voix d’entreprise. 
4. Attribuez Teams mode uniquement aux utilisateurs.

## <a name="create-a-user-and-assign-the-license"></a>Créer un utilisateur et attribuer la licence

Il existe deux options pour créer un utilisateur dans Microsoft 365. Toutefois, Microsoft recommande à votre organisation de choisir une option pour éviter les problèmes de routage : 

- Créez l’utilisateur dans Active Directory local et synchronisez-le avec le cloud. Consultez [Intégrer vos répertoires locaux à Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).
- Créez l’utilisateur directement dans le Centre d'administration Microsoft 365. Consultez [Ajouter des utilisateurs individuellement ou en bloc pour Microsoft 365 ou Office 365 - Aide de l’administrateur](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

Si votre déploiement Skype Entreprise Online coexiste avec Skype Entreprise 2015 ou Lync 2010 ou 2013 en local, la seule option prise en charge consiste à créer l’utilisateur dans le Active Directory local et à synchroniser l’utilisateur avec le cloud (option 1). 

Pour plus d’informations sur les exigences de licence, consultez [licences et autres exigences](direct-routing-plan.md#licensing-and-other-requirements) dans [Planifier le routage direct](direct-routing-plan.md).

## <a name="ensure-that-the-user-is-homed-online"></a>Vérifier que l’utilisateur est hébergé en ligne 

Cette étape s’applique à Skype Entreprise Server Voix Entreprise utilisateurs activés migrés vers Teams routage direct.

Le routage direct nécessite que l’utilisateur soit hébergé en ligne. Vous pouvez vérifier en examinant le paramètre RegistrarPool, qui doit avoir une valeur dans le domaine infra.lync.com. Microsoft recommande, mais n’exige pas, de remplacer lineURI local par en ligne lors de la migration d’utilisateurs vers Teams routage direct. 

1. Connecter une session PowerShell Microsoft Teams.

2. Émettez la commande : 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUri,LineUri
    ``` 
    Si OnPremLineUri est rempli avec un numéro de téléphone E.164 <>, le numéro de téléphone a été attribué localement et synchronisé avec Microsoft 365. Si vous souhaitez gérer le numéro de téléphone en ligne, désactivez le paramètre à l’aide de Skype Entreprise Management Shell local et synchronisez-le avec Microsoft 365 avant de configurer le numéro de téléphone à l’aide de Teams PowerShell. 

1. À partir de Skype Entreprise Management Shell, exécutez la commande : 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null
    ``` 
 > [!NOTE]
 > Ne définissez pas EnterpriseVoiceEnabled sur False, car il n’est pas nécessaire de le faire, ce qui peut entraîner des problèmes de normalisation du plan de numérotation si des téléphones Skype Entreprise hérités sont en service et que la configuration hybride du locataire est définie avec UseOnPremDialPlan $True. 
    
   Une fois les modifications synchronisées avec Microsoft 365, la sortie `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUri,LineUri` attendue est la suivante :

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURI                        : 
   LineURI                              : 
   ```
 > [!NOTE]
 > Tous les attributs de téléphone de l’utilisateur doivent être gérés en ligne avant [de décomissionr votre environnement Skype Entreprise local](/skypeforbusiness/hybrid/decommission-on-prem-overview). 

## <a name="configure-the-phone-number-and-enable-enterprise-voice"></a>Configurer le numéro de téléphone et activer la voix d’entreprise 

Une fois que vous avez créé l’utilisateur et attribué une licence, vous devez configurer les paramètres de téléphone en ligne de l’utilisateur. La configuration de Messagerie vocale infonuagique pour l’utilisateur est automatique ; aucune autre configuration n’a besoin d’être effectuée.

Vous pouvez configurer le numéro de téléphone à l’aide du centre d’administration Teams ou à l’aide de Teams PowerShell.

### <a name="use-teams-admin-center"></a>Utiliser Teams centre d’administration

1. Accédez aux **utilisateurs UsersManage** -> .

2. Sélectionnez un utilisateur.

2. Sous **Informations générales sur** le **compte**, **sélectionnez Modifier**.

3. Sous **Affecter un numéro de téléphone**, dans le menu déroulant **Téléphone type de numéro**, sélectionnez **Routage direct**.

4. Entrez un numéro de téléphone attribué et une extension de numéro de téléphone, le cas échéant.

5. Sélectionnez **Appliquer.**

Les informations générales du compte affichent désormais le numéro de téléphone affecté et le routage direct en tant que type de numéro de téléphone.


### <a name="use-powershell"></a>Utiliser PowerShell

1. Connecter à une session PowerShell Microsoft Teams. 

2. Les étapes suivantes varient selon que vous gérez le numéro de téléphone de l’utilisateur en local ou en ligne. Si vous gérez le numéro de téléphone en local, vous devez utiliser l’environnement local Skype Entreprise Management Shell, Panneau de configuration ou l’une des méthodes expliquées dans [Décider comment gérer les attributs après la désaffectation](/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes).

   - Si vous gérez le numéro de téléphone de l’utilisateur en local, vous devez vous assurer que l’utilisateur est Voix Entreprise activé en ligne à l’aide de la commande suivante :

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -EnterpriseVoiceEnabled $true
       ```
       
   - Si vous gérez le numéro de téléphone de l’utilisateur en ligne, vous devez attribuer le numéro de téléphone à l’utilisateur à l’aide de la commande suivante dans Teams PowerShell. L’utilisateur est automatiquement Voix Entreprise activé par la commande : 
 
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -PhoneNumber <phone number> -PhoneNumberType DirectRouting
       ```
    
       Par exemple, pour ajouter un numéro de téléphone pour l’utilisateur « Spencer Low », entrez ce qui suit : 

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388797" -PhoneNumberType DirectRouting
       ```
       Si les utilisateurs « Spencer Low » et « Ase Quinn » partagent le même numéro de base avec des extensions uniques, entrez les éléments suivants :
    
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388701;ext=1001" -PhoneNumberType DirectRouting
       Set-CsPhoneNumberAssignment -Identity "stacy.quinn@contoso.com" -PhoneNumber "+14255388701;ext=1002" -PhoneNumberType DirectRouting
       ```

    Microsoft recommande, mais ne nécessite pas, que le numéro de téléphone soit configuré en tant que numéro de téléphone E.164 complet avec le code du pays. Vous pouvez configurer des numéros de téléphone avec des extensions. Ces extensions seront utilisées pour rechercher des utilisateurs lorsque la recherche par rapport au numéro de base retourne plusieurs résultats. Cette fonctionnalité permet aux entreprises de configurer des numéros de téléphone avec le même numéro de base et les mêmes extensions uniques. Pour que la recherche réussisse, l’invitation doit inclure le numéro complet avec l’extension comme suit :
    
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```


## <a name="configure-sending-calls-directly-to-voicemail"></a>Configurer l’envoi d’appels directement à la messagerie vocale

Le routage direct vous permet de terminer l’appel à un utilisateur et de l’envoyer directement à la messagerie vocale de l’utilisateur. Si vous souhaitez envoyer l’appel directement à la messagerie vocale, attachez opaque=app:voicemail à l’en-tête Request URI. Par exemple, « sip:user@yourdomain.com;opaque=app:voicemail ». L’utilisateur Teams ne recevra pas la notification d’appel. Au lieu de cela, l’appel est connecté directement à la messagerie vocale de l’utilisateur.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Attribuer Teams mode uniquement aux utilisateurs pour s’assurer que les appels arrivent dans Microsoft Teams

Le routage direct nécessite que les utilisateurs soient en mode Teams uniquement pour s’assurer que les appels entrants arrivent dans le client Teams. Pour placer les utilisateurs en mode Teams uniquement, affectez-leur l’instance « UpgradeToTeams » de TeamsUpgradePolicy. Pour plus d’informations, consultez [Stratégies de mise à niveau pour les administrateurs informatiques](upgrade-to-teams-on-prem-implement.md). Si votre organisation utilise Skype Entreprise Server, consultez l’article suivant pour plus d’informations sur l’interopérabilité entre Skype et Teams : [Migration et interopérabilité avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md).

## <a name="see-also"></a>Voir aussi

[Planifier le routage direct](direct-routing-plan.md)

[Configurer le routage direct](direct-routing-configure.md)

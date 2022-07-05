---
title: Configurer un compte de ressource dans Skype Entreprise Server 2019
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection: ''
description: Configurez un compte de ressource pour Skype Entreprise Server 2019.
ms.openlocfilehash: ebaf79229097df8d3477b4d9b74504c278bfd59c
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615610"
---
# <a name="configure-resource-accounts"></a>Configurer des comptes de ressource

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype Entreprise Server 2019, les implémentations hybrides utilisent uniquement les services cloud fournis par le système téléphonique pour la messagerie unifiée et ne s’intègrent pas à Exchange Online. Dans Skype Entreprise Server 2019, vous pouvez désormais utiliser les files d’attente d’appels cloud et les standards automatiques décrits dans [Voici ce que vous obtenez avec le système téléphonique dans Microsoft 365 ou Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

Pour utiliser un standard automatique du système téléphonique ou une file d’attente d’appels avec Skype Entreprise Server 2019, vous devez créer des comptes de ressources qui agissent comme des points de terminaison d’application et qui peuvent être affectés à des numéros de téléphone, puis utiliser le centre d’administration Teams en ligne pour configurer la file d’attente des appels ou le standard automatique. Ce compte de ressource peut être hébergé en ligne (voir [Gérer les comptes de ressources dans Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) pour créer des comptes de ressources hébergés en ligne) ou localement, comme décrit dans cet article. En règle générale, vous disposez de plusieurs nœuds de file d’attente ou de standard automatique du système téléphonique, chacun étant mappé à un compte de ressources, qui peut être hébergé en ligne ou dans Skype Entreprise Server 2019.

Si vous disposez d’un standard automatique de messagerie unifiée Exchange et d’un système de file d’attente d’appels, avant de passer à Exchange Server 2019 ou Exchange Online, vous devez enregistrer manuellement les détails comme décrit ci-dessous, puis implémenter un système entièrement nouveau à l’aide du Centre d’administration Teams.

## <a name="overview"></a>Aperçu

Si votre standard automatique du système téléphonique ou votre file d’attente d’appels a besoin d’un numéro de service, les différentes dépendances peuvent être satisfaites dans la séquence suivante :

1. Obtenez un numéro de service.
2. Obtenez une [licence de compte de ressource Téléphonie Microsoft Teams](/MicrosoftTeams/teams-add-on-licensing/virtual-user) gratuite ou une licence système téléphonique payante à utiliser avec le compte de ressource.
3. Créez le compte de ressource. Un standard automatique ou une file d’attente d’appels est nécessaire pour avoir un compte de ressource associé.
4. Attendez une synchronisation Active Directory entre en ligne et localement.
5. Affectez la licence Système téléphonique au compte de ressource.
6. Attribuez un numéro de service au compte de ressource.
7. Créez une file d’attente d’appels du système téléphonique ou un standard automatique.
8. Associez le compte de ressource à un standard automatique ou à une file d’attente d’appels : (New-CsApplicationInstanceAssociation).

Si le standard automatique ou la file d’attente d’appels est imbriqué sous un standard automatique de niveau supérieur, le compte de ressource associé a uniquement besoin d’un numéro de téléphone si vous souhaitez que plusieurs points d’entrée dans la structure des standards automatiques et des files d’attente d’appels.

Pour rediriger les appels vers des personnes de votre organisation hébergées en ligne, elles doivent disposer d’une licence **système téléphonique** et être activées pour Voix Entreprise ou avoir des forfaits d’appels Microsoft 365 ou Office 365. Voir [Attribuer des licences Microsoft Teams](/MicrosoftTeams/assign-teams-licenses). Pour les activer pour Voix Entreprise, vous pouvez utiliser Windows PowerShell. Par exemple, exécutez :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Si le standard automatique du système téléphonique ou la file d’attente d’appels que vous créez est imbriqué et n’a pas besoin d’un numéro de téléphone, le processus est le suivante :

1. Créer le compte de ressource  
2. Attendre une synchronisation Active Directory entre en ligne et localement
3. Créer un standard automatique du système téléphonique ou une file d’attente d’appels
4. Associer le compte de ressource à un standard automatique du système téléphonique ou à une file d’attente d’appels

## <a name="create-a-resource-account-with-a-phone-number"></a>Créer un compte de ressource avec un numéro de téléphone

La création d’un compte de ressource qui utilise un numéro de téléphone nécessite d’effectuer les tâches suivantes dans l’ordre suivant :

1. Portez ou obtenez un numéro de service payant ou gratuit. Le numéro ne peut pas être affecté à d’autres services vocaux ou comptes de ressources.

   Avant d’affecter un numéro de téléphone à un compte de ressource, vous devez obtenir ou porter vos numéros de service payants ou gratuits existants. Une fois que vous avez obtenu les numéros de téléphone de service payants ou gratuits, ils s’affichent dans les **numéros de téléphone** **vocaux** >  du Centre  > **d’administration Microsoft Teams**, et le **type de numéro** répertorié est répertorié en tant que **service gratuit**. Pour obtenir vos numéros de service, consultez [Obtenir des numéros de téléphone de service](/MicrosoftTeams/getting-service-phone-numbers) ou si vous souhaitez transférer un numéro de service existant, consultez Transférer des [numéros de téléphone vers Teams](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams).

   Si vous êtes en dehors de la États-Unis, vous ne pouvez pas utiliser le Centre d’administration Microsoft Teams pour obtenir des numéros de service. Accédez plutôt à [Gérer les numéros de téléphone de votre organisation](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) pour voir comment procéder à partir de l’extérieur du États-Unis.

2. Acheter une licence système téléphonique. Voir :  
   - [licence de compte de ressource Téléphonie Microsoft Teams](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 Entreprise E1 et E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Entreprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 Entreprise E5 Business Software](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Créez un compte de ressource local en exécutant l’applet `New-CsHybridApplicationEndpoint` de commande pour chaque standard automatique ou file d’attente d’appels du système téléphonique, et donnez à chacun un nom, une adresse sip, et ainsi de suite.

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Pour plus d’informations sur cette commande, consultez [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .

4. (Facultatif) Une fois vos comptes de ressources créés, vous pouvez attendre qu’AD se synchronise entre en ligne et localement, ou forcer une synchronisation et passer à la configuration en ligne du standard automatique du système téléphonique ou des files d’attente d’appels. Pour forcer une synchronisation, exécutez la commande suivante sur l’ordinateur exécutant AAD Connect (si vous ne l’avez pas déjà fait, vous devez `import-module adsync` charger pour exécuter la commande) :

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Pour plus d’informations sur cette commande, consultez [Start-ADSyncSyncCycle](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) .

    À ce stade, le compte peut avoir été synchronisé, mais l’approvisionnement n’est peut-être pas terminé.  Vérifiez la sortie de [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint).  Si le point de terminaison synchronisé n’a pas encore terminé l’approvisionnement, il n’apparaît pas ici.  Vous pouvez vérifier l’état des demandes d’approvisionnement dans le portail M365 sous [État d’installation de Teams](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning).  Cette phase d’approvisionnement peut prendre jusqu’à 24 heures.

5. Attribuez la licence **Téléphonie Microsoft Teams compte de** ressource ou **la licence Téléphonie Teams standard** au compte de ressources. Voir [Attribuer des licences de module complémentaire Microsoft Teams](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) et [attribuer des licences aux utilisateurs](/microsoft-365/admin/manage/assign-licenses-to-users).

   Si vous attribuez un numéro de téléphone à un compte de ressource, vous pouvez désormais utiliser la licence **de compte de ressources Téléphonie Microsoft Teams** gratuite. Cela fournit des fonctionnalités de système téléphonique aux numéros de téléphone au niveau de l’organisation et vous permet de créer des fonctionnalités de standard automatique et de file d’attente d’appels.

6. Affectez le numéro de service au compte de ressource. Utilisez la `Set-CsHybridApplicationEndpoint` commande pour affecter un numéro de téléphone (avec l’option -LineURI) au compte de ressource.

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    Pour plus d’informations sur cette commande, consultez [Set-CsHybridApplicationEndpoint](/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) .

    Pour affecter un numéro de routage direct ou hybride à un compte de ressource, utilisez l’applet de commande suivante :

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   Le compte de ressource aura besoin d’un numéro de téléphone attribué s’il est affecté à un standard automatique de niveau supérieur ou à une file d’attente d’appels. Les numéros de téléphone de l’utilisateur (abonné) ne peuvent pas être affectés à un compte de ressource. Seuls les numéros de téléphone payants ou gratuits peuvent être utilisés.

     Vous pouvez affecter un routage direct ou un numéro hybride à votre compte de ressources. Pour plus d’informations, consultez [Plan Direct Routing](/MicrosoftTeams/direct-routing-plan) et [Plan Cloud Auto Attendants](plan-cloud-auto-attendant.md).

     > [!NOTE]
     > Les numéros de service de routage direct affectés aux comptes de ressources pour le standard automatique et les files d’attente d’appels sont pris en charge uniquement pour les utilisateurs et agents Microsoft Teams.

7. Créez le standard automatique du système téléphonique ou la file d’attente des appels. Consultez l’une des rubriques suivantes :

   - [Configurer un standard automatique dans le cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Créer une file d'attente pour les appels dans le Cloud](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. Associez le compte de ressource au standard automatique du système téléphonique ou à la file d’attente d’appels que vous avez choisie précédemment.

## <a name="create-a-resource-account-without-a-phone-number"></a>Créer un compte de ressource sans numéro de téléphone

Cette section décrit la création d’un compte de ressource hébergé localement. La création d’un compte de ressource hébergé en ligne est abordée [dans Gérer les comptes de ressources dans Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).

Ces étapes sont nécessaires, que vous créiez un standard automatique de système téléphonique ou une structure de file d’attente d’appels, ou que vous reconstruisiez la structure créée à l’origine dans la messagerie unifiée Exchange.

Connectez-vous au serveur frontal Skype Entreprise et exécutez les applets de commande PowerShell suivantes :

1. Créez un compte de ressource local en exécutant l’applet `New-CsHybridApplicationEndpoint` de commande pour chaque standard automatique ou file d’attente d’appels du système téléphonique, et donnez à chacun un nom, une adresse sip, et ainsi de suite.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Pour plus d’informations sur cette commande, consultez [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .

2. (Facultatif) Une fois vos comptes de ressources créés, vous pouvez attendre qu’AD se synchronise entre en ligne et localement, ou forcer une synchronisation et passer à la configuration en ligne du standard automatique du système téléphonique ou des files d’attente d’appels. Pour forcer une synchronisation, exécutez la commande suivante sur l’ordinateur exécutant AAD Connect (si vous ne l’avez pas déjà fait, vous devez `import-module adsync` charger pour exécuter la commande) :

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Pour plus d’informations sur cette commande, consultez [Start-ADSyncSyncCycle](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) .

3. Créez le standard automatique du système téléphonique ou la file d’attente des appels. Consultez l’une des rubriques suivantes :
   - [Configurer un standard automatique dans le cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Créer une file d'attente pour les appels dans le Cloud](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. Associez le compte de ressource et le standard automatique du système téléphonique ou la file d’attente d’appels que vous avez choisi précédemment.

## <a name="test-the-implementation"></a>Tester l’implémentation

La meilleure façon de tester l’implémentation consiste à appeler le numéro configuré pour un standard automatique du système téléphonique ou une file d’attente d’appels et à se connecter à l’un des agents ou menus. Vous pouvez également passer rapidement un appel de test à l’aide du **bouton Test** dans le volet Action du centre d’administration. Si vous souhaitez apporter des modifications à un standard automatique du système téléphonique ou à une file d’attente d’appels, sélectionnez-le, puis, dans le volet Action, cliquez sur **Modifier**. 

> [!TIP]
> Si votre compte de ressources a des difficultés à être affecté à une file d’attente d’appels ou à un standard automatique, consultez [les problèmes connus pour Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) et la section [Comment résoudre mes instances d’application hybride](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) dans le blog Microsoft Teams.

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Déplacement d’un standard automatique de messagerie unifiée Exchange ou d’une file d’attente d’appels vers le système téléphonique

La migration de la messagerie unifiée Exchange vers le système téléphonique nécessitera la recréation de la file d’attente des appels et de la structure du standard automatique. La migration directe de l’un vers l’autre n’est pas prise en charge. Pour ré implémenter un ensemble de files d’attente d’appels et de standards automatiques :

1. Obtenez la liste de tous les standards automatiques et files d’attente d’appels de messagerie unifiée Exchange en exécutant la commande suivante sur le système Exchange 2013 ou 2016 lors de la connexion en tant qu’administrateur :

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. Pour chaque file d’attente d’appels de messagerie unifiée Exchange répertoriée ou standard automatique, notez sa place dans la structure, les paramètres et obtenez des copies des fichiers audio ou de synthèse vocale associés (le guid dans la sortie sera le nom d’un dossier où les fichiers sont stockés). Vous pouvez obtenir ces détails en exécutant la commande :

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    Pour plus d’informations sur cette commande, consultez [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) . Une liste complète des options que vous devrez peut-être capturer se trouve dans les [membres UMAutoAttendant](/previous-versions/office/exchange-server-api/ff340649(v=exchg.150)) , mais les options les plus importantes à noter sont les suivantes :

    - Heures d'ouverture
    - Heures non ouvrées
    - Language
    - Planning des congés

3. Créez des points de terminaison locaux comme décrit précédemment.
   Affectez au standard automatique de niveau supérieur un numéro temporaire à des fins de test.

4. Configurez un standard automatique du système téléphonique ou une file d’attente d’appels qui utilise les points de terminaison comme décrit précédemment.

5. Testez le standard automatique du système téléphonique ou la file d’attente des appels.

6. Réattribuez le numéro de téléphone lié à la file d’attente d’appels de messagerie unifiée Exchange ou au standard automatique du système téléphonique correspondant ou à la file d’attente d’appels.  

   À ce stade, si vous avez déjà migré la messagerie vocale unifiée, vous devez être en mesure de migrer vers Exchange Server 2019.

## <a name="see-also"></a>Voir aussi

[Créer une file d'attente pour les appels dans le Cloud](/MicrosoftTeams/create-a-phone-system-call-queue)

[Un standard Cloud automatique, qu’est-ce que c’est ?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[Configurer un standard automatique dans le cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[Planifier les standards automatiques cloud](plan-cloud-auto-attendant.md)

[Planifier les files d’attente d’appels cloud](plan-call-queue.md)

[Planifier Messagerie vocale infonuagique service pour les utilisateurs locaux](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Gérer les comptes de ressources dans Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \( pour créer des comptes de ressources hébergés en ligne\)
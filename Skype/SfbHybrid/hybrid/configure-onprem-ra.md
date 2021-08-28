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
description: Configurer un compte de ressource pour Skype Entreprise Server 2019.
ms.openlocfilehash: 473a8cbcd77e3e0cb212481a4837f1c50801f20f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602029"
---
# <a name="configure-resource-accounts"></a>Configurer des comptes de ressource

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype Entreprise Server 2019 hybrides utilisent uniquement les services Cloud fournis par Système téléphonique pour la messagerie unifiée et ne s’intègrent pas à Exchange Online. Dans Skype Entreprise Server 2019, vous pouvez désormais utiliser les files [d’attente d’appels](/MicrosoftTeams/here-s-what-you-get-with-phone-system)cloud et les attendants automatiques décrits dans voici ce que vous obtenez avec Système téléphonique dans Microsoft 365 ou Office 365 .

Pour utiliser un attendant automatique Système téléphonique ou une file d’attente d’appels avec Skype Entreprise Server 2019, vous devez créer des comptes de ressources qui agissent comme des points de terminaison d’application et peuvent se voir attribuer des numéros de téléphone, puis utiliser le Centre d’administration Teams en ligne pour configurer la file d’attente d’appels ou le attendant automatique. Ce compte de ressource peut être en ligne (voir Gérer les comptes de ressources dans [Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) pour créer des comptes de ressources en ligne) ou en local, comme décrit dans cet article. En règle générale, vous avez plusieurs Système téléphonique de file d’attente d’appels ou de attendant automatiques, chacun d’eux est mappé à un compte de ressource, qui peut être homed online ou dans Skype Entreprise Server 2019.

Si vous avez un standard automatique de Exchange et un système de files d’attente d’appels de Exchange, avant de basculer vers Exchange Server 2019 ou Exchange online, vous devrez enregistrer manuellement les détails comme décrit ci-dessous, puis implémenter un système entièrement nouveau à l’aide du Centre d’administration Teams.

## <a name="overview"></a>Vue d’ensemble

Si votre Système téléphonique ou file d’attente d’appels aura besoin d’un numéro de service, les différentes dépendances peuvent être satisfaites dans l’ordre suivant :

1. Obtenez un numéro de service.
2. Obtenez une licence Système téléphonique gratuite - [Utilisateur](/MicrosoftTeams/teams-add-on-licensing/virtual-user) virtuel ou une licence Système téléphonique payante à utiliser avec le compte de ressource.
3. Créez le compte de ressource. Un service de gestion automatique ou une file d’attente d’appels doit être associé à un compte de ressource.
4. Attendez une synchronisation Active Directory en ligne et en local.
5. Attribuez la Système téléphonique licence au compte de ressource.
6. Affectez un numéro de service au compte de ressource.
7. Créez un Système téléphonique file d’attente d’appels ou un attendant automatique.
8. Associez le compte de ressource à un attendant automatique ou à une file d’attente d’appels : (New-CsApplicationInstanceAssociation).

Si le attendant automatique ou la file d’attente d’appels est imbrique sous un attendant automatique de niveau supérieur, le compte de ressource associé a uniquement besoin d’un numéro de téléphone si vous souhaitez plusieurs points d’entrée dans la structure des attendants automatiques et des files d’attente d’appels.

Pour rediriger les appels vers les personnes de votre organisation qui sont en ligne, elles doivent avoir une licence Système téléphonique et être activées pour **Voix Entreprise** ou avoir Microsoft 365 ou Office 365 forfaits d’appels. Voir [Attribuer Microsoft Teams licences.](/MicrosoftTeams/assign-teams-licenses) Pour les activer pour Voix Entreprise, vous pouvez utiliser Windows PowerShell. Par exemple, exécutez :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Si le Téléphone système automatique ou la file d’attente d’appels que vous créez est imbrmbré et n’a pas besoin d’un numéro de téléphone, le processus est :

1. Créer le compte de ressource  
2. Attendre une synchronisation Active Directory en ligne et en local
3. Créer un Système téléphonique automatique ou une file d’attente d’appels
4. Associer le compte de ressource à un Système téléphonique automatique ou une file d’attente d’appels

## <a name="create-a-resource-account-with-a-phone-number"></a>Créer un compte de ressource avec un numéro de téléphone

La création d’un compte de ressource qui utilise un numéro de téléphone nécessite d’effectuer les tâches suivantes dans l’ordre suivant :

1. Portez ou obtenez un numéro de service gratuit ou gratuit. Le numéro ne peut pas être affecté à d’autres services vocaux ou comptes de ressources.

   Avant d’affecter un numéro de téléphone à un compte de ressource, vous devez obtenir ou mettre en port vos numéros de service gratuits ou gratuits existants. Une fois que vous avez reçu les numéros de téléphone de service gratuits ou gratuits, ils s’afficheront dans les numéros Microsoft Teams du Centre d’administration  >  **Voice**  >  **Téléphone**  et le type de numéro répertorié sera répertorié en tant que **Service -** Gratuit . Pour obtenir vos numéros de service, consultez Obtenir des numéros de téléphone de [service](/MicrosoftTeams/getting-service-phone-numbers) ou si vous souhaitez transférer un numéro de service [existant,](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)consultez Transférer des numéros de téléphone vers Teams .

   Si vous êtes en dehors des États-Unis, vous ne pouvez pas utiliser le centre d’administration Microsoft Teams pour obtenir des numéros de service. Go to [Manage phone numbers for your organization](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.

2. Achetez une licence Système téléphonique licence. Voir :  
   - [Système téléphonique–Virtual User License](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 Entreprise E1 et E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Entreprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 Entreprise E5 Business Software](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Créez un compte de ressource local en exécutant la cmdlet pour chaque attendant automatique ou file d’attente d’appels Système téléphonique et donnez à chacun un nom, une `New-CsHybridApplicationEndpoint` adresse sip, etc.

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Pour plus d’informations sur cette commande, voir [New-CsHybridApplicationEndpoint.](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

4. (Facultatif) Une fois vos comptes de ressources créés, vous pouvez attendre qu’AD se synchronise en ligne et en local, ou forcer une synchronisation et passer à la configuration en ligne du attendant automatique ou des files d’attente d’appels Système téléphonique. Pour forcer une synchronisation, exécutez la commande suivante sur l’ordinateur exécutant AAD Connecter (si ce n’est pas déjà fait, vous devrez charger pour exécuter la `import-module adsync` commande) :

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Pour plus d’informations sur cette commande, [voir Start-ADSyncSyncCycle.](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler)
    
    Remarque : à ce stade, le compte a peut-être été synchronisé, mais la mise en service n’est peut-être pas terminée.  Vérifiez la sortie de [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint).  Si le point de terminaison synchronisé n’a pas encore terminé la mise en service, il n’apparaîtra pas ici.  Vous pouvez vérifier l’état des demandes d’approvisionnement dans le portail M365 sous [Teams statut du programme d’installation.](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning)  Cette phase d’approvisionnement peut prendre jusqu’à 24 heures.

5. Attribuez la Système téléphonique - Utilisateur virtuel ou Système téléphonique licence au compte de ressource. Voir [Attribuer Microsoft Teams licences de modules](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) et [attribuer des licences aux utilisateurs.](/microsoft-365/admin/manage/assign-licenses-to-users)

   Si vous affectez un numéro de téléphone à un compte de ressource, vous pouvez désormais utiliser la licence Système téléphonique - Virtual User. Cela offre Système téléphonique fonctionnalités de numéro de téléphone au niveau de l’organisation et vous permet de créer des fonctionnalités de service de téléphone et de numéro de file d’attente d’appels.


6. Affectez le numéro de service au compte de ressource. Utilisez la `Set-CsHybridApplicationEndpoint` commande pour affecter un numéro de téléphone (avec l’option -LineURI) au compte de ressource.

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    Pour plus d’informations sur cette commande, voir [Set-CsHybridApplicationEndpoint.](/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps)

    Pour affecter un numéro de routage direct ou hybride à un compte de ressource, utilisez l’cmdlet suivante :

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   Le compte de ressource a besoin d’un numéro de téléphone affecté s’il est affecté à un numéro de téléphone ou un numéro de téléphone de niveau supérieur. Les numéros de téléphone des utilisateurs (abonnés) ne peuvent pas être affectés à un compte de ressource, seuls les numéros de téléphone gratuits ou de service peuvent être utilisés.

     Vous pouvez affecter un numéro de routage direct ou hybride à votre compte de ressource. Pour plus d’informations, voir [Plan Direct Routing](/MicrosoftTeams/direct-routing-plan) and [Plan Cloud auto attendants](plan-cloud-auto-attendant.md).

     > [!NOTE]
     > Les numéros de service de routage direct affectés aux comptes de ressources pour le service de gestion automatique et les files d’attente d’appels sont pris en charge pour Microsoft Teams utilisateurs et agents uniquement.

7. Créez le Système téléphonique automatique ou la file d’attente d’appels. Consultez l’une des rubriques suivantes :

   - [Configurer un standard automatique dans le cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Créer une file d'attente pour les appels dans le Cloud](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. Associez le compte de ressource au Système téléphonique automatique ou à la file d’attente d’appels que vous avez choisi précédemment.

## <a name="create-a-resource-account-without-a-phone-number"></a>Créer un compte de ressource sans numéro de téléphone

Cette section traite de la création d’un compte de ressource qui est homed sur site. La création d’un compte de ressource qui est en ligne est abordée dans Gérer les comptes de ressources [dans Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).

Ces étapes sont nécessaires, que vous créiez un nouveau Système téléphonique automatique ou une structure de file d’attente d’appels, ou que vous restructuriez la structure créée à l’origine dans Exchange de la Exchange.

Connectez-vous au Skype Entreprise frontal et exécutez les cmdlets PowerShell suivantes :

1. Créez un compte de ressource local en exécutant la cmdlet pour chaque attendant automatique ou file d’attente d’appels Système téléphonique et donnez à chacun un nom, une `New-CsHybridApplicationEndpoint` adresse sip, etc.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Pour plus d’informations sur cette commande, voir [New-CsHybridApplicationEndpoint.](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

2. (Facultatif) Une fois vos comptes de ressources créés, vous pouvez attendre qu’AD se synchronise en ligne et en local, ou forcer une synchronisation et passer à la configuration en ligne du attendant automatique ou des files d’attente d’appels Système téléphonique. Pour forcer une synchronisation, exécutez la commande suivante sur l’ordinateur exécutant AAD Connecter (si ce n’est pas déjà fait, vous devrez charger pour exécuter la `import-module adsync` commande) :

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Pour plus d’informations sur cette commande, [voir Start-ADSyncSyncCycle.](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler)

3. Créez le Système téléphonique automatique ou la file d’attente d’appels. Consultez l’une des rubriques suivantes :
   - [Configurer un standard automatique dans le cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Créer une file d'attente pour les appels dans le Cloud](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. Associez le compte de ressource et le Système téléphonique ou file d’attente d’appels que vous avez choisi précédemment.

## <a name="test-the-implementation"></a>Tester l’implémentation

La meilleure façon de tester l’implémentation consiste à appeler le numéro configuré pour un attendant automatique ou une file d’attente d’appels Système téléphonique et à se connecter à l’un des agents ou menus. Vous pouvez également rapidement placer un appel de test à l’aide du bouton **Test** dans le volet Actions du Centre d’administration. Si vous souhaitez apporter des modifications à un Système téléphonique automatique ou à une file d’attente d’appels, sélectionnez-le, puis dans le volet Action, cliquez sur **Modifier.** 

> [!TIP]
> Si votre compte de ressource a des difficultés à être affecté à une file d’attente d’appels ou à un attendant automatique, consultez Problèmes connus pour [Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) et la section Comment résoudre mes [instances d’application](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) hybride dans le blog Microsoft Teams.

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Déplacement d’un Exchange ou d’une file d’attente d’appels de la Système téléphonique

La migration de la Exchange vers la Système téléphonique nécessite la recréation de la file d’attente d’appels et de la structure du attendant automatique, la migration directe de l’une vers l’autre n’est pas prise en charge. Pour ré-implémenter un ensemble de files d’attente d’appels et de attendants automatiques :

1. Obtenez la liste de tous les attendants automatiques et files d’attente d’appels de Exchange de la Exchange en exécutant la commande suivante sur le système Exchange 2013 ou 2016 lorsque vous êtes connecté en tant qu’administrateur :

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. Pour chaque file d’attente d’appels de messagerie unie ou un attendant automatique répertoriés, notez sa place dans la structure, les paramètres et obtenez des copies des fichiers audio ou de reconnaissance vocale associés (le guid dans la sortie sera le nom d’un dossier dans lequel les fichiers sont stockés). Exchange Vous pouvez obtenir ces détails en exécutant la commande :

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    Pour plus d’informations sur cette commande, [voir Get-UMAutoAttendant.](/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) La liste complète des options que vous devrez peut-être capturer se trouve dans les membres [UMAutoAttendant,](/previous-versions/office/exchange-server-api/ff340649(v=exchg.150)) mais les options les plus importantes à noter sont :

    - Heures d'ouverture
    - En de autres heures d’ouverture
    - Langue
    - Planning des congés

3. Créez des points de terminaison locaux comme décrit précédemment.
   Attribuez un numéro temporaire au attendant automatique de niveau supérieur à des fins de test.

4. Configurez un Système téléphonique automatique ou une file d’attente d’appels qui utilise les points de terminaison comme décrit précédemment.

5. Testez le Système téléphonique automatique ou la file d’attente d’appels.

6. Réaffectez le numéro de téléphone lié à la file d’attente d’appels de Exchange de la Exchange ou au attendant automatique au Système téléphonique ou à la file d’attente d’appels.  

   À ce stade, si vous avez déjà migré la messagerie vocale de messagerie unée, vous devez être en mesure de migrer vers Exchange Server 2019.

## <a name="see-also"></a>Voir aussi

[Créer une file d'attente pour les appels dans le Cloud](/MicrosoftTeams/create-a-phone-system-call-queue)

[Un standard Cloud automatique, qu’est-ce que c’est ?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[Configurer un standard automatique dans le cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[Planifier les standards automatiques cloud](plan-cloud-auto-attendant.md)

[Planifier les files d’attente d’appels cloud](plan-call-queue.md)

[Planifier Messagerie vocale infonuagique service pour les utilisateurs locaux](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Gérer les comptes de ressources dans Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)  -  \( pour créer des comptes de ressources en ligne\)
---
title: Configuration d’un compte de ressource dans Skype entreprise Server 2019
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Configurez un compte de ressource pour Skype entreprise Server 2019.
ms.openlocfilehash: 33211f7dcd56e402167a3c810343947d4dfe0954
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/03/2019
ms.locfileid: "36160534"
---
# <a name="configure-resource-accounts"></a>Configurer des comptes de ressources

Les implémentations hybrides de Skype entreprise Server 2019 utilisent uniquement les services Cloud fournis par le système téléphonique pour la messagerie unifiée et ne s’intègrent pas à Exchange Online. Dans Skype entreprise Server 2019, vous pouvez désormais utiliser les files d’attente d’appels Cloud et les standards automatiques décrits dans la section relative à la prise en charge du [système téléphonique dans Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

Pour utiliser ces services de système téléphonique avec Skype entreprise Server 2019, vous devrez créer des comptes de ressources qui agissent en tant que points de terminaison d’application et peuvent recevoir des numéros de téléphone, puis utiliser le centre d’administration teams Online pour configurer la file d’attente d’appels ou le standard automatique. Ce compte de ressource peut être hébergé en ligne (consultez la rubrique [Manage Resource Accounts in Microsoft teams](/MicrosoftTeams/manage-resource-accounts) pour créer des comptes de ressource hébergés en ligne) ou sur site comme décrit dans cet article. En règle générale, vous aurez plusieurs nœuds de service de système téléphonique, chacun d’entre eux étant mappé sur un compte de ressource qui peut être hébergé en ligne ou dans Skype entreprise Server 2019.

Si vous disposez d’un système de file d’attente automatique et d’appels de messagerie unifiée Exchange existant, avant de passer à Exchange Server 2019 ou Exchange Online, vous devez enregistrer manuellement les détails comme décrit ci-dessous, puis implémenter un système entièrement nouveau à l’aide du centre d’administration Teams. .

## <a name="overview"></a>Vue d’ensemble

Si votre service de système téléphonique nécessite un numéro de service, les diverses dépendances peuvent être satisfaites dans la séquence suivante:

1. Obtenir un numéro de service
2. Acheter une licence de système téléphonique
3. Créez le compte de ressource. Un standard automatique ou une file d’attente d’appels doit être associé à un compte de ressource.
4. Attendre une synchronisation Active Directory entre en ligne et sur site
5. Affectez la licence de système téléphonique au compte de ressource.
6. Affectez un numéro de service au compte de ressource.
7. Créer un service système téléphonique (une file d’attente d’appels ou un standard automatique)
8. Associer le compte de ressource à un service: (New-CsApplicationInstanceAssociation)

Si le standard automatique ou la file d’attente des appels est imbriqué sous un standard automatique de niveau supérieur, le compte de ressource associé n’a besoin que d’un numéro de téléphone si vous souhaitez utiliser plusieurs points d’entrée dans la structure des standards automatiques et des files d’attente d’appels.

Pour rediriger les appels vers des personnes de votre organisation qui sont hébergées en ligne, ils doivent disposer d’une licence de **système téléphonique** et être activés pour voix entreprise ou avoir des forfaits d’appels Office 365. Consultez la rubrique [attribuer des licences Microsoft teams](/MicrosoftTeams/assign-teams-licenses). Pour les activer pour voix entreprise, vous pouvez utiliser Windows PowerShell. Par exemple, exécutez:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Si le service système téléphonique que vous créez est imbriqué et n’a pas besoin de numéro de téléphone, le processus est le suivant:

1. Créer le compte de ressource  
2. Attendre une synchronisation Active Directory entre en ligne et sur site
3. Créer un service système téléphonique
4. Associer le compte de ressource à un service de système téléphonique

## <a name="create-a-resource-account-with-a-phone-number"></a>Créer un compte de ressource avec un numéro de téléphone

La création d’un compte de ressource qui utilise un numéro de téléphone nécessiterait d’effectuer les tâches suivantes dans l’ordre suivant:

1. Port ou obtenir un numéro de service payant ou gratuit. Le numéro ne peut être attribué à aucun autre service de téléphonie ou compte de ressource.

   Avant d’attribuer un numéro de téléphone à un compte de ressource, vous devrez obtenir ou transférer vos numéros de service payants ou gratuits. Une fois que vous avez obtenu les numéros de téléphone du service payant ou gratuit, ceux-ci s’afficheront dans les**numéros de téléphone****vocaux** > du centre > d' **administration Microsoft teams**, et le **type de numéro** affiché sera mentionné en tant que **service-** gratuit. Pour obtenir vos numéros de service, reportez-vous à la rubrique [obtention de numéros de téléphone de service](/MicrosoftTeams/getting-service-phone-numbers) ou pour transférer un numéro de service existant, consultez la rubrique transférer des [numéros de téléphone vers Office 365](/MicrosoftTeams/transfer-phone-numbers-to-office-365).

   Si vous n’êtes pas aux États-Unis, vous ne pouvez pas utiliser le centre d’administration Microsoft teams pour obtenir des numéros de service. Accédez à la rubrique [gérer les numéros de téléphone de votre organisation](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) à la place de l’extérieur des États-Unis.

2. Acheter une licence de système téléphonique. Voir :  
   - [Office 365 entreprise E1 et E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Entreprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 entreprise E5 Software](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Créez un compte de ressource local en exécutant l' `New-CsHybridApplicationEndpoint` applet de commande pour chaque service de système téléphonique et attribuez un nom, une adresse SIP et ainsi de suite à chacun d’eux.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Pour plus d’informations sur cette commande [, voir New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .

4. Module Une fois que vos comptes de ressource sont créés, vous pouvez soit attendre la synchronisation de l’annonce publicitaire en ligne et en local, soit forcer une synchronisation et passer à la configuration en ligne des services du système téléphonique. Pour forcer une synchronisation, vous devez exécuter la commande suivante sur l’ordinateur exécutant AAD Connect (si vous ne l’avez pas déjà fait, vous `import-module adsync` devez charger pour exécuter la commande):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Pour plus d’informations sur cette commande, voir [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) .

5. Affectez la licence de système téléphonique au compte de ressource. Consultez la rubrique [attribuer des licences Microsoft teams](/MicrosoftTeams/assign-teams-licenses) et [attribuer des licences à un utilisateur](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).

    Si vous affectez un numéro de téléphone à un compte de ressource, vous pouvez désormais utiliser la licence utilisateur virtuelle du système téléphonique économique. Cela fournit des fonctionnalités de système téléphonique aux numéros de téléphone au niveau de l’organisation et vous permet de créer des fonctionnalités de standard automatique et de file d’attente d’appel.


6. Affectez le numéro de service au compte de ressource. Utilisez la `Set-CsHybridApplicationEndpoint` commande pour affecter un numéro de téléphone (avec l’option-LineURI) au compte de ressource.

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    Pour plus d’informations sur cette commande, voir [Set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) .

    Pour affecter un routage direct ou un numéro hybride à un compte de ressource, utilisez l’applet de commande suivante:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

Le compte de ressource aura besoin d’un numéro de téléphone attribué s’il doit être affecté à un standard automatique de niveau supérieur ou une file d’attente d’appels. Les numéros de téléphone des utilisateurs (abonnés) ne peuvent pas être attribués à un compte de ressource, seuls les numéros payants ou gratuits du service peuvent être utilisés.

    You can assign a Direct Routing Hybrid number to your resource account.  See [Plan Direct Routing](direct-routing-plan) for details.

    > [!NOTE]
    > Direct Routing service numbers assigned to resource accounts for auto attendant and call queues are supported for Microsoft Teams users and agents only.

    > [!NOTE]
    > Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.

7. Créez le service système téléphonique. Consultez l’une des rubriques suivantes :

   - [Configurer un standard automatique Cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Créer une file d’attente d’appels sur le Cloud](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. Associez le compte de ressource au service système téléphonique que vous avez choisi précédemment.

Un exemple d’implémentation de petite entreprise est disponible dans l’exemple de la petite [entreprise: set up a auto](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) -exemple de standard automatique et de [petite entreprise-configurer une file d’attente d’appels](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).

## <a name="create-a-resource-account-without-a-phone-number"></a>Créer un compte de ressource sans numéro de téléphone

Cette section traite de la création d’un compte de ressource hébergé sur site. La création d’un compte de ressource hébergé en ligne est abordée dans [Manage Resource Accounts in Microsoft teams](/MicrosoftTeams/manage-resource-accounts).

Ces étapes sont nécessaires si vous créez un nouveau système de service de système téléphonique, ou si vous créez une structure créée dans la messagerie unifiée Exchange.

Connectez-vous au serveur frontal Skype entreprise et exécutez les applets de commande PowerShell suivantes:

1. Créez un compte de ressource local en exécutant l' `New-CsHybridApplicationEndpoint` applet de commande pour chaque service de système téléphonique et attribuez un nom, une adresse SIP et ainsi de suite à chacun d’eux.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Pour plus d’informations sur cette commande [, voir New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .

2. Module Une fois que vos comptes de ressource sont créés, vous pouvez soit attendre la synchronisation de l’annonce publicitaire en ligne et en local, soit forcer une synchronisation et passer à la configuration en ligne des services du système téléphonique. Pour forcer une synchronisation, vous devez exécuter la commande suivante sur l’ordinateur exécutant AAD Connect (si vous ne l’avez pas déjà fait, vous `import-module adsync` devez charger pour exécuter la commande):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Pour plus d’informations sur cette commande, voir [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) .

3. Créez le service système téléphonique. Consultez l’une des rubriques suivantes :
   - [Configurer un standard automatique Cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Créer une file d’attente d’appels sur le Cloud](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. Associez le compte de ressource et le service système téléphonique que vous avez choisi précédemment.

Un exemple d’implémentation de petite entreprise est disponible dans l’exemple de la petite [entreprise: set up a auto](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) -exemple de standard automatique et de [petite entreprise-configurer une file d’attente d’appels](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).

## <a name="test-the-implementation"></a>Tester l’implémentation

La meilleure façon de tester l’implémentation est d’appeler le numéro configuré pour un service de système téléphonique et de se connecter à l’un des agents ou des menus. Vous pouvez également passer rapidement un appel de test à l’aide du **bouton test** dans le volet d’action du centre d’administration. Si vous souhaitez apporter des modifications à un service de système téléphonique, sélectionnez-le, puis, dans le volet Actions, cliquez sur **modifier**.

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Transfert d’un standard automatique de messagerie unifiée Exchange ou d’une file d’attente d’appels vers le système téléphonique

La migration du service de messagerie unifiée Exchange vers le système téléphonique nécessite la recréation de la file d’attente et de la structure du standard automatique, la migration directe de l’une vers l’autre n’est pas prise en charge. Pour réimplémenter un ensemble de files d’attente d’appels et de standards automatiques:

1. Obtenez la liste de tous les standards automatiques de messagerie unifiée Exchange et des files d’attente d’appels en exécutant la commande suivante sur le système Exchange 2013 ou 2016 lorsque vous êtes connecté en tant qu’administrateur:

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. Pour chaque file d’attente d’appels de messagerie unifiée Exchange ou standard automatique, notez son emplacement dans la structure, les paramètres et les copies des fichiers audio ou de synthèse vocale associés (le GUID dans le résultat sera le nom d’un dossier dans lequel les fichiers sont stockés). Vous pouvez obtenir ces détails en exécutant la commande:

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    Pour plus d’informations sur cette commande, voir [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) . La liste complète des options que vous devrez peut-être capturer concerne les [membres UMAutoAttendant](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) , mais les options les plus importantes à noter sont les suivantes:

    - Heures d'ouverture
    - Heures d’ouverture
    - Langue
    - Planning des congés

3. Créez de nouveaux points de terminaison sur site, comme décrit précédemment.
   Affectez au standard automatique de niveau supérieur un numéro temporaire à des fins de test.

4. Configurez un service de système téléphonique qui utilise les points de terminaison comme décrit précédemment.

   Il peut s’avérer utile d’utiliser les exercices du didacticiel intitulé [petite entreprise-configurer un standard automatique](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) pour créer une carte logique des hiérarchies dans votre ancien système de messagerie unifiée Exchange.
5. Testez le service système téléphonique.
6. Réassignez le numéro de téléphone lié à la file d’attente d’appels de messagerie unifiée Exchange ou au standard automatique pour le service système téléphonique correspondant.  

   À ce stade, si vous avez déjà migré la messagerie vocale de messagerie unifiée, vous devez être en mesure de migrer vers Exchange Server 2019.

## <a name="see-also"></a>Voir aussi

[Créer une file d’attente d’appels sur le Cloud](/MicrosoftTeams/create-a-phone-system-call-queue)

[Qu’est-ce que les standards automatiques Cloud?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[Configurer un standard automatique Cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[Planifier les standards automatiques Cloud](plan-cloud-auto-attendant.md)

[Planifier les files d’attente des appels Cloud](plan-call-queue.md)

[Planifier le service de messagerie vocale sur le Cloud pour les utilisateurs locaux](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Gérer les comptes de ressources dans Microsoft teams](/MicrosoftTeams/manage-resource-accounts) - \(pour créer des comptes de ressource hébergés en ligne\)

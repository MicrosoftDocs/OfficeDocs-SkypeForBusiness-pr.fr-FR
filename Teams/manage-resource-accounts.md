---
title: Gérer les comptes de ressource dans Teams
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: En savoir plus sur la gestion des comptes de ressources dans Microsoft teams
ms.openlocfilehash: 4dcb9327efba7be70628ad71a90734940fc3317e
ms.sourcegitcommit: 016beacc8b64eaeeaefb641360dd9bb8d2191c4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394499"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Gérer les comptes de ressources dans Microsoft Teams

Un compte de ressource est également connu sous le nom d’objet utilisateur désactivé dans Azure Active Directory et peut être utilisé pour représenter des ressources en général. Dans Exchange, il peut être utilisé pour représenter des salles de conférence, par exemple, et leur permettre d’avoir un numéro de téléphone. Un compte de ressource peut être hébergé dans Microsoft 365 ou sur site à l’aide de Skype entreprise Server 2019.

Dans Microsoft teams ou Skype entreprise Online, chaque file d’attente d’appels ou standard automatique est requis pour disposer d’un compte de ressources associé. La nécessité d’utiliser un numéro de téléphone pour un compte de ressources dépend de la façon dont vous souhaitez utiliser la file d’attente d’appels ou le standard automatique associé. Pour attribuer un numéro de téléphone à un compte de ressources, voir les articles sur les files d’attente d’appels et les standards automatiques liés au bas de cet article.

> [!NOTE]
> Cet article s’applique à Microsoft teams et à Skype entreprise online. Pour les comptes de ressources hébergés sur Skype entreprise Server 2019, voir [configurer les comptes de ressources](/SkypeForBusiness/hybrid/configure-onprem-ra).

## <a name="overview"></a>Vue d’ensemble

Si le service de votre système téléphonique nécessite un numéro de service, les différentes dépendances peuvent être satisfaites dans l’ordre suivant:

1. Obtenez un numéro de service
2. Achat d’une licence de système téléphonique (Office 365 entreprise E1 ou E3 avec le système téléphonique ajouté ou Office 365 entreprise E5 qui inclut un système téléphonique)
3. Créez le compte de ressource. Un standard automatique ou une file d’attente d’appels doivent être associés à un compte de ressources associé.
4. Affectez la licence du système téléphonique au compte de ressource.
5. Attribuez un numéro de téléphone au compte de ressource.
6. Créer un service de système téléphonique (une file d’attente d’appels ou un standard automatique)
7. Associer le compte de ressource à un service: (New-CsApplicationInstanceAssociation)

Si le standard automatique ou la file d’attente d’appels est imbriquée sous un standard automatique de niveau supérieur, le compte de ressources associé a uniquement besoin d’un numéro de téléphone si vous voulez que plusieurs points d’entrée soient présents dans la structure des standards automatiques et des files d’attente d’appels.

Pour rediriger les appels vers des utilisateurs de votre organisation qui sont hébergés en ligne, ils doivent disposer d’une licence de **système téléphonique** et être activés pour Enterprise Voice ou disposer de plans d’appel Office 365. Voir [attribuer des licences Microsoft teams](assign-teams-licenses.md). Pour les activer pour Enterprise Voice, vous pouvez utiliser Windows PowerShell. Par exemple, exécutez :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Si le service de système téléphonique que vous créez est imbriqué et ne nécessite pas de numéro de téléphone, le processus est le suivant:

1. Créer le compte de ressources  
2. Créer un service de système téléphonique
3. Associer le compte de ressource à un service de système téléphonique

### <a name="create-a-resource-account-with-a-phone-number"></a>Créer un compte de ressources avec un numéro de téléphone

Pour créer un compte de ressource qui utilise un numéro de téléphone, vous devez effectuer les tâches suivantes dans l’ordre suivant:

1. Transférez ou obtenez un numéro de service gratuit ou payant. Le numéro ne peut pas être attribué à un autre service vocal ou à un autre compte de ressources.

   Avant d’affecter un numéro de téléphone à un compte de ressources, vous devez obtenir ou porter vos numéros de service gratuits ou payants existants. Une fois que vous avez obtenu les numéros de téléphone de service gratuits ou payants, ceux-ci apparaissent dans les**numéros de téléphone****vocaux** > du centre > d' **administration Microsoft teams**et le **type de numéro** mentionné est répertorié en tant que **service-** gratuit. Pour obtenir vos numéros de service, reportez-vous à la rubrique [obtention de numéros de service](getting-service-phone-numbers.md) ou, si vous souhaitez transférer un numéro de service existant, reportez-vous à la section transférer des [numéros de téléphone vers Office 365](transfer-phone-numbers-to-office-365.md).

2. Achetez une licence de système téléphonique. Savoir  
   - [Office 365 Entreprise E1 et E3](teams-add-on-licensing/office-365-enterprise-e1-e3.md)
   - [Office 365 Entreprise E5](teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing.md)
   - [Logiciel Office 365 entreprise E5 pour les entreprises](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Créer un compte de ressource. Voir [créer un compte de ressources dans le centre d’administration Microsoft teams](#create-a-resource-account-in-microsoft-teams-admin-center) ou [créer un compte de ressources dans PowerShell](#create-a-resource-account-in-powershell)
4. Affectez la licence du système téléphonique au compte de ressource. Voir [attribuer des licences Microsoft teams](assign-teams-licenses.md) et [affecter des licences à un utilisateur](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).
5. Attribuez le numéro de service au compte de ressource. Voir [affecter/retirer des numéros de téléphone et des services](#assignunassign-phone-numbers-and-services).
6. Configurez l’une des options suivantes:
   - [Standard automatique Cloud](create-a-phone-system-auto-attendant.md)
   - [File d’attente d’appels Cloud](create-a-phone-system-call-queue.md)
7. Affectez le compte de ressource au service. Voir [affectation/désaffectation de numéros de téléphone et services](#assignunassign-phone-numbers-and-services)

### <a name="create-a-resource-account-without-a-phone-number"></a>Créer un compte de ressources sans numéro de téléphone

Pour créer un compte de ressources sans numéro de téléphone, vous devez effectuer les tâches suivantes dans l’ordre suivant:

1. Créer un compte de ressource. Voir [créer un compte de ressources dans le centre d’administration Microsoft teams](#create-a-resource-account-in-microsoft-teams-admin-center) ou [créer un compte de ressources dans PowerShell](#create-a-resource-account-in-powershell)
2. Configurez l’une des options suivantes:
   - [Standard automatique Cloud](create-a-phone-system-auto-attendant.md)
   - [File d’attente d’appels Cloud](create-a-phone-system-call-queue.md)
3. Affectez le compte de ressource au service. Voir [affectation/désaffectation de numéros de téléphone et services](#assignunassign-phone-numbers-and-services)

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a>Créer un compte de ressources dans le centre d’administration Microsoft teams

Après avoir acheté une licence de système téléphonique et un plan d’appels à l’aide du centre d’administration de Microsoft Teams, accédez à**comptes de ressources**de **paramètres** > à l’échelle de l’organisation.

![Capture d’écran de la page comptes de ressources](media/r-a-master.png)

![Icône du numéro 1 qui référence une légende dans la capture d’écran précédente](media/sfbcallout1.png)

Pour créer un compte de ressource, cliquez sur **+ nouveau compte**. Dans la fenêtre qui s’affiche, indiquez le nom d’affichage et le nom d’utilisateur du compte de ressource (le nom de domaine doit remplir automatiquement), puis cliquez sur **Enregistrer**.

![Capture d’écran des options de nouveau compte de ressources](media/res-acct.png)

Ensuite, appliquez une licence au compte de ressources dans le centre d’administration O365, comme décrit dans la section [attribuer des licences aux utilisateurs dans Office 365 pour les entreprises](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) .

### <a name="edit-resource-account-name"></a>Modifier le nom du compte de la ressource

![Icône du numéro 2, qui référence une légende dans la capture d'](media/sfbcallout2.png) écran précédente, vous pouvez modifier le nom d’affichage du compte de la ressource à l’aide de l’option **modifier** .  Lorsque vous avez fin, cliquez sur **Enregistrer** .
![Capture d’écran de l’option modifier le compte de ressources](media/r-a-edit.png)

### <a name="assignunassign-phone-numbers-and-services"></a>Attribution/désaffectation des numéros de téléphone et services

![Icône du numéro 3, qui référence une légende dans la capture d'](media/sfbcallout3.png) écran précédente une fois que vous avez créé le compte de ressources et attribué la licence, vous pouvez cliquer sur **affecter/annuler** pour affecter un numéro de service au compte de ressource ou affecter la ressource compte vers une file d’attente d’appels ou un standard automatique qui existe déjà. L’attribution d’un numéro d’acheminement direct peut être réalisé à l’aide d’une cmdlet uniquement. Si la file d’attente d’appels ou le standard automatique doit toujours être créé, vous pouvez lier le compte de ressources lors de sa création. Lorsque vous avez fin, cliquez sur **Enregistrer** .

Pour affecter un routage direct ou un numéro hybride à un compte de ressource, vous devez utiliser PowerShell, reportez-vous à la section suivante.

> [!IMPORTANT]
> Si votre client ne dispose pas d’une licence de système téléphonique, un échec de vérification interne entraîne un échec lorsque vous tentez d’affecter le numéro de téléphone au compte de ressource. Vous ne pourrez pas affecter le numéro ou associer le compte de ressources à un service.

![Capture d’écran des options d’attribution/de désaffectation](media/r-a-assign.png)

## <a name="create-a-resource-account-in-powershell"></a>Créer un compte de ressources dans PowerShell

Selon que votre compte de ressources se trouve en ligne ou en local, vous devez vous connecter à l’invite PowerShell appropriée avec les privilèges d’administrateur.

- Les exemples de cmdlet PowerShell suivants présupposent que le compte de ressource est hébergé en ligne à l’aide [de New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) pour créer un compte de ressources hébergé en ligne.

- Pour les comptes de ressources hébergés en local dans Skype entreprise Server 2019 qui peuvent être utilisés avec les files d’attente d’appels Cloud et les standards automatiques Cloud, voir [configurer des files d’attente d’appels](/skypeforbusiness/hybrid/configure-call-queue.md) Cloud ou [configurer des standards automatiques de Cloud](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md). Les implémentations hybrides (numéros hébergés sur le routage direct) utilisent [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).

L’ID d’application que vous devez utiliser lors de la création des instances d’application est le suivant:

- **Standard automatique:** ce933385-9390-45D1-9512-c8d228074e07
- **File d’attente des appels:** 11cd3e2e-FCCB-42AD-AD00-878b93575e07

> [!NOTE]
> Si vous souhaitez que la file d’attente d’appels ou le standard automatique puissent être recherchés par des utilisateurs locaux, vous devez créer vos comptes de ressources en local, car les comptes de ressources en ligne ne sont pas synchronisés avec Active Directory.

1. Pour créer un compte de ressources en ligne à utiliser avec un standard automatique, utilisez la commande suivante.  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. Vous ne serez pas en mesure d’utiliser le compte de ressource tant que vous n’avez pas appliqué de licence. Pour plus d’informations sur la façon d’appliquer une licence à un compte dans le centre d’administration O365, voir [attribuer des licences aux utilisateurs dans Office 365 pour les entreprises](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) , ainsi qu' [affecter des licences Skype entreprise](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).

3. Facultatif Une fois la licence correcte appliquée au compte de ressources, vous pouvez définir un numéro de téléphone sur le compte de ressource, comme illustré ci-dessous. Tous les comptes de ressources ne nécessitent pas de numéro de téléphone. Si vous n’avez pas appliqué de licence au compte de ressource, l’affectation de numéro de téléphone échoue.

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

Pour plus d’informations sur cette commande [, voir Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .

> [!NOTE]
> Il est plus facile de définir le numéro de téléphone en ligne à l’aide du centre d’administration de Microsoft Teams, comme décrit précédemment.

Pour attribuer un routage direct ou un numéro hybride à un compte de ressources, utilisez l’applet de commande suivante:

``` Powershell
Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a>Gérer les paramètres de compte de ressources dans le centre d’administration Microsoft teams

Pour gérer les paramètres de compte de ressources dans le centre d’administration de Microsoft Teams, accédez à**comptes de ressources**de **paramètres**  > à l’échelle de l’organisation, sélectionnez le compte de ressources dont vous avez besoin pour modifier les paramètres, puis cliquez sur le bouton **modifier** . dans l’écran **modifier le compte de ressources** , vous pouvez modifier les paramètres suivants:

- **Nom d’affichage** du compte
- File d’attente d’appels ou standard automatique qui utilise le compte
- Numéro de téléphone attribué au compte

Lorsque vous avez terminé, cliquez sur **Enregistrer**.

## <a name="delete-a-resource-account"></a>Supprimer un compte de ressource

Vérifiez que vous avez dissocié le numéro de téléphone du compte de ressources avant de le supprimer, afin d’éviter de rester bloqué dans le mode en attente. Pour ce faire, vous pouvez utiliser l’applet de commande suivante:

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

Lorsque vous procédez ainsi, vous pouvez supprimer le compte de ressources du portail d’administration Office 365, sous l’onglet utilisateurs.

## <a name="troubleshooting"></a>Résolution des problèmes

Si vous ne voyez pas le numéro de téléphone attribué au compte de ressources dans le centre d’administration teams et que vous ne pouvez pas attribuer le numéro à partir de cet emplacement, vérifiez les points suivants:

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

Si l’attribut Service affiche le point de terminaison d’une application Skype entreprise, exécutez l’applet de demande ci-dessous:

``` Powershell
Set-MsolUser -ObjectId  -Department "Microsoft Communication Application Instance"
```
> [!NOTE]
> Actualisez la page Web du centre d’administration teams après avoir exécuté le cmldet et vous devriez pouvoir affecter le numéro correctement.

## <a name="related-information"></a>Informations connexes

Pour les implémentations hybrides avec Skype entreprise Server, procédez comme suit:

[Planifier les standards automatiques cloud](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[Configurer des standards automatiques cloud](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

Pour les implémentations dans teams ou Skype entreprise Online:

[Un standard Cloud automatique, qu’est-ce que c’est ?](what-are-phone-system-auto-attendants.md)

[Configurer un standard automatique dans le cloud](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[Exemple de petite entreprise : configurer un standard automatique](/microsoftteams/tutorial-org-aa)

[Créer une file d’attente d’appels cloud](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[Nouveau-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[Nouveau-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

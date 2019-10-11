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
ms.openlocfilehash: 998436e48acec3552bc88f960d12771d9f1e941b
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435157"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Gérer les comptes de ressources dans Microsoft Teams

Un compte de ressource est également connu sous le nom d' *objet utilisateur désactivé* dans Azure ad et peut être utilisé pour représenter des ressources en général. Dans Exchange, il peut être utilisé pour représenter des salles de conférence, par exemple, et leur permettre d’avoir un numéro de téléphone. Un compte de ressource peut être hébergé dans Microsoft 365 ou sur site à l’aide de Skype entreprise Server 2019.

Dans Microsoft teams ou Skype entreprise Online, chaque file d’attente d’appels du système téléphonique ou le standard automatique est requis pour disposer d’au moins un compte de ressources associé. La nécessité pour un compte de ressources d’avoir besoin d’un numéro de téléphone dépend de la manière dont vous souhaitez utiliser la file d’attente d’appels ou le standard automatique associé, comme illustré dans le schéma suivant. Vous pouvez également vous référer aux articles sur les files d’attente d’appels et aux standards automatiques liés au bas de cet article avant d’affecter un numéro de téléphone à un compte de ressources.

![exemple de comptes de ressources et de licences utilisateur](media/resource-account.png)

> [!NOTE]
> Cet article s’applique à Microsoft teams et à Skype entreprise online. Pour les comptes de ressources hébergés sur Skype entreprise Server 2019, voir [configurer les comptes de ressources](/SkypeForBusiness/hybrid/configure-onprem-ra).

## <a name="overview"></a>Vue d’ensemble

Si votre organisation utilise déjà au moins une licence de système téléphonique, vous pouvez attribuer un numéro de téléphone à la file d’attente d’appels du système téléphonique le processus est le suivant :

1. Obtenez un numéro de service.
2. Procurez-vous un système téléphonique [gratuit ou une licence de](teams-add-on-licensing/virtual-user.md) système téléphonique payant à utiliser avec le compte de ressources ou une licence de système téléphonique.
3. Créez le compte de ressource. Un standard automatique ou une file d’attente d’appels doivent être associés à un compte de ressources associé.
4. Attribuez le système téléphonique ou un système téléphonique-licence utilisateur virtuel au compte de ressources.
5. Affectez un numéro de téléphone de service au compte de ressource auquel vous venez d’affecter des licences.
6. Créer une file d’attente des appels du système téléphonique ou un standard automatique
7. Liez le compte de ressource avec une file d’attente d’appels ou un standard automatique.

<!-- Auto attendants created after November 1st, 2019 also create a new resource account that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available. -->

Si le standard automatique ou la file d’attente d’appels est imbriquée sous un standard automatique de niveau supérieur, le compte de ressources associé a uniquement besoin d’un numéro de téléphone si vous voulez que plusieurs points d’entrée soient présents dans la structure des standards automatiques et des files d’attente d’appels.

Pour rediriger les appels vers des utilisateurs de votre organisation qui sont hébergés en ligne, ils doivent disposer d’une licence de **système téléphonique** et être activés pour Enterprise Voice ou disposer de plans d’appel Office 365. Voir [attribuer des licences Microsoft teams](assign-teams-licenses.md). Pour les activer pour Enterprise Voice, vous pouvez utiliser Windows PowerShell. Par exemple, exécutez :`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

> [!WARNING]
> Afin d’éviter les problèmes liés au compte de ressources, procédez comme suit dans cet ordre.

Si la file d’attente d’appels du système téléphonique ou le standard automatique que vous créez est imbriqué et qu’il n’est pas nécessaire de composer un numéro de téléphone, le processus est le suivant :

1. Créer le compte de ressources
2. Créer une file d’attente des appels du système téléphonique ou un standard automatique
3. Associez le compte de ressource à une file d’attente d’appels du système téléphonique ou un standard automatique

### <a name="create-a-resource-account-with-a-phone-number"></a>Créer un compte de ressources avec un numéro de téléphone

<a name="phonenumber"> </a>

> [!IMPORTANT]
> Un numéro de téléphone n’est pas attribué directement au standard automatique ou à la file d’attente d’appels, mais plutôt au compte de ressources associé au standard automatique ou à la file d’attente d’appels.

Un standard automatique ou une file d’attente d’appels de niveau supérieur exige qu’un numéro de téléphone soit lié à son standard automatique. Pour créer un compte de ressource qui utilise un numéro de téléphone, le processus est le suivant :

1. Transférez ou obtenez un numéro de service gratuit ou payant. Le numéro ne peut pas être attribué à un autre service vocal ou à un autre compte de ressources.

   Avant d’affecter un numéro de téléphone à un compte de ressources, vous devez obtenir ou porter vos numéros de service gratuits ou payants existants. Une fois que vous avez obtenu les numéros de téléphone de service gratuits ou payants, ils s’affichent dans les**numéros de téléphone****vocaux** > du centre > d' **administration Microsoft teams**et le **type de numéro** est répertorié en tant que **service-** gratuit. Pour obtenir vos numéros de service, reportez-vous à la rubrique [obtention de numéros de service](getting-service-phone-numbers.md) ou, si vous souhaitez transférer un numéro de service existant, reportez-vous à la section transférer des [numéros de téléphone vers Office 365](transfer-phone-numbers-to-office-365.md).

   Si vous affectez un numéro de téléphone à un compte de ressources, vous pouvez désormais utiliser la licence utilisateur virtuel du système téléphonique sans frais. Cela fournit des fonctionnalités de système téléphonique aux numéros de téléphone au niveau de l’organisation, et vous permet de créer des capacités de mise en file d’attente et de standard automatique.

2. Obtenez une licence d’utilisateur virtuel de système téléphonique ou une licence de système téléphonique classique.

   Pour obtenir la licence de l’utilisateur virtuel, à partir du centre d’administration 365 de **** > Microsoft, accédez à la section**abonnements au composant additionnel**  > **services d’achat**de facturation et faites défiler jusqu’à la fin de l’appel de la licence « système téléphonique-utilisateur virtuel ». Sélectionnez **acheter maintenant**. Il y a un coût zéro, mais vous devez toujours suivre ces étapes pour acquérir la licence.
3. Créer un compte de ressource. Voir [créer un compte de ressources dans le centre d’administration Microsoft teams](#create-a-resource-account-in-microsoft-teams-admin-center) ou [créer un compte de ressources dans PowerShell](#create-a-resource-account-in-powershell)
4. Attribution d’un système téléphonique- [licence d’utilisateur virtuel](teams-add-on-licensing/virtual-user.md) ou de système téléphonique au compte de ressources. Voir [attribuer des licences Microsoft teams](assign-teams-licenses.md) et [affecter des licences à un utilisateur](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).
5. Attribuez le numéro de service au compte de ressource. Voir [affecter/retirer des numéros de téléphone et des services](#assignunassign-phone-numbers-and-services).
6. Configurez l’une des options suivantes :
   - [Standard automatique Cloud](create-a-phone-system-auto-attendant.md)
   - [File d’attente d’appels Cloud](create-a-phone-system-call-queue.md)
7. Liez le compte de ressources au standard automatique ou à la file d’attente d’appels. Voir [affectation/désaffectation de numéros de téléphone et services](#assignunassign-phone-numbers-and-services)

Lorsque vous créez un compte de ressources lors de la création d’un standard automatique, les licences sont appliquées automatiquement.

### <a name="create-a-resource-account-without-a-phone-number"></a>Créer un compte de ressources sans numéro de téléphone

Un standard automatique ou une file d’attente d’appels imbriqués nécessiteront un compte de ressources, mais dans de nombreux cas, le compte de ressource correspondant n’aura pas besoin d’un numéro de téléphone et de la gestion des licences nécessaires à la prise en charge d’un numéro de téléphone. Pour créer un compte de ressources sans numéro de téléphone, vous devez effectuer les tâches suivantes dans l’ordre suivant :

1. Créer un compte de ressource. Voir [créer un compte de ressources dans le centre d’administration Microsoft teams](#create-a-resource-account-in-microsoft-teams-admin-center) ou [créer un compte de ressources dans PowerShell](#create-a-resource-account-in-powershell)
2. Configurez l’une des options suivantes :
   - [Standard automatique Cloud](create-a-phone-system-auto-attendant.md)
   - [File d’attente d’appels Cloud](create-a-phone-system-call-queue.md)
3. Affectez le compte de ressource à la file d’attente d’appels ou au standard automatique. Voir [affectation/désaffectation de numéros de téléphone et services](#assignunassign-phone-numbers-and-services)


## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a>Créer un compte de ressources dans le centre d’administration Microsoft teams

Après avoir acheté une licence de système téléphonique, le centre d’administration Microsoft teams vous permet d’accéder aux**comptes de ressources**de **paramètres** > à l’échelle de l’organisation.

![Capture d’écran de la page comptes de ressources](media/r-a-master.png)

![Icône du numéro 1 qui référence une légende dans la capture d’écran précédente](media/sfbcallout1.png)

Pour créer un compte de ressource, cliquez sur **+ nouveau compte**. Dans la fenêtre qui s’affiche, indiquez le nom d’affichage et le nom d’utilisateur du compte de ressource (le nom de domaine doit remplir automatiquement), puis cliquez sur **Enregistrer**.

![Capture d’écran des options de nouveau compte de ressources](media/res-acct.png)

Ensuite, appliquez une licence au compte de ressources dans le centre d’administration O365, comme décrit dans la section [attribuer des licences aux utilisateurs dans Office 365 pour les entreprises](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) .

### <a name="edit-resource-account-name"></a>Modifier le nom du compte de la ressource

![Icône du numéro 2, qui référence une légende dans la capture d'](media/sfbcallout2.png) écran précédente, vous pouvez modifier le nom d’affichage du compte de la ressource à l’aide de l’option **modifier** . Lorsque vous avez fin, cliquez sur **Enregistrer** .
![Capture d’écran de l’option modifier le compte de ressources](media/r-a-edit.png)

<a name="phonenumber"> </a>

### <a name="assignunassign-phone-numbers-and-services"></a>Attribution/désaffectation des numéros de téléphone et services

![Icône du numéro 3, qui référence une légende dans la capture d'](media/sfbcallout3.png) écran précédente une fois que vous avez créé le compte de ressources et attribué la licence, vous pouvez cliquer sur **affecter/annuler** pour affecter un numéro de service au compte de ressource ou affecter la ressource compte vers une file d’attente d’appels ou un standard automatique qui existe déjà. L’attribution d’un numéro d’acheminement direct peut être réalisé à l’aide d’une cmdlet uniquement. Si la file d’attente d’appels ou le standard automatique doit toujours être créé, vous pouvez lier le compte de ressources lors de sa création. Lorsque vous avez fin, cliquez sur **Enregistrer** .

Pour affecter un routage direct ou un numéro hybride à un compte de ressource, vous devez utiliser PowerShell, reportez-vous à la section suivante.

> [!IMPORTANT]
> Si votre compte de ressource ne possède pas de licence valide, un échec de vérification interne entraîne un échec lorsque vous tentez d’affecter le numéro de téléphone au compte de ressource. Vous ne pourrez pas affecter le numéro ou associer le compte de ressources à une file d’attente d’appels ou un standard automatique.

> [!IMPORTANT]
> Un numéro de téléphone n’est pas attribué directement au standard automatique ou à la file d’attente d’appels, mais plutôt au compte de ressources associé au standard automatique ou à la file d’attente d’appels.

![Capture d’écran des options d’attribution/de désaffectation](media/r-a-assign.png)

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>Modifier un compte de ressource existant pour utiliser une licence utilisateur virtuel

Si vous décidez de basculer entre les licences sur votre compte de ressources existant d’une licence de système téléphonique vers une licence utilisateur virtuel, vous devez acquérir la licence utilisateur virtuel gratuite, puis suivre les étapes liées dans le centre d’administration Microsoft 365 pour [déplacer des utilisateurs vers un abonnement différent](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription). 

> [!WARNING]
> Supprimez toujours une licence de système téléphonique complet et attribuez-la à la licence utilisateur virtuel dans la même activité de licence. Si vous supprimez l’ancienne licence, enregistrez les modifications du compte, ajoutez la nouvelle licence, puis enregistrez de nouveau les paramètres du compte, le compte de ressources risque de ne plus fonctionner comme prévu. Si tel est le cas, nous vous recommandons de créer un compte de ressources pour la licence d’utilisateur virtuel et de supprimer le compte de ressource endommagé. 

## <a name="create-a-resource-account-in-powershell"></a>Créer un compte de ressources dans PowerShell

Selon que votre compte de ressources se trouve en ligne ou sur Skype entreprise Server 2019, vous devez vous connecter à l’invite PowerShell appropriée avec les privilèges d’administrateur.

- Les exemples de cmdlets PowerShell suivants illustrent la création d’un compte de ressource hébergé en ligne à l’aide [de New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps). 

- Pour les comptes de ressources hébergés sur Skype entreprise Server 2019 qui peuvent être utilisés avec les files d’attente d’appels Cloud et les standards automatiques Cloud, voir [configurer des files d’attente d’appels](/skypeforbusiness/hybrid/configure-call-queue.md) Cloud ou [configurer les standards automatiques du Cloud](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md). Les implémentations hybrides (numéros hébergés sur le routage direct) utilisent [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).

L’ID d’application que vous devez utiliser lors de la création des instances d’application est le suivant :

- **Standard automatique :** ce933385-9390-45D1-9512-c8d228074e07
- **File d’attente des appels :** 11cd3e2e-FCCB-42AD-AD00-878b93575e07

> [!NOTE]
> Si vous souhaitez que la file d’attente d’appels ou le standard automatique puissent être recherchés par les utilisateurs de Skype entreprise Server 2019, vous devez créer vos comptes de ressources dans Skype entreprise Server 2019, car les comptes de ressources en ligne ne sont pas synchronisés avec Active Directory. Lorsque les enregistrements DNS SRV pour sipfederationtls sont résolus en Skype entreprise Server 2019, les comptes de ressources **doivent** être créés dans Skype entreprise Server 2019 à l’aide de marketing Management Shell et synchronisés avec Azure AD en ligne.

 

1. Pour créer un compte de ressources en ligne à utiliser avec un standard automatique, utilisez la commande suivante :

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. Vous ne serez pas en mesure d’utiliser le compte de ressource tant que vous n’avez pas appliqué de licence. Pour plus d’informations sur la façon d’appliquer une licence à un compte dans le centre d’administration O365, voir [attribuer des licences aux utilisateurs dans Office 365 pour les entreprises](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) , ainsi qu' [affecter des licences Skype entreprise](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).

3. Facultatif Une fois la licence correcte appliquée au compte de ressources, vous pouvez affecter un numéro de téléphone au compte de ressource, comme illustré ci-dessous. Tous les comptes de ressources ne nécessitent pas de numéro de téléphone. Si vous n’avez pas appliqué de licence au compte de ressource, l’affectation de numéro de téléphone échoue.

   ``` Powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   Pour plus d’informations sur cette commande [, voir Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .

   > [!NOTE]
   > Il est plus facile de définir le numéro de téléphone en ligne à l’aide du centre d’administration de Microsoft Teams, comme décrit précédemment.

   Pour attribuer un numéro de téléphone de routage direct à un compte de ressources (hébergé dans Microsoft teams ou Skype entreprise Server 2019), utilisez l’applet de commande suivante pour Skype entreprise Online PowerShell :

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a>Gérer les paramètres de compte de ressources dans le centre d’administration Microsoft teams

Pour gérer les paramètres de compte de ressources dans le centre d’administration de Microsoft Teams, accédez à**comptes de ressources**de **paramètres** > à l’échelle de l’organisation, sélectionnez le compte de ressources dont vous avez besoin pour modifier les paramètres, puis cliquez sur le bouton **modifier** . dans l’écran **modifier le compte de ressources** , vous pouvez modifier les paramètres suivants :

- **Nom d’affichage** du compte
- File d’attente d’appels ou standard automatique qui utilise le compte
- Numéro de téléphone attribué au compte

Lorsque vous avez terminé, cliquez sur **Enregistrer**.

## <a name="delete-a-resource-account"></a>Supprimer un compte de ressource

Vérifiez que vous avez dissocié le numéro de téléphone du compte de ressources avant de le supprimer, afin d’éviter de rester bloqué dans le mode en attente. Pour ce faire, vous pouvez utiliser l’applet de commande suivante :

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

Lorsque vous procédez ainsi, vous pouvez supprimer le compte de ressources du portail d’administration Office 365, sous l’onglet utilisateurs.

Pour dissocier un numéro de téléphone de routage direct du compte de ressources, utilisez l’applet de commande suivante :

``` Powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a>Résolution des problèmes

Si vous ne voyez pas le numéro de téléphone attribué au compte de ressources dans le centre d’administration teams et que vous ne pouvez pas attribuer le numéro à partir de cet emplacement, vérifiez les points suivants :

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

Si l’attribut Service affiche le point de terminaison d’une application Skype entreprise, exécutez l’applet de demande ci-dessous :

``` Powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> Actualisez la page Web du centre d’administration teams après avoir exécuté le cmldet et vous devriez pouvoir affecter le numéro correctement.

## <a name="related-information"></a>Informations connexes

Pour les implémentations hybrides avec Skype entreprise Server, procédez comme suit :

   [Planifier les standards automatiques cloud](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [Planifier les files d’attente d’appels cloud](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [Configurer les comptes de ressources locaux](/SkypeForBusiness/hybrid/configure-onprem-ra)


Pour les implémentations dans teams ou Skype entreprise Online :

   [Un standard Cloud automatique, qu’est-ce que c’est ?](what-are-phone-system-auto-attendants.md)

   [Configurer un standard automatique dans le cloud](/microsoftteams/create-a-phone-system-auto-attendant)

   [Exemple de petite entreprise : configurer un standard automatique](/microsoftteams/tutorial-org-aa)

   [Créer une file d’attente d’appels cloud](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[Nouveau-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[Nouveau-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Système téléphonique-licence utilisateur virtuel](teams-add-on-licensing/virtual-user.md)

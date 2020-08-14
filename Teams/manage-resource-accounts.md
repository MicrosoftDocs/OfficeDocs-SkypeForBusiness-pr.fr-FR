---
title: Gérer les comptes de ressource dans Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: Dans cet article, vous allez découvrir comment créer, modifier et gérer des comptes de ressources dans Microsoft Teams.
ms.openlocfilehash: 90e8ab26782424c6cc341936f185a253c6d1fbe6
ms.sourcegitcommit: eb8b573a426b6a68c763968c4cd2d45bc0d6a4b4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46672855"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Gérer les comptes de ressources dans Microsoft Teams

Un compte de ressource est également connu sous le nom d' *objet utilisateur désactivé* dans Azure ad et peut être utilisé pour représenter des ressources en général. Dans Exchange, il peut être utilisé pour représenter des salles de conférence, par exemple, et leur permettre d’avoir un numéro de téléphone. Un compte de ressource peut être hébergé dans Microsoft 365 ou sur site à l’aide de Skype entreprise Server 2019.

Dans Microsoft teams ou Skype entreprise Online, chaque file d’attente d’appels du système téléphonique ou le standard automatique est requis pour disposer d’au moins un compte de ressources associé. La nécessité pour un compte de ressources d’avoir besoin d’un numéro de téléphone dépend de la manière dont vous souhaitez utiliser la file d’attente d’appels ou le standard automatique associé, comme illustré dans le schéma suivant. Vous pouvez également vous référer aux articles sur les files d’attente d’appels et aux standards automatiques liés au bas de cet article avant d’affecter un numéro de téléphone à un compte de ressources.

![exemple de comptes de ressources et de licences utilisateur](media/resource-account.png)

> [!NOTE]
> Cet article s’applique à Microsoft teams et à Skype entreprise online. Pour les comptes de ressources hébergés sur Skype entreprise Server 2019, voir [configurer les comptes de ressources](/SkypeForBusiness/hybrid/configure-onprem-ra).

## <a name="assign-a-phone-number-to-a-phone-system-call-queue"></a>Affectation d’un numéro de téléphone à la file d’attente d’appels d’un système téléphonique

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

Pour rediriger les appels vers des utilisateurs de votre organisation qui sont hébergés en ligne, ils doivent disposer d’une licence de **système téléphonique** et être activés pour Enterprise Voice ou disposer d’offres Microsoft 365 ou Office 365. Voir [affecter des licences de compléments Microsoft teams](teams-add-on-licensing/assign-teams-add-on-licenses.md). Pour les activer pour Enterprise Voice, vous pouvez utiliser Windows PowerShell. Par exemple, exécutez : `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

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

   Avant d’affecter un numéro de téléphone à un compte de ressources, vous devez obtenir ou porter vos numéros de service gratuits ou payants existants. Une fois que vous avez obtenu les numéros de téléphone de service gratuits ou payants, ils s’affichent dans les numéros de téléphone vocaux du **Centre d’administration Microsoft teams**  >  **Voice**  >  **Phone numbers**et le **type de numéro** est répertorié en tant que **service-** gratuit. Pour obtenir vos numéros de service, reportez-vous à la rubrique [obtention de numéros de service](getting-service-phone-numbers.md) ou pour transférer un numéro de service existant, reportez-vous à la section transférer des [numéros de téléphone vers teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

   Si vous affectez un numéro de téléphone à un compte de ressources, vous pouvez désormais utiliser la licence utilisateur virtuel du système téléphonique sans frais. Cela fournit des fonctionnalités de système téléphonique aux numéros de téléphone au niveau de l’organisation, et vous permet de créer des capacités de mise en file d’attente et de standard automatique.

2. Obtenez une licence d’utilisateur virtuel de système téléphonique ou une licence de système téléphonique classique.

   Pour obtenir la licence de l’utilisateur virtuel, dans le centre d’administration 365 de **Billing**Microsoft, accédez à  >  la section abonnements au composant additionnel**services d’achat**de facturation  >  **Add-on subscriptions** et faites défiler jusqu’à la fin, vous verrez la licence « système téléphonique-utilisateur virtuel ». Sélectionnez **acheter maintenant**. Il y a un coût zéro, mais vous devez toujours suivre ces étapes pour acquérir la licence.
3. Créer un compte de ressource. Pour plus d’affichage, voir [créer un compte de ressources dans le centre d’administration Microsoft teams](#create-a-resource-account-in-the-microsoft-teams-admin-center) ou [créer un compte de ressources dans PowerShell](#create-a-resource-account-in-powershell).
4. Attribution d’un système téléphonique- [licence d’utilisateur virtuel](teams-add-on-licensing/virtual-user.md) ou de système téléphonique au compte de ressources. Voir [affecter des licences de compléments Microsoft teams](teams-add-on-licensing/assign-teams-add-on-licenses.md) et [attribuer des licences aux utilisateurs](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).
5. Attribuez le numéro de service au compte de ressource. Voir [affecter/retirer des numéros de téléphone et des services](#assignunassign-phone-numbers-and-services).
6. Configurez l’une des options suivantes :
   - [Standard automatique Cloud](create-a-phone-system-auto-attendant.md)
   - [File d’attente d’appels Cloud](create-a-phone-system-call-queue.md)
7. Liez le compte de ressources au standard automatique ou à la file d’attente d’appels. Voir [affectation/désaffectation de numéros de téléphone et services](#assignunassign-phone-numbers-and-services)

Lorsque vous créez un compte de ressources lors de la création d’un standard automatique, les licences sont appliquées automatiquement.

### <a name="create-a-resource-account-without-a-phone-number"></a>Créer un compte de ressources sans numéro de téléphone

Un standard automatique ou une file d’attente d’appels imbriqués nécessiteront un compte de ressources, mais dans de nombreux cas, le compte de ressource correspondant n’aura pas besoin d’un numéro de téléphone et de la gestion des licences nécessaires à la prise en charge d’un numéro de téléphone. Pour créer un compte de ressources sans numéro de téléphone, vous devez effectuer les tâches suivantes dans l’ordre suivant :

1. Créer un compte de ressource. Pour plus d’affichage, voir [créer un compte de ressources dans le centre d’administration Microsoft teams](#create-a-resource-account-in-the-microsoft-teams-admin-center) ou [créer un compte de ressources dans PowerShell](#create-a-resource-account-in-powershell).

2. Configurez l’une des options suivantes :
   - [Standard automatique Cloud](create-a-phone-system-auto-attendant.md)
   - [File d’attente d’appels Cloud](create-a-phone-system-call-queue.md)
   
3. Affectez le compte de ressource à la file d’attente d’appels ou au standard automatique. Voir [affecter/retirer des numéros de téléphone et des services](#assignunassign-phone-numbers-and-services).


## <a name="create-a-resource-account-in-the-microsoft-teams-admin-center"></a>Créer un compte de ressources dans le centre d’administration Microsoft teams

Après avoir acheté une licence de système téléphonique, dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à comptes de ressources de paramètres à l’échelle de l' **organisation**  >  **Resource accounts**.

![Capture d’écran de la page comptes de ressources](media/r-a-master.png)

![Icône du numéro 1 qui référence une légende dans la capture d’écran précédente](media/teamscallout1.png)

Pour créer un compte de ressource, cliquez sur **Ajouter**. Dans le **volet ajouter un compte de ressources** , spécifiez le nom d' **affichage**, le nom **d’utilisateur** (le nom de domaine doit remplir automatiquement) et le **type de compte de ressources** pour le compte de ressource. Le type de compte de ressource peut être de type **standard automatique** ou **file d’attente d’appels**, en fonction de l’application que vous voulez associer au compte de ressources. Lorsque vous êtes prêt, cliquez sur **Enregistrer**.

![Capture d’écran des options de nouveau compte de ressources](media/res-acct.png)

Appliquez ensuite une licence au compte de ressources dans le centre d’administration Microsoft 365, comme décrit dans la section [attribuer des licences aux utilisateurs](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

### <a name="edit-resource-account"></a>Modifier le compte de ressources 

![Icône du numéro 2, qui référence une légende dans la capture d’écran précédente, ](media/teamscallout2.png) vous pouvez modifier le **nom d’affichage** du compte de ressources et le type de compte de **ressources** à l’aide de l’option **modifier** . Lorsque vous avez fin, cliquez sur **Enregistrer** .

![Capture d’écran de l’option modifier le compte de ressources](media/r-a-edit.png)

<a name="phonenumber"> </a>

### <a name="assignunassign-phone-numbers-and-services"></a>Attribution/désaffectation des numéros de téléphone et services

![Icône du numéro 3, qui référence une légende dans la capture d’écran précédente ](media/teamscallout3.png) une fois que vous avez créé le compte de ressources et attribué la licence, vous pouvez cliquer sur **affecter/annuler** pour attribuer un numéro de service au compte de ressource, définir le type de numéro de téléphone ou affecter le compte de ressource à un standard automatique ou une file d’attente d’appels existante. L’attribution d’un numéro d’acheminement direct peut être réalisé à l’aide d’une cmdlet uniquement. Si vous n’avez pas encore créé la file d’attente d’appels ou le standard automatique que vous allez associer au compte de ressources, laissez ce champ vide. Vous pouvez lier le compte de ressources lors de sa création. Lorsque vous avez fin, cliquez sur **Enregistrer** .

Les options disponibles pour le **type de numéro de téléphone** sont les suivantes :

- Aucun
- Online
- Numéro gratuit
- Sur site

![Capture d’écran des options d’attribution/de désaffectation](media/r-a-assign.png)

Pour affecter un routage direct ou un numéro hybride à un compte de ressource, vous devez utiliser PowerShell, reportez-vous à la section suivante.

> [!IMPORTANT]
> Si votre compte de ressource ne possède pas de licence valide, un échec de vérification interne entraîne un échec lorsque vous tentez d’affecter le numéro de téléphone au compte de ressource. Vous ne pourrez pas affecter le numéro ou associer le compte de ressources à une file d’attente d’appels ou un standard automatique.

> [!IMPORTANT]
> Un numéro de téléphone n’est pas attribué directement au standard automatique ou à la file d’attente d’appels, mais plutôt au compte de ressources associé au standard automatique ou à la file d’attente d’appels.



## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>Modifier un compte de ressource existant pour utiliser une licence utilisateur virtuel

Si vous décidez de basculer entre les licences sur votre compte de ressources existant d’une licence de système téléphonique vers une licence utilisateur virtuel, vous devez acquérir la licence utilisateur virtuel gratuite, puis suivre les étapes du centre d’administration 365 Microsoft pour [déplacer des utilisateurs vers un autre abonnement](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Supprimez toujours une licence de système téléphonique complet et attribuez-la à la licence utilisateur virtuel dans la même activité de licence. Si vous supprimez l’ancienne licence, enregistrez les modifications du compte, ajoutez la nouvelle licence, puis enregistrez de nouveau les paramètres du compte, le compte de ressources risque de ne plus fonctionner comme prévu. Si tel est le cas, nous vous recommandons de créer un compte de ressources pour la licence d’utilisateur virtuel et de supprimer le compte de ressource endommagé.

## <a name="create-a-resource-account-in-powershell"></a>Créer un compte de ressources dans PowerShell

Selon que votre compte de ressources se trouve en ligne ou sur Skype entreprise Server 2019, vous devez vous connecter à l’invite PowerShell appropriée avec les privilèges d’administrateur.

- Les exemples de cmdlets PowerShell suivants illustrent la création d’un compte de ressource hébergé en ligne à l’aide [de New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps). 

- Pour les comptes de ressources hébergés sur Skype entreprise Server 2019 qui peuvent être utilisés avec les files d’attente d’appels Cloud et les standards automatiques Cloud, voir [planifier des files d’attente d’appels Cloud](/SkypeforBusiness/hybrid/plan-call-queue) ou [planifier des standards automatiques Cloud](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant). Les implémentations hybrides (numéros d’hébergement sur le routage direct) sont configurées à l’aide de l’applet de nouvelle applet de [CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) sur un serveur Skype entreprise Server 2019 local.

L’ID d’application que vous devez utiliser lors de la création des instances d’application est le suivant :

- **Standard automatique :** ce933385-9390-45D1-9512-c8d228074e07
- **File d’attente des appels :** 11cd3e2e-FCCB-42AD-AD00-878b93575e07

> [!NOTE]
> Si vous souhaitez que la file d’attente d’appels ou le standard automatique puissent être recherchés par les utilisateurs de Skype entreprise Server 2019, vous devez créer vos comptes de ressources dans Skype entreprise Server 2019, car les comptes de ressources en ligne ne sont pas synchronisés avec Active Directory. Lorsque les enregistrements DNS SRV pour sipfederationtls sont résolus en Skype entreprise Server 2019, les comptes de ressources **doivent** être créés dans Skype entreprise Server 2019 à l’aide de marketing Management Shell et synchronisés avec Azure AD en ligne.

 

1. Pour créer un compte de ressources en ligne à utiliser avec un standard automatique, utilisez la commande suivante :

    ```powershell
    New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId "ce933385-9390-45d1-9512-c8d228074e07" -DisplayName "Resource account 1"
    ```

2. Vous ne serez pas en mesure d’utiliser le compte de ressource tant que vous n’avez pas appliqué de licence. Pour plus d’informations sur l’application d’une licence à un compte dans le centre d’administration 365 Microsoft, voir[attribuer des licences à des utilisateurs](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) et [attribuer des licences Skype entreprise](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).

3. Facultatif Une fois la licence correcte appliquée au compte de ressources, vous pouvez affecter un numéro de téléphone au compte de ressource, comme illustré ci-dessous. Tous les comptes de ressources ne nécessitent pas de numéro de téléphone. Si vous n’avez pas appliqué de licence au compte de ressource, le numéro de téléphone ne peut pas être attribué.

   ```powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   Pour plus d’informations sur cette commande [, voir Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .

   > [!NOTE]
   > Il est plus facile de définir le numéro de téléphone en ligne à l’aide du centre d’administration de Microsoft Teams, comme décrit précédemment.

   Pour attribuer un numéro de téléphone de routage direct à un compte de ressources (hébergé dans Microsoft teams ou Skype entreprise Server 2019), utilisez l’applet de commande suivante pour Skype entreprise Online PowerShell :

   ```powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-the-microsoft-teams-admin-center"></a>Gérer les paramètres de compte de ressources dans le centre d’administration Microsoft teams

Pour gérer les paramètres de compte de ressources dans le centre d’administration de Microsoft Teams, accédez à comptes de ressources de paramètres à l’échelle de l' **organisation**  >  **Resource accounts**, sélectionnez le compte de ressources dont vous avez besoin pour modifier les paramètres, puis cliquez sur **modifier**. Dans le volet **modifier le compte de ressources** , vous pouvez modifier les paramètres suivants :

- **Nom d’affichage** du compte
- File d’attente d’appels ou standard automatique qui utilise le compte
- Numéro de téléphone attribué au compte

Lorsque vous avez terminé, cliquez sur **Enregistrer**.

## <a name="delete-a-resource-account"></a>Supprimer un compte de ressource

Vérifiez que vous avez dissocié le numéro de téléphone du compte de ressources avant de le supprimer, afin d’éviter de rester bloqué dans le mode en attente. Pour ce faire, vous pouvez utiliser l’applet de commande suivante :

```powershell
Set-CsOnlineVoiceApplicationInstance -Identity <Resource Account oid> -TelephoneNumber $null
```

Après quoi, vous pouvez supprimer le compte de ressources dans le centre d’administration 365 Microsoft, sous l’onglet utilisateurs.

Pour dissocier un numéro de téléphone de routage direct du compte de ressources, utilisez l’applet de commande suivante :

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a>Résolution des problèmes

### <a name="you-dont-see-the-phone-number-assigned-to-the-resource-account-in-the-microsoft-teams-admin-center"></a>Le numéro de téléphone attribué au compte de ressource n’apparaît pas dans le centre d’administration Microsoft teams

Si vous ne voyez pas le numéro de téléphone attribué au compte de ressources dans le centre d’administration Microsoft teams et que vous ne pouvez pas attribuer le numéro à partir de cet emplacement, vérifiez les points suivants :

```powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

Si l’attribut Service affiche le point de terminaison d’une application Skype entreprise, exécutez l’applet de demande ci-dessous :

```powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> Actualisez la page Web du centre d’administration teams après avoir exécuté le cmldet et vous devriez pouvoir affecter le numéro correctement.

### <a name="you-get-a-we-cant-use-this-resource-account-for-services-error-message"></a>Vous obtenez un « nous ne pouvons pas utiliser ce compte de ressources pour les services ». message d’erreur

<a name="blocksignin"> </a>

Vous recevez le message d’erreur suivant lorsque vous essayez d’utiliser un compte de ressources :

«Nous ne pouvons pas utiliser ce compte de ressources pour les services. Le compte de ressource doit être désactivé et empêché de se connecter. Vous devez bloquer les connexions pour ce compte de ressources dans la page utilisateurs du centre d’administration 365 Microsoft.»

Par défaut, lorsque vous créez un compte de ressource, il est désactivé et la connexion est bloquée pour le compte. Vous ne devez pas modifier ces paramètres. Pour résoudre ce problème, bloquez le compte de ressources pour vous connecter. Pour ce faire :

1. Dans le centre d’administration Microsoft 365, accédez à **utilisateurs**, recherchez, puis sélectionnez le compte de ressource.
2. Dans la partie supérieure du volet sous le nom d’affichage, cliquez sur **bloquer cet utilisateur ?**, activez la case à cocher **empêcher cet utilisateur de vous connecter** , puis cliquez sur **enregistrer les modifications**.

   ![Capture d’écran de l’option Bloquer cet utilisateur](media/res-acct-block.png)

    Après cela, vous verrez « connexion bloquée » sous le nom d’affichage.

      ![Capture d’écran du message de connexion bloqué](media/res-acct-sign-in-blocked.png)

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

[Nouveau-CsOnlineApplicationInstanceAssociation](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstanceassociation?view=skype-ps)

[Système téléphonique-licence utilisateur virtuel](teams-add-on-licensing/virtual-user.md)

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
- m365initiative-voice
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
ms.openlocfilehash: 2a043b608dfe311003dea26acc8a0c236460fad5
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031020"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Gérer les comptes de ressources dans Microsoft Teams

Un compte de ressource est un objet utilisateur désactivé dans Azure AD et peut être utilisé pour représenter des ressources en général. Par exemple, un compte de ressource peut être utilisé dans Exchange pour représenter des salles de conférence et leur permettre d’avoir un numéro de téléphone et un calendrier. Un compte de ressource peut être hébergé dans Microsoft 365 ou sur site à l’aide de Skype entreprise Server 2019.

Dans Microsoft Teams, un compte de ressource est requis pour chaque standard automatique ou file d’attente d’appels. Des numéros de téléphone de service pourront également être attribués aux comptes de ressources. C’est ainsi que vous attribuez des numéros de téléphone aux standards automatiques et aux files d’attente d’appels permettant aux appelants d’équipes externes de joindre le standard automatique ou la file d’attente d’appels.

Cet article décrit la création de comptes de ressources et leur disponibilité pour une utilisation avec des standards automatiques et des files d’attente d’appels.

Avant de commencer les procédures décrites dans cet article, assurez-vous que vous avez terminé les actions suivantes :

- [Obtenir des licences utilisateur virtuelles](#obtain-virtual-user-licenses)
- [Obtention des numéros de service](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a>Obtenir des licences utilisateur virtuelles

Pour pouvoir utiliser les standards automatiques et les files d’attente, les comptes de ressources doivent disposer d’une licence. Vous pouvez utiliser un *système téléphonique Microsoft 365 gratuit-licence utilisateur virtuel* . Pour obtenir ces licences, voir [licence utilisateur virtuel](teams-add-on-licensing/virtual-user.md).

Nous vous décrivons comment attribuer la licence à un compte de ressources plus loin dans cet article.

Pour obtenir la licence de l’utilisateur virtuel, dans le centre d’administration 365 de **Billing** Microsoft, accédez à  >  la section abonnements au composant additionnel **services d’achat**  >  **de** facturation *Phone System - Virtual User* et faites défiler jusqu’à la fin. Sélectionnez **acheter maintenant**. Il y a un coût zéro, mais vous devez toujours suivre ces étapes pour acquérir la licence.

### <a name="obtain-service-numbers"></a>Obtention des numéros de service

Les numéros de service sont facultatifs pour les standards automatiques et les files d’attente d’appels, mais vous devez disposer d’au moins un numéro de service pour permettre aux appelants de joindre le standard automatique et la configuration de la file d’attente. Pour tout standard automatique ou file d’attente d’appels que vous souhaitez joindre directement par un numéro de service, vous devez disposer d’un compte de ressources avec un numéro de service associé.

Les comptes de ressources peuvent utiliser des numéros de service gratuits ou payants. Vous pouvez demander de nouveaux numéros ou transférer des numéros existants à partir d’un autre opérateur.

Pour obtenir de nouveaux numéros de service, consultez la rubrique [obtention de numéros de téléphone de service](getting-service-phone-numbers.md).

Pour porter un numéro à partir d’un autre opérateur, voir [transférer des numéros de téléphone vers teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

## <a name="create-a-resource-account"></a>Créer un compte de ressources

Vous pouvez créer un compte de ressources dans le centre d’administration Teams.

![Capture d’écran de l’interface utilisateur Ajouter un compte de ressources](media/resource-account-add.png)

1. Dans le centre d’administration Teams, développez **paramètres à l’échelle** de l’organisation, puis cliquez sur **comptes de ressources**.

2. Cliquez sur **Ajouter**.

3. Dans le **volet ajouter un compte de ressources** , spécifiez le nom d' **affichage** , le nom **d’utilisateur** et le **type de compte de ressource**. Le type de compte de ressource peut être de type **standard automatique** ou **file d’attente d’appels** , selon la manière dont vous envisagez d’utiliser ce compte de ressources.

4. Cliquez sur **Enregistrer**.

![Capture d’écran d’une liste de comptes de ressources](media/resource-accounts-page.png)

## <a name="assign-a-license"></a>Attribuer une licence

Pour chaque compte de ressource, vous devez attribuer un *système téléphonique Microsoft 365* ou une licence de *système téléphonique* .

![Capture d’écran de l’interface utilisateur affecter des licences dans le centre d’administration Microsoft 365](media/resource-account-assign-virtual-user-license.png)

1. Dans le centre d’administration Microsoft 365, cliquez sur le compte de ressources auquel vous souhaitez attribuer une licence.

2. Dans l’onglet **licences et applications** , sous **licences** , sélectionnez **système téléphonique Microsoft 365-utilisateur virtuel**.

3. Cliquez sur **enregistrer les modifications**.

## <a name="assign-a-service-number"></a>Affectation d’un numéro de service

Si vous envisagez d’utiliser le compte de ressources avec un standard automatique ou une file d’attente d’appels qui nécessite un numéro de service, attribuez un numéro au compte de ressource.

![Capture d’écran de l’interface utilisateur affecter des numéros de service](media/resource-account-assign-phone-number.png)

1. Dans le centre d’administration Teams, dans la page **comptes de ressources** , sélectionnez le compte de ressources auquel vous souhaitez attribuer un numéro de service, puis cliquez sur **affecter/** retirer.

2. Dans la liste déroulante **type de numéro de téléphone** , choisissez le type de numéro que vous voulez utiliser.

3. Dans la zone **numéro de téléphone attribué** , recherchez le numéro que vous voulez utiliser, puis cliquez sur **Ajouter**.

4. Cliquez sur **Enregistrer**.


Pour affecter un routage direct ou un numéro hybride à un compte de ressources, vous devez utiliser PowerShell :

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a>Étapes suivantes

Lorsque vous avez terminé la configuration du compte de ressources et que vous affectez un numéro de service le cas échéant, vous pouvez utiliser le compte de ressources avec un standard automatique ou une file d’attente d’appels.

Voir les références suivantes :

 - [Standard automatique Cloud](create-a-phone-system-auto-attendant.md)

 - [File d’attente d’appels Cloud](create-a-phone-system-call-queue.md)

Vous pouvez modifier le nom d' **affichage** du compte de ressources et le type de **compte de ressources** en utilisant l’option **modifier** . Lorsque vous avez fin, cliquez sur **Enregistrer** .

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>Modifier un compte de ressource existant pour utiliser une licence utilisateur virtuel

Si vous décidez de basculer entre les licences sur votre compte de ressources existant d’une licence de **système téléphonique** vers une licence utilisateur virtuel, vous devez acquérir la licence utilisateur virtuel gratuite, puis suivre les étapes du centre d’administration 365 Microsoft pour [déplacer des utilisateurs vers un autre abonnement](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Supprimez toujours une licence de système téléphonique complet et attribuez-la à la licence utilisateur virtuel dans la même activité de licence. Si vous supprimez l’ancienne licence, enregistrez les modifications du compte, ajoutez la nouvelle licence, puis enregistrez de nouveau les paramètres du compte, le compte de ressources risque de ne plus fonctionner comme prévu. Si tel est le cas, nous vous recommandons de créer un compte de ressources pour la licence d’utilisateur virtuel et de supprimer le compte de ressource endommagé.

## <a name="skype-for-business-server-2019"></a>Skype entreprise Server 2019

Pour les comptes de ressources hébergés sur Skype entreprise Server 2019 qui peuvent être utilisés avec les files d’attente d’appels Cloud et les standards automatiques Cloud, voir [planifier des files d’attente d’appels Cloud](/SkypeforBusiness/hybrid/plan-call-queue) ou [planifier des standards automatiques Cloud](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant). Les implémentations hybrides (numéros d’hébergement sur le routage direct) sont configurées à l’aide de l’applet de nouvelle applet de [CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) sur un serveur Skype entreprise Server 2019 local.

Les ID d’application que vous devez utiliser lors de la création des instances d’application sont les suivants :

- **Standard automatique :** ce933385-9390-45D1-9512-c8d228074e07
- **File d’attente des appels :** 11cd3e2e-FCCB-42AD-AD00-878b93575e07

> [!NOTE]
> Si vous souhaitez que la file d’attente d’appels ou le standard automatique puissent être recherchés par les utilisateurs de Skype entreprise Server 2019, vous devez créer vos comptes de ressources dans Skype entreprise Server 2019, car les comptes de ressources en ligne ne sont pas synchronisés avec Active Directory. Lorsque les enregistrements DNS SRV pour sipfederationtls sont résolus vers Skype entreprise Server 2019, les comptes de ressources **doivent** être créés dans Skype entreprise Server 2019 à l’aide de marketing Management Shell et synchronisés avec Azure ad.

Pour les implémentations hybrides avec Skype entreprise Server, procédez comme suit :

   [Planifier les standards automatiques cloud](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [Planifier les files d’attente d’appels cloud](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [Configurer les comptes de ressources locaux](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a>Supprimer un compte de ressource

Vérifiez que vous avez dissocié le numéro de téléphone du compte de ressources avant de le supprimer, afin d’éviter de rester bloqué dans le mode en attente.

Après quoi, vous pouvez supprimer le compte de ressources dans le centre d’administration 365 Microsoft, sous l’onglet utilisateurs.

Pour dissocier un numéro de téléphone de routage direct du compte de ressources, utilisez l’applet de commande suivante :

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

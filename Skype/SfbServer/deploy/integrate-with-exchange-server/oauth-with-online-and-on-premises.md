---
title: Intégration entre Skype pour Business Online et Exchange server
ms.reviewer: cbland
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/2/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Configuration OAuth authentification entre Exchange sur site et Skype pour Business Online permet la Skype pour les fonctionnalités d’entreprise et l’intégration d’Exchange décrites dans prise en charge de la fonctionnalité.
ms.openlocfilehash: 976aae8287c1d9f209975d53ebc64ac80033c591
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216661"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a>Configurer l’intégration entre Skype pour les entreprises en ligne ou les équipes Microsoft et Exchange Server 

Configuration de l’intégration entre Exchange server et Skype pour Business Online permet la Skype pour les fonctionnalités d’entreprise et l’intégration d’Exchange décrites dans la [fonction prend en charge](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).

Cette rubrique s’applique à l’intégration avec Exchange Server 2013 par le biais de 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Que devez-vous savoir avant de commencer ?

- Temps estimé pour réaliser cette tâche : 15 minutes

-  Avant de pouvoir réaliser cette (ces) procédure(s), des autorisations doivent vous avoir été attribuées. Pour voir les autorisations dont vous avez besoin, consultez la rubrique [autorisations d’infrastructure Exchange et Shell](https://go.microsoft.com/fwlink/p/?LinkId=746511) .

- Pour plus d’informations sur les raccourcis clavier applicables aux procédures de cette rubrique, voir [raccourcis clavier dans le centre d’administration Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Configurer l’intégration entre Exchange Server et O365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Étape 1 : Configurer l’authentification OAuth entre Exchange Server et O365

Effectuez les étapes de l’article suivant :

[Configurer l’authentification OAuth entre des organisations Exchange et Exchange Online](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a>Étape 2 : Créer un nouveau compte d’utilisateur de messagerie pour le Skype pour Business en ligne ou une Application partenaire équipes

Cette étape est effectuée sur le serveur Exchange. Elle crée un utilisateur de messagerie et lui attribue les droits de rôle de gestion adaptés. Ce compte sera alors utilisé lors de l’étape suivante.

Spécifiez un domaine vérifié pour votre organisation Exchange. Ce domaine doit être le même domaine que celui utilisé en tant que le domaine SMTP principal utilisé pour les comptes Exchange sur site. Ce domaine est appelé \<votre domaine vérifié\> dans la procédure suivante. En outre, le \<DomainControllerFQDN\> doit être le nom de domaine complet du contrôleur de domaine.

``` Powershell
$user = New-MailUser -Name O365-ApplicationAccount -ExternalEmailAddress O365-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Cette commande masquera le nouvel utilisateur de messagerie dans les listes d’adresses.

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Les deux commandes qui suivent permettront d’attribuer les rôles de gestion ArchiveApplication et UserApplication à ce nouveau compte.

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a>Étape 3 : Créer et activer une Application partenaire pour Skype pour Business en ligne ou des équipes

Créez une nouvelle application partenaire et utilisez le compte que vous venez de créer. Exécutez la commande suivante dans Exchange PowerShell dans votre environnement local organisation Exchange.

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a>Vérifiez que tout fonctionne correctement

Vérifiez que la configuration est correcte en vérifiant que certaines fonctionnalités fonctionnent correctement. 

1. Vérifier la délégation du calendrier Outlook fonctionne comprise entre les deux utilisateurs équipes avec Exchange Server 2016 ou 2019 les boîtes aux lettres.

2. Vérifiez l’historique des conversations pour les clients mobiles est visible dans le dossier historique des conversations Outlook.

Consultez également le trafic. Le trafic dans un protocole OAuth est vraiment différente (et ne ressemble à l’authentification de base), en particulier autour de domaines, où vous allez commencer à voir le trafic émetteur qui ressemble à ceci : 00000004-0000-0ff1-ce00-000000000000 @ (parfois avec un / avant le signe @), dans les jetons sont passées. Vous ne verrez pas un nom d’utilisateur ou le mot de passe, qui est le point de OAuth. Mais vous verrez l’émetteur « Office », dans ce cas '4' Skype pour les entreprises – et le domaine de votre abonnement.

Si vous souhaitez que vous utilisez correctement OAuth, assurez-vous que vous savez quoi s’attendre et savoir quoi doit ressembler le trafic. C' [est ici à quoi s’attendre](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), Voici un assez standard [exemple du trafic OAuth dans une application Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (très utile lire, s’il n’utilise des jetons d’actualisation), et il existe des extensions de Fiddler qui vous permet de rechercher dans votre JWT (JSON OAuth Jeton Web).

Voici un [exemple de configuration](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), mais vous pouvez utiliser n’importe quel outil de suivi réseau que vous entreprenez ce processus.

## <a name="related-topics"></a>Voir aussi

[Configurer l’authentification OAuth entre des organisations Exchange et Exchange Online](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

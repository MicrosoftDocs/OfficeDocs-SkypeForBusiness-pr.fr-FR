---
title: Intégration de Skype entreprise Online et du serveur Exchange
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: La configuration de l’authentification OAuth entre Exchange sur site et Skype entreprise Online permet d’activer les fonctionnalités d’intégration de Skype entreprise et Exchange décrites dans la rubrique prise en charge des fonctionnalités.
ms.openlocfilehash: be1fd4ae0c1a1046a8da1d9a30550ac238a4034a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278125"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a>Configurer l’intégration entre Skype entreprise Online, Microsoft teams et Exchange Server 

La configuration de l’intégration d’Exchange Server et de Skype entreprise Online permet d’activer les fonctionnalités d’intégration Skype entreprise et Exchange décrites dans la rubrique [prise en charge](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)des fonctionnalités.

Cette rubrique s’applique à l’intégration à Exchange Server 2013 à 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Que devez-vous savoir avant de commencer ?

- Temps estimé pour réaliser cette tâche : 15 minutes

-  Avant de pouvoir réaliser cette (ces) procédure(s), des autorisations doivent vous avoir été attribuées. Pour connaître les autorisations dont vous avez besoin, consultez la rubrique [autorisations d’infrastructure Exchange et noyau](https://go.microsoft.com/fwlink/p/?LinkId=746511) .

- Pour plus d’informations sur les raccourcis clavier susceptibles d’être appliqués aux procédures décrites dans cette rubrique, voir [raccourcis clavier dans le centre d’administration Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Configurer l’intégration entre Exchange Server et O365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Étape 1: configuration de l’authentification OAuth entre Exchange Server et O365

Suivez les étapes décrites dans l’article suivant:

[Configurer l’authentification OAuth entre les organisations Exchange et Exchange Online](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a>Étape 2: créer un compte d’utilisateur de messagerie pour l’application partenaire de Skype entreprise Online ou teams

Cette étape est exécutée sur le serveur Exchange. Elle crée un utilisateur de messagerie et lui attribue les droits de rôle de gestion adaptés. Ce compte sera alors utilisé lors de l’étape suivante.

Spécifiez un domaine vérifié pour votre organisation Exchange. Ce domaine doit être identique à celui utilisé pour le domaine SMTP principal utilisé pour les comptes Exchange locaux. Ce domaine est connu sous \<le nom de\> domaine vérifié dans la procédure suivante. Par ailleurs, \<le\> DomainControllerFQDN doit être le nom de domaine complet d’un contrôleur de domaine.

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

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a>Étape 3: créer et activer une application partenaire pour Skype entreprise Online ou teams

Créez une nouvelle application partenaire et utilisez le compte que vous venez de créer. Exécutez la commande suivante dans Exchange PowerShell dans votre organisation Exchange locale.

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a>Vérifiez que tout fonctionne correctement

Vérifiez que la configuration est correcte en vérifiant que certaines fonctionnalités fonctionnent correctement. 

1. Confirmer le fonctionnement de la délégation de calendrier Outlook entre deux utilisateurs de teams avec des boîtes aux lettres Exchange Server 2016 ou 2019.

2. L’historique des conversations pour les clients mobiles est visible dans le dossier historique des conversations Outlook.

Vous pouvez également examiner votre trafic. Le trafic d’une connexion OAuth est réellement distinctif (et ne ressemble pas à l’authentification de base), en particulier par rapport aux domaines, où vous allez commencer à voir le trafic de l’émetteur qui ressemble à ce qui suit: 00000004-0000-0ff1-CE00-000000000000 @ (parfois avec un/avant). le signe @), dans les jetons transmis. Aucun nom d’utilisateur ou mot de passe ne s’affiche, qui est le point de OAuth. Néanmoins, vous verrez l’émetteur’Office', dans le cas où «4» est Skype entreprise, ainsi que le domaine de votre abonnement.

Si vous voulez vous assurer que vous utilisez correctement OAuth, assurez-vous que vous savez à quoi il doit s’attendre et que vous savez à quoi ressemble le trafic. Voici [ce à quoi vous pouvez vous attendre, vous](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)trouverez ci-dessous un [exemple standard de trafic OAuth dans une application Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (il est réellement utile de lire, même si elle n’utilise pas de jeton d’actualisation), et il existe des extensions Fiddler qui vous permettront d’accéder à votre JWT OAuth (JSON). Jeton Web).

Voici un [exemple de configuration d’une valeur unique](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), mais vous pouvez utiliser n’importe quel outil de suivi réseau qui vous plaît pour engager ce processus.

## <a name="related-topics"></a>Voir aussi

[Configurer l’authentification OAuth entre les organisations Exchange et Exchange Online](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

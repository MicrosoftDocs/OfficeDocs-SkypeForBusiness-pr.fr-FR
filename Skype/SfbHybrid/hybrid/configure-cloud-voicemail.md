---
title: Configurer le service de messagerie vocale Cloud pour les utilisateurs locaux
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instructions pour l’implémentation de la messagerie vocale en nuage pour les utilisateurs hébergés sur Skype entreprise Server.
ms.openlocfilehash: 7423f16e7985a063ae5a974ea6c36684bfb75e7c
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37616068"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a>Configurer le service de messagerie vocale Cloud pour les utilisateurs locaux

## <a name="overview"></a>Vue d’ensemble 
Cet article explique comment configurer le service de messagerie vocale Microsoft Cloud pour vos utilisateurs locaux de Skype entreprise.  

Dans cet article, nous partons du principe que vous avez déjà déployé Skype entreprise Server dans une topologie prise en charge et que vous respectez les conditions préalables à la configuration de la connectivité hybride.

Pour plus d’informations sur les avantages, les considérations relatives à la planification et les conditions requises pour l’implémentation de la messagerie vocale Cloud, voir [plan Cloud de messagerie vocale](plan-cloud-voicemail.md).




La configuration de la messagerie vocale Cloud implique les tâches suivantes :

1.  Assurez-vous que vous remplissez les conditions préalables décrites dans [plan Cloud de messagerie vocale](plan-cloud-voicemail.md).

2.  Assurez-vous que vous avez configuré la connectivité hybride comme décrit dans [plan Hybrid Connectivity](plan-hybrid-connectivity.md) et [configure Hybrid Connectivity](configure-hybrid-connectivity.md). 

3.  [Configurez le service de messagerie vocale Cloud en tant que fournisseur d’hébergement sur le serveur Edge](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) , comme décrit dans cet article.

4.  [Configurez une stratégie de messagerie vocale hébergée](#configure-a-hosted-voicemail-policy) comme décrit dans cet article.

5.  [Affectez une stratégie de messagerie vocale hébergée](#assign-a-hosted-voicemail-policy) , comme décrit dans cet article.

6.  [Activez un utilisateur pour la messagerie vocale Cloud](#enable-a-user-for-cloud-voicemail) comme décrit dans cet article.


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a>Configuration de la messagerie vocale sur le Cloud en tant que fournisseur d’hébergement sur le serveur Edge 

Vous configurez la messagerie vocale Cloud en tant que fournisseur d’hébergement sur un serveur frontal à l’aide de la cmdlet New-CsHostingProvider avec les paramètres suivants :

- **Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez ; par exemple, la messagerie vocale Cloud. 

- **Enabled** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. Ce paramètre doit être défini sur true.

- **EnabledSharedAddressSpace** indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adressage SIP partagé. Ce paramètre doit être défini sur true.

- **HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger les comptes Skype entreprise Server. Ce paramètre doit avoir la valeur false.

- **ProxyFQDN** spécifie le nom de domaine complet (FQDN) du serveur proxy utilisé par le fournisseur d’hébergement ; par exemple, proxyserver.contoso.com. Demandez cette information au fournisseur d’hébergement. Cette valeur ne peut pas être modifiée. Si le fournisseur d’hébergement modifie son serveur proxy, vous devrez supprimer puis recréer l’entrée pour ce fournisseur.

- **IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre topologie Skype entreprise Server. Ce paramètre doit avoir la valeur false.

Par exemple, dans Skype entreprise Management Shell, l’applet de commande suivante configure la messagerie vocale du Cloud en tant que fournisseur d’hébergement :


```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>Configurer une stratégie de messagerie vocale hébergée

Pour vous assurer que la messagerie vocale de votre organisation est acheminée vers le service de messagerie vocale Cloud, vous devez configurer une stratégie de messagerie vocale hébergée pour votre organisation. Dans de nombreux cas, une seule stratégie de messagerie vocale hébergée est requise et vous pouvez modifier la stratégie globale pour répondre à tous vos besoins. Si votre organisation requiert plusieurs stratégies de messagerie vocale hébergée, vous pouvez ajouter des stratégies à l’aide de la cmdlet New-cshostedvoicemailpolicy.

Pour modifier la stratégie globale, exécutez la commande suivante dans Skype entreprise Server Management Shell après avoir mis à jour votre organisation et TenantID :

```
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -Tenant “11111111-1111-1111-1111-111111111111”
```

- **Destination** : spécifie le nom de domaine complet (FQDN) du service de messagerie vocale hébergée dans le Cloud. Cette valeur doit être définie sur **EXAP.um.Outlook.com**.

- **Organization** est le domaine par défaut affecté à votre client. Vous pouvez récupérer ces informations en faisant en sorte que l’administrateur client se connecte à office.com, cliquez sur l’application du centre d’administration, accédez à l' **installation** sur la gauche, puis cliquez sur **domaines**. Par exemple : mytenant.onmicrosoft.com.

    Le nom de l’organisation est également le nom de domaine par défaut dans Office 365.

- Le **client** est utilisé pour identifier votre client dans Office 365. Pour plus d’informations, consultez [la rubrique trouver votre ID de client Office 365](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).

Pour vous assurer qu’une stratégie de messagerie vocale hébergée a été correctement créée, exécutez la commande suivante :

```
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>Affecter une stratégie de messagerie vocale hébergée

Par défaut, la stratégie de messagerie vocale hébergée globale est affectée à tous les utilisateurs. Si vous utilisez une autre stratégie, avant d’activer les utilisateurs pour la messagerie vocale hébergée, vous devez d’abord accorder aux utilisateurs la stratégie de messagerie vocale hébergée souhaitée à l’aide de la cmdlet [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) .

Par exemple, la commande suivante attribue une stratégie de messagerie vocale hébergée non globale à un utilisateur :


```
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>Activer un utilisateur pour la messagerie vocale sur le Cloud

Pour permettre aux appels de messagerie vocale d’un utilisateur d’être acheminé vers la messagerie vocale Cloud, utilisez la cmdlet [Set-Csuser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) avec le paramètre HostedVoiceMail. 

Par exemple, la commande suivante active un compte d’utilisateur pour la messagerie vocale sur le Cloud : 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

L’applet de commande vérifie qu’une stratégie de messagerie vocale Cloud, au niveau global, site ou utilisateur, s’applique à cet utilisateur. Si aucune stratégie ne s’applique, la cmdlet échoue.  

L’exemple suivant désactive un compte d’utilisateur pour la messagerie vocale sur le Cloud :

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

L’applet de commande vérifie qu’aucune stratégie de messagerie vocale hébergée (au niveau global, site ou utilisateur) ne s’applique à cet utilisateur. Si une stratégie s’applique, la cmdlet échoue.

> [!NOTE]
>  Les utilisateurs doivent être activés pour la voix entreprise pour utiliser le service de messagerie vocale Microsoft Cloud.

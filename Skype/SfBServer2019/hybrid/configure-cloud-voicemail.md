---
title: Configurer le service de messagerie vocale dans le nuage
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 5/9/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instructions relatives à la mise en œuvre la messagerie vocale en nuage pour les utilisateurs hébergement sur Skype pour Business Server.
ms.openlocfilehash: 05c486ed338e8e77ab68f12a64c3a59646a157d0
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838745"
---
# <a name="configure-cloud-voicemail-service"></a>Configurer le service de messagerie vocale dans le nuage

## <a name="overview"></a>Vue d’ensemble 
Cet article explique comment configurer le service de messagerie vocale de Microsoft dans le nuage pour votre Skype pour les utilisateurs locaux professionnels.  

Cet article suppose que vous avez déjà Skype pour Business Server déployé dans une topologie prise en charge, et que vous remplissez les conditions requises pour configurer la connectivité hybride.

Pour plus d’informations sur les avantages des considérations relatives à la planification et configuration requise pour l’implémentation de la messagerie vocale dans le nuage, voir [service de planification de la messagerie vocale dans le nuage](plan-cloud-voicemail.md).




Configuration de la messagerie vocale dans le nuage implique les tâches suivantes :

1.  Vérifiez que vous remplissez les conditions préalables comme décrit dans le [service de planification de la messagerie vocale dans le nuage](plan-cloud-voicemail.md).

2.  Vérifiez que vous avez configuré une connectivité hybride comme décrit dans la [connectivité hybride de Plan](plan-hybrid-connectivity.md) et de [connectivité de configuration hybride](configure-hybrid-connectivity.md). 

3.  [Configurer la messagerie vocale dans le nuage en tant que le fournisseur d’hébergement sur le serveur Edge](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) comme décrit dans cet article.

4.  [Configurer une stratégie de messagerie vocale hébergée](#configure-a-hosted-voicemail-policy) comme décrit dans cet article.

5.  [Attribuer une stratégie de messagerie vocale hébergée](#assign-a-hosted-voicemail-policy) comme décrit dans cet article.

6.  [Permettre à un utilisateur pour la messagerie vocale dans le nuage](#enable-a-user-for-cloud-voicemail) comme décrit dans cet article.


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a>Configurer la messagerie vocale dans le nuage en tant que le fournisseur d’hébergement sur le serveur Edge 

Vous configurez la messagerie vocale dans le nuage en tant que le fournisseur d’hébergement sur le serveur Edge à l’aide de l’applet de commande New-CsHostingProvider avec les paramètres suivants :

- **Identité** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez ; par exemple, la messagerie vocale dans le nuage. 

- **Enabled ** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. Ce paramètre doit être défini sur True.

- **EnabledSharedAddressSpace** indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adresse SIP partagé. Ce paramètre doit être défini sur True.

- **HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger Skype pour les comptes Business Server. Ce paramètre doit être défini sur False.

- **ProxyFQDN** Spécifie le nom de domaine complet (FQDN) du serveur proxy utilisé par le fournisseur d’hébergement ; par exemple, proxyserver.contoso.com. Pour que ces informations, contactez votre fournisseur d’hébergement. Cette valeur ne peut pas être modifiée. Si le fournisseur d’hébergement change de serveur proxy, vous devez supprimer et recréer l’entrée pour ce fournisseur.

- **IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre Skype pour la topologie du serveur d’entreprise. Ce paramètre doit être défini sur False.

Par exemple, dans Skype pour Business Management shell, l’applet de commande suivante permet de configurer de la messagerie vocale dans le nuage en tant que le fournisseur d’hébergement :


```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>Configurer une stratégie de messagerie vocale hébergée

Pour vous assurer que la messagerie vocale pour votre organisation est dirigé vers le service de messagerie vocale dans le nuage, vous devez configurer une stratégie de messagerie vocale hébergée pour votre organisation. Dans de nombreux cas, messagerie vocale hébergée qu’une seule stratégie est nécessaire, et vous pouvez modifier la stratégie globale pour répondre à tous vos besoins. Si votre organisation a besoin de plusieurs stratégies de messagerie vocale hébergée, vous pouvez ajouter des stratégies à l’aide de l’applet de commande nouvelle-cshostedvoicemailpolicy.

Pour modifier la stratégie globale, exécutez la commande suivante dans le Skype pour Business Server shell de gestion après la mise à jour de votre organisation et l’ID client sur :

```
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -TenantID “11111111-1111-1111-1111-111111111111”
```

- **Destination** Spécifie le nom de domaine complet (FQDN) du service de messagerie vocale dans le nuage hébergé. Cette valeur doit être définie sur **exap.um.outlook.com**.

- **Organisation** est le domaine par défaut affecté à votre client. Vous pouvez récupérer ces informations grâce à l’administrateur du client de se connecter à office.com, cliquez sur l’application du centre d’administration, accédez à **installation** sur la gauche et cliquez sur **domaines**. Par exemple : mytenant.onmicrosoft.com.

    Le nom de l’organisation est également le nom de domaine par défaut dans Office 365.

- **ID client sur** sert à identifier votre client dans Office 365. Pour plus d’informations, voir [Rechercher votre ID de client Office 365](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).

Pour vous assurer qu’une stratégie de messagerie vocale hébergée a été créée avec succès, exécutez la commande suivante :

```
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>Attribuer une stratégie de messagerie vocale hébergée

Par défaut, Global hébergé stratégie de messagerie vocale est affectée à tous les utilisateurs. Si vous utilisez une stratégie différente, avant d’activer les utilisateurs pour la messagerie vocale hébergée, vous devez d’abord accorder aux utilisateurs la stratégie de messagerie vocale hébergée souhaité à l’aide de l’applet de commande [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) .

Par exemple, la commande suivante attribue une stratégie de messagerie vocale hébergée non globale à un utilisateur :


```
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>Permettre à un utilisateur pour la messagerie vocale dans le nuage

Pour activer les appels de messagerie vocale d’un utilisateur à être acheminés vers la messagerie vocale dans le nuage, vous utilisez l’applet de commande [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) avec le paramètre HostedVoiceMail. 

Par exemple, la commande suivante permet à un compte d’utilisateur pour la messagerie vocale dans le nuage : 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

L’applet de commande vérifie si une stratégie de messagerie vocale dans le nuage--au niveau global, site ou au niveau utilisateur--s’applique à cet utilisateur. Si aucune stratégie s’applique, l’applet de commande échoue.  

L’exemple suivant désactive un compte d’utilisateur pour la messagerie vocale dans le nuage :

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

L’applet de commande vérifie si aucune stratégie de messagerie vocale hébergée--au niveau global, site ou au niveau utilisateur--s’applique à cet utilisateur. Si une stratégie s’applique, l’applet de commande échoue.

> [!NOTE]
>  Les utilisateurs doivent être activé pour utiliser le Service de messagerie vocale du Cloud Microsoft de voix entreprise.
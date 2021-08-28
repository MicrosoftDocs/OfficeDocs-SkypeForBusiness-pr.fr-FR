---
title: Configurer le service Messagerie vocale infonuagique pour les utilisateurs locaux
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection: ''
description: Instructions d’implémentation de la messagerie vocale en nuage pour les utilisateurs Skype Entreprise Server.
ms.openlocfilehash: 4f38c181c84edb695fce54d6da805482563cfe01
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625746"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a>Configurer le service Messagerie vocale infonuagique pour les utilisateurs locaux

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


## <a name="overview"></a>Vue d’ensemble 
Cet article explique comment configurer Messagerie vocale infonuagique Microsoft service pour vos utilisateurs Skype Entreprise locaux.  

Cet article suppose que vous avez déjà déployé Skype Entreprise Server dans une topologie prise en charge et que vous avez satisfait aux conditions préalables à la configuration de la connectivité hybride.

Pour plus d’informations sur les avantages, les considérations relatives à la planification et les conditions requises pour l’Messagerie vocale infonuagique, voir [Plan Messagerie vocale infonuagique service](plan-cloud-voicemail.md).




La configuration Messagerie vocale infonuagique implique les tâches suivantes :

1.  Assurez-vous que vous avez satisfait aux conditions préalables décrites dans [plan Messagerie vocale infonuagique service](plan-cloud-voicemail.md).

2.  Assurez-vous que vous avez configuré la connectivité hybride comme décrit dans [Planifier](plan-hybrid-connectivity.md) la connectivité hybride et [configurer la connectivité hybride.](configure-hybrid-connectivity.md) 

3.  [Configurez Messagerie vocale infonuagique en tant que fournisseur d’hébergement](#configure-cloud-voicemail-as-the-hosting-provider) sur le serveur frontal, comme décrit dans cet article.

4.  [Configurez une stratégie de messagerie vocale hébergée](#configure-a-hosted-voicemail-policy) comme décrit dans cet article.

5.  [Affectez une stratégie de messagerie vocale hébergée](#assign-a-hosted-voicemail-policy) comme décrit dans cet article.

6.  [Activez un utilisateur pour Messagerie vocale infonuagique](#enable-a-user-for-cloud-voicemail) comme décrit dans cet article.


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a>Configurer Messagerie vocale infonuagique en tant que fournisseur d’hébergement 

Vous configurez Messagerie vocale infonuagique en tant que fournisseur d’hébergement sur un serveur frontal à l’aide de la cmdlet New-CsHostingProvider avec les paramètres suivants :

- **Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez ; par exemple, Messagerie vocale infonuagique. 

- **Enabled** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. Ce paramètre doit avoir la valeur True.

- **EnabledSharedAddressSpace** indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adressage SIP partagé. Ce paramètre doit avoir la valeur True.

- **HostsOCSUsers indique** si le fournisseur d’hébergement est utilisé pour héberger Skype Entreprise Server comptes. Ce paramètre doit avoir la valeur False.

- **ProxyFQDN** spécifie le nom de domaine complet (FQDN) du serveur proxy utilisé par le fournisseur d’hébergement ; par exemple, proxyserver.contoso.com. Demandez cette information au fournisseur d’hébergement. Cette valeur ne peut pas être modifiée. Si le fournisseur d’hébergement change de serveur proxy, vous devrez supprimer, puis re-créer l’entrée pour ce fournisseur.

- **IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans Skype Entreprise Server topologie. Ce paramètre doit avoir la valeur False.

Par exemple, dans l’Skype Entreprise Management Shell, l’cmdlet suivante configure Messagerie vocale infonuagique en tant que fournisseur d’hébergement :


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>Configurer une stratégie de messagerie vocale hébergée

Pour vous assurer que la messagerie vocale de votre organisation est acheminée vers le service Messagerie vocale infonuagique, vous devez configurer une stratégie de messagerie vocale hébergée pour votre organisation. Dans de nombreux cas, une seule stratégie de messagerie vocale hébergée est requise et vous pouvez modifier la stratégie globale pour répondre à vos besoins. Si votre organisation nécessite plusieurs stratégies de messagerie vocale hébergée, vous pouvez ajouter des stratégies à l’aide de la cmdlet new-cshostedvoicemailpolicy.

Pour modifier la stratégie globale, exécutez la commande suivante dans l’environnement de Skype Entreprise Server management Shell après avoir mis à jour votre Organisation et TenantID :

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- **La** destination spécifie le nom de domaine complet (FQDN) du service Messagerie vocale infonuagique hébergé. Cette valeur doit être définie sur **exap.um.outlook.com**.

- **L’organisation** est le domaine par défaut affecté à votre client. Vous pouvez récupérer ces informations en ayant l’administrateur client se connecter à office.com, cliquer sur l’application Centre d’administration, accéder au programme d’installation sur la gauche, puis cliquer sur **Domaines**.  Par exemple : mytenant.onmicrosoft.com.

    Le nom de l’organisation est également le nom de domaine par défaut Microsoft 365 ou Office 365.

Pour vous assurer qu’une stratégie de messagerie vocale hébergée a été créée correctement, exécutez la commande suivante :

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>Affecter une stratégie de messagerie vocale hébergée

Par défaut, la stratégie de messagerie vocale hébergée globale est affectée à tous les utilisateurs. Si vous utilisez une stratégie différente, avant d’activer les utilisateurs pour la messagerie vocale hébergée, vous devez d’abord accorder aux utilisateurs la stratégie de messagerie vocale hébergée souhaitée à l’aide de l’cmdlet [Grant-CSHostedVoicemailPolicy.](/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps)

Par exemple, la commande suivante affecte une stratégie de messagerie vocale hébergée non globale à un utilisateur :


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -PolicyName "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>Activer un utilisateur pour Messagerie vocale infonuagique

Pour que les appels de messagerie vocale d’un utilisateur soient acheminés vers Messagerie vocale infonuagique, utilisez l’cmdlet [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) avec le paramètre HostedVoiceMail. 

Par exemple, la commande suivante active un compte d’utilisateur pour Messagerie vocale infonuagique : 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

L’cmdlet vérifie qu’une stratégie Messagerie vocale infonuagique(au niveau global, du site ou de l’utilisateur) s’applique à cet utilisateur. Si aucune stratégie ne s’applique, la cmdlet échoue.  

L’exemple suivant désactive un compte d’utilisateur pour Messagerie vocale infonuagique :

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

La cmdlet vérifie qu’aucune stratégie de messagerie vocale hébergée (au niveau global, du site ou de l’utilisateur) ne s’applique à cet utilisateur. Si une stratégie s’applique, la cmdlet échoue.

> [!NOTE]
>  Les utilisateurs doivent être activés pour utiliser le service Messagerie vocale infonuagique Microsoft entreprise.
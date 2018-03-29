---
title: Configurer l’intégration entre Skype sur site pour Business Server 2015 et Outlook Web App
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/7/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Résumé : Intégrer Skype pour Business Server et Outlook Web App.'
ms.openlocfilehash: 4ac4d6a71f8006e813d09631f8ccf28742940ff2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-2015-and-outlook-web-app"></a>Configurer l’intégration entre Skype sur site pour Business Server 2015 et Outlook Web App
 
**Résumé :** Intégrer Skype pour Business Server et Outlook Web App.
  
Les clients utilisant les Skype sur site pour les déploiements d’entreprise serveur 2015 peuvent configurer l’interopérabilité avec Microsoft Outlook Web App dans Microsoft Exchange Online dans un mode de déploiement hybride. Les fonctionnalités d’interopérabilité comprennent l’ouverture de session unique, l’intégration de la messagerie instantanée et de la présence dans l’interface d’Outlook Web App. Pour activer cette intégration, vous devez configurer le serveur de transport Edge dans votre Skype sur site pour le déploiement de serveur d’entreprise en effectuant les tâches suivantes : 
  
- configurer un espace d’adressage SIP partagé ;
    
- Configurer un fournisseur d’hébergement sur le serveur de transport Edge
    
- Vérification de la réplication de la banque d’administration centrale mis à jour
    
## <a name="configure-a-shared-sip-address-space"></a>Configurer un espace d’adressage SIP partagé

Pour intégrer des locaux Skype pour 2015 de serveur d’entreprise avec Exchange Online, vous devez configurer un espace d’adressage partagé SIP. Le même espace d’adressage de domaine SIP est pris en charge par Skype pour Business Server et le service Exchange en ligne.
  
À l’aide de la Skype pour Business Server Management Shell, de configurer le serveur de transport Edge pour la fédération en exécutant la cmdlet **Set-CSAccessEdgeConfiguration** , en utilisant les paramètres affichés dans l’exemple suivant :
  
```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- **AllowFederatedUsers** paramètre spécifie si les utilisateurs internes sont autorisés à communiquer avec les utilisateurs de domaines fédérés. Cette propriété détermine également si les utilisateurs internes peuvent communiquer avec des utilisateurs dans un scénario d’espace d’adresse SIP partagé avec Skype pour Business Server et Exchange Online.
    
Pour plus d’informations sur l’utilisation de la Skype pour Business Server Management Shell, voir [Skype pour Business Server 2015 Management Shell](../../manage/management-shell.md).
  
## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Configurer un fournisseur d’hébergement sur le serveur Edge.

À l’aide de la Skype pour Business Server Management Shell, configurer un fournisseur d’hébergement sur le serveur de transport Edge en exécutant la cmdlet **New-CsHostingProvider** , en utilisant les paramètres dans l’exemple suivant :
  
```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Si vous utilisez Office 365 activé par 21Vianet en Chine, remplacez dans cet exemple la valeur du paramètre **ProxyFqdn** (« exap.um.outlook.com ») par le FQDN du service activé par 21Vianet: « exap.um.partner.outlook.cn ».
  
- **Identité** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez (par exemple, Exchange « en ligne »). Les valeurs qui contiennent des espaces doivent être placées entre guillemets doubles.
    
- **Enabled ** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. Ce paramètre doit avoir la valeur True.
    
- **EnabledSharedAddressSpace** indique si le fournisseur d’hébergement doit être utilisé dans un scénario d’espace adresse SIP partagé. Ce paramètre doit avoir la valeur True.
    
- **HostsOCSUsers** indique si le fournisseur d’hébergement permet d’héberger Office Communications Server ou Skype pour Business Server. Ce paramètre doit avoir la valeur False.
    
- **ProxyFQDN** Spécifie le nom de domaine pleinement qualifié (FQDN) du serveur proxy utilisé par le fournisseur d’hébergement. Pour Exchange Online, le nom de domaine complet est exap.um.outlook.com.
    
- **IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement figure dans votre Skype pour la topologie du serveur de l’entreprise. Ce paramètre doit avoir la valeur False.
    
- **VerificationLevel** Indique le niveau de vérification autorisé pour les messages qui sont envoyés vers et à partir du fournisseur hébergé. Spécifiez **UseSourceVerification**, qui s’appuie sur le niveau de vérification inclus dans les messages envoyés par le fournisseur d’hébergement. Si ce niveau n’est pas spécifié, le message sera rejeté comme étant non vérifiable.
    
## <a name="verify-replication-of-the-updated-central-management-store"></a>Vérifier la réplication du magasin central de gestion mis à jour

Les modifications apportées à l’aide des applets de commande dans les sections précédentes sont automatiquement appliquées sur le serveur de transport Edge et généralement prennent moins d’une minute à répliquer. Vous pouvez valider l’état de la réplication et confirmez que les modifications ont été appliquées à votre serveur de transport Edge à l’aide des applets de commande suivantes.
  
Pour vérifier les mises à jour de réplication, sur un serveur interne dans votre Skype pour le déploiement du serveur de l’entreprise, exécutez l’applet de commande suivante :
  
```
Get-CsManagementStoreReplicationStatus
```

Pour confirmer que les modifications ont été appliquées sur le serveur Edge, exécutez l’applet de commande suivante :
  
```
Get-CsHostingProvider -LocalStore
```

## <a name="see-also"></a>Voir aussi

#### 

[Prévoyant Skype Business Server 2015 utilisateurs voice mail sur hébergé de messagerie unifiée Exchange](http://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)
  
[Hébergé intégration de messagerie unifiée Exchange dans Skype pour Business Server 2015](http://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)


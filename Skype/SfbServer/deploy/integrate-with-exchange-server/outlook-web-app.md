---
title: Configurer l’intégration entre locale Skype pour Business Server et Outlook Web App
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
ms.openlocfilehash: 5ad1f6bc898a29c2a5e0f326d3a5edc4d782bab2
ms.sourcegitcommit: 25066ab000f7615aff31f77d9d39c266c65e2aa5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2018
ms.locfileid: "22914095"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Configurer l’intégration entre locale Skype pour Business Server et Outlook Web App
 
**Résumé :** Intégrer Skype pour Business Server et Outlook Web App.
  
Les clients qui utilisent des locaux Skype pour les déploiements de serveur d’entreprise peuvent configurer l’interopérabilité avec Microsoft Outlook Web App dans Microsoft Exchange Online dans un mode de déploiement hybride. Les fonctionnalités d’interopérabilité comprennent l’ouverture de session unique, l’intégration de la messagerie instantanée et de la présence dans l’interface d’Outlook Web App. Pour activer cette intégration, vous devez configurer le serveur de périphérie dans votre Skype sur site pour le déploiement de serveur d’entreprise en effectuant les tâches suivantes : 
  
- configurer un espace d’adressage SIP partagé ;
    
- Configurer un fournisseur d’hébergement sur le serveur Edge
    
- Vérifier la réplication du magasin Central de gestion mis à jour
    
## <a name="configure-a-shared-sip-address-space"></a>Configurer un espace d’adressage SIP partagé

Pour intégrer locale Skype pour Business Server avec Exchange Online, vous devez configurer un espace d’adressage SIP partagé. Le même espace d’adresse de domaine SIP est pris en charge par Skype pour Business Server et le service Exchange Online.
  
À l’aide de la Skype pour Business Server Management Shell, configurez le serveur de périphérie pour la fédération en exécutant l’applet de commande **Set-CSAccessEdgeConfiguration** avec les paramètres affichés dans l’exemple suivant :
  
```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- **AllowFederatedUsers** Spécifie si les utilisateurs internes sont autorisés à communiquer avec les utilisateurs des domaines fédérés. Cette propriété détermine également si les utilisateurs internes peuvent communiquer avec des utilisateurs dans un scénario d’espace d’adresse SIP partagé avec Skype pour Business Server et Exchange Online.
    
Pour plus d’informations sur l’utilisation de la Skype pour Business Server Management Shell, voir [Skype pour Business Server Management Shell](../../manage/management-shell.md).
  
## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Configurer un fournisseur d’hébergement sur le serveur Edge.

À l’aide de la Skype pour Business Server Management Shell, configurez un fournisseur d’hébergement sur le serveur Edge en exécutant l’applet de commande **New-CsHostingProvider** avec les paramètres de l’exemple suivant :
  
```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Si vous utilisez Office 365 activé par 21Vianet en Chine, remplacez dans cet exemple la valeur du paramètre ProxyFqdn (« exap.um.outlook.com ») par le FQDN du service activé par 21Vianet: « exap.um.partner.outlook.cn ». Si vous utilisez Office 365 GCC haute, remplacez la valeur du paramètre ProxyFqdn dans cet exemple (« exap.um.outlook.com ») avec le nom de domaine complet GCC High : « exap.um.office365.us ».
  
- **Identité** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez (par exemple, « Exchange Online »). Les valeurs qui contiennent des espaces doivent être placées entre guillemets doubles.
    
- **Enabled ** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. Ce paramètre doit avoir la valeur True.
    
- **EnabledSharedAddressSpace** indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adresse SIP partagé. Ce paramètre doit avoir la valeur True.
    
- **HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger Office Communications Server ou Skype pour Business Server. Ce paramètre doit avoir la valeur False.
    
- **ProxyFQDN** Spécifie le nom de domaine complet (FQDN) du serveur proxy utilisé par le fournisseur d’hébergement. Pour Exchange Online, le nom de domaine complet est exap.um.outlook.com.
    
- **IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre Skype pour la topologie du serveur d’entreprise. Ce paramètre doit avoir la valeur False.
    
- **VerificationLevel** Indique le niveau de vérification autorisé pour les messages qui sont envoyés vers ou à partir du fournisseur hébergé. Spécifiez **UseSourceVerification**, qui repose sur le niveau de vérification inclus dans les messages envoyés à partir du fournisseur d’hébergement. Si ce niveau n’est pas spécifié, le message sera rejeté comme étant non vérifiables.
    
## <a name="verify-replication-of-the-updated-central-management-store"></a>Vérifier la réplication du magasin central de gestion mis à jour

Les modifications apportées à l’aide des applets de commande dans les sections précédentes sont automatiquement appliquées au serveur de périphérie et prennent généralement moins d’une minute à répliquer. Vous pouvez valider l’état de la réplication et confirmer que les modifications ont été appliquées à votre serveur Edge à l’aide des applets de commande suivantes.
  
Pour vérifier les mises à jour de réplication, sur un serveur interne dans votre Skype pour le déploiement de Business Server, exécutez l’applet de commande suivante :
  
```
Get-CsManagementStoreReplicationStatus
```

Pour confirmer que les modifications ont été appliquées, sur le serveur Edge, exécutez l’applet de commande suivante :
  
```
Get-CsHostingProvider -LocalStore
```

## <a name="see-also"></a>Voir aussi

[Fourniture Skype pour Business Server utilisateurs la messagerie vocale sur hébergé la messagerie unifiée Exchange](http://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)
  
[Hébergée intégration de messagerie unifiée Exchange dans Skype pour Business Server](http://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
---
title: Contournement du déploiement multimédia dans la version Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Pour plus d’informations sur la procédure de déploiement d’une dérivation multimédia avec la version 2,0 et les versions ultérieures, voir la rubrique.
ms.openlocfilehash: 771d3a7294fde38b032e4cd9a281f70156280d3a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802344"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Contournement du déploiement multimédia dans la version Cloud Connector
 
Pour plus d’informations sur la procédure de déploiement d’une dérivation multimédia avec la version 2,0 et les versions ultérieures, voir la rubrique. 
  
Bypass Media permet à un client d’envoyer des contenus multimédias directement sur le tronçon de réseau téléphonique commuté (PSTN), une passerelle ou un contrôleur de bordure de session (SBC), et d’éliminer le composant Cloud Connector édition sur le chemin multimédia. Voir aussi [plan de contournement multimédia dans la version Cloud Connector](plan-for-media-bypass-in-cloud-connector-edition.md).
  
## <a name="enable-media-bypass"></a>Activer la déviation du trafic multimédia

Pour activer la déviation du trafic multimédia, vous devez configurer le nom DNS du service web de déviation du trafic multimédia et activer la déviation du trafic multimédia dans la configuration de client. Le service web de déviation du trafic multimédia se déploie automatiquement sur chaque serveur de médiation. Un administrateur de client doit choisir un nom pour un service de voix hybride (site) et ce nom doit provenir d'un domaine SIP inscrit pour la voix hybride. Le nom du service doit être identique sur tous les appareils Cloud Connector et sur tous les sites RTC, quel que soit l’emplacement du client. Le service web doit être disponible uniquement en interne sur le réseau.
  
Un administrateur client doit configurer un enregistrement DNS A dans la production interne Active Directory. Si vous disposez d’un environnement multisite complexe, reportez-vous à l’exemple [ci-dessous : enregistrements DNS du site Web bypass dans les environnements multisites complexes](deploy-media-bypass-in-cloud-connector.md#Example). L'enregistrement DNS doit uniquement résoudre les clients du réseau interne, il ne doit pas résoudre les clients du réseau externe.
  
Après avoir configuré le DNS, connectez-vous à Skype Entreprise Online en utilisant PowerShell à distance avec les informations d'identification d'administrateur Skype Entreprise. Pour plus d’informations, voir [configurer votre ordinateur pour Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .
  
Dans la session PowerShell, entrez les commandes suivantes pour activer la déviation du trafic multimédia :
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Activer la déviation du trafic multimédia en deux étapes. L'applet de commande New-CsNetworkMedia n'enregistre pas immédiatement la nouvelle configuration, elle crée uniquement les paramètres en mémoire. L'objet créé par cette applet de commande doit être enregistré vers une variable, puis affecté à la propriété MediaBypassSettings de la configuration réseau. Pour plus d’informations, reportez-vous à la section [exemple : Media Bypass site Web Records dans les environnements multisites complexes](deploy-media-bypass-in-cloud-connector.md#Example).
  
La réplication entre les composants locaux et en ligne peut prendre jusqu'à 24 heures, c'est pourquoi Microsoft vous recommande d'exécuter les commandes nécessaires avant d'activer les utilisateurs.
  
## <a name="confirm-media-bypass-settings"></a>Confirmer les paramètres de déviation du trafic multimédia

Vous pouvez vérifier les paramètres de déviation du trafic multimédia comme suit.  
  
Pour vérifier la réplication en ligne vers votre pool de clients, exécutez la commande suivante dans PowerShell distant :
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

Pour vérifier la réplication locale, connectez-vous aux serveurs de médiation Cloud Connector, exécutez la commande suivante dans PowerShell et confirmez que enabled = true et AlwaysBypass = true
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

Pour vérifier les paramètres du client, déconnectez-vous du client Skype entreprise, reconnectez-vous, puis vérifiez que le client a reçu l’URL du service comme suit :
  
1. Ouvrez %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. 
    
2. Recherchez hybridconfigserviceinternalurl et confirmez que l'URL correspond à celle que vous avez définie.
    
## <a name="change-media-bypass-parameters"></a>Modifier les paramètres de déviation du trafic multimédia

Les administrateurs clients peuvent modifier le nom DNS du service web en exécutant l'applet de commande suivante :
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> Les clients doivent se déconnecter et se reconnecter pour voir le nouveau nom de service et observer les modifications.  
  
## <a name="temporarily-disable-media-bypass"></a>Désactiver la déviation du trafic multimédia temporairement

Ce scénario peut être utile pour la résolution des problèmes et la maintenance. Pour désactiver le service, exécutez les applets de commande suivantes :
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Après avoir effectué la modification, la réplication de toutes les modifications sur tous les Cloud Connectors peut prendre du temps. Pour vérifier l’état de la réplication, exécutez l’applet de commande suivante dans PowerShell sur les serveurs de médiation Cloud Connector : 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

Lorsque les modifications sont répliquées, le service web sur le serveur de médiation commencera à rejeter les demandes des clients pour le service de déviation du trafic multimédia.
  
## <a name="disable-media-bypass-permanently"></a>Désactiver la déviation du trafic multimédia de façon permanente

Pour désactiver la déviation du trafic multimédia de façon permanente, un administrateur client doit exécuter les commandes suivantes : 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

Un administrateur devra également supprimer les adresses web pour la déviation du trafic multimédia des serveurs DNS internes. Après avoir effectué la modification, il est possible que les modifications soient répliquées sur tous les appareils Cloud Connector. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Exemple : enregistrements DNS de sites seb de déviation du trafic multimédia dans des environnements multisites complexes
<a name="Example"> </a>

Les clients recevront l'adresse web du service web de déviation du trafic multimédia depuis un serveur DNS interne. Le nom du service Web sera le même sur tous les appareils Cloud Connector et sur les sites RTC du Cloud Connector. Dans un environnement multisite complexe, nous vous recommandons d'utiliser la stratégie DNS de gestion du trafic basée sur la géolocalisation de Windows Server 2016 afin que les clients puissent être redirigés vers le service web local de leur réseau. 
  
Pour plus d’informations sur les stratégies DNS de Windows 2016, voir [utilisation de la stratégie DNS pour la gestion du trafic basée sur la géolocalisation avec les serveurs principaux](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).
  
Voici un exemple de configuration pour une entreprise avec plusieurs sites utilisant une stratégie DNS de gestion du trafic basée sur la géolocalisation de Windows Server 2016.
  
Le nom du service de contournement est « hybridvoice.adatum.biz ».
  
Le site d’Amsterdam comporte quatre appareils Cloud Connector déployés avec les adresses IP du serveur de médiation suivantes :
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
Le site de Seattle comporte trois appareils Cloud Connector déployés avec les adresses IP du serveur de médiation suivantes :
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
En utilisant la gestion du trafic basée sur la géolocalisation, les serveurs DNS seraient configurés comme suit :
  
1. créez des sous-réseaux client DNS pour les réseaux d'Amsterdam et de Seattle.
    
2. Créez des étendues de zone DNS pour adatum.biz pour Amsterdam et Seattle.
    
3. Créez des enregistrements DNS dans chaque étendue de zone DNS.
    
    Amsterdam
    
   - Type A ;
    
   - Nom : hybridvoice dans l'étendue de zone DNS adatum.biz
    
   - Cible : 192.168.1.45
    
     Créez des enregistrements supplémentaires pour les serveurs de médiation supplémentaires
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     Seattle
    
   - Type A
    
   - Nom : hybridvoice dans l'étendue de zone DNS adatum.biz
    
   - Cible : 10.10.1.8
    
     Créez des enregistrements supplémentaires pour les serveurs de médiation supplémentaires
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. Créez une stratégie DNS qui relie les sous-réseaux du client à l'étendue de zone appropriée pour assurer la résolution DNS souhaitée.
    
À ce stade, les clients effectuant des requêtes DNS depuis le sous-réseau d'Amsterdam pour hybridvoice.adatum.biz renvoient les adresses 192.168.1.45, 192.168.1.46, 192.168.1.47 et 192.168.1.48, tandis que les clients effectuant des requêtes DNS depuis Seattle renvoient les adresses 10.10.1.8, 10.10.1.9 et 10.10.1.10.

> [!NOTE]
> Si l’application CCE ne donne pas les paramètres mis à jour, vérifiez si l’application peut contacter le client par le biais de PowerShell distante. Vous pouvez utiliser Remote PowerShell pour vérifier l’état de l’appareil avec Get-CsHybridPSTNAppliance ou utiliser PowerShell sur l’hôte CCE pour vérifier l’état avec Get-CcApplianceStatus.

  
## <a name="see-also"></a>Voir aussi
<a name="Example"> </a>

[Planifier le contournement de média dans Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)

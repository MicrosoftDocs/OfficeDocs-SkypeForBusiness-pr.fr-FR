---
title: Déployer le contournement de média dans le nuage connecteur Edition
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Lisez cette rubrique pour en savoir plus sur les étapes nécessaires pour déployer le contournement de média avec le nuage connecteur Edition version 2.0 et versions ultérieure.
ms.openlocfilehash: 38ff1ffa3aef7e6cd85237048c46c5746b61e7bb
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531702"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Déployer le contournement de média dans le nuage connecteur Edition
 
Lisez cette rubrique pour en savoir plus sur les étapes nécessaires pour déployer le contournement de média avec le nuage connecteur Edition version 2.0 et versions ultérieure. 
  
Le contournement de média permet au client d’envoyer des données multimédia directement au saut suivant Public réseau de téléphonique commuté (RTC) — une passerelle ou un contrôleur de Session en périphérie (SBC) — et d’éliminer le composant nuage connecteur Edition à partir du chemin d’accès des médias. Voir aussi [Plan pour le média de contournement dans le nuage connecteur Edition](plan-for-media-bypass-in-cloud-connector-edition.md).
  
## <a name="enable-media-bypass"></a>Activer la déviation du trafic multimédia

Pour activer la déviation du trafic multimédia, vous devez configurer le nom DNS du service web de déviation du trafic multimédia et activer la déviation du trafic multimédia dans la configuration de client. Le service web de déviation du trafic multimédia se déploie automatiquement sur chaque serveur de médiation. Un administrateur de client doit choisir un nom pour un service de voix hybride (site) et ce nom doit provenir d'un domaine SIP inscrit pour la voix hybride. Le nom du service doit être la même sur tous les appareils de nuage connecteur et tous les sites PSTN quel que soit l’emplacement du client. Le service web doit être disponible uniquement en interne sur le réseau.
  
Un administrateur client doit configurer un enregistrement DNS A dans la production interne Active Directory. Si vous avez un environnement complexe de plusieurs site, consultez l’exemple dans [exemple : site web les enregistrements DNS dans les environnements multisites du contournement de média](deploy-media-bypass-in-cloud-connector.md#Example). L'enregistrement DNS doit uniquement résoudre les clients du réseau interne, il ne doit pas résoudre les clients du réseau externe.
  
Après avoir configuré le DNS, connectez-vous à Skype Entreprise Online en utilisant PowerShell à distance avec les informations d'identification d'administrateur Skype Entreprise. Pour plus d'informations, reportez-vous à la rubrique [Se connecter à Skype Entreprise Online en utilisant Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
Dans la session PowerShell, entrez les commandes suivantes pour activer la déviation du trafic multimédia :
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Activer la déviation du trafic multimédia en deux étapes. L'applet de commande New-CsNetworkMedia n'enregistre pas immédiatement la nouvelle configuration, elle crée uniquement les paramètres en mémoire. L'objet créé par cette applet de commande doit être enregistré vers une variable, puis affecté à la propriété MediaBypassSettings de la configuration réseau. Pour plus d’informations, voir [exemple : site web les enregistrements DNS dans les environnements multisites du contournement de média](deploy-media-bypass-in-cloud-connector.md#Example).
  
La réplication entre les composants locaux et en ligne peut prendre jusqu'à 24 heures, c'est pourquoi Microsoft vous recommande d'exécuter les commandes nécessaires avant d'activer les utilisateurs.
  
## <a name="confirm-media-bypass-settings"></a>Confirmer les paramètres de déviation du trafic multimédia

Vous pouvez vérifier les paramètres de déviation du trafic multimédia comme suit.  
  
Pour vérifier la réplication en ligne pour votre pool de client, exécutez la commande suivante dans PowerShell distant :
  
```
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

Pour vérifier la réplication locale, se connecter aux serveurs de médiation de connecteur dans le nuage, exécutez la commande suivante dans PowerShell et confirmez que Enabled = True et AlwaysBypass = True
  
```
Get-CsNetworkConfiguration -LocalStore
```

Pour vérifier les paramètres du client, vous déconnecter le Skype pour client d’entreprise, vous reconnecter et vérifiez que le client a reçu l’URL de service comme suit :
  
1. Ouvrez %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. 
    
2. Recherchez hybridconfigserviceinternalurl et confirmez que l'URL correspond à celle que vous avez définie.
    
## <a name="change-media-bypass-parameters"></a>Modifier les paramètres de déviation du trafic multimédia

Les administrateurs clients peuvent modifier le nom DNS du service web en exécutant l'applet de commande suivante :
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> Les clients doivent se déconnecter et se reconnecter pour voir le nouveau nom de service et observer les modifications.  
  
## <a name="temporarily-disable-media-bypass"></a>Désactiver la déviation du trafic multimédia temporairement

Ce scénario peut être utile pour la résolution des problèmes et la maintenance. Pour désactiver le service, exécutez les applets de commande suivantes :
  
```
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Après avoir effectué la modification, la réplication de toutes les modifications sur tous les Cloud Connectors peut prendre du temps. Pour vérifier l’état de réplication, exécutez la cmdlet suivante dans PowerShell sur les serveurs de médiation de connecteur dans le nuage : 
  
```
Get- CsNetworkConfiguration -LocalStore
```

Lorsque les modifications sont répliquées, le service web sur le serveur de médiation commencera à rejeter les demandes des clients pour le service de déviation du trafic multimédia.
  
## <a name="disable-media-bypass-permanently"></a>Désactiver la déviation du trafic multimédia de façon permanente

Pour désactiver la déviation du trafic multimédia de façon permanente, un administrateur client doit exécuter les commandes suivantes : 
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

Un administrateur devra également supprimer les adresses web pour la déviation du trafic multimédia des serveurs DNS internes. Après avoir apporté les modifications, elle peut prendre du temps pour les modifications soient répliquées dans tous les appareils de nuage connecteur. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Exemple : enregistrements DNS de sites seb de déviation du trafic multimédia dans des environnements multisites complexes
<a name="Example"> </a>

Les clients recevront l'adresse web du service web de déviation du trafic multimédia depuis un serveur DNS interne. Le nom du service web sera la même pour tous les appareils nuage connecteur et sites nuage connecteur PSTN. Dans un environnement multisite complexe, nous vous recommandons d'utiliser la stratégie DNS de gestion du trafic basée sur la géolocalisation de Windows Server 2016 afin que les clients puissent être redirigés vers le service web local de leur réseau. 
  
Pour plus d’informations sur les stratégies de DNS Windows 2016, voir [Utiliser la stratégie DNS pour la gestion d’un trafic en fonction de géolocalisation avec les serveurs principaux](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).
  
Voici un exemple de configuration pour une entreprise avec plusieurs sites utilisant une stratégie DNS de gestion du trafic basée sur la géolocalisation de Windows Server 2016.
  
Le nom du service de contournement de média est « hybridvoice.adatum.biz ».
  
Le site à Amsterdam comporte quatre appliances nuage connecteur déployés avec les adresses IP de serveur de médiation suivantes :
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
Le site de Seattle a trois appliances nuage connecteur déployés avec les adresses IP de serveur de médiation suivantes :
  
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
> Si l’appliance CCE ne semble pas obtenir les paramètres de mise à jour, vérifiez si elle n’est pas en mesure de contacter le client par le biais de PowerShell à distance. Vous pouvez utiliser PowerShell à distance pour vérifier l’état d’application avec Get-CsHybridPSTNAppliance ou comment utiliser PowerShell sur l’hôte CCE pour vérifier l’état avec Get-CcApplianceStatus.

  
## <a name="see-also"></a>Voir aussi
<a name="Example"> </a>

[Planification de la déviation du trafic multimédia dans la version Cloud Connector](plan-for-media-bypass-in-cloud-connector-edition.md)

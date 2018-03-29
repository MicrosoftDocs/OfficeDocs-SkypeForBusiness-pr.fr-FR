---
title: Déployer le contournement de média dans le nuage lien édition
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Lisez cette rubrique pour en savoir plus sur les étapes à suivre pour déployer, media de contournement avec connecteur de nuage Edition version 2.0 et ultérieure.
ms.openlocfilehash: a9f03d1d83d398a6aa78f90a4741d0010ea50392
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Déployer le contournement de média dans le nuage lien édition
 
Lisez cette rubrique pour en savoir plus sur les étapes à suivre pour déployer, media de contournement avec connecteur de nuage Edition version 2.0 et ultérieure. 
  
Le contournement de média permet au client d’envoyer le CD directement sur le tronçon suivant de commutation de téléphone RTPC (réseau Public), une passerelle ou un contrôleur de Session en périphérie (SBC) — et d’éliminer le composant d’édition de connecteur de nuage du chemin d’accès de média. Voir aussi le [Plan de support ignorer dans le nuage lien édition](plan-for-media-bypass-in-cloud-connector-edition.md).
  
## <a name="enable-media-bypass"></a>Activer la déviation du trafic multimédia

Pour activer le contournement de média, vous devez configurer le nom DNS du service web de contournement de média et activer le contournement de média dans la configuration des clients. Le service web de contournement media déploie automatiquement sur chaque serveur de médiation. Un administrateur doit choisir un nom pour un service de voix hybride (site), et ce nom doit être d’un domaine SIP enregistré pour les voix hybride. Le nom du service doit être le même sur tous les appareils du connecteur du nuage et de tous les sites de RTPC, quel que soit l’emplacement du client. Le service web doit uniquement être disponible en interne sur le réseau.
  
Un administrateur doit configurer un enregistrement DNS A dans la production interne de Active Directory. Si vous disposez d’un environnement complexe de plusieurs sites, consultez l’exemple dans [exemple : media ignore les enregistrements DNS de site web dans des environnements complexes sur plusieurs sites](deploy-media-bypass-in-cloud-connector.md#Example). L’enregistrement DNS doit résoudre uniquement pour les clients du réseau interne ; Il ne doit pas résolu pour les clients du réseau externe.
  
Après la configuration du service DNS, connecter à Skype pour entreprise en ligne à l’aide du PowerShell distant avec Skype pour les informations d’identification de l’administrateur de l’entreprise. Pour plus d’informations, consultez [connexion à Skype pour entreprise en ligne à l’aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
Dans la session PowerShell, entrez les commandes suivantes pour activer la déviation du trafic multimédia :
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Activer le contournement de média est un processus en deux étapes. L’applet de commande New-CsNetworkMedia n’enregistre pas immédiatement la nouvelle configuration ; Il crée les paramètres dans la mémoire. L’objet créé par cette applet de commande doit être enregistré dans une variable et ensuite assignée à la propriété MediaBypassSettings de la configuration réseau. Pour plus d’informations, consultez [exemple : media ignore les enregistrements DNS de site web dans des environnements complexes sur plusieurs sites](deploy-media-bypass-in-cloud-connector.md#Example).
  
La réplication entre les locaux et les composants en ligne peut prendre jusqu'à 24 heures, afin que Microsoft recommande d’exécuter les commandes nécessaires avant d’activer les utilisateurs.
  
## <a name="confirm-media-bypass-settings"></a>Confirmer les paramètres de déviation du trafic multimédia

Vous pouvez vérifier les paramètres de déviation du trafic multimédia comme suit.  
  
Pour vérifier la réplication en ligne pour votre pool de client, exécutez la commande suivante dans PowerShell distant :
  
```
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore

```

Pour vérifier la réplication locale, de se connecter aux serveurs de médiation de connecteur de nuage, exécutez la commande suivante dans PowerShell et confirmer que Enabled = True et AlwaysBypass = True
  
```
Get-CsNetworkConfiguration -LocalStore
```

Pour vérifier les paramètres du client, se déconnecter de la Skype pour client d’entreprise, vous reconnecter et confirmer que le client a reçu l’URL de service comme suit :
  
1. Ouvrez %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.  
    
2. Recherchez hybridconfigserviceinternalurl et confirmez l’URL correspond à celui que vous avez défini.
    
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

Après avoir apporté la modification, il peut prendre un certain temps pour que les modifications à répliquer sur tous les connecteurs de nuage. Pour vérifier l’état de la réplication, exécutez l’applet de commande suivant dans PowerShell sur les serveurs de médiation de connecteur de nuage : 
  
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

Un administrateur devra également à supprimer les adresses web de contournement de média à partir de serveurs DNS internes. Après avoir apporté la modification, il peut prendre un certain temps pour que les modifications à répliquer sur tous les appareils de connecteur de nuage. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Exemple : enregistrements DNS de sites seb de déviation du trafic multimédia dans des environnements multisites complexes
<a name="Example"> </a>

Les clients recevront l’adresse web du service web de contournement de média à partir d’un serveur DNS interne. Le nom du service web sera la même sur tous les appareils du connecteur du nuage et sites de nuage connecteur PSTN. Dans un environnement multisite complexe, nous vous recommandons d’à l’aide de la stratégie de DNS Windows 2016 pour la gestion du trafic en fonction de géolocalisation, afin que les clients peuvent être redirigés vers le service web qui est local pour leur réseau. 
  
Pour plus d’informations sur les stratégies de DNS Windows 2016, voir [Utiliser une stratégie DNS de géolocalisation en fonction de la gestion du trafic avec les serveurs principaux](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/primary-geo-location).
  
Voici un exemple de configuration pour une entreprise avec plusieurs sites utilisant une stratégie DNS de gestion du trafic basée sur la géolocalisation de Windows Server 2016.
  
Le nom du service de contournement est 'hybridvoice.adatum.biz'.
  
Le site d’Amsterdam a quatre appliances de connecteur de nuage déployés avec les adresses IP de serveur de médiation suivantes :
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
Le site de Seattle a trois appareils de connecteur de nuage déployés avec les adresses IP de serveur de médiation suivantes :
  
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
  
## <a name="see-also"></a>Voir aussi
<a name="Example"> </a>

#### 

[Planifier le contournement de média dans le nuage lien édition](plan-for-media-bypass-in-cloud-connector-edition.md)


---
title: Déploiement de la déviation du trafic multimédia dans Cloud Connector Edition
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
description: Lisez cette rubrique pour en savoir plus sur les étapes de déploiement de la déviation du trafic multimédia avec la version 2,0 et les versions ultérieures de Cloud Connector.
ms.openlocfilehash: eeb566e2a1a16e235813c077d4e4bf6903a467d7
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359310"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Déploiement de la déviation du trafic multimédia dans Cloud Connector Edition
 
> [!Important]
> La version Cloud Connector sera déconnectée le 31 juillet 2021 avec Skype entreprise online. Une fois que votre organisation a effectué la mise à niveau vers Teams, Découvrez comment connecter votre réseau téléphonique local à teams à l’aide du [routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Lisez cette rubrique pour en savoir plus sur les étapes de déploiement de la déviation du trafic multimédia avec la version 2,0 et les versions ultérieures de Cloud Connector. 
  
La déviation du trafic multimédia permet à un client d’envoyer directement des médias au tronçon suivant du réseau téléphonique commuté (RTC), à savoir un contrôleur de frontière de session ou un contrôleur SBC (session Border Controller) et d’éliminer le composant Cloud Connector Edition du chemin de média. Voir aussi [plan for Media Bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).
  
## <a name="enable-media-bypass"></a>Activer le contournement de média

Pour activer la déviation du trafic multimédia, vous devez configurer le nom DNS du service Web de déviation du trafic multimédia et activer la déviation du trafic multimédia dans la configuration du client. Le service Web de déviation du trafic multimédia se déploie automatiquement sur chaque serveur de médiation. Un administrateur client doit choisir un nom pour un service voix hybride (site), et ce nom doit provenir d’un domaine SIP enregistré pour la voix hybride. Le nom du service doit être le même pour toutes les appliances Cloud Connector et tous les sites PSTN, quel que soit l’emplacement du client. Le service Web ne doit être disponible qu’en interne sur le réseau.
  
Un administrateur client doit configurer un enregistrement DNS A dans le service Active Directory de production interne. Si vous disposez d’un environnement multisite complexe, consultez l’exemple de l’exemple [ci-dessous : enregistrements DNS du site Web de déviation du trafic multimédia dans des environnements multisites complexes](deploy-media-bypass-in-cloud-connector.md#Example). L’enregistrement DNS ne doit être résolu que pour les clients du réseau interne ; il ne doit pas être résolu pour les clients du réseau externe.
  
Après avoir configuré le DNS, connectez-vous à Skype entreprise Online à l’aide de PowerShell à distance avec les informations d’identification de l’administrateur Skype entreprise. Pour plus d’informations, reportez-vous à [configurer votre ordinateur pour Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .
  
Dans la session PowerShell, entrez les commandes suivantes pour activer la déviation du trafic multimédia :
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

L’activation de la déviation du trafic multimédia est un processus en deux étapes. La cmdlet New-CsNetworkMedia n’enregistre pas immédiatement la nouvelle configuration ; Il crée uniquement les paramètres en mémoire. L’objet créé par cette applet de commande doit être enregistré dans une variable, puis affecté à la propriété MediaBypassSettings de la configuration réseau. Pour plus d’informations, reportez-vous aux [enregistrements DNS du site Web de contournement de média dans les environnements multisites complexes](deploy-media-bypass-in-cloud-connector.md#Example).
  
La réplication entre les composants locaux et en ligne peut prendre jusqu’à 24 heures, c’est pourquoi Microsoft vous recommande d’exécuter les commandes nécessaires avant d’activer les utilisateurs.
  
## <a name="confirm-media-bypass-settings"></a>Vérifier les paramètres de contournement de média

Vous pouvez vérifier les paramètres de déviation du trafic multimédia comme suit. 
  
Pour vérifier la réplication en ligne de votre pool de locataires, exécutez la commande suivante dans PowerShell à distance :
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

Pour vérifier la réplication locale, connectez-vous aux serveurs de médiation Cloud Connector, exécutez la commande suivante dans PowerShell, puis confirmez que enabled = true et AlwaysBypass = true.
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

Pour vérifier les paramètres du client, déconnectez-vous du client Skype entreprise, reconnectez-vous, puis confirmez que le client a reçu l’URL de service comme suit :
  
1. Ouvrir%appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. 
    
2. Recherchez hybridconfigserviceinternalurl et confirmez que l’URL correspond à celle que vous avez définie.
    
## <a name="change-media-bypass-parameters"></a>Modifier les paramètres de contournement de média

Les administrateurs clients peuvent modifier le nom DNS du service Web en exécutant l’applet de commande suivante :
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> Les clients doivent se déconnecter et se connecter pour obtenir le nouveau nom de service et reconnaître la modification. 
  
## <a name="temporarily-disable-media-bypass"></a>Désactiver temporairement la déviation du trafic multimédia

Ce scénario peut être utile pour le dépannage ou la maintenance. Pour désactiver le service, exécutez les applets de commande suivantes :
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Après avoir effectué la modification, la réplication des modifications sur tous les connecteurs Cloud peut prendre du temps. Pour vérifier l’état de la réplication, exécutez l’applet de commande suivante dans PowerShell sur les serveurs de médiation Cloud Connector : 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

Une fois les modifications répliquées, le service Web sur le serveur de médiation commence à rejeter les demandes des clients pour le service de déviation du trafic multimédia.
  
## <a name="disable-media-bypass-permanently"></a>Désactiver définitivement la déviation du trafic multimédia

Pour désactiver la déviation du trafic multimédia de façon permanente, un administrateur client doit exécuter les commandes suivantes : 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

Un administrateur doit également supprimer les adresses Web pour la déviation du trafic multimédia des serveurs DNS internes. Après avoir effectué la modification, la réplication des modifications sur tous les appareils Cloud Connector peut prendre du temps. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Exemple : enregistrements DNS du site Web de contournement de média dans des environnements multisites complexes
<a name="Example"> </a>

Les clients recevront l’adresse Web du service Web de déviation du trafic multimédia à partir d’un serveur DNS interne. Le nom du service Web est le même pour tous les appareils Cloud Connector et les sites RTC de Cloud Connector. Dans un environnement multisite complexe, nous vous recommandons d’utiliser la stratégie DNS Windows 2016 pour la gestion du trafic basé sur l’emplacement géographique, afin que les clients puissent être redirigés vers le service Web qui est local pour leur réseau. 
  
Pour plus d’informations sur les stratégies DNS Windows 2016, reportez-vous à la rubrique [use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).
  
Voici un exemple de configuration pour une société avec plusieurs sites utilisant la stratégie DNS Windows 2016 pour la gestion du trafic basée sur l’emplacement géographique.
  
Le nom du service de contournement est « hybridvoice.adatum.biz ».
  
Le site à Amsterdam est doté de quatre Appliances Cloud Connector déployées avec les adresses IP de serveur de médiation suivantes :
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
Le site à Seattle dispose de trois appliances Cloud Connector déployées avec les adresses IP de serveur de médiation suivantes :
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
À l’aide de la gestion du trafic basé sur l’emplacement géographique, les serveurs DNS sont configurés comme suit :
  
1. Créez des sous-réseaux de client DNS pour les sous-réseaux d’Amsterdam et de Seattle.
    
2. Créez des étendues de zone DNS pour adatum.biz pour Amsterdam et Seattle.
    
3. Créez des enregistrements DNS dans chaque étendue de zone DNS.
    
    Amsterdam
    
   - Type A ;
    
   - Nom : hybridvoice dans la zone DNS adatum.biz
    
   - Cible : 192.168.1.45
    
     Créer des enregistrements supplémentaires pour les serveurs de médiation supplémentaires
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     Seattle
    
   - Tapez un
    
   - Nom : hybridvoice dans la zone DNS adatum.biz
    
   - Cible : 10.10.1.8
    
     Créer des enregistrements supplémentaires pour les serveurs de médiation supplémentaires
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. Créez la stratégie DNS qui connecte les sous-réseaux client aux étendues de zone appropriées afin de garantir la résolution DNS souhaitée.
    
À ce stade, les clients qui effectuent des requêtes DNS à partir du sous-réseau d’Amsterdam pour hybridvoice.adatum.biz renverront les adresses 192.168.1.45, 192.168.1.46, 192.168.1.47 et 192.168.1.48, tandis que les clients faisant le même formulaire de requête Seattle renverront 10.10.1.8, 10.10.1.9 et 10.10.1.10.

> [!NOTE]
> Si l’appliance CCE ne semble pas recevoir les paramètres mis à jour, vérifiez si l’appliance peut contacter le client via PowerShell à distance. Vous pouvez utiliser PowerShell à distance pour vérifier l’état du matériel avec Get-CsHybridPSTNAppliance ou utiliser PowerShell sur l’hôte CCE pour vérifier l’état avec Get-CcApplianceStatus.

  
## <a name="see-also"></a>Voir aussi
<a name="Example"> </a>

[Planifier le contournement de média dans Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)

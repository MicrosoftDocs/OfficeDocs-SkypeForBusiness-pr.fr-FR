---
title: Déployer le contournement de média dans Cloud Connector Edition
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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Lisez cette rubrique pour en savoir plus sur les étapes de déploiement de la déviation du média avec La version 2.0 de Cloud Connector et les versions ultérieures.
ms.openlocfilehash: edc00467d878f0f2ae137c86f179f864bb2ca53f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613774"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Déployer le contournement de média dans Cloud Connector Edition
 
> [!Important]
> Cloud Connector Edition sera retirer le 31 juillet 2021 avec Skype Entreprise Online. Une fois votre organisation mise à niveau vers Teams, découvrez comment connecter votre réseau téléphonique local à Teams l’aide du [routage direct.](/MicrosoftTeams/direct-routing-landing-page)

Lisez cette rubrique pour en savoir plus sur les étapes de déploiement de la déviation du média avec La version 2.0 de Cloud Connector et les versions ultérieures. 
  
La déviation du trafic multimédia permet à un client d’envoyer du trafic multimédia directement au saut suivant du réseau téléphonique commuté (PSTN) (passerelle ou contrôleur SBC) et d’éliminer le composant Cloud Connector Edition du chemin d’accès du média. Voir aussi [Planifier le contournement de média dans Cloud Connector Edition.](plan-for-media-bypass-in-cloud-connector-edition.md)
  
## <a name="enable-media-bypass"></a>Activer le contournement de média

Pour activer la déviation du trafic multimédia, vous devez configurer le nom DNS du service web de déviation du trafic multimédia et activer la déviation du trafic multimédia dans la configuration du client. Le service web de déviation du trafic multimédia se déploie automatiquement sur chaque serveur de médiation. Un administrateur client doit choisir un nom pour un service vocal hybride (site), et ce nom doit être issu d’un domaine SIP enregistré pour la voix hybride. Le nom du service doit être le même pour toutes les appliances Cloud Connector et tous les sites PSTN, quel que soit l’emplacement du client. Le service web doit uniquement être disponible en interne sur le réseau.
  
Un administrateur client doit configurer un enregistrement DNS A dans active Directory de production interne. Si vous avez un environnement multisesse complexe, voir l’exemple dans l’exemple : enregistrements DNS de site web de déviation du trafic multimédia dans des [environnements multisesses complexes.](deploy-media-bypass-in-cloud-connector.md#Example) L’enregistrement DNS doit uniquement être résolu pour les clients réseau internes ; il ne doit pas être résolu pour les clients réseau externes.
  
Après avoir configuré le DNS, connectez-vous à Skype Entreprise Online à l’aide de PowerShell à distance avec Skype Entreprise’informations d’identification de l’administrateur. Pour plus d’informations, voir [Configurer votre ordinateur pour Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .
  
Dans la session PowerShell, entrez les commandes suivantes pour activer le contournement de média :
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

L’activation du contournement de média est un processus en deux étapes. LNew-CsNetworkMedia cmdlet n’enregistre pas immédiatement la nouvelle configuration . Il crée uniquement les paramètres en mémoire. L’objet créé par cette cmdlet doit être enregistré dans une variable, puis affecté à la propriété MediaBypassSettings de la configuration réseau. Pour plus d’informations, voir l’exemple : enregistrements DNS de site web de déviation du trafic multimédia dans des [environnements multisesses complexes.](deploy-media-bypass-in-cloud-connector.md#Example)
  
La réplication entre les composants locaux et en ligne peut prendre jusqu’à 24 heures. Microsoft vous recommande donc d’exécuter les commandes nécessaires avant d’activer les utilisateurs.
  
## <a name="confirm-media-bypass-settings"></a>Confirmer les paramètres de déviation du média

Vous pouvez vérifier les paramètres de déviation du média comme suit. 
  
Pour vérifier la réplication en ligne dans votre pool de locataires, exécutez la commande suivante dans PowerShell à distance :
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

Pour vérifier la réplication sur site, connectez-vous aux serveurs de médiation Cloud Connector, exécutez la commande suivante dans PowerShell et vérifiez que Enabled=True et AlwaysBypass=True
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

Pour vérifier les paramètres du client, connectez-vous au client Skype Entreprise, connectez-vous et vérifiez que le client a reçu l’URL du service comme suit :
  
1. Ouvrez %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. 
    
2. Recherchez hybridconfigserviceinternalurl et confirmez que l’URL correspond à celle que vous avez définie.
    
## <a name="change-media-bypass-parameters"></a>Modifier les paramètres de déviation du média

Les administrateurs clients peuvent modifier le nom DNS du service web en exécutant l’cmdlet suivante :
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> Les clients doivent se signer et se connectent pour obtenir le nouveau nom de service et reconnaître la modification. 
  
## <a name="temporarily-disable-media-bypass"></a>Désactiver temporairement le contournement de média

Ce scénario peut être utile pour la résolution des problèmes ou la maintenance. Pour désactiver le service, exécutez les cmdlets suivantes :
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Après avoir apporté la modification, la réplication des modifications sur tous les connecteurs cloud peut prendre un certain temps. Pour vérifier l’état de la réplication, exécutez la cmdlet suivante dans PowerShell sur les serveurs de médiation Cloud Connector : 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

Une fois les modifications répliquées, le service web sur le serveur de médiation commence à rejeter les demandes des clients pour le service de déviation du trafic multimédia.
  
## <a name="disable-media-bypass-permanently"></a>Désactiver définitivement le contournement de média

Pour désactiver définitivement le contournement de média, un administrateur client doit exécuter les commandes suivantes : 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

Un administrateur devra également supprimer les adresses web pour la déviation du trafic multimédia des serveurs DNS internes. Après avoir apporté la modification, la réplication des modifications sur toutes les appliances Cloud Connector peut prendre un certain temps. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Exemple : enregistrements DNS de site web de déviation du trafic multimédia dans des environnements multisesses complexes
<a name="Example"> </a>

Les clients recevront l’adresse web du service web de déviation du trafic multimédia à partir d’un serveur DNS interne. Le nom du service web sera le même pour toutes les appliances Cloud Connector et tous les sites PSTN Cloud Connector. Dans un environnement multisession complexe, nous vous recommandons d’utiliser la stratégie DNS Windows 2016 pour la gestion du trafic basé sur Geo-Location, afin que les clients soient redirigés vers le service web local pour leur réseau. 
  
Pour plus d’informations sur Windows stratégies DNS 2016, voir Utiliser la stratégie [DNS](/windows-server/networking/dns/deploy/primary-geo-location)pour Geo-Location gestion du trafic basée sur les serveurs principaux.
  
Voici un exemple de configuration pour une entreprise avec plusieurs sites utilisant Windows 2016 DNS policy for Geo-Location Based Traffic Management.
  
Le nom du service de contournement est « hybridvoice.adatum.biz ».
  
Le site à Amsterdam dispose de quatre appliances Cloud Connector déployées avec les adresses IP du serveur de médiation suivantes :
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
Le site de Seattle dispose de trois appliances Cloud Connector déployées avec les adresses IP du serveur de médiation suivantes :
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
À lGeo-Location de trafic basé sur la gestion du trafic, les serveurs DNS seraient configurés comme suit :
  
1. Créez des sous-réseaux clients DNS pour les sous-réseaux Amsterdam et Seattle.
    
2. Créez des étendues de zone DNS adatum.biz pour Amsterdam et Seattle.
    
3. Créez des enregistrements DNS dans chaque étendue de zone DNS.
    
    Amsterdam
    
   - Tapez A ;
    
   - Name : hybridvoice dans la zone adatum.biz DNS
    
   - Cible : 192.168.1.45
    
     Créer des enregistrements supplémentaires pour des serveurs de médiation supplémentaires
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     Seattle
    
   - Type A
    
   - Name : hybridvoice dans adatum.biz zone DNS
    
   - Cible : 10.10.1.8
    
     Créer des enregistrements supplémentaires pour des serveurs de médiation supplémentaires
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. Créez la stratégie DNS qui connecte les sous-réseaux clients aux étendues de zone appropriées pour garantir la résolution DNS souhaitée.
    
À ce stade, les clients qui font des requêtes DNS à partir du sous-réseau d’Amsterdam pour hybridvoice.adatum.biz retourneront le 192.168.1.45, 192.168.1.46, 192.168.1.47 et 192.168.1.48, tandis que les clients qui font le même formulaire de requête Seattle retournent 10.10.1.8, 10.10.1.9 et 10.10.1.10.

> [!NOTE]
> Si l’appliance CCE ne semble pas obtenir les paramètres mis à jour, vérifiez si l’appliance est en mesure de contacter le client via PowerShell à distance. Vous pouvez utiliser Remote PowerShell pour vérifier l’état de l’appliance avec Get-CsHybridPSTNAppliance ou utiliser PowerShell sur l’hôte CCE pour vérifier l’état avec Get-CcApplianceStatus.

  
## <a name="see-also"></a>Voir aussi
<a name="Example"> </a>

[Planifier le contournement de média dans Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)
---
title: 'Lync Server 2013 : configuration du routage géodépendant pour les conférences'
TOCTitle: Configuration du routage géodépendant pour les conférences
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56269658
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration du routage géodépendant pour les conférences dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

L’application de conférence avec routage géodépendant s’appuie sur la configuration du routage géodépendant Lync Server 2013. Les configurations principales suivantes sont disponibles :

  - L’emplacement des participants rejoignant une réunion est déterminé sur la base de leur site réseau. Un site réseau et les sous-réseaux associés doivent être définis dans Lync Server pour appliquer le routage géodépendant.

  - Pour appliquer le routage géodépendant des réunions, le routage géodépendant doit être activé pour les participants Lync.

  - Pour appliquer le routage géodépendant des points de terminaison PSTN rejoignant des réunions, le tronçon SIP utilisé pour connecter les points de terminaison PSTN doit être configuré pour le routage géodépendant.

Pour plus d’informations sur le déploiement et la configuration du routage géodépendant de Lync Server 2013, voir [Configuration du routage géodépendant](lync-server-2013-configuring-location-based-routing.md).

## Activation de l’application de conférence avec routage géodépendant

L’application de conférence avec routage géodépendant est désactivée par défaut. Avant d’activer cette application, vous devez déterminer la priorité adaptée à affecter à l’application. Pour ce faire, exécutez l’applet de commande suivante dans Lync Server Management Shell :

Get-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\>

Dans cette applet de commande, \<Pool FQDN\> correspond au pool dans lequel l’application de conférence avec routage géodépendant doit être activée.

Cette applet de commande retourne la liste des applications hébergées par le serveur Lync Server et la valeur de priorité pour chacun d’eux. Une valeur de priorité supérieure à celle de l’application « UdcAgent » et inférieure à celle des applications « DefaultRouting », « ExumRouting » et « OutboundRouting » doit être affectée à l’application de conférence avec routage géodépendant. Il est recommandé d’affecter à l’application de conférence avec routage géodépendant une valeur de priorité supérieure d’un point à celle de l’application « UdcAgent ».

Par exemple, si l’application « UdcAgent » a la valeur de priorité « 2 », l’application « DefaultRouting » a la valeur de priorité « 8 », l’application « ExumRouting » a la valeur de priorité « 9 » et l’application « OutboundRouting » a la valeur de priorité « 10 », vous devez affecter la valeur de priorité « 3 » à l’application de conférence avec routage géodépendant. Ainsi, la priorité des applications est définie dans l’ordre suivant : autres applications (priorités : 0 à 1), « UdcAgent » (priorité : 2), application de conférence avec routage géodépendant (priorité : 3), autres applications (priorités : 4 à 8), « DefaultRouting » (priorité : 9), « ExumRouting » (priorité : 10) et « OutboundRouting » (priorité : 11).

Une fois que vous avez déterminé la valeur de priorité correcte pour l’application de conférence avec routage géodépendant, tapez l’applet de commande suivante pour chaque pool frontal ou serveur Standard Edition Server qui héberge des utilisateurs pour lesquels le routage géodépendant est activé :

New-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\>/LBRouting -Priority \<Application Priority\> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting

Par exemple :

New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting

Une fois que vous avez utilisé cette applet de commande, redémarrez tous les serveurs frontaux dans le pool ou les serveurs Standard Edition Server sur lesquels l’application de conférence avec routage géodépendant a été activée.

> [!IMPORTANT]  
> Les restrictions de routage géodépendant relatives aux conférences ou transferts consultatifs ne sont pas appliquées tant que tous les serveurs frontaux dans les pools applicables ou les serveurs Standard Edition Server ne sont pas redémarrés. Si vous définissez <strong>–Critical</strong> sur <strong>$true</strong> dans les applets de commande précédentes, vos services Lync redémarrent immédiatement. Si vous ne souhaitez pas que ces services redémarrent immédiatement, définissez <strong>–Critical</strong> sur <strong>$false</strong> pour le moment, puis utilisez <strong>Set-CsServerApplication</strong> pour modifier <strong>-Critical</strong> sur <strong>$true</strong> par la suite, une fois que les services ont redémarré.

Une fois l’application de conférence avec routage géodépendant correctement activée et tous les serveurs Lync applicables redémarrés, toutes les conférences organisées par des utilisateurs Lync pour lesquels le routage géodépendant est activé seront surveillées pour empêcher le contournement des frais de réseau téléphonique commuté.


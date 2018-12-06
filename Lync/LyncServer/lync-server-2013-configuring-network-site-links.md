---
title: Configuration des liens du site réseau
TOCTitle: Configuration des liens du site réseau
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg521023(v=OCS.15)
ms:contentKeyID: 49297871
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des liens du site réseau

 

_**Dernière rubrique modifiée :** 2012-11-01_

Dans une configuration de contrôle d’admission des appels, vous pouvez créer des stratégies réseau intersite qui définissent les restrictions de bande passante entre les sites qui sont directement liés. Quand des sites de réseau partagent un lien direct, des restrictions de bande passante pour les connexions audio et vidéo peuvent être définies pour lesdits sites. Vous ne pouvez pas utiliser le Panneau de configuration Lync Server pour configurer les stratégies réseau de site. Pour cela, vous devez utiliser les applets de commande Lync Server Management Shell. Vous pouvez créer, modifier et supprimer un lien de site réseau (appelé également stratégie réseau intersite) à partir de Lync Server Management Shell.

## Pour créer un lien de site réseau

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé, en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires tels que décrits dans [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  À l’invite de commandes, tapez la commande suivante en spécifiant les valeurs valides pour votre configuration :
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    Cet exemple créé un lien de site réseau nommé Reno\_Portland qui définit des restrictions de la bande passante entre les sites réseau Reno et Portland. Les sites réseau et le profil de stratégie de bande passante doivent être existants avant d’exécuter cette commande.

Pour plus d’informations sur les descriptions des paramètres, voir [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterSitePolicy) dans la documentation de Lync Server Management Shell. Pour récupérer une liste des profils de stratégie de bande passante pouvant être appliqués au lien de site réseau, appelez l’applet de commande **Get-CsNetworkBandwidthPolicyProfile**. Pour plus d’informations, voir [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) dans la documentation de Lync Server Management Shell.

## Pour modifier un lien de site réseau

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé, en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires tels que décrits dans [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Utilisez l’applet de commande **Set-CsNetworkInterSitePolicy** pour modifier les propriétés d’un lien de site réseau donné. Vous pouvez modifier l’un ou l’autre des sites connectés, ou les deux, ainsi que le profil de stratégie de bande passante associé au lien. Voici un exemple de modification du profil de stratégie de bande passante d’un lien de site nommé Reno\_Portland :
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Pour plus d’informations sur les descriptions des paramètres, voir [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterSitePolicy) dans la documentation de Lync Server Management Shell.

## Pour supprimer un lien de site réseau

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé, en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires tels que décrits dans [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Utilisez l’applet de commande **Remove-CsNetworkInterSitePolicy** pour supprimer un lien de site réseau. L’exemple suivant supprime le lien de site réseau Reno\_Portland :
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Pour plus d’informations sur les descriptions des paramètres, voir [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterSitePolicy) dans la documentation de Lync Server Management Shell.

## Voir aussi

#### Concepts

[Cmdlets du contrôle d’admission des appels](https://docs.microsoft.com/en-us/powershell/module/skype/)  

#### Autres ressources

[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)


---
title: "Suppr. des paramètres de configuration de la qualité de l’expérience (QoE)"
TOCtitle: "Suppr. des paramètres de configuration de la qualité de l’expérience (QoE)"
ms:assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182613(v=OCS.15)
ms:contentKeyID: 49299440
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression des paramètres de configuration de la qualité de l’expérience (QoE)

 

_**Dernière rubrique modifiée :** 2013-02-23_

Les mesures QoE (qualité de l’expérience) effectuent le suivi de la qualité des appels audio et vidéo dans votre organisation, y compris le nombre de paquets réseau perdus, le bruit de fond et le montant de « gigue » (différences de retard des paquets). Ces mesures sont stockées dans une base de données distincte des autres données (telles que les enregistrements des détails des appels), ce qui permet d’activer et de désactiver l’enregistrement QoE indépendamment de l’enregistrement des autres données.

Lorsque vous installez Microsoft Lync Server 2013, une collection unique et globale de paramètres de configuration QoE est crée pour vous. Les administrateurs peuvent également créer des collections de paramètres personnalisés pouvant être appliquées aux sites individuels. Par conception, les paramètres configurés sur l’étendue Site sont prioritaires sur les paramètres configurés sur l’étendue Global. Si vous supprimez les paramètres sur l’étendue Site, la QoE sera gérée dans ce site en utilisant les paramètres globaux.

Notez que vous pouvez également « supprimer » les paramètres globaux. Cependant, les paramètres globaux ne seront pas réellement supprimés. Toutes les propriétés de la collection seront en revanche réinitialisées à leurs valeurs par défaut. Par exemple, la purge est activée par défaut dans une collection de paramètres de configuration QoE. Supposons que vous modifiez la collection globale pour que la purge soit désactivée. Si vous supprimez ultérieurement les paramètres globaux, toutes les propriétés seront réinitialisées à leurs valeurs par défaut. Dans ce cas, cela signifie que la purge sera de nouveau activée.

Vous pouvez supprimer les paramètres de configuration QoE en utilisant Panneau de configuration Lync Server ou la cmdlet [Remove-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsQoEConfiguration).

## Pour supprimer les paramètres de configuration QoE en utilisant Panneau de configuration Lync Server

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.

4.  Sur la page **Données QoE**, cliquez sur la stratégie de votre choix, puis sur **Modifier**, et enfin sur **Supprimer**.

5.  Cliquez sur **OK**.

## Pour supprimer les paramètres de configuration QoE en utilisant les cmdlets Lync Server Management Shell

Vous pouvez également supprimer les paramètres de configuration QoE en utilisant Lync Server Management Shell et la cmdlet **Remove-CsQoEConfiguration**. Vous pouvez exécuter cette cmdlet depuis Lync Server 2013 Management Shell ou depuis une session distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour supprimer une collection spécifiée de paramètres de configuration QoE

  - Cette commande supprime les paramètres de configuration QoE appliqués au site Redmond :
    
        Remove-CsQoEConfiguration -Identity "site:Redmond"

## Pour supprimer tous les paramètres de configuration QoE appliqués à l’étendue Site

  - Cette commande supprime tous les paramètres de configuration QoE appliqués à l’étendue Site :
    
        Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration

## Pour supprimer tous les paramètres de configuration QoE lorsque le suivi QoE est désactivé

  - Cette commande supprime tous les paramètres de configuration QoE lorsque le suivi QoE est désactivé :
    
        Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration

Pour plus d’informations, voir [Remove-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsQoEConfiguration).


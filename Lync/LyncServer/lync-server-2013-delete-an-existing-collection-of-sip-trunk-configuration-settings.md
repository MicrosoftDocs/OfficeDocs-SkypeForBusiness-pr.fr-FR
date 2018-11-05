---
title: "Supp. d’une collection existante de par. de conf. de jonction SIP dans LS 2013"
TOCtitle: "Supp. d’une collection existante de par. de conf. de jonction SIP dans LS 2013"
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49891310
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression d’une collection existante de paramètres de configuration de jonction SIP dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-22_

Les paramètres de configuration de jonction SIP définissent la relation et les capacités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un autocommutateur privé IP (PBX) ou un contrôleur SBC du côté fournisseur de services. Ces paramètres permettent de spécifier ce qui suit :

  - L’activation ou non du contournement de média sur les jonctions.

  - Les conditions d’envoi des paquets RTCP (Real-time Transport Control Protocol).

  - L’application ou non du chiffrement SRTP (Secure Real-Time Protocol) sur chaque jonction.

Quand vous installez Microsoft Lync Server 2013, une collection globale de paramètres de configuration de jonction SIP est créée automatiquement. Si cette collection globale de paramètres ne peut pas être supprimée, vous pouvez toutefois utiliser le Panneau de configuration Lync Server ou l’applet de commande [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) pour rétablir la valeur par défaut des propriétés de la collection globale. Par exemple, si vous avez attribué à la propriété Enable3pccRefer la valeur True, lors de la « réinitialisation » de la collection globale, la propriété Enable3pccRefer reprend sa valeur par défaut (False).

Les administrateurs peuvent aussi créer des paramètres de configuration de jonction personnalisés étendus à un site ou un service (pour une passerelle PSTN individuelle) ; ces paramètres personnalisés peuvent être supprimés. Au moment de supprimer ces paramètres personnalisés, tenez compte des points suivants :

  - Si vous supprimez des paramètres étendus à un service, la jonction SIP gérée par ces paramètres est gérée par les paramètres appliqués à son site, le cas échéant. En l’absence de paramètres de site, la jonction est gérée par la collection globale de paramètres de configuration de jonction.

  - Si vous supprimez des paramètres étendus à un site, les jonctions SIP gérées par ces paramètres sont alors gérées par la collection globale de paramètres de configuration de jonction.

## Suppression des paramètres de configuration de jonction à partir du Panneau de configuration Lync Server

1.  Dans le Panneau de configuration Lync Server, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.

2.  Sous l’onglet **Configuration de la jonction**, sélectionnez la collection de paramètres de configuration de jonction SIP à supprimer, cliquez sur **Modifier**, puis sur **Supprimer**. Pour supprimer plusieurs collections en une seule opération, cliquez sur la première collection à supprimer, maintenez la touche Ctrl enfoncée, puis cliquez sur les autres collections à supprimer.

3.  La propriété **État** de la collection est mise à jour et présente la valeur **Non validé**. Pour valider les modifications et supprimer la collection, cliquez sur **Valider**, puis sur **Valider tout**.

4.  Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.

5.  Dans la boîte de dialogue **Panneau de configuration Microsoft Lync Server 2013**, cliquez sur **OK**.

6.  Si vous changez d’avis et décidez de ne pas supprimer la collection, cliquez sur **Valider**, puis sur **Annuler toutes les modifications non validées**. Quand la boîte de dialogue **Panneau de configuration Microsoft Lync Server 2013** s’affiche, cliquez sur **OK**.

## Suppression des paramètres de configuration de jonction à l’aide des applets de commande Lync Server PowerShell

Les paramètres de configuration de jonction peuvent aussi être supprimés à l’aide de l’applet de commande Windows PowerShell Remove-CsTrunkConfiguration. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Suppression d’une collection de paramètres spécifiée

  - La commande suivante supprime les paramètres de configuration de jonction appliqués au site Redmond :
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

## Suppression de toutes les collections appliquées dans l’étendue du site

  - Cette commande supprime tous les paramètres de configuration de jonction appliqués dans l’étendue du site :
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

## Suppression de toutes les collections avec e contournement de média activé

  - La commande suivante supprime tous les paramètres de configuration de jonction dès lors que le contournement de média est activé :
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration).


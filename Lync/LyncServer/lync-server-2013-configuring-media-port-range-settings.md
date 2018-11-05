---
title: Configuration des paramètres des plages de ports multimédias
TOCTitle: Configuration des paramètres des plages de ports multimédias
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204770(v=OCS.15)
ms:contentKeyID: 49296724
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des paramètres des plages de ports multimédias

 

_**Dernière rubrique modifiée :** 2015-03-09_

Les paramètres des plages de ports multimédias peuvent affecter considérablement les performances du client et doivent donc être configurés. Vous pouvez les configurer dans Lync Server Management Shell.

### Paramètres de plage de ports multimédias

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Paramètre</th>
<th>Description</th>
<th>Applet de commande Lync Server Management Shell</th>
<th>Paramètres de l’applet de commande</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Portrange\Enabled</p></td>
<td><p>Spécifie si les plages de ports envoyées par le serveur doivent être utilisées par le client pour les médias et la signalisation. Utilisée conjointement avec les sous-valeurs MinMediaPort et MaxMediaPort.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRangeEnabled</p></td>
</tr>
<tr class="even">
<td><p>Portrange\MinMediaPort</p></td>
<td><p>Spécifie le numéro de port de début à utiliser pour le trafic multimédia. Combinée avec MaxMediaPort pour spécifier la plage de ports. La plage minimale recommandée est de 40 ports.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPort (représente le numéro de port de début à utiliser pour le trafic multimédia client)</p></td>
</tr>
<tr class="odd">
<td><p>Portrange\MaxMediaPort</p></td>
<td><p>Spécifie le numéro de port le plus élevé à utiliser pour le trafic multimédia. Combinée avec MinMediaPort pour spécifier la plage de ports. La plage minimale recommandée est de 40 ports.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRange (indique le nombre total de ports disponibles pour le trafic multimédia client. La valeur par défaut est 40)</p></td>
</tr>
</tbody>
</table>


## Pour configurer les paramètres de la plage de ports multimédias

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande suivante :
    
        Get-CsConferencingConfiguration
    
    Cette applet de commande renvoie les paramètres de configuration de conférence.

3.  Exécutez l’applet de commande suivante avec les paramètres et valeurs que vous souhaitez modifier (pour plus d’informations sur les paramètres de cette applet de commande, voir la documentation de Lync Server Management Shell) :
    
        Set-CsConferencingConfiguration
    
    > [!NOTE]  
    > Vous pouvez créer des ensembles de paramètres de configuration de conférence supplémentaires pour des sites spécifiques. Utilisez l’applet de commande <strong>New- CsConferencingConfiguration</strong> avec une identité de site. Lorsque vous créez de nouveaux paramètres de configuration de conférence pour des sites, ces paramètres prévalent sur les paramètres globaux. Pour plus d’informations, voir la documentation Lync Server Management Shell.

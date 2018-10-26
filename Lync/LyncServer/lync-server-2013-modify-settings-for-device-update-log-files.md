---
title: Modifier les paramètres des fichiers journaux de mise à jour des périphériques
TOCTitle: Modifier les paramètres des fichiers journaux de mise à jour des périphériques
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182554(v=OCS.15)
ms:contentKeyID: 49298333
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modifier les paramètres des fichiers journaux de mise à jour des périphériques

 

_**Dernière rubrique modifiée :** 2015-03-09_

Vous pouvez modifier les paramètres de journalisation des informations de mise à jour des périphériques dans votre organisation à l’aide du Panneau de configuration Lync Server ou de Lync Server Management Shell. Le tableau suivant indique les paramètres qui sont modifiables et les outils à utiliser pour les modifier.

Les paramètres des journaux peuvent être modifiés globalement ou par site.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Pour modifier</th>
<th>Utilisez</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>La taille maximale (en octets) d’un fichier journal</p></td>
<td><p>Panneau de configuration Lync Server</p>
<p>- ou -</p>
<p>Lync Server Management Shell</p></td>
</tr>
<tr class="even">
<td><p>La quantité maximale d’informations (en octets) pouvant être conservée dans le cache</p></td>
<td><p>Panneau de configuration Lync Server</p>
<p>- ou -</p>
<p>Lync Server Management Shell</p></td>
</tr>
<tr class="odd">
<td><p>La fréquence (en minutes) d’écriture des informations du cache dans le fichier journal</p></td>
<td><p>Panneau de configuration Lync Server</p>
<p>- ou -</p>
<p>Lync Server Management Shell</p></td>
</tr>
<tr class="even">
<td><p>La durée (en jours) de conservation des fichiers journaux</p></td>
<td><p>Panneau de configuration Lync Server</p>
<p>- ou -</p>
<p>Lync Server Management Shell</p></td>
</tr>
<tr class="odd">
<td><p>Quand (heure de la journée) vérifier la présence de fichiers expirés qui doivent être supprimés</p></td>
<td><p>Lync Server Management Shell</p></td>
</tr>
<tr class="even">
<td><p>Les extensions de fichiers journaux à autoriser</p></td>
<td><p>Lync Server Management Shell</p></td>
</tr>
<tr class="odd">
<td><p>Les types de fichiers journaux à conserver</p></td>
<td><p>Lync Server Management Shell</p></td>
</tr>
</tbody>
</table>


## Pour modifier les paramètres de journalisation à l’aide du Panneau de configuration Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur **Configuration du fichier journal du périphérique**.

3.  Dans la page **Configuration du fichier journal du périphérique**, double-cliquez sur la configuration à modifier.

4.  Dans la boîte de dialogue **Modifier le paramètre du fichier journal**, modifiez un ou plusieurs des paramètres suivants :
    
      - **Taille de fichier maximale (octets)**   Spécifie la taille maximale qu’un fichier journal peut atteindre avant d’être supprimé définitivement. La valeur par défaut est 1 024 000 octets (1 Mo).
    
      - **Taille de cache maximale (octets)**   Spécifie la quantité maximale d’informations (en octets) pouvant être conservée dans la mémoire cache du fichier journal avant le nettoyage du cache et l’enregistrement des données dans un fichier journal. La valeur par défaut est 512 000 octets (0,5 Mo).
    
      - **Délai de vidage du cache en minutes (1-60)**   Indique la fréquence à laquelle les informations stockées dans la mémoire cache du fichier journal sont écrites dans le fichier journal réel. Une fois les données enregistrées, la mémoire cache est effacée. La valeur par défaut est de cinq minutes.
    
      - **Jours pendant lesquels conserver les fichiers journaux (1-365)**   Spécifie le nombre de jours pendant lesquels les fichiers journaux doivent être conservés avant d’être supprimés définitivement. La valeur par défaut est 10 jours.

5.  Cliquez sur **Valider**.

## Modification des paramètres de journalisation à l’aide d’applets de commande Windows PowerShell

Les paramètres des fichiers journaux de mise à jour des périphériques peuvent être modifiés à l’aide de Windows PowerShell et de l’applet de commande **Set-CsDeviceUpdateConfiguration**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell.

> [!NOTE]  
> Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>.

Les exemples suivants montrent comment modifier des paramètres à l’aide de **Set-CsDeviceUpdateConfiguration**.

## Pour modifier la taille maximale des fichiers journaux et l’intervalle de nettoyage des journaux

  - La commande suivante modifie les paramètres des journaux de mise à jour des périphériques appliqués au site Redmond. Dans cet exemple, la taille maximale des fichiers journaux est de 204 800 octets et l’intervalle de nettoyage des journaux est de 14 jours.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

## Pour modifier l’heure de nettoyage des journaux

  - Cette commande définit à 03h00 l’horaire de nettoyage des journaux du site Redmond.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsDeviceUpdateConfiguration).


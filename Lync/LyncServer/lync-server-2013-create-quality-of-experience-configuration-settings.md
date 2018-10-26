﻿---
title: Création des paramètres de configuration de la qualité de l’expérience (QoE)
TOCTitle: Création des paramètres de configuration de la qualité de l’expérience (QoE)
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg521006(v=OCS.15)
ms:contentKeyID: 49297429
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création des paramètres de configuration de la qualité de l’expérience (QoE)

 

_**Dernière rubrique modifiée :** 2015-03-09_

Les mesures de la qualité de l’expérience (QoE) effectuent le suivi de la qualité des appels audio et vidéo dans votre organisation, y compris le nombre de paquets réseau perdus, le bruit de fond et le montant de « gigue » (différences de retard des paquets). Ces mesures sont stockées dans une base de données distincte des autres données (telles que les enregistrements des détails des appels), ce qui permet d’activer et de désactiver l’enregistrement QoE indépendamment de l’enregistrement des autres données.

Lorsque vous installez Microsoft Lync Server 2013, une collection globale et unique de paramètres de configuration QoE est créée pour vous. Les administrateurs ont également la possibilité de créer des paramètres personnalisés au niveau de l’étendue du site. Chaque fois que ces paramètres étendus aux sites sont utilisés, ils ont priorité sur les paramètres globaux. Par exemple, si vous créez des paramètres étendus au site pour le site Redmond, ceux-ci (et non les paramètres globaux) sont utilisés pour gérer la qualité de l’expérience à Redmond.

Vous pouvez créer des paramètres de configuration QoE à l’aide du Panneau de configuration Lync Server ou de l’applet de commande [New-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsQoEConfiguration). Si vous utilisez le Panneau de configuration Lync Server pour créer des paramètres, les options suivantes vous sont proposées :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Paramètre de l’interface utilisateur</th>
<th>Paramètre PowerShell</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nom</p></td>
<td><p>Identity</p></td>
<td><p>Identificateur unique des paramètres à créer. Les paramètres de configuration QoE peuvent uniquement être créés au niveau de l’étendue du site.</p></td>
</tr>
<tr class="even">
<td><p>Activer la surveillance des données de QoE</p></td>
<td><p>EnableQoE</p></td>
<td><p>Spécifie si les enregistrements QoE seront collectés et enregistrés dans la base de données de surveillance.</p></td>
</tr>
<tr class="odd">
<td><p>Activer le vidage des données de QoE</p></td>
<td><p>EnablePurging</p></td>
<td><p>Spécifie si les rapports sont vidés une fois la durée définie dans la propriété <strong>Conserver les données QoE pendant la durée maximale (jours)</strong> écoulée.</p></td>
</tr>
<tr class="even">
<td><p>Conserver les données QoE pendant la durée maximale (jours)</p></td>
<td><p>KeepQoEDataForDays</p></td>
<td><p>Nombre de jours pendant lesquels les données QoE sont enregistrées avant d’être vidées de la base de données. Cette valeur est ignorée si le vidage est désactivé.</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> L’applet de commande New-CsQoEConfiguration comprend des options supplémentaires qui ne sont pas disponibles dans le Panneau de configuration Lync Server. Pour plus d’informations, voir la rubrique d’aide <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</a>.

## Pour créer des paramètres de configuration QoE à l’aide du Panneau de configuration Lync Server

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.

4.  Dans la page **Données de qualité de l’expérience**, cliquez sur **Nouveau**.

5.  Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit être appliquée, puis cliquez sur **OK**.

6.  Dans **Nouveau paramètre de qualité de l’expérience**, procédez comme suit :
    
      - Sélectionnez **Activer la surveillance des données de QoE** pour activer la surveillance.
    
      - Sélectionnez **Activer le vidage des données de QoE** pour activer le vidage.
    
      - Dans **Conserver les données QoE pendant la durée maximale (jours)**, sélectionnez le nombre maximum de jours de rétention des enregistrements QoE.

7.  Cliquez sur **Valider**.

## Pour créer des paramètres de configuration QoE à l’aide d’applets de commande Windows PowerShell

Vous pouvez également créer des paramètres de configuration QoE à l’aide de Windows PowerShell et de l’applet de commande New-CsQoEConfiguration. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour créer une collection de paramètres de configuration QoE

  - Cette commande crée une collection de paramètres de configuration QoE qui sont appliqués au site Redmond :
    
        New-CsQoEConfiguration -Identity "site:Redmond"

## Pour créer une collection de paramètres de configuration QoE dans laquelle la surveillance QoE est désactivée

  - Étant donné qu’aucun paramètre (à l’exception du paramètre Identity obligatoire) n’a été spécifié dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés. Pour créer des paramètres qui utilisent des valeurs de propriété différentes, incluez simplement le paramètre approprié et la valeur du paramètre. Par exemple, pour créer une collection de paramètres de configuration de qualité de l’expérience qui, par défaut, permet de désactiver enregistrement de données QoE, utilisez une commande semblable à celle-ci :
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

## Pour spécifier plusieurs valeurs de propriété lors de création d’une collection de paramètres de configuration QoE

  - Vous pouvez spécifier plusieurs valeurs de propriétés en incluant plusieurs paramètres. Par exemple, cette commande configure les nouveaux paramètres de manière à conserver les données QoE pendant 30 jours et à vider les anciennes données à 03:00 :
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [New-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsQoEConfiguration).


---
title: "Créa. ou mo. d’une coll. de par. de con. de l’enr. des détails des appels"
TOCtitle: "Créa. ou mo. d’une coll. de par. de con. de l’enr. des détails des appels"
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49891538
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création ou modification d’une collection de paramètres de configuration de l’enregistrement des détails des appels

 

_**Dernière rubrique modifiée :** 2015-03-09_

L’enregistrement des détails des appels permet d’assurer le suivi des sessions de messagerie instantanée d’égal à égal, des appels téléphoniques VoIP (Voice over Internet Protocol) et des téléconférences. Ces données d’utilisation permettent de savoir qui appelle qui, à quelle heure et la durée de l’entretien.

Quand vous installez Microsoft Lync Server 2013, une simple collection globale de paramètres de configuration d’enregistrement des détails des appels est automatiquement créée. Les administrateurs peuvent aussi créer des paramètres personnalisés sur l’étendue du site. Chaque fois que ces paramètres d’étendue de site sont utilisés, ils prennent la priorité sur les paramètres globaux. Par exemple, si vous créez des paramètres pour l’étendue du site de Redmond, ces paramètres (au lieu des paramètres globaux) servent alors à gérer l’enregistrement des détails des appels à Redmond.

Vous pouvez créer des paramètres de configuration d’enregistrement des détails des appels à l’aide du Panneau de configuration Lync Server ou de l’applet de commande [New-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCdrConfiguration). Le Panneau de configuration Lync Server comme l’applet de commande [Set-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration) permettent de modifier les paramètres. Si vous utilisez le Panneau de configuration Lync Server pour effectuer ces tâches, vous disposez alors des options suivantes :


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
<td><p>Name</p></td>
<td><p>Identity</p></td>
<td><p>Identificateur unique pour les paramètres de configuration d’enregistrement des détails des appels créés. Ces paramètres peuvent uniquement être créés au niveau de l’étendue Site.</p></td>
</tr>
<tr class="even">
<td><p>Activer la surveillance des enregistrements des détails des appels</p></td>
<td><p>EnableCDR</p></td>
<td><p>Indique si l’enregistrement des détails des appels est activé ou non.</p></td>
</tr>
<tr class="odd">
<td><p>Activer le vidage des enregistrements des détails des appels</p></td>
<td><p>EnablePurging</p></td>
<td><p>Indique si les enregistrements des détails des appels doivent être périodiquement supprimés de la base de données d’enregistrements des détails des appels.</p></td>
</tr>
<tr class="even">
<td><p>Conserver les enregistrements des détails des appels pendant la durée maximale (jours)</p></td>
<td><p>KeepCallDetailForDays</p></td>
<td><p>Indique le nombre de jours pendant lesquels les enregistrements des détails des appels sont conservés dans la base de données. Tout enregistrement plus ancien que le nombre de jours spécifié est automatiquement supprimé. (Notez que le vidage ne se produit que s’il est activé.)</p></td>
</tr>
<tr class="odd">
<td><p>Conserver les données de signalement d’erreurs pendant la durée maximale (jours)</p></td>
<td><p>KeepErrorReportForDays</p></td>
<td><p>Indique le nombre de jours pendant lesquels les rapports d’erreur des détails des appels sont conservés. Tout rapport plus ancien que le nombre de jours spécifié est automatiquement supprimé. Les rapports d’erreur des détails des appels sont des rapports de diagnostic téléchargés par les applications clientes.</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Les applets de commande New-CsCdrConfiguration et Set-CsCdrConfiguration comprennent des options supplémentaires non disponibles dans le Panneau de configuration Lync Server. Pour plus d’informations, voir les rubriques d’aide <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</a> et <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</a>.

## Pour créer des paramètres de configuration d’enregistrements des détails des appels à l’aide du Panneau de configuration Lync Server

1.  Dans le Panneau de configuration Lync Server, cliquez sur **Surveillance et archivage**.

2.  Sous l’onglet **Enregistrement des détails des appels**, cliquez sur **Nouveau**.

3.  Dans la boîte de dialogue **Sélectionner un site**, indiquez le site où les nouveaux paramètres de configuration doivent être créés. Si la boîte de dialogue est vide, cela indique qu’une collection de paramètres de configuration d’enregistrement des détails des appels a déjà été affectée à tous vos sites. Chaque site ne peut recevoir qu’une seule collection. Vous pouvez dans ce cas supprimer puis recréer les paramètres ou modifier simplement les paramètres existants.

4.  Dans la boîte de dialogue **Nouveau paramètre d’enregistrement des détails des appels (CDR)**, sélectionnez les options voulues, puis cliquez sur **Valider**.

## Pour modifier les paramètres de configuration d’enregistrements des détails des appels à l’aide du Panneau de configuration Lync Server

1.  Dans le Panneau de configuration Lync Server, cliquez sur **Surveillance et archivage**.

2.  Double-cliquez sur la collection de paramètres à modifier, ou sélectionnez la collection, cliquez sur **Modifier**, puis sur **Afficher les détails**. Sachez que vous ne pouvez modifier qu’une seule collection à la fois. Pour appliquer les mêmes modifications à plusieurs collections, faites appel à Lync Server Management Shell.

3.  Dans la boîte de dialogue **Modifier le paramètre de l’enregistrement des détails des appels**, sélectionnez les options voulues, puis cliquez sur **Valider**.

## Pour créer des paramètres de configuration d’enregistrements des détails des appels à l’aide des applets de commande Lync Server Management Shell

Vous pouvez créer des paramètres de configuration d’enregistrement des détails des appels en utilisant Windows PowerShell et l’applet de commande **New-CsCdrConfiguration**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour créer une collection de paramètres de configuration d’enregistrement des détails des appels

  - La commande crée une collection de paramètres de configuration pour l’enregistrement des détails des appels qui s’applique au site Redmond :
    
        New-CsCdrConfiguration -Identity "site:Redmond"

## Pour créer une collection de paramètres de configuration d’enregistrement des détails des appels qui désactivent l’enregistrement des détails des appels

  - Comme aucun paramètre (autre que celui obligatoire sur l’identité) n’a été précisé dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés. Pour créer des paramètres qui font appel à d’autres valeurs de propriétés, incluez simplement le paramètre approprié et sa valeur. Par exemple, pour créer une collection de paramètres de configuration des détails des appels, l’autorisation de la désactivation de l’enregistrement des détails des appels fait appel par défaut à une commande comme celle-ci :
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

## Pour spécifier plusieurs valeurs de propriétés pendant la création d’une collection de paramètres de configuration d’enregistrement des détails des appels

  - Vous pouvez modifier plusieurs valeurs de propriétés en incluant plusieurs paramètres. Par exemple, cette commande configure les nouveaux paramètres pour conserver les enregistrements des détails des appels pendant 30 jours et les rapports d’erreur 90 jours :
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

Pour plus d’informations, voir la rubrique d’aide de l’applet de commande [New-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCdrConfiguration).


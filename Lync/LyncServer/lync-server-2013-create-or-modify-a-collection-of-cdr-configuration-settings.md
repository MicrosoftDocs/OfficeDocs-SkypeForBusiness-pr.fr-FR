---
title: 'Lync Server 2013 : création ou modification d’un ensemble de paramètres de configuration de CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37ed8be52827f56b14c52f1bddd950ab39883cdf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>Créer ou modifier un ensemble de paramètres de configuration de CDR dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

L’enregistrement des détails des appels permet d’assurer le suivi des sessions de messagerie instantanée d’égal à égal, des appels téléphoniques VoIP (Voice over Internet Protocol) et des téléconférences. Ces données d’utilisation permettent de savoir qui appelle qui, à quelle heure et la durée de l’entretien.

Lorsque vous installez Microsoft Lync Server 2013, une collection globale unique de paramètres de configuration CDR est créée pour vous. Les administrateurs peuvent aussi créer des paramètres personnalisés sur l’étendue du site. Chaque fois que ces paramètres d’étendue de site sont utilisés, ils prennent la priorité sur les paramètres globaux. Par exemple, si vous créez des paramètres pour l’étendue du site de Redmond, ces paramètres (au lieu des paramètres globaux) servent alors à gérer l’enregistrement des détails des appels à Redmond.

Vous pouvez créer des paramètres de configuration de CDR à l’aide du panneau de configuration de Lync Server ou de l’applet [de commande New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) . Vous pouvez utiliser le panneau de configuration de Lync Server ou l’applet de commande [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) pour modifier les paramètres existants. Si vous utilisez le panneau de configuration de Lync Server pour créer ou modifier des paramètres, les options suivantes sont disponibles :


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


<div>


> [!NOTE]  
> Les applets de commande New-CsCdrConfiguration et Set-CsCdrConfiguration incluent des options supplémentaires qui ne sont pas disponibles dans le panneau de configuration de Lync Server. Pour plus d’informations, reportez-vous à la rubrique <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">nouvelle-CsCdrConfiguration</A> et aux rubriques d’aide de <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> .



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a>Pour créer des paramètres de configuration de CDR en utilisant le panneau de configuration de Lync Server

1.  Dans le panneau de configuration de Lync Server, cliquez sur **surveillance et archivage**.

2.  Dans l’onglet **enregistrement des détails des appels** , cliquez sur **nouveau**.

3.  Dans la boîte de dialogue **Sélectionner un site**, indiquez le site où les nouveaux paramètres de configuration doivent être créés. Si la boîte de dialogue est vide, cela indique qu’une collection de paramètres de configuration d’enregistrement des détails des appels a déjà été affectée à tous vos sites. Chaque site ne peut recevoir qu’une seule collection. Vous pouvez dans ce cas supprimer puis recréer les paramètres ou modifier simplement les paramètres existants.

4.  Dans la boîte de dialogue **Nouveau paramètre d’enregistrement des détails des appels (CDR)**, sélectionnez les options voulues, puis cliquez sur **Valider**.

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a>Pour modifier les paramètres de configuration de CDR existants en utilisant le panneau de configuration de Lync Server

1.  Dans le panneau de configuration de Lync Server, cliquez sur **surveillance et archivage**.

2.  Double-cliquez sur la collection de paramètres à modifier, ou sélectionnez la collection, cliquez sur **Modifier**, puis sur **Afficher les détails**. Sachez que vous ne pouvez modifier qu’une seule collection à la fois. Pour modifier plusieurs collections, utilisez plutôt Lync Server Management Shell.

3.  Dans la boîte de dialogue **Modifier le paramètre de l’enregistrement des détails des appels**, sélectionnez les options voulues, puis cliquez sur **Valider**.

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Création de paramètres de configuration de CDR à l’aide d’applets de cmdlet Windows PowerShell

Vous pouvez créer des paramètres de configuration de CDR en utilisant Windows PowerShell et l’applet **de nouvelle applet de nouveau-CsCdrConfiguration** . Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>Pour créer une collection de paramètres de configuration d’enregistrement des détails des appels

  - La commande crée une collection de paramètres de configuration pour l’enregistrement des détails des appels qui s’applique au site Redmond :
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>Pour créer une collection de paramètres de configuration d’enregistrement des détails des appels qui désactivent l’enregistrement des détails des appels

  - Comme aucun paramètre (autre que celui obligatoire sur l’identité) n’a été précisé dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés. Pour créer des paramètres qui font appel à d’autres valeurs de propriétés, incluez simplement le paramètre approprié et sa valeur. Par exemple, pour créer une collection de paramètres de configuration des détails des appels, l’autorisation de la désactivation de l’enregistrement des détails des appels fait appel par défaut à une commande comme celle-ci :
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>Pour spécifier plusieurs valeurs de propriétés pendant la création d’une collection de paramètres de configuration d’enregistrement des détails des appels

  - Vous pouvez modifier plusieurs valeurs de propriétés en incluant plusieurs paramètres. Par exemple, cette commande configure les nouveaux paramètres pour conserver les enregistrements des détails des appels pendant 30 jours et les rapports d’erreur 90 jours :
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de [nouvelle-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>


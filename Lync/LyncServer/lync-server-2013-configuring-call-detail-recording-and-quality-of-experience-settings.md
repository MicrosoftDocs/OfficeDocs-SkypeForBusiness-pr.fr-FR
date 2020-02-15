---
title: Configuration des paramètres d’enregistrement des détails des appels et de qualité de l’expérience
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring call detail recording and Quality of Experience settings
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204621(v=OCS.15)
ms:contentKeyID: 48183223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8382d95ebc1c90a46ab1edee8248b7892e297ea2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-call-detail-recording-and-quality-of-experience-settings-in-lync-server-2013"></a>Configuration des paramètres d’enregistrement des détails des appels et de qualité de l’expérience dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-17_

Une fois que vous avez associé un magasin de surveillance à un pool frontal, configurez le magasin de surveillance, puis installez et configurez SQL Server Reporting Services et configurez les rapports de surveillance pour gérer les enregistrements des détails des appels et la qualité de l’expérience (QoE). surveillance à l’aide de Lync Server Management Shell. Les applets de commande Lync Server Management Shell vous permettent d’activer et de désactiver la surveillance des enregistrements des détails des appels et/ou QoE pour un site particulier ou pour l’ensemble de votre déploiement Lync Server ; Cela peut être réalisé à l’aide d’une commande simple, comme suit :

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

Lorsque vous installez Microsoft Lync Server 2013, vous installez également une collection prédéfinie de paramètres de configuration globaux pour les enregistrements des détails des appels et QoE. Les valeurs par défaut de certains des paramètres les plus couramment utilisés par l’enregistrement des détails des appels sont indiquées dans le tableau suivant :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Propriété</th>
<th>Description</th>
<th>Valeur par défaut</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableCDR</p></td>
<td><p>Indique si l’enregistrement des détails des appels est activé ou non. Si la valeur est True, tous les enregistrements CDR sont collectés et enregistrés dans la base de données de surveillance.</p></td>
<td><p>Vrai</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>Indique si les enregistrements des détails des appels doivent être périodiquement supprimés de la base de données. Si la valeur est définie sur True, les enregistrements sont supprimés après la période spécifiée par les propriétés KeepCallDetailForDays (pour les enregistrements CDR) et KeepErrorReportForDays (pour les erreurs CDR). Si la valeur est définie sur False, les enregistrements CDR sont conservés indéfiniment.</p></td>
<td><p>Vrai</p></td>
</tr>
<tr class="odd">
<td><p>KeepCallDetailForDays</p></td>
<td><p>Indique le nombre de jours durant lesquels les enregistrements CDR sont conservés dans la base de données. Tout enregistrement plus ancien que le nombre de jours spécifié est automatiquement supprimé. Mais pour cela, la purge doit être activée.</p>
<p>Vous pouvez définir la propriété KeepCallDetailForDays sur n’importe quelle valeur entière comprise entre 1 et 2562 jours (environ 7 ans).</p></td>
<td><p>60 jours</p></td>
</tr>
<tr class="even">
<td><p>KeepErrorReportForDays</p></td>
<td><p>Indique le nombre de jours pendant lesquels les rapports d’erreurs CDR sont conservés ; tous les rapports plus anciens que le nombre spécifié de jours sont automatiquement supprimés. Les rapports d’erreurs CDR sont des rapports de diagnostic téléchargés par des applications clientes telles que Microsoft Lync 2013.</p>
<p>Vous pouvez définir cette propriété sur n’importe quelle valeur entière comprise entre 1 et 2562.</p></td>
<td><p>60 jours</p></td>
</tr>
</tbody>
</table>


De même, les valeurs par défaut pour les paramètres de la qualité de l’expérience (QoE) sélectionnés sont indiquées dans ce tableau :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Propriété</th>
<th>Description</th>
<th>Valeur par défaut</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableQoE</p></td>
<td><p>Indique si la surveillance QoE est activée ou non. Si la valeur est True, tous les enregistrements QoE sont collectés et enregistrés dans la base de données de surveillance.</p></td>
<td><p>Vrai</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>Indique si les enregistrements QoE doivent être périodiquement supprimés de la base de données. Si la valeur est True, les enregistrements sont supprimés après la période spécifiée par la propriété KeepQoEDataForDays. Si la valeur est False, les enregistrements QoE sont conservés indéfiniment.</p></td>
<td><p>Vrai</p></td>
</tr>
<tr class="odd">
<td><p>KeepQoEDataForDays</p></td>
<td><p>Indique le nombre de jours durant lesquels les enregistrements QoE sont conservés dans la base de données. Tout enregistrement plus ancien que le nombre de jours spécifié est automatiquement supprimé. Mais pour cela, la purge doit être activée.</p>
<p>KeepCallDetailForDays peut être défini sur n’importe quelle valeur entière comprise entre 1 et 2562 jours.</p></td>
<td><p>60 jours</p></td>
</tr>
</tbody>
</table>


Si vous devez modifier ces paramètres globaux, vous pouvez pour cela utiliser les applets de commande Set-CsCdrConfiguration et Set-CsQoEConfiguration. Par exemple, cette commande (qui s’exécute depuis Lync Server Management Shell) désactive la surveillance CDR au niveau global ; il suffit pour cela de définir la propriété EnableCDR sur False ($False):

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

Notez que le fait de désactiver la surveillance ne dissocie pas le magasin d’analyse du pool frontal, ni ne désinstalle et n’a un impact sur la base de données de surveillance principale. Lorsque vous utilisez Lync Server Management Shell pour désactiver la surveillance des enregistrements des détails des appels ou des données QoE, vous empêchez temporairement Lync Server de collecter et d’archiver les données d’analyse. Pour reprendre la collecte et l’archivage des données de l’enregistrement CDR, il vous suffit de redéfinir la propriété EnableCDR sur True ($True):

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

De même, cette commande désactive la purge des enregistrements QoE globaux :

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

Outre les paramètres globaux, les paramètres de configuration CDR et QoE peuvent être assignés pour un site. Cela offre plus de flexibilité pour la gestion de la surveillance ; par exemple, un administrateur peut activer la surveillance CDR pour le site de Redmond et la désactiver pour le site de Dublin. Pour créer de nouveaux paramètres de configuration CDR pour un site, utilisez une commande similaire à celle-ci :

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

Gardez à l’esprit que les paramètres configurés pour un site prévalent sur les paramètres globaux configurés. Supposons, par exemple, que la surveillance CDR soit activée globalement, mais désactivée pour un site (le site de Redmond). Dans ce cas, les informations de l’enregistrement des détails des appels ne seront pas archivées pour les utilisateurs du site de Redmond mais elles le seront pour les utilisateurs des autres sites (c’est-à-dire, les utilisateurs gérés par les paramètres globaux et non par les paramètres du site de Redmond).

Pour créer de nouveaux paramètres QoE pour un site, il suffit d’utiliser une commande similaire à la commande suivante :

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

Pour plus d’informations, tapez les commandes suivantes dans Lync Server Management Shell :

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

</div>

<span> </span>

</div>

</div>

</div>


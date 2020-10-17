---
title: 'Lync Server 2013 : création des paramètres de configuration de la qualité de l’expérience'
description: 'Lync Server 2013 : créez des paramètres de configuration de la qualité de l’expérience.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Quality of Experience configuration settings
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48184357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 279265f396fc8fcbfba80d195fc587924a2979f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562190"
---
# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a>Créer des paramètres de configuration de qualité de l’expérience dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Les mesures de la qualité de l’expérience (QoE) effectuent le suivi de la qualité des appels audio et vidéo dans votre organisation, y compris le nombre de paquets réseau perdus, le bruit de fond et le montant de « gigue » (différences de retard des paquets). Ces mesures sont stockées dans une base de données distincte des autres données (telles que les enregistrements des détails des appels), ce qui permet d’activer et de désactiver l’enregistrement QoE indépendamment de l’enregistrement des autres données.

Lorsque vous installez Microsoft Lync Server 2013, une seule collection globale de paramètres de configuration QoE est créée pour vous. Les administrateurs peuvent aussi créer des paramètres personnalisés sur l’étendue du site. Chaque fois que ces paramètres étendus aux sites sont utilisés, ils ont priorité sur les paramètres globaux. Par exemple, si vous créez des paramètres étendus au site pour le site Redmond, ceux-ci (et non les paramètres globaux) sont utilisés pour gérer la qualité de l’expérience à Redmond.

Les paramètres de configuration QoE peuvent être créés à l’aide du panneau de configuration Lync Server ou de la cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) . Si vous utilisez le panneau de configuration Lync Server pour créer de nouveaux paramètres, les options suivantes sont disponibles :


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
<td><p>Identité</p></td>
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


<div>


> [!NOTE]  
> L’applet de commande New-CsQoEConfiguration inclut des options supplémentaires qui ne sont pas disponibles dans le panneau de configuration Lync Server. Pour plus d’informations, consultez la rubrique d’aide <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> .



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a>Pour créer des paramètres de configuration QoE à l’aide du panneau de configuration Lync Server

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.

4.  Dans la page **Données de qualité de l’expérience**, cliquez sur **Nouveau**.

5.  Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit être appliquée, puis cliquez sur **OK**.

6.  Dans **Nouveau paramètre de qualité de l’expérience**, procédez comme suit :
    
      - Sélectionnez **Activer la surveillance des données de QoE** pour activer la surveillance.
    
      - Sélectionnez **Activer le vidage des données de QoE** pour activer le vidage.
    
      - Dans **Conserver les données QoE pendant la durée maximale (jours)**, sélectionnez le nombre maximum de jours de rétention des enregistrements QoE.

7.  Cliquez sur **Valider**.

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Création de paramètres de configuration QoE à l’aide d’applets de commande Windows PowerShell

Vous pouvez créer des paramètres de configuration QoE à l’aide de Windows PowerShell et de l’applet de commande New-CsQoEConfiguration. Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>Pour créer une collection de paramètres de configuration QoE

  - Cette commande crée une collection de paramètres de configuration QoE qui sont appliqués au site Redmond :
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Pour créer une collection de paramètres de configuration QoE dans laquelle la surveillance QoE est désactivée

  - Étant donné qu’aucun paramètre (à l’exception du paramètre Identity obligatoire) n’a été spécifié dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés. Pour créer des paramètres qui utilisent des valeurs de propriété différentes, incluez simplement le paramètre approprié et la valeur du paramètre. Par exemple, pour créer une collection de paramètres de configuration de qualité de l’expérience qui, par défaut, permet de désactiver enregistrement de données QoE, utilisez une commande semblable à celle-ci :
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>Pour spécifier plusieurs valeurs de propriété lors de création d’une collection de paramètres de configuration QoE

  - Vous pouvez spécifier plusieurs valeurs de propriétés en incluant plusieurs paramètres. Par exemple, cette commande configure les nouveaux paramètres de manière à conserver les données QoE pendant 30 jours et à vider les anciennes données à 03:00 :
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à la cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>


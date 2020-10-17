---
title: 'Lync Server 2013 : configuration de voix entreprise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca998a723e4ef84fc1c203d6eddc5f9016f28739
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532551"
---
# <a name="configuring-enterprise-voice-in-lync-server-2013"></a>Configuration de voix entreprise dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-12_

Pour déployer voix entreprise, vous devez configurer les éléments suivants :

  - Créer une jonction

  - Définir une stratégie de voix

  - Définition d’un itinéraire des communications vocales

  - Activer les utilisateurs pour voix entreprise

<div>

## <a name="create-a-trunk"></a>Créer une jonction

Vous devez définir des jonctions dans votre déploiement voix entreprise. Pour le routage des Location-Based, vous devez créer une configuration de jonction par jonction. À l’aide du générateur de topologie Lync Server, définissez vos jonctions et utilisez la commande Lync Server Windows PowerShell, New-applet cstrunkconfiguration ou le panneau de configuration Lync Server pour définir les configurations de jonction correspondantes. Pour plus d’informations sur l’activation du routage des Location-Based sur les configurations de jonctions, consultez la section relative à l’activation du routage des Location-Based sur les jonctions dans la rubrique, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md). Pour cet exemple, le tableau suivant illustre les jonctions utilisées dans ce scénario.

Pour plus d’informations, reportez-vous à la rubrique [define Additional jonctions in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom de la jonction</th>
<th>Type du système</th>
<th>Nom</th>
<th>Emplacement</th>
<th>Serveur de médiation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Jonction 1 DEL-GW</p></td>
<td><p>Passerelle PSTN</p></td>
<td><p>DEL-GW</p></td>
<td><p>Delhi</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Jonction 2 HYD-GW</p></td>
<td><p>Passerelle PSTN</p></td>
<td><p>HYD-GW</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="odd">
<td><p>Jonction 3 DEL-PBX</p></td>
<td><p>PBX</p></td>
<td><p>DEL-PBX</p></td>
<td><p>Delhi</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Jonction 4 HYD-PBX</p></td>
<td><p>PBX</p></td>
<td><p>HYD-PBX</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a>Définit les stratégies de voix

Vous devez définir des stratégies de voix pour votre déploiement voix entreprise. Définir une stratégie de voix pour appliquer des restrictions de routage Location-Based à un sous-ensemble d’utilisateurs si seul un sous-ensemble de ces derniers est requis pour utiliser le routage de Location-Based. Pour cet exemple, le tableau suivant illustre les stratégies de voix utilisées dans ce scénario. Seuls les paramètres spécifiques à Location-Based routage sont inclus dans le tableau à des fins d’illustration.

Pour plus d’informations, reportez-vous à la rubrique [Configuration des stratégies de voix et des enregistrements d’utilisation RTC pour autoriser les fonctionnalités d’appel et les privilèges dans Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Stratégie de voix 1</th>
<th>Stratégie de voix 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ID de stratégie de voix</p></td>
<td><p>Stratégie de voix de Delhi</p></td>
<td><p>Stratégie de voix Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Utilisations RTC</p></td>
<td><p>Utilisation de Delhi, utilisation de PBX del, utilisation de PBX HYD</p></td>
<td><p>Utilisation de Hyderabad, utilisation de la HYD PBX, utilisation de PBX del</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>False</p></td>
<td><p>False</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a>Définir les itinéraires des communications vocales

Vous devez définir des itinéraires de communications vocales pour votre déploiement voix entreprise. Pour cet exemple, le tableau suivant illustre les itinéraires des communications vocales utilisés dans ce scénario. Seuls les paramètres spécifiques à Location-Based routage sont inclus dans le tableau à des fins d’illustration.

Pour plus d’informations, reportez-vous à la rubrique [Configuration des itinéraires des communications vocales pour les appels sortants dans Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Itinéraire des communications vocales 1</th>
<th>Itinéraire des communications vocales 2</th>
<th>Itinéraire des communications vocales 3</th>
<th>Itinéraire des communications vocales 4</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nom</p></td>
<td><p>Itinéraire de l’Delhi</p></td>
<td><p>Itinéraire Hyderabad</p></td>
<td><p>Itinéraire de la del PBX</p></td>
<td><p>Itinéraire HYD PBX</p></td>
</tr>
<tr class="even">
<td><p>Utilisations RTC</p></td>
<td><p>Utilisation de Delhi</p></td>
<td><p>Utilisation de Hyderabad</p></td>
<td><p>Utilisation de PBX del</p></td>
<td><p>Utilisation de la HYD PBX</p></td>
</tr>
<tr class="odd">
<td><p>Urbain</p></td>
<td><p>Jonction 1 DEL-GW</p></td>
<td><p>Jonction 2 HYD-GW</p></td>
<td><p>Jonction 3 DEL-PBX</p></td>
<td><p>Jonction 4 HYD-PBX</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a>Activer les utilisateurs pour voix entreprise

Activez les utilisateurs pour voix entreprise et affectez-leur une stratégie de voix que vous avez définie précédemment. Pour cet exemple, le tableau suivant illustre l’affectation utilisée dans ce scénario. Seuls les paramètres spécifiques à Location-Based routage sont inclus dans le tableau à des fins d’illustration.

Pour plus d’informations, consultez la rubrique [activation des utilisateurs pour voix entreprise dans Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Utilisateurs situés à l’adresse de Delhi</th>
<th>Utilisateurs situés dans Hyderabad</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Stratégie de voix associée</p></td>
<td><p>Stratégie de voix de Delhi</p></td>
<td><p>Stratégie de voix Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Exemples d’utilisateurs</p></td>
<td><p>DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</p></td>
<td><p>HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration du routage des Location-Based dans Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


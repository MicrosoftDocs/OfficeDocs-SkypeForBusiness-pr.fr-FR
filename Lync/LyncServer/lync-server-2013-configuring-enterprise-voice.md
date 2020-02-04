---
title: 'Lync Server 2013 : configuration d’Enterprise Voice'
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
ms.openlocfilehash: 9d6bf9f79725f1f4812ac1e1c1c3c0e3217b939b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a>Configuration d’Enterprise Voice dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-12_

Pour déployer Enterprise Voice, vous devez configurer les éléments suivants :

  - Créer un Trunk

  - Définir une politique vocale

  - Définir une gamme vocale

  - Enable Users for Enterprise Voice

<div>

## <a name="create-a-trunk"></a>Créer un Trunk

Vous devez définir des Trunks dans votre déploiement voix entreprise. Pour le routage basé sur l’emplacement, vous devez créer une configuration de Trunk par Trunk. Utilisez le générateur de topologie de serveur Lync pour définir vos Trunks, puis utilisez la commande Windows PowerShell de Lync Server, le nouveau-CsTrunkConfiguration ou le panneau de configuration de Lync Server pour définir les configurations de Trunk correspondantes. Pour plus d’informations sur l’activation du routage par emplacement sur des configurations de Trunk, reportez-vous à la section permettre le routage par emplacement vers des lignes de routage dans [Lync Server 2013](lync-server-2013-enabling-location-based-routing.md). Pour cet exemple, le tableau ci-dessous illustre les Trunks utilisés dans ce scénario.

Pour plus d’informations, reportez-vous à la section [définir des lignes supplémentaires dans le générateur de topologie de Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).


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
<th>Nom du Trunk</th>
<th>Type de système</th>
<th>Nom</th>
<th>Lieu</th>
<th>serveur de médiation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Trunk 1 DEL-GW</p></td>
<td><p>Passerelle RTC</p></td>
<td><p>DEL-GW</p></td>
<td><p>Delhi</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Trunk 2 HYD-GW</p></td>
<td><p>Passerelle RTC</p></td>
<td><p>HYD-GW</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="odd">
<td><p>Trunk 3 DEL-PBX</p></td>
<td><p>Private</p></td>
<td><p>DEL-PBX</p></td>
<td><p>Delhi</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Trunk 4 HYD-PBX</p></td>
<td><p>Private</p></td>
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

## <a name="defines-voice-policies"></a>Définit les stratégies vocales

Vous devez définir des politiques vocales pour le déploiement de votre voix entreprise. Définissez une stratégie vocale pour appliquer des restrictions de routage basées sur les emplacements à un sous-ensemble d’utilisateurs, si seul un sous-ensemble de ces derniers est requis pour utiliser le routage basé sur l’emplacement. Pour cet exemple, le tableau ci-dessous illustre les stratégies vocales utilisées dans ce scénario. Seuls les paramètres spécifiques au routage de géolocalisation sont inclus dans la table à des fins d’illustration.

Pour plus d’informations, reportez-vous [à configuration des stratégies de voix et des enregistrements d’utilisation RTC pour autoriser les fonctionnalités et privilèges d’utilisation dans Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Politique vocale 1</th>
<th>Politique vocale 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ID de la stratégie vocale</p></td>
<td><p>Politique vocale de Delhi</p></td>
<td><p>Politique vocale Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Usages RTC</p></td>
<td><p>Utilisation de Delhi, utilisation de PBX del, utilisation du PBX HYD</p></td>
<td><p>Utilisation de Hyderabad, utilisation de PBX HYD, utilisation de PBX del</p></td>
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

## <a name="define-voice-routes"></a>Définir des itinéraires vocaux

Vous devez définir des itinéraires vocaux pour votre déploiement voix entreprise. Pour cet exemple, le tableau ci-dessous illustre les itinéraires vocaux utilisés dans ce scénario. Seuls les paramètres spécifiques au routage de géolocalisation sont inclus dans la table à des fins d’illustration.

Pour plus d’informations, reportez-vous à la rubrique [Configuration des itinéraires vocaux pour les appels sortants dans Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).


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
<th>Route vocale 1</th>
<th>Route vocale 2</th>
<th>Route vocale 3</th>
<th>Route vocale 4</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nom</p></td>
<td><p>Delhi route</p></td>
<td><p>Route Hyderabad</p></td>
<td><p>Route PBX del</p></td>
<td><p>Route HYD PBX</p></td>
</tr>
<tr class="even">
<td><p>Usages RTC</p></td>
<td><p>L’utilisation de Delhi</p></td>
<td><p>Utilisation de Hyderabad</p></td>
<td><p>Utilisation de PBX del</p></td>
<td><p>Utilisation de HYD PBX</p></td>
</tr>
<tr class="odd">
<td><p>Jonction</p></td>
<td><p>Trunk 1 DEL-GW</p></td>
<td><p>Trunk 2 HYD-GW</p></td>
<td><p>Trunk 3 DEL-PBX</p></td>
<td><p>Trunk 4 HYD-PBX</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a>Enable Users for Enterprise Voice

Activez les utilisateurs pour voix entreprise et attribuez-leur une stratégie vocale déjà définie. Pour cet exemple, le tableau ci-dessous illustre l’affectation utilisée dans ce scénario. Seuls les paramètres spécifiques au routage de géolocalisation sont inclus dans la table à des fins d’illustration.

Pour plus d’informations, reportez-vous à [activer l’application voix entreprise dans Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Utilisateurs situés à Delhi</th>
<th>Utilisateurs situés dans Hyderabad</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Politique vocale associée</p></td>
<td><p>Politique vocale de Delhi</p></td>
<td><p>Politique vocale Hyderabad</p></td>
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


[Configuration du routage géodépendant dans Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


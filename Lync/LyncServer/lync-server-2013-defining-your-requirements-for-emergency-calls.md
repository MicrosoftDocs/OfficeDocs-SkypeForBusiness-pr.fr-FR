---
title: 'Lync Server 2013 : définition de la configuration requise pour les appels d’urgence'
description: 'Lync Server 2013 : définition de la configuration requise pour les appels d’urgence.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for emergency calls
ms:assetid: 5c12b517-9be6-41d0-83e2-11c78793620c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398404(v=OCS.15)
ms:contentKeyID: 48184276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d3c9908dcb4008a1442af86971e42eb4096a98b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545400"
---
# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a>Définition de la configuration requise pour les appels d’urgence dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-06_

Avant de commencer un déploiement de Microsoft Lync Server 2013 E9-1-1, vous devez d’abord pouvoir répondre aux questions détaillées dans les sections suivantes. La planification dont vous avez besoin dépend du type de solution E9-1-1 que vous choisissez de déployer : fournisseur de services E9-1-1 de jonction SIP ou numéro ELIN (Emergency Location Identification Number). Le tableau suivant identifie les sections du document de planification que vous devez consulter pour chacune de ces solutions.

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a>Étapes de planification par type de solution E9-1-1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Fournisseur de services de jonction SIP</th>
<th>Passerelle ELIN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Définition de l’étendue du déploiement E9-1-1 dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Définition de l’étendue du déploiement E9-1-1 dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Définition des éléments réseau utilisés pour déterminer l’emplacement dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Définition des éléments réseau utilisés pour déterminer l’emplacement dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Activation des utilisateurs pour E9-1-1 dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Activation des utilisateurs pour E9-1-1 dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Gestion des emplacements pour les fournisseurs de services de jonction SIP dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Gestion des emplacements pour les passerelles ELIN dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Définition de l’expérience utilisateur pour l’acquisition manuelle d’un emplacement dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Définition de l’expérience utilisateur pour l’acquisition manuelle d’un emplacement dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Conception de la jonction SIP pour E9-1-1 dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-including-the-security-desk.md">Inclusion du service de sécurité dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-including-the-security-desk.md">Inclusion du service de sécurité dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-location-policy.md">Définition de la stratégie d’emplacement pour Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Choix d’un fournisseur de services E9-1-1 pour Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">Affectation de l’étendue de la stratégie d’emplacement dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-location-policy.md">Définition de la stratégie d’emplacement pour Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">Affectation de l’étendue de la stratégie d’emplacement dans Lync Server 2013</a></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>Dans cette section

  - [Définition de l’étendue du déploiement E9-1-1 dans Lync Server 2013](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [Définition des éléments réseau utilisés pour déterminer l’emplacement dans Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [Activation des utilisateurs pour E9-1-1 dans Lync Server 2013](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [Gestion des emplacements pour les fournisseurs de services de jonction SIP dans Lync Server 2013](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [Gestion des emplacements pour les passerelles ELIN dans Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [Définition de l’expérience utilisateur pour l’acquisition manuelle d’un emplacement dans Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [Conception de la jonction SIP pour E9-1-1 dans Lync Server 2013](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [Inclusion du service de sécurité dans Lync Server 2013](lync-server-2013-including-the-security-desk.md)

  - [Choix d’un fournisseur de services E9-1-1 pour Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [Définition de la stratégie d’emplacement pour Lync Server 2013](lync-server-2013-defining-the-location-policy.md)

  - [Affectation de l’étendue de la stratégie d’emplacement dans Lync Server 2013](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


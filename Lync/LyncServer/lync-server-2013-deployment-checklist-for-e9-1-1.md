---
title: 'Lync Server 2013 : liste de vérification du déploiement pour E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48185655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a8bc7072cb1faa197f733d01eb545a964ed6612
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a>Liste de vérification du déploiement pour E9-1-1 dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-03_

Pour effectuer une planification efficace du système Enhanced 9-1-1 (E9-1-1), vous devez tenir compte des exigences de déploiement suivantes :

  - Conditions préalables au déploiement E9-1-1

  - Étapes nécessaires au déploiement E9-1-1

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a>Conditions préalables au déploiement E9-1-1

Avant de déployer E9-1-1, vous devez déjà avoir déployé vos serveurs internes Lync Server, notamment un magasin central de gestion, un pool frontal ou un serveur Standard Edition, un ou plusieurs serveurs de médiation ou pools de serveurs de médiation, ainsi que des clients Lync Server. Le déploiement E9-1-1 requiert également une jonction SIP vers un fournisseur de services E9-1-1 certifié ou une passerelle ELIN vers votre réseau téléphonique commuté (RTC). Lync Server prend en charge l’utilisation des fournisseurs de services E9-1-1 uniquement aux États-Unis.

</div>

<div>

## <a name="deployment-process"></a>Processus de déploiement

Le tableau suivant présente une vue d’ensemble du processus de déploiement E9-1-1. Pour plus d’informations sur les étapes de déploiement, voir [configure enhanced 9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) dans la documentation de déploiement.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Étapes</th>
<th>Rôles</th>
<th>Documentation de déploiement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configurer les utilisations de voix, itinéraires et configurations de jonction</p></td>
<td><ol>
<li><p>Créez un nouvel enregistrement d’utilisation PSTN. Son nom doit être identique à celui du paramètre <strong>Utilisation PSTN</strong> utilisé dans la stratégie d’emplacement.</p></li>
<li><p>Créez ou affectez un itinéraire de communications vocales à l’enregistrement d’utilisation PSTN créé dans l’étape précédente, puis pointez l’attribut de passerelle vers la jonction SIP E9-1-1 ou la passerelle ELIN.</p></li>
<li><p>Pour un fournisseur de services E9-1-1 de jonction SIP, définissez la jonction qui traitera les appels E9-1-1 via le protocole SIP pour transmettre les données PIDF-LO à l’aide de l’applet de commande <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong>.</p></li>
<li><p>Pour un fournisseur de services E9-1-1 de jonction SIP, vous pouvez éventuellement créer ou affecter un itinéraire PSTN local pour les appels qui ne sont pas traités par la jonction SIP du fournisseur de services E9-1-1. Cet itinéraire sera utilisé si la connexion au fournisseur de services E9-1-1 n’est pas disponible. Si cette option est prise en charge par votre fournisseur de services E9-1-1, affectez une règle de configuration de jonction à la passerelle qui traduit la chaîne de numérotation 911 en numéro SDA (sélection directe à l’arrivée) du centre d’intervention en cas d’appels d’urgence (ECRC) national/régional.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configuration d’un itinéraire des communications vocales E9-1-1 dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Créer des stratégies d’emplacement et les attribuer aux utilisateurs et aux sous-réseaux</p></td>
<td><ol>
<li><p>Vérifiez la stratégie d’emplacement globale.</p></li>
<li><p>Créez une stratégie d’emplacement avec une étendue de niveau utilisateur ; ou, si l’organisation a plusieurs sites avec différentes utilisations d’urgence, créez une stratégie d’emplacement avec une étendue de niveau réseau.</p></li>
<li><p>Attribuez la stratégie d’emplacement aux sites réseau.</p></li>
<li><p>Ajoutez les sous-réseaux appropriés au site réseau.</p></li>
<li><p>(Facultatif) Attribuez la stratégie d’emplacement aux stratégies d’utilisateur.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin (sauf pour la création de stratégies d’emplacement)</p></td>
<td><p><a href="lync-server-2013-create-location-policies.md">Créer des stratégies d’emplacement dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Ajouter une stratégie d’emplacement à un site réseau dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Associer des sous-réseaux à des sites réseau pour E9-1-1 dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurer la base de données d’emplacements</p></td>
<td><ol>
<li><p>Remplir la base de données avec une correspondance des éléments réseau avec les emplacements.</p></li>
<li><p>Pour les passerelles ELIN, ajoutez numéros à la &lt;colonne&gt; CompanyName.</p></li>
<li><p>Configurez la connexion au fournisseur de services E9-1-1 pour valider les adresses.</p></li>
<li><p>Validez les adresses avec le fournisseur de services E9-1-1.</p></li>
<li><p>Publier la base de données mise à jour.</p></li>
<li><p>Pour les passerelles ELIN, téléchargez les numéros d’identification de l’emplacement en cas d’urgence vers la base de données ALI (Automatic Location Identification) de votre opérateur RTC.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin</p></td>
<td><p><a href="lync-server-2013-configure-the-location-database.md">Configuration de la base de données d’emplacements dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurer les fonctionnalités avancées (facultatif)</p></td>
<td><ol>
<li><p>Configurez l’URL pour l’application SNMP.</p></li>
<li><p>Configurez l’URL pour l’emplacement du service d’informations d’emplacement secondaire.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-snmp-application.md">Configurer une application SNMP dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configurer un service d’informations d’emplacement secondaire dans Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


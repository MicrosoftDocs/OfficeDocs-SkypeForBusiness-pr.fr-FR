---
title: 'Lync Server 2013 : Liste de vérification du déploiement pour le service E9-1-1'
TOCTitle: Liste de vérification du déploiement pour le service E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398864(v=OCS.15)
ms:contentKeyID: 49298846
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Liste de vérification du déploiement pour le service E9-1-1 dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Pour effectuer une planification efficace du système Enhanced 9-1-1 (E9-1-1), vous devez tenir compte des exigences de déploiement suivantes :

  - Conditions préalables au déploiement E9-1-1

  - Étapes nécessaires au déploiement E9-1-1

## Conditions préalables au déploiement E9-1-1

Avant de déployer E9-1-1, vous devez avoir déployé vos serveurs internes Lync Server ( magasin central de gestion, pool de serveurs frontaux ou serveur Standard Edition Server, un ou plusieurs serveurs de médiation ou pools de serveurs de médiation, ainsi que les clients Lync Server). Le déploiement E9-1-1 requiert également une jonction SIP vers un fournisseur de services E9-1-1 certifié ou une passerelle ELIN vers votre réseau téléphonique commuté (RTC). Lync Server prend en charge l’utilisation de fournisseurs de services E9-1-1 aux États-Unis uniquement.

## Processus de déploiement

Le tableau ci-dessous présente une vue d’ensemble du processus de déploiement E9-1-1. Pour plus d’informations sur les étapes de déploiement, reportez-vous à [Configuration d’Enhanced 9-1-1 dans Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) dans la documentation de déploiement.


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
<li><p>Créez un nouvel enregistrement d’utilisation RTC. Son nom doit être identique à celui du paramètre <strong>Utilisation RTC</strong> utilisé dans la stratégie d’emplacement.</p></li>
<li><p>Créez ou affectez un itinéraire de communications vocales à l’enregistrement d’utilisation RTC créé dans l’étape précédente, puis pointez l’attribut de passerelle vers la jonction SIP E9-1-1 ou la passerelle ELIN.</p></li>
<li><p>Pour un fournisseur de services E9-1-1 de jonction SIP, définissez la jonction qui traitera les appels E9-1-1 via le protocole SIP pour transmettre les données PIDF-LO à l’aide de l’applet de commande <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong>.</p></li>
<li><p>Pour un fournisseur de services E9-1-1 de jonction SIP, vous pouvez éventuellement créer ou affecter un itinéraire RTC local pour les appels qui ne sont pas traités par la jonction SIP du fournisseur de services E9-1-1. Cet itinéraire sera utilisé si la connexion au fournisseur de services E9-1-1 n’est pas disponible. Si cette option est prise en charge par votre fournisseur de services E9-1-1, affectez une règle de configuration de jonction à la passerelle qui convertit la chaîne de numérotation 911 en numéro SDA (sélection directe à l’arrivée) du centre d’intervention en cas d’appels d’urgence (ECRC) national/régional.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configurer un itinéraire des communications vocales E9-1-1 dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Créer des stratégies d’emplacement et les attribuer aux utilisateurs et aux sous-réseaux</p></td>
<td><ol>
<li><p>Vérifiez la stratégie d’emplacement globale.</p></li>
<li><p>Créez une stratégie d’emplacement avec une étendue de niveau utilisateur ; ou, si l’organisation a plusieurs sites avec différentes utilisations d’urgence, créez une stratégie d’emplacement avec une étendue de niveau réseau.</p></li>
<li><p>Attribuez la stratégie d’emplacement aux sites réseau.</p></li>
<li><p>Ajoutez les sous-réseaux appropriés au site réseau.</p></li>
<li><p>(Facultatif) Attribuez la stratégie d’emplacement aux stratégies d’utilisateur.</p></li>
</ol>
<p></p></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin (sauf pour la création de stratégies d’emplacement)</p></td>
<td><p><a href="lync-server-2013-create-location-policies.md">Créer des stratégies d’emplacement dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Ajouter une stratégie d’emplacement à un site réseau</a></p>
<p><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Associer des sous-réseaux à des sites réseau pour E9-1-1</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurer la base de données d’emplacements</p></td>
<td><ol>
<li><p>Remplir la base de données avec une correspondance des éléments réseau avec les emplacements.</p></li>
<li><p>Pour les passerelles ELIN, ajoutez les numéros d’identification de l’emplacement en cas d’urgence à la colonne &lt;CompanyName&gt;.</p></li>
<li><p>Configurez la connexion au fournisseur de services E9-1-1 pour valider les adresses.</p></li>
<li><p>Validez les adresses avec le fournisseur de services E9-1-1.</p></li>
<li><p>Publier la base de données mise à jour.</p></li>
<li><p>Pour les passerelles ELIN, téléchargez les numéros d’identification de l’emplacement en cas d’urgence vers la base de données ALI (Automatic Location Identification) de votre opérateur RTC.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin</p></td>
<td><p><a href="lync-server-2013-configure-the-location-database.md">Configurer la base de données d’emplacements dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurer les fonctionnalités avancées (facultatif)</p></td>
<td><ol>
<li><p>Configurez l’URL pour l’application SNMP.</p></li>
<li><p>Configurez l’URL pour l’emplacement du service d’informations sur l’emplacement secondaire.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-snmp-application.md">Configurer une application SNMP</a></p>
<p><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configurer un service Informations d’emplacement secondaire</a></p></td>
</tr>
</tbody>
</table>


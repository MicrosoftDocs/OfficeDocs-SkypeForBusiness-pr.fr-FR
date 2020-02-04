---
title: 'Lync Server 2013 : ports et protocoles pour les serveurs internes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1001cce83d9b23125b177725c77715bd19a00e03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a>Ports et protocoles pour les serveurs internes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-04-06_

Cette section résume les ports et les protocoles utilisés par les serveurs, les équilibreurs de charge et les clients dans le déploiement de Lync Server.

<div>


> [!IMPORTANT]  
> Les clients Lync et Communicator intervenant dans le cadre d’une communication une à une, sont souvent désignés sous le nom d’égal à égal. Techniquement, les deux clients communiquent en une seule conversation avec l’unité de contrôle multipoint (IMMCU) de messagerie instantanée au milieu. IMMCU est un composant du serveur frontal. Le placement du IMMCU dans le flux de travail de communication requis autorise l’enregistrement des détails des appels et d’autres fonctionnalités que le serveur frontal autorise. La communication provient d’un port source dynamique du client vers le port de serveur frontal TLS/TCP/5061 (en partant du principe que l’utilisation de la sécurité de couche de transport recommandée). Par conception, la communication d’égal à égal (et la messagerie instantanée à plusieurs parties) est possible uniquement lorsque Lync Server et IMMCU est actif et disponible.



</div>

<div>

## <a name="port-and-protocol-details"></a>Détails sur les ports et protocoles

<div>


> [!NOTE]  
> Le pare-feu Windows doit être en cours d’exécution avant que vous ne démarriez les services Lync Server sur un serveur, car c’est le cas lorsque Lync Server ouvre les ports requis dans le pare-feu.



</div>

Pour plus d’informations sur la configuration du pare-feu pour les composants Edge, voir [déterminer les exigences en matière de port et de pare-feu A/V externes pour Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

Le tableau suivant répertorie les ports qui doivent être ouverts sur chaque rôle serveur interne.

### <a name="required-server-ports-by-server-role"></a>Ports de serveurs requis (par rôle serveur)

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
<th>Rôle serveur</th>
<th>Nom du service</th>
<th>Port</th>
<th>Protocole</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tous les serveurs</p></td>
<td><p>SQL Browser</p></td>
<td><p>1434</p></td>
<td><p>UDP</p></td>
<td><p>Navigateur SQL pour la copie locale répliquée de la base de données centrale de la Banque d’administration.</p></td>
</tr>
<tr class="even">
<td><p>serveurs frontaux</p></td>
<td><p>Service frontal de Lync Server</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé facultativement par les serveurs Standard Edition Server et les serveurs frontaux pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.</p></td>
</tr>
<tr class="odd">
<td><p>serveurs frontaux</p></td>
<td><p>Service frontal de Lync Server</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Utilisé par les serveurs Standard Edition Server et les pools frontaux pour toutes les communications SIP internes entre serveurs (MTLS), pour les communications SIP entre serveurs et clients (TLS) et pour les communications SIP entre serveurs frontaux et serveurs de médiation (MTLS). Également utilisé pour communiquer avec le serveur de surveillance.</p></td>
</tr>
<tr class="even">
<td><p>serveurs frontaux</p></td>
<td><p>Service frontal de Lync Server</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>Utilisé pour la communication HTTPs entre le focus (composant serveur Lync qui gère l’état de la Conférence) et les serveurs individuels.</p>
<p>Ce port est également utilisé pour la communication TCP entre les appareils succursales Survivables et les serveurs frontaux.</p></td>
</tr>
<tr class="odd">
<td><p>serveurs frontaux</p></td>
<td><p>Service frontal de Lync Server</p></td>
<td><p>135</p></td>
<td><p>DCOM et appel de procédure distante (RPC)</p></td>
<td><p>Utilisé pour les opérations DCOM, telles que le déplacement des utilisateurs, la synchronisation du réplicateur d’utilisateurs et la synchronisation du carnet d’adresses.</p></td>
</tr>
<tr class="even">
<td><p>serveurs frontaux</p></td>
<td><p>Service de conférence par messagerie instantanée Lync Server</p></td>
<td><p>5062</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les demandes SIP entrantes dans le cadre de conférences de messagerie instantanée.</p></td>
</tr>
<tr class="odd">
<td><p>serveurs frontaux</p></td>
<td><p>Service de conférence Web Lync Server</p></td>
<td><p>8057</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Utilisé pour l’écoute des connexions PSOM (Persistent Shared Object Model) à partir d’un client.</p></td>
</tr>
<tr class="even">
<td><p>serveurs frontaux</p></td>
<td><p>Service de compatibilité des conférences Web de Lync Server</p></td>
<td><p>8058</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Utilisé pour écouter les connexions PSOM (persistent Shared Object mode) du client Live Meeting et des versions précédentes de Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>serveurs frontaux</p></td>
<td><p>Service de visioconférence Lync Server audio/vidéo</p></td>
<td><p>5063</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les demandes SIP entrantes dans le cadre de conférences audio/vidéo (A/V).</p></td>
</tr>
<tr class="even">
<td><p>serveurs frontaux</p></td>
<td><p>Service de visioconférence Lync Server audio/vidéo</p></td>
<td><p>57501-65535</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Plage de ports multimédias utilisée pour les conférences vidéo.</p></td>
</tr>
<tr class="odd">
<td><p>serveurs frontaux</p></td>
<td><p>Service de compatibilité Web de Lync Server</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
<td><p>Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS) lorsque HTTPS n’est pas utilisé.</p></td>
</tr>
<tr class="even">
<td><p>serveurs frontaux</p></td>
<td><p>Service de compatibilité Web de Lync Server</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS).</p></td>
</tr>
<tr class="odd">
<td><p>serveurs frontaux</p></td>
<td><p>Service de compatibilité Web de Lync Server</p></td>
<td><p>8080</p></td>
<td><p>TCP et HTTP</p></td>
<td><p>Utilisé par les composants web pour l’accès externe.</p></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux</p></td>
<td><p>Composant de serveur web</p></td>
<td><p>4443</p></td>
<td><p>HTTPS</p></td>
<td><p>Communications HTTPS (du proxy inverse) et HTTPS inter-pool frontal pour connexion à la découverte automatique.</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs frontaux</p></td>
<td><p>Composant de serveur web</p></td>
<td><p>8060</p></td>
<td><p>TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux</p></td>
<td><p>Composant de serveur web</p></td>
<td><p>8061</p></td>
<td><p>TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>serveurs frontaux</p></td>
<td><p>Composant des services de mobilité</p></td>
<td><p>5086</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Port SIP utilisé pour les processus internes des services de mobilité.</p></td>
</tr>
<tr class="even">
<td><p>serveurs frontaux</p></td>
<td><p>Composant des services de mobilité</p></td>
<td><p>5087</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Port SIP utilisé pour les processus internes des services de mobilité.</p></td>
</tr>
<tr class="odd">
<td><p>serveurs frontaux</p></td>
<td><p>Composant des services de mobilité</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>serveurs frontaux</p></td>
<td><p>Service de surveillance des conférences de Lync Server (Conférence rendez-vous)</p></td>
<td><p>5064</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les demandes SIP entrantes dans le cadre de conférences rendez-vous.</p></td>
</tr>
<tr class="odd">
<td><p>serveurs frontaux</p></td>
<td><p>Service de surveillance des conférences de Lync Server (Conférence rendez-vous)</p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les demandes SIP entrantes pour le service d’assistance téléphonique (Conférence rendez-vous).</p></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</p></td>
<td><p>Service médiation de Lync Server</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal vers le serveur de médiation.</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</p></td>
<td><p>Service médiation de Lync Server</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.</p></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</p></td>
<td><p>Service médiation de Lync Server</p></td>
<td><p>5068</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</p></td>
<td><p>Service médiation de Lync Server</p></td>
<td><p>5081</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.</p></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</p></td>
<td><p>Service médiation de Lync Server</p></td>
<td><p>5082</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.</p></td>
</tr>
<tr class="odd">
<td><p>serveurs frontaux</p></td>
<td><p>Service de partage d’application Lync Server</p></td>
<td><p>5065</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les demandes d’écoute SIP entrantes dans le cadre du partage d’application.</p></td>
</tr>
<tr class="even">
<td><p>serveurs frontaux</p></td>
<td><p>Service de partage d’application Lync Server</p></td>
<td><p>49152-65535</p></td>
<td><p>TCP</p></td>
<td><p>Plage de ports multimédias utilisée pour le partage d’application.</p></td>
</tr>
<tr class="odd">
<td><p>serveurs frontaux</p></td>
<td><p>Service d’annonce Lync Server Conferencing</p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les demandes SIP entrantes pour le service d’annonce Lync Server Conferencing (c’est-à-dire pour la Conférence rendez-vous).</p></td>
</tr>
<tr class="even">
<td><p>serveurs frontaux</p></td>
<td><p>service de parcage d’appel Lync Server</p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les demandes SIP entrantes de l’application de parcage d’appel.</p></td>
</tr>
<tr class="odd">
<td><p>serveurs frontaux</p></td>
<td><p>Service de test audio de Lync Server</p></td>
<td><p>5076</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les demandes SIP entrantes du service de test audio.</p></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux</p></td>
<td><p>Non applicable</p></td>
<td><p>5066</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour la passerelle Enhanced 9-1-1 (E9-1-1) sortante.</p></td>
</tr>
<tr class="odd">
<td><p>serveurs frontaux</p></td>
<td><p>service Response Group Lync Server</p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les demandes SIP entrantes de l’application Response Group.</p></td>
</tr>
<tr class="even">
<td><p>serveurs frontaux</p></td>
<td><p>service Response Group Lync Server</p></td>
<td><p>8404</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Utilisé pour les demandes SIP entrantes de l’application Response Group.</p></td>
</tr>
<tr class="odd">
<td><p>serveurs frontaux</p></td>
<td><p>Service de stratégie de bande passante de Lync Server</p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour le contrôle d’admission des appels par le service de stratégie de bande passante, lui-même utilisé pour le trafic TURN Edge A/V.</p></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux</p></td>
<td><p>Service de stratégie de bande passante de Lync Server</p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour le contrôle d’admission des appels par le service de stratégie de bande passante de Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs frontaux dans lesquels réside le magasin de gestion central</p></td>
<td><p>Service de l’agent réplicateur de serveurs maîtres de Lync Server</p></td>
<td><p>445</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour transmettre les données de configuration du magasin central de gestion à des serveurs exécutant Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Tous les serveurs</p></td>
<td><p>SQL Browser</p></td>
<td><p>1434</p></td>
<td><p>UDP</p></td>
<td><p>Navigateur SQL pour la copie locale répliquée des données du magasin de gestion central dans l’instance SQL Server locale</p></td>
</tr>
<tr class="odd">
<td><p>Tous les serveurs internes</p></td>
<td><p>Divers</p></td>
<td><p>49152-57500</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Plage de ports multimédias utilisée pour les conférences audio sur tous les serveurs internes. Utilisé par tous les serveurs qui terminent les appels audio : serveurs front-end (pour le service de surveillance des conférences de Lync Server, service d’annonce de conférence Lync Server et service de visioconférence Lync Server) et serveur de médiation.</p></td>
</tr>
<tr class="even">
<td><p>Serveurs Office Web Apps Server</p></td>
<td></td>
<td><p>443</p></td>
<td></td>
<td><p>Utilisé par Lync Server 2013 pour la connexion à Office Web Apps Server.</p></td>
</tr>
<tr class="odd">
<td><p>directeurs</p></td>
<td><p>Service frontal de Lync Server</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé facultativement pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.</p></td>
</tr>
<tr class="even">
<td><p>directeurs</p></td>
<td><p>Service frontal de Lync Server</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>Communication entre serveurs frontaux et directeurs. Par ailleurs, le certificat client est publié (pour les serveurs frontaux) ou validé si le certificat client a déjà été publié.</p></td>
</tr>
<tr class="odd">
<td><p>directeurs</p></td>
<td><p>Service de compatibilité Web de Lync Server</p></td>
<td><p>80</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les communications initiales entre les directeurs et les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS). En fonctionnement normal, bascule vers le trafic HTTPS en utilisant le port 443 et le type de protocole TCP.</p></td>
</tr>
<tr class="even">
<td><p>Directeurs</p></td>
<td><p>Service de compatibilité Web de Lync Server</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>Utilisé pour les communications entre les directeurs et les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS).</p></td>
</tr>
<tr class="odd">
<td><p>directeurs</p></td>
<td><p>Service frontal de Lync Server</p></td>
<td><p>5061</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les communications internes entre serveurs et pour les connexions client.</p></td>
</tr>
<tr class="even">
<td><p>serveurs de médiation</p></td>
<td><p>Service médiation de Lync Server</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal.</p></td>
</tr>
<tr class="odd">
<td><p>serveurs de médiation</p></td>
<td><p>Service médiation de Lync Server</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Utilisé pour les demandes SIP entrantes de la passerelle PSTN.</p></td>
</tr>
<tr class="even">
<td><p>Serveurs de médiation</p></td>
<td><p>Service médiation de Lync Server</p></td>
<td><p>5068</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les demandes SIP entrantes de la passerelle PSTN.</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs de médiation</p></td>
<td><p>Service médiation de Lync Server</p></td>
<td><p>5070</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Utilisé pour les demandes SIP des serveurs frontaux.</p></td>
</tr>
<tr class="even">
<td><p>Serveur frontal de conversation permanente</p></td>
<td><p>SIP de conversation permanente</p></td>
<td><p>5041</p></td>
<td><p>TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Serveur frontal de conversation permanente</p></td>
<td><p>Windows Communication Foundation (WCF) de conversation permanente</p></td>
<td><p>881</p></td>
<td><p>TCP (TLS) et TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Serveur frontal de conversation permanente</p></td>
<td><p>Service de transfert de fichiers de conversation permanente</p></td>
<td><p>443</p></td>
<td><p>TCP (TLS)</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Certains scénarios de contrôle d’appel distant requièrent une connexion TCP entre le serveur frontal ou le directeur et le PBX. Même si Lync Server n’utilise plus 5060 port TCP, lors du déploiement d’un contrôle d’appel distant, vous créez une configuration de serveur approuvé, qui associe le nom de domaine complet du serveur de ligne RCC au port TCP utilisé par le serveur frontal ou le directeur pour se connecter au système PBX. Pour plus d’informations, voir l’applet de connexion <STRONG>CsTrustedApplicationComputer</STRONG> dans la documentation Lync Server Management Shell.



</div>

Pour les pools utilisant uniquement l’équilibrage de la charge matérielle (et non pas l’équilibrage de charge DNS), le tableau suivant indique les ports qui doivent ouvrir les programmes d’équilibrage de la charge matérielle.

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a>Ports des programmes d’équilibrage de la charge matérielle si uniquement l’équilibrage de la charge matérielle est utilisé

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Programme d’équilibrage de charge</th>
<th>Port</th>
<th>Protocole</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Programme d’équilibrage de charge du serveur frontal</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS)</p></td>
</tr>
<tr class="even">
<td><p>Programme d’équilibrage de charge du serveur frontal</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Programme d’équilibrage de charge du serveur frontal</p></td>
<td><p>135</p></td>
<td><p>DCOM et appel de procédure distante (RPC)</p></td>
</tr>
<tr class="even">
<td><p>Programme d’équilibrage de charge du serveur frontal</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Programme d’équilibrage de charge du serveur frontal</p></td>
<td><p>8080</p></td>
<td><p>TCP : récupération client/appareil du certificat racine à partir du serveur frontal, notamment clients et appareils authentifiés par NTLM</p></td>
</tr>
<tr class="even">
<td><p>Programme d’équilibrage de charge du serveur frontal</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Programme d’équilibrage de charge du serveur frontal</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (du proxy inverse)</p></td>
</tr>
<tr class="even">
<td><p>Programme d’équilibrage de charge du serveur frontal</p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Programme d’équilibrage de charge du serveur frontal</p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Programme d’équilibrage de charge du serveur frontal</p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Programme d’équilibrage de charge du serveur frontal</p></td>
<td><p>5076</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Programme d’équilibrage de charge du serveur frontal</p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Programme d’équilibrage de charge du serveur frontal</p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Programme d’équilibrage de charge du serveur frontal</p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Programme d’équilibrage de charge du serveur de médiation</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Programme d’équilibrage de charge du serveur frontal (si le pool exécute également le serveur de médiation)</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Programme d’équilibrage de charge du directeur</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>Programme d’équilibrage de charge du directeur</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Programme d’équilibrage de charge du directeur</p></td>
<td><p>5061</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Programme d’équilibrage de charge du directeur</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (du proxy inverse)</p></td>
</tr>
</tbody>
</table>


Vos pools frontaux et pools directeurs qui font appel à l’équilibrage de charge DNS doivent également déployer un programme d’équilibrage de la charge matérielle. Le tableau suivant affiche les ports qui doivent être ouverts sur ces programmes d’équilibrage de la charge matérielle.

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a>Ports des programmes d’équilibrage de la charge matérielle si l’équilibrage de charge DNS est utilisé

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Programme d’équilibrage de charge</th>
<th>Port</th>
<th>Protocole</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Programme d’équilibrage de charge du serveur frontal</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
</tr>
<tr class="even">
<td><p>Programme d’équilibrage de charge du serveur frontal</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Programme d’équilibrage de charge du serveur frontal</p></td>
<td><p>8080</p></td>
<td><p>TCP : récupération client/appareil du certificat racine à partir du serveur frontal, notamment clients et appareils authentifiés par NTLM</p></td>
</tr>
<tr class="even">
<td><p>Programme d’équilibrage de charge du serveur frontal</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (du proxy inverse)</p></td>
</tr>
<tr class="odd">
<td><p>Programme d’équilibrage de charge du directeur</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Programme d’équilibrage de charge du directeur</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (du proxy inverse)</p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a>Ports client requis

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Composant</th>
<th>Port</th>
<th>Protocole</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Clients</p></td>
<td><p>67/68</p></td>
<td><p>DHCP</p></td>
<td><p>Utilisé par Lync Server pour rechercher le nom de domaine complet (FQDN) du Bureau d’enregistrement (autrement dit, en cas d’échec de la configuration du service DNS SRV et de paramètres manuels).</p></td>
</tr>
<tr class="even">
<td><p>Clients</p></td>
<td><p>443</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Utilisé pour le trafic SIP client à serveur pour l’accès des utilisateurs externes.</p></td>
</tr>
<tr class="odd">
<td><p>Clients</p></td>
<td><p>443</p></td>
<td><p>TCP (PSOM/TLS)</p></td>
<td><p>Utilisé pour que les utilisateurs externes puissent accéder aux sessions de conférence Web.</p></td>
</tr>
<tr class="even">
<td><p>Clients</p></td>
<td><p>443</p></td>
<td><p>TCP (STUN/MSTURN)</p></td>
<td><p>Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (TCP).</p></td>
</tr>
<tr class="odd">
<td><p>Clients</p></td>
<td><p>3478</p></td>
<td><p>UDP (STUN/MSTURN)</p></td>
<td><p>Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (UDP).</p></td>
</tr>
<tr class="even">
<td><p>Clients</p></td>
<td><p>5061</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Utilisé pour le trafic SIP client à serveur pour l’accès des utilisateurs externes.</p></td>
</tr>
<tr class="odd">
<td><p>Clients</p></td>
<td><p>6891-6901</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour le transfert de fichiers entre clients Lync et clients précédents (clients de Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 et Live Communications Server 2005).</p></td>
</tr>
<tr class="even">
<td><p>Clients</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Plage de ports audio (au moins 20 ports requis).</p></td>
</tr>
<tr class="odd">
<td><p>Clients</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Plage de ports vidéo (au moins 20 ports requis).</p></td>
</tr>
<tr class="even">
<td><p>Clients</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP</p></td>
<td><p>Transfert de fichiers d’égal à égal. Pour le transfert de fichiers de conférence, les clients utilisent le modèle PSOM.</p></td>
</tr>
<tr class="odd">
<td><p>Clients</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP</p></td>
<td><p>Partage d’application.</p></td>
</tr>
<tr class="even">
<td><p>Téléphone de partie commune Aastra 6721ip</p>
<p>Téléphone de bureau Aastra 6725ip</p>
<p>Téléphone IP HP 4110 (téléphone de partie commune)</p>
<p>Téléphone IP HP 4120 (téléphone de bureau)</p>
<p>Téléphone de partie commune IP Polycom CX500</p>
<p>Téléphone de bureau IP Polycom CX600</p>
<p>Téléphone de bureau IP CX700</p>
<p>Téléphone de conférence IP Polycom CX3000</p></td>
<td><p>67/68</p></td>
<td><p>DHCP</p></td>
<td><p>Utilisé par les périphériques répertoriés pour trouver le certificat de serveur Lync, le nom de domaine complet de mise en service et le nom de domaine complet du Bureau d’enregistrement.</p></td>
</tr>
</tbody>
</table>


**\*** Pour configurer des ports spécifiques pour ces types de médias, utilisez l’applet de applet de CsConferencingConfiguration (ClientMediaPortRangeEnabled, ClientMediaPort et les paramètres ClientMediaPortRange).

<div>


> [!NOTE]  
> Les programmes Set pour les clients Lync créent automatiquement les exceptions de pare-feu du système d’exploitation requises sur l’ordinateur client.



</div>

<div>


> [!NOTE]  
> Les ports utilisés pour l’accès des utilisateurs externes sont nécessaires dans tout scénario où le client doit franchir le pare-feu de l’organisation (par exemple, les communications externes ou les réunions hébergées par d’autres organisations).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


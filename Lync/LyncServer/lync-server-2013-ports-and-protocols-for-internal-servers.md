---
title: 'Lync Server 2013 : ports et protocoles pour les serveurs internes'
TOCTitle: Ports et protocoles pour les serveurs internes
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398833(v=OCS.15)
ms:contentKeyID: 49298816
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ports et protocoles pour les serveurs internes dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-04-06_

Cette section résume les ports et protocoles utilisés par les serveurs, les programmes d’équilibrage de charge et les clients dans le cadre du déploiement de Lync Server.

> [!IMPORTANT]  
> La communication un-à-un entre des clients Lync et Communicator est souvent désignée comme communication d’égal à égal. D’un point de vue technique, les deux clients communiquent via une conversation un-à-un, avec l’unité de contrôle multipoint Messagerie instantanée au milieu (composant du serveur frontal.) Le fait de placer celle-ci dans le flux de communication requis active l’enregistrement des détails des appels et d’autres fonctionnalités activées par le serveur frontal. La communication est établie entre un port source dynamique sur le client et le port TLS/TCP/5061 du serveur frontal (en supposant que le protocole TLS recommandé est utilisé). Par défaut, la communication d’égal à égal (ainsi que la messagerie instantanée entre plusieurs utilisateurs) n’est possible que lorsque Lync Server et l’unité de contrôle multipoint Messagerie instantanée sont actives et disponibles.

## Détails sur les ports et protocoles

> [!NOTE]  
> Le pare-feu Windows doit être en cours d’exécution avant le démarrage des services Lync Server sur un serveur, car c’est à ce moment-là que Lync Server ouvre les ports requis dans le pare-feu.

Pour plus d’informations sur la configuration du pare-feu pour les composants Edge, voir [Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

Le tableau suivant répertorie les ports qui doivent être ouverts sur chaque rôle serveur interne.

### Ports de serveurs requis (par rôle serveur)

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
<td><p>SQL Browser pour la copie répliquée locale de la base de données du magasin central de gestion.</p></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux</p></td>
<td><p>Service frontal Lync Server</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé facultativement par les serveurs Standard Edition Server et les serveurs frontaux pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs frontaux</p></td>
<td><p>Service frontal Lync Server</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Utilisé par les serveurs Standard Edition Server et les pools frontaux pour toutes les communications SIP internes entre serveurs (MTLS), pour les communications SIP entre serveurs et clients (TLS) et pour les communications SIP entre serveurs frontaux et serveurs de médiation (MTLS). Également utilisé pour les communications avec le serveur de surveillance.</p></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux</p></td>
<td><p>Service frontal Lync Server</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>Utilisé pour les communications HTTPS entre le focus (composant Lync Server qui gère l’état des conférences) et les serveurs individuels.</p>
<p>Ce port est également utilisé pour les communications TCP entre les serveurs Survivable Branch Appliance et les serveurs frontaux.</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs frontaux</p></td>
<td><p>Service frontal Lync Server</p></td>
<td><p>135</p></td>
<td><p>DCOM et appel de procédure distante (RPC)</p></td>
<td><p>Utilisé pour les opérations DCOM, telles que le déplacement des utilisateurs, la synchronisation du réplicateur d’utilisateurs et la synchronisation du carnet d’adresses.</p></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux</p></td>
<td><p>Service de conférence de messagerie instantanée Lync Server</p></td>
<td><p>5062</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les demandes SIP entrantes dans le cadre de conférences de messagerie instantanée.</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs frontaux</p></td>
<td><p>Service de conférence web Lync Server</p></td>
<td><p>8057</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Utilisé pour l’écoute des connexions PSOM (Persistent Shared Object Model) à partir d’un client.</p></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux</p></td>
<td><p>Service de compatibilité de conférence web Lync Server</p></td>
<td><p>8058</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Utilisé pour l’écoute des connexions PSOM (Persistent Shared Object Model) à partir du client Live Meeting et des versions antérieures de Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs frontaux</p></td>
<td><p>Service de conférence audio/vidéo Lync Server</p></td>
<td><p>5063</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les demandes SIP entrantes dans le cadre de conférences audio/vidéo (A/V).</p></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux</p></td>
<td><p>Service de conférence audio/vidéo Lync Server</p></td>
<td><p>57501-65535</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Plage de ports multimédias utilisée pour les conférences vidéo.</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs frontaux</p></td>
<td><p>Service de compatibilité web Lync Server</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
<td><p>Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS) lorsque HTTPS n’est pas utilisé.</p></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux</p></td>
<td><p>Service de compatibilité web Lync Server</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS).</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs frontaux</p></td>
<td><p>Service de compatibilité web Lync Server</p></td>
<td><p>8080</p></td>
<td><p>TCP et HTTP</p></td>
<td><p>Utilisé par les composants web pour l’accès externe.</p></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux</p></td>
<td><p>Composant de serveur web</p></td>
<td><p>4443</p></td>
<td><p>HTTPS</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Serveurs frontaux</p></td>
<td><p>Composant de serveur web</p></td>
<td><p>8060</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux</p></td>
<td><p>Composant de serveur web</p></td>
<td><p>8061</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Serveurs frontaux</p></td>
<td><p>Composant des services de mobilité</p></td>
<td><p>5086</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Port SIP utilisé pour les processus internes des services de mobilité.</p></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux</p></td>
<td><p>Composant des services de mobilité</p></td>
<td><p>5087</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Port SIP utilisé pour les processus internes des services de mobilité.</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs frontaux</p></td>
<td><p>Composant des services de mobilité</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux</p></td>
<td><p>Service Intendant Conférence Lync Server (conférence rendez-vous)</p></td>
<td><p>5064</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les demandes SIP entrantes dans le cadre de conférences rendez-vous.</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs frontaux</p></td>
<td><p>Service Intendant Conférence Lync Server (conférence rendez-vous)</p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les demandes SIP entrantes pour Intendant (conférences rendez-vous).</p></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</p></td>
<td><p>Service de médiation Lync Server</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal vers le serveur de médiation.</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</p></td>
<td><p>Service de médiation Lync Server</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.</p></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</p></td>
<td><p>Service de médiation Lync Server</p></td>
<td><p>5068</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</p>
<p></p></td>
<td><p>Service de médiation Lync Server</p>
<p></p></td>
<td><p>5081</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.</p></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</p>
<p></p></td>
<td><p>Service de médiation Lync Server</p>
<p></p></td>
<td><p>5082</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs frontaux</p></td>
<td><p>Service de partage d’application Lync Server</p></td>
<td><p>5065</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les demandes d’écoute SIP entrantes dans le cadre du partage d’application.</p></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux</p></td>
<td><p>Service de partage d’application Lync Server</p></td>
<td><p>49152-65535</p></td>
<td><p>TCP</p></td>
<td><p>Plage de ports multimédias utilisée pour le partage d’application.</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs frontaux</p></td>
<td><p>Service d’annonce de conférence Lync Server</p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les demandes SIP entrantes du service d’annonce de conférence Lync Server (pour les conférences rendez-vous).</p></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux</p></td>
<td><p>Service de parcage d’appel Lync Server</p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les demandes SIP entrantes de l’application de parcage d’appel.</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs frontaux</p></td>
<td><p>Service de test audio Lync Server</p></td>
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
<td><p>Serveurs frontaux</p></td>
<td><p>Service Response Group Lync Server</p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les demandes SIP entrantes de l’application Response Group.</p></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux</p></td>
<td><p>Service Response Group Lync Server</p></td>
<td><p>8404</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Utilisé pour les demandes SIP entrantes de l’application Response Group.</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs frontaux</p></td>
<td><p>Service de stratégie de bande passante Lync Server</p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour le contrôle d’admission des appels par le service de stratégie de bande passante, lui-même utilisé pour le trafic TURN Edge A/V.</p></td>
</tr>
<tr class="even">
<td><p>Serveurs frontaux</p></td>
<td><p>Service de stratégie de bande passante Lync Server</p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour le contrôle d’admission des appels par le service de stratégie de bande passante Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs frontaux où réside le magasin central de gestion.</p></td>
<td><p>Service de l’agent réplicateur maître Lync Server</p></td>
<td><p>445</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour acheminer les données de configuration du magasin central de gestion vers des serveurs exécutant Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Tous les serveurs</p></td>
<td><p>SQL Browser</p></td>
<td><p>1434</p></td>
<td><p>UDP</p></td>
<td><p>SQL Browser pour la copie répliquée locale des données magasin central de gestion dans l’instance locale SQL Server.</p></td>
</tr>
<tr class="odd">
<td><p>Tous les serveurs internes</p></td>
<td><p>Divers</p></td>
<td><p>49152-57500</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Plage de ports multimédias utilisée pour les conférences audio sur tous les serveurs internes. Utilisé par tous les serveurs qui permettent le raccordement audio : serveurs frontaux (pour le service Intendant Conférence Lync Server, service d’annonce de conférence Lync Server et service de conférence audio/vidéo Lync Server) et serveur de médiation.</p></td>
</tr>
<tr class="even">
<td><p>Serveurs Office Web Apps Server</p></td>
<td><p></p></td>
<td><p>443</p></td>
<td><p></p></td>
<td><p>Utilisés par Lync Server 2013 pour se connecter au serveur Office Web Apps Server.</p></td>
</tr>
<tr class="odd">
<td><p>Directeurs</p></td>
<td><p>Service frontal Lync Server</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé facultativement pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.</p></td>
</tr>
<tr class="even">
<td><p>Directeurs</p></td>
<td><p>Service frontal Lync Server</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>Communication entre serveurs frontaux et directeurs. En outre, le certificat client est publié (dans les serveurs frontaux) ou validé s’il a déjà été publié.</p></td>
</tr>
<tr class="odd">
<td><p>Directeurs</p></td>
<td><p>Service de compatibilité web Lync Server</p></td>
<td><p>80</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les communications initiales entre les directeurs et les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS). En fonctionnement normal, bascule vers le trafic HTTPS en utilisant le port 443 et le type de protocole TCP.</p></td>
</tr>
<tr class="even">
<td><p>Directeurs</p></td>
<td><p>Service de compatibilité web Lync Server</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>Utilisé pour les communications entre les directeurs et les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS).</p></td>
</tr>
<tr class="odd">
<td><p>Directeurs</p></td>
<td><p>Service frontal Lync Server</p></td>
<td><p>5061</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les communications internes entre serveurs et pour les connexions client.</p></td>
</tr>
<tr class="even">
<td><p>Serveurs de médiation</p></td>
<td><p>Service de médiation Lync Server</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal.</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs de médiation</p></td>
<td><p>Service de médiation Lync Server</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Utilisé pour les demandes SIP entrantes de la passerelle PSTN.</p></td>
</tr>
<tr class="even">
<td><p>Serveurs de médiation</p></td>
<td><p>Service de médiation Lync Server</p></td>
<td><p>5068</p></td>
<td><p>TCP</p></td>
<td><p>Utilisé pour les demandes SIP entrantes de la passerelle PSTN.</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs de médiation</p></td>
<td><p>Service de médiation Lync Server</p></td>
<td><p>5070</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Utilisé pour les demandes SIP des serveurs frontaux.</p></td>
</tr>
<tr class="even">
<td><p>Serveur frontal de conversation permanente</p></td>
<td><p>SIP de conversation permanente</p></td>
<td><p>5041</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Serveur frontal de conversation permanente</p></td>
<td><p>Windows Communication Foundation (WCF) de conversation permanente</p></td>
<td><p>881</p></td>
<td><p>TCP (TLS) et TCP (MTLS)</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Serveur frontal de conversation permanente</p></td>
<td><p>Service de transfert de fichiers de conversation permanente</p></td>
<td><p>443</p></td>
<td><p>TCP (TLS)</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Certains scénarios de contrôle d’appel distant requièrent une connexion TCP entre le serveur frontal ou le directeur et le PBX. Bien que Lync Server n’utilise plus le port TCP 5060, au cours du déploiement du contrôle d’appel distant (RCC), vous créez une configuration de serveur approuvé qui associe le nom de domaine complet du serveur de ligne RCC au port TCP que le serveur frontal ou le directeur utilise pour assurer la connexion au système PBX. Pour plus d’informations, voir l’applet de commande <strong>CsTrustedApplicationComputer</strong> dans la documentation Lync Server Management Shell.

Pour les pools utilisant uniquement l’équilibrage de la charge matérielle (et non pas l’équilibrage de charge DNS), le tableau suivant indique les ports qui doivent ouvrir les programmes d’équilibrage de la charge matérielle.

### Ports des programmes d’équilibrage de la charge matérielle si uniquement l’équilibrage de la charge matérielle est utilisé

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
<td><p>TCP - Récupération client/périphérique du certificat racine depuis le serveur frontal – clients et périphériques authentifiés par NTLM</p></td>
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
<td><p>Programme d’équilibrage de charge du serveur frontal</p>
<p></p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Programme d’équilibrage de charge du serveur frontal</p>
<p></p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Programme d’équilibrage de charge du serveur frontal</p>
<p></p></td>
<td><p>5076</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Programme d’équilibrage de charge du serveur frontal</p>
<p></p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Programme d’équilibrage de charge du serveur frontal</p>
<p></p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Programme d’équilibrage de charge du serveur frontal</p>
<p></p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Programme d’équilibrage de charge du serveur de médiation</p>
<p></p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Programme d’équilibrage de charge du serveur frontal (si le pool exécute également le serveur de médiation)</p>
<p></p></td>
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
<td><p>Programme d’équilibrage de charge du directeur</p>
<p></p></td>
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

### Ports des programmes d’équilibrage de la charge matérielle si l’équilibrage de charge DNS est utilisé

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
<td><p>TCP - Récupération client/périphérique du certificat racine depuis le serveur frontal – clients et périphériques authentifiés par NTLM</p></td>
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


### Ports client requis

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
<td><p>Utilisé par Lync Server pour trouver le nom de domaine complet du serveur d’inscriptions (si le serveur DNS échoue et que les paramètres manuels ne sont pas configurés).</p></td>
</tr>
<tr class="even">
<td><p>Clients</p>
<p></p></td>
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
<td><p>Utilisé pour le transfert de fichiers entre les clients Lync et les clients antérieurs (clients de Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 et Live Communications Server 2005).</p></td>
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
<td><p>TCP/UDP</p>
<p></p></td>
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
<td><p>Utilisé par les périphériques répertoriés pour trouver le certificat Lync Server, le nom de domaine complet de provisionnement et le nom de domaine complet du serveur d’inscriptions.</p></td>
</tr>
</tbody>
</table>


**\*** Pour configurer des ports spécifiques pour ces types de média, utilisez l’applet de commande CsConferencingConfiguration (paramètres ClientMediaPortRangeEnabled, ClientMediaPort et ClientMediaPortRange).

> [!NOTE]  
> Les programmes définis pour les clients Lync créent automatiquement les exceptions requises du pare-feu du système d’exploitation sur l’ordinateur client.

> [!NOTE]  
> Les ports utilisés pour l’accès des utilisateurs externes sont nécessaires dans tout scénario où le client doit franchir le pare-feu de l’organisation (par exemple, les communications externes ou les réunions hébergées par d’autres organisations).

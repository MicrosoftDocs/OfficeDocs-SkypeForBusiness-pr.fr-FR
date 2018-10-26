---
title: Menaces fréquentes pour la sécurité dans l’informatique moderne
TOCTitle: Menaces fréquentes pour la sécurité dans l’informatique moderne
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56559394
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Menaces fréquentes pour la sécurité dans l’informatique moderne

 

_**Dernière rubrique modifiée :** 2015-03-09_

Lync Server 2013 étant un système de communication professionnel, vous devez être informé des atteintes les plus fréquentes à la sécurité susceptibles d’affecter son infrastructure et ses communications.

## Attaque par clé compromise

Une clé est un code ou un nombre secret utilisé pour chiffrer, déchiffrer ou valider des informations confidentielles. Deux clés de l’infrastructure à clé publique (PKI) sont particulièrement sensibles :

  - la clé privée que possède chaque détenteur de certificat ;

  - la clé de session, utilisée après l’identification et l’échange de clé de session entre les partenaires communiquant entre eux.

Une attaque par clé compromise se produit lorsqu’un intrus parvient à identifier la clé privée ou la clé de session. Lorsque l’intrus parvient à déterminer la clé, il s’en sert pour déchiffrer des données chiffrées, à l’insu de l’expéditeur des données.

Lync Server 2013 utilise les fonctionnalités de l’infrastructure à clé publique dans le système d’exploitation Windows Server pour protéger les données de clé utilisées pour le chiffrement des connexions TLS (Transport Layer Security). Les clés utilisées pour le chiffrement multimédia sont échangées via des connexions TLS.

## Attaque réseau par déni de service

Une *attaque par déni de service* se produit lorsqu’une personne malveillante empêche des utilisateurs valides de travailler et d’utiliser le réseau normalement. Pour ce faire, elle inonde le service avec des demandes légitimes qui submergent l’utilisation du service par les utilisateurs légitimes. Lors d’une attaque de ce type, la personne malveillante peut :

  - envoyer des données non valides à des applications et des services exécutés sur le réseau faisant l’objet de l’attaque, afin de perturber leur exécution normale ;

  - envoyer un volume de trafic important, de manière à surcharger le système jusqu’à ce que celui-ci cesse de fonctionner ou nécessite beaucoup de temps pour répondre aux demandes légitimes ;

  - masquer les signes d’attaque ;

  - empêcher les utilisateurs d’accéder aux ressources réseau.

## Attaque par écoute (Eavesdropping)

Une *attaque par écoute* peut se produire lorsqu’une personne malveillante parvient à accéder au chemin d’accès des données d’un réseau et qu’elle peut ainsi surveiller et lire le trafic. Cette attaque est également appelée *reniflage* (« sniffing ») ou *surveillance* (« snooping »). Si le trafic consiste en du texte simple, l’intrus peut lire le trafic lorsqu’il accède au chemin d’accès des données. Par exemple, une attaque peut être lancée en contrôlant un routeur sur le chemin de données.

La configuration par défaut recommandée pour le trafic au sein de Microsoft Lync Server 2013 consiste à utiliser MTLS (Mutual TLS) entre les serveurs approuvés et TLS entre le client et le serveur. Cette mesure de protection rend ce type d’attaque difficile, voire impossible, durant le laps de temps pendant lequel une conversation donnée peut être attaquée. Le protocole TLS authentifie toutes les parties et chiffre le trafic. Ceci n’empêche pas les attaques par écoute, mais l’intrus ne peut pas lire le trafic à moins que le chiffrement ne soit rompu.

Le protocole TURN (Traversal Using Relay NAT) n’exige pas que le trafic soit chiffré. Les informations acheminées sont protégées par l’intégrité des messages. Bien qu’elles puissent faire l’objet d’une attaque par écoute, les informations acheminées (autrement dit, les adresses IP et le port) peuvent être extraites directement, en observant simplement les adresses source et de destination des paquets. Le service Edge A/V s’assure que les données sont valides en vérifiant l’intégrité du message à l’aide d’une clé dérivée de plusieurs éléments, dont un mot de passe TURN, qui n’est jamais transmise en texte en clair. Si le protocole SRTP (Secure Real Time Protocol) est utilisé, le trafic multimédia est également chiffré.

## Usurpation d’identité (usurpation d’adresse IP)

On parle d’*usurpation d’identité* lorsqu’une personne malveillante parvient à déterminer et à utiliser l’adresse IP d’un réseau, d’un ordinateur ou d’un composant réseau, sans y avoir été autorisée. Si l’attaque réussit, l’intrus peut opérer comme s’il était l’utilisateur habituellement identifié par l’adresse IP. Dans le contexte de Microsoft Lync Server 2013, ce scénario se produit uniquement si l’administrateur a effectué les deux opérations suivantes :

  - configuré des connexions qui prennent uniquement en charge le protocole TCP (Transmission Control Protocol), ce qui n’est pas recommandé car les communications TCP ne sont pas chiffrées ;

  - marqué les adresses IP de ces connexions en tant qu’hôtes approuvés.

Ce problème est moins grave pour les connexions TLS (Transport Layer Security), car TLS authentifie toutes les parties et chiffre le trafic. L’utilisation du protocole TLS empêche une personne malveillante d‘usurper une adresse IP sur une connexion spécifique (par exemple, les connexions Mutual TLS). Toutefois, elle peut usurper l’adresse du serveur DNS utilisé par Lync Server 2013. Comme l’authentification est assurée à l’aide de certificats dans Lync, un intrus n’aurait pas de certificat valide nécessaire pour usurper l’identité d’une des parties dans la communication.

## Attaque de l’intercepteur (« man-in-the-middle »)

Une attaque de l’intercepteur se produit lorsqu’une personne malveillante redirige les communications entre deux utilisateurs via son propre ordinateur, à l’insu des deux participants. L’intrus peut surveiller et lire le trafic avant de l’acheminer vers le destinataire concerné. Chacun des utilisateurs envoie et reçoit du trafic vers/de l’intrus, alors qu’il pense communiquer avec l’utilisateur concerné uniquement. Cela peut se produire si une personne malveillante modifie les services de domaine Active Directory pour ajouter son serveur en tant que serveur approuvé, ou si elle modifie DNS (Domain Name System) pour faire en sorte que les clients se connectent au serveur via l’ordinateur de l’intrus à l’origine de l’attaque. Une attaque de l’intercepteur peut également affecter le trafic multimédia entre deux clients. Toutefois, dans Microsoft Lync Server 2013, les flux multimédias point à point sont chiffrés à l’aide de SRTP, avec des clés de chiffrement qui sont négociées entre les homologues à l’aide du protocole SIP (Session Initiation Protocol) sur TLS. Les serveurs tels que le serveur de conversation de groupe utilisent le protocole HTTPS pour sécuriser le trafic.

## Attaque par relecture RTP

Une *attaque par relecture* se produit lorsqu’une transmission multimédia valide entre deux correspondants est interceptée, puis retransmise à des fins malveillantes. L’utilisation de SRTP avec un protocole de signalisation sécurisé protège les transmissions contre les attaques par relecture. En effet, le destinataire est alors en mesure d’établir un index des paquets RTP déjà reçus et de comparer chaque nouveau paquet à ceux répertoriés dans l’index.

## Messages instantanés indésirables (Spim)

Le *spim* correspond à des messages instantanés commerciaux ou des demandes d’abonnement aux informations de présence non sollicités. S’il ne constitue pas à lui seul une menace envers le réseau, il peut néanmoins perturber les activités des utilisateurs et avoir un impact négatif sur la disponibilité des ressources et la production. Il représente donc un risque potentiel pour le réseau. Prenons le cas d’utilisateurs qui génèrent du spim en s’envoyant mutuellement des demandes. Un utilisateur peut en bloquer un autre pour ne plus recevoir de messages instantanés indésirables. Toutefois, dans le cas de la fédération, il peut s’avérer difficile de faire face à une attaque de spim coordonnée, à moins de désactiver la fédération pour le partenaire.

## Virus et vers

Un *virus* est une unité de code dont le seul rôle consiste à reproduire d’autres unités de code similaires. Pour fonctionner, un virus doit être hébergé dans un fichier, un courrier électronique ou un programme. Un *ver* est une unité de code programmée pour reproduire d’autres unités de code similaires. Toutefois, il n’est pas nécessaire qu’il soit hébergé. Les virus et les vers apparaissent principalement lors du transfert de fichiers entre clients ou lorsque d’autres utilisateurs transmettent des URL. Une fois qu’un virus se trouve sur votre ordinateur, il peut, par exemple, usurper votre identité et envoyer des messages instantanés à votre nom.

## Informations d’identification personnelle

Microsoft Lync Server 2013 peut publier sur un réseau public des informations susceptibles d’être associées à un utilisateur individuel. Ces informations appartiennent à deux catégories :

  - **Données de présence enrichie** Les données de présence enrichie sont des informations qu’un utilisateur peut, s’il le souhaite, partager via une liaison avec un partenaire fédéré ou avec des contacts, au sein d’une organisation. Elles ne sont pas partagées avec les utilisateurs d’un réseau public de messagerie instantanée. Selon les stratégies de groupe en vigueur et la configuration du client, l’administrateur système peut contrôler ces informations. Dans Lync Server 2013, le mode de confidentialité de présence enrichie peut être configuré pour un utilisateur individuel afin d’empêcher les utilisateurs Lync ne figurant pas dans sa liste de contacts de voir ses informations de présence. Le mode de confidentialité de présence enrichie n’empêche pas les utilisateurs de Microsoft Office Communicator 2007 et Microsoft Office Communicator 2007 R2 de voir les informations de présence d’un utilisateur. Pour plus d’informations, voir [Nouveautés pour les clients dans Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) dans la documentation de mise en route et [Configuration du mode de confidentialité améliorée de la présence](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) dans la documentation de déploiement.

  - **Données obligatoires** Les données obligatoires sont des données requises pour que le serveur ou le client s’exécute correctement. Elles ne sont PAS contrôlées par le client ou l’administrateur système. Elles sont requises au niveau du serveur ou du réseau à des fins de routage, de maintenance de l’état et de signalisation.

Les tableaux suivants répertorient les données exposées sur un réseau public.

### Données de présence enrichie

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Données divulguées</th>
<th>Paramètres possibles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Données personnelles</p></td>
<td><p>Nom, Fonction, Société, Adresse électronique, Fuseau horaire</p></td>
</tr>
<tr class="even">
<td><p>Numéros de téléphone</p></td>
<td><p>Bureau, Mobile, Domicile</p></td>
</tr>
<tr class="odd">
<td><p>Informations de calendrier</p></td>
<td><p>Libre/Occupé(e), notification d’absence du bureau, détails de réunion (pour les personnes ayant accès à votre calendrier)</p></td>
</tr>
<tr class="even">
<td><p>Statut de présence</p></td>
<td><p>Absent(e), Disponible, Occupé(e), Ne pas déranger, Hors connexion</p></td>
</tr>
</tbody>
</table>


### Données obligatoires

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Données divulguées</th>
<th>Exemples d’informations</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Adresse IP</p></td>
<td><p>Adresse réelle de l’ordinateur ou adresse traduite via NAT</p></td>
</tr>
<tr class="even">
<td><p>URI SIP</p></td>
<td><p>jeremylos@litwareinc.com</p></td>
</tr>
</tbody>
</table>


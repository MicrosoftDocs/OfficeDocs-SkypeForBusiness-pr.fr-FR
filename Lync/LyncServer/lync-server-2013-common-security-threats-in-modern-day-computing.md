---
title: 'Lync Server 2013 : menaces de sécurité courantes au sein de l’informatique moderne'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common security threats in modern day computing
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56708403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99e17f9f6dbba30697c72fecf77fbff4bfbdc003
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a>Menaces fréquentes pour la sécurité dans l’informatique moderne

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-09-10_

Dans la mesure où Lync Server 2013 est un système de communication d’entreprise, vous devez tenir compte des attaques courantes de sécurité qui pourraient affecter son infrastructure et ses communications.

<div>

## <a name="compromised-key-attack"></a>Attaque par clé compromise

Une clé est un code ou un nombre secret utilisé pour chiffrer, déchiffrer ou valider des informations confidentielles. Deux clés de l’infrastructure à clé publique (PKI) sont particulièrement sensibles :

  - la clé privée que possède chaque détenteur de certificat ;

  - la clé de session, utilisée après l’identification et l’échange de clé de session entre les partenaires communiquant entre eux.

Une attaque par clé compromise se produit lorsqu’un intrus parvient à identifier la clé privée ou la clé de session. Lorsque l’intrus parvient à déterminer la clé, il s’en sert pour déchiffrer des données chiffrées, à l’insu de l’expéditeur des données.

Lync Server 2013 utilise les fonctionnalités de PKI dans le système d’exploitation Windows Server pour protéger les données clés utilisées pour le chiffrement des connexions TLS (Transport Layer Security). Les clés utilisées pour le chiffrement multimédia sont échangées via des connexions TLS.

</div>

<div>

## <a name="network-denial-of-service-attack"></a>Attaque réseau par déni de service

Une *attaque par déni de service* se produit lorsqu’une personne malveillante empêche des utilisateurs valides de travailler et d’utiliser le réseau normalement. Pour ce faire, elle inonde le service avec des demandes légitimes qui submergent l’utilisation du service par les utilisateurs légitimes. Lors d’une attaque de ce type, la personne malveillante peut :

  - envoyer des données non valides à des applications et des services exécutés sur le réseau faisant l’objet de l’attaque, afin de perturber leur exécution normale ;

  - envoyer un volume de trafic important, de manière à surcharger le système jusqu’à ce que celui-ci cesse de fonctionner ou nécessite beaucoup de temps pour répondre aux demandes légitimes ;

  - masquer les signes d’attaque ;

  - empêcher les utilisateurs d’accéder aux ressources réseau.

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a>Attaque par écoute (Eavesdropping)

Une *attaque par écoute* peut se produire lorsqu’une personne malveillante parvient à accéder au chemin d’accès des données d’un réseau et qu’elle peut ainsi surveiller et lire le trafic. Cette attaque est également appelée *reniflage* (« sniffing ») ou *surveillance* (« snooping »). Si le trafic consiste en du texte simple, l’intrus peut lire le trafic lorsqu’il accède au chemin d’accès des données. Par exemple, une attaque peut être lancée en contrôlant un routeur sur le chemin de données.

Par défaut, le paramétrage du trafic au sein de Microsoft Lync Server 2013 consiste à utiliser Mutual TLS (MTLS) entre les serveurs de confiance et TLS du client vers le serveur. Cette mesure de protection rend ce type d’attaque difficile, voire impossible, durant le laps de temps pendant lequel une conversation donnée peut être attaquée. Le protocole TLS authentifie toutes les parties et chiffre le trafic. Ceci n’empêche pas les attaques par écoute, mais l’intrus ne peut pas lire le trafic à moins que le chiffrement ne soit rompu.

Le protocole TURN (Traversal Using Relay NAT) n’exige pas que le trafic soit chiffré. Les informations acheminées sont protégées par l’intégrité des messages. Bien qu’elles puissent faire l’objet d’une attaque par écoute, les informations acheminées (autrement dit, les adresses IP et le port) peuvent être extraites directement, en observant simplement les adresses source et de destination des paquets. Le service Edge A/V s’assure que les données sont valides en vérifiant l’intégrité du message à l’aide d’une clé dérivée de plusieurs éléments, dont un mot de passe TURN, qui n’est jamais transmise en texte en clair. Si le protocole SRTP (Secure Real Time Protocol) est utilisé, le trafic multimédia est également chiffré.

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a>Usurpation d’identité (usurpation d’adresse IP)

On parle d’*usurpation d’identité* lorsqu’une personne malveillante parvient à déterminer et à utiliser l’adresse IP d’un réseau, d’un ordinateur ou d’un composant réseau, sans y avoir été autorisée. Si l’attaque réussit, l’intrus peut opérer comme s’il était l’utilisateur habituellement identifié par l’adresse IP. Dans le cadre de Microsoft Lync Server 2013, cette situation ne s’exécute que si un administrateur a réalisé les deux opérations suivantes :

  - configuré des connexions qui prennent uniquement en charge le protocole TCP (Transmission Control Protocol), ce qui n’est pas recommandé car les communications TCP ne sont pas chiffrées ;

  - marqué les adresses IP de ces connexions en tant qu’hôtes approuvés.

Ce problème est moins grave pour les connexions TLS (Transport Layer Security), car TLS authentifie toutes les parties et chiffre le trafic. L’utilisation du protocole TLS empêche une personne malveillante d’usurper une adresse IP sur une connexion spécifique (par exemple, les connexions Mutual TLS). En revanche, une personne malveillante pourrait toujours usurper l’adresse du serveur DNS utilisé par Lync Server 2013. Toutefois, dans la mesure où l’authentification dans Lync est effectuée avec des certificats, l’attaquant ne dispose pas d’un certificat valide requis pour usurper une des parties de la communication.

</div>

<div>

## <a name="man-in-the-middle-attack"></a>Attaque de l’intercepteur (« man-in-the-middle »)

Une attaque de l’intercepteur se produit lorsqu’une personne malveillante redirige les communications entre deux utilisateurs via son propre ordinateur, à l’insu des deux participants. L’intrus peut surveiller et lire le trafic avant de l’acheminer vers le destinataire concerné. Chacun des utilisateurs envoie et reçoit du trafic vers/de l’intrus, alors qu’il pense communiquer avec l’utilisateur concerné uniquement. Cela peut se produire si une personne malveillante modifie les services de domaine Active Directory pour ajouter son serveur en tant que serveur approuvé, ou si elle modifie DNS (Domain Name System) pour faire en sorte que les clients se connectent au serveur via l’ordinateur de l’intrus à l’origine de l’attaque. Une attaque de l’intercepteur peut également affecter le trafic multimédia entre deux clients. Néanmoins, dans Microsoft Lync Server 2013, les flux audio et vidéo, et le partage d’applications, les flux sont chiffrés avec SRTP, à l’aide de clés de chiffrement négociées entre les homologues utilisant le protocole SIP (Session Initiation Protocol) sur TLS. Les serveurs tels que le serveur de conversation de groupe utilisent le protocole HTTPS pour sécuriser le trafic.

</div>

<div>

## <a name="rtp-replay-attack"></a>Attaque par relecture RTP

Une *attaque par relecture* se produit lorsqu’une transmission multimédia valide entre deux correspondants est interceptée, puis retransmise à des fins malveillantes. L’utilisation de SRTP avec un protocole de signalisation sécurisé protège les transmissions contre les attaques par relecture. En effet, le destinataire est alors en mesure d’établir un index des paquets RTP déjà reçus et de comparer chaque nouveau paquet à ceux répertoriés dans l’index.

</div>

<div>

## <a name="spim"></a>Messages instantanés indésirables (Spim)

Le *spim* correspond à des messages instantanés commerciaux ou des demandes d’abonnement aux informations de présence non sollicités. S’il ne constitue pas à lui seul une menace envers le réseau, il peut néanmoins perturber les activités des utilisateurs et avoir un impact négatif sur la disponibilité des ressources et la production. Il représente donc un risque potentiel pour le réseau. Prenons le cas d’utilisateurs qui génèrent du spim en s’envoyant mutuellement des demandes. Un utilisateur peut en bloquer un autre pour ne plus recevoir de messages instantanés indésirables. Toutefois, dans le cas de la fédération, il peut s’avérer difficile de faire face à une attaque de spim coordonnée, à moins de désactiver la fédération pour le partenaire.

</div>

<div>

## <a name="viruses-and-worms"></a>Virus et vers

Un *virus* est une unité de code dont le seul rôle consiste à reproduire d’autres unités de code similaires. Pour fonctionner, un virus doit être hébergé dans un fichier, un courrier électronique ou un programme. Un *ver* est une unité de code programmée pour reproduire d’autres unités de code similaires. Toutefois, il n’est pas nécessaire qu’il soit hébergé. Les virus et les vers apparaissent principalement lors du transfert de fichiers entre clients ou lorsque d’autres utilisateurs transmettent des URL. Une fois qu’un virus se trouve sur votre ordinateur, il peut, par exemple, usurper votre identité et envoyer des messages instantanés à votre nom.

</div>

<div>

## <a name="personally-identifiable-information"></a>Informations d’identification personnelle

Microsoft Lync Server 2013 est en mesure de divulguer des informations sur un réseau public qui peuvent être liées à une personne. Ces informations appartiennent à deux catégories :

  - **Données de présence améliorées** Les données de présence améliorées sont des informations que les utilisateurs peuvent choisir de partager ou de ne pas partager sur un lien vers un partenaire fédéré ou avec des contacts au sein d’une organisation. Elles ne sont pas partagées avec les utilisateurs d’un réseau public de messagerie instantanée. Selon les stratégies de groupe en vigueur et la configuration du client, l’administrateur système peut contrôler ces informations. Dans Lync Server 2013, le mode de confidentialité Enhanced presence peut être configuré pour un utilisateur individuel afin d’empêcher les utilisateurs de Lync d’avoir à voir les informations de présence de l’utilisateur dans la liste des contacts de l’utilisateur. Le mode de confidentialité de présence enrichie n’empêche pas les utilisateurs de Microsoft Office Communicator 2007 et Microsoft Office Communicator 2007 R2 de voir les informations de présence d’un utilisateur. Pour plus d’informations, reportez-vous aux [nouveautés pour les clients dans Lync server 2013](lync-server-2013-what-s-new-for-clients.md) dans la documentation de mise en route et [configuration du mode de confidentialité de présence avancée dans Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) dans la documentation de déploiement.

  - **Données obligatoires** Des données obligatoires sont nécessaires pour le bon fonctionnement du serveur ou du client et ne sont pas sous le contrôle de l’administration du client ou du système. Il s’agit d’informations nécessaires au niveau du serveur ou du réseau aux fins de routage, de maintenance de l’État et de signalisation.

Les tableaux suivants répertorient les données exposées sur un réseau public.

### <a name="enhanced-presence-data"></a>Données de présence enrichie

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


### <a name="mandatory-data"></a>Données obligatoires

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
<td><p>Adresse IP</p></td>
<td><p>Adresse réelle de l’ordinateur ou adresse traduite via NAT</p></td>
</tr>
<tr class="even">
<td><p>URI SIP</p></td>
<td><p>jeremylos@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013 : menaces de sécurité courantes lors de l’informatique moderne'
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
ms.openlocfilehash: 6dffff9cfbc501a8e6a9a79439183966ef0a1956
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a>Menaces de sécurité courantes lors de l’informatique moderne

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-09-10_

Étant donné que Lync Server 2013 est un système de communication d’entreprise, vous devez être conscient des attaques de sécurité courantes susceptibles d’avoir une incidence sur son infrastructure et ses communications.

<div>

## <a name="compromised-key-attack"></a>Attaque par clé compromise

Une clé est un code ou un nombre secret utilisé pour chiffrer, déchiffrer ou valider des informations confidentielles. Il existe deux clés sensibles utilisées dans l’infrastructure à clé publique (PKI) qui doivent être considérées comme suit :.

  - La clé privée que chaque détenteur de certificat a

  - La clé de session utilisée après l’identification et l’échange de clés de session réussies par les partenaires communicants.

Une attaque par clé compromise se produit lorsque l’intrus détermine la clé privée ou la clé de session. Lorsque l’intrus parvient à déterminer la clé, il s’en sert pour déchiffrer des données chiffrées, à l’insu de l’expéditeur des données.

Lync Server 2013 utilise les fonctionnalités de l’infrastructure à clé publique dans le système d’exploitation Windows Server pour protéger les données clés utilisées pour le chiffrement des connexions TLS (Transport Layer Security). Les clés utilisées pour le chiffrement multimédia sont échangées via des connexions TLS.

</div>

<div>

## <a name="network-denial-of-service-attack"></a>Attaque réseau par déni de service

L' *attaque par déni de service* se produit lorsque l’agresseur empêche l’utilisation et la fonction réseau normales par les utilisateurs valides. Cette opération est réalisée lorsque l’agresseur inonde le service de demandes légitimes qui inondent l’utilisation du service par des utilisateurs légitimes. À l’aide d’une attaque par déni de service, l’agresseur peut effectuer les opérations suivantes :

  - envoyer des données non valides à des applications et des services exécutés sur le réseau faisant l’objet de l’attaque, afin de perturber leur exécution normale ;

  - envoyer un volume de trafic important, de manière à surcharger le système jusqu’à ce que celui-ci cesse de fonctionner ou nécessite beaucoup de temps pour répondre aux demandes légitimes ;

  - masquer les signes d’attaque ;

  - empêcher les utilisateurs d’accéder aux ressources réseau.

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a>Écoute clandestine (reniflage, espionnage)

Une *écoute clandestine* peut se produire lorsqu’un agresseur accède au chemin des données d’un réseau et qu’il a la possibilité de surveiller et de lire le trafic. Il s’agit également de *reniflage* ou d' *espionnage*. Si le trafic consiste en du texte simple, l’intrus peut lire le trafic lorsqu’il accède au chemin d’accès des données. Par exemple, une attaque peut être lancée en contrôlant un routeur sur le chemin de données.

La recommandation et le paramétrage par défaut du trafic au sein de Microsoft Lync Server 2013 consiste à utiliser Mutual TLS (MTLS) entre les serveurs approuvés et TLS entre le client et le serveur. Cette mesure de protection rendrait une attaque très difficile ou impossible à réaliser pendant la période pendant laquelle une conversation donnée a lieu. TLS authentifie toutes les parties et chiffre tout le trafic. Cela n’empêche pas les écoutes, mais l’agresseur ne peut pas lire le trafic, sauf si le chiffrement est rompu.

Le protocole Traversal NAT (TURN) de relais n’impose pas le chiffrement du trafic et les informations qu’il envoie sont protégées par l’intégrité des messages. Bien qu’elle soit ouverte aux écoutes, les informations envoyées (c’est-à-dire, les adresses IP et le port) peuvent être extraites directement en examinant simplement les adresses source et de destination des paquets. Le service Edge A/V garantit que les données sont valides en vérifiant l’intégrité des messages à l’aide de la clé dérivée de quelques éléments, y compris un mot de passe de retour, qui n’est jamais envoyé en texte clair. Si le protocole SRTP (Secure Real Time Protocol) est utilisé, le trafic multimédia est également chiffré.

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a>Usurpation d’identité (usurpation d’adresse IP)

L' *usurpation* se produit lorsque l’agresseur détermine et utilise une adresse IP d’un réseau, d’un ordinateur ou d’un composant réseau sans être autorisé à le faire. Une attaque réussie permet à l’agresseur de fonctionner comme s’il s’agissait de l’entité normalement identifiée par l’adresse IP. Dans le contexte de Microsoft Lync Server 2013, cette situation ne s’exécute que si un administrateur a réalisé les deux opérations suivantes :

  - Connexions configurées qui prennent uniquement en charge le protocole TCP (Transmission Control Protocol) (ce qui n’est pas recommandé, car les communications TCP ne sont pas chiffrées).

  - Marqué les adresses IP de ces connexions en tant qu’hôtes approuvés.

Il s’agit moins d’un problème pour les connexions TLS (Transport Layer Security), car TLS authentifie toutes les parties et chiffre tout le trafic. L’utilisation de TLS empêche une personne malveillante d’effectuer une usurpation d’adresse IP sur une connexion spécifique (par exemple, les connexions Mutual TLS). Toutefois, un agresseur peut toujours usurper l’adresse du serveur DNS utilisé par Lync Server 2013. Toutefois, étant donné que l’authentification dans Lync est effectuée avec des certificats, un agresseur ne dispose pas d’un certificat valide requis pour usurper l’une des parties dans la communication.

</div>

<div>

## <a name="man-in-the-middle-attack"></a>Attaque de l’intercepteur

Une attaque de l’intercepteur se produit lorsqu’un agresseur redirige la communication entre deux utilisateurs par le biais de l’ordinateur de l’agresseur sans avoir connaissance des deux utilisateurs communicants. L’agresseur peut surveiller et lire le trafic avant de l’envoyer au destinataire concerné. Chaque utilisateur de la communication envoie un trafic vers et reçoit le trafic de l’agresseur, tout en pensant qu’il communique uniquement avec l’utilisateur prévu. Cela peut se produire si un agresseur peut modifier les services de domaine Active Directory pour ajouter son serveur en tant que serveur approuvé ou modifier le système DNS (Domain Name System) pour permettre aux clients de se connecter au serveur par l’intermédiaire de l’agresseur. Une attaque de l’intercepteur peut également se produire avec le trafic multimédia entre deux clients. Toutefois, dans Microsoft Lync Server 2013 point à point, la vidéo et le partage d’application, les flux sont chiffrés avec SRTP, à l’aide de clés de chiffrement négociées entre les homologues qui utilisent le protocole SIP (Session Initiation Protocol) sur TLS. Les serveurs tels que la conversation de groupe utilisent le protocole HTTPs pour améliorer la sécurité du trafic Web.

</div>

<div>

## <a name="rtp-replay-attack"></a>Attaque par relecture RTP

Une *attaque par relecture* se produit lorsqu’une transmission de média valide entre deux parties est interceptée et retransmise à des fins malveillantes. Les SRTP utilisés dans le cadre d’un protocole de signalisation sécurisé protègent les transmissions des attaques de relecture en permettant au récepteur de maintenir un index des paquets RTP déjà reçus et de comparer chaque nouveau paquet à ceux figurant déjà dans l’index.

</div>

<div>

## <a name="spim"></a>Désir

*SPIM* désigne les messages instantanés commerciaux non sollicités ou les demandes d’abonnement de présence. Bien qu’il ne soit pas en soi un compromis du réseau, il est ennuyeux au moins, peut réduire la disponibilité et la production des ressources, et peut entraîner une compromission du réseau. Par exemple, les utilisateurs se spimmingent mutuellement en envoyant des demandes. Les utilisateurs peuvent se bloquer pour éviter cela, mais avec la Fédération, si une attaque de spim coordonné est établie, il peut être difficile de la surmonter, sauf si vous désactivez la Fédération pour le partenaire.

</div>

<div>

## <a name="viruses-and-worms"></a>Virus et vers

Un *virus* est une unité de code dont l’objectif est de reproduire des unités de code similaires supplémentaires. Pour fonctionner, un virus doit être hébergé dans un fichier, un message électronique ou un programme. Un *ver* est une unité de code dont l’objectif est de reproduire des unités de code similaires, mais il n’a pas besoin d’un hôte. Les virus et les vers apparaissent principalement lors du transfert de fichiers entre clients ou lorsque d’autres utilisateurs transmettent des URL. Une fois qu’un virus se trouve sur votre ordinateur, il peut, par exemple, usurper votre identité et envoyer des messages instantanés en votre nom.

</div>

<div>

## <a name="personally-identifiable-information"></a>Informations d’identification personnelle

Microsoft Lync Server 2013 a le potentiel de divulguer des informations sur un réseau public qui pourrait être lié à un individu. Les types d’informations peuvent être divisées en deux catégories spécifiques :

  - **Données de présence enrichies** Les données de présence enrichies sont des informations qu’un utilisateur peut choisir de partager ou non via un lien vers un partenaire fédéré ou avec des contacts au sein d’une organisation. Ces données ne sont pas partagées avec les utilisateurs d’un réseau de messagerie instantanée public. Les stratégies de client et les autres configurations de client peuvent mettre en place un contrôle auprès de l’administrateur système. Dans Lync Server 2013, le mode de confidentialité améliorée de la présence peut être configuré pour un utilisateur individuel afin d’empêcher les utilisateurs de Lync ne figurant pas dans la liste des contacts de voir les informations de présence de l’utilisateur. Le mode de confidentialité de la présence enrichie n’empêche pas les utilisateurs de Microsoft Office Communicator 2007 et de Microsoft Office Communicator 2007 R2 de voir les informations de présence d’un utilisateur. Pour plus d’informations, voir [what’s New for clients in Lync server 2013](lync-server-2013-what-s-new-for-clients.md) dans la documentation de prise en main et [Configuring Enhanced presence Privacy mode in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) dans la documentation de déploiement.

  - **Données obligatoires** Des données obligatoires sont requises pour le bon fonctionnement du serveur ou du client et ne sont pas sous le contrôle de l’administration du client ou du système. Il s’agit d’informations nécessaires au niveau d’un serveur ou d’un réseau à des fins de routage, d’état de maintenance et de signalisation.

Les tableaux suivants répertorient les données exposées sur un réseau public.

### <a name="enhanced-presence-data"></a>Données de présence enrichies

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
<td><p>Nom, titre, société, adresse de messagerie, fuseau horaire</p></td>
</tr>
<tr class="even">
<td><p>Numéros de téléphone</p></td>
<td><p>Bureau, mobile, domicile</p></td>
</tr>
<tr class="odd">
<td><p>Informations de calendrier</p></td>
<td><p>Informations de disponibilité, de notification d’absence de ville, de détails de réunion (pour les personnes ayant accès à votre calendrier)</p></td>
</tr>
<tr class="even">
<td><p>Statut de présence</p></td>
<td><p>Absent, disponible, occupé, ne pas déranger, hors connexion</p></td>
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
<th>Exemple d’informations</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Adresse IP</p></td>
<td><p>Adresse réelle de l’ordinateur ou de l’adresse de l’adresse de l’utilisateur</p></td>
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


---
title: Chiffrement pour Lync Server 2013
TOCTitle: Chiffrement pour Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59679144
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Chiffrement pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Microsoft Lync Server 2013 utilise TLS et MTLS pour chiffrer les messages instantanés. L’ensemble du trafic serveur à serveur nécessite MTLS, et ce que le trafic soit confiné au réseau interne ou qu’il traverse le périmètre du réseau interne. TLS est facultatif mais vivement conseillé entre le serveur de médiation et la passerelle multimédia. Si TLS est configuré sur cette liaison, MTLS est requis. Par conséquent, la passerelle doit être configurée avec un certificat provenant d’une autorité de certification approuvée par le serveur de médiation.

Les exigences du trafic client à client varient selon que le trafic traverse ou non le pare-feu d’entreprise interne. Le trafic strictement interne peut utiliser TLS, auquel cas le message instantané est chiffré, ou TCP, auquel cas il ne l’est pas.

Le tableau suivant résume les exigences de protocole pour chaque type de trafic.

### Protection du trafic

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de trafic</th>
<th>Protégé par</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serveur à serveur</p></td>
<td><p>MTLS</p></td>
</tr>
<tr class="even">
<td><p>Client à serveur</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>Messagerie instantanée et présence</p></td>
<td><p>TLS (si configuré pour TLS)</p></td>
</tr>
<tr class="even">
<td><p>Partage multimédia audio, vidéo et de bureau</p></td>
<td><p>SRTP</p></td>
</tr>
<tr class="odd">
<td><p>Partage du bureau (signalisation)</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="even">
<td><p>Conférence Web</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>Téléchargement de contenu de réunion, téléchargement de carnet d’adresses, développement de groupe de distribution</p></td>
<td><p>HTTPS</p></td>
</tr>
</tbody>
</table>


## Chiffrement multimédia

Le trafic multimédia est chiffré à l’aide de Secure RTP (SRTP), un profil RTP (Real-Time Transport Protocol) qui offre confidentialité, authentification et protection contre les attaques par relecture sur le trafic RTP. SRTP utilise une clé de session générée par le service d’authentification du serveur relais multimédia en réponse à une authentification réussie de la demande de serveur (pour le compte des participants multimédias). La clé de session est sécurisée par le nom d’utilisateur et le mot de passe négociés présentés au service d’authentification du serveur relais multimédia par les serveurs frontaux et envoyés aux participants sur le canal SIP sécurisé par TLS. Le déchiffrement de la clé de session sécurisée avec le nom d’utilisateur et le mot de passe utilisés par le service de relais multimédia, et fournis de manière sécurisée par le biais du certificat TLS des participants et du canal SIP sécurisé, permet aux participants de déchiffrer le flux SRTP. De plus, les données multimédias acheminées dans les deux directions entre le serveur de médiation et son tronçon suivant interne sont également chiffrées avec SRTP. Les données acheminées dans les deux directions entre le serveur de médiation et une passerelle multimédia ne sont pas chiffrées. Le serveur de médiation peut prendre en charge le chiffrement sur la passerelle multimédia, mais la passerelle doit prendre en charge MTLS et le stockage d’un certificat.

> [!NOTE]  
> L’audio/video (A/V) est pris en charge avec la nouvelle version de Windows Live Messenger. Si vous implémentez la fédération A/V avec Windows Live Messenger, vous devez également modifier le niveau de chiffrement de Lync Server. Par défaut, le niveau de chiffrement est Obligatoire. Vous devez définir ce paramètre sur Pris en charge en utilisant le Lync Server Management Shell. Pour plus d’informations, voir <a href="lync-server-2013-deploying-external-user-access.md">Déploiement de l’accès des utilisateurs externes dans Lync Server 2013</a> dans la documentation de déploiement.

Le trafic multimédia audio et vidéo n’est pas chiffré entre Microsoft Lync 2013 et les clients Windows Live.

## FIPS

Lync Server 2013 et Microsoft Exchange Server 2013 fonctionnent avec une prise en charge des algorithmes FIPS (Federal Information Processing Standard) 140-2 si les systèmes d’exploitation Windows Server sont configurés pour utiliser les algorithmes FIPS 140-2 pour le chiffrement système. Pour permettre une prise en charge de la norme FIPS, vous devez configurer chaque serveur équipé de Lync Server 2013 pour que ce dernier puisse la reconnaître. Pour plus d’informations sur les algorithmes compatibles FIPS et la manière d’autoriser la prise en charge de cette norme, voir l’article 811833 de la Base de connaissances Microsoft sur les effets de l’activation du paramètre de sécurité « System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing » dans Windows XP et les versions ultérieures de Windows à l’adresse [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833). Pour plus d’informations sur la prise en charge des algorithmes FIPS 140-2 et les restrictions à cet égard dans Exchange 2010, voir Exchange 2010 SP1 and Support for FIPS Compliant Algorithms à l’adresse [http://go.microsoft.com/fwlink/p/?LinkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335).


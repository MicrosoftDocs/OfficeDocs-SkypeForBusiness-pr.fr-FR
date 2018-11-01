---
title: "Lync Server 2013 : Déf. de la conf. req. pour le pare-feu A/V et les ports"
TOCTitle: Définition de la configuration requise pour le pare-feu A/V et les ports
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425882(v=OCS.15)
ms:contentKeyID: 49296938
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La communication audio/vidéo (A/V) peut être complexe. Du fait de la nature des protocoles utilisés et de la façon dont les clients et les serveurs les utilisent dans le cadre de cette communication, nous avons jugé utile de consacrer une section à expliquer les différences entre les versions client et serveur.

Le tableau ci-dessous intitulé Pare-feu A/V et les ports vous permet de déterminer les conditions requises pour le pare-feu et les ports à ouvrir. Examinez ensuite la terminologie propre à la conversion d’adresses réseau (NAT, Network Address Translation), car cette fonctionnalité peut être implémentée de nombreuses façons. Pour obtenir un exemple détaillé des paramètres de port de pare-feu, reportez-vous aux architectures de référence à la rubrique [Scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

### Utilisation générale des protocoles pour UDP et TCP dans le trafic audio/vidéo et multimédia

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Transport audio/vidéo</th>
<th>Utilisation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP</p></td>
<td><p>Protocole de couche transport par défaut pour les données audio et vidéo</p></td>
</tr>
<tr class="even">
<td><p>TCP</p></td>
<td><p>Protocole de couche transport de secours pour les données audio et vidéo</p>
<p>Protocole de couche transport requis pour le partage d’application dans Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013</p>
<p>Protocole de couche transport requis pour le transfert de fichier vers Lync Server 2010 et Lync Server 2013</p></td>
</tr>
</tbody>
</table>


## Conditions requises pour les ports du pare-feu A/V externe pour l’accès des utilisateurs externes

Les conditions requises pour les ports du pare-feu pour les interfaces SIP et de conférence externes (et internes) sont cohérentes, quelle que soit la version de votre client ou la version du partenaire de fédération.

Ce n’est pas le cas de l’interface externe Edge A/V. Pour une fédération avec Office Communications Server 2007, le service Edge A/V exige que des règles de pare-feu externes autorisent le trafic RTP/TCP et RTP/UDP à transiter via la plage de ports 50 000 à 59 999 dans les deux sens. Le tableau précédent suppose que Lync Server 2013 est le partenaire principal de la fédération et est configuré pour communiquer avec l’un des autres types de partenaire de fédération répertoriés.

Quand vous configurez la plage de ports audio/vidéo 50 000-59 999, gardez à l’esprit que celle-ci contiendra les ports sources des communications vers les partenaires de fédération. Plus précisément, considérez qu’une communication est initiée à partir d’un partenaire de fédération. La communication depuis les ports du service Edge A/V dans la plage 50 000-59 999 établira une connexion avec le port TCP 443 du service Edge A/V du partenaire. À l’inverse, le trafic entrant vers le port TCP 443 de votre service Edge A/V aura un port source dans la plage 50 000-59 999.

Suivant les pare-feu et les stratégies d’administration de pare-feu, seules des règles de destination doivent être configurées ou à la fois la source et la destination doivent être configurées. Si vos exigences ne concernent que les ports de destination, les contraintes audio/vidéo sont les suivantes :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Adresse IP source</th>
<th>Adresse IP de destination</th>
<th>Port de destination</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interface du service Edge A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Interface du service Edge A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>Indifférente</p></td>
<td><p>Interface du service Edge A/V</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Indifférente</p></td>
<td><p>Interface du service Edge A/V</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


Si vos stratégies nécessitent des définitions de règle de pare-feu entrante et sortante, les contraintes audio/vidéo sont les suivantes :


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Adresse IP source</th>
<th>Adresse IP de destination</th>
<th>Port source</th>
<th>Port de destination</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interface du service Edge A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>TCP 50 000-59 999</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Interface du service Edge A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>UDP 3478</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>Indifférente</p></td>
<td><p>Interface du service Edge A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Indifférente</p></td>
<td><p>Interface du service Edge A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


> [!IMPORTANT]  
> Microsoft Office Communications Server 2007 nécessite une configuration légèrement différente. La plage de port TCP et UDP 50 000-59 999 doit être sortante et entrante à connexions ouvertes. Cette contrainte concerne uniquement Office Communicator 2007. Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013 nécessitent uniquement une plage TCP 50 000-59 999 sortante à connexions ouvertes.

## Configuration requise pour la conversion d’adresses réseau (NAT) concernant l’accès des utilisateurs externes

La conversion d’adresses réseau (NAT) est à la base une fonction de routage. Cependant, il est possible de la configurer sur des périphériques récents, tels que les pare-feu et même le matériel d’équilibrage de charge. L’objet de cette rubrique n’est pas de déterminer quel périphérique est capable d’exécuter la fonction NAT, mais de décrire le comportement requis de cette fonction.

Les logiciels de communicationLync Server 2013 ne prennent pas en charge NAT pour le trafic à destination et en provenance de l’interface interne Edge, mais pour l’interface externe Edge, NAT doit avoir le comportement suivant.

> [!IMPORTANT]  
> Vous devez configurer la fonction NAT symétrique pour le trafic entrant et sortant. La fonction NAT symétrique est la technologie NAT décrite dans cette rubrique.

Dans cette documentation, les termes ChangeDST et ChangeSRC sont utilisés dans les tableaux et les illustrations pour définir le comportement requis suivant :

  - **ChangeDST**   Processus de changement de l’adresse IP de destination des paquets destinés au réseau qui utilise NAT. Ce processus est également appelé transparence, redirection de ports, mode de destination NAT ou mode semi-NAT.

  - **ChangeSRC**   Processus de changement de l’adresse IP source des paquets provenant du réseau qui utilise NAT. Ce processus est également appelé proxy, NAT sécurisé, NAT avec état, NAT source ou mode NAT intégral.

Quel que soit le nom utilisé, le comportement NAT requis pour l’interface externe du serveur Edge est le suivant :

  - Pour le trafic allant d’Internet vers l’interface externe Edge :
    
      - Changez l’adresse IP de destination du paquet entrant, de l’adresse IP publique de l’interface externe Edge en adresse IP convertie de l’interface externe Edge.
    
      - Laissez l’adresse IP source intacte de sorte à laisser un itinéraire de retour pour le trafic.

  - Pour le trafic allant de l’interface externe Edge vers Internet :
    
      - Changez l’adresse IP source du paquet quittant l’interface externe Edge, de l’adresse IP convertie en adresse IP publique de l’interface externe de sorte que l’adresse IP de l’interface interne Edge ne soit pas exposée (car il s’agit d’une adresse IP non routable).
    
      - Laissez l’adresse IP de destination intacte sur les paquets sortants.

L’illustration suivante montre la distinction entre le changement de l’adresse IP de destination (ChangeDST) pour le trafic entrant et le changement de l’adresse IP source (ChangeSRC) pour le trafic sortant, avec le serveur Edge A/V comme exemple.

**Changement de l’adresse IP de destination (ChangeDST) pour le trafic entrant et changement de l’adresse IP source (ChangeSRC)**

![Modification des adresses IP source/de destination](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Modification des adresses IP source/de destination")

Les principaux points sont les suivants :

  - Pour le trafic entrant à destination du serveur exécutant le service Edge A/V, l’adresse IP source ne change pas, mais l’adresse IP de destination passe de 131.107.155.30 à 10.45.16.10, qui est l’adresse IP convertie.

  - Pour le trafic sortant en provenance du serveur exécutant le service Edge A/V et de retour vers la station de travail, l’adresse IP source passe de l’adresse IP publique du serveur à l’adresse IP publique du serveur exécutant le service Edge A/V. L’adresse IP de destination reste l’adresse IP publique de la station de travail. Une fois que le paquet quitte le premier périphérique NAT sortant, la règle du périphérique NAT remplace l’adresse IP source du serveur exécutant l’adresse IP de l’interface externe du service Edge A/V (10.45.16.10) par son adresse IP publique (131.107.155.30).


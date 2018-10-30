---
title: 'Lync Server 2013 : Configuration des interfaces réseau pour les serveurs Edge'
TOCTitle: Configuration des interfaces réseau pour les serveurs Edge
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412847(v=OCS.15)
ms:contentKeyID: 49298535
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des interfaces réseau pour les serveurs Edge dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-08_

Chaque serveur Edge est un ordinateur multirésident avec des interfaces interne et externe. Les paramètres DNS (Domain Name System) dépendent de la présence ou non de serveurs DNS dans le réseau de périmètre. Si le périmètre comporte des serveurs DNS, ils doivent présenter une zone contenant un ou plusieurs enregistrements DNS A pour le serveur ou le pool du tronçon suivant (un pool frontal désigné ou un pool directeur) et pour les requêtes externes ils renvoient les recherches de noms à d’autres serveurs DNS publics. Si aucun serveur DNS ne figure dans le périmètre, les serveurs Edge utilisent des serveurs DNS externes pour résoudre les recherches de noms Internet et chaque serveur Edge utilise un fichier HOST pour résoudre les noms des serveurs du tronçon suivant en adresses IP.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="security" alt="security" />Sécurité Remarque :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Pour des raisons de sécurité, il est préférable que vos serveurs Edge n’accèdent pas à un serveur DNS figurant dans le réseau interne.</td>
</tr>
</tbody>
</table>

## Pour configurer des interfaces avec des serveurs DNS dans le réseau de périmètre

1.  Installez deux cartes réseau pour chaque serveur Edge, une pour l’interface côté interne et une pour l’interface côté externe.
    
    > [!IMPORTANT]  
    > Les sous-réseaux interne et externe ne doivent pas être routables entre eux.

2.  Sur l’interface externe, configurez trois adresses IP statiques sur le sous-réseau du réseau de périmètre extérieur (également appelé zone démilitarisée, DMZ ou sous-réseau filtré) et pointez la passerelle par défaut sur l’interface interne du pare-feu externe. Configurez les paramètres de la carte réseau DNS de manière à pointer sur une paire de serveurs DNS de périmètre.
    
    > [!NOTE]  
    > Il est possible de n’utiliser qu’une seule adresse IP pour cette interface, mais pour cela vous devez modifier les affectations des ports sur des valeurs différentes des valeurs par défaut. Vous déterminez cela lors de la création de la topologie dans le Générateur de topologie.

3.  Sur l’interface interne, configurez une adresse IP statique sur le sous-réseau du réseau de périmètre interne et ne définissez aucune passerelle par défaut. Configurez les paramètres de la carte réseau DNS de manière à pointer sur au moins un serveur DNS, de préférence une paire de serveurs DNS de périmètre.

4.  Créez des itinéraires statiques persistants sur l’interface interne, vers tous les réseaux internes où se trouvent les clients, Lync Server 2013 et les serveurs de messagerie unifiée Exchange.

## Pour configurer des interfaces sans serveurs DNS dans le réseau de périmètre

1.  Installez deux cartes réseau pour chaque serveur Edge, une pour l’interface côté interne et une pour l’interface côté externe.
    
    > [!IMPORTANT]  
    > Les sous-réseaux interne et externe ne doivent pas être routables entre eux.

2.  Sur l’interface externe, configurez trois adresses IP statiques sur le sous-réseau du réseau de périmètre extérieur. Vous configurez également la passerelle par défaut sur l’interface externe. Définissez, par exemple, le routeur accessible sur Internet ou le pare-feu feu externe comme passerelle par défaut. Configurez les paramètres DNS de manière à pointer vers un serveur DNS, de préférence une paire de serveurs DNS externes.
    
    > [!NOTE]  
    > Il est possible, mais déconseillé, de n’utiliser qu’une seule adresse IP pour l’interface externe. Pour que cela fonctionne, vous devez définir des valeurs autres que les valeurs par défaut pour les affectations de ports, et autres que le port par défaut 443 qui est généralement « destiné aux pare-feu », pour la communication cliente. Vous déterminez le paramètre d’adresse IP et les paramètres de port lors de la création de la topologie dans le Générateur de topologie.

3.  Sur l’interface interne, configurez une adresse IP statique sur le sous-réseau du réseau de périmètre interne et ne définissez aucune passerelle par défaut. Laissez les paramètres DNS de la carte réseau vides.

4.  Créez des itinéraires statiques persistants sur l’interface interne, vers tous les réseaux internes où se trouvent les clients Lync ou les serveurs exécutant Lync Server 2013.

5.  Modifiez le fichier HOST sur chaque serveur Edge de manière à inclure un enregistrement pour l’IP virtuelle (VIP) ou le serveur du tronçon suivant (l’enregistrement sera le serveur Standard Edition directeur ou un pool frontal configuré comme adresse du tronçon suivant pour le serveur Edge dans le Générateur de topologie). Si vous utilisez l’équilibrage de la charge DNS, incluez une ligne pour chaque membre du pool du tronçon suivant.


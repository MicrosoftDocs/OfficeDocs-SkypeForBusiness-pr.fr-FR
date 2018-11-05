---
title: 'Lync Server 2013 : Configuration des cartes réseau'
TOCTitle: Configuration des cartes réseau
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429707(v=OCS.15)
ms:contentKeyID: 49297431
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des cartes réseau dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-11-07_

Vous devez affecter une ou plusieurs adresses IP à la carte réseau externe et au moins une adresse IP à la carte réseau interne.

Dans les procédures suivantes, le serveur qui exécute Forefront Threat Management Gateway (TMG) 2010 ou Internet Information Server Application Request Routing a deux cartes réseau :

  - une carte réseau publique ou externe pour les clients qui tentent de se connecter à votre site web (habituellement par le biais d’Internet) ;

  - une interface réseau privée ou interne pour les serveurs internes exécutant Lync Server, qui hébergent les services web.

> [!IMPORTANT]  
> Comme pour les serveurs Edge, vous définissez la passerelle par défaut sur la carte réseau externe uniquement. La passerelle par défaut est l’adresse IP du routeur ou du pare-feu côté externe qui dirige le trafic vers Internet. Pour le trafic destiné à la carte réseau côté interne face à partir du proxy inverse, vous devez utiliser des itinéraires statiques permanents (notamment la commande route dans Windows Server) pour tous les sous-réseaux contenant des serveurs référencés par les règles de publication web. La définition d’un itinéraire permanent ne transforme pas l’ordinateur en routeur. Si le transfert IP n’est pas activé, l’ordinateur n’agit que pour diriger le trafic spécifique destiné à un autre réseau vers l’interface appropriée. Grosso modo, cela revient à définir deux passerelles : une passerelle par défaut pointant vers les réseaux externes et une autre passerelle pour le trafic destiné à l’interface interne et sur un routeur ou un autre réseau.<br />
Cependant, la création d’itinéraires permanents pour tous les sous-réseaux peut ne pas être nécessaire si les routeurs de votre réseau sont configurés de manière à résumer les itinéraires. Créez un itinéraire permanent au réseau où le routeur est défini et utilisez le routeur comme passerelle par défaut. Si vous n’êtes pas sûr du mode de configuration de votre réseau et que vous avez besoin d’aide concernant les itinéraires permanents à créer, contactez les ingénieurs réseau de votre entreprise.<br />
Le proxy inverse doit être en mesure de résoudre les enregistrements d’hôte DNS (A) pour le directeur ou le serveur frontal interne et les noms de domaine complets du pool de tronçon suivant utilisés dans les règles de publication web. Comme pour les serveurs Edge, il est préférable que vous ne configuriez pas un proxy inverse pour l’utilisation d’un serveur DNS situé sur le réseau interne à des fins de sécurité. Cela signifie que vous devez utiliser soit des serveurs DNS dans le périmètre, soit des entrées de fichier HOSTS sur le proxy inverse qui résout chacun de ces noms de domaine complets en adresse IP interne des serveurs.

## Pour configurer les cartes réseau sur l’ordinateur de proxy inverse

1.  Sur le serveur Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2 exécuté comme proxy inverse, ouvrez **Modifier les paramètres de la carte** . Pour ce faire, cliquez sur **Démarrer** , pointez sur **Panneau de configuration** , cliquez sur **Centre Réseau et partage** , puis sur **Modifier les paramètres de la carte** .

2.  Cliquez avec le bouton droit sur la connexion réseau externe que vous souhaitez utiliser pour l’interface externe, puis cliquez sur **Propriétés** .

3.  Dans la page **Propriétés** , cliquez sur l’onglet **Réseau** , cliquez sur **Protocole Internet version 4 (TCP/IPv4)** dans la liste **Cette connexion utilise les éléments suivants** , puis cliquez sur **Propriétés** .

4.  Dans la page **Propriétés du protocole Internet (TCP/IP)** , configurez les adresses IP comme il convient pour le sous-réseau auquel la carte réseau est associée.
    
    > [!NOTE]  
    > Si le proxy inverse est déjà utilisé par d’autres applications recourant à HTTPS/TCP/443, comme pour la publication d’Outlook Web Access, soit vous devez ajouter une autre adresse IP afin de pouvoir publier les services web Lync Server 2013 sur HTTPS//TCP/443 sans interférer avec les règles existantes et les ports d’écoute web, soit vous devez remplacer le certificat existant par un autre certificat qui ajoute les noms de domaine complets externes à l’autre nom du sujet.

5.  Cliquez sur **OK** , puis sur **OK** .

6.  Dans **Connexions réseau** , cliquez avec le bouton droit sur la connexion réseau interne que vous souhaitez utiliser pour l’interface interne, puis cliquez sur **Propriétés** .

7.  Répétez les étapes 3 à 5 pour configurer la connexion au réseau interne.

